# paper

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

<!-- 
name: Paper
on:
  push:
    branches:
      - main
jobs:
  build:
    name: Build Web
    env:
      my_secret: ${{secrets.commit_secret}}
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - uses: subosito/flutter-action@v1
        with:
          channel: 'stable'
      - run: flutter config --enable-web
      - run: flutter clean
      - run: flutter pub get
      # base ref need to remove or change manually(./)
      - run: flutter build web --release --web-renderer html --base-href /paper/
      - run: |
          cd build/web
          git init
          git config --global user.email morningos@foxmail.com
          git config --global user.name iMorning
          git status
          git remote add origin https://${{secrets.commit_secret}}@github.com/morningos/paper.git
          git checkout -b gh-pages
          git add --all
          git commit -m "update"
          git push origin gh-pages -f 
-->