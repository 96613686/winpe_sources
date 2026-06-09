# DockedUsage::AssignedAccessAccount(int *)

- ea: `0x180021e80`
- end: `0x180022158`
- name: `?AssignedAccessAccount@DockedUsage@@UEAAJPEAH@Z`
- size: `728`
- prototype: `__int64 __fastcall(DockedUsage *__hidden this, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007644`
- `0x180007660`
- `0x1800183f4`
- `0x1800209fc`
- `0x180020eb4`
- `0x180021614`
- `0x180021e80`
- `0x180023a18`
- `0x18003ef60`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002209e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002209e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022060`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022060`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180021f43`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180021f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180021f73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180021f73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002204f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002204f`

## string_xrefs

- `0x180021eb8`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`
- `0x1800220f4`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`
- `0x180022107`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`
- `0x18002211c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`
- `0x180022131`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`
- `0x180022145`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall DockedUsage::AssignedAccessAccount(DockedUsage *this, WCHAR *a2)
{
  __int64 result; // rax
  __int64 v4; // rdi
  __int64 **v5; // rax
  __int64 *v6; // rsi
  wil *v7; // rcx
  const char *v8; // r9
  char *v9; // rdx
  const char *v10; // r9
  HRESULT v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  void *v18; // rcx
  void *Block; // [rsp+20h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-70h] BYREF
  __int64 *v21; // [rsp+30h] [rbp-68h]
  int v22; // [rsp+38h] [rbp-60h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-58h] BYREF
  __int64 v24; // [rsp+48h] [rbp-50h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-48h] BYREF
  HSTRING string; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  StringSid = a2;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
      (const char *)0x80004003LL,
      (int)Block);
    return 2147500035LL;
  }
  try
  {
    try
    {
      v4 = -1;
      v22 = -1;
      v21 = 0;
      v5 = (__int64 **)wil::ActivateInstance<Windows::Internal::AssignedAccess::IAssignedAccessManager>(&Block);
      v6 = *v5;
      *v5 = 0;
      v21 = v6;
      v7 = (wil *)Block;
      if ( Block )
        (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
    }
    catch ( ... )
    {
      if ( (unsigned int)wil::ResultFromCaughtException(v7) != -2147221164 )
        throw;
      *(_DWORD *)StringSid = 0;
      if ( v21 )
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      return 0;
    }
    Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(&hObject);
    v9 = (char *)hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::get_token_information<_TOKEN_USER>(&Block);
      StringSid = 0;
      if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
          v10);
      string = 0;
      do
        ++v4;
      while ( StringSid[v4] );
      v11 = WindowsCreateString(StringSid, v4, &string);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
          (const char *)(unsigned int)v11,
          (int)Block);
      v25 = 0;
      v12 = *v6;
      v25 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v12 + 56))(v6, &v25);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
          (const char *)(unsigned int)v13,
          (int)Block);
      v24 = 0;
      v14 = *v25;
      v24 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v14 + 64))(v25, string, &v24);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7E,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
          (const char *)(unsigned int)v15,
          (int)Block);
      v16 = v24;
      if ( v24 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 80LL))(v24, &v22);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x82,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
            (const char *)(unsigned int)v17,
            (int)Block);
        v16 = v24;
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v25 )
        (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
      if ( string )
        WindowsDeleteString(string);
      if ( StringSid )
        LocalFree(StringSid);
      v18 = Block;
      Block = 0;
      if ( v18 )
        operator delete(v18);
      v9 = (char *)hObject;
    }
    *(_DWORD *)a2 = (unsigned int)(v22 - 1) <= 2;
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v9);
    if ( v6 )
      (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8C,
                           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\d"
                                         "ll\\dockedusage.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180021e80  push    rbx
0x180021e82  push    rsi
0x180021e83  push    rdi
0x180021e84  push    r14
0x180021e86  sub     rsp, 78h
0x180021e8a  mov     rax, cs:__security_cookie
0x180021e91  xor     rax, rsp
0x180021e94  mov     [rsp+98h+var_38], rax
0x180021e99  mov     r14, rdx
0x180021e9c  mov     [rsp+98h+StringSid], rdx
0x180021ea1  xor     ebx, ebx
0x180021ea3  test    rdx, rdx
0x180021ea6  jnz     short loc_180021ECF
0x180021ea8  mov     rcx, [rsp+98h]; this
0x180021eb0  mov     ebx, 80004003h
0x180021eb5  mov     r9d, ebx; char *
0x180021eb8  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180021ebf  lea     edx, [r14+57h]; void *
0x180021ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ec8  mov     eax, ebx
0x180021eca  jmp     loc_1800220DD
0x180021ecf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180021ed3  mov     [rsp+98h+var_60], edi
0x180021ed7  mov     [rsp+98h+var_68], rbx
0x180021edc  lea     rcx, [rsp+98h+Block]
0x180021ee1  call    ??$ActivateInstance@UIAssignedAccessManager@AssignedAccess@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAssignedAccessManager@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Internal::AssignedAccess::IAssignedAccessManager>(ushort const *)
0x180021ee6  mov     rsi, [rax]
0x180021ee9  mov     [rax], rbx
0x180021eec  mov     [rsp+98h+var_68], rsi
0x180021ef1  mov     rcx, [rsp+98h+Block]
0x180021ef6  test    rcx, rcx
0x180021ef9  jz      short loc_180021F08
0x180021efb  mov     rax, [rcx]
0x180021efe  mov     rax, [rax+10h]
0x180021f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f07  nop
0x180021f08  lea     rcx, [rsp+98h+hObject]
0x180021f0d  call    ?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)
0x180021f12  nop
0x180021f13  mov     rdx, [rsp+98h+hObject]
0x180021f18  lea     rax, [rdx-1]
0x180021f1c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021f20  ja      loc_180022080
0x180021f26  lea     rcx, [rsp+98h+Block]
0x180021f2b  call    ??$get_token_information@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z
0x180021f30  nop
0x180021f31  mov     [rsp+98h+StringSid], rbx
0x180021f36  lea     rdx, [rsp+98h+StringSid]; StringSid
0x180021f3b  mov     rcx, [rsp+98h+Block]
0x180021f40  mov     rcx, [rcx]; Sid
0x180021f43  call    cs:__imp_ConvertSidToStringSidW
0x180021f49  mov     rcx, [rsp+98h]; this
0x180021f51  test    eax, eax
0x180021f53  jz      loc_1800220F4
0x180021f59  mov     [rsp+98h+string], rbx
0x180021f5e  mov     rcx, [rsp+98h+StringSid]; sourceString
0x180021f63  inc     rdi
0x180021f66  cmp     [rcx+rdi*2], bx
0x180021f6a  jnz     short loc_180021F63
0x180021f6c  lea     r8, [rsp+98h+string]; string
0x180021f71  mov     edx, edi; length
0x180021f73  call    cs:__imp_WindowsCreateString
0x180021f79  mov     rcx, [rsp+98h]; this
0x180021f81  test    eax, eax
0x180021f83  js      loc_180022104
0x180021f89  mov     [rsp+98h+var_48], rbx
0x180021f8e  mov     rax, [rsi]
0x180021f91  mov     [rsp+98h+var_48], rbx
0x180021f96  lea     rdx, [rsp+98h+var_48]
0x180021f9b  mov     rcx, rsi
0x180021f9e  mov     rax, [rax+38h]
0x180021fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa7  mov     rcx, [rsp+98h]; this
0x180021faf  test    eax, eax
0x180021fb1  js      loc_180022119
0x180021fb7  mov     [rsp+98h+var_50], rbx
0x180021fbc  mov     rcx, [rsp+98h+var_48]
0x180021fc1  mov     rax, [rcx]
0x180021fc4  mov     [rsp+98h+var_50], rbx
0x180021fc9  lea     r8, [rsp+98h+var_50]
0x180021fce  mov     rdx, [rsp+98h+string]
0x180021fd3  mov     rax, [rax+40h]
0x180021fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fdc  mov     rcx, [rsp+98h]; this
0x180021fe4  test    eax, eax
0x180021fe6  js      loc_18002212E
0x180021fec  mov     rcx, [rsp+98h+var_50]
0x180021ff1  test    rcx, rcx
0x180021ff4  jz      short loc_18002201C
0x180021ff6  mov     rax, [rcx]
0x180021ff9  lea     rdx, [rsp+98h+var_60]
0x180021ffe  mov     rax, [rax+50h]
0x180022002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022007  mov     rcx, [rsp+98h]; this
0x18002200f  test    eax, eax
0x180022011  js      loc_180022142
0x180022017  mov     rcx, [rsp+98h+var_50]
0x18002201c  test    rcx, rcx
0x18002201f  jz      short loc_18002202E
0x180022021  mov     rax, [rcx]
0x180022024  mov     rax, [rax+10h]
0x180022028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002202d  nop
0x18002202e  mov     rcx, [rsp+98h+var_48]
0x180022033  test    rcx, rcx
0x180022036  jz      short loc_180022045
0x180022038  mov     rax, [rcx]
0x18002203b  mov     rax, [rax+10h]
0x18002203f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022044  nop
0x180022045  mov     rcx, [rsp+98h+string]; string
0x18002204a  test    rcx, rcx
0x18002204d  jz      short loc_180022056
0x18002204f  call    cs:__imp_WindowsDeleteString
0x180022055  nop
0x180022056  mov     rcx, [rsp+98h+StringSid]; hMem
0x18002205b  test    rcx, rcx
0x18002205e  jz      short loc_180022067
0x180022060  call    cs:__imp_LocalFree
0x180022066  nop
0x180022067  mov     rcx, [rsp+98h+Block]; Block
0x18002206c  mov     [rsp+98h+Block], rbx
0x180022071  test    rcx, rcx
0x180022074  jz      short loc_18002207B
0x180022076  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002207b  mov     rdx, [rsp+98h+hObject]
0x180022080  mov     eax, [rsp+98h+var_60]
0x180022084  dec     eax
0x180022086  mov     ecx, ebx
0x180022088  cmp     eax, 2
0x18002208b  setbe   cl
0x18002208e  mov     [r14], ecx
0x180022091  lea     rax, [rdx-1]
0x180022095  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022099  ja      short loc_1800220A5
0x18002209b  mov     rcx, rdx; hObject
0x18002209e  call    cs:__imp_CloseHandle
0x1800220a4  nop
0x1800220a5  test    rsi, rsi
0x1800220a8  jz      short loc_1800220BA
0x1800220aa  mov     rax, [rsi]
0x1800220ad  mov     rcx, rsi
0x1800220b0  mov     rax, [rax+10h]
0x1800220b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b9  nop
0x1800220ba  xor     eax, eax
0x1800220bc  jmp     short loc_1800220DD
0x1800220be  mov     rcx, [rsp+98h+var_68]
0x1800220c3  test    rcx, rcx
0x1800220c6  jz      short loc_1800220D5
0x1800220c8  mov     rax, [rcx]
0x1800220cb  mov     rax, [rax+10h]
0x1800220cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220d4  nop
0x1800220d5  xor     eax, eax
0x1800220d7  jmp     short loc_1800220DD
0x1800220d9  mov     eax, [rsp+98h+var_60]
0x1800220dd  mov     rcx, [rsp+98h+var_38]
0x1800220e2  xor     rcx, rsp; StackCookie
0x1800220e5  call    __security_check_cookie
0x1800220ea  add     rsp, 78h
0x1800220ee  pop     r14
0x1800220f0  pop     rdi
0x1800220f1  pop     rsi
0x1800220f2  pop     rbx
0x1800220f3  retn
0x1800220f4  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800220fb  lea     edx, [rax+72h]; void *
0x1800220fe  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180022104  mov     r9d, eax; char *
0x180022107  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002210e  mov     edx, 78h ; 'x'; void *
0x180022113  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022119  mov     r9d, eax; char *
0x18002211c  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180022123  mov     edx, 7Bh ; '{'; void *
0x180022128  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002212e  mov     r9d, eax; char *
0x180022131  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180022138  mov     edx, 7Eh ; '~'; void *
0x18002213d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022142  mov     r9d, eax; char *
0x180022145  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002214c  mov     edx, 82h; void *
0x180022151  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
