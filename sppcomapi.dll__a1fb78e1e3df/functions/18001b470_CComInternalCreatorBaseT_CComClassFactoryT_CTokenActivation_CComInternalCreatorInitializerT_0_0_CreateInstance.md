# CComInternalCreatorBaseT<CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b470`
- end: `0x18001b529`
- name: `?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCTokenActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001b470`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b47f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b47f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b494`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b494`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorBaseT<CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance(
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
    *(_QWORD *)v5 = &CUnknownImplT<CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>,0>::`vftable';
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
0x18001b470  push    rbx
0x18001b472  push    rbp
0x18001b473  push    rsi
0x18001b474  push    rdi
0x18001b475  sub     rsp, 28h
0x18001b479  mov     rsi, rdx
0x18001b47c  mov     rbp, rcx
0x18001b47f  call    cs:__imp_GetProcessHeap
0x18001b486  nop     dword ptr [rax+rax+00h]
0x18001b48b  xor     edx, edx; dwFlags
0x18001b48d  mov     rcx, rax; hHeap
0x18001b490  lea     r8d, [rdx+10h]; dwBytes
0x18001b494  call    cs:__imp_HeapAlloc
0x18001b49b  nop     dword ptr [rax+rax+00h]
0x18001b4a0  mov     rbx, rax
0x18001b4a3  test    rax, rax
0x18001b4a6  jz      short loc_18001B4C4
0x18001b4a8  lea     rax, ??_7?$CUnknownImplT@V?$CComClassFactoryT@VCTokenActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@6B@; const CUnknownImplT<CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>,0>::`vftable'
0x18001b4af  mov     [rbx], rax
0x18001b4b2  mov     dword ptr [rbx+8], 1
0x18001b4b9  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b4c0  xor     edi, edi
0x18001b4c2  jmp     short loc_18001B4D2
0x18001b4c4  mov     edi, 8007000Eh
0x18001b4c9  xor     ebx, ebx
0x18001b4cb  mov     ecx, edi
0x18001b4cd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b4d2  mov     ecx, edi
0x18001b4d4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b4d9  test    edi, edi
0x18001b4db  jns     short loc_18001B4E1
0x18001b4dd  mov     ecx, edi
0x18001b4df  jmp     short loc_18001B4FD
0x18001b4e1  mov     rax, [rbx]
0x18001b4e4  mov     r8, rsi
0x18001b4e7  mov     rdx, rbp
0x18001b4ea  mov     rcx, rbx
0x18001b4ed  mov     rax, [rax]
0x18001b4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4f5  mov     edi, eax
0x18001b4f7  test    eax, eax
0x18001b4f9  jns     short loc_18001B502
0x18001b4fb  mov     ecx, eax
0x18001b4fd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b502  mov     ecx, edi
0x18001b504  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b509  test    rbx, rbx
0x18001b50c  jz      short loc_18001B51D
0x18001b50e  mov     rcx, [rbx]
0x18001b511  mov     rax, [rcx+10h]
0x18001b515  mov     rcx, rbx
0x18001b518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b51d  mov     eax, edi
0x18001b51f  add     rsp, 28h
0x18001b523  pop     rdi
0x18001b524  pop     rsi
0x18001b525  pop     rbp
0x18001b526  pop     rbx
0x18001b527  retn
```
