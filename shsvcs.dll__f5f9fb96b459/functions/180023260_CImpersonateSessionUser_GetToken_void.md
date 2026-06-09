# CImpersonateSessionUser::_GetToken(void * *)

- ea: `0x180023260`
- end: `0x1800232fe`
- name: `?_GetToken@CImpersonateSessionUser@@MEAAJPEAPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(CImpersonateSessionUser *__hidden this, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800056c8`

## callees

- `0x180023260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023294`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023294`
- `ntdll!RtlGetActiveConsoleId` at `0x1800232b1`
- `ntdll!RtlGetActiveConsoleId` at `0x1800232b1`
- `WINSTA!WinStationQueryInformationW` at `0x1800232d8`
- `WINSTA!WinStationQueryInformationW` at `0x1800232d8`

## pseudocode

```c
__int64 __fastcall CImpersonateSessionUser::_GetToken(CImpersonateSessionUser *this, void **a2)
{
  unsigned int ActiveConsoleId; // eax
  _QWORD v6[2]; // [rsp+30h] [rbp-28h] BYREF
  void *v7; // [rsp+40h] [rbp-18h]
  int v8; // [rsp+60h] [rbp+8h] BYREF

  v8 = 0;
  v7 = 0;
  v6[0] = GetCurrentProcessId();
  v6[1] = GetCurrentThreadId();
  ActiveConsoleId = *((_DWORD *)this + 4);
  v7 = 0;
  if ( !ActiveConsoleId )
    ActiveConsoleId = RtlGetActiveConsoleId();
  if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD *, int, int *))WinStationQueryInformationW)(
                           0,
                           ActiveConsoleId,
                           14,
                           v6,
                           24,
                           &v8) )
    return 2147500037LL;
  *a2 = v7;
  return 0;
}

```

## disassembly

```asm
0x180023260  mov     [rsp+arg_8], rbx
0x180023265  push    rdi
0x180023266  sub     rsp, 50h
0x18002326a  xorps   xmm0, xmm0
0x18002326d  mov     [rsp+58h+arg_0], 0
0x180023275  xor     eax, eax
0x180023277  mov     rdi, rdx
0x18002327a  movups  [rsp+58h+var_28], xmm0
0x18002327f  mov     [rsp+58h+var_18], rax
0x180023284  mov     rbx, rcx
0x180023287  call    cs:__imp_GetCurrentProcessId
0x18002328d  mov     eax, eax
0x18002328f  mov     qword ptr [rsp+58h+var_28], rax
0x180023294  call    cs:__imp_GetCurrentThreadId
0x18002329a  mov     eax, eax
0x18002329c  mov     qword ptr [rsp+58h+var_28+8], rax
0x1800232a1  mov     eax, [rbx+10h]
0x1800232a4  mov     [rsp+58h+var_18], 0
0x1800232ad  test    eax, eax
0x1800232af  jnz     short loc_1800232B7
0x1800232b1  call    cs:__imp_RtlGetActiveConsoleId
0x1800232b7  lea     rcx, [rsp+58h+arg_0]
0x1800232bc  mov     r8d, 0Eh
0x1800232c2  mov     [rsp+58h+var_30], rcx
0x1800232c7  lea     r9, [rsp+58h+var_28]
0x1800232cc  xor     ecx, ecx
0x1800232ce  mov     [rsp+58h+var_38], 18h
0x1800232d6  mov     edx, eax
0x1800232d8  call    cs:__imp_WinStationQueryInformationW
0x1800232de  test    al, al
0x1800232e0  jz      short loc_1800232EE
0x1800232e2  mov     rax, [rsp+58h+var_18]
0x1800232e7  mov     [rdi], rax
0x1800232ea  xor     eax, eax
0x1800232ec  jmp     short loc_1800232F3
0x1800232ee  mov     eax, 80004005h
0x1800232f3  mov     rbx, [rsp+58h+arg_8]
0x1800232f8  add     rsp, 50h
0x1800232fc  pop     rdi
0x1800232fd  retn
```
