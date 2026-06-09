# CRecheckQueue::Push(CDetectoid *,RECHECK_TYPE,_FILETIME const *)

- ea: `0x18002047c`
- end: `0x18002057a`
- name: `?Push@CRecheckQueue@@QEAAJPEAVCDetectoid@@W4RECHECK_TYPE@@PEBU_FILETIME@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64 *, __int64, int, const FILETIME *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a740`
- `0x180038500`
- `0x180038824`

## callees

- `0x180009f40`
- `0x18000b560`
- `0x18001ff74`
- `0x18002047c`
- `0x180029e74`
- `0x18002a6b4`
- `0x18003aacc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180020523`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180020523`

## pseudocode

```c
__int64 __fastcall CRecheckQueue::Push(__int64 *a1, __int64 a2, int a3, const FILETIME *a4)
{
  char *v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rcx
  int v12; // ebp
  _QWORD *v13; // rsi
  FILETIME FileTime2; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *HeadPosition; // [rsp+70h] [rbp+8h] BYREF

  if ( !*a1 )
    return 2147500037LL;
  if ( !a2 && a3 != 2 )
    return 2147942487LL;
  v9 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
    return (unsigned int)-2147024882;
  v10 = 0;
  *(FILETIME *)(v9 + 12) = *a4;
  *(_QWORD *)v9 = a2;
  *((_DWORD *)v9 + 2) = a3;
  v11 = *a1;
  if ( *(_DWORD *)(*a1 + 48) )
  {
    v12 = 0;
    HeadPosition = CList<unsigned short *,unsigned short *>::GetHeadPosition(v11);
    v13 = HeadPosition;
    if ( HeadPosition )
    {
      while ( !v12 )
      {
        FileTime2 = *(FILETIME *)(CList<CRecheckItem *,CRecheckItem *>::GetNext(*a1, &HeadPosition) + 12);
        if ( CompareFileTime(a4, &FileTime2) < 0 )
        {
          CList<CRecheckItem *,CRecheckItem *>::InsertBefore(*a1, v13, v9);
          v12 = 1;
        }
        v13 = HeadPosition;
        if ( !HeadPosition )
        {
          if ( v12 )
            return v10;
          goto LABEL_14;
        }
      }
      return v10;
    }
LABEL_14:
    v11 = *a1;
  }
  if ( !CList<CExternalBase *,CExternalBase *>::AddTail(v11, v9) )
  {
    operator delete(v9);
    return (unsigned int)-2147024882;
  }
  return v10;
}

```

## disassembly

```asm
0x18002047c  push    rbx
0x18002047e  push    rbp
0x18002047f  push    rsi
0x180020480  push    rdi
0x180020481  push    r14
0x180020483  push    r15
0x180020485  sub     rsp, 38h
0x180020489  cmp     qword ptr [rcx], 0
0x18002048d  mov     r15, r9
0x180020490  mov     esi, r8d
0x180020493  mov     rbp, rdx
0x180020496  mov     r14, rcx
0x180020499  jnz     short loc_1800204A5
0x18002049b  mov     eax, 80004005h
0x1800204a0  jmp     loc_18002056D
0x1800204a5  test    rbp, rbp
0x1800204a8  jnz     short loc_1800204B9
0x1800204aa  cmp     esi, 2
0x1800204ad  jz      short loc_1800204B9
0x1800204af  mov     eax, 80070057h
0x1800204b4  jmp     loc_18002056D
0x1800204b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800204c0  mov     ecx, 18h; unsigned __int64
0x1800204c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800204ca  mov     rbx, rax
0x1800204cd  test    rax, rax
0x1800204d0  jz      loc_180020566
0x1800204d6  mov     rax, [r15]
0x1800204d9  xor     edi, edi
0x1800204db  mov     [rbx+0Ch], rax
0x1800204df  mov     [rbx], rbp
0x1800204e2  mov     [rbx+8], esi
0x1800204e5  mov     rcx, [r14]
0x1800204e8  cmp     [rcx+30h], edi
0x1800204eb  jz      short loc_180020551
0x1800204ed  xor     ebp, ebp
0x1800204ef  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x1800204f4  mov     [rsp+68h+arg_0], rax
0x1800204f9  mov     rsi, rax
0x1800204fc  test    rax, rax
0x1800204ff  jz      short loc_18002054E
0x180020501  test    ebp, ebp
0x180020503  jnz     short loc_18002056B
0x180020505  mov     rcx, [r14]
0x180020508  lea     rdx, [rsp+68h+arg_0]
0x18002050d  call    ?GetNext@?$CList@PEAVCRecheckItem@@PEAV1@@@QEAAPEAVCRecheckItem@@AEAPEAU_CListElement@@@Z; CList<CRecheckItem *,CRecheckItem *>::GetNext(_CListElement * &)
0x180020512  lea     rdx, [rsp+68h+FileTime2]; lpFileTime2
0x180020517  mov     rcx, [rax+0Ch]
0x18002051b  mov     qword ptr [rsp+68h+FileTime2.dwLowDateTime], rcx
0x180020520  mov     rcx, r15; lpFileTime1
0x180020523  call    cs:__imp_CompareFileTime
0x180020529  test    eax, eax
0x18002052b  jns     short loc_180020540
0x18002052d  mov     rcx, [r14]
0x180020530  mov     r8, rbx
0x180020533  mov     rdx, rsi
0x180020536  call    ?InsertBefore@?$CList@PEAVCRecheckItem@@PEAV1@@@QEAAPEAU_CListElement@@PEAU2@PEAVCRecheckItem@@@Z; CList<CRecheckItem *,CRecheckItem *>::InsertBefore(_CListElement *,CRecheckItem *)
0x18002053b  mov     ebp, 1
0x180020540  mov     rsi, [rsp+68h+arg_0]
0x180020545  test    rsi, rsi
0x180020548  jnz     short loc_180020501
0x18002054a  test    ebp, ebp
0x18002054c  jnz     short loc_18002056B
0x18002054e  mov     rcx, [r14]
0x180020551  mov     rdx, rbx
0x180020554  call    ?AddTail@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAPEAU_CListElement@@PEAVCExternalBase@@@Z; CList<CExternalBase *,CExternalBase *>::AddTail(CExternalBase *)
0x180020559  test    rax, rax
0x18002055c  jnz     short loc_18002056B
0x18002055e  mov     rcx, rbx; Block
0x180020561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020566  mov     edi, 8007000Eh
0x18002056b  mov     eax, edi
0x18002056d  add     rsp, 38h
0x180020571  pop     r15
0x180020573  pop     r14
0x180020575  pop     rdi
0x180020576  pop     rsi
0x180020577  pop     rbp
0x180020578  pop     rbx
0x180020579  retn
```
