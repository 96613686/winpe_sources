# CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::get__NewEnum(IEnumVARIANT * *)

- ea: `0x180021350`
- end: `0x180021408`
- name: `?get__NewEnum@?$CDispCollectionOnDispImpl@VCOfflineActivationPhoneStore@@VCOfflineActivationPhoneData@@UIOfflineActivationPhoneData@@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U6@B@@UEAAJPEAPEAUIEnumVARIANT@@@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x180021350`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021371`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021371`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021386`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021386`

## pseudocode

```c
__int64 __fastcall CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::get__NewEnum(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rdi

  if ( !a2 )
  {
    v4 = -2147024809;
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_7;
  }
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 0, 0x20u);
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    goto LABEL_6;
  }
  v6[2] = 0;
  *v6 = &CUnknownImplT<EnumVARIANTImpl,0>::`vftable';
  *((_DWORD *)v6 + 6) = 1;
  _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
  v6[2] = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  *((_DWORD *)v7 + 2) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v4 = 0;
  *a2 = v7;
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x180021350  mov     [rsp+arg_0], rbx
0x180021355  mov     [rsp+arg_8], rsi
0x18002135a  push    rdi
0x18002135b  sub     rsp, 20h
0x18002135f  mov     rsi, rdx
0x180021362  mov     rbx, rcx
0x180021365  test    rdx, rdx
0x180021368  jnz     short loc_180021371
0x18002136a  mov     ebx, 80070057h
0x18002136f  jmp     short loc_1800213E7
0x180021371  call    cs:__imp_GetProcessHeap
0x180021378  nop     dword ptr [rax+rax+00h]
0x18002137d  xor     edx, edx; dwFlags
0x18002137f  mov     rcx, rax; hHeap
0x180021382  lea     r8d, [rdx+20h]; dwBytes
0x180021386  call    cs:__imp_HeapAlloc
0x18002138d  nop     dword ptr [rax+rax+00h]
0x180021392  mov     rdi, rax
0x180021395  test    rax, rax
0x180021398  jz      short loc_1800213E2
0x18002139a  mov     qword ptr [rax+10h], 0
0x1800213a2  lea     rax, ??_7?$CUnknownImplT@VEnumVARIANTImpl@@$0A@@@6B@; const CUnknownImplT<EnumVARIANTImpl,0>::`vftable'
0x1800213a9  mov     [rdi], rax
0x1800213ac  mov     dword ptr [rdi+18h], 1
0x1800213b3  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x1800213ba  mov     [rdi+10h], rbx
0x1800213be  mov     rcx, rbx
0x1800213c1  mov     rax, [rbx]
0x1800213c4  mov     rax, [rax+8]
0x1800213c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213cd  mov     dword ptr [rdi+8], 0
0x1800213d4  xor     ecx, ecx
0x1800213d6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800213db  xor     ebx, ebx
0x1800213dd  mov     [rsi], rdi
0x1800213e0  jmp     short loc_1800213EE
0x1800213e2  mov     ebx, 8007000Eh
0x1800213e7  mov     ecx, ebx
0x1800213e9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800213ee  mov     ecx, ebx
0x1800213f0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800213f5  mov     rsi, [rsp+28h+arg_8]
0x1800213fa  mov     eax, ebx
0x1800213fc  mov     rbx, [rsp+28h+arg_0]
0x180021401  add     rsp, 20h
0x180021405  pop     rdi
0x180021406  retn
```
