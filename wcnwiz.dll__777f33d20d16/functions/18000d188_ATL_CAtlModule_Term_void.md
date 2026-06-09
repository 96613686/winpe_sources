# ATL::CAtlModule::Term(void)

- ea: `0x18000d188`
- end: `0x18000d23f`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003010`

## callees

- `0x180001844`
- `0x18000d188`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d1c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d1c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d226`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d226`

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
0x18000d188  push    rbx
0x18000d18a  push    rsi
0x18000d18b  push    rdi
0x18000d18c  push    r14
0x18000d18e  push    r15
0x18000d190  sub     rsp, 20h
0x18000d194  mov     rdi, rcx
0x18000d197  lea     r14, [rcx+8]
0x18000d19b  cmp     dword ptr [r14], 0
0x18000d19f  jz      loc_18000D233
0x18000d1a5  cmp     qword ptr [rcx+10h], 0
0x18000d1aa  jz      short loc_18000D20D
0x18000d1ac  mov     rax, rcx
0x18000d1af  neg     rax
0x18000d1b2  sbb     rsi, rsi
0x18000d1b5  and     rsi, r14
0x18000d1b8  jnz     short loc_18000D1CF
0x18000d1ba  xor     r9d, r9d; lpArguments
0x18000d1bd  xor     r8d, r8d; nNumberOfArguments
0x18000d1c0  lea     edx, [rsi+1]; dwExceptionFlags
0x18000d1c3  mov     ecx, 0C0000005h; dwExceptionCode
0x18000d1c8  call    cs:__imp_RaiseException
0x18000d1ce  int     3; Trap to Debugger
0x18000d1cf  mov     r15, [rsi+8]
0x18000d1d3  test    r15, r15
0x18000d1d6  jz      short loc_18000D1FD
0x18000d1d8  mov     rcx, [r15+8]
0x18000d1dc  mov     rax, [r15]
0x18000d1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1e4  mov     rbx, [r15+10h]
0x18000d1e8  mov     edx, 18h
0x18000d1ed  mov     rcx, r15; Block
0x18000d1f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d1f5  mov     r15, rbx
0x18000d1f8  test    rbx, rbx
0x18000d1fb  jnz     short loc_18000D1D8
0x18000d1fd  mov     qword ptr [rsi+8], 0
0x18000d205  mov     qword ptr [rdi+10h], 0
0x18000d20d  mov     rcx, [rdi+40h]
0x18000d211  test    rcx, rcx
0x18000d214  jz      short loc_18000D222
0x18000d216  mov     rax, [rcx]
0x18000d219  mov     rax, [rax+10h]
0x18000d21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d222  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000d226  call    cs:__imp_DeleteCriticalSection
0x18000d22c  mov     dword ptr [r14], 0
0x18000d233  add     rsp, 20h
0x18000d237  pop     r15
0x18000d239  pop     r14
0x18000d23b  pop     rdi
0x18000d23c  pop     rsi
0x18000d23d  pop     rbx
0x18000d23e  retn
```
