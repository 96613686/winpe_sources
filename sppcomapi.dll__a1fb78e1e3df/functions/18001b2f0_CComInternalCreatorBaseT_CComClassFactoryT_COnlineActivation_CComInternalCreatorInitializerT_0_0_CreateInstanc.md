# CComInternalCreatorBaseT<CComClassFactoryT<COnlineActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b2f0`
- end: `0x18001b3a9`
- name: `?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCOnlineActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001b2f0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b2ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b2ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b314`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b314`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorBaseT<CComClassFactoryT<COnlineActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance(
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
    *(_QWORD *)v5 = &CUnknownImplT<CComClassFactoryT<COnlineActivation,CComInternalCreatorInitializerT,0>,0>::`vftable';
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
0x18001b2f0  push    rbx
0x18001b2f2  push    rbp
0x18001b2f3  push    rsi
0x18001b2f4  push    rdi
0x18001b2f5  sub     rsp, 28h
0x18001b2f9  mov     rsi, rdx
0x18001b2fc  mov     rbp, rcx
0x18001b2ff  call    cs:__imp_GetProcessHeap
0x18001b306  nop     dword ptr [rax+rax+00h]
0x18001b30b  xor     edx, edx; dwFlags
0x18001b30d  mov     rcx, rax; hHeap
0x18001b310  lea     r8d, [rdx+10h]; dwBytes
0x18001b314  call    cs:__imp_HeapAlloc
0x18001b31b  nop     dword ptr [rax+rax+00h]
0x18001b320  mov     rbx, rax
0x18001b323  test    rax, rax
0x18001b326  jz      short loc_18001B344
0x18001b328  lea     rax, ??_7?$CUnknownImplT@V?$CComClassFactoryT@VCOnlineActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@6B@; const CUnknownImplT<CComClassFactoryT<COnlineActivation,CComInternalCreatorInitializerT,0>,0>::`vftable'
0x18001b32f  mov     [rbx], rax
0x18001b332  mov     dword ptr [rbx+8], 1
0x18001b339  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b340  xor     edi, edi
0x18001b342  jmp     short loc_18001B352
0x18001b344  mov     edi, 8007000Eh
0x18001b349  xor     ebx, ebx
0x18001b34b  mov     ecx, edi
0x18001b34d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b352  mov     ecx, edi
0x18001b354  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b359  test    edi, edi
0x18001b35b  jns     short loc_18001B361
0x18001b35d  mov     ecx, edi
0x18001b35f  jmp     short loc_18001B37D
0x18001b361  mov     rax, [rbx]
0x18001b364  mov     r8, rsi
0x18001b367  mov     rdx, rbp
0x18001b36a  mov     rcx, rbx
0x18001b36d  mov     rax, [rax]
0x18001b370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b375  mov     edi, eax
0x18001b377  test    eax, eax
0x18001b379  jns     short loc_18001B382
0x18001b37b  mov     ecx, eax
0x18001b37d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b382  mov     ecx, edi
0x18001b384  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b389  test    rbx, rbx
0x18001b38c  jz      short loc_18001B39D
0x18001b38e  mov     rcx, [rbx]
0x18001b391  mov     rax, [rcx+10h]
0x18001b395  mov     rcx, rbx
0x18001b398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b39d  mov     eax, edi
0x18001b39f  add     rsp, 28h
0x18001b3a3  pop     rdi
0x18001b3a4  pop     rsi
0x18001b3a5  pop     rbp
0x18001b3a6  pop     rbx
0x18001b3a7  retn
```
