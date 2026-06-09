# _lambda_e1b59a74a951869dc8650816fa791795_::_lambda_invoker_cdecl_(HWND__ *,__int64)

- ea: `0x1800123b0`
- end: `0x180012419`
- name: `?_lambda_invoker_cdecl_@_lambda_e1b59a74a951869dc8650816fa791795_@@CAHPEAUHWND__@@_J@Z`
- size: `105`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800123b0`

## import_xrefs

- `USER32!IsWindowVisible` at `0x1800123e3`
- `USER32!IsWindowVisible` at `0x1800123e3`
- `USER32!GetWindowThreadProcessId` at `0x1800123d1`
- `USER32!GetWindowThreadProcessId` at `0x1800123d1`
- `USER32!MonitorFromWindow` at `0x1800123f5`
- `USER32!MonitorFromWindow` at `0x1800123f5`

## pseudocode

```c
_BOOL8 __fastcall _lambda_e1b59a74a951869dc8650816fa791795_::_lambda_invoker_cdecl_(HWND a1, __int64 a2)
{
  HMONITOR *v4; // rbx
  DWORD v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  GetWindowThreadProcessId(a1, &v6);
  if ( *(_DWORD *)(a2 + 8) == v6 && IsWindowVisible(a1) )
  {
    v4 = *(HMONITOR **)a2;
    *v4 = MonitorFromWindow(a1, 0);
  }
  return **(_QWORD **)a2 == 0;
}

```

## disassembly

```asm
0x1800123b0  mov     rax, rsp
0x1800123b3  mov     [rax+8], rbx
0x1800123b7  mov     [rax+18h], rsi
0x1800123bb  push    rdi
0x1800123bc  sub     rsp, 20h
0x1800123c0  mov     rdi, rdx
0x1800123c3  mov     dword ptr [rax+10h], 0
0x1800123ca  lea     rdx, [rax+10h]; lpdwProcessId
0x1800123ce  mov     rsi, rcx
0x1800123d1  call    cs:__imp_GetWindowThreadProcessId
0x1800123d7  mov     eax, [rsp+28h+arg_8]
0x1800123db  cmp     [rdi+8], eax
0x1800123de  jnz     short loc_1800123FE
0x1800123e0  mov     rcx, rsi; hWnd
0x1800123e3  call    cs:__imp_IsWindowVisible
0x1800123e9  test    eax, eax
0x1800123eb  jz      short loc_1800123FE
0x1800123ed  mov     rbx, [rdi]
0x1800123f0  xor     edx, edx; dwFlags
0x1800123f2  mov     rcx, rsi; hwnd
0x1800123f5  call    cs:__imp_MonitorFromWindow
0x1800123fb  mov     [rbx], rax
0x1800123fe  mov     rcx, [rdi]
0x180012401  xor     eax, eax
0x180012403  mov     rbx, [rsp+28h+arg_0]
0x180012408  mov     rsi, [rsp+28h+arg_10]
0x18001240d  cmp     [rcx], rax
0x180012410  setz    al
0x180012413  add     rsp, 20h
0x180012417  pop     rdi
0x180012418  retn
```
