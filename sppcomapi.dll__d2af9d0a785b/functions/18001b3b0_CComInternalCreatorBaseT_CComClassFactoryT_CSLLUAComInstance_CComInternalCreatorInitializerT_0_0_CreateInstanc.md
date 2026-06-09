# CComInternalCreatorBaseT<CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b3b0`
- end: `0x18001b469`
- name: `?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCSLLUAComInstance@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001b3b0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b3d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b3d4`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorBaseT<CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>,0>::CreateInstance(
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
    *(_QWORD *)v5 = &CUnknownImplT<CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>,0>::`vftable';
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
0x18001b3b0  push    rbx
0x18001b3b2  push    rbp
0x18001b3b3  push    rsi
0x18001b3b4  push    rdi
0x18001b3b5  sub     rsp, 28h
0x18001b3b9  mov     rsi, rdx
0x18001b3bc  mov     rbp, rcx
0x18001b3bf  call    cs:__imp_GetProcessHeap
0x18001b3c6  nop     dword ptr [rax+rax+00h]
0x18001b3cb  xor     edx, edx; dwFlags
0x18001b3cd  mov     rcx, rax; hHeap
0x18001b3d0  lea     r8d, [rdx+10h]; dwBytes
0x18001b3d4  call    cs:__imp_HeapAlloc
0x18001b3db  nop     dword ptr [rax+rax+00h]
0x18001b3e0  mov     rbx, rax
0x18001b3e3  test    rax, rax
0x18001b3e6  jz      short loc_18001B404
0x18001b3e8  lea     rax, ??_7?$CUnknownImplT@V?$CComClassFactoryT@VCSLLUAComInstance@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@6B@; const CUnknownImplT<CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>,0>::`vftable'
0x18001b3ef  mov     [rbx], rax
0x18001b3f2  mov     dword ptr [rbx+8], 1
0x18001b3f9  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b400  xor     edi, edi
0x18001b402  jmp     short loc_18001B412
0x18001b404  mov     edi, 8007000Eh
0x18001b409  xor     ebx, ebx
0x18001b40b  mov     ecx, edi
0x18001b40d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b412  mov     ecx, edi
0x18001b414  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b419  test    edi, edi
0x18001b41b  jns     short loc_18001B421
0x18001b41d  mov     ecx, edi
0x18001b41f  jmp     short loc_18001B43D
0x18001b421  mov     rax, [rbx]
0x18001b424  mov     r8, rsi
0x18001b427  mov     rdx, rbp
0x18001b42a  mov     rcx, rbx
0x18001b42d  mov     rax, [rax]
0x18001b430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b435  mov     edi, eax
0x18001b437  test    eax, eax
0x18001b439  jns     short loc_18001B442
0x18001b43b  mov     ecx, eax
0x18001b43d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b442  mov     ecx, edi
0x18001b444  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b449  test    rbx, rbx
0x18001b44c  jz      short loc_18001B45D
0x18001b44e  mov     rcx, [rbx]
0x18001b451  mov     rax, [rcx+10h]
0x18001b455  mov     rcx, rbx
0x18001b458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b45d  mov     eax, edi
0x18001b45f  add     rsp, 28h
0x18001b463  pop     rdi
0x18001b464  pop     rsi
0x18001b465  pop     rbp
0x18001b466  pop     rbx
0x18001b467  retn
```
