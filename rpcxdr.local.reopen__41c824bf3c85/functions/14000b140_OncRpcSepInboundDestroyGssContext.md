# OncRpcSepInboundDestroyGssContext

- ea: `0x14000b140`
- end: `0x14000b1b2`
- name: `OncRpcSepInboundDestroyGssContext`
- size: `114`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000aa3c`
- `0x14000af44`
- `0x14000b1b8`
- `0x14000bb64`

## callees

- `0x14000b140`
- `0x14000cdf8`
- `0x140012a60`

## import_xrefs

- `ksecdd!DeleteSecurityContext` at `0x14000b18c`
- `ksecdd!DeleteSecurityContext` at `0x14000b18c`

## pseudocode

```c
__int64 __fastcall OncRpcSepInboundDestroyGssContext(__int64 a1, __int64 a2, int a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_dZ(WPP_GLOBAL_Control->AttachedDevice, 14, a3, *(_DWORD *)(a1 + 64), a1 + 160);
  if ( (*(_DWORD *)(a1 + 112) & 1) != 0 )
  {
    DeleteSecurityContext((PCtxtHandle)(a1 + 88));
    *(_DWORD *)(a1 + 112) &= ~1u;
  }
  return NfsMemMgrStructureFreeByHandle(qword_14001AA00, a1);
}

```

## disassembly

```asm
0x14000b140  push    rbx
0x14000b142  sub     rsp, 30h
0x14000b146  mov     rbx, rcx
0x14000b149  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b150  lea     rax, WPP_GLOBAL_Control
0x14000b157  cmp     rcx, rax
0x14000b15a  jz      short loc_14000B181
0x14000b15c  mov     eax, [rcx+2Ch]
0x14000b15f  test    al, 40h
0x14000b161  jz      short loc_14000B181
0x14000b163  mov     r9d, [rbx+40h]
0x14000b167  lea     rax, [rbx+0A0h]
0x14000b16e  mov     rcx, [rcx+18h]
0x14000b172  mov     edx, 0Eh
0x14000b177  mov     [rsp+38h+var_18], rax
0x14000b17c  call    WPP_SF_dZ
0x14000b181  mov     eax, [rbx+70h]
0x14000b184  test    al, 1
0x14000b186  jz      short loc_14000B19C
0x14000b188  lea     rcx, [rbx+58h]; phContext
0x14000b18c  call    cs:__imp_DeleteSecurityContext
0x14000b193  nop     dword ptr [rax+rax+00h]
0x14000b198  and     dword ptr [rbx+70h], 0FFFFFFFEh
0x14000b19c  mov     rcx, cs:qword_14001AA00
0x14000b1a3  mov     rdx, rbx
0x14000b1a6  call    NfsMemMgrStructureFreeByHandle
0x14000b1ab  add     rsp, 30h
0x14000b1af  pop     rbx
0x14000b1b0  retn
```
