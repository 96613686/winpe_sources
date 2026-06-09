# CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::get_Item(tagVARIANT,IOfflineActivationPhoneData * *)

- ea: `0x180020d40`
- end: `0x180020e81`
- name: `?get_Item@?$CDispCollectionOnDispImpl@VCOfflineActivationPhoneStore@@VCOfflineActivationPhoneData@@UIOfflineActivationPhoneData@@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U6@B@@UEAAJUtagVARIANT@@PEAPEAUIOfflineActivationPhoneData@@@Z`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001e0a8`
- `0x180020d40`
- `0x18003c52a`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020d85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020d9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020d9c`

## pseudocode

```c
__int64 __fastcall CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::get_Item(
        __int64 a1,
        __int64 a2,
        unsigned __int64 *a3)
{
  unsigned __int64 v3; // rbx
  __int64 v6; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v8; // rax
  unsigned __int64 v9; // rsi
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rcx

  v3 = 0;
  if ( !a3
    || ((*(_WORD *)a2 - 3) & 0xFFEF) != 0
    || (v6 = *(int *)(a2 + 8), (unsigned int)v6 >= *(_DWORD *)(*(_QWORD *)(a1 + 136) + 12LL)) )
  {
    v12 = 2147942487LL;
    v11 = -2147024809;
    goto LABEL_10;
  }
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 0, 0x98u);
  v9 = (unsigned __int64)v8;
  if ( !v8 )
  {
    v11 = -2147024882;
    v12 = 2147942414LL;
LABEL_10:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    goto LABEL_11;
  }
  v8[1] = 0;
  v8[2] = 0;
  memset_0(v8 + 3, 0, 0x68u);
  *(_DWORD *)(v9 + 128) = 0;
  memset_0((void *)(v9 & -(__int64)(v9 != -136)), 0, 0x90u);
  *(_QWORD *)(v9 + 136) = 0;
  *(_QWORD *)v9 = &CUnknownImplT<COfflineActivationPhoneData,0>::`vftable';
  *(_DWORD *)(v9 + 144) = 1;
  _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
  v10 = COfflineActivationPhoneData::InitializeObject(
          (COfflineActivationPhoneData *)v9,
          *(struct COfflineActivationPhoneStore **)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 16LL) + 8 * v6));
  v11 = v10;
  if ( v10 >= 0 )
  {
    v3 = 0;
    *a3 = v9;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
    v3 = v9;
  }
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  if ( v3 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v3 + 16LL))(v3);
  return v11;
}

```

## disassembly

```asm
0x180020d40  push    rbx
0x180020d42  push    rbp
0x180020d43  push    rsi
0x180020d44  push    rdi
0x180020d45  push    r14
0x180020d47  sub     rsp, 20h
0x180020d4b  xor     ebx, ebx
0x180020d4d  mov     r14, r8
0x180020d50  mov     rbp, rcx
0x180020d53  test    r8, r8
0x180020d56  jz      loc_180020E4C
0x180020d5c  movzx   eax, word ptr [rdx]
0x180020d5f  mov     ecx, 0FFEFh
0x180020d64  sub     ax, 3
0x180020d68  test    cx, ax
0x180020d6b  jnz     loc_180020E4C
0x180020d71  mov     rax, [rbp+88h]
0x180020d78  movsxd  rdi, dword ptr [rdx+8]
0x180020d7c  cmp     edi, [rax+0Ch]
0x180020d7f  jnb     loc_180020E4C
0x180020d85  call    cs:__imp_GetProcessHeap
0x180020d8c  nop     dword ptr [rax+rax+00h]
0x180020d91  xor     edx, edx; dwFlags
0x180020d93  mov     r8d, 98h; dwBytes
0x180020d99  mov     rcx, rax; hHeap
0x180020d9c  call    cs:__imp_HeapAlloc
0x180020da3  nop     dword ptr [rax+rax+00h]
0x180020da8  mov     rsi, rax
0x180020dab  test    rax, rax
0x180020dae  jz      loc_180020E43
0x180020db4  lea     rcx, [rax+18h]; void *
0x180020db8  mov     [rax+8], rbx
0x180020dbc  xor     edx, edx; Val
0x180020dbe  mov     [rax+10h], rbx
0x180020dc2  lea     r8d, [rbx+68h]; Size
0x180020dc6  call    memset_0
0x180020dcb  mov     [rsi+80h], ebx
0x180020dd1  mov     r8d, 90h; Size
0x180020dd7  lea     rbx, [rsi+88h]
0x180020dde  mov     rax, rbx
0x180020de1  neg     rax
0x180020de4  sbb     rcx, rcx
0x180020de7  xor     edx, edx; Val
0x180020de9  and     rcx, rsi; void *
0x180020dec  call    memset_0
0x180020df1  lea     rax, ??_7?$CUnknownImplT@VCOfflineActivationPhoneData@@$0A@@@6B@; const CUnknownImplT<COfflineActivationPhoneData,0>::`vftable'
0x180020df8  mov     qword ptr [rbx], 0
0x180020dff  mov     [rsi], rax
0x180020e02  mov     dword ptr [rsi+90h], 1
0x180020e0c  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x180020e13  mov     rax, [rbp+88h]
0x180020e1a  mov     rcx, rsi; this
0x180020e1d  mov     rdx, [rax+10h]
0x180020e21  mov     rdx, [rdx+rdi*8]; struct COfflineActivationPhoneStore *
0x180020e25  call    ?InitializeObject@COfflineActivationPhoneData@@QEAAJPEAVCOfflineActivationPhoneStore@@@Z; COfflineActivationPhoneData::InitializeObject(COfflineActivationPhoneStore *)
0x180020e2a  mov     edi, eax
0x180020e2c  test    eax, eax
0x180020e2e  jns     short loc_180020E3C
0x180020e30  mov     ecx, eax
0x180020e32  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020e37  mov     rbx, rsi
0x180020e3a  jmp     short loc_180020E58
0x180020e3c  xor     ebx, ebx
0x180020e3e  mov     [r14], rsi
0x180020e41  jmp     short loc_180020E58
0x180020e43  mov     edi, 8007000Eh
0x180020e48  mov     ecx, edi
0x180020e4a  jmp     short loc_180020E53
0x180020e4c  mov     ecx, 80070057h
0x180020e51  mov     edi, ecx
0x180020e53  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020e58  mov     ecx, edi
0x180020e5a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020e5f  test    rbx, rbx
0x180020e62  jz      short loc_180020E73
0x180020e64  mov     rax, [rbx]
0x180020e67  mov     rcx, rbx
0x180020e6a  mov     rax, [rax+10h]
0x180020e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e73  mov     eax, edi
0x180020e75  add     rsp, 20h
0x180020e79  pop     r14
0x180020e7b  pop     rdi
0x180020e7c  pop     rsi
0x180020e7d  pop     rbp
0x180020e7e  pop     rbx
0x180020e7f  retn
```
