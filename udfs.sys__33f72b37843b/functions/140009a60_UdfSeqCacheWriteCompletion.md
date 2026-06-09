# UdfSeqCacheWriteCompletion

- ea: `0x140009a60`
- end: `0x140009b5b`
- name: `UdfSeqCacheWriteCompletion`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140009a60`
- `0x14000a2e8`
- `0x14001093c`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140009af2`
- `ntoskrnl!IoFreeMdl` at `0x140009af2`
- `ntoskrnl!MmUnlockPages` at `0x140009ae2`
- `ntoskrnl!MmUnlockPages` at `0x140009ae2`
- `ntoskrnl!KeSetEvent` at `0x140009b39`
- `ntoskrnl!KeSetEvent` at `0x140009b39`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheWriteCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  struct _MDL *v6; // rcx
  int v7; // eax
  ERESOURCE_THREAD v8; // r8

  v3 = *(_QWORD *)(a3 + 720);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      18,
      WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids,
      *(unsigned int *)(a3 + 692),
      *(_DWORD *)(a2 + 48));
  }
  if ( *(int *)(a2 + 48) >= 0 )
  {
    *(_DWORD *)(v3 + 684) += *(_DWORD *)(a3 + 660);
    *(_DWORD *)(v3 + 668) -= *(_DWORD *)(a3 + 660);
  }
  v6 = *(struct _MDL **)(a2 + 8);
  if ( v6 )
  {
    MmUnlockPages(v6);
    IoFreeMdl(*(PMDL *)(a2 + 8));
    *(_QWORD *)(a2 + 8) = 0;
  }
  v7 = *(_DWORD *)(a3 + 4);
  if ( (v7 & 0x40) != 0 )
  {
    v8 = *(_QWORD *)(a3 + 616);
    *(_DWORD *)(a3 + 4) = v7 & 0xFFFFFFBF;
    UdfReleaseDevice((__int64)v6, v3, v8);
  }
  *(_DWORD *)(a3 + 656) = *(_DWORD *)(a2 + 48);
  KeSetEvent((PRKEVENT)(a3 + 664), 1, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140009a60  mov     [rsp+arg_0], rbx
0x140009a65  mov     [rsp+arg_8], rsi
0x140009a6a  push    rdi
0x140009a6b  sub     rsp, 30h
0x140009a6f  mov     rsi, [r8+2D0h]
0x140009a76  mov     rbx, r8
0x140009a79  mov     rdi, rdx
0x140009a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a83  lea     rax, WPP_GLOBAL_Control
0x140009a8a  cmp     rcx, rax
0x140009a8d  jz      short loc_140009ABB
0x140009a8f  test    dword ptr [rcx+2Ch], 20000000h
0x140009a96  jz      short loc_140009ABB
0x140009a98  mov     r9d, [r8+2B4h]
0x140009a9f  mov     edx, 12h
0x140009aa4  mov     eax, [rdi+30h]
0x140009aa7  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x140009aae  mov     rcx, [rcx+18h]
0x140009ab2  mov     [rsp+38h+var_18], eax
0x140009ab6  call    WPP_SF_dd
0x140009abb  cmp     dword ptr [rdi+30h], 0
0x140009abf  jl      short loc_140009AD9
0x140009ac1  mov     eax, [rbx+294h]
0x140009ac7  add     [rsi+2ACh], eax
0x140009acd  mov     eax, [rbx+294h]
0x140009ad3  sub     [rsi+29Ch], eax
0x140009ad9  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140009add  test    rcx, rcx
0x140009ae0  jz      short loc_140009B06
0x140009ae2  call    cs:__imp_MmUnlockPages
0x140009ae9  nop     dword ptr [rax+rax+00h]
0x140009aee  mov     rcx, [rdi+8]; Mdl
0x140009af2  call    cs:__imp_IoFreeMdl
0x140009af9  nop     dword ptr [rax+rax+00h]
0x140009afe  mov     qword ptr [rdi+8], 0
0x140009b06  mov     eax, [rbx+4]
0x140009b09  test    al, 40h
0x140009b0b  jz      short loc_140009B22
0x140009b0d  mov     r8, [rbx+268h]
0x140009b14  and     eax, 0FFFFFFBFh
0x140009b17  mov     rdx, rsi
0x140009b1a  mov     [rbx+4], eax
0x140009b1d  call    UdfReleaseDevice
0x140009b22  mov     eax, [rdi+30h]
0x140009b25  lea     rcx, [rbx+298h]; Event
0x140009b2c  xor     r8d, r8d; Wait
0x140009b2f  mov     [rbx+290h], eax
0x140009b35  lea     edx, [r8+1]; Increment
0x140009b39  call    cs:__imp_KeSetEvent
0x140009b40  nop     dword ptr [rax+rax+00h]
0x140009b45  mov     rbx, [rsp+38h+arg_0]
0x140009b4a  mov     eax, 0C0000016h
0x140009b4f  mov     rsi, [rsp+38h+arg_8]
0x140009b54  add     rsp, 30h
0x140009b58  pop     rdi
0x140009b59  retn
```
