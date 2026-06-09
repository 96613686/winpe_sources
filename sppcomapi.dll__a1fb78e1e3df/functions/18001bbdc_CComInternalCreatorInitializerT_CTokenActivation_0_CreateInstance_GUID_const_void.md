# CComInternalCreatorInitializerT<CTokenActivation,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001bbdc`
- end: `0x18001bd43`
- name: `?CreateInstance@?$CComInternalCreatorInitializerT@VCTokenActivation@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b050`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001bbdc`
- `0x180038f90`
- `0x18003c52a`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bbed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bbed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bc04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bc04`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorInitializerT<CTokenActivation,0>::CreateInstance(__int64 a1, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rax
  unsigned __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0x120u);
  v6 = (unsigned __int64)v5;
  if ( v5 )
  {
    v5[1] = 0;
    v5[2] = 0;
    memset_0(v5 + 3, 0, 0x68u);
    *(_DWORD *)(v6 + 128) = 0;
    *(_QWORD *)(v6 + 144) = 0;
    memset_0((void *)(v6 & -(__int64)(v6 != -152)), 0, 0x118u);
    *(_QWORD *)(v6 + 152) = 0;
    *(_QWORD *)v6 = &CUnknownImplT<CTokenActivation,0>::`vftable'{for `CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>'};
    *(_QWORD *)(v6 + 136) = &CUnknownImplT<CTokenActivation,0>::`vftable'{for `CElevationConfigurable'};
    *(_QWORD *)(v6 + 192) = 0;
    *(_QWORD *)(v6 + 216) = 0;
    *(_QWORD *)(v6 + 224) = 0;
    *(_QWORD *)(v6 + 232) = 0;
    *(_QWORD *)(v6 + 240) = 0;
    *(_QWORD *)(v6 + 256) = 0;
    *(_QWORD *)(v6 + 264) = 0;
    *(_QWORD *)(v6 + 272) = 0;
    *(_DWORD *)(v6 + 280) = 1;
    _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
    v7 = 0;
  }
  else
  {
    v7 = -2147024882;
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
  {
    v8 = v7;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_10;
  }
  v9 = CTokenActivation::InitializeObject((CTokenActivation *)v6);
  v7 = v9;
  if ( v9 < 0
    || (v9 = (**(__int64 (__fastcall ***)(unsigned __int64, __int64, __int64))v6)(v6, a1, a2), v7 = v9, v9 < 0) )
  {
    v8 = (unsigned int)v9;
    goto LABEL_9;
  }
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x18001bbdc  push    rbx
0x18001bbde  push    rbp
0x18001bbdf  push    rsi
0x18001bbe0  push    rdi
0x18001bbe1  push    r14
0x18001bbe3  sub     rsp, 20h
0x18001bbe7  mov     rsi, rdx
0x18001bbea  mov     rbp, rcx
0x18001bbed  call    cs:__imp_GetProcessHeap
0x18001bbf4  nop     dword ptr [rax+rax+00h]
0x18001bbf9  xor     edx, edx; dwFlags
0x18001bbfb  mov     r8d, 120h; dwBytes
0x18001bc01  mov     rcx, rax; hHeap
0x18001bc04  call    cs:__imp_HeapAlloc
0x18001bc0b  nop     dword ptr [rax+rax+00h]
0x18001bc10  xor     r14d, r14d
0x18001bc13  mov     rbx, rax
0x18001bc16  test    rax, rax
0x18001bc19  jz      loc_18001BCCD
0x18001bc1f  lea     rcx, [rax+18h]; void *
0x18001bc23  mov     [rax+8], r14
0x18001bc27  xor     edx, edx; Val
0x18001bc29  mov     [rax+10h], r14
0x18001bc2d  lea     r8d, [r14+68h]; Size
0x18001bc31  call    memset_0
0x18001bc36  lea     rdi, [rbx+98h]
0x18001bc3d  mov     [rbx+80h], r14d
0x18001bc44  mov     rax, rdi
0x18001bc47  mov     [rbx+90h], r14
0x18001bc4e  neg     rax
0x18001bc51  mov     r8d, 118h; Size
0x18001bc57  sbb     rcx, rcx
0x18001bc5a  xor     edx, edx; Val
0x18001bc5c  and     rcx, rbx; void *
0x18001bc5f  call    memset_0
0x18001bc64  lea     rax, ??_7?$CUnknownImplT@VCTokenActivation@@$0A@@@6B?$CDispatchImplT@UITokenActivation@@$1?IID_ITokenActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@@; const CUnknownImplT<CTokenActivation,0>::`vftable'{for `CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>'}
0x18001bc6b  mov     [rdi], r14
0x18001bc6e  mov     [rbx], rax
0x18001bc71  lea     rax, ??_7?$CUnknownImplT@VCTokenActivation@@$0A@@@6BCElevationConfigurable@@@; const CUnknownImplT<CTokenActivation,0>::`vftable'{for `CElevationConfigurable'}
0x18001bc78  mov     [rbx+88h], rax
0x18001bc7f  mov     [rbx+0C0h], r14
0x18001bc86  mov     [rbx+0D8h], r14
0x18001bc8d  mov     [rbx+0E0h], r14
0x18001bc94  mov     [rbx+0E8h], r14
0x18001bc9b  mov     [rbx+0F0h], r14
0x18001bca2  mov     [rbx+100h], r14
0x18001bca9  mov     [rbx+108h], r14
0x18001bcb0  mov     [rbx+110h], r14
0x18001bcb7  mov     dword ptr [rbx+118h], 1
0x18001bcc1  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001bcc8  mov     edi, r14d
0x18001bccb  jmp     short loc_18001BCDC
0x18001bccd  mov     edi, 8007000Eh
0x18001bcd2  mov     rbx, r14
0x18001bcd5  mov     ecx, edi
0x18001bcd7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bcdc  mov     ecx, edi
0x18001bcde  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bce3  test    edi, edi
0x18001bce5  jns     short loc_18001BCEB
0x18001bce7  mov     ecx, edi
0x18001bce9  jmp     short loc_18001BD15
0x18001bceb  mov     rcx, rbx; this
0x18001bcee  call    ?InitializeObject@CTokenActivation@@QEAAJXZ; CTokenActivation::InitializeObject(void)
0x18001bcf3  mov     edi, eax
0x18001bcf5  test    eax, eax
0x18001bcf7  js      short loc_18001BD13
0x18001bcf9  mov     rax, [rbx]
0x18001bcfc  mov     r8, rsi
0x18001bcff  mov     rdx, rbp
0x18001bd02  mov     rcx, rbx
0x18001bd05  mov     rax, [rax]
0x18001bd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd0d  mov     edi, eax
0x18001bd0f  test    eax, eax
0x18001bd11  jns     short loc_18001BD1A
0x18001bd13  mov     ecx, eax
0x18001bd15  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bd1a  mov     ecx, edi
0x18001bd1c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bd21  test    rbx, rbx
0x18001bd24  jz      short loc_18001BD35
0x18001bd26  mov     rax, [rbx]
0x18001bd29  mov     rcx, rbx
0x18001bd2c  mov     rax, [rax+10h]
0x18001bd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd35  mov     eax, edi
0x18001bd37  add     rsp, 20h
0x18001bd3b  pop     r14
0x18001bd3d  pop     rdi
0x18001bd3e  pop     rsi
0x18001bd3f  pop     rbp
0x18001bd40  pop     rbx
0x18001bd41  retn
```
