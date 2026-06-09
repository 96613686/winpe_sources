# CComInternalCreatorBaseT<CComClassFactoryT<CLicensingStateTools,CComInternalCreatorInitializerT,0>,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b170`
- end: `0x18001b229`
- name: `?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCLicensingStateTools@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001b170`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b17f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b17f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b194`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b194`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorBaseT<CComClassFactoryT<CLicensingStateTools,CComInternalCreatorInitializerT,0>,0>::CreateInstance(
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
    *(_QWORD *)v5 = &CUnknownImplT<CComClassFactoryT<CLicensingStateTools,CComInternalCreatorInitializerT,0>,0>::`vftable';
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
0x18001b170  push    rbx
0x18001b172  push    rbp
0x18001b173  push    rsi
0x18001b174  push    rdi
0x18001b175  sub     rsp, 28h
0x18001b179  mov     rsi, rdx
0x18001b17c  mov     rbp, rcx
0x18001b17f  call    cs:__imp_GetProcessHeap
0x18001b186  nop     dword ptr [rax+rax+00h]
0x18001b18b  xor     edx, edx; dwFlags
0x18001b18d  mov     rcx, rax; hHeap
0x18001b190  lea     r8d, [rdx+10h]; dwBytes
0x18001b194  call    cs:__imp_HeapAlloc
0x18001b19b  nop     dword ptr [rax+rax+00h]
0x18001b1a0  mov     rbx, rax
0x18001b1a3  test    rax, rax
0x18001b1a6  jz      short loc_18001B1C4
0x18001b1a8  lea     rax, ??_7?$CUnknownImplT@V?$CComClassFactoryT@VCLicensingStateTools@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@6B@; const CUnknownImplT<CComClassFactoryT<CLicensingStateTools,CComInternalCreatorInitializerT,0>,0>::`vftable'
0x18001b1af  mov     [rbx], rax
0x18001b1b2  mov     dword ptr [rbx+8], 1
0x18001b1b9  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b1c0  xor     edi, edi
0x18001b1c2  jmp     short loc_18001B1D2
0x18001b1c4  mov     edi, 8007000Eh
0x18001b1c9  xor     ebx, ebx
0x18001b1cb  mov     ecx, edi
0x18001b1cd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b1d2  mov     ecx, edi
0x18001b1d4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b1d9  test    edi, edi
0x18001b1db  jns     short loc_18001B1E1
0x18001b1dd  mov     ecx, edi
0x18001b1df  jmp     short loc_18001B1FD
0x18001b1e1  mov     rax, [rbx]
0x18001b1e4  mov     r8, rsi
0x18001b1e7  mov     rdx, rbp
0x18001b1ea  mov     rcx, rbx
0x18001b1ed  mov     rax, [rax]
0x18001b1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1f5  mov     edi, eax
0x18001b1f7  test    eax, eax
0x18001b1f9  jns     short loc_18001B202
0x18001b1fb  mov     ecx, eax
0x18001b1fd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b202  mov     ecx, edi
0x18001b204  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b209  test    rbx, rbx
0x18001b20c  jz      short loc_18001B21D
0x18001b20e  mov     rcx, [rbx]
0x18001b211  mov     rax, [rcx+10h]
0x18001b215  mov     rcx, rbx
0x18001b218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b21d  mov     eax, edi
0x18001b21f  add     rsp, 28h
0x18001b223  pop     rdi
0x18001b224  pop     rsi
0x18001b225  pop     rbp
0x18001b226  pop     rbx
0x18001b227  retn
```
