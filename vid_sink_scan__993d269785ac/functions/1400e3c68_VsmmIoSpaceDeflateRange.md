# VsmmIoSpaceDeflateRange

- ea: `0x1400e3c68`
- end: `0x1400e3d74`
- name: `VsmmIoSpaceDeflateRange`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400264ac`
- `0x14002a078`
- `0x14002d684`
- `0x140035040`
- `0x1400e3d7c`

## callees

- `0x140023804`
- `0x14002f524`
- `0x1400e3c68`

## import_xrefs

- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e3cff`
- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e3d3a`
- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e3cff`
- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e3d3a`

## pseudocode

```c
__int64 __fastcall VsmmIoSpaceDeflateRange(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rbx
  __int64 result; // rax
  _QWORD v7[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  v2 = *a2;
  v8 = 0;
  v3 = v2 & 0x3FFFFFFF;
  v4 = (v2 >> 12) & 0xFFFFFFFFC0000LL;
  v5 = (v3 + 1) << 18;
  if ( (_DWORD)a1 == 1 )
  {
    v7[0] = v4;
    v7[1] = v5 + v4 - 1;
    if ( (int)VsmmSvcpExecuteFastSimpleCall(19, v7, 0x10u, 0, 0) < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmIoSpaceDeflateRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c", 497);
      __int2c();
    }
  }
  LOBYTE(a1) = 1;
  if ( (int)WinHvRemovePhysicalMemory(a1, v4, v5, &v8) < 0 )
  {
    VidTraceErrorStatusInternal0("VsmmIoSpaceDeflateRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c", 510);
    __int2c();
  }
  result = WinHvRemovePhysicalMemory(0, v4, v5, &v8);
  if ( (int)result < 0 )
  {
    result = VidTraceErrorStatusInternal0("VsmmIoSpaceDeflateRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c", 519);
    __int2c();
  }
  return result;
}

```

## disassembly

```asm
0x1400e3c68  mov     r11, rsp
0x1400e3c6b  mov     [r11+8], rbx
0x1400e3c6f  push    rdi
0x1400e3c70  sub     rsp, 40h
0x1400e3c74  mov     rbx, [rdx]
0x1400e3c77  mov     rax, 0FFFFFFFFC0000h
0x1400e3c81  mov     rdi, rbx
0x1400e3c84  mov     qword ptr [r11+10h], 0
0x1400e3c8c  and     ebx, 3FFFFFFFh
0x1400e3c92  shr     rdi, 0Ch
0x1400e3c96  inc     rbx
0x1400e3c99  and     rdi, rax
0x1400e3c9c  shl     rbx, 12h
0x1400e3ca0  cmp     ecx, 1
0x1400e3ca3  jnz     short loc_1400E3CF2
0x1400e3ca5  xor     r9d, r9d
0x1400e3ca8  mov     [r11-18h], rdi
0x1400e3cac  lea     r8d, [rcx+0Fh]
0x1400e3cb0  mov     [rsp+48h+var_28], 0
0x1400e3cb8  lea     rax, [rdi-1]
0x1400e3cbc  add     rax, rbx
0x1400e3cbf  lea     rdx, [r11-18h]
0x1400e3cc3  lea     ecx, [r9+13h]
0x1400e3cc7  mov     [r11-10h], rax
0x1400e3ccb  call    VsmmSvcpExecuteFastSimpleCall
0x1400e3cd0  test    eax, eax
0x1400e3cd2  jns     short loc_1400E3CF2
0x1400e3cd4  mov     r9d, eax
0x1400e3cd7  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e3cde  mov     r8d, 1F1h
0x1400e3ce4  lea     rcx, aVsmmiospacedef; "VsmmIoSpaceDeflateRange"
0x1400e3ceb  call    VidTraceErrorStatusInternal0
0x1400e3cf0  int     2Ch; Windows NT - assertion failure
0x1400e3cf2  lea     r9, [rsp+48h+arg_8]
0x1400e3cf7  mov     r8, rbx
0x1400e3cfa  mov     rdx, rdi
0x1400e3cfd  mov     cl, 1
0x1400e3cff  call    cs:__imp_WinHvRemovePhysicalMemory
0x1400e3d06  nop     dword ptr [rax+rax+00h]
0x1400e3d0b  test    eax, eax
0x1400e3d0d  jns     short loc_1400E3D2D
0x1400e3d0f  mov     r9d, eax
0x1400e3d12  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e3d19  mov     r8d, 1FEh
0x1400e3d1f  lea     rcx, aVsmmiospacedef; "VsmmIoSpaceDeflateRange"
0x1400e3d26  call    VidTraceErrorStatusInternal0
0x1400e3d2b  int     2Ch; Windows NT - assertion failure
0x1400e3d2d  lea     r9, [rsp+48h+arg_8]
0x1400e3d32  mov     r8, rbx
0x1400e3d35  mov     rdx, rdi
0x1400e3d38  xor     ecx, ecx
0x1400e3d3a  call    cs:__imp_WinHvRemovePhysicalMemory
0x1400e3d41  nop     dword ptr [rax+rax+00h]
0x1400e3d46  test    eax, eax
0x1400e3d48  jns     short loc_1400E3D68
0x1400e3d4a  mov     r9d, eax
0x1400e3d4d  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e3d54  mov     r8d, 207h
0x1400e3d5a  lea     rcx, aVsmmiospacedef; "VsmmIoSpaceDeflateRange"
0x1400e3d61  call    VidTraceErrorStatusInternal0
0x1400e3d66  int     2Ch; Windows NT - assertion failure
0x1400e3d68  mov     rbx, [rsp+48h+arg_0]
0x1400e3d6d  add     rsp, 40h
0x1400e3d71  pop     rdi
0x1400e3d72  retn
```
