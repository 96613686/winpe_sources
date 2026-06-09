# ATL::CAtlModule::Term(void)

- ea: `0x1800086d0`
- end: `0x180008783`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003750`
- `0x18000878c`
- `0x180033690`

## callees

- `0x1800086d0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008733`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008733`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000876a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000876a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008710`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008710`

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
0x1800086d0  push    rbx
0x1800086d2  push    rsi
0x1800086d3  push    rdi
0x1800086d4  push    r14
0x1800086d6  push    r15
0x1800086d8  sub     rsp, 20h
0x1800086dc  mov     rdi, rcx
0x1800086df  lea     r14, [rcx+8]
0x1800086e3  cmp     dword ptr [r14], 0
0x1800086e7  jz      loc_180008777
0x1800086ed  cmp     qword ptr [rcx+10h], 0
0x1800086f2  jz      short loc_180008751
0x1800086f4  mov     rax, rcx
0x1800086f7  neg     rax
0x1800086fa  sbb     rsi, rsi
0x1800086fd  and     rsi, r14
0x180008700  jnz     short loc_180008717
0x180008702  xor     r9d, r9d; lpArguments
0x180008705  xor     r8d, r8d; nNumberOfArguments
0x180008708  lea     edx, [rsi+1]; dwExceptionFlags
0x18000870b  mov     ecx, 0C0000005h; dwExceptionCode
0x180008710  call    cs:__imp_RaiseException
0x180008716  int     3; Trap to Debugger
0x180008717  mov     r15, [rsi+8]
0x18000871b  test    r15, r15
0x18000871e  jz      short loc_180008741
0x180008720  mov     rcx, [r15+8]
0x180008724  mov     rax, [r15]
0x180008727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872c  mov     rbx, [r15+10h]
0x180008730  mov     rcx, r15
0x180008733  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008739  mov     r15, rbx
0x18000873c  test    rbx, rbx
0x18000873f  jnz     short loc_180008720
0x180008741  mov     qword ptr [rsi+8], 0
0x180008749  mov     qword ptr [rdi+10h], 0
0x180008751  mov     rcx, [rdi+40h]
0x180008755  test    rcx, rcx
0x180008758  jz      short loc_180008766
0x18000875a  mov     rax, [rcx]
0x18000875d  mov     rax, [rax+10h]
0x180008761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008766  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000876a  call    cs:__imp_DeleteCriticalSection
0x180008770  mov     dword ptr [r14], 0
0x180008777  add     rsp, 20h
0x18000877b  pop     r15
0x18000877d  pop     r14
0x18000877f  pop     rdi
0x180008780  pop     rsi
0x180008781  pop     rbx
0x180008782  retn
```
