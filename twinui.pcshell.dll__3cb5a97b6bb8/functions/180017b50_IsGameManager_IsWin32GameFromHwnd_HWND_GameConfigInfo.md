# IsGameManager::IsWin32GameFromHwnd(HWND__ *,GameConfigInfo *)

- ea: `0x180017b50`
- end: `0x180017f96`
- name: `?IsWin32GameFromHwnd@IsGameManager@@UEAAJPEAUHWND__@@PEAUGameConfigInfo@@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(IsGameManager *__hidden this, HWND hWnd, struct GameConfigInfo *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800134f8`
- `0x180017784`
- `0x180017b50`
- `0x180017fa0`
- `0x180018180`
- `0x1800184dc`
- `0x180019f84`
- `0x1800237c8`
- `0x180031c70`
- `0x1801f1348`
- `0x180300e04`
- `0x180356360`
- `0x18035b7e5`
- `0x18039b174`
- `0x18039b960`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017d2b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017d2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017c74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017c74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017cca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017ecd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017cca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017bfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017bfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017d1f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017b9e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017b9e`

## string_xrefs

- `0x180017db7`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180017df5`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180017e30`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180017ea5`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180017f32`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180017f63`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x1806ec49a`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x1806ec4b6`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsGameManager::IsWin32GameFromHwnd(RTL_SRWLOCK *this, HWND hWnd, struct GameConfigInfo *a3)
{
  int v5; // eax
  unsigned int v6; // r14d
  unsigned int v7; // ebx
  int v8; // r14d
  DWORD v9; // ebx
  struct _GUID v10; // xmm6
  DWORD v11; // r14d
  PVOID Ptr; // rcx
  int IsGameEnabled; // eax
  IsGameManager *v14; // rcx
  HSTRING v15; // rcx
  PCWSTR StringRawBuffer; // rax
  int v18; // eax
  PVOID v19; // rcx
  int v20; // eax
  int StringFromGameConfigStore; // eax
  int updated; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  PVOID v26; // rcx
  int v27; // eax
  int v28; // [rsp+28h] [rbp-59h]
  bool v29; // [rsp+48h] [rbp-39h] BYREF
  HSTRING string; // [rsp+50h] [rbp-31h] BYREF
  DWORD dwProcessId[4]; // [rsp+58h] [rbp-29h] BYREF
  struct _GUID Buf1; // [rsp+68h] [rbp-19h] BYREF
  struct _GUID v33; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  dwProcessId[0] = 0;
  *(_WORD *)a3 = 0;
  *((_BYTE *)a3 + 2) = 0;
  GetWindowThreadProcessId(hWnd, dwProcessId);
  string = 0;
  *((_BYTE *)a3 + 2) = 0;
  v5 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, _QWORD, HSTRING *))this->Ptr + 13))(this, dwProcessId[0], &string);
  v6 = v5;
  v7 = -2147024891;
  if ( v5 == -2147024891 || (v7 = -2147024809, v5 == -2147024809) )
  {
    if ( string )
      WindowsDeleteString(string);
    return v7;
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x811,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v5,
      v28);
    if ( string )
      WindowsDeleteString(string);
    return v6;
  }
  v8 = 0;
  if ( !*((_BYTE *)a3 + 2) )
  {
    do
    {
      if ( v8 )
        break;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v18 = _o__wcsicmp(StringRawBuffer, g_rgExplorerApps);
      *((_BYTE *)a3 + 2) = v18 == 0;
      v8 = 1;
    }
    while ( v18 );
  }
  if ( string )
    WindowsDeleteString(string);
  if ( *((_BYTE *)a3 + 2) )
    return 0;
  v9 = dwProcessId[0];
  v33 = (struct _GUID)xmmword_180769B30;
  LODWORD(string) = 0;
  *(_BYTE *)a3 = 0;
  *((_BYTE *)a3 + 4) = 0;
  v10 = (struct _GUID)xmmword_180769B30;
  Windows::Internal::String::Release((struct GameConfigInfo *)((char *)a3 + 32));
  if ( (*(int (__fastcall **)(PVOID, _QWORD, struct _GUID *))(*(_QWORD *)this[2].Ptr + 32LL))(this[2].Ptr, v9, &v33) < 0
    || (Buf1 = v33,
        (int)IsGameManager::IsEnabledInGameConfigStore(
               (IsGameManager *)this,
               &Buf1,
               (bool *)a3,
               (bool *)a3 + 4,
               (unsigned int *)&string) < 0) )
  {
    v33 = (struct _GUID)xmmword_180769B30;
    Buf1 = (struct _GUID)xmmword_180769B30;
    v11 = dwProcessId[0];
    AcquireSRWLockShared(this + 4);
    string = 0;
    v29 = 0;
    Ptr = this[3].Ptr;
    if ( Ptr )
    {
      IsGameEnabled = (*(__int64 (__fastcall **)(PVOID, _QWORD, HSTRING *))(*(_QWORD *)Ptr + 48LL))(Ptr, v11, &string);
      if ( IsGameEnabled == -2147023728 || IsGameEnabled == -2147024894 )
      {
        v15 = string;
        if ( string )
        {
          string = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      else
      {
        if ( IsGameEnabled >= 0 )
        {
          IsGameEnabled = IsGameManager::IsGameEnabled(v14, (struct KnownGameList::IGameEntry *)string, &v29);
          if ( IsGameEnabled >= 0 )
          {
            if ( !memcmp_0(&Buf1, &xmmword_180769B30, 0x10u) )
            {
              Buf1 = (struct _GUID)xmmword_180769B30;
              updated = IsGameManager::UpdateGameConfigStoreFromKGL(
                          (IsGameManager *)this,
                          (struct KnownGameList::IGameEntry *)string,
                          &Buf1,
                          0,
                          0,
                          (struct GameConfigInfo *)((char *)a3 + 32),
                          &v33);
              if ( updated < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x4A3,
                  (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
                  (const char *)(unsigned int)updated,
                  v28);
              IsGameManager::SendAddGameToConfigStoreTelemetry((IsGameManager *)this, v11);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
            ReleaseSRWLockShared(this + 4);
            *(_BYTE *)a3 = v29;
            if ( memcmp_0(&v33, &xmmword_180769B30, 0x10u) )
              v10 = v33;
            goto LABEL_37;
          }
          v25 = 1178;
        }
        else
        {
          v25 = 1176;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)IsGameEnabled,
          v28);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      }
    }
    ReleaseSRWLockShared(this + 4);
    *(_BYTE *)a3 = 0;
    return 0;
  }
  if ( !(_DWORD)string )
  {
    LODWORD(string) = 1;
    v19 = this[2].Ptr;
    Buf1 = v33;
    v28 = 4;
    v20 = (*(__int64 (__fastcall **)(PVOID, struct _GUID *, _QWORD, HSTRING *))(*(_QWORD *)v19 + 72LL))(
            v19,
            &Buf1,
            0,
            &string);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x478,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)(unsigned int)v20,
        4);
  }
  Buf1 = v33;
  StringFromGameConfigStore = IsGameManager::GetStringFromGameConfigStore(
                                (__int64)this,
                                &Buf1,
                                0xFu,
                                (struct GameConfigInfo *)((char *)a3 + 32));
  if ( StringFromGameConfigStore < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x47D,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)StringFromGameConfigStore,
      v28);
  v10 = v33;
  LODWORD(string) = 0;
  v26 = this[2].Ptr;
  Buf1 = v33;
  v28 = 4;
  v27 = (*(__int64 (__fastcall **)(PVOID, struct _GUID *, __int64, HSTRING *))(*(_QWORD *)v26 + 72LL))(
          v26,
          &Buf1,
          14,
          &string);
  v7 = v27;
  if ( v27 >= 0 )
  {
LABEL_37:
    if ( *(_BYTE *)a3 )
    {
      Buf1 = v10;
      IsGameManager::GetAutoGameModeFromGameConfigStore((IsGameManager *)this, &Buf1, a3);
      Buf1 = v10;
      v23 = IsGameManager::UpdateGameFullPathInGameConfigStore((IsGameManager *)this, dwProcessId[0], &Buf1);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x15B,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)v23,
          v28);
      Buf1 = v10;
      v24 = IsGameManager::UpdateGameLastRunTime((IsGameManager *)this, &Buf1);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x15E,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)v24,
          v28);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x138,
    (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
    (const char *)(unsigned int)v27,
    4);
  return v7;
}

```

## disassembly

```asm
0x180017b50  mov     rax, rsp
0x180017b53  mov     [rax+20h], rbx
0x180017b57  push    rbp
0x180017b58  push    rsi
0x180017b59  push    rdi
0x180017b5a  push    r12
0x180017b5c  push    r13
0x180017b5e  push    r14
0x180017b60  push    r15
0x180017b62  lea     rbp, [rax-5Fh]
0x180017b66  sub     rsp, 0A0h
0x180017b6d  movaps  xmmword ptr [rax-48h], xmm6
0x180017b71  mov     rax, cs:__security_cookie
0x180017b78  xor     rax, rsp
0x180017b7b  mov     [rbp+57h+var_50], rax
0x180017b7f  mov     rsi, r8
0x180017b82  mov     rax, rdx
0x180017b85  mov     rdi, rcx
0x180017b88  xor     r13d, r13d
0x180017b8b  mov     [rbp+57h+dwProcessId], r13d
0x180017b8f  mov     [r8], r13w
0x180017b93  mov     [r8+2], r13b
0x180017b97  lea     rdx, [rbp+57h+dwProcessId]; lpdwProcessId
0x180017b9b  mov     rcx, rax; hWnd
0x180017b9e  call    cs:__imp_GetWindowThreadProcessId
0x180017ba4  mov     [rbp+57h+string], r13
0x180017ba8  mov     [rsi+2], r13b
0x180017bac  mov     rax, [rdi]
0x180017baf  lea     r8, [rbp+57h+string]
0x180017bb3  mov     edx, [rbp+57h+dwProcessId]
0x180017bb6  mov     rcx, rdi
0x180017bb9  mov     rax, [rax+68h]
0x180017bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bc2  mov     r14d, eax
0x180017bc5  mov     ebx, 80070005h
0x180017bca  cmp     eax, ebx
0x180017bcc  jz      loc_180017E1E
0x180017bd2  mov     ebx, 80070057h
0x180017bd7  cmp     eax, ebx
0x180017bd9  jz      loc_180017E1E
0x180017bdf  test    eax, eax
0x180017be1  js      loc_180017E29
0x180017be7  mov     r14d, r13d
0x180017bea  cmp     [rsi+2], r13b
0x180017bee  jz      loc_180017D01
0x180017bf4  mov     rcx, [rbp+57h+string]; string
0x180017bf8  test    rcx, rcx
0x180017bfb  jz      short loc_180017C03
0x180017bfd  call    cs:__imp_WindowsDeleteString
0x180017c03  cmp     [rsi+2], r13b
0x180017c07  jnz     loc_180017CD3
0x180017c0d  lea     r15, [rsi+20h]
0x180017c11  mov     ebx, [rbp+57h+dwProcessId]
0x180017c14  movups  xmm0, cs:xmmword_180769B30
0x180017c1b  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180017c20  mov     dword ptr [rbp+57h+string], r13d
0x180017c24  mov     [rsi], r13b
0x180017c27  mov     [rsi+4], r13b
0x180017c2b  movups  xmm6, cs:xmmword_180769B30
0x180017c32  mov     rcx, r15; this
0x180017c35  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x180017c3a  mov     rcx, [rdi+10h]
0x180017c3e  mov     rax, [rcx]
0x180017c41  lea     r8, [rbp+57h+var_60]
0x180017c45  mov     edx, ebx
0x180017c47  mov     rax, [rax+20h]
0x180017c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c50  test    eax, eax
0x180017c52  jns     loc_180017D45
0x180017c58  movups  xmm0, cs:xmmword_180769B30
0x180017c5f  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180017c64  movdqa  [rbp+57h+Buf1], xmm6
0x180017c69  mov     r14d, [rbp+57h+dwProcessId]
0x180017c6d  lea     rbx, [rdi+20h]
0x180017c71  mov     rcx, rbx; SRWLock
0x180017c74  call    cs:__imp_AcquireSRWLockShared
0x180017c7a  mov     [rbp+57h+string], r13
0x180017c7e  mov     [rbp+57h+var_90], r13b
0x180017c82  mov     rcx, [rdi+18h]
0x180017c86  test    rcx, rcx
0x180017c89  jz      loc_180017E0C
0x180017c8f  mov     rax, [rcx]
0x180017c92  lea     r8, [rbp+57h+string]
0x180017c96  mov     edx, r14d
0x180017c99  mov     rax, [rax+30h]
0x180017c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ca2  cmp     eax, 80070490h
0x180017ca7  jnz     loc_180017F79
0x180017cad  mov     rcx, [rbp+57h+string]
0x180017cb1  test    rcx, rcx
0x180017cb4  jz      short loc_180017CC7
0x180017cb6  mov     [rbp+57h+string], r13
0x180017cba  mov     rax, [rcx]
0x180017cbd  mov     rax, [rax+10h]
0x180017cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cc6  nop
0x180017cc7  mov     rcx, rbx; SRWLock
0x180017cca  call    cs:__imp_ReleaseSRWLockShared
0x180017cd0  mov     [rsi], r13b
0x180017cd3  xor     eax, eax
0x180017cd5  mov     rcx, [rbp+57h+var_50]
0x180017cd9  xor     rcx, rsp; StackCookie
0x180017cdc  call    __security_check_cookie
0x180017ce1  lea     r11, [rsp+0D0h+var_30]
0x180017ce9  mov     rbx, [r11+58h]
0x180017ced  movaps  xmm6, xmmword ptr [r11-10h]
0x180017cf2  mov     rsp, r11
0x180017cf5  pop     r15
0x180017cf7  pop     r14
0x180017cf9  pop     r13
0x180017cfb  pop     r12
0x180017cfd  pop     rdi
0x180017cfe  pop     rsi
0x180017cff  pop     rbp
0x180017d00  retn
0x180017d01  cmp     r14d, 1
0x180017d05  jnb     loc_180017BF4
0x180017d0b  mov     eax, r14d
0x180017d0e  lea     rbx, ?g_rgExplorerApps@@3PAPEBGA; ushort const * near * g_rgExplorerApps
0x180017d15  mov     rbx, [rbx+rax*8]
0x180017d19  xor     edx, edx; length
0x180017d1b  mov     rcx, [rbp+57h+string]; string
0x180017d1f  call    cs:__imp_WindowsGetStringRawBuffer
0x180017d25  mov     rdx, rbx
0x180017d28  mov     rcx, rax
0x180017d2b  call    cs:__imp__o__wcsicmp
0x180017d31  test    eax, eax
0x180017d33  setz    cl
0x180017d36  mov     [rsi+2], cl
0x180017d39  inc     r14d
0x180017d3c  test    eax, eax
0x180017d3e  jnz     short loc_180017D01
0x180017d40  jmp     loc_180017BF4
0x180017d45  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x180017d49  movdqa  [rbp+57h+Buf1], xmm0
0x180017d4e  lea     rax, [rbp+57h+string]
0x180017d52  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x180017d57  lea     r9, [rsi+4]; bool *
0x180017d5b  mov     r8, rsi; bool *
0x180017d5e  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x180017d62  mov     rcx, rdi; this
0x180017d65  call    ?IsEnabledInGameConfigStore@IsGameManager@@AEAAJU_GUID@@PEA_N1PEAK@Z; IsGameManager::IsEnabledInGameConfigStore(_GUID,bool *,bool *,ulong *)
0x180017d6a  test    eax, eax
0x180017d6c  js      loc_180017C58
0x180017d72  mov     ebx, 4
0x180017d77  cmp     dword ptr [rbp+57h+string], r13d
0x180017d7b  jnz     short loc_180017DC8
0x180017d7d  mov     dword ptr [rbp+57h+string], 1
0x180017d84  mov     rcx, [rdi+10h]
0x180017d88  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x180017d8c  movdqa  [rbp+57h+Buf1], xmm0
0x180017d91  mov     rax, [rcx]
0x180017d94  mov     dword ptr [rsp+0D0h+var_B0], ebx; int
0x180017d98  lea     r9, [rbp+57h+string]
0x180017d9c  xor     r8d, r8d
0x180017d9f  lea     rdx, [rbp+57h+Buf1]
0x180017da3  mov     rax, [rax+48h]
0x180017da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dac  mov     rcx, [rbp+5Fh]; this
0x180017db0  test    eax, eax
0x180017db2  jns     short loc_180017DC8
0x180017db4  mov     r9d, eax; char *
0x180017db7  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180017dbe  mov     edx, 478h; void *
0x180017dc3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017dc8  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x180017dcc  movdqa  [rbp+57h+Buf1], xmm0
0x180017dd1  mov     r9, r15
0x180017dd4  mov     r8d, 0Fh
0x180017dda  lea     rdx, [rbp+57h+Buf1]
0x180017dde  mov     rcx, rdi
0x180017de1  call    ?GetStringFromGameConfigStore@IsGameManager@@AEAAJU_GUID@@W4GameProperty_t@ExecutionModel@@PEAVString@Internal@Windows@@@Z; IsGameManager::GetStringFromGameConfigStore(_GUID,ExecutionModel::GameProperty_t,Windows::Internal::String *)
0x180017de6  mov     rcx, [rbp+5Fh]; this
0x180017dea  test    eax, eax
0x180017dec  jns     loc_1806EC45A
0x180017df2  mov     r9d, eax; char *
0x180017df5  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180017dfc  mov     edx, 47Dh; void *
0x180017e01  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017e06  nop
0x180017e07  jmp     loc_1806EC45A
0x180017e0c  jmp     loc_180017CC7
0x180017e11  call    cs:__imp_WindowsDeleteString
0x180017e17  mov     eax, ebx
0x180017e19  jmp     loc_180017CD5
0x180017e1e  mov     rcx, [rbp+57h+string]; string
0x180017e22  test    rcx, rcx
0x180017e25  jz      short loc_180017E17
0x180017e27  jmp     short loc_180017E11
0x180017e29  mov     rcx, [rbp+5Fh]; this
0x180017e2d  mov     r9d, r14d; char *
0x180017e30  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180017e37  mov     edx, 811h; void *
0x180017e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e41  mov     rcx, [rbp+57h+string]; string
0x180017e45  test    rcx, rcx
0x180017e48  jz      short loc_180017E50
0x180017e4a  call    cs:__imp_WindowsDeleteString
0x180017e50  mov     ebx, r14d
0x180017e53  jmp     short loc_180017E17
0x180017e55  mov     r8d, 10h; Size
0x180017e5b  lea     rdx, xmmword_180769B30; Buf2
0x180017e62  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180017e66  call    memcmp_0
0x180017e6b  test    eax, eax
0x180017e6d  jnz     short loc_180017EC1
0x180017e6f  movdqa  [rbp+57h+Buf1], xmm6
0x180017e74  lea     rax, [rbp+57h+var_60]
0x180017e78  mov     [rsp+0D0h+var_A0], rax; struct _GUID *
0x180017e7d  mov     [rsp+0D0h+var_A8], r15; struct Windows::Internal::String *
0x180017e82  mov     byte ptr [rsp+0D0h+var_B0], r13b; int
0x180017e87  mov     r9d, r13d; unsigned int
0x180017e8a  lea     r8, [rbp+57h+Buf1]; struct _GUID
0x180017e8e  mov     rdx, [rbp+57h+string]; struct KnownGameList::IGameEntry *
0x180017e92  mov     rcx, rdi; this
0x180017e95  call    ?UpdateGameConfigStoreFromKGL@IsGameManager@@AEAAJPEAUIGameEntry@KnownGameList@@U_GUID@@K_NPEAVString@Internal@Windows@@PEAU4@@Z; IsGameManager::UpdateGameConfigStoreFromKGL(KnownGameList::IGameEntry *,_GUID,ulong,bool,Windows::Internal::String *,_GUID *)
0x180017e9a  test    eax, eax
0x180017e9c  jns     short loc_180017EB6
0x180017e9e  mov     rcx, [rbp+5Fh]; this
0x180017ea2  mov     r9d, eax; char *
0x180017ea5  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180017eac  mov     edx, 4A3h; void *
0x180017eb1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017eb6  mov     edx, r14d; unsigned int
0x180017eb9  mov     rcx, rdi; this
0x180017ebc  call    ?SendAddGameToConfigStoreTelemetry@IsGameManager@@AEAAXK@Z; IsGameManager::SendAddGameToConfigStoreTelemetry(ulong)
0x180017ec1  lea     rcx, [rbp+57h+string]
0x180017ec5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017eca  mov     rcx, rbx; SRWLock
0x180017ecd  call    cs:__imp_ReleaseSRWLockShared
0x180017ed3  mov     al, [rbp+57h+var_90]
0x180017ed6  mov     [rsi], al
0x180017ed8  mov     r8d, 10h; Size
0x180017ede  lea     rdx, xmmword_180769B30; Buf2
0x180017ee5  lea     rcx, [rbp+57h+var_60]; Buf1
0x180017ee9  call    memcmp_0
0x180017eee  test    eax, eax
0x180017ef0  jz      short loc_180017EF6
0x180017ef2  movaps  xmm6, xmmword ptr [rbp+57h+var_60.Data1]
0x180017ef6  cmp     [rsi], r13b
0x180017ef9  jz      loc_180017CD3
0x180017eff  movdqa  [rbp+57h+Buf1], xmm6
0x180017f04  mov     r8, rsi; struct GameConfigInfo *
0x180017f07  lea     rdx, [rbp+57h+Buf1]; struct _GUID
0x180017f0b  mov     rcx, rdi; this
0x180017f0e  call    ?GetAutoGameModeFromGameConfigStore@IsGameManager@@AEAAJU_GUID@@PEAUGameConfigInfo@@@Z; IsGameManager::GetAutoGameModeFromGameConfigStore(_GUID,GameConfigInfo *)
0x180017f13  movdqa  [rbp+57h+Buf1], xmm6
0x180017f18  lea     r8, [rbp+57h+Buf1]; struct _GUID
0x180017f1c  mov     edx, [rbp+57h+dwProcessId]; unsigned int
0x180017f1f  mov     rcx, rdi; this
0x180017f22  call    ?UpdateGameFullPathInGameConfigStore@IsGameManager@@AEAAJKU_GUID@@@Z; IsGameManager::UpdateGameFullPathInGameConfigStore(ulong,_GUID)
0x180017f27  test    eax, eax
0x180017f29  jns     short loc_180017F43
0x180017f2b  mov     rcx, [rbp+5Fh]; this
0x180017f2f  mov     r9d, eax; char *
0x180017f32  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180017f39  mov     edx, 15Bh; void *
0x180017f3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017f43  movdqa  [rbp+57h+Buf1], xmm6
0x180017f48  lea     rdx, [rbp+57h+Buf1]; struct _GUID
0x180017f4c  mov     rcx, rdi; this
0x180017f4f  call    ?UpdateGameLastRunTime@IsGameManager@@AEAAJU_GUID@@@Z; IsGameManager::UpdateGameLastRunTime(_GUID)
0x180017f54  test    eax, eax
0x180017f56  jns     loc_180017CD3
0x180017f5c  mov     rcx, [rbp+5Fh]; this
0x180017f60  mov     r9d, eax; char *
0x180017f63  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180017f6a  mov     edx, 15Eh; void *
0x180017f6f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017f74  jmp     loc_180017CD3
0x180017f79  cmp     eax, 80070002h
0x180017f7e  jz      loc_180017CAD
0x180017f84  test    eax, eax
0x180017f86  jns     loc_1806EC4D8
0x180017f8c  mov     edx, 498h
0x180017f91  jmp     loc_1806EC4B6
0x1806ec45a  movaps  xmm6, xmmword ptr [rbp+57h+var_60.Data1]
0x1806ec45e  mov     dword ptr [rbp+57h+string], r13d
0x1806ec462  mov     rcx, [rdi+10h]
0x1806ec466  movdqa  [rbp+57h+Buf1], xmm6
0x1806ec46b  mov     rax, [rcx]
0x1806ec46e  mov     dword ptr [rsp+0D0h+var_B0], ebx; int
0x1806ec472  lea     r9, [rbp+57h+string]
0x1806ec476  mov     r8d, 0Eh
0x1806ec47c  lea     rdx, [rbp+57h+Buf1]
0x1806ec480  mov     rax, [rax+48h]
0x1806ec484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806ec489  mov     ebx, eax
0x1806ec48b  test    eax, eax
0x1806ec48d  jns     loc_180017EF6
0x1806ec493  mov     rcx, [rbp+5Fh]; this
0x1806ec497  mov     r9d, eax; char *
0x1806ec49a  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1806ec4a1  mov     edx, 138h; void *
0x1806ec4a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1806ec4ab  nop
0x1806ec4ac  jmp     loc_180017E17
0x1806ec4b1  mov     edx, 49Ah; void *
0x1806ec4b6  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1806ec4bd  mov     r9d, eax; char *
  ... truncated ...
```
