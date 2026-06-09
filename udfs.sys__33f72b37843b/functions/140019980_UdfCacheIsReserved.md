# UdfCacheIsReserved

- ea: `0x140019980`
- end: `0x140019ac8`
- name: `UdfCacheIsReserved`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001a478`

## callees

- `0x140009980`
- `0x140019980`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400199f3`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400199f3`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140019a70`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140019a70`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x140019a9a`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x140019a9a`

## pseudocode

```c
__int64 __fastcall UdfCacheIsReserved(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  unsigned int v4; // esi
  unsigned int v5; // edi
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  LONGLONG v14; // r8
  LONGLONG v15; // r9
  LONGLONG v16; // rdx
  __int64 Lbn; // [rsp+40h] [rbp-28h] BYREF
  __int64 SectorCountFromLbn; // [rsp+70h] [rbp+8h] BYREF
  __int64 StartingLbn; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  Lbn = 0;
  v5 = 0;
  SectorCountFromLbn = 0;
  StartingLbn = 0;
  while ( v5 < *(unsigned __int16 *)(a3 + 24) )
  {
    if ( FsRtlLookupLargeMcbEntry(
           *(PLARGE_MCB *)(a2 + 736),
           *(unsigned int *)(a3 + 16),
           &Lbn,
           &SectorCountFromLbn,
           &StartingLbn,
           0,
           0) )
    {
      v10 = (unsigned int)SectorCountFromLbn;
      if ( StartingLbn != -1 )
      {
        v11 = *(unsigned __int16 *)(a3 + 24);
        *a4 = 1;
        if ( (unsigned int)v10 < v11 )
        {
          v12 = 32 * v10;
          *(_OWORD *)(v12 + a3) = *(_OWORD *)a3;
          *(_OWORD *)(v12 + a3 + 16) = *(_OWORD *)(a3 + 16);
          *(_WORD *)(a3 + 24) = v10;
          *(_DWORD *)(v12 + a3 + 16) += v10;
          *(_WORD *)(v12 + a3 + 24) -= v10;
          v13 = *(_QWORD *)(a3 + 8);
          if ( v13 != -1 )
          {
            LOBYTE(v9) = 1;
            UdfSeqCacheUpdateFileRefCount(v13, v9, 0);
          }
        }
        FsRtlRemoveLargeMcbEntry(*(PLARGE_MCB *)(a2 + 736), *(unsigned int *)(a3 + 16), *(unsigned __int16 *)(a3 + 24));
        v14 = Lbn;
        v15 = *(unsigned __int16 *)(a3 + 24);
        v16 = *(unsigned int *)(a3 + 16);
        *(_DWORD *)(a3 + 20) = Lbn;
        *(_WORD *)(a3 + 26) = 257;
        if ( !FsRtlAddLargeMcbEntry(*(PLARGE_MCB *)(a2 + 728), v16, v14, v15) )
          return (unsigned int)-1073741801;
        return v4;
      }
    }
    else
    {
      LODWORD(v10) = 1;
    }
    v5 += v10;
  }
  return v4;
}

```

## disassembly

```asm
0x140019980  mov     rax, rsp
0x140019983  mov     [rax+10h], rbx
0x140019987  mov     [rax+20h], rbp
0x14001998b  mov     [rax+8], rcx
0x14001998f  push    rsi
0x140019990  push    rdi
0x140019991  push    r14
0x140019993  sub     rsp, 50h
0x140019997  xor     esi, esi
0x140019999  mov     qword ptr [rax-28h], 0
0x1400199a1  xor     edi, edi
0x1400199a3  mov     qword ptr [rax+8], 0
0x1400199ab  mov     r14, r9
0x1400199ae  mov     qword ptr [rax+18h], 0
0x1400199b6  mov     rbx, r8
0x1400199b9  mov     rbp, rdx
0x1400199bc  movzx   eax, word ptr [rbx+18h]
0x1400199c0  cmp     edi, eax
0x1400199c2  jnb     loc_140019AB0
0x1400199c8  mov     edx, [rbx+10h]; Vbn
0x1400199cb  lea     rax, [rsp+68h+arg_10]
0x1400199d3  mov     rcx, [rbp+2E0h]; Mcb
0x1400199da  lea     r9, [rsp+68h+SectorCountFromLbn]; SectorCountFromLbn
0x1400199df  mov     [rsp+68h+Index], rsi; Index
0x1400199e4  lea     r8, [rsp+68h+Lbn]; Lbn
0x1400199e9  mov     [rsp+68h+SectorCountFromStartingLbn], rsi; SectorCountFromStartingLbn
0x1400199ee  mov     [rsp+68h+StartingLbn], rax; StartingLbn
0x1400199f3  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x1400199fa  nop     dword ptr [rax+rax+00h]
0x1400199ff  test    al, al
0x140019a01  jnz     short loc_140019A0A
0x140019a03  mov     ecx, 1
0x140019a08  jmp     short loc_140019A19
0x140019a0a  cmp     [rsp+68h+arg_10], 0FFFFFFFFFFFFFFFFh
0x140019a13  mov     ecx, dword ptr [rsp+68h+SectorCountFromLbn]
0x140019a17  jnz     short loc_140019A1D
0x140019a19  add     edi, ecx
0x140019a1b  jmp     short loc_1400199BC
0x140019a1d  movzx   eax, word ptr [rbx+18h]
0x140019a21  mov     byte ptr [r14], 1
0x140019a25  cmp     ecx, eax
0x140019a27  jnb     short loc_140019A61
0x140019a29  movups  xmm0, xmmword ptr [rbx]
0x140019a2c  mov     rax, rcx
0x140019a2f  shl     rax, 5
0x140019a33  movups  xmmword ptr [rax+rbx], xmm0
0x140019a37  movups  xmm1, xmmword ptr [rbx+10h]
0x140019a3b  movups  xmmword ptr [rax+rbx+10h], xmm1
0x140019a40  mov     [rbx+18h], cx
0x140019a44  add     [rax+rbx+10h], ecx
0x140019a48  sub     [rax+rbx+18h], cx
0x140019a4d  mov     rcx, [rbx+8]
0x140019a51  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140019a55  jz      short loc_140019A61
0x140019a57  xor     r8d, r8d
0x140019a5a  mov     dl, 1
0x140019a5c  call    UdfSeqCacheUpdateFileRefCount
0x140019a61  movzx   r8d, word ptr [rbx+18h]; SectorCount
0x140019a66  mov     edx, [rbx+10h]; Vbn
0x140019a69  mov     rcx, [rbp+2E0h]; Mcb
0x140019a70  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x140019a77  nop     dword ptr [rax+rax+00h]
0x140019a7c  mov     r8, [rsp+68h+Lbn]; Lbn
0x140019a81  movzx   r9d, word ptr [rbx+18h]; SectorCount
0x140019a86  mov     edx, [rbx+10h]; Vbn
0x140019a89  mov     [rbx+14h], r8d
0x140019a8d  mov     word ptr [rbx+1Ah], 101h
0x140019a93  mov     rcx, [rbp+2D8h]; Mcb
0x140019a9a  call    cs:__imp_FsRtlAddLargeMcbEntry
0x140019aa1  nop     dword ptr [rax+rax+00h]
0x140019aa6  test    al, al
0x140019aa8  mov     ecx, 0C0000017h
0x140019aad  cmovz   esi, ecx
0x140019ab0  lea     r11, [rsp+68h+var_18]
0x140019ab5  mov     eax, esi
0x140019ab7  mov     rbx, [r11+28h]
0x140019abb  mov     rbp, [r11+38h]
0x140019abf  mov     rsp, r11
0x140019ac2  pop     r14
0x140019ac4  pop     rdi
0x140019ac5  pop     rsi
0x140019ac6  retn
```
