# ATL::CAtlModule::Term(void)

- ea: `0x18000d478`
- end: `0x18000d52a`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008db0`
- `0x18000e610`
- `0x180021d20`

## callees

- `0x180001554`
- `0x18000d478`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d511`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d511`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d4b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d4b8`

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
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
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
0x18000d478  push    rbx
0x18000d47a  push    rsi
0x18000d47b  push    rdi
0x18000d47c  push    r14
0x18000d47e  push    r15
0x18000d480  sub     rsp, 20h
0x18000d484  lea     r14, [rcx+8]
0x18000d488  mov     rdi, rcx
0x18000d48b  cmp     dword ptr [r14], 0
0x18000d48f  jz      loc_18000D51E
0x18000d495  cmp     qword ptr [rcx+10h], 0
0x18000d49a  jz      short loc_18000D4F8
0x18000d49c  mov     rax, rcx
0x18000d49f  neg     rax
0x18000d4a2  sbb     rsi, rsi
0x18000d4a5  and     rsi, r14
0x18000d4a8  jnz     short loc_18000D4BF
0x18000d4aa  xor     r9d, r9d; lpArguments
0x18000d4ad  lea     edx, [rsi+1]; dwExceptionFlags
0x18000d4b0  xor     r8d, r8d; nNumberOfArguments
0x18000d4b3  mov     ecx, 0C0000005h; dwExceptionCode
0x18000d4b8  call    cs:__imp_RaiseException
0x18000d4be  int     3; Trap to Debugger
0x18000d4bf  mov     r15, [rsi+8]
0x18000d4c3  test    r15, r15
0x18000d4c6  jz      short loc_18000D4E8
0x18000d4c8  mov     rcx, [r15+8]
0x18000d4cc  mov     rax, [r15]
0x18000d4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4d4  mov     rbx, [r15+10h]
0x18000d4d8  mov     rcx, r15; Block
0x18000d4db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d4e0  mov     r15, rbx
0x18000d4e3  test    rbx, rbx
0x18000d4e6  jnz     short loc_18000D4C8
0x18000d4e8  mov     qword ptr [rsi+8], 0
0x18000d4f0  mov     qword ptr [rdi+10h], 0
0x18000d4f8  mov     rcx, [rdi+40h]
0x18000d4fc  test    rcx, rcx
0x18000d4ff  jz      short loc_18000D50D
0x18000d501  mov     rax, [rcx]
0x18000d504  mov     rax, [rax+10h]
0x18000d508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d50d  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000d511  call    cs:__imp_DeleteCriticalSection
0x18000d517  mov     dword ptr [r14], 0
0x18000d51e  add     rsp, 20h
0x18000d522  pop     r15
0x18000d524  pop     r14
0x18000d526  pop     rdi
0x18000d527  pop     rsi
0x18000d528  pop     rbx
0x18000d529  retn
```
