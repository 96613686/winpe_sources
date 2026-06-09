# ATL::CAtlModule::Term(void)

- ea: `0x140004c18`
- end: `0x140004cc1`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400024c0`
- `0x140002510`
- `0x140004aac`
- `0x140007790`

## callees

- `0x1400011b0`
- `0x140004c18`
- `0x14000539c`
- `0x140008010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140004c9d`
- `KERNEL32!DeleteCriticalSection` at `0x140004c9d`

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
        JUMPOUT(0x140004CC0LL);
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
0x140004c18  push    rbx
0x140004c1a  push    rsi
0x140004c1b  push    rdi
0x140004c1c  push    r14
0x140004c1e  push    r15
0x140004c20  sub     rsp, 20h
0x140004c24  mov     rdi, rcx
0x140004c27  lea     r14, [rcx+8]
0x140004c2b  cmp     dword ptr [r14], 0
0x140004c2f  jz      short loc_140004CAA
0x140004c31  cmp     qword ptr [rcx+10h], 0
0x140004c36  jz      short loc_140004C84
0x140004c38  mov     rax, rcx
0x140004c3b  neg     rax
0x140004c3e  sbb     rsi, rsi
0x140004c41  and     rsi, r14
0x140004c44  jz      short loc_140004CB6
0x140004c46  mov     r15, [rsi+8]
0x140004c4a  test    r15, r15
0x140004c4d  jz      short loc_140004C74
0x140004c4f  mov     rcx, [r15+8]
0x140004c53  mov     rax, [r15]
0x140004c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c5b  mov     rbx, [r15+10h]
0x140004c5f  mov     edx, 18h
0x140004c64  mov     rcx, r15; Block
0x140004c67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004c6c  mov     r15, rbx
0x140004c6f  test    rbx, rbx
0x140004c72  jnz     short loc_140004C4F
0x140004c74  mov     qword ptr [rsi+8], 0
0x140004c7c  mov     qword ptr [rdi+10h], 0
0x140004c84  mov     rcx, [rdi+40h]
0x140004c88  test    rcx, rcx
0x140004c8b  jz      short loc_140004C99
0x140004c8d  mov     rax, [rcx]
0x140004c90  mov     rax, [rax+10h]
0x140004c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c99  lea     rcx, [rdi+18h]; lpCriticalSection
0x140004c9d  call    cs:__imp_DeleteCriticalSection
0x140004ca3  mov     dword ptr [r14], 0
0x140004caa  add     rsp, 20h
0x140004cae  pop     r15
0x140004cb0  pop     r14
0x140004cb2  pop     rdi
0x140004cb3  pop     rsi
0x140004cb4  pop     rbx
0x140004cb5  retn
0x140004cb6  mov     ecx, 0C0000005h; unsigned int
0x140004cbb  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
