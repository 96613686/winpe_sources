# ATL::CAtlModule::Term(void)

- ea: `0x180009968`
- end: `0x180009a1a`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007230`
- `0x18000a1bc`
- `0x180015c20`

## callees

- `0x1800012d4`
- `0x180009968`
- `0x180016010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800099a8`
- `KERNEL32!RaiseException` at `0x1800099a8`
- `KERNEL32!DeleteCriticalSection` at `0x180009a01`
- `KERNEL32!DeleteCriticalSection` at `0x180009a01`

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
0x180009968  push    rbx
0x18000996a  push    rsi
0x18000996b  push    rdi
0x18000996c  push    r14
0x18000996e  push    r15
0x180009970  sub     rsp, 20h
0x180009974  lea     r14, [rcx+8]
0x180009978  mov     rdi, rcx
0x18000997b  cmp     dword ptr [r14], 0
0x18000997f  jz      loc_180009A0E
0x180009985  cmp     qword ptr [rcx+10h], 0
0x18000998a  jz      short loc_1800099E8
0x18000998c  mov     rax, rcx
0x18000998f  neg     rax
0x180009992  sbb     rsi, rsi
0x180009995  and     rsi, r14
0x180009998  jnz     short loc_1800099AF
0x18000999a  xor     r9d, r9d; lpArguments
0x18000999d  lea     edx, [rsi+1]; dwExceptionFlags
0x1800099a0  xor     r8d, r8d; nNumberOfArguments
0x1800099a3  mov     ecx, 0C0000005h; dwExceptionCode
0x1800099a8  call    cs:__imp_RaiseException
0x1800099ae  int     3; Trap to Debugger
0x1800099af  mov     r15, [rsi+8]
0x1800099b3  test    r15, r15
0x1800099b6  jz      short loc_1800099D8
0x1800099b8  mov     rcx, [r15+8]
0x1800099bc  mov     rax, [r15]
0x1800099bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c4  mov     rbx, [r15+10h]
0x1800099c8  mov     rcx, r15; Block
0x1800099cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099d0  mov     r15, rbx
0x1800099d3  test    rbx, rbx
0x1800099d6  jnz     short loc_1800099B8
0x1800099d8  mov     qword ptr [rsi+8], 0
0x1800099e0  mov     qword ptr [rdi+10h], 0
0x1800099e8  mov     rcx, [rdi+40h]
0x1800099ec  test    rcx, rcx
0x1800099ef  jz      short loc_1800099FD
0x1800099f1  mov     rax, [rcx]
0x1800099f4  mov     rax, [rax+10h]
0x1800099f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099fd  lea     rcx, [rdi+18h]; lpCriticalSection
0x180009a01  call    cs:__imp_DeleteCriticalSection
0x180009a07  mov     dword ptr [r14], 0
0x180009a0e  add     rsp, 20h
0x180009a12  pop     r15
0x180009a14  pop     r14
0x180009a16  pop     rdi
0x180009a17  pop     rsi
0x180009a18  pop     rbx
0x180009a19  retn
```
