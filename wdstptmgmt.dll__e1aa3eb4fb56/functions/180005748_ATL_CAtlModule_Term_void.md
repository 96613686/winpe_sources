# ATL::CAtlModule::Term(void)

- ea: `0x180005748`
- end: `0x180005811`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `201`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002ac4`

## callees

- `0x180005748`
- `0x180005c28`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800057ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057ae`
- `KERNEL32!DeleteCriticalSection` at `0x1800057e5`
- `KERNEL32!DeleteCriticalSection` at `0x1800057e5`

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
        __debugbreak();
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
0x180005748  mov     rax, rsp
0x18000574b  mov     [rax+8], rbx
0x18000574f  mov     [rax+10h], rsi
0x180005753  mov     [rax+18h], rdi
0x180005757  mov     [rax+20h], r14
0x18000575b  push    r15
0x18000575d  sub     rsp, 20h
0x180005761  mov     rdi, rcx
0x180005764  lea     r14, [rcx+8]
0x180005768  cmp     dword ptr [r14], 0
0x18000576c  jz      loc_1800057F5
0x180005772  cmp     qword ptr [rcx+10h], 0
0x180005777  jz      short loc_1800057CC
0x180005779  mov     rax, rcx
0x18000577c  neg     rax
0x18000577f  sbb     rsi, rsi
0x180005782  and     rsi, r14
0x180005785  jnz     short loc_180005792
0x180005787  mov     ecx, 0C0000005h; unsigned int
0x18000578c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180005791  int     3; Trap to Debugger
0x180005792  mov     r15, [rsi+8]
0x180005796  test    r15, r15
0x180005799  jz      short loc_1800057C2
0x18000579b  mov     rcx, [r15+8]
0x18000579f  mov     rax, [r15]
0x1800057a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a7  mov     rbx, [r15+10h]
0x1800057ab  mov     rcx, r15
0x1800057ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800057b5  nop     dword ptr [rax+rax+00h]
0x1800057ba  mov     r15, rbx
0x1800057bd  test    rbx, rbx
0x1800057c0  jnz     short loc_18000579B
0x1800057c2  and     qword ptr [rsi+8], 0
0x1800057c7  and     qword ptr [rdi+10h], 0
0x1800057cc  mov     rcx, [rdi+40h]
0x1800057d0  test    rcx, rcx
0x1800057d3  jz      short loc_1800057E1
0x1800057d5  mov     rax, [rcx]
0x1800057d8  mov     rax, [rax+10h]
0x1800057dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e1  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800057e5  call    cs:__imp_DeleteCriticalSection
0x1800057ec  nop     dword ptr [rax+rax+00h]
0x1800057f1  and     dword ptr [r14], 0
0x1800057f5  mov     rbx, [rsp+28h+arg_0]
0x1800057fa  mov     rsi, [rsp+28h+arg_8]
0x1800057ff  mov     rdi, [rsp+28h+arg_10]
0x180005804  mov     r14, [rsp+28h+arg_18]
0x180005809  add     rsp, 20h
0x18000580d  pop     r15
0x18000580f  retn
```
