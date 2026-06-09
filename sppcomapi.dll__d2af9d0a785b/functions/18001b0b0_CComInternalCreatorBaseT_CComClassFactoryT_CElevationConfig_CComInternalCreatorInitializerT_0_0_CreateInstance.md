# CComInternalCreatorBaseT<CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b0b0`
- end: `0x18001b169`
- name: `?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCElevationConfig@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001b0b0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b0bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b0bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b0d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b0d4`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorBaseT<CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>,0>::CreateInstance(
        __int64 a1,
        __int64 a2)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rcx
  int v8; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0x10u);
  if ( v5 )
  {
    *(_QWORD *)v5 = &CUnknownImplT<CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>,0>::`vftable';
    v5[2] = 1;
    _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
    v6 = 0;
  }
  else
  {
    v6 = -2147024882;
    v5 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) == 0 )
  {
    v8 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v5)(v5, a1, a2);
    v6 = v8;
    if ( v8 >= 0 )
      goto LABEL_9;
    v7 = (unsigned int)v8;
  }
  else
  {
    v7 = v6;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v5 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  return v6;
}

```

## disassembly

```asm
0x18001b0b0  push    rbx
0x18001b0b2  push    rbp
0x18001b0b3  push    rsi
0x18001b0b4  push    rdi
0x18001b0b5  sub     rsp, 28h
0x18001b0b9  mov     rsi, rdx
0x18001b0bc  mov     rbp, rcx
0x18001b0bf  call    cs:__imp_GetProcessHeap
0x18001b0c6  nop     dword ptr [rax+rax+00h]
0x18001b0cb  xor     edx, edx; dwFlags
0x18001b0cd  mov     rcx, rax; hHeap
0x18001b0d0  lea     r8d, [rdx+10h]; dwBytes
0x18001b0d4  call    cs:__imp_HeapAlloc
0x18001b0db  nop     dword ptr [rax+rax+00h]
0x18001b0e0  mov     rbx, rax
0x18001b0e3  test    rax, rax
0x18001b0e6  jz      short loc_18001B104
0x18001b0e8  lea     rax, ??_7?$CUnknownImplT@V?$CComClassFactoryT@VCElevationConfig@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@6B@; const CUnknownImplT<CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>,0>::`vftable'
0x18001b0ef  mov     [rbx], rax
0x18001b0f2  mov     dword ptr [rbx+8], 1
0x18001b0f9  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b100  xor     edi, edi
0x18001b102  jmp     short loc_18001B112
0x18001b104  mov     edi, 8007000Eh
0x18001b109  xor     ebx, ebx
0x18001b10b  mov     ecx, edi
0x18001b10d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b112  mov     ecx, edi
0x18001b114  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b119  test    edi, edi
0x18001b11b  jns     short loc_18001B121
0x18001b11d  mov     ecx, edi
0x18001b11f  jmp     short loc_18001B13D
0x18001b121  mov     rax, [rbx]
0x18001b124  mov     r8, rsi
0x18001b127  mov     rdx, rbp
0x18001b12a  mov     rcx, rbx
0x18001b12d  mov     rax, [rax]
0x18001b130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b135  mov     edi, eax
0x18001b137  test    eax, eax
0x18001b139  jns     short loc_18001B142
0x18001b13b  mov     ecx, eax
0x18001b13d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b142  mov     ecx, edi
0x18001b144  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b149  test    rbx, rbx
0x18001b14c  jz      short loc_18001B15D
0x18001b14e  mov     rcx, [rbx]
0x18001b151  mov     rax, [rcx+10h]
0x18001b155  mov     rcx, rbx
0x18001b158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b15d  mov     eax, edi
0x18001b15f  add     rsp, 28h
0x18001b163  pop     rdi
0x18001b164  pop     rsi
0x18001b165  pop     rbp
0x18001b166  pop     rbx
0x18001b167  retn
```
