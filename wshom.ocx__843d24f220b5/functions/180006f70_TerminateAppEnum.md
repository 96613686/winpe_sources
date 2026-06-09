# TerminateAppEnum

- ea: `0x180006f70`
- end: `0x180006fbc`
- name: `TerminateAppEnum`
- size: `76`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180006f70`

## import_xrefs

- `USER32!PostMessageA` at `0x180006fa6`
- `USER32!PostMessageA` at `0x180006fa6`
- `USER32!GetWindowThreadProcessId` at `0x180006f8d`
- `USER32!GetWindowThreadProcessId` at `0x180006f8d`

## pseudocode

```c
__int64 __fastcall TerminateAppEnum(HWND a1, int a2)
{
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( dwProcessId == a2 )
    PostMessageA(a1, 0x10u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x180006f70  mov     [rsp+arg_0], rbx
0x180006f75  push    rdi
0x180006f76  sub     rsp, 20h
0x180006f7a  mov     rbx, rdx
0x180006f7d  mov     [rsp+28h+dwProcessId], 0
0x180006f85  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180006f8a  mov     rdi, rcx
0x180006f8d  call    cs:__imp_GetWindowThreadProcessId
0x180006f93  cmp     [rsp+28h+dwProcessId], ebx
0x180006f97  jnz     short loc_180006FAC
0x180006f99  xor     r9d, r9d; lParam
0x180006f9c  xor     r8d, r8d; wParam
0x180006f9f  mov     rcx, rdi; hWnd
0x180006fa2  lea     edx, [r9+10h]; Msg
0x180006fa6  call    cs:__imp_PostMessageA
0x180006fac  mov     rbx, [rsp+28h+arg_0]
0x180006fb1  mov     eax, 1
0x180006fb6  add     rsp, 20h
0x180006fba  pop     rdi
0x180006fbb  retn
```
