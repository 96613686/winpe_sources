# Windows::System::Internal::UserProfile::LoadFromRegistry(HKEY__ *)

- ea: `0x18004f294`
- end: `0x18004f769`
- name: `?LoadFromRegistry@UserProfile@Internal@System@Windows@@AEAAJPEAUHKEY__@@@Z`
- size: `1237`
- prototype: `int(Windows::System::Internal::UserProfile *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ceb24`
- `0x1800cf450`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180040bec`
- `0x18004df20`
- `0x18004f294`
- `0x18004f770`
- `0x180053638`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f2b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f3cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f2b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f3cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f653`

## string_xrefs

- `0x18004f301`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f34c`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f3b1`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f407`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f44e`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f498`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f4df`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f529`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f582`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f5db`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f634`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f68d`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f6e3`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004f743`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Internal::UserProfile::LoadFromRegistry(
        Windows::System::Internal::UserProfile *this,
        HKEY a2)
{
  HSTRING *v4; // rbx
  unsigned int v5; // eax
  char v6; // di
  char v7; // cl
  unsigned int v8; // eax
  char v9; // cl
  unsigned int v10; // eax
  char v11; // cl
  unsigned int v12; // eax
  char v13; // cl
  unsigned int v14; // eax
  char v15; // cl
  unsigned int v16; // eax
  char v17; // cl
  unsigned int v18; // eax
  char v19; // cl
  unsigned int v20; // eax
  char v21; // cl
  unsigned int v22; // eax
  char v23; // cl
  unsigned int v24; // eax
  char v25; // cl
  unsigned int v26; // eax
  char v27; // cl
  unsigned int v28; // eax
  char v29; // cl
  unsigned int v30; // r14d
  int Values; // eax
  _QWORD v33[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v4 = (HSTRING *)((char *)this + 120);
  WindowsDeleteString(*((HSTRING *)this + 15));
  *v4 = 0;
  v5 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(a2, L"Sid", v4);
  v6 = 1;
  if ( (int)(v5 + 0x80000000) < 0 || (v7 = 1, v5 == -2147024894) )
    v7 = 0;
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v5,
      v33[0]);
  v8 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned char>(a2);
  if ( ((v8 + 0x80000000) & 0x80000000) != 0 || (v9 = 1, v8 == -2147024894) )
    v9 = 0;
  if ( v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v8,
      v33[0]);
  if ( !*((_DWORD *)this + 21) )
    *((_BYTE *)this + 129) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  v10 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(
          a2,
          L"ProfileName",
          (HSTRING *)this + 11);
  if ( ((v10 + 0x80000000) & 0x80000000) != 0 || (v11 = 1, v10 == -2147024894) )
    v11 = 0;
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v10,
      v33[0]);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  v12 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(
          a2,
          L"EmailAddress",
          (HSTRING *)this + 12);
  if ( ((v12 + 0x80000000) & 0x80000000) != 0 || (v13 = 1, v12 == -2147024894) )
    v13 = 0;
  if ( v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v12,
      v33[0]);
  v14 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned char>(a2);
  if ( ((v14 + 0x80000000) & 0x80000000) != 0 || (v15 = 1, v14 == -2147024894) )
    v15 = 0;
  if ( v15 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v14,
      v33[0]);
  v16 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned char>(a2);
  if ( ((v16 + 0x80000000) & 0x80000000) != 0 || (v17 = 1, v16 == -2147024894) )
    v17 = 0;
  if ( v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v16,
      v33[0]);
  v18 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned char>(a2);
  if ( ((v18 + 0x80000000) & 0x80000000) != 0 || (v19 = 1, v18 == -2147024894) )
    v19 = 0;
  if ( v19 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v18,
      v33[0]);
  v20 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned long>(
          a2,
          L"UserTypeInternal",
          (LPBYTE)this + 132);
  if ( ((v20 + 0x80000000) & 0x80000000) != 0 || (v21 = 1, v20 == -2147024894) )
    v21 = 0;
  if ( v21 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v20,
      v33[0]);
  WindowsDeleteString(*((HSTRING *)this + 17));
  *((_QWORD *)this + 17) = 0;
  v22 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(
          a2,
          L"DisplayName",
          (HSTRING *)this + 17);
  if ( ((v22 + 0x80000000) & 0x80000000) != 0 || (v23 = 1, v22 == -2147024894) )
    v23 = 0;
  if ( v23 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v22,
      v33[0]);
  WindowsDeleteString(*((HSTRING *)this + 18));
  *((_QWORD *)this + 18) = 0;
  v24 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(
          a2,
          L"FirstName",
          (HSTRING *)this + 18);
  if ( ((v24 + 0x80000000) & 0x80000000) != 0 || (v25 = 1, v24 == -2147024894) )
    v25 = 0;
  if ( v25 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v24,
      v33[0]);
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  v26 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(
          a2,
          L"LastName",
          (HSTRING *)this + 19);
  if ( ((v26 + 0x80000000) & 0x80000000) != 0 || (v27 = 1, v26 == -2147024894) )
    v27 = 0;
  if ( v27 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v26,
      v33[0]);
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  v28 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(
          a2,
          L"UserPicture",
          (HSTRING *)this + 20);
  if ( ((v28 + 0x80000000) & 0x80000000) != 0 || (v29 = 1, v28 == -2147024894) )
    v29 = 0;
  if ( v29 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v28,
      v33[0]);
  v30 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned char>(a2);
  if ( (int)(v30 + 0x80000000) < 0 || v30 == -2147024894 || *((_DWORD *)this + 21) )
    v6 = 0;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)v30,
      v33[0]);
  if ( !*((_DWORD *)this + 21) )
    *((_BYTE *)this + 130) = 0;
  v33[0] = off_1800EDFD0;
  v33[3] = v33;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 112);
  Values = Windows::System::Internal::Implementation::RegUtil::ReadValues(a2);
  if ( Values < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)Values,
      v33[0]);
  return v30;
}

```

## disassembly

```asm
0x18004f294  push    rbp
0x18004f296  push    rbx
0x18004f297  push    rsi
0x18004f298  push    rdi
0x18004f299  push    r12
0x18004f29b  push    r13
0x18004f29d  push    r14
0x18004f29f  push    r15
0x18004f2a1  mov     rbp, rsp
0x18004f2a4  sub     rsp, 48h
0x18004f2a8  mov     r15, rdx
0x18004f2ab  mov     rsi, rcx
0x18004f2ae  lea     rbx, [rcx+78h]
0x18004f2b2  mov     rcx, [rbx]; string
0x18004f2b5  call    cs:__imp_WindowsDeleteString
0x18004f2bb  xor     r12d, r12d
0x18004f2be  mov     [rbx], r12
0x18004f2c1  mov     r8, rbx; string
0x18004f2c4  lea     rdx, aSid_2; "Sid"
0x18004f2cb  mov     rcx, r15; hKey
0x18004f2ce  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004f2d3  mov     r14d, 80000000h
0x18004f2d9  lea     ecx, [rax+r14]
0x18004f2dd  mov     dil, 1
0x18004f2e0  mov     r13d, 80070002h
0x18004f2e6  test    r14d, ecx
0x18004f2e9  jnz     short loc_18004F2F3
0x18004f2eb  cmp     eax, r13d
0x18004f2ee  mov     cl, dil
0x18004f2f1  jnz     short loc_18004F2F6
0x18004f2f3  mov     cl, r12b
0x18004f2f6  mov     r10, [rbp+40h]
0x18004f2fa  test    cl, cl
0x18004f2fc  jz      short loc_18004F316
0x18004f2fe  mov     r9d, eax; char *
0x18004f301  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f308  mov     edx, 121h; void *
0x18004f30d  mov     rcx, r10; this
0x18004f310  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f316  mov     byte ptr [rbp+arg_0], r12b
0x18004f31a  lea     r8, [rbp+arg_0]
0x18004f31e  lea     rdx, aIsnewuser; "IsNewUser"
0x18004f325  mov     rcx, r15; hKey
0x18004f328  call    ??$ReadValue@E@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAE@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<uchar>(HKEY__ *,ushort const *,uchar *)
0x18004f32d  lea     ecx, [rax+r14]
0x18004f331  test    r14d, ecx
0x18004f334  jnz     short loc_18004F33E
0x18004f336  cmp     eax, r13d
0x18004f339  mov     cl, dil
0x18004f33c  jnz     short loc_18004F341
0x18004f33e  mov     cl, r12b
0x18004f341  mov     r10, [rbp+40h]
0x18004f345  test    cl, cl
0x18004f347  jz      short loc_18004F361
0x18004f349  mov     r9d, eax; char *
0x18004f34c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f353  mov     edx, 125h; void *
0x18004f358  mov     rcx, r10; this
0x18004f35b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f361  cmp     [rsi+54h], r12d
0x18004f365  jnz     short loc_18004F370
0x18004f367  mov     al, byte ptr [rbp+arg_0]
0x18004f36a  mov     [rsi+81h], al
0x18004f370  lea     rbx, [rsi+58h]
0x18004f374  mov     rcx, [rbx]; string
0x18004f377  call    cs:__imp_WindowsDeleteString
0x18004f37d  mov     [rbx], r12
0x18004f380  mov     r8, rbx; string
0x18004f383  lea     rdx, aProfilename_0; "ProfileName"
0x18004f38a  mov     rcx, r15; hKey
0x18004f38d  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004f392  lea     ecx, [rax+r14]
0x18004f396  test    r14d, ecx
0x18004f399  jnz     short loc_18004F3A3
0x18004f39b  cmp     eax, r13d
0x18004f39e  mov     cl, dil
0x18004f3a1  jnz     short loc_18004F3A6
0x18004f3a3  mov     cl, r12b
0x18004f3a6  mov     r10, [rbp+40h]
0x18004f3aa  test    cl, cl
0x18004f3ac  jz      short loc_18004F3C6
0x18004f3ae  mov     r9d, eax; char *
0x18004f3b1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f3b8  mov     edx, 12Ch; void *
0x18004f3bd  mov     rcx, r10; this
0x18004f3c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f3c6  lea     rbx, [rsi+60h]
0x18004f3ca  mov     rcx, [rbx]; string
0x18004f3cd  call    cs:__imp_WindowsDeleteString
0x18004f3d3  mov     [rbx], r12
0x18004f3d6  mov     r8, rbx; string
0x18004f3d9  lea     rdx, aEmailaddress; "EmailAddress"
0x18004f3e0  mov     rcx, r15; hKey
0x18004f3e3  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004f3e8  lea     ecx, [rax+r14]
0x18004f3ec  test    r14d, ecx
0x18004f3ef  jnz     short loc_18004F3F9
0x18004f3f1  cmp     eax, r13d
0x18004f3f4  mov     cl, dil
0x18004f3f7  jnz     short loc_18004F3FC
0x18004f3f9  mov     cl, r12b
0x18004f3fc  mov     r10, [rbp+40h]
0x18004f400  test    cl, cl
0x18004f402  jz      short loc_18004F41C
0x18004f404  mov     r9d, eax; char *
0x18004f407  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f40e  mov     edx, 12Fh; void *
0x18004f413  mov     rcx, r10; this
0x18004f416  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f41c  lea     r8, [rsi+69h]
0x18004f420  lea     rdx, aPersistcreds; "PersistCreds"
0x18004f427  mov     rcx, r15; hKey
0x18004f42a  call    ??$ReadValue@E@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAE@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<uchar>(HKEY__ *,ushort const *,uchar *)
0x18004f42f  lea     ecx, [rax+r14]
0x18004f433  test    r14d, ecx
0x18004f436  jnz     short loc_18004F440
0x18004f438  cmp     eax, r13d
0x18004f43b  mov     cl, dil
0x18004f43e  jnz     short loc_18004F443
0x18004f440  mov     cl, r12b
0x18004f443  mov     r10, [rbp+40h]
0x18004f447  test    cl, cl
0x18004f449  jz      short loc_18004F463
0x18004f44b  mov     r9d, eax; char *
0x18004f44e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f455  mov     edx, 132h; void *
0x18004f45a  mov     rcx, r10; this
0x18004f45d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f463  lea     r8, [rsi+80h]
0x18004f46a  lea     rdx, aSysmanaged; "SysManaged"
0x18004f471  mov     rcx, r15; hKey
0x18004f474  call    ??$ReadValue@E@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAE@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<uchar>(HKEY__ *,ushort const *,uchar *)
0x18004f479  lea     ecx, [rax+r14]
0x18004f47d  test    r14d, ecx
0x18004f480  jnz     short loc_18004F48A
0x18004f482  cmp     eax, r13d
0x18004f485  mov     cl, dil
0x18004f488  jnz     short loc_18004F48D
0x18004f48a  mov     cl, r12b
0x18004f48d  mov     r10, [rbp+40h]
0x18004f491  test    cl, cl
0x18004f493  jz      short loc_18004F4AD
0x18004f495  mov     r9d, eax; char *
0x18004f498  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f49f  mov     edx, 135h; void *
0x18004f4a4  mov     rcx, r10; this
0x18004f4a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f4ad  lea     r8, [rsi+68h]
0x18004f4b1  lea     rdx, aAutosignin; "AutoSignIn"
0x18004f4b8  mov     rcx, r15; hKey
0x18004f4bb  call    ??$ReadValue@E@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAE@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<uchar>(HKEY__ *,ushort const *,uchar *)
0x18004f4c0  lea     ecx, [rax+r14]
0x18004f4c4  test    r14d, ecx
0x18004f4c7  jnz     short loc_18004F4D1
0x18004f4c9  cmp     eax, r13d
0x18004f4cc  mov     cl, dil
0x18004f4cf  jnz     short loc_18004F4D4
0x18004f4d1  mov     cl, r12b
0x18004f4d4  mov     r10, [rbp+40h]
0x18004f4d8  test    cl, cl
0x18004f4da  jz      short loc_18004F4F4
0x18004f4dc  mov     r9d, eax; char *
0x18004f4df  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f4e6  mov     edx, 138h; void *
0x18004f4eb  mov     rcx, r10; this
0x18004f4ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f4f4  lea     r8, [rsi+84h]; lpData
0x18004f4fb  lea     rdx, aUsertypeintern_0; "UserTypeInternal"
0x18004f502  mov     rcx, r15; hKey
0x18004f505  call    ??$ReadValue@K@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAK@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<ulong>(HKEY__ *,ushort const *,ulong *)
0x18004f50a  lea     ecx, [rax+r14]
0x18004f50e  test    r14d, ecx
0x18004f511  jnz     short loc_18004F51B
0x18004f513  cmp     eax, r13d
0x18004f516  mov     cl, dil
0x18004f519  jnz     short loc_18004F51E
0x18004f51b  mov     cl, r12b
0x18004f51e  mov     r10, [rbp+40h]
0x18004f522  test    cl, cl
0x18004f524  jz      short loc_18004F53E
0x18004f526  mov     r9d, eax; char *
0x18004f529  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f530  mov     edx, 13Bh; void *
0x18004f535  mov     rcx, r10; this
0x18004f538  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f53e  lea     rbx, [rsi+88h]
0x18004f545  mov     rcx, [rbx]; string
0x18004f548  call    cs:__imp_WindowsDeleteString
0x18004f54e  mov     [rbx], r12
0x18004f551  mov     r8, rbx; string
0x18004f554  lea     rdx, aDisplayname_0; "DisplayName"
0x18004f55b  mov     rcx, r15; hKey
0x18004f55e  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004f563  lea     ecx, [rax+r14]
0x18004f567  test    r14d, ecx
0x18004f56a  jnz     short loc_18004F574
0x18004f56c  cmp     eax, r13d
0x18004f56f  mov     cl, dil
0x18004f572  jnz     short loc_18004F577
0x18004f574  mov     cl, r12b
0x18004f577  mov     r10, [rbp+40h]
0x18004f57b  test    cl, cl
0x18004f57d  jz      short loc_18004F597
0x18004f57f  mov     r9d, eax; char *
0x18004f582  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f589  mov     edx, 13Eh; void *
0x18004f58e  mov     rcx, r10; this
0x18004f591  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f597  lea     rbx, [rsi+90h]
0x18004f59e  mov     rcx, [rbx]; string
0x18004f5a1  call    cs:__imp_WindowsDeleteString
0x18004f5a7  mov     [rbx], r12
0x18004f5aa  mov     r8, rbx; string
0x18004f5ad  lea     rdx, aFirstname_0; "FirstName"
0x18004f5b4  mov     rcx, r15; hKey
0x18004f5b7  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004f5bc  lea     ecx, [rax+r14]
0x18004f5c0  test    r14d, ecx
0x18004f5c3  jnz     short loc_18004F5CD
0x18004f5c5  cmp     eax, r13d
0x18004f5c8  mov     cl, dil
0x18004f5cb  jnz     short loc_18004F5D0
0x18004f5cd  mov     cl, r12b
0x18004f5d0  mov     r10, [rbp+40h]
0x18004f5d4  test    cl, cl
0x18004f5d6  jz      short loc_18004F5F0
0x18004f5d8  mov     r9d, eax; char *
0x18004f5db  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f5e2  mov     edx, 141h; void *
0x18004f5e7  mov     rcx, r10; this
0x18004f5ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f5f0  lea     rbx, [rsi+98h]
0x18004f5f7  mov     rcx, [rbx]; string
0x18004f5fa  call    cs:__imp_WindowsDeleteString
0x18004f600  mov     [rbx], r12
0x18004f603  mov     r8, rbx; string
0x18004f606  lea     rdx, aLastname_0; "LastName"
0x18004f60d  mov     rcx, r15; hKey
0x18004f610  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004f615  lea     ecx, [rax+r14]
0x18004f619  test    r14d, ecx
0x18004f61c  jnz     short loc_18004F626
0x18004f61e  cmp     eax, r13d
0x18004f621  mov     cl, dil
0x18004f624  jnz     short loc_18004F629
0x18004f626  mov     cl, r12b
0x18004f629  mov     r10, [rbp+40h]
0x18004f62d  test    cl, cl
0x18004f62f  jz      short loc_18004F649
0x18004f631  mov     r9d, eax; char *
0x18004f634  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f63b  mov     edx, 144h; void *
0x18004f640  mov     rcx, r10; this
0x18004f643  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f649  lea     rbx, [rsi+0A0h]
0x18004f650  mov     rcx, [rbx]; string
0x18004f653  call    cs:__imp_WindowsDeleteString
0x18004f659  mov     [rbx], r12
0x18004f65c  mov     r8, rbx; string
0x18004f65f  lea     rdx, aUserpicture; "UserPicture"
0x18004f666  mov     rcx, r15; hKey
0x18004f669  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004f66e  lea     ecx, [rax+r14]
0x18004f672  test    r14d, ecx
0x18004f675  jnz     short loc_18004F67F
0x18004f677  cmp     eax, r13d
0x18004f67a  mov     cl, dil
0x18004f67d  jnz     short loc_18004F682
0x18004f67f  mov     cl, r12b
0x18004f682  mov     r10, [rbp+40h]
0x18004f686  test    cl, cl
0x18004f688  jz      short loc_18004F6A2
0x18004f68a  mov     r9d, eax; char *
0x18004f68d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f694  mov     edx, 147h; void *
0x18004f699  mov     rcx, r10; this
0x18004f69c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f6a2  mov     byte ptr [rbp+arg_0], r12b
0x18004f6a6  lea     r8, [rbp+arg_0]
0x18004f6aa  lea     rdx, aDirty; "Dirty"
0x18004f6b1  mov     rcx, r15; hKey
0x18004f6b4  call    ??$ReadValue@E@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAE@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<uchar>(HKEY__ *,ushort const *,uchar *)
0x18004f6b9  mov     r14d, eax
0x18004f6bc  mov     eax, 80000000h
0x18004f6c1  lea     ecx, [r14+rax]
0x18004f6c5  test    eax, ecx
0x18004f6c7  jnz     short loc_18004F6D4
0x18004f6c9  cmp     r14d, r13d
0x18004f6cc  jz      short loc_18004F6D4
0x18004f6ce  cmp     [rsi+54h], r12d
0x18004f6d2  jz      short loc_18004F6D7
0x18004f6d4  mov     dil, r12b
0x18004f6d7  mov     rcx, [rbp+40h]; this
0x18004f6db  test    dil, dil
0x18004f6de  jz      short loc_18004F6F5
0x18004f6e0  mov     r9d, r14d; char *
0x18004f6e3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f6ea  mov     edx, 14Bh; void *
0x18004f6ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f6f5  cmp     [rsi+54h], r12d
  ... truncated ...
```
