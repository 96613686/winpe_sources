# VsmmIoSpaceInflateRange

- ea: `0x1400e6914`
- end: `0x1400e6a96`
- name: `VsmmIoSpaceInflateRange`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002664c`

## callees

- `0x140023804`
- `0x14002f724`
- `0x1400e6800`
- `0x1400e6914`

## import_xrefs

- `winhvr!WinHvAddPhysicalMemory` at `0x1400e696b`
- `winhvr!WinHvAddPhysicalMemory` at `0x1400e69fe`
- `winhvr!WinHvAddPhysicalMemory` at `0x1400e696b`
- `winhvr!WinHvAddPhysicalMemory` at `0x1400e69fe`
- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e69b7`
- `winhvr!WinHvRemovePhysicalMemory` at `0x1400e69b7`

## pseudocode

```c
__int64 __fastcall VsmmIoSpaceInflateRange(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rsi
  int v4; // ebp
  __int64 v5; // rdi
  __int64 v6; // rsi
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  _QWORD v13[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+78h] [rbp+10h] BYREF
  __int64 v15; // [rsp+80h] [rbp+18h] BYREF
  __int64 v16; // [rsp+88h] [rbp+20h] BYREF

  v2 = *a2;
  v14 = 0;
  v16 = 0;
  v4 = a1;
  v5 = ((v2 & 0x3FFFFFFF) + 1) << 18;
  v6 = (v2 >> 12) & 0xFFFFFFFFC0000LL;
  LOBYTE(a1) = 1;
  v7 = WinHvAddPhysicalMemory(a1, v6, v5, &v14);
  v8 = v7;
  if ( v7 >= 0 )
  {
    WinHvAddPhysicalMemory(0, v6, v5, &v16);
    if ( v4 == 1 )
    {
      v10 = ((*a2 & 0x3FFFFFFF) << 18) + 0x3FFFF;
      v13[0] = (*a2 >> 12) & 0xFFFFFFFFC0000LL;
      v13[1] = v10 + v13[0];
      v11 = VsmmSvcpExecuteFastSimpleCall(18, v13, 16);
      v8 = v11;
      if ( v11 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VsmmIoSpaceInflateRange",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c",
          429,
          (unsigned int)v11);
        VsmmIoSpaceDeflateRange(1, a2);
      }
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmIoSpaceInflateRange",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c",
      410,
      (unsigned int)v7);
    v15 = 0;
    v9 = WinHvRemovePhysicalMemory(0, v6, v14, &v15);
    if ( v9 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmIoSpaceInflateRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospace.c",
        452,
        (unsigned int)v9);
      __int2c();
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1400e6914  mov     rax, rsp
0x1400e6917  mov     [rax+8], rbx
0x1400e691b  push    rbp
0x1400e691c  push    rsi
0x1400e691d  push    rdi
0x1400e691e  push    r13
0x1400e6920  push    r14
0x1400e6922  sub     rsp, 40h
0x1400e6926  mov     rdi, [rdx]
0x1400e6929  lea     r9, [rax+10h]
0x1400e692d  mov     rsi, rdi
0x1400e6930  mov     qword ptr [rax+10h], 0
0x1400e6938  and     edi, 3FFFFFFFh
0x1400e693e  shr     rsi, 0Ch
0x1400e6942  mov     r14, rdx
0x1400e6945  mov     qword ptr [rax+20h], 0
0x1400e694d  mov     ebp, ecx
0x1400e694f  inc     rdi
0x1400e6952  mov     r13, 0FFFFFFFFC0000h
0x1400e695c  shl     rdi, 12h
0x1400e6960  and     rsi, r13
0x1400e6963  mov     r8, rdi
0x1400e6966  mov     rdx, rsi
0x1400e6969  mov     cl, 1
0x1400e696b  call    cs:__imp_WinHvAddPhysicalMemory
0x1400e6972  nop     dword ptr [rax+rax+00h]
0x1400e6977  mov     ebx, eax
0x1400e6979  test    eax, eax
0x1400e697b  jns     short loc_1400E69EE
0x1400e697d  mov     r9d, eax
0x1400e6980  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e6987  mov     r8d, 19Ah
0x1400e698d  lea     rcx, aVsmmiospaceinf; "VsmmIoSpaceInflateRange"
0x1400e6994  call    VidTraceErrorStatusInternal0
0x1400e6999  mov     r8, [rsp+68h+arg_8]
0x1400e699e  lea     r9, [rsp+68h+arg_10]
0x1400e69a6  mov     rdx, rsi
0x1400e69a9  mov     [rsp+68h+arg_10], 0
0x1400e69b5  xor     ecx, ecx
0x1400e69b7  call    cs:__imp_WinHvRemovePhysicalMemory
0x1400e69be  nop     dword ptr [rax+rax+00h]
0x1400e69c3  test    eax, eax
0x1400e69c5  jns     loc_1400E6A82
0x1400e69cb  mov     r9d, eax
0x1400e69ce  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e69d5  mov     r8d, 1C4h
0x1400e69db  lea     rcx, aVsmmiospaceinf; "VsmmIoSpaceInflateRange"
0x1400e69e2  call    VidTraceErrorStatusInternal0
0x1400e69e7  int     2Ch; Windows NT - assertion failure
0x1400e69e9  jmp     loc_1400E6A82
0x1400e69ee  lea     r9, [rsp+68h+arg_18]
0x1400e69f6  mov     r8, rdi
0x1400e69f9  mov     rdx, rsi
0x1400e69fc  xor     ecx, ecx
0x1400e69fe  call    cs:__imp_WinHvAddPhysicalMemory
0x1400e6a05  nop     dword ptr [rax+rax+00h]
0x1400e6a0a  cmp     ebp, 1
0x1400e6a0d  jnz     short loc_1400E6A82
0x1400e6a0f  mov     rcx, [r14]
0x1400e6a12  lea     r8d, [rbp+0Fh]
0x1400e6a16  mov     rax, rcx
0x1400e6a19  mov     [rsp+68h+var_48], 0
0x1400e6a21  and     ecx, 3FFFFFFFh
0x1400e6a27  shr     rax, 0Ch
0x1400e6a2b  shl     rcx, 12h
0x1400e6a2f  lea     rdx, [rsp+68h+var_38]
0x1400e6a34  and     rax, r13
0x1400e6a37  add     rcx, 3FFFFh
0x1400e6a3e  mov     [rsp+68h+var_38], rax
0x1400e6a43  xor     r9d, r9d
0x1400e6a46  add     rax, rcx
0x1400e6a49  lea     ecx, [rbp+11h]
0x1400e6a4c  mov     [rsp+68h+var_30], rax
0x1400e6a51  call    VsmmSvcpExecuteFastSimpleCall
0x1400e6a56  mov     ebx, eax
0x1400e6a58  test    eax, eax
0x1400e6a5a  jns     short loc_1400E6A82
0x1400e6a5c  mov     r9d, eax
0x1400e6a5f  lea     rdx, aOnecoreVmVidSy_68; "onecore\\vm\\vid\\sys\\vsmm\\vsmmiospac"...
0x1400e6a66  mov     r8d, 1ADh
0x1400e6a6c  lea     rcx, aVsmmiospaceinf; "VsmmIoSpaceInflateRange"
0x1400e6a73  call    VidTraceErrorStatusInternal0
0x1400e6a78  mov     rdx, r14
0x1400e6a7b  mov     ecx, ebp
0x1400e6a7d  call    VsmmIoSpaceDeflateRange
0x1400e6a82  mov     eax, ebx
0x1400e6a84  mov     rbx, [rsp+68h+arg_0]
0x1400e6a89  add     rsp, 40h
0x1400e6a8d  pop     r14
0x1400e6a8f  pop     r13
0x1400e6a91  pop     rdi
0x1400e6a92  pop     rsi
0x1400e6a93  pop     rbp
0x1400e6a94  retn
```
