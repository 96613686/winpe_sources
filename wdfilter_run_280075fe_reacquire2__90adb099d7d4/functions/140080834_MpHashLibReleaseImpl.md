# MpHashLibReleaseImpl

- ea: `0x140080834`
- end: `0x14008088c`
- name: `MpHashLibReleaseImpl`
- size: `88`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400506a4`
- `0x14007bef0`
- `0x140080828`

## callees

- `0x140080834`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x140080865`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140080865`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080879`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080879`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14008084c`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14008084c`

## pseudocode

```c
void __fastcall MpHashLibReleaseImpl(char *P)
{
  void *v2; // rcx

  if ( P )
  {
    v2 = (void *)*((_QWORD *)P + 1);
    if ( v2 )
      BCryptCloseAlgorithmProvider(v2, 0);
    if ( *((_DWORD *)P + 32) )
      ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(P + 32));
    ExFreePoolWithTag(P, 0x6864504Du);
  }
}

```

## disassembly

```asm
0x140080834  test    rcx, rcx
0x140080837  jz      short locret_14008088A
0x140080839  push    rbx
0x14008083a  sub     rsp, 20h
0x14008083e  mov     rbx, rcx
0x140080841  mov     rcx, [rcx+8]; hAlgorithm
0x140080845  test    rcx, rcx
0x140080848  jz      short loc_140080858
0x14008084a  xor     edx, edx; dwFlags
0x14008084c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140080853  nop     dword ptr [rax+rax+00h]
0x140080858  cmp     dword ptr [rbx+80h], 0
0x14008085f  jz      short loc_140080871
0x140080861  lea     rcx, [rbx+20h]; Lookaside
0x140080865  call    cs:__imp_ExDeleteLookasideListEx
0x14008086c  nop     dword ptr [rax+rax+00h]
0x140080871  mov     edx, 6864504Dh; Tag
0x140080876  mov     rcx, rbx; P
0x140080879  call    cs:__imp_ExFreePoolWithTag
0x140080880  nop     dword ptr [rax+rax+00h]
0x140080885  add     rsp, 20h
0x140080889  pop     rbx
0x14008088a  retn
```
