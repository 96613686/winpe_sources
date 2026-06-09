# GetInputWindow

- ea: `0x180006898`
- end: `0x180006910`
- name: `GetInputWindow`
- size: `120`
- prototype: `HWND __fastcall(__int64, HWND)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b70`
- `0x180008c10`

## callees

- `0x180006898`

## import_xrefs

- `win32u!NtUserQueryInformationThread` at `0x1800068bc`
- `win32u!NtUserQueryInformationThread` at `0x1800068bc`
- `USER32!GetWindow` at `0x1800068e8`
- `USER32!GetWindow` at `0x1800068e8`
- `USER32!IsWindowEnabled` at `0x1800068d2`
- `USER32!IsWindowEnabled` at `0x1800068d2`

## pseudocode

```c
HWND __fastcall GetInputWindow(__int64 a1, HWND a2)
{
  __int64 v2; // rcx
  HWND Window; // rcx
  HWND result; // rax
  UINT v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  v6 = gCmsHungAppTimeout;
  NtUserQueryInformationThread(v2, 4, &v6, 4);
  if ( v6 )
    return 0;
  if ( IsWindowEnabled(a2) )
    return 0;
  Window = GetWindow(a2, 6u);
  if ( !Window )
    return 0;
  result = 0;
  if ( Window != a2 )
    return Window;
  return result;
}

```

## disassembly

```asm
0x180006898  push    rbx
0x18000689a  sub     rsp, 20h
0x18000689e  mov     eax, cs:gCmsHungAppTimeout
0x1800068a4  lea     r8, [rsp+28h+arg_0]
0x1800068a9  mov     rcx, [rcx+40h]
0x1800068ad  mov     rbx, rdx
0x1800068b0  mov     edx, 4
0x1800068b5  mov     [rsp+28h+arg_0], eax
0x1800068b9  mov     r9d, edx
0x1800068bc  call    cs:__imp_NtUserQueryInformationThread
0x1800068c3  nop     dword ptr [rax+rax+00h]
0x1800068c8  cmp     [rsp+28h+arg_0], 0
0x1800068cd  jnz     short loc_180006907
0x1800068cf  mov     rcx, rbx; hWnd
0x1800068d2  call    cs:__imp_IsWindowEnabled
0x1800068d9  nop     dword ptr [rax+rax+00h]
0x1800068de  test    eax, eax
0x1800068e0  jnz     short loc_180006907
0x1800068e2  lea     edx, [rax+6]; uCmd
0x1800068e5  mov     rcx, rbx; hWnd
0x1800068e8  call    cs:__imp_GetWindow
0x1800068ef  nop     dword ptr [rax+rax+00h]
0x1800068f4  mov     rcx, rax
0x1800068f7  test    rax, rax
0x1800068fa  jz      short loc_180006907
0x1800068fc  xor     eax, eax
0x1800068fe  cmp     rcx, rbx
0x180006901  cmovnz  rax, rcx
0x180006905  jmp     short loc_180006909
0x180006907  xor     eax, eax
0x180006909  add     rsp, 20h
0x18000690d  pop     rbx
0x18000690e  retn
```
