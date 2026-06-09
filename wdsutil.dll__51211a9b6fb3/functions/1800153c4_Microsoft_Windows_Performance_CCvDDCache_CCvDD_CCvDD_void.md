# Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)

- ea: `0x1800153c4`
- end: `0x1800154a1`
- name: `??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `221`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800151a8`
- `0x180015e34`
- `0x180016248`
- `0x18003284a`
- `0x1800328a1`

## callees

- `0x1800153c4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800153fe`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015416`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001542e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800153fe`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015416`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001542e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001544d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015479`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001544d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015479`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(
        Microsoft::Windows::Performance::CCvDDCache::CCvDD *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 14) = 0;
  }
  operator delete[](*((void **)this + 11));
  *((_QWORD *)this + 11) = 0;
  operator delete[](*((void **)this + 10));
  *((_QWORD *)this + 10) = 0;
  operator delete[](*((void **)this + 9));
  *((_QWORD *)this + 9) = 0;
  if ( *((_QWORD *)this + 7) >= 8u )
    operator delete(*((void **)this + 4));
  *((_QWORD *)this + 7) = 7;
  *((_QWORD *)this + 6) = 0;
  *((_WORD *)this + 16) = 0;
  if ( *((_QWORD *)this + 3) >= 8u )
    operator delete(*(void **)this);
  *((_QWORD *)this + 3) = 7;
  *((_QWORD *)this + 2) = 0;
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x1800153c4  push    rbx
0x1800153c6  sub     rsp, 20h
0x1800153ca  mov     rbx, rcx
0x1800153cd  mov     rcx, [rcx+60h]
0x1800153d1  test    rcx, rcx
0x1800153d4  jz      short loc_1800153FA
0x1800153d6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800153dd  nop     dword ptr [rax+rax+00h]
0x1800153e2  mov     qword ptr [rbx+60h], 0
0x1800153ea  mov     qword ptr [rbx+68h], 0
0x1800153f2  mov     qword ptr [rbx+70h], 0
0x1800153fa  mov     rcx, [rbx+58h]
0x1800153fe  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015405  nop     dword ptr [rax+rax+00h]
0x18001540a  mov     qword ptr [rbx+58h], 0
0x180015412  mov     rcx, [rbx+50h]
0x180015416  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001541d  nop     dword ptr [rax+rax+00h]
0x180015422  mov     qword ptr [rbx+50h], 0
0x18001542a  mov     rcx, [rbx+48h]
0x18001542e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015435  nop     dword ptr [rax+rax+00h]
0x18001543a  mov     qword ptr [rbx+48h], 0
0x180015442  cmp     qword ptr [rbx+38h], 8
0x180015447  jb      short loc_180015459
0x180015449  mov     rcx, [rbx+20h]
0x18001544d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015454  nop     dword ptr [rax+rax+00h]
0x180015459  xor     eax, eax
0x18001545b  mov     qword ptr [rbx+38h], 7
0x180015463  mov     qword ptr [rbx+30h], 0
0x18001546b  mov     [rbx+20h], ax
0x18001546f  cmp     qword ptr [rbx+18h], 8
0x180015474  jb      short loc_180015485
0x180015476  mov     rcx, [rbx]
0x180015479  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015480  nop     dword ptr [rax+rax+00h]
0x180015485  xor     eax, eax
0x180015487  mov     qword ptr [rbx+18h], 7
0x18001548f  mov     qword ptr [rbx+10h], 0
0x180015497  mov     [rbx], ax
0x18001549a  add     rsp, 20h
0x18001549e  pop     rbx
0x18001549f  retn
```
