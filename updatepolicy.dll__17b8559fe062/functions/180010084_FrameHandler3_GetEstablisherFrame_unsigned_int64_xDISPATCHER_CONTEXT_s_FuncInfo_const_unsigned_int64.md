# __FrameHandler3::GetEstablisherFrame(unsigned __int64 *,_xDISPATCHER_CONTEXT *,_s_FuncInfo const *,unsigned __int64 *)

- ea: `0x180010084`
- end: `0x180010174`
- name: `?GetEstablisherFrame@__FrameHandler3@@SAPEA_KPEA_KPEAU_xDISPATCHER_CONTEXT@@PEBU_s_FuncInfo@@0@Z`
- size: `240`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, const struct _s_FuncInfo *, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ffd8`
- `0x1800111f8`
- `0x180011244`
- `0x180011994`
- `0x180011b5c`
- `0x180014044`

## callees

- `0x180010084`
- `0x180011290`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800100fc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1800100fc`

## pseudocode

```c
unsigned __int64 *__fastcall __FrameHandler3::GetEstablisherFrame(
        unsigned __int64 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        const struct _s_FuncInfo *a3,
        unsigned __int64 *a4)
{
  unsigned int nTryBlocks; // ebp
  int v9; // r14d
  __int64 v10; // rdi
  __int64 v11; // rbx
  PRUNTIME_FUNCTION v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // r8
  unsigned int v15; // r9d
  _DWORD *v16; // rdx
  unsigned __int64 ImageBase; // [rsp+50h] [rbp+8h] BYREF

  nTryBlocks = a3->nTryBlocks;
  ImageBase = 0;
  v9 = __FrameHandler3::StateFromControlPc(a3, a2);
  *a4 = *a1;
  while ( nTryBlocks )
  {
    v10 = a2->ImageBase;
    v11 = a3->dispTryBlockMap + 20LL * --nTryBlocks;
    if ( v9 > *(_DWORD *)(v11 + v10 + 4) && v9 <= *(_DWORD *)(v11 + v10 + 8) )
    {
      v12 = RtlLookupFunctionEntry(a2->ControlPc, &ImageBase, 0);
      v13 = 0;
      v14 = ImageBase + *(int *)(v11 + v10 + 16);
      v15 = *(_DWORD *)(v11 + v10 + 12);
      if ( v15 )
      {
        v16 = (_DWORD *)(v14 + 12);
        while ( *v16 != (unsigned __int64)v12->BeginAddress )
        {
          v13 = (unsigned int)(v13 + 1);
          v16 += 5;
          if ( (unsigned int)v13 >= v15 )
            goto LABEL_8;
        }
LABEL_11:
        _mm_lfence();
        *a4 = *(_QWORD *)(*(int *)(v14 + 20 * v13 + 16) + *a1);
        return a4;
      }
LABEL_8:
      if ( (unsigned int)v13 < v15 )
        goto LABEL_11;
    }
  }
  return a4;
}

```

## disassembly

```asm
0x180010084  mov     rax, rsp
0x180010087  mov     [rax+10h], rbx
0x18001008b  mov     [rax+18h], rbp
0x18001008f  mov     [rax+20h], rsi
0x180010093  push    rdi
0x180010094  push    r12
0x180010096  push    r13
0x180010098  push    r14
0x18001009a  push    r15
0x18001009c  sub     rsp, 20h
0x1800100a0  mov     ebp, [r8+0Ch]
0x1800100a4  mov     r13, rcx
0x1800100a7  mov     rcx, r8; struct _s_FuncInfo *
0x1800100aa  mov     qword ptr [rax+8], 0
0x1800100b2  mov     rsi, r9
0x1800100b5  mov     r15, r8
0x1800100b8  mov     r12, rdx
0x1800100bb  call    ?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)
0x1800100c0  mov     r10, [r13+0]
0x1800100c4  mov     r14d, eax
0x1800100c7  mov     [rsi], r10
0x1800100ca  jmp     short loc_180010137
0x1800100cc  movsxd  rax, dword ptr [r15+10h]
0x1800100d0  lea     ecx, [rbp-1]
0x1800100d3  mov     rdi, [r12+8]
0x1800100d8  lea     rdx, [rcx+rcx*4]
0x1800100dc  mov     ebp, ecx
0x1800100de  lea     rbx, [rax+rdx*4]
0x1800100e2  cmp     r14d, [rbx+rdi+4]
0x1800100e7  jle     short loc_180010137
0x1800100e9  cmp     r14d, [rbx+rdi+8]
0x1800100ee  jg      short loc_180010137
0x1800100f0  mov     rcx, [r12]; ControlPc
0x1800100f4  lea     rdx, [rsp+48h+ImageBase]; ImageBase
0x1800100f9  xor     r8d, r8d; HistoryTable
0x1800100fc  call    cs:__imp_RtlLookupFunctionEntry
0x180010102  movsxd  r8, dword ptr [rbx+rdi+10h]
0x180010107  xor     ecx, ecx
0x180010109  add     r8, [rsp+48h+ImageBase]
0x18001010e  mov     r9d, [rbx+rdi+0Ch]
0x180010113  mov     r10d, [rax]
0x180010116  test    r9d, r9d
0x180010119  jz      short loc_180010132
0x18001011b  lea     rdx, [r8+0Ch]
0x18001011f  movsxd  rax, dword ptr [rdx]
0x180010122  cmp     rax, r10
0x180010125  jz      short loc_18001013D
0x180010127  inc     ecx
0x180010129  add     rdx, 14h
0x18001012d  cmp     ecx, r9d
0x180010130  jb      short loc_18001011F
0x180010132  cmp     ecx, r9d
0x180010135  jb      short loc_18001013D
0x180010137  test    ebp, ebp
0x180010139  jnz     short loc_1800100CC
0x18001013b  jmp     short loc_180010154
0x18001013d  lfence
0x180010140  mov     rax, [r13+0]
0x180010144  lea     rcx, [rcx+rcx*4]
0x180010148  movsxd  rcx, dword ptr [r8+rcx*4+10h]
0x18001014d  mov     rcx, [rcx+rax]
0x180010151  mov     [rsi], rcx
0x180010154  mov     rbx, [rsp+48h+arg_8]
0x180010159  mov     rax, rsi
0x18001015c  mov     rsi, [rsp+48h+arg_18]
0x180010161  mov     rbp, [rsp+48h+arg_10]
0x180010166  add     rsp, 20h
0x18001016a  pop     r15
0x18001016c  pop     r14
0x18001016e  pop     r13
0x180010170  pop     r12
0x180010172  pop     rdi
0x180010173  retn
```
