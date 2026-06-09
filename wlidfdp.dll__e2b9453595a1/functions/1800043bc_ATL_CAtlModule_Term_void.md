# ATL::CAtlModule::Term(void)

- ea: `0x1800043bc`
- end: `0x180004473`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800036ac`

## callees

- `0x180002814`
- `0x1800043bc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000445a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000445a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800043fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800043fc`

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
0x1800043bc  push    rbx
0x1800043be  push    rsi
0x1800043bf  push    rdi
0x1800043c0  push    r14
0x1800043c2  push    r15
0x1800043c4  sub     rsp, 20h
0x1800043c8  mov     rdi, rcx
0x1800043cb  lea     r14, [rcx+8]
0x1800043cf  cmp     dword ptr [r14], 0
0x1800043d3  jz      loc_180004467
0x1800043d9  cmp     qword ptr [rcx+10h], 0
0x1800043de  jz      short loc_180004441
0x1800043e0  mov     rax, rcx
0x1800043e3  neg     rax
0x1800043e6  sbb     rsi, rsi
0x1800043e9  and     rsi, r14
0x1800043ec  jnz     short loc_180004403
0x1800043ee  xor     r9d, r9d; lpArguments
0x1800043f1  xor     r8d, r8d; nNumberOfArguments
0x1800043f4  lea     edx, [rsi+1]; dwExceptionFlags
0x1800043f7  mov     ecx, 0C0000005h; dwExceptionCode
0x1800043fc  call    cs:__imp_RaiseException
0x180004402  int     3; Trap to Debugger
0x180004403  mov     r15, [rsi+8]
0x180004407  test    r15, r15
0x18000440a  jz      short loc_180004431
0x18000440c  mov     rcx, [r15+8]
0x180004410  mov     rax, [r15]
0x180004413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004418  mov     rbx, [r15+10h]
0x18000441c  mov     edx, 18h
0x180004421  mov     rcx, r15; Block
0x180004424  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004429  mov     r15, rbx
0x18000442c  test    rbx, rbx
0x18000442f  jnz     short loc_18000440C
0x180004431  mov     qword ptr [rsi+8], 0
0x180004439  mov     qword ptr [rdi+10h], 0
0x180004441  mov     rcx, [rdi+40h]
0x180004445  test    rcx, rcx
0x180004448  jz      short loc_180004456
0x18000444a  mov     rax, [rcx]
0x18000444d  mov     rax, [rax+10h]
0x180004451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004456  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000445a  call    cs:__imp_DeleteCriticalSection
0x180004460  mov     dword ptr [r14], 0
0x180004467  add     rsp, 20h
0x18000446b  pop     r15
0x18000446d  pop     r14
0x18000446f  pop     rdi
0x180004470  pop     rsi
0x180004471  pop     rbx
0x180004472  retn
```
