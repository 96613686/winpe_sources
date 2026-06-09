# GetCanonicalizationProofPhysicalPath(ushort const *,int,STRU *)

- ea: `0x180019ff8`
- end: `0x18001a05f`
- name: `?GetCanonicalizationProofPhysicalPath@@YAJPEBGHPEAVSTRU@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, struct STRU *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c4c`
- `0x18001a914`

## callees

- `0x180019ff8`

## import_xrefs

- `iisutil!?UnescapeOnly@STRU@@QEAAJXZ` at `0x18001a022`
- `iisutil!?UnescapeOnly@STRU@@QEAAJXZ` at `0x18001a022`
- `iisutil!MakePathCanonicalizationProof` at `0x18001a00f`
- `iisutil!MakePathCanonicalizationProof` at `0x18001a00f`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001a047`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001a047`

## pseudocode

```c
__int64 __fastcall GetCanonicalizationProofPhysicalPath(const unsigned __int16 *a1, int a2, struct STRU *a3)
{
  int PathCanonicalizationProof; // edi
  __int64 v6; // rcx
  __int64 v7; // rdx

  PathCanonicalizationProof = MakePathCanonicalizationProof(a1, a3);
  if ( PathCanonicalizationProof >= 0 )
  {
    if ( a2 )
      STRU::UnescapeOnly(a3);
    if ( *((_DWORD *)a3 + 12) )
    {
      v6 = *((unsigned int *)a3 + 12);
      v7 = *((_QWORD *)a3 + 4);
      if ( *(_WORD *)(v7 + 2 * v6 - 2) == 92 )
      {
        *(_WORD *)(v7 + 2 * v6 - 2) = 0;
        STRU::SyncWithBuffer(a3);
      }
    }
  }
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180019ff8  mov     [rsp+arg_0], rbx
0x180019ffd  mov     [rsp+arg_8], rsi
0x18001a002  push    rdi
0x18001a003  sub     rsp, 20h
0x18001a007  mov     esi, edx
0x18001a009  mov     rbx, r8
0x18001a00c  mov     rdx, r8
0x18001a00f  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18001a015  mov     edi, eax
0x18001a017  test    eax, eax
0x18001a019  js      short loc_18001A04D
0x18001a01b  test    esi, esi
0x18001a01d  jz      short loc_18001A028
0x18001a01f  mov     rcx, rbx
0x18001a022  call    cs:__imp_?UnescapeOnly@STRU@@QEAAJXZ; STRU::UnescapeOnly(void)
0x18001a028  cmp     dword ptr [rbx+30h], 0
0x18001a02c  jbe     short loc_18001A04D
0x18001a02e  mov     ecx, [rbx+30h]
0x18001a031  mov     rdx, [rbx+20h]
0x18001a035  cmp     word ptr [rdx+rcx*2-2], 5Ch ; '\'
0x18001a03b  jnz     short loc_18001A04D
0x18001a03d  xor     eax, eax
0x18001a03f  mov     [rdx+rcx*2-2], ax
0x18001a044  mov     rcx, rbx
0x18001a047  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001a04d  mov     rbx, [rsp+28h+arg_0]
0x18001a052  mov     eax, edi
0x18001a054  mov     rsi, [rsp+28h+arg_8]
0x18001a059  add     rsp, 20h
0x18001a05d  pop     rdi
0x18001a05e  retn
```
