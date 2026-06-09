# GetPowerChangeSource

- ea: `0x1800116e0`
- end: `0x1800119db`
- name: `GetPowerChangeSource`
- size: `763`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011290`
- `0x180057310`
- `0x1800ac0d0`

## callees

- `0x1800116e0`
- `0x1800119f0`
- `0x180026e68`
- `0x18003a540`
- `0x1800612c8`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001191f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001191f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119d0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001172b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001177a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800117f4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180011858`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001189f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800118d4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001172b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001177a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800117f4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180011858`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001189f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800118d4`

## string_xrefs

- `0x180011822`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`
- `0x180011906`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`
- `0x18001192f`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`
- `0x180011958`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`
- `0x180011981`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`
- `0x18001199c`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`
- `0x1800119b7`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`

## pseudocode

```c
__int64 GetPowerChangeSource()
{
  unsigned int v0; // eax
  char *v1; // rbx
  const char *v2; // r9
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  const char *v8; // r9
  HANDLE TokenHandle; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL IsMember; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  TokenHandle = 0;
  v0 = LocalQueryRpcClientToken(&TokenHandle);
  if ( v0 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x845,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
      (const char *)v0,
      (unsigned int)TokenHandle);
    v1 = (char *)TokenHandle;
LABEL_21:
    if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v1);
    return 0;
  }
  IsMember = 0;
  v1 = (char *)TokenHandle;
  if ( Sid )
  {
    if ( CheckTokenMembership(TokenHandle, Sid, &IsMember) )
    {
      if ( IsMember )
      {
        if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v1);
        return 3;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x849,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
        v2);
    }
  }
  if ( qword_18013F480 )
  {
    if ( CheckTokenMembership(v1, qword_18013F480, &IsMember) )
    {
      if ( IsMember )
      {
        if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v1);
        return 4;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x850,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
        v4);
    }
  }
  if ( !qword_18013F488 )
    goto LABEL_15;
  if ( !CheckTokenMembership(v1, qword_18013F488, &IsMember) )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x857,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
      v6);
    goto LABEL_15;
  }
  if ( !IsMember )
  {
LABEL_15:
    if ( qword_18013F490 )
    {
      if ( CheckTokenMembership(v1, qword_18013F490, &IsMember) )
      {
        if ( IsMember )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          return 6;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x85E,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
          v7);
      }
    }
    if ( qword_18013F498 )
    {
      if ( CheckTokenMembership(v1, qword_18013F498, &IsMember) )
      {
        if ( IsMember )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          return 9;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x865,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
          v8);
      }
    }
    if ( CheckTokenMembership(v1, qword_18013F468, &IsMember) )
    {
      if ( IsMember )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return 7;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x86C,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
        v5);
    }
    goto LABEL_21;
  }
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v1);
  return 5;
}

```

## disassembly

```asm
0x1800116e0  push    rbx
0x1800116e2  sub     rsp, 40h
0x1800116e6  mov     rax, cs:__security_cookie
0x1800116ed  xor     rax, rsp
0x1800116f0  mov     [rsp+48h+var_18], rax
0x1800116f5  xor     ebx, ebx
0x1800116f7  lea     rcx, [rsp+48h+TokenHandle]; void **
0x1800116fc  mov     [rsp+48h+TokenHandle], rbx; unsigned int
0x180011701  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x180011706  test    eax, eax
0x180011708  jnz     loc_18001181D
0x18001170e  mov     rdx, cs:Sid; SidToCheck
0x180011715  mov     [rsp+48h+IsMember], ebx
0x180011719  mov     rbx, [rsp+48h+TokenHandle]
0x18001171e  test    rdx, rdx
0x180011721  jz      short loc_180011766
0x180011723  lea     r8, [rsp+48h+IsMember]; IsMember
0x180011728  mov     rcx, rbx; TokenHandle
0x18001172b  call    cs:__imp_CheckTokenMembership
0x180011731  test    eax, eax
0x180011733  jz      loc_180011901
0x180011739  cmp     [rsp+48h+IsMember], 0
0x18001173e  jz      short loc_180011766
0x180011740  lea     rax, [rbx-1]
0x180011744  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011748  jbe     loc_18001191C
0x18001174e  mov     eax, 3
0x180011753  mov     rcx, [rsp+48h+var_18]
0x180011758  xor     rcx, rsp; StackCookie
0x18001175b  call    __security_check_cookie
0x180011760  add     rsp, 40h
0x180011764  pop     rbx
0x180011765  retn
0x180011766  mov     rdx, cs:qword_18013F480; SidToCheck
0x18001176d  test    rdx, rdx
0x180011770  jz      short loc_1800117B5
0x180011772  lea     r8, [rsp+48h+IsMember]; IsMember
0x180011777  mov     rcx, rbx; TokenHandle
0x18001177a  call    cs:__imp_CheckTokenMembership
0x180011780  test    eax, eax
0x180011782  jz      loc_18001192A
0x180011788  cmp     [rsp+48h+IsMember], 0
0x18001178d  jz      short loc_1800117B5
0x18001178f  lea     rax, [rbx-1]
0x180011793  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011797  jbe     loc_180011945
0x18001179d  mov     eax, 4
0x1800117a2  mov     rcx, [rsp+48h+var_18]
0x1800117a7  xor     rcx, rsp; StackCookie
0x1800117aa  call    __security_check_cookie
0x1800117af  add     rsp, 40h
0x1800117b3  pop     rbx
0x1800117b4  retn
0x1800117b5  mov     rdx, cs:qword_18013F488; SidToCheck
0x1800117bc  test    rdx, rdx
0x1800117bf  jnz     loc_180011850
0x1800117c5  mov     rdx, cs:qword_18013F490; SidToCheck
0x1800117cc  test    rdx, rdx
0x1800117cf  jnz     loc_180011897
0x1800117d5  mov     rdx, cs:qword_18013F498; SidToCheck
0x1800117dc  test    rdx, rdx
0x1800117df  jnz     loc_1800118CC
0x1800117e5  mov     rdx, cs:qword_18013F468; SidToCheck
0x1800117ec  lea     r8, [rsp+48h+IsMember]; IsMember
0x1800117f1  mov     rcx, rbx; TokenHandle
0x1800117f4  call    cs:__imp_CheckTokenMembership
0x1800117fa  test    eax, eax
0x1800117fc  jz      loc_1800119B2
0x180011802  cmp     [rsp+48h+IsMember], 0
0x180011807  jz      short loc_18001183B
0x180011809  lea     rcx, [rsp+48h+TokenHandle]
0x18001180e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011813  mov     eax, 7
0x180011818  jmp     loc_180011753
0x18001181d  mov     rcx, [rsp+48h]; this
0x180011822  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180011829  mov     r9d, eax; char *
0x18001182c  mov     edx, 845h; void *
0x180011831  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180011836  mov     rbx, [rsp+48h+TokenHandle]
0x18001183b  lea     rax, [rbx-1]
0x18001183f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011843  jbe     loc_1800119CD
0x180011849  xor     eax, eax
0x18001184b  jmp     loc_180011753
0x180011850  lea     r8, [rsp+48h+IsMember]; IsMember
0x180011855  mov     rcx, rbx; TokenHandle
0x180011858  call    cs:__imp_CheckTokenMembership
0x18001185e  test    eax, eax
0x180011860  jz      loc_180011953
0x180011866  cmp     [rsp+48h+IsMember], 0
0x18001186b  jz      loc_1800117C5
0x180011871  lea     rax, [rbx-1]
0x180011875  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011879  jbe     loc_18001196E
0x18001187f  mov     eax, 5
0x180011884  mov     rcx, [rsp+48h+var_18]
0x180011889  xor     rcx, rsp; StackCookie
0x18001188c  call    __security_check_cookie
0x180011891  add     rsp, 40h
0x180011895  pop     rbx
0x180011896  retn
0x180011897  lea     r8, [rsp+48h+IsMember]; IsMember
0x18001189c  mov     rcx, rbx; TokenHandle
0x18001189f  call    cs:__imp_CheckTokenMembership
0x1800118a5  test    eax, eax
0x1800118a7  jz      loc_18001197C
0x1800118ad  cmp     [rsp+48h+IsMember], 0
0x1800118b2  jz      loc_1800117D5
0x1800118b8  lea     rcx, [rsp+48h+TokenHandle]
0x1800118bd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800118c2  mov     eax, 6
0x1800118c7  jmp     loc_180011753
0x1800118cc  lea     r8, [rsp+48h+IsMember]; IsMember
0x1800118d1  mov     rcx, rbx; TokenHandle
0x1800118d4  call    cs:__imp_CheckTokenMembership
0x1800118da  test    eax, eax
0x1800118dc  jz      loc_180011997
0x1800118e2  cmp     [rsp+48h+IsMember], 0
0x1800118e7  jz      loc_1800117E5
0x1800118ed  lea     rcx, [rsp+48h+TokenHandle]
0x1800118f2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800118f7  mov     eax, 9
0x1800118fc  jmp     loc_180011753
0x180011901  mov     rcx, [rsp+48h]; this
0x180011906  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18001190d  mov     edx, 849h; void *
0x180011912  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180011917  jmp     loc_180011766
0x18001191c  mov     rcx, rbx; hObject
0x18001191f  call    cs:__imp_CloseHandle
0x180011925  jmp     loc_18001174E
0x18001192a  mov     rcx, [rsp+48h]; this
0x18001192f  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180011936  mov     edx, 850h; void *
0x18001193b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180011940  jmp     loc_1800117B5
0x180011945  mov     rcx, rbx; hObject
0x180011948  call    cs:__imp_CloseHandle
0x18001194e  jmp     loc_18001179D
0x180011953  mov     rcx, [rsp+48h]; this
0x180011958  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18001195f  mov     edx, 857h; void *
0x180011964  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180011969  jmp     loc_1800117C5
0x18001196e  mov     rcx, rbx; hObject
0x180011971  call    cs:__imp_CloseHandle
0x180011977  jmp     loc_18001187F
0x18001197c  mov     rcx, [rsp+48h]; this
0x180011981  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x180011988  mov     edx, 85Eh; void *
0x18001198d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180011992  jmp     loc_1800117D5
0x180011997  mov     rcx, [rsp+48h]; this
0x18001199c  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800119a3  mov     edx, 865h; void *
0x1800119a8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800119ad  jmp     loc_1800117E5
0x1800119b2  mov     rcx, [rsp+48h]; this
0x1800119b7  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800119be  mov     edx, 86Ch; void *
0x1800119c3  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800119c8  jmp     loc_18001183B
0x1800119cd  mov     rcx, rbx; hObject
0x1800119d0  call    cs:__imp_CloseHandle
0x1800119d6  jmp     loc_180011849
```
