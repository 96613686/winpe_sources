# WinHvpFreeOverlayPhysicalPage

- ea: `0x140005dcc`
- end: `0x140005e30`
- name: `WinHvpFreeOverlayPhysicalPage`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140023350`
- `0x140023540`
- `0x1400236fc`

## callees

- `0x140009c50`

## import_xrefs

- `ntoskrnl!MmFreePagesFromMdl` at `0x140005e11`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140005e11`

## pseudocode

```c
void __fastcall WinHvpFreeOverlayPhysicalPage(__int64 a1)
{
  struct _MDL v1; // [rsp+20h] [rbp-48h] BYREF
  __int64 v2; // [rsp+50h] [rbp-18h]

  memset(&v1.MdlFlags + 1, 0, 28);
  v1.Next = 0;
  *(_DWORD *)&v1.Size = 56;
  v2 = a1;
  *(_QWORD *)&v1.ByteCount = 4096;
  MmFreePagesFromMdl(&v1);
}

```

## disassembly

```asm
0x140005dcc  mov     r11, rsp
0x140005dcf  sub     rsp, 68h
0x140005dd3  mov     rax, cs:__security_cookie
0x140005dda  xor     rax, rsp
0x140005ddd  mov     [rsp+68h+var_10], rax
0x140005de2  xor     edx, edx
0x140005de4  xorps   xmm0, xmm0
0x140005de7  movdqu  [rsp+68h+var_3C], xmm0
0x140005ded  mov     [rsp+68h+var_2C], edx
0x140005df1  mov     [r11-48h], rdx
0x140005df5  mov     [rsp+68h+var_40], 38h ; '8'
0x140005dfd  mov     [r11-18h], rcx
0x140005e01  lea     rcx, [r11-48h]; MemoryDescriptorList
0x140005e05  mov     [r11-28h], rdx
0x140005e09  mov     qword ptr [r11-20h], 1000h
0x140005e11  call    cs:__imp_MmFreePagesFromMdl
0x140005e18  nop     dword ptr [rax+rax+00h]
0x140005e1d  mov     rcx, [rsp+68h+var_10]
0x140005e22  xor     rcx, rsp; StackCookie
0x140005e25  call    __security_check_cookie
0x140005e2a  add     rsp, 68h
0x140005e2e  retn
```
