sample/: プロジェクト名とパッケージ名が同じディレクトリ

venv/: 仮想環境ディレクトリ

manage.py: Django プロジェクトを操作するためのコマンドラインユーティリティ


## アプリの作成

python manage.py startapp myapp

これで myapp という名前のアプリケーションが作成されます。
※実際のプロジェクトでは、このアプリケーションが担う機能の名称にするのが良い

## 設定ファイル

次に sample/settings.py ファイルを編集して、作成したアプリケーションを有効化します。
INSTALLED_APPS の配列に 'myapp' を追加します。

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'myapp', # 追加
]
また、 LANGUAGE_CODE を 'ja' などの日本語コードに変更すれば、Django の管理画面の表示言語を日本語にできます。

LANGUAGE_CODE = 'ja'

## ビューとURLルーティングの設定

この時点で起動することもできますが、せっかくなので Hello World のようなチュートリアルまで行ってしまいましょう。

myapp/views.py ファイルにビューを作成し、 sample/urls.py ファイルでURLルーティングを設定します。
まず myapp/views.py を編集して、ビューを作成します。

from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, Django!")
次に sample/urls.py を編集し、URLルーティングを設定します。

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('myapp.urls')), # 追加
]
最後に myapp/urls.py ファイルを新規作成し、ビューとURLのマッピングを設定します。

from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
これで、ルートのパスが index 関数と紐づきました。


## マイグレーション実行

マイグレーションを実行しましょう。
これにより初期の Django アプリケーションに必要なテーブルがデータベースに作成されます。

特に設定していない場合は、デフォルトで同梱されている sqlite に設定が反映されています。

python manage.py migrate

## サーバーの起動

設定が完了したら、次のコマンドでサーバーを起動できます。

python manage.py runserver

サーバーが起動したら、ブラウザで http://127.0.0.1:8000/ にアクセスすると、Hello, Django! と表示されるはずです。

