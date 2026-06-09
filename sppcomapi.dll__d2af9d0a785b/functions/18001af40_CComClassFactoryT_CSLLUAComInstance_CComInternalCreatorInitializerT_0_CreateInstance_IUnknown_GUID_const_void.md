# CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001af40`
- end: `0x18001b04a`
- name: `?CreateInstance@?$CComClassFactoryT@VCSLLUAComInstance@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001af40`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001af74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001af74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001af89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001af89`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rbx
  __int64 v10; // rcx
  int v11; // eax

  if ( !a4 )
  {
    v6 = -2147467261;
LABEL_16:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_17;
  }
  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    goto LABEL_16;
  }
  ProcessHeap = GetProcessHeap();
  v8 = (unsigned __int64)HeapAlloc(ProcessHeap, 0, 0x18u);
  v9 = v8;
  if ( v8 )
  {
    *(_OWORD *)(v8 & -(__int64)(v8 != -8)) = 0;
    *(_QWORD *)v8 = &CUnknownImplT<CSLLUAComInstance,0>::`vftable';
    *(_DWORD *)(v8 + 16) = 1;
    _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
    v6 = 0;
  }
  else
  {
    v6 = -2147024882;
    v9 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) == 0 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v11 = (**(__int64 (__fastcall ***)(unsigned __int64, __int64, _QWORD *))v9)(v9, a3, a4);
    v6 = v11;
    if ( v11 >= 0 )
      goto LABEL_13;
    v10 = (unsigned int)v11;
  }
  else
  {
    v10 = v6;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v9 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_16;
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  return v6;
}

```

## disassembly

```asm
0x18001af40  push    rbx
0x18001af42  push    rbp
0x18001af43  push    rsi
0x18001af44  push    rdi
0x18001af45  sub     rsp, 28h
0x18001af49  mov     rsi, r9
0x18001af4c  mov     rbp, r8
0x18001af4f  test    r9, r9
0x18001af52  jnz     short loc_18001AF5E
0x18001af54  mov     edi, 80004003h
0x18001af59  jmp     loc_18001B030
0x18001af5e  mov     qword ptr [r9], 0
0x18001af65  test    rdx, rdx
0x18001af68  jz      short loc_18001AF74
0x18001af6a  mov     edi, 80040110h
0x18001af6f  jmp     loc_18001B030
0x18001af74  call    cs:__imp_GetProcessHeap
0x18001af7b  nop     dword ptr [rax+rax+00h]
0x18001af80  xor     edx, edx; dwFlags
0x18001af82  mov     rcx, rax; hHeap
0x18001af85  lea     r8d, [rdx+18h]; dwBytes
0x18001af89  call    cs:__imp_HeapAlloc
0x18001af90  nop     dword ptr [rax+rax+00h]
0x18001af95  mov     rbx, rax
0x18001af98  test    rax, rax
0x18001af9b  jz      short loc_18001AFCC
0x18001af9d  add     rax, 8
0x18001afa1  xorps   xmm0, xmm0
0x18001afa4  neg     rax
0x18001afa7  lea     rax, ??_7?$CUnknownImplT@VCSLLUAComInstance@@$0A@@@6B@; const CUnknownImplT<CSLLUAComInstance,0>::`vftable'
0x18001afae  sbb     rcx, rcx
0x18001afb1  and     rcx, rbx
0x18001afb4  movups  xmmword ptr [rcx], xmm0
0x18001afb7  mov     [rbx], rax
0x18001afba  mov     dword ptr [rbx+10h], 1
0x18001afc1  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001afc8  xor     edi, edi
0x18001afca  jmp     short loc_18001AFDA
0x18001afcc  mov     edi, 8007000Eh
0x18001afd1  xor     ebx, ebx
0x18001afd3  mov     ecx, edi
0x18001afd5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001afda  mov     ecx, edi
0x18001afdc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001afe1  test    edi, edi
0x18001afe3  jns     short loc_18001AFE9
0x18001afe5  mov     ecx, edi
0x18001afe7  jmp     short loc_18001B00C
0x18001afe9  xor     ecx, ecx
0x18001afeb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001aff0  mov     rax, [rbx]
0x18001aff3  mov     r8, rsi
0x18001aff6  mov     rdx, rbp
0x18001aff9  mov     rcx, rbx
0x18001affc  mov     rax, [rax]
0x18001afff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b004  mov     edi, eax
0x18001b006  test    eax, eax
0x18001b008  jns     short loc_18001B011
0x18001b00a  mov     ecx, eax
0x18001b00c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b011  mov     ecx, edi
0x18001b013  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b018  test    rbx, rbx
0x18001b01b  jz      short loc_18001B02C
0x18001b01d  mov     rax, [rbx]
0x18001b020  mov     rcx, rbx
0x18001b023  mov     rax, [rax+10h]
0x18001b027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b02c  test    edi, edi
0x18001b02e  jns     short loc_18001B037
0x18001b030  mov     ecx, edi
0x18001b032  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b037  mov     ecx, edi
0x18001b039  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b03e  mov     eax, edi
0x18001b040  add     rsp, 28h
0x18001b044  pop     rdi
0x18001b045  pop     rsi
0x18001b046  pop     rbp
0x18001b047  pop     rbx
0x18001b048  retn
```
