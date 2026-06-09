# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180005110`
- end: `0x1800051b0`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `160`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800051c0`
- `0x1800597e0`

## callees

- `0x180005110`
- `0x180005364`
- `0x18005a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000515a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000515a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005191`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005191`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
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
        ATL::_AtlRaiseException((unsigned int)this, a2);
        JUMPOUT(0x1800051AFLL);
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
0x180005110  push    rbx
0x180005112  push    rsi
0x180005113  push    rdi
0x180005114  push    r14
0x180005116  push    r15
0x180005118  sub     rsp, 20h
0x18000511c  mov     rdi, rcx
0x18000511f  lea     r14, [rcx+8]
0x180005123  cmp     dword ptr [r14], 0
0x180005127  jz      short loc_18000519E
0x180005129  cmp     qword ptr [rcx+10h], 0
0x18000512e  jz      short loc_180005178
0x180005130  mov     rax, rcx
0x180005133  neg     rax
0x180005136  sbb     rsi, rsi
0x180005139  and     rsi, r14
0x18000513c  jz      short loc_1800051AA
0x18000513e  mov     r15, [rsi+8]
0x180005142  test    r15, r15
0x180005145  jz      short loc_180005168
0x180005147  mov     rcx, [r15+8]
0x18000514b  mov     rax, [r15]
0x18000514e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005153  mov     rbx, [r15+10h]
0x180005157  mov     rcx, r15
0x18000515a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005160  mov     r15, rbx
0x180005163  test    rbx, rbx
0x180005166  jnz     short loc_180005147
0x180005168  mov     qword ptr [rsi+8], 0
0x180005170  mov     qword ptr [rdi+10h], 0
0x180005178  mov     rcx, [rdi+40h]
0x18000517c  test    rcx, rcx
0x18000517f  jz      short loc_18000518D
0x180005181  mov     rax, [rcx]
0x180005184  mov     rax, [rax+10h]
0x180005188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180005191  call    cs:__imp_DeleteCriticalSection
0x180005197  mov     dword ptr [r14], 0
0x18000519e  add     rsp, 20h
0x1800051a2  pop     r15
0x1800051a4  pop     r14
0x1800051a6  pop     rdi
0x1800051a7  pop     rsi
0x1800051a8  pop     rbx
0x1800051a9  retn
0x1800051aa  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
