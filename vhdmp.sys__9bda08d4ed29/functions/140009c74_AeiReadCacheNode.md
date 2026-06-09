# AeiReadCacheNode

- ea: `0x140009c74`
- end: `0x140009dca`
- name: `AeiReadCacheNode`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000861c`

## callees

- `0x140002870`
- `0x140009c74`
- `0x140009f18`
- `0x14000b340`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140009d3c`
- `ntoskrnl!IoAllocateMdl` at `0x140009d3c`
- `ntoskrnl!IoInitializeIrpEx` at `0x140009cfa`
- `ntoskrnl!IoInitializeIrpEx` at `0x140009cfa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140009c91`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140009c91`

## pseudocode

```c
__int64 __fastcall AeiReadCacheNode(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // r14
  _QWORD *v7; // rbp
  unsigned __int16 v8; // si
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // r9
  _QWORD *v12; // rbx
  PMDL Mdl; // rax
  __int64 result; // rax

  v2 = a1[1];
  v5 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v2 + 64));
  v6 = v5;
  if ( v5 )
  {
    v5[21] = v2;
    v5[23] = 0;
    v7 = v5 + 28;
    v8 = *(_WORD *)(v2 + 24);
    v9 = *(_QWORD *)(v2 + 16);
    v10 = *(_QWORD *)(v2 + 8);
    memset(v5 + 3, 0, 0x58u);
    *v6 = v10;
    v6[1] = v9;
    v6[2] = v7;
    LOBYTE(v11) = *(_BYTE *)(v10 + 544);
    IoInitializeIrpEx(v7, -1, v8, v11);
    v7[18] = v6;
    v12 = v6 + 14;
    *((_WORD *)v6 + 108) = 255;
    *((_DWORD *)v6 + 53) = 1073741825;
    Mdl = IoAllocateMdl(0, 0x1000u, 0, 0, 0);
    v6[23] = Mdl;
    if ( Mdl )
    {
      Mdl->Process = 0;
      *(_DWORD *)(v6[23] + 40LL) = 0;
      *((_DWORD *)v6 + 52) = 1;
      return AeiPerformCacheRead(a1, a2, v12);
    }
    AeSupportFreeIo(v6 + 14);
  }
  *(_BYTE *)(a2 + 12) = 1;
  *(_QWORD *)(a2 + 16) = AeiCacheReadReserveIo;
  result = AeAcquireAsyncLock(*a1, a1 + 68, a2);
  if ( (_BYTE)result )
  {
    v12 = (_QWORD *)a1[67];
    return AeiPerformCacheRead(a1, a2, v12);
  }
  return result;
}

```

## disassembly

```asm
0x140009c74  push    rbx
0x140009c76  push    rbp
0x140009c77  push    rsi
0x140009c78  push    rdi
0x140009c79  push    r13
0x140009c7b  push    r14
0x140009c7d  push    r15
0x140009c7f  sub     rsp, 30h
0x140009c83  mov     rdi, [rcx+8]
0x140009c87  mov     r15, rcx
0x140009c8a  mov     r13, rdx
0x140009c8d  lea     rcx, [rdi+40h]; Lookaside
0x140009c91  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140009c98  nop     dword ptr [rax+rax+00h]
0x140009c9d  mov     r14, rax
0x140009ca0  test    rax, rax
0x140009ca3  jz      loc_140009D9B
0x140009ca9  mov     [rax+0A8h], rdi
0x140009cb0  lea     rcx, [rax+18h]; void *
0x140009cb4  mov     qword ptr [rax+0B8h], 0
0x140009cbf  lea     rbp, [rax+0E0h]
0x140009cc6  movzx   esi, word ptr [rdi+18h]
0x140009cca  xor     edx, edx; Val
0x140009ccc  mov     rbx, [rdi+10h]
0x140009cd0  mov     rdi, [rdi+8]
0x140009cd4  lea     r8d, [rdx+58h]; Size
0x140009cd8  call    memset
0x140009cdd  mov     [r14], rdi
0x140009ce0  movzx   r8d, si
0x140009ce4  mov     [r14+8], rbx
0x140009ce8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140009cec  mov     [r14+10h], rbp
0x140009cf0  mov     rcx, rbp
0x140009cf3  mov     r9b, [rdi+220h]
0x140009cfa  call    cs:__imp_IoInitializeIrpEx
0x140009d01  nop     dword ptr [rax+rax+00h]
0x140009d06  mov     [rbp+90h], r14
0x140009d0d  lea     rbx, [r14+70h]
0x140009d11  xor     r9d, r9d; ChargeQuota
0x140009d14  mov     word ptr [r14+0D8h], 0FFh
0x140009d1e  xor     r8d, r8d; SecondaryBuffer
0x140009d21  mov     dword ptr [r14+0D4h], 40000001h
0x140009d2c  mov     edx, 1000h; Length
0x140009d31  mov     [rsp+68h+Irp], 0; Irp
0x140009d3a  xor     ecx, ecx; VirtualAddress
0x140009d3c  call    cs:__imp_IoAllocateMdl
0x140009d43  nop     dword ptr [rax+rax+00h]
0x140009d48  mov     [r14+0B8h], rax
0x140009d4f  test    rax, rax
0x140009d52  jz      short loc_140009D93
0x140009d54  mov     qword ptr [rax+10h], 0
0x140009d5c  mov     rax, [r14+0B8h]
0x140009d63  mov     dword ptr [rax+28h], 0
0x140009d6a  mov     dword ptr [r14+0D0h], 1
0x140009d75  mov     r8, rbx
0x140009d78  mov     rdx, r13
0x140009d7b  mov     rcx, r15
0x140009d7e  call    AeiPerformCacheRead
0x140009d83  add     rsp, 30h
0x140009d87  pop     r15
0x140009d89  pop     r14
0x140009d8b  pop     r13
0x140009d8d  pop     rdi
0x140009d8e  pop     rsi
0x140009d8f  pop     rbp
0x140009d90  pop     rbx
0x140009d91  retn
0x140009d93  mov     rcx, rbx
0x140009d96  call    AeSupportFreeIo
0x140009d9b  lea     rax, AeiCacheReadReserveIo
0x140009da2  mov     byte ptr [r13+0Ch], 1
0x140009da7  mov     [r13+10h], rax
0x140009dab  lea     rdx, [r15+220h]
0x140009db2  mov     rcx, [r15]
0x140009db5  mov     r8, r13
0x140009db8  call    AeAcquireAsyncLock
0x140009dbd  test    al, al
0x140009dbf  jz      short loc_140009D83
0x140009dc1  mov     rbx, [r15+218h]
0x140009dc8  jmp     short loc_140009D75
```
