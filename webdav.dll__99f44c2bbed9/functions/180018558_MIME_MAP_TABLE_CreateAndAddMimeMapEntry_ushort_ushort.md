# MIME_MAP_TABLE::CreateAndAddMimeMapEntry(ushort *,ushort *)

- ea: `0x180018558`
- end: `0x180018636`
- name: `?CreateAndAddMimeMapEntry@MIME_MAP_TABLE@@AEAAJPEAG0@Z`
- size: `222`
- prototype: `__int64 __fastcall(MIME_MAP_TABLE *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180018778`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x180004808`
- `0x180018558`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18001860c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001860c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800185b3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800185b3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180018592`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180018592`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018616`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018616`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001859c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001859c`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x1800185c4`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x1800185c4`

## pseudocode

```c
__int64 __fastcall MIME_MAP_TABLE::CreateAndAddMimeMapEntry(
        MIME_MAP_TABLE *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rsi
  char *v6; // rax
  _DWORD *v7; // rdi

  v3 = a3 + 1;
  if ( *a3 != 46 )
    v3 = a3;
  v6 = (char *)operator new(0x90u);
  v7 = v6;
  if ( v6 )
  {
    STRU::STRU((STRU *)(v6 + 24));
    STRA::STRA((STRA *)(v7 + 20));
    v7[34] = 1;
    if ( (int)STRU::Copy((STRU *)(v7 + 6), v3) < 0 || (int)STRA::CopyWTruncate((STRA *)(v7 + 20), a2) < 0 )
      v7[34] = 0;
    *(_QWORD *)v7 = *((_QWORD *)v7 + 7);
    *((_WORD *)v7 + 8) = *((_WORD *)v7 + 36);
    *((_QWORD *)v7 + 1) = 0;
    if ( v7[34] )
    {
      STATIC_WSTRING_HASH::InsertRecord((MIME_MAP_TABLE *)((char *)this + 8), (struct STATIC_WSTRING_HASH_RECORD *)v7);
      return 0;
    }
    STRA::~STRA((STRA *)(v7 + 20));
    STRU::~STRU((STRU *)(v7 + 6));
    operator delete(v7);
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180018558  push    rbx
0x18001855a  push    rbp
0x18001855b  push    rsi
0x18001855c  push    rdi
0x18001855d  push    r14
0x18001855f  push    r15
0x180018561  sub     rsp, 28h
0x180018565  cmp     word ptr [r8], 2Eh ; '.'
0x18001856a  lea     rsi, [r8+2]
0x18001856e  mov     r14, rcx
0x180018571  mov     r15, rdx
0x180018574  mov     ecx, 90h; Size
0x180018579  cmovnz  rsi, r8
0x18001857d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018582  mov     rdi, rax
0x180018585  test    rax, rax
0x180018588  jz      loc_180018624
0x18001858e  lea     rcx, [rax+18h]
0x180018592  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180018598  lea     rcx, [rdi+50h]
0x18001859c  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800185a2  mov     rdx, rsi
0x1800185a5  mov     dword ptr [rdi+88h], 1
0x1800185af  lea     rcx, [rdi+18h]
0x1800185b3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800185b9  test    eax, eax
0x1800185bb  js      short loc_1800185CE
0x1800185bd  mov     rdx, r15
0x1800185c0  lea     rcx, [rdi+50h]
0x1800185c4  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x1800185ca  test    eax, eax
0x1800185cc  jns     short loc_1800185D8
0x1800185ce  mov     dword ptr [rdi+88h], 0
0x1800185d8  mov     rax, [rdi+38h]
0x1800185dc  mov     [rdi], rax
0x1800185df  movzx   eax, word ptr [rdi+48h]
0x1800185e3  mov     [rdi+10h], ax
0x1800185e7  mov     qword ptr [rdi+8], 0
0x1800185ef  cmp     dword ptr [rdi+88h], 0
0x1800185f6  jz      short loc_180018608
0x1800185f8  lea     rcx, [r14+8]; this
0x1800185fc  mov     rdx, rdi; struct STATIC_WSTRING_HASH_RECORD *
0x1800185ff  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x180018604  xor     eax, eax
0x180018606  jmp     short loc_180018629
0x180018608  lea     rcx, [rdi+50h]
0x18001860c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180018612  lea     rcx, [rdi+18h]
0x180018616  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001861c  mov     rcx, rdi; Block
0x18001861f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018624  mov     eax, 80070008h
0x180018629  add     rsp, 28h
0x18001862d  pop     r15
0x18001862f  pop     r14
0x180018631  pop     rdi
0x180018632  pop     rsi
0x180018633  pop     rbp
0x180018634  pop     rbx
0x180018635  retn
```
