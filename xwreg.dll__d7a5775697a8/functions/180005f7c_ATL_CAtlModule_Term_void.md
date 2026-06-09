# ATL::CAtlModule::Term(void)

- ea: `0x180005f7c`
- end: `0x18000602f`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002fc0`
- `0x180006038`
- `0x180012ee0`

## callees

- `0x180005f7c`
- `0x180013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005fdf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005fdf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006016`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006016`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005fbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005fbc`

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
0x180005f7c  push    rbx
0x180005f7e  push    rsi
0x180005f7f  push    rdi
0x180005f80  push    r14
0x180005f82  push    r15
0x180005f84  sub     rsp, 20h
0x180005f88  mov     rdi, rcx
0x180005f8b  lea     r14, [rcx+8]
0x180005f8f  cmp     dword ptr [r14], 0
0x180005f93  jz      loc_180006023
0x180005f99  cmp     qword ptr [rcx+10h], 0
0x180005f9e  jz      short loc_180005FFD
0x180005fa0  mov     rax, rcx
0x180005fa3  neg     rax
0x180005fa6  sbb     rsi, rsi
0x180005fa9  and     rsi, r14
0x180005fac  jnz     short loc_180005FC3
0x180005fae  xor     r9d, r9d; lpArguments
0x180005fb1  xor     r8d, r8d; nNumberOfArguments
0x180005fb4  lea     edx, [rsi+1]; dwExceptionFlags
0x180005fb7  mov     ecx, 0C0000005h; dwExceptionCode
0x180005fbc  call    cs:__imp_RaiseException
0x180005fc2  int     3; Trap to Debugger
0x180005fc3  mov     r15, [rsi+8]
0x180005fc7  test    r15, r15
0x180005fca  jz      short loc_180005FED
0x180005fcc  mov     rcx, [r15+8]
0x180005fd0  mov     rax, [r15]
0x180005fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd8  mov     rbx, [r15+10h]
0x180005fdc  mov     rcx, r15
0x180005fdf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005fe5  mov     r15, rbx
0x180005fe8  test    rbx, rbx
0x180005feb  jnz     short loc_180005FCC
0x180005fed  mov     qword ptr [rsi+8], 0
0x180005ff5  mov     qword ptr [rdi+10h], 0
0x180005ffd  mov     rcx, [rdi+40h]
0x180006001  test    rcx, rcx
0x180006004  jz      short loc_180006012
0x180006006  mov     rax, [rcx]
0x180006009  mov     rax, [rax+10h]
0x18000600d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006012  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006016  call    cs:__imp_DeleteCriticalSection
0x18000601c  mov     dword ptr [r14], 0
0x180006023  add     rsp, 20h
0x180006027  pop     r15
0x180006029  pop     r14
0x18000602b  pop     rdi
0x18000602c  pop     rsi
0x18000602d  pop     rbx
0x18000602e  retn
```
