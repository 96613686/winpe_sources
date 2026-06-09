# ATL::CAtlModule::Term(void)

- ea: `0x14000852c`
- end: `0x1400085d0`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400125d0`
- `0x140015710`

## callees

- `0x140001b90`
- `0x14000852c`
- `0x1400087e8`
- `0x140016010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400085b1`
- `KERNEL32!DeleteCriticalSection` at `0x1400085b1`

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
        ATL::_AtlRaiseException((unsigned int)this, a2);
        JUMPOUT(0x1400085CFLL);
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
0x14000852c  push    rbx
0x14000852e  push    rsi
0x14000852f  push    rdi
0x140008530  push    r14
0x140008532  push    r15
0x140008534  sub     rsp, 20h
0x140008538  lea     r14, [rcx+8]
0x14000853c  mov     rdi, rcx
0x14000853f  cmp     dword ptr [r14], 0
0x140008543  jz      short loc_1400085BE
0x140008545  cmp     qword ptr [rcx+10h], 0
0x14000854a  jz      short loc_140008598
0x14000854c  mov     rax, rcx
0x14000854f  neg     rax
0x140008552  sbb     rsi, rsi
0x140008555  and     rsi, r14
0x140008558  jz      short loc_1400085CA
0x14000855a  mov     r15, [rsi+8]
0x14000855e  test    r15, r15
0x140008561  jz      short loc_140008588
0x140008563  mov     rcx, [r15+8]
0x140008567  mov     rax, [r15]
0x14000856a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000856f  mov     rbx, [r15+10h]
0x140008573  mov     edx, 18h
0x140008578  mov     rcx, r15; Block
0x14000857b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008580  mov     r15, rbx
0x140008583  test    rbx, rbx
0x140008586  jnz     short loc_140008563
0x140008588  mov     qword ptr [rsi+8], 0
0x140008590  mov     qword ptr [rdi+10h], 0
0x140008598  mov     rcx, [rdi+40h]
0x14000859c  test    rcx, rcx
0x14000859f  jz      short loc_1400085AD
0x1400085a1  mov     rax, [rcx]
0x1400085a4  mov     rax, [rax+10h]
0x1400085a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085ad  lea     rcx, [rdi+18h]; lpCriticalSection
0x1400085b1  call    cs:__imp_DeleteCriticalSection
0x1400085b7  mov     dword ptr [r14], 0
0x1400085be  add     rsp, 20h
0x1400085c2  pop     r15
0x1400085c4  pop     r14
0x1400085c6  pop     rdi
0x1400085c7  pop     rsi
0x1400085c8  pop     rbx
0x1400085c9  retn
0x1400085ca  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
