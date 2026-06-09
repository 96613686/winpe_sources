# VsmmIoSpaceInflateRange

- ea: `0x1400e3d7c`
- end: `0x1400e3efe`
- name: `VsmmIoSpaceInflateRange`
- size: `386`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400264ac`

## callees

- `0x140023804`
- `0x14002f524`
- `0x1400e3c68`
- `0x1400e3d7c`

## import_xrefs

- `winhvr!WinHvAddPhysicalMemory` at `0x1400e3dd3`
- `winhvr!WinHvAddPhysicalMemory` at `0x1400e3e66`
- `winhvr!WinHvAddPhysicalMemory` at `0x1400e3dd3`
- `winhvr!WinHvAddPhysicalMemory` at `0x1400e3e66`
- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e3e1f`
- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e3e1f`

## pseudocode

```c
__int64 __fastcall VsmmIoSpaceInflateRange(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rsi
  int v4; // ebp
  __int64 v5; // rdi
  __int64 v6; // rsi
  int v7; // ebx
  __int64 v8; // rcx
  _QWORD v10[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+78h] [rbp+10h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h] BYREF

  v2 = *a2;
  v11 = 0;
  v13 = 0;
  v4 = a1;
  v5 = ((v2 & 0x3FFFFFFF) + 1) << 18;
  v6 = (v2 >> 12) & 0xFFFFFFFFC0000LL;
  LOBYTE(a1) = 1;
  v7 = WinHvAddPhysicalMemory(a1, v6, v5, &v11);
  if ( v7 >= 0 )
  {
    WinHvAddPhysicalMemory(0, v6, v5, &v13);
    if ( v4 == 1 )
    {
      v8 = ((*a2 & 0x3FFFFFFF) << 18) + 0x3FFFF;
      v10[0] = (*a2 >> 12) & 0xFFFFFFFFC0000LL;
      v10[1] = v8 + v10[0];
      v7 = VsmmSvcpExecuteFastSimpleCall(18, v10, 0x10u, 0, 0);
      if ( v7 < 0 )
      {
        VidTraceErrorStatusInternal0("VsmmIoSpaceInflateRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c", 429);
        VsmmIoSpaceDeflateRange(1, a2);
      }
    }
  }
  else
  {
    VidTraceErrorStatusInternal0("VsmmIoSpaceInflateRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c", 410);
    v12 = 0;
    if ( (int)WinHvRemovePhysicalMemory(0, v6, v11, &v12) < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmIoSpaceInflateRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c", 452);
      __int2c();
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400e3d7c  mov     rax, rsp
0x1400e3d7f  mov     [rax+8], rbx
0x1400e3d83  push    rbp
0x1400e3d84  push    rsi
0x1400e3d85  push    rdi
0x1400e3d86  push    r13
0x1400e3d88  push    r14
0x1400e3d8a  sub     rsp, 40h
0x1400e3d8e  mov     rdi, [rdx]
0x1400e3d91  lea     r9, [rax+10h]
0x1400e3d95  mov     rsi, rdi
0x1400e3d98  mov     qword ptr [rax+10h], 0
0x1400e3da0  and     edi, 3FFFFFFFh
0x1400e3da6  shr     rsi, 0Ch
0x1400e3daa  mov     r14, rdx
0x1400e3dad  mov     qword ptr [rax+20h], 0
0x1400e3db5  mov     ebp, ecx
0x1400e3db7  inc     rdi
0x1400e3dba  mov     r13, 0FFFFFFFFC0000h
0x1400e3dc4  shl     rdi, 12h
0x1400e3dc8  and     rsi, r13
0x1400e3dcb  mov     r8, rdi
0x1400e3dce  mov     rdx, rsi
0x1400e3dd1  mov     cl, 1
0x1400e3dd3  call    cs:__imp_WinHvAddPhysicalMemory
0x1400e3dda  nop     dword ptr [rax+rax+00h]
0x1400e3ddf  mov     ebx, eax
0x1400e3de1  test    eax, eax
0x1400e3de3  jns     short loc_1400E3E56
0x1400e3de5  mov     r9d, eax
0x1400e3de8  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e3def  mov     r8d, 19Ah
0x1400e3df5  lea     rcx, aVsmmiospaceinf; "VsmmIoSpaceInflateRange"
0x1400e3dfc  call    VidTraceErrorStatusInternal0
0x1400e3e01  mov     r8, [rsp+68h+arg_8]
0x1400e3e06  lea     r9, [rsp+68h+arg_10]
0x1400e3e0e  mov     rdx, rsi
0x1400e3e11  mov     [rsp+68h+arg_10], 0
0x1400e3e1d  xor     ecx, ecx
0x1400e3e1f  call    cs:__imp_WinHvRemovePhysicalMemory
0x1400e3e26  nop     dword ptr [rax+rax+00h]
0x1400e3e2b  test    eax, eax
0x1400e3e2d  jns     loc_1400E3EEA
0x1400e3e33  mov     r9d, eax
0x1400e3e36  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e3e3d  mov     r8d, 1C4h
0x1400e3e43  lea     rcx, aVsmmiospaceinf; "VsmmIoSpaceInflateRange"
0x1400e3e4a  call    VidTraceErrorStatusInternal0
0x1400e3e4f  int     2Ch; Windows NT - assertion failure
0x1400e3e51  jmp     loc_1400E3EEA
0x1400e3e56  lea     r9, [rsp+68h+arg_18]
0x1400e3e5e  mov     r8, rdi
0x1400e3e61  mov     rdx, rsi
0x1400e3e64  xor     ecx, ecx
0x1400e3e66  call    cs:__imp_WinHvAddPhysicalMemory
0x1400e3e6d  nop     dword ptr [rax+rax+00h]
0x1400e3e72  cmp     ebp, 1
0x1400e3e75  jnz     short loc_1400E3EEA
0x1400e3e77  mov     rcx, [r14]
0x1400e3e7a  lea     r8d, [rbp+0Fh]
0x1400e3e7e  mov     rax, rcx
0x1400e3e81  mov     [rsp+68h+var_48], 0
0x1400e3e89  and     ecx, 3FFFFFFFh
0x1400e3e8f  shr     rax, 0Ch
0x1400e3e93  shl     rcx, 12h
0x1400e3e97  lea     rdx, [rsp+68h+var_38]
0x1400e3e9c  and     rax, r13
0x1400e3e9f  add     rcx, 3FFFFh
0x1400e3ea6  mov     [rsp+68h+var_38], rax
0x1400e3eab  xor     r9d, r9d
0x1400e3eae  add     rax, rcx
0x1400e3eb1  lea     ecx, [rbp+11h]
0x1400e3eb4  mov     [rsp+68h+var_30], rax
0x1400e3eb9  call    VsmmSvcpExecuteFastSimpleCall
0x1400e3ebe  mov     ebx, eax
0x1400e3ec0  test    eax, eax
0x1400e3ec2  jns     short loc_1400E3EEA
0x1400e3ec4  mov     r9d, eax
0x1400e3ec7  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e3ece  mov     r8d, 1ADh
0x1400e3ed4  lea     rcx, aVsmmiospaceinf; "VsmmIoSpaceInflateRange"
0x1400e3edb  call    VidTraceErrorStatusInternal0
0x1400e3ee0  mov     rdx, r14
0x1400e3ee3  mov     ecx, ebp
0x1400e3ee5  call    VsmmIoSpaceDeflateRange
0x1400e3eea  mov     eax, ebx
0x1400e3eec  mov     rbx, [rsp+68h+arg_0]
0x1400e3ef1  add     rsp, 40h
0x1400e3ef5  pop     r14
0x1400e3ef7  pop     r13
0x1400e3ef9  pop     rdi
0x1400e3efa  pop     rsi
0x1400e3efb  pop     rbp
0x1400e3efc  retn
```
