# ATL::CAtlModule::Term(void)

- ea: `0x180036f84`
- end: `0x18003703b`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180036de4`

## callees

- `0x18000324c`
- `0x180036f84`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037022`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037022`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036fc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036fc4`

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
0x180036f84  push    rbx
0x180036f86  push    rsi
0x180036f87  push    rdi
0x180036f88  push    r14
0x180036f8a  push    r15
0x180036f8c  sub     rsp, 20h
0x180036f90  mov     rdi, rcx
0x180036f93  lea     r14, [rcx+8]
0x180036f97  cmp     dword ptr [r14], 0
0x180036f9b  jz      loc_18003702F
0x180036fa1  cmp     qword ptr [rcx+10h], 0
0x180036fa6  jz      short loc_180037009
0x180036fa8  mov     rax, rcx
0x180036fab  neg     rax
0x180036fae  sbb     rsi, rsi
0x180036fb1  and     rsi, r14
0x180036fb4  jnz     short loc_180036FCB
0x180036fb6  xor     r9d, r9d; lpArguments
0x180036fb9  xor     r8d, r8d; nNumberOfArguments
0x180036fbc  lea     edx, [rsi+1]; dwExceptionFlags
0x180036fbf  mov     ecx, 0C0000005h; dwExceptionCode
0x180036fc4  call    cs:__imp_RaiseException
0x180036fca  int     3; Trap to Debugger
0x180036fcb  mov     r15, [rsi+8]
0x180036fcf  test    r15, r15
0x180036fd2  jz      short loc_180036FF9
0x180036fd4  mov     rcx, [r15+8]
0x180036fd8  mov     rax, [r15]
0x180036fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fe0  mov     rbx, [r15+10h]
0x180036fe4  mov     edx, 18h
0x180036fe9  mov     rcx, r15; Block
0x180036fec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036ff1  mov     r15, rbx
0x180036ff4  test    rbx, rbx
0x180036ff7  jnz     short loc_180036FD4
0x180036ff9  mov     qword ptr [rsi+8], 0
0x180037001  mov     qword ptr [rdi+10h], 0
0x180037009  mov     rcx, [rdi+40h]
0x18003700d  test    rcx, rcx
0x180037010  jz      short loc_18003701E
0x180037012  mov     rax, [rcx]
0x180037015  mov     rax, [rax+10h]
0x180037019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003701e  lea     rcx, [rdi+18h]; lpCriticalSection
0x180037022  call    cs:__imp_DeleteCriticalSection
0x180037028  mov     dword ptr [r14], 0
0x18003702f  add     rsp, 20h
0x180037033  pop     r15
0x180037035  pop     r14
0x180037037  pop     rdi
0x180037038  pop     rsi
0x180037039  pop     rbx
0x18003703a  retn
```
