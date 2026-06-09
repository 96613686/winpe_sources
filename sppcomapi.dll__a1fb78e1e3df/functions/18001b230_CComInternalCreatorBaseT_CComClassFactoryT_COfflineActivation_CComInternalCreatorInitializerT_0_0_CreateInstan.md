# CComInternalCreatorBaseT<CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b230`
- end: `0x18001b2e9`
- name: `?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCOfflineActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001b230`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b23f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b23f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b254`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b254`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorBaseT<CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance(
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
    *(_QWORD *)v5 = &CUnknownImplT<CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>,0>::`vftable';
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
0x18001b230  push    rbx
0x18001b232  push    rbp
0x18001b233  push    rsi
0x18001b234  push    rdi
0x18001b235  sub     rsp, 28h
0x18001b239  mov     rsi, rdx
0x18001b23c  mov     rbp, rcx
0x18001b23f  call    cs:__imp_GetProcessHeap
0x18001b246  nop     dword ptr [rax+rax+00h]
0x18001b24b  xor     edx, edx; dwFlags
0x18001b24d  mov     rcx, rax; hHeap
0x18001b250  lea     r8d, [rdx+10h]; dwBytes
0x18001b254  call    cs:__imp_HeapAlloc
0x18001b25b  nop     dword ptr [rax+rax+00h]
0x18001b260  mov     rbx, rax
0x18001b263  test    rax, rax
0x18001b266  jz      short loc_18001B284
0x18001b268  lea     rax, ??_7?$CUnknownImplT@V?$CComClassFactoryT@VCOfflineActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@6B@; const CUnknownImplT<CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>,0>::`vftable'
0x18001b26f  mov     [rbx], rax
0x18001b272  mov     dword ptr [rbx+8], 1
0x18001b279  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b280  xor     edi, edi
0x18001b282  jmp     short loc_18001B292
0x18001b284  mov     edi, 8007000Eh
0x18001b289  xor     ebx, ebx
0x18001b28b  mov     ecx, edi
0x18001b28d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b292  mov     ecx, edi
0x18001b294  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b299  test    edi, edi
0x18001b29b  jns     short loc_18001B2A1
0x18001b29d  mov     ecx, edi
0x18001b29f  jmp     short loc_18001B2BD
0x18001b2a1  mov     rax, [rbx]
0x18001b2a4  mov     r8, rsi
0x18001b2a7  mov     rdx, rbp
0x18001b2aa  mov     rcx, rbx
0x18001b2ad  mov     rax, [rax]
0x18001b2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2b5  mov     edi, eax
0x18001b2b7  test    eax, eax
0x18001b2b9  jns     short loc_18001B2C2
0x18001b2bb  mov     ecx, eax
0x18001b2bd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b2c2  mov     ecx, edi
0x18001b2c4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b2c9  test    rbx, rbx
0x18001b2cc  jz      short loc_18001B2DD
0x18001b2ce  mov     rcx, [rbx]
0x18001b2d1  mov     rax, [rcx+10h]
0x18001b2d5  mov     rcx, rbx
0x18001b2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2dd  mov     eax, edi
0x18001b2df  add     rsp, 28h
0x18001b2e3  pop     rdi
0x18001b2e4  pop     rsi
0x18001b2e5  pop     rbp
0x18001b2e6  pop     rbx
0x18001b2e7  retn
```
