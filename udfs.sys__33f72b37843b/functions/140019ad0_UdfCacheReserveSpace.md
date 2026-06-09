# UdfCacheReserveSpace

- ea: `0x140019ad0`
- end: `0x140019b89`
- name: `UdfCacheReserveSpace`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a478`

## callees

- `0x140019ad0`
- `0x14001b59c`

## import_xrefs

- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x140019b2c`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x140019b2c`

## pseudocode

```c
BOOLEAN __fastcall UdfCacheReserveSpace(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, unsigned int *a5, char a6)
{
  unsigned int v6; // r11d
  unsigned int v8; // r12d
  LARGE_MCB *v11; // rcx
  unsigned int v12; // edi
  unsigned int v13; // eax
  LONGLONG v14; // r8
  BOOLEAN v15; // bp

  v6 = *(_DWORD *)(a3 + 16);
  v8 = *(_DWORD *)(a2 + 744);
  v11 = *(LARGE_MCB **)(a2 + 736);
  v12 = *a5;
  if ( v6 - v8 <= *a5 )
    v12 = *(_DWORD *)(a3 + 16) - v8;
  v13 = v8 + *a5;
  v14 = (unsigned int)*a4;
  if ( v6 - v8 <= *a5 )
    v13 = v6;
  *(_DWORD *)(a2 + 744) = v13;
  v15 = FsRtlAddLargeMcbEntry(v11, v8, v14, v12);
  if ( v15 )
  {
    if ( !a6 || (int)UdfSeqCacheWriteZeroesAtPsn(a1, a2, (unsigned int)*a4, v12) >= 0 )
    {
      *a4 += v12;
      *a5 -= v12;
      return v15;
    }
    *(_BYTE *)(a1 + 895) |= 4u;
    v15 = 0;
  }
  *(_DWORD *)(a2 + 744) = v8;
  return v15;
}

```

## disassembly

```asm
0x140019ad0  push    rbx
0x140019ad2  push    rbp
0x140019ad3  push    rsi
0x140019ad4  push    rdi
0x140019ad5  push    r12
0x140019ad7  push    r14
0x140019ad9  push    r15
0x140019adb  sub     rsp, 30h
0x140019adf  mov     r11d, [r8+10h]
0x140019ae3  mov     rbx, r9
0x140019ae6  mov     r12d, [rdx+2E8h]
0x140019aed  mov     r15, rdx
0x140019af0  mov     r14, [rsp+68h+arg_20]
0x140019af8  mov     r10d, r11d
0x140019afb  sub     r10d, r12d
0x140019afe  mov     rsi, rcx
0x140019b01  mov     rcx, [r15+2E0h]; Mcb
0x140019b08  mov     r8d, [r14]
0x140019b0b  cmp     r10d, r8d
0x140019b0e  mov     edi, r8d
0x140019b11  cmovbe  edi, r10d
0x140019b15  mov     r9d, edi; SectorCount
0x140019b18  lea     eax, [r12+r8]
0x140019b1c  mov     r8d, [rbx]; Lbn
0x140019b1f  cmovbe  eax, r11d
0x140019b23  mov     [rdx+2E8h], eax
0x140019b29  mov     edx, r12d; Vbn
0x140019b2c  call    cs:__imp_FsRtlAddLargeMcbEntry
0x140019b33  nop     dword ptr [rax+rax+00h]
0x140019b38  mov     bpl, al
0x140019b3b  test    al, al
0x140019b3d  jz      short loc_140019B68
0x140019b3f  cmp     [rsp+68h+arg_28], 0
0x140019b47  jz      short loc_140019B82
0x140019b49  mov     r8d, [rbx]
0x140019b4c  mov     r9d, edi
0x140019b4f  mov     rdx, r15
0x140019b52  mov     rcx, rsi
0x140019b55  call    UdfSeqCacheWriteZeroesAtPsn
0x140019b5a  test    eax, eax
0x140019b5c  jns     short loc_140019B82
0x140019b5e  or      byte ptr [rsi+37Fh], 4
0x140019b65  xor     bpl, bpl
0x140019b68  mov     [r15+2E8h], r12d
0x140019b6f  mov     al, bpl
0x140019b72  add     rsp, 30h
0x140019b76  pop     r15
0x140019b78  pop     r14
0x140019b7a  pop     r12
0x140019b7c  pop     rdi
0x140019b7d  pop     rsi
0x140019b7e  pop     rbp
0x140019b7f  pop     rbx
0x140019b80  retn
0x140019b82  add     [rbx], edi
0x140019b84  sub     [r14], edi
0x140019b87  jmp     short loc_140019B6F
```
