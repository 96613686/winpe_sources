# ATL::CAtlModule::Term(void)

- ea: `0x18001c0bc`
- end: `0x18001c173`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b144`

## callees

- `0x180002360`
- `0x18001c0bc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c15a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c15a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c0fc`

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
0x18001c0bc  push    rbx
0x18001c0be  push    rsi
0x18001c0bf  push    rdi
0x18001c0c0  push    r14
0x18001c0c2  push    r15
0x18001c0c4  sub     rsp, 20h
0x18001c0c8  mov     rdi, rcx
0x18001c0cb  lea     r14, [rcx+8]
0x18001c0cf  cmp     dword ptr [r14], 0
0x18001c0d3  jz      loc_18001C167
0x18001c0d9  cmp     qword ptr [rcx+10h], 0
0x18001c0de  jz      short loc_18001C141
0x18001c0e0  mov     rax, rcx
0x18001c0e3  neg     rax
0x18001c0e6  sbb     rsi, rsi
0x18001c0e9  and     rsi, r14
0x18001c0ec  jnz     short loc_18001C103
0x18001c0ee  xor     r9d, r9d; lpArguments
0x18001c0f1  xor     r8d, r8d; nNumberOfArguments
0x18001c0f4  lea     edx, [rsi+1]; dwExceptionFlags
0x18001c0f7  mov     ecx, 0C0000005h; dwExceptionCode
0x18001c0fc  call    cs:__imp_RaiseException
0x18001c102  int     3; Trap to Debugger
0x18001c103  mov     r15, [rsi+8]
0x18001c107  test    r15, r15
0x18001c10a  jz      short loc_18001C131
0x18001c10c  mov     rcx, [r15+8]
0x18001c110  mov     rax, [r15]
0x18001c113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c118  mov     rbx, [r15+10h]
0x18001c11c  mov     edx, 18h
0x18001c121  mov     rcx, r15; Block
0x18001c124  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c129  mov     r15, rbx
0x18001c12c  test    rbx, rbx
0x18001c12f  jnz     short loc_18001C10C
0x18001c131  mov     qword ptr [rsi+8], 0
0x18001c139  mov     qword ptr [rdi+10h], 0
0x18001c141  mov     rcx, [rdi+40h]
0x18001c145  test    rcx, rcx
0x18001c148  jz      short loc_18001C156
0x18001c14a  mov     rax, [rcx]
0x18001c14d  mov     rax, [rax+10h]
0x18001c151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c156  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001c15a  call    cs:__imp_DeleteCriticalSection
0x18001c160  mov     dword ptr [r14], 0
0x18001c167  add     rsp, 20h
0x18001c16b  pop     r15
0x18001c16d  pop     r14
0x18001c16f  pop     rdi
0x18001c170  pop     rsi
0x18001c171  pop     rbx
0x18001c172  retn
```
