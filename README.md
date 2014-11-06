# 라이선스 고르기 웹사이트 [![Build Status](https://travis-ci.org/codenamu/choosealicense.kr.svg?branch=gh-pages)](https://travis-ci.org/codenamu/choosealicense.kr)


모험 고르기 사이트 같지만, 단지 훨씬 덜 재밌다는 점.
Like a Choose Your Own Adventure site, but only much less interesting.

# 소개
# Intro

깃헙에 있는 많은 레포지토리들이 라이선스가 없어요. 깃헙은 라이선스 선택기를 제공하는데,
정작 사용자가 라이선스에 대해 아무것도 모르면, 어떻게 생각하고 결정할 수 있겠어요?
A lot of repositories on GitHub.com don't have a license. GitHub provides
a license chooser, but if you don't know anything about licenses, how are you
supposed to make an informed decision?

ChooseALicense.kr은 사람들이 라이선스에 대해 충분히 생각하고 결정할 수 있도록 돕기 위해 만들었어요.
ChooseALicense.com is designed to help people make an informed decision about
licenses.

# 당장 목표
# Immediate Goals

* 장인 아님. 우리 목표는 단지 *너*의 목표에 맞는 라이선스를 찾을 수 있도록 돕는 거임.
* Non-partisan. Our goal is to help you find a license that meets *your* goals.
* 잘 디자인해서 말하지 않아도 알도록.
* Well designed, but that goes without saying.
* 홈페이지는 1%가 아니라 99%의 횽아들이 결정을 내릴 수 있도록 도와야 함.
* The homepage should have just enough to help 99% of folks make a decision.
* 1%를 위해서 사이트에는 특정 커뮤니티와 상황에 많이 사용하는 라이선스 목록을 찾을 수 있음.
* For the 1%, the site will contain a list of licenses common to specific
communities and situations.
* 전부 다 하는 건 아님. 약간 이상해보일 수도 있지만 저 바깥에는 열라 많은 라이선스가 있으니까,
우리는 중요한 라이선스만 뽑아서 되도록 스크롤 짧은 목록만 제공할 거임..
* Not comprehensive. Seems like an odd goal, but there are a bajillion
licenses out there. We're going to have to filter that down to a
small list of those that matter.

# 니 컴터에서 돌리기
# Run It On Your Machine

```bash
git clone https://github.com/github/choosealicense.com.git
cd choosealicense.com
script/bootstrap
script/server
```
Open `http://localhost:4000` in your favorite browser.

# 라이선스 추가하기
# Adding a license

The text of the license should be wrapped to a 78 character width.

Licenses sit in the `/licenses` folder. Each license has YAML front matter
describing the license's properties. The body of the file should be the text
of the license in plain text. The available metadata fields are:

* `title` - The name of the license
* `layout` - This should be `license`
* `permalink` - The absolute URL to the license, beginning with `/licenses/`
* `source` - URL to the license source text
* `note` - The note field in the sidebar (optional)
* `how` - How to use the license, also in the sidebar
* `required`, `permitted`, `forbidden` - bulleted list of rules applicable to the license (see below)
* `filename` - The filename to be created on GitHub.com when a repository is initialized with this license.

The licenses on choosealicense.com are regularly imported to GitHub.com to be
used as the list of licenses available when creating a repository. When we
create a repository, we will replace certain strings in the license with
variables from the repository. These can be used to create accurate copyright
notices. The available variables are:

* `[fullname]` - The full name or username of the repository owner
* `[login]` - The repository owner's username
* `[email]` - The repository owner's primary email address
* `[project]` - The repository name
* `[description]` - The description of the repository
* `[year]` - The current year

# Rules

Rules (the license's properties) are stored as a bulleted list within the
licenses YAML front matter. A full list of rules can be found in the
repository's `_config.yml` file. Each rule has a name e.g.,
`include-copyright`, a human-readable label, e.g., `Copyright inclusion`,
and a description `Include the original copyright with the code`.
To add a new rule, simply add it to `config.yml` and reference it in the
appropriate license.

# License

The content of this project itself is licensed under the
[Creative Commons Attribution 3.0 license](http://creativecommons.org/licenses/by/3.0/us/deed.en_US),
and the underlying source code used to format and display that content
is licensed under the [MIT license](http://opensource.org/licenses/mit-license.php).
