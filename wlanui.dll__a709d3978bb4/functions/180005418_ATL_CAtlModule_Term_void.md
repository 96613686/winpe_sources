# ATL::CAtlModule::Term(void)

- ea: `0x180005418`
- end: `0x1800054bd`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002d50`
- `0x180005ca0`
- `0x18001c520`

## callees

- `0x180005418`
- `0x180005b7c`
- `0x18001d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005462`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005462`
- `KERNEL32!DeleteCriticalSection` at `0x180005499`
- `KERNEL32!DeleteCriticalSection` at `0x180005499`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v2 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x1800054BCLL);
      }
      v5 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180005418  push    rbx
0x18000541a  push    rsi
0x18000541b  push    rdi
0x18000541c  push    r14
0x18000541e  push    r15
0x180005420  sub     rsp, 20h
0x180005424  lea     r14, [rcx+8]
0x180005428  mov     rdi, rcx
0x18000542b  cmp     dword ptr [r14], 0
0x18000542f  jz      short loc_1800054A6
0x180005431  cmp     qword ptr [rcx+10h], 0
0x180005436  jz      short loc_180005480
0x180005438  mov     rax, rcx
0x18000543b  neg     rax
0x18000543e  sbb     rsi, rsi
0x180005441  and     rsi, r14
0x180005444  jz      short loc_1800054B2
0x180005446  mov     r15, [rsi+8]
0x18000544a  test    r15, r15
0x18000544d  jz      short loc_180005470
0x18000544f  mov     rcx, [r15+8]
0x180005453  mov     rax, [r15]
0x180005456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000545b  mov     rbx, [r15+10h]
0x18000545f  mov     rcx, r15
0x180005462  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005468  mov     r15, rbx
0x18000546b  test    rbx, rbx
0x18000546e  jnz     short loc_18000544F
0x180005470  mov     qword ptr [rsi+8], 0
0x180005478  mov     qword ptr [rdi+10h], 0
0x180005480  mov     rcx, [rdi+40h]
0x180005484  test    rcx, rcx
0x180005487  jz      short loc_180005495
0x180005489  mov     rax, [rcx]
0x18000548c  mov     rax, [rax+10h]
0x180005490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005495  lea     rcx, [rdi+18h]; lpCriticalSection
0x180005499  call    cs:__imp_DeleteCriticalSection
0x18000549f  mov     dword ptr [r14], 0
0x1800054a6  add     rsp, 20h
0x1800054aa  pop     r15
0x1800054ac  pop     r14
0x1800054ae  pop     rdi
0x1800054af  pop     rsi
0x1800054b0  pop     rbx
0x1800054b1  retn
0x1800054b2  mov     ecx, 0C0000005h; unsigned int
0x1800054b7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
