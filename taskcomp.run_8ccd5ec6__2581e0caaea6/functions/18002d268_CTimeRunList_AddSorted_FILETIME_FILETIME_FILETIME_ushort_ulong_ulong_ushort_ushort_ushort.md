# CTimeRunList::AddSorted(_FILETIME,_FILETIME,_FILETIME,ushort *,ulong,ulong,ushort,ushort *,ushort)

- ea: `0x18002d268`
- end: `0x18002d449`
- name: `?AddSorted@CTimeRunList@@QEAAJU_FILETIME@@00PEAGKKG1G@Z`
- size: `481`
- prototype: `int(CTimeRunList *__hidden this, struct _FILETIME, struct _FILETIME, struct _FILETIME, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16, unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001fc0`

## callees

- `0x180007948`
- `0x18002d268`
- `0x18002d450`
- `0x18002d520`
- `0x18002d550`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d2b8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d2d6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d317`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d2b8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d2d6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d317`

## pseudocode

```c
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
0x18002d268  mov     [rsp-38h+arg_10], rbx
0x18002d26d  mov     qword ptr [rsp-38h+FileTime2.dwLowDateTime], rdx
0x18002d272  push    rbp
0x18002d273  push    rsi
0x18002d274  push    rdi
0x18002d275  push    r12
0x18002d277  push    r13
0x18002d279  push    r14
0x18002d27b  push    r15
0x18002d27d  mov     rbp, rsp
0x18002d280  sub     rsp, 20h
0x18002d284  mov     r14, [rcx+10h]
0x18002d288  xor     r12d, r12d
0x18002d28b  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x18002d28f  mov     rbx, r9
0x18002d292  mov     rdi, r8
0x18002d295  mov     rsi, rcx
0x18002d298  mov     rax, [r14+18h]
0x18002d29c  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18002d2a0  test    eax, eax
0x18002d2a2  jnz     short loc_18002D2B0
0x18002d2a4  shr     rax, 20h
0x18002d2a8  test    eax, eax
0x18002d2aa  jz      loc_18002D336
0x18002d2b0  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002d2b4  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18002d2b8  call    cs:__imp_CompareFileTime
0x18002d2bf  nop     dword ptr [rax+rax+00h]
0x18002d2c4  test    eax, eax
0x18002d2c6  jnz     short loc_18002D2CE
0x18002d2c8  cmp     [r14+30h], r12
0x18002d2cc  jz      short loc_18002D2EC
0x18002d2ce  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002d2d2  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18002d2d6  call    cs:__imp_CompareFileTime
0x18002d2dd  nop     dword ptr [rax+rax+00h]
0x18002d2e2  test    eax, eax
0x18002d2e4  js      short loc_18002D336
0x18002d2e6  mov     r14, [r14+10h]
0x18002d2ea  jmp     short loc_18002D298
0x18002d2ec  movzx   eax, [rbp+arg_38]
0x18002d2f0  mov     rdx, rbx; struct _FILETIME
0x18002d2f3  cmp     [r14+68h], ax
0x18002d2f8  mov     rcx, r14; this
0x18002d2fb  cmovb   ax, [r14+68h]
0x18002d301  mov     [r14+68h], ax
0x18002d306  call    ?AdvanceKillTime@CRun@@QEAAXU_FILETIME@@@Z; CRun::AdvanceKillTime(_FILETIME)
0x18002d30b  lea     rdx, [r14+20h]; lpFileTime2
0x18002d30f  mov     qword ptr [rbp+arg_20.dwLowDateTime], rdi
0x18002d313  lea     rcx, [rbp+arg_20]; lpFileTime1
0x18002d317  call    cs:__imp_CompareFileTime
0x18002d31e  nop     dword ptr [rax+rax+00h]
0x18002d323  test    eax, eax
0x18002d325  jle     short loc_18002D32F
0x18002d327  mov     rax, qword ptr [rbp+arg_20.dwLowDateTime]
0x18002d32b  mov     [r14+20h], rax
0x18002d32f  xor     eax, eax
0x18002d331  jmp     loc_18002D433
0x18002d336  mov     r15, [rbp+arg_40]
0x18002d33d  mov     r13d, 1
0x18002d343  movzx   ecx, [rbp+arg_48]
0x18002d34a  cmp     [r15], cx
0x18002d34e  jb      short loc_18002D382
0x18002d350  mov     rcx, [rsi+10h]; this
0x18002d354  cmp     rcx, r14
0x18002d357  jnz     short loc_18002D361
0x18002d359  mov     eax, r13d
0x18002d35c  jmp     loc_18002D433
0x18002d361  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x18002d366  test    rcx, rcx
0x18002d369  jz      short loc_18002D379
0x18002d36b  mov     rax, [rcx]
0x18002d36e  mov     edx, r13d
0x18002d371  mov     rax, [rax]
0x18002d374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d379  mov     eax, 0FFFFh
0x18002d37e  add     [r15], ax
0x18002d382  mov     ecx, 78h ; 'x'; Size
0x18002d387  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d38c  mov     rsi, rax
0x18002d38f  test    rax, rax
0x18002d392  jz      loc_18002D42E
0x18002d398  mov     [rax+8], r12
0x18002d39c  mov     [rax+10h], r12
0x18002d3a0  lea     rax, ??_7CRun@@6B@; const CRun::`vftable'
0x18002d3a7  mov     [rsi], rax
0x18002d3aa  mov     rcx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x18002d3ae  mov     eax, [rbp+arg_28]
0x18002d3b1  mov     [rsi+60h], eax
0x18002d3b4  mov     eax, [rbp+arg_30]
0x18002d3b7  mov     [rsi+64h], eax
0x18002d3ba  movzx   eax, [rbp+arg_38]
0x18002d3be  mov     [rsi+18h], rcx
0x18002d3c2  mov     rcx, rsi; this
0x18002d3c5  mov     [rsi+68h], ax
0x18002d3c9  mov     [rsi+20h], rdi
0x18002d3cd  mov     [rsi+28h], rbx
0x18002d3d1  mov     [rsi+30h], r12
0x18002d3d5  mov     [rsi+38h], r12
0x18002d3d9  mov     [rsi+40h], r12d
0x18002d3dd  mov     [rsi+48h], r12
0x18002d3e1  mov     [rsi+50h], r12
0x18002d3e5  mov     [rsi+58h], r12
0x18002d3e9  mov     [rsi+6Ch], r12
0x18002d3ed  mov     [rsi+74h], r12d
0x18002d3f1  call    ?SetName@CRun@@QEAAJPEBG@Z; CRun::SetName(ushort const *)
0x18002d3f6  mov     ebx, eax
0x18002d3f8  test    eax, eax
0x18002d3fa  jns     short loc_18002D411
0x18002d3fc  mov     rcx, [rsi]
0x18002d3ff  mov     edx, r13d
0x18002d402  mov     rax, [rcx]
0x18002d405  mov     rcx, rsi
0x18002d408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d40d  mov     eax, ebx
0x18002d40f  jmp     short loc_18002D433
0x18002d411  mov     rax, [r14+8]
0x18002d415  mov     [rsi+8], rax
0x18002d419  mov     [rax+10h], rsi
0x18002d41d  mov     [r14+8], rsi
0x18002d421  mov     [rsi+10h], r14
0x18002d425  add     [r15], r13w
0x18002d429  jmp     loc_18002D32F
0x18002d42e  mov     eax, 8007000Eh
0x18002d433  mov     rbx, [rsp+20h+arg_10]
0x18002d438  add     rsp, 20h
0x18002d43c  pop     r15
0x18002d43e  pop     r14
0x18002d440  pop     r13
0x18002d442  pop     r12
0x18002d444  pop     rdi
0x18002d445  pop     rsi
0x18002d446  pop     rbp
0x18002d447  retn
```
