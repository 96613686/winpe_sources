# ATL::CAtlModule::Term(void)

- ea: `0x18000cac0`
- end: `0x18000cb77`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008130`
- `0x180008220`
- `0x18000cb80`

## callees

- `0x180001674`
- `0x18000cac0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cb00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cb00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb5e`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x18000cac0  push    rbx
0x18000cac2  push    rsi
0x18000cac3  push    rdi
0x18000cac4  push    r14
0x18000cac6  push    r15
0x18000cac8  sub     rsp, 20h
0x18000cacc  mov     rdi, rcx
0x18000cacf  lea     r14, [rcx+8]
0x18000cad3  cmp     dword ptr [r14], 0
0x18000cad7  jz      loc_18000CB6B
0x18000cadd  cmp     qword ptr [rcx+10h], 0
0x18000cae2  jz      short loc_18000CB45
0x18000cae4  mov     rax, rcx
0x18000cae7  neg     rax
0x18000caea  sbb     rsi, rsi
0x18000caed  and     rsi, r14
0x18000caf0  jnz     short loc_18000CB07
0x18000caf2  xor     r9d, r9d; lpArguments
0x18000caf5  xor     r8d, r8d; nNumberOfArguments
0x18000caf8  lea     edx, [rsi+1]; dwExceptionFlags
0x18000cafb  mov     ecx, 0C0000005h; dwExceptionCode
0x18000cb00  call    cs:__imp_RaiseException
0x18000cb06  int     3; Trap to Debugger
0x18000cb07  mov     r15, [rsi+8]
0x18000cb0b  test    r15, r15
0x18000cb0e  jz      short loc_18000CB35
0x18000cb10  mov     rcx, [r15+8]
0x18000cb14  mov     rax, [r15]
0x18000cb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb1c  mov     rbx, [r15+10h]
0x18000cb20  mov     edx, 18h
0x18000cb25  mov     rcx, r15; Block
0x18000cb28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cb2d  mov     r15, rbx
0x18000cb30  test    rbx, rbx
0x18000cb33  jnz     short loc_18000CB10
0x18000cb35  mov     qword ptr [rsi+8], 0
0x18000cb3d  mov     qword ptr [rdi+10h], 0
0x18000cb45  mov     rcx, [rdi+40h]
0x18000cb49  test    rcx, rcx
0x18000cb4c  jz      short loc_18000CB5A
0x18000cb4e  mov     rax, [rcx]
0x18000cb51  mov     rax, [rax+10h]
0x18000cb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5a  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000cb5e  call    cs:__imp_DeleteCriticalSection
0x18000cb64  mov     dword ptr [r14], 0
0x18000cb6b  add     rsp, 20h
0x18000cb6f  pop     r15
0x18000cb71  pop     r14
0x18000cb73  pop     rdi
0x18000cb74  pop     rsi
0x18000cb75  pop     rbx
0x18000cb76  retn
```
