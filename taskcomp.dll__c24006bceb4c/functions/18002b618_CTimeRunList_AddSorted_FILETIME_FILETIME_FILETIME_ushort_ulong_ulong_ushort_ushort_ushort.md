# CTimeRunList::AddSorted(_FILETIME,_FILETIME,_FILETIME,ushort *,ulong,ulong,ushort,ushort *,ushort)

- ea: `0x18002b618`
- end: `0x18002b7e2`
- name: `?AddSorted@CTimeRunList@@QEAAJU_FILETIME@@00PEAGKKG1G@Z`
- size: `458`
- prototype: `__int64 __fastcall(CTimeRunList *this, FILETIME, struct _FILETIME, struct _FILETIME, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16, unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001f20`

## callees

- `0x180007488`
- `0x18002b618`
- `0x18002b7e8`
- `0x18002b81c`
- `0x18002b84c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b664`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b67c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b6b7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b664`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b67c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002b6b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTimeRunList::AddSorted(
        CTimeRunList *this,
        FILETIME a2,
        struct _FILETIME a3,
        struct _FILETIME a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int16 a8,
        unsigned __int16 *a9,
        unsigned __int16 a10)
{
  __int64 v10; // r14
  unsigned __int16 v14; // ax
  unsigned __int16 *v16; // r15
  CDLink *v17; // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  _QWORD *v19; // rax
  const unsigned __int16 *v20; // rdx
  _QWORD *v21; // rsi
  FILETIME v22; // rcx
  unsigned __int16 v23; // ax
  int v24; // ebx
  __int64 v25; // rax
  FILETIME FileTime1; // [rsp+60h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+68h] [rbp+48h] BYREF

  FileTime2 = a2;
  v10 = *((_QWORD *)this + 2);
  FileTime1 = 0;
  while ( 1 )
  {
    FileTime1 = *(FILETIME *)(v10 + 24);
    if ( !*(_QWORD *)&FileTime1 )
      break;
    if ( !CompareFileTime(&FileTime1, &FileTime2) && !*(_QWORD *)(v10 + 48) )
    {
      v14 = a8;
      if ( *(_WORD *)(v10 + 104) < a8 )
        v14 = *(_WORD *)(v10 + 104);
      *(_WORD *)(v10 + 104) = v14;
      CRun::AdvanceKillTime((CRun *)v10, a4);
      a5 = (unsigned __int16 *)a3;
      if ( CompareFileTime((const FILETIME *)&a5, (const FILETIME *)(v10 + 32)) > 0 )
        *(_QWORD *)(v10 + 32) = a5;
      return 0;
    }
    if ( CompareFileTime(&FileTime1, &FileTime2) < 0 )
      break;
    v10 = *(_QWORD *)(v10 + 16);
  }
  v16 = a9;
  if ( *a9 >= a10 )
  {
    v17 = (CDLink *)*((_QWORD *)this + 2);
    if ( v17 == (CDLink *)v10 )
      return 1;
    CDLink::UnLink(v17);
    if ( v18 )
      (**v18)(v18, 1);
    --*v16;
  }
  v19 = operator new(0x78u);
  v21 = v19;
  if ( !v19 )
    return 2147942414LL;
  v19[1] = 0;
  v19[2] = 0;
  *v19 = &CRun::`vftable';
  v22 = FileTime2;
  *((_DWORD *)v19 + 24) = a6;
  *((_DWORD *)v19 + 25) = a7;
  v23 = a8;
  v21[3] = v22;
  *((_WORD *)v21 + 52) = v23;
  v21[4] = a3;
  v21[5] = a4;
  v21[6] = 0;
  v21[7] = 0;
  *((_DWORD *)v21 + 16) = 0;
  v21[9] = 0;
  v21[10] = 0;
  v21[11] = 0;
  *(_QWORD *)((char *)v21 + 108) = 0;
  *((_DWORD *)v21 + 29) = 0;
  v24 = CRun::SetName((CRun *)v21, v20);
  if ( v24 >= 0 )
  {
    v25 = *(_QWORD *)(v10 + 8);
    v21[1] = v25;
    *(_QWORD *)(v25 + 16) = v21;
    *(_QWORD *)(v10 + 8) = v21;
    v21[2] = v10;
    ++*v16;
    return 0;
  }
  (*(void (__fastcall **)(_QWORD *, __int64))*v21)(v21, 1);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18002b618  mov     [rsp-38h+arg_10], rbx
0x18002b61d  mov     qword ptr [rsp-38h+FileTime2.dwLowDateTime], rdx
0x18002b622  push    rbp
0x18002b623  push    rsi
0x18002b624  push    rdi
0x18002b625  push    r12
0x18002b627  push    r13
0x18002b629  push    r14
0x18002b62b  push    r15
0x18002b62d  mov     rbp, rsp
0x18002b630  sub     rsp, 20h
0x18002b634  mov     r14, [rcx+10h]
0x18002b638  xor     r12d, r12d
0x18002b63b  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x18002b63f  mov     rbx, r9
0x18002b642  mov     rdi, r8
0x18002b645  mov     rsi, rcx
0x18002b648  mov     rax, [r14+18h]
0x18002b64c  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18002b650  test    eax, eax
0x18002b652  jnz     short loc_18002B65C
0x18002b654  shr     rax, 20h
0x18002b658  test    eax, eax
0x18002b65a  jz      short loc_18002B6D0
0x18002b65c  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002b660  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18002b664  call    cs:__imp_CompareFileTime
0x18002b66a  test    eax, eax
0x18002b66c  jnz     short loc_18002B674
0x18002b66e  cmp     [r14+30h], r12
0x18002b672  jz      short loc_18002B68C
0x18002b674  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002b678  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18002b67c  call    cs:__imp_CompareFileTime
0x18002b682  test    eax, eax
0x18002b684  js      short loc_18002B6D0
0x18002b686  mov     r14, [r14+10h]
0x18002b68a  jmp     short loc_18002B648
0x18002b68c  movzx   eax, [rbp+arg_38]
0x18002b690  mov     rdx, rbx; struct _FILETIME
0x18002b693  cmp     [r14+68h], ax
0x18002b698  mov     rcx, r14; this
0x18002b69b  cmovb   ax, [r14+68h]
0x18002b6a1  mov     [r14+68h], ax
0x18002b6a6  call    ?AdvanceKillTime@CRun@@QEAAXU_FILETIME@@@Z; CRun::AdvanceKillTime(_FILETIME)
0x18002b6ab  lea     rdx, [r14+20h]; lpFileTime2
0x18002b6af  mov     qword ptr [rbp+arg_20.dwLowDateTime], rdi
0x18002b6b3  lea     rcx, [rbp+arg_20]; lpFileTime1
0x18002b6b7  call    cs:__imp_CompareFileTime
0x18002b6bd  test    eax, eax
0x18002b6bf  jle     short loc_18002B6C9
0x18002b6c1  mov     rax, qword ptr [rbp+arg_20.dwLowDateTime]
0x18002b6c5  mov     [r14+20h], rax
0x18002b6c9  xor     eax, eax
0x18002b6cb  jmp     loc_18002B7CD
0x18002b6d0  mov     r15, [rbp+arg_40]
0x18002b6d7  mov     r13d, 1
0x18002b6dd  movzx   ecx, [rbp+arg_48]
0x18002b6e4  cmp     [r15], cx
0x18002b6e8  jb      short loc_18002B71C
0x18002b6ea  mov     rcx, [rsi+10h]; this
0x18002b6ee  cmp     rcx, r14
0x18002b6f1  jnz     short loc_18002B6FB
0x18002b6f3  mov     eax, r13d
0x18002b6f6  jmp     loc_18002B7CD
0x18002b6fb  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x18002b700  test    rcx, rcx
0x18002b703  jz      short loc_18002B713
0x18002b705  mov     rax, [rcx]
0x18002b708  mov     edx, r13d
0x18002b70b  mov     rax, [rax]
0x18002b70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b713  mov     eax, 0FFFFh
0x18002b718  add     [r15], ax
0x18002b71c  mov     ecx, 78h ; 'x'; Size
0x18002b721  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b726  mov     rsi, rax
0x18002b729  test    rax, rax
0x18002b72c  jz      loc_18002B7C8
0x18002b732  mov     [rax+8], r12
0x18002b736  mov     [rax+10h], r12
0x18002b73a  lea     rax, ??_7CRun@@6B@; const CRun::`vftable'
0x18002b741  mov     [rsi], rax
0x18002b744  mov     rcx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x18002b748  mov     eax, [rbp+arg_28]
0x18002b74b  mov     [rsi+60h], eax
0x18002b74e  mov     eax, [rbp+arg_30]
0x18002b751  mov     [rsi+64h], eax
0x18002b754  movzx   eax, [rbp+arg_38]
0x18002b758  mov     [rsi+18h], rcx
0x18002b75c  mov     rcx, rsi; this
0x18002b75f  mov     [rsi+68h], ax
0x18002b763  mov     [rsi+20h], rdi
0x18002b767  mov     [rsi+28h], rbx
0x18002b76b  mov     [rsi+30h], r12
0x18002b76f  mov     [rsi+38h], r12
0x18002b773  mov     [rsi+40h], r12d
0x18002b777  mov     [rsi+48h], r12
0x18002b77b  mov     [rsi+50h], r12
0x18002b77f  mov     [rsi+58h], r12
0x18002b783  mov     [rsi+6Ch], r12
0x18002b787  mov     [rsi+74h], r12d
0x18002b78b  call    ?SetName@CRun@@QEAAJPEBG@Z; CRun::SetName(ushort const *)
0x18002b790  mov     ebx, eax
0x18002b792  test    eax, eax
0x18002b794  jns     short loc_18002B7AB
0x18002b796  mov     rcx, [rsi]
0x18002b799  mov     edx, r13d
0x18002b79c  mov     rax, [rcx]
0x18002b79f  mov     rcx, rsi
0x18002b7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7a7  mov     eax, ebx
0x18002b7a9  jmp     short loc_18002B7CD
0x18002b7ab  mov     rax, [r14+8]
0x18002b7af  mov     [rsi+8], rax
0x18002b7b3  mov     [rax+10h], rsi
0x18002b7b7  mov     [r14+8], rsi
0x18002b7bb  mov     [rsi+10h], r14
0x18002b7bf  add     [r15], r13w
0x18002b7c3  jmp     loc_18002B6C9
0x18002b7c8  mov     eax, 8007000Eh
0x18002b7cd  mov     rbx, [rsp+20h+arg_10]
0x18002b7d2  add     rsp, 20h
0x18002b7d6  pop     r15
0x18002b7d8  pop     r14
0x18002b7da  pop     r13
0x18002b7dc  pop     r12
0x18002b7de  pop     rdi
0x18002b7df  pop     rsi
0x18002b7e0  pop     rbp
0x18002b7e1  retn
```
