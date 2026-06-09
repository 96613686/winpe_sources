# ResizeVirtualDiskInternal

- ea: `0x1800095e4`
- end: `0x180009691`
- name: `ResizeVirtualDiskInternal`
- size: `173`
- prototype: `DWORD __fastcall(void *, __int64, int, int, int, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008cb0`
- `0x180009480`

## callees

- `0x180005730`
- `0x1800095e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000966e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000966e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000965e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000965e`

## pseudocode

```c
DWORD __fastcall ResizeVirtualDiskInternal(void *a1, __int64 a2, int a3, int a4, int a5, struct _OVERLAPPED *a6)
{
  DWORD v7; // [rsp+40h] [rbp-28h] BYREF
  __int128 v8; // [rsp+48h] [rbp-20h] BYREF

  v7 = 0;
  v8 = 0;
  *(_QWORD *)&v8 = a2;
  BYTE8(v8) = a3 != 0;
  BYTE9(v8) = a4 != 0;
  BYTE11(v8) = a5 != 0;
  if ( DeviceIoControl(a1, 0x2D1950u, &v8, 0x10u, 0, 0, &v7, a6) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800095e4  mov     r11, rsp
0x1800095e7  sub     rsp, 68h
0x1800095eb  mov     rax, cs:__security_cookie
0x1800095f2  xor     rax, rsp
0x1800095f5  mov     [rsp+68h+var_10], rax
0x1800095fa  mov     rax, [rsp+68h+arg_28]
0x180009602  test    r8d, r8d
0x180009605  mov     [r11-30h], rax
0x180009609  lea     r8, [r11-20h]; lpInBuffer
0x18000960d  xorps   xmm0, xmm0
0x180009610  mov     [rsp+68h+var_28], 0
0x180009618  movups  [rsp+68h+var_20], xmm0
0x18000961d  mov     [r11-20h], rdx
0x180009621  lea     rax, [r11-28h]
0x180009625  setnz   byte ptr [rsp+68h+var_20+8]
0x18000962a  mov     [r11-38h], rax
0x18000962e  test    r9d, r9d
0x180009631  mov     [rsp+68h+nOutBufferSize], 0; nOutBufferSize
0x180009639  mov     r9d, 10h; nInBufferSize
0x18000963f  mov     qword ptr [r11-48h], 0
0x180009647  setnz   byte ptr [rsp+68h+var_20+9]
0x18000964c  mov     edx, 2D1950h; dwIoControlCode
0x180009651  cmp     [rsp+68h+arg_20], 0
0x180009659  setnz   byte ptr [rsp+68h+var_20+0Bh]
0x18000965e  call    cs:__imp_DeviceIoControl
0x180009665  nop     dword ptr [rax+rax+00h]
0x18000966a  test    eax, eax
0x18000966c  jnz     short loc_18000967C
0x18000966e  call    cs:__imp_GetLastError
0x180009675  nop     dword ptr [rax+rax+00h]
0x18000967a  jmp     short loc_18000967E
0x18000967c  xor     eax, eax
0x18000967e  mov     rcx, [rsp+68h+var_10]
0x180009683  xor     rcx, rsp; StackCookie
0x180009686  call    __security_check_cookie
0x18000968b  add     rsp, 68h
0x18000968f  retn
```
