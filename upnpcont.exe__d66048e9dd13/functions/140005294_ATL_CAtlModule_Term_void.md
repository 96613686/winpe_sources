# ATL::CAtlModule::Term(void)

- ea: `0x140005294`
- end: `0x14000533d`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140002110`
- `0x1400021a0`
- `0x140005c80`
- `0x140006780`

## callees

- `0x140001110`
- `0x140005294`
- `0x140005b9c`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005319`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005319`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v1; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v1 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v1 & -(__int64)(this != 0);
      if ( !v3 )
      {
        ATL::_AtlRaiseException(0xC0000005);
        JUMPOUT(0x14000533CLL);
      }
      v4 = *(_QWORD **)((v1 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x140005294  push    rbx
0x140005296  push    rsi
0x140005297  push    rdi
0x140005298  push    r14
0x14000529a  push    r15
0x14000529c  sub     rsp, 20h
0x1400052a0  lea     r14, [rcx+8]
0x1400052a4  mov     rdi, rcx
0x1400052a7  cmp     dword ptr [r14], 0
0x1400052ab  jz      short loc_140005326
0x1400052ad  cmp     qword ptr [rcx+10h], 0
0x1400052b2  jz      short loc_140005300
0x1400052b4  mov     rax, rcx
0x1400052b7  neg     rax
0x1400052ba  sbb     rsi, rsi
0x1400052bd  and     rsi, r14
0x1400052c0  jz      short loc_140005332
0x1400052c2  mov     r15, [rsi+8]
0x1400052c6  test    r15, r15
0x1400052c9  jz      short loc_1400052F0
0x1400052cb  mov     rcx, [r15+8]
0x1400052cf  mov     rax, [r15]
0x1400052d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052d7  mov     rbx, [r15+10h]
0x1400052db  mov     edx, 18h
0x1400052e0  mov     rcx, r15; Block
0x1400052e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400052e8  mov     r15, rbx
0x1400052eb  test    rbx, rbx
0x1400052ee  jnz     short loc_1400052CB
0x1400052f0  mov     qword ptr [rsi+8], 0
0x1400052f8  mov     qword ptr [rdi+10h], 0
0x140005300  mov     rcx, [rdi+40h]
0x140005304  test    rcx, rcx
0x140005307  jz      short loc_140005315
0x140005309  mov     rax, [rcx]
0x14000530c  mov     rax, [rax+10h]
0x140005310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005315  lea     rcx, [rdi+18h]; lpCriticalSection
0x140005319  call    cs:__imp_DeleteCriticalSection
0x14000531f  mov     dword ptr [r14], 0
0x140005326  add     rsp, 20h
0x14000532a  pop     r15
0x14000532c  pop     r14
0x14000532e  pop     rdi
0x14000532f  pop     rsi
0x140005330  pop     rbx
0x140005331  retn
0x140005332  mov     ecx, 0C0000005h; unsigned int
0x140005337  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
