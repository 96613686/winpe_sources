# ATL::CAtlModule::Term(void)

- ea: `0x180013170`
- end: `0x180013219`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180010000`
- `0x1800139a0`
- `0x180016190`

## callees

- `0x18000213c`
- `0x180013170`
- `0x1800137dc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800131f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800131f5`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v3; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v3 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180013218LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x180013170  push    rbx
0x180013172  push    rsi
0x180013173  push    rdi
0x180013174  push    r14
0x180013176  push    r15
0x180013178  sub     rsp, 20h
0x18001317c  mov     rdi, rcx
0x18001317f  lea     r14, [rcx+8]
0x180013183  cmp     dword ptr [r14], 0
0x180013187  jz      short loc_180013202
0x180013189  cmp     qword ptr [rcx+10h], 0
0x18001318e  jz      short loc_1800131DC
0x180013190  mov     rax, rcx
0x180013193  neg     rax
0x180013196  sbb     rsi, rsi
0x180013199  and     rsi, r14
0x18001319c  jz      short loc_18001320E
0x18001319e  mov     r15, [rsi+8]
0x1800131a2  test    r15, r15
0x1800131a5  jz      short loc_1800131CC
0x1800131a7  mov     rcx, [r15+8]
0x1800131ab  mov     rax, [r15]
0x1800131ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131b3  mov     rbx, [r15+10h]
0x1800131b7  mov     edx, 18h
0x1800131bc  mov     rcx, r15; Block
0x1800131bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800131c4  mov     r15, rbx
0x1800131c7  test    rbx, rbx
0x1800131ca  jnz     short loc_1800131A7
0x1800131cc  mov     qword ptr [rsi+8], 0
0x1800131d4  mov     qword ptr [rdi+10h], 0
0x1800131dc  mov     rcx, [rdi+40h]
0x1800131e0  test    rcx, rcx
0x1800131e3  jz      short loc_1800131F1
0x1800131e5  mov     rax, [rcx]
0x1800131e8  mov     rax, [rax+10h]
0x1800131ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131f1  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800131f5  call    cs:__imp_DeleteCriticalSection
0x1800131fb  mov     dword ptr [r14], 0
0x180013202  add     rsp, 20h
0x180013206  pop     r15
0x180013208  pop     r14
0x18001320a  pop     rdi
0x18001320b  pop     rsi
0x18001320c  pop     rbx
0x18001320d  retn
0x18001320e  mov     ecx, 0C0000005h; unsigned int
0x180013213  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
