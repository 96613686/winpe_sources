# DockedPower::CreatePDCTask(void)

- ea: `0x180020330`
- end: `0x18002046b`
- name: `?CreatePDCTask@DockedPower@@UEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(DockedPower *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180007660`
- `0x180020330`
- `0x1800209fc`
- `0x180020ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800203eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800203eb`
- `UMPDC!PdcTaskClientUnregister` at `0x1800203e3`
- `UMPDC!PdcTaskClientUnregister` at `0x1800203fe`
- `UMPDC!PdcTaskClientUnregister` at `0x1800203e3`
- `UMPDC!PdcTaskClientUnregister` at `0x1800203fe`
- `UMPDC!PdcTaskClientRegister` at `0x18002036e`
- `UMPDC!PdcTaskClientRegister` at `0x18002036e`
- `UMPDC!PdcTaskClientRequest` at `0x180020396`
- `UMPDC!PdcTaskClientRequest` at `0x180020396`

## string_xrefs

- `0x18002042c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`
- `0x180020443`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`
- `0x180020458`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall DockedPower::CreatePDCTask(DockedPower *this)
{
  __int64 *v1; // rbx
  int v2; // eax
  __int64 v3; // rdx
  int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // rbx
  DWORD LastError; // esi
  int v9; // [rsp+20h] [rbp-28h]
  __int64 v10; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = (__int64 *)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    v10 = 0;
    v2 = PdcTaskClientRegister(85, &v10);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        (const char *)(unsigned int)v2,
        v9);
    if ( !v10 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        (const char *)0x8000FFFFLL,
        v9);
    LOBYTE(v3) = 1;
    v4 = PdcTaskClientRequest(v10, v3);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        (const char *)(unsigned int)v4,
        v9);
    v5 = *v1;
    *v1 = 0;
    if ( v1 == &v10 )
    {
      v6 = v10;
    }
    else
    {
      *v1 = v10;
      v6 = 0;
      v10 = 0;
    }
    if ( v6 )
    {
      LastError = GetLastError();
      PdcTaskClientUnregister(v6);
      SetLastError(LastError);
    }
    v10 = v5;
    if ( v5 )
      PdcTaskClientUnregister(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180020330  mov     r11, rsp
0x180020333  mov     [r11+10h], rbx
0x180020337  mov     [r11+18h], rsi
0x18002033b  push    rdi
0x18002033c  sub     rsp, 40h
0x180020340  mov     rax, cs:__security_cookie
0x180020347  xor     rax, rsp
0x18002034a  mov     [rsp+48h+var_18], rax
0x18002034f  lea     rbx, [rcx+10h]
0x180020353  cmp     qword ptr [rbx], 0
0x180020357  jnz     loc_180020404
0x18002035d  mov     qword ptr [r11-20h], 0
0x180020365  lea     rdx, [r11-20h]
0x180020369  mov     ecx, 55h ; 'U'
0x18002036e  call    cs:__imp_PdcTaskClientRegister
0x180020374  mov     rcx, [rsp+48h]; this
0x180020379  test    eax, eax
0x18002037b  js      loc_180020429
0x180020381  mov     rax, [rsp+48h]
0x180020386  mov     rcx, [rsp+48h+var_20]
0x18002038b  test    rcx, rcx
0x18002038e  jz      loc_18002043D
0x180020394  mov     dl, 1
0x180020396  call    cs:__imp_PdcTaskClientRequest
0x18002039c  mov     rcx, [rsp+48h]; this
0x1800203a1  test    eax, eax
0x1800203a3  js      loc_180020455
0x1800203a9  mov     rdi, [rbx]
0x1800203ac  mov     qword ptr [rbx], 0
0x1800203b3  lea     rax, [rsp+48h+var_20]
0x1800203b8  cmp     rbx, rax
0x1800203bb  jz      short loc_1800203CE
0x1800203bd  mov     rax, [rsp+48h+var_20]
0x1800203c2  mov     [rbx], rax
0x1800203c5  xor     ebx, ebx
0x1800203c7  mov     [rsp+48h+var_20], rbx
0x1800203cc  jmp     short loc_1800203D3
0x1800203ce  mov     rbx, [rsp+48h+var_20]
0x1800203d3  test    rbx, rbx
0x1800203d6  jz      short loc_1800203F1
0x1800203d8  call    cs:__imp_GetLastError
0x1800203de  mov     esi, eax
0x1800203e0  mov     rcx, rbx
0x1800203e3  call    cs:__imp_PdcTaskClientUnregister
0x1800203e9  mov     ecx, esi; dwErrCode
0x1800203eb  call    cs:__imp_SetLastError
0x1800203f1  mov     [rsp+48h+var_20], rdi
0x1800203f6  test    rdi, rdi
0x1800203f9  jz      short loc_180020404
0x1800203fb  mov     rcx, rdi
0x1800203fe  call    cs:__imp_PdcTaskClientUnregister
0x180020404  xor     eax, eax
0x180020406  jmp     short loc_18002040C
0x180020408  mov     eax, [rsp+48h+var_28]
0x18002040c  mov     rcx, [rsp+48h+var_18]
0x180020411  xor     rcx, rsp; StackCookie
0x180020414  call    __security_check_cookie
0x180020419  mov     rbx, [rsp+48h+arg_8]
0x18002041e  mov     rsi, [rsp+48h+arg_10]
0x180020423  add     rsp, 40h
0x180020427  pop     rdi
0x180020428  retn
0x180020429  mov     r9d, eax; char *
0x18002042c  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180020433  mov     edx, 48h ; 'H'; void *
0x180020438  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002043d  mov     r9d, 8000FFFFh; char *
0x180020443  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002044a  lea     edx, [rcx+49h]; void *
0x18002044d  mov     rcx, rax; this
0x180020450  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020455  mov     r9d, eax; char *
0x180020458  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002045f  mov     edx, 4Ah ; 'J'; void *
0x180020464  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
