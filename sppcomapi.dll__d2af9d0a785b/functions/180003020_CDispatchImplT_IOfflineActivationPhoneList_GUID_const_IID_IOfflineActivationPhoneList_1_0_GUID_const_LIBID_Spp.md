# CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(void *)

- ea: `0x180003020`
- end: `0x1800031f3`
- name: `??$AddTypeLib@$00$0A@@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@IEAAJPEAX@Z`
- size: `467`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180019b4c`
- `0x18001b530`
- `0x18001b6cc`
- `0x18001b864`
- `0x18001ba44`
- `0x18001e0a8`
- `0x180020e90`
- `0x180038f90`

## callees

- `0x180003020`
- `0x1800033cc`
- `0x180003520`
- `0x1800038a8`
- `0x180003c18`
- `0x18000405c`
- `0x180004288`
- `0x180004340`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031c8`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180003079`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180003079`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(
        __int64 a1)
{
  ITypeLib *v2; // rbx
  __int64 v3; // r15
  int v4; // r12d
  HRESULT CurrentModuleFileName; // eax
  LPCOLESTR v6; // r14
  unsigned int v7; // edi
  unsigned int v8; // r13d
  ITypeLib *v9; // rax
  bool v10; // zf
  unsigned __int8 v11; // al
  int v12; // r13d
  int v13; // eax
  int v14; // esi
  __int64 v15; // rcx
  HANDLE ProcessHeap; // rax
  ITypeLib *v18; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+28h] [rbp-8h]
  LPCOLESTR szFile; // [rsp+78h] [rbp+48h] BYREF
  ITypeLib *pptlib; // [rsp+80h] [rbp+50h] BYREF
  __int64 v22; // [rsp+88h] [rbp+58h] BYREF

  szFile = 0;
  v2 = 0;
  pptlib = 0;
  v22 = 0;
  v3 = 0;
  v4 = 0;
  CurrentModuleFileName = CComHelpersT<CEmptyType>::GetCurrentModuleFileName(&szFile);
  v6 = szFile;
  v7 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0
    || (CurrentModuleFileName = LoadTypeLib(szFile, &pptlib), v7 = CurrentModuleFileName, CurrentModuleFileName < 0)
    || (CurrentModuleFileName = ((__int64 (__fastcall *)(ITypeLib *, __int64 *))pptlib->lpVtbl->GetLibAttr)(
                                  pptlib,
                                  &v22),
        v7 = CurrentModuleFileName,
        CurrentModuleFileName < 0) )
  {
    v15 = (unsigned int)CurrentModuleFileName;
    goto LABEL_18;
  }
  v8 = *(_DWORD *)(v22 + 16);
  ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->ReleaseTLibAttr)(pptlib);
  v9 = pptlib;
  v3 = a1 + 24;
  v10 = pptlib == 0;
  pptlib = 0;
  v19 = v8;
  if ( !v10 )
    v2 = v9;
  v18 = v2;
  if ( a1 != -24 )
  {
    CRWLock2T<CEmptyType>::AcquireExclusive(a1 + 24);
    v4 = 1;
  }
  LODWORD(szFile) = 0;
  v7 = 0;
  v11 = CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Find(
          a1 + 8,
          v8,
          &szFile);
  v12 = v11;
  if ( !v11 )
  {
    v13 = CArray<CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Insert(
            a1 + 8,
            (unsigned int)szFile,
            &v18);
    v7 = v13;
    if ( v13 < 0 )
    {
      v14 = 0;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
      v2 = v18;
      goto LABEL_13;
    }
    v2 = v18;
  }
  v14 = v12 ^ 1;
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
  {
LABEL_14:
    v15 = v7;
LABEL_18:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
    goto LABEL_19;
  }
  if ( !v14 )
  {
    v7 = -2147418113;
    goto LABEL_14;
  }
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v3 && v4 )
    CRWLock2T<CEmptyType>::ReleaseLockEx(v3);
  if ( v2 )
    ((void (__fastcall *)(ITypeLib *))v2->lpVtbl->Release)(v2);
  if ( pptlib )
  {
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    pptlib = 0;
  }
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x180003020  mov     [rsp-38h+arg_0], rbx
0x180003025  mov     [rsp-38h+szFile], rdx
0x18000302a  push    rbp
0x18000302b  push    rsi
0x18000302c  push    rdi
0x18000302d  push    r12
0x18000302f  push    r13
0x180003031  push    r14
0x180003033  push    r15
0x180003035  mov     rbp, rsp
0x180003038  sub     rsp, 30h
0x18000303c  mov     rsi, rcx
0x18000303f  mov     [rbp+szFile], 0
0x180003047  xor     ebx, ebx
0x180003049  mov     [rbp+pptlib], 0
0x180003051  lea     rcx, [rbp+szFile]
0x180003055  mov     [rbp+arg_18], rbx
0x180003059  xor     r15d, r15d
0x18000305c  xor     r12d, r12d
0x18000305f  call    ?GetCurrentModuleFileName@?$CComHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CComHelpersT<CEmptyType>::GetCurrentModuleFileName(ushort * *)
0x180003064  mov     r14, [rbp+szFile]
0x180003068  mov     edi, eax
0x18000306a  test    eax, eax
0x18000306c  js      loc_18000315D
0x180003072  lea     rdx, [rbp+pptlib]; pptlib
0x180003076  mov     rcx, r14; szFile
0x180003079  call    cs:__imp_LoadTypeLib
0x180003080  nop     dword ptr [rax+rax+00h]
0x180003085  mov     edi, eax
0x180003087  test    eax, eax
0x180003089  js      loc_18000315D
0x18000308f  mov     rcx, [rbp+pptlib]
0x180003093  lea     rdx, [rbp+arg_18]
0x180003097  mov     rax, [rcx]
0x18000309a  mov     rax, [rax+38h]
0x18000309e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a3  mov     edi, eax
0x1800030a5  test    eax, eax
0x1800030a7  js      loc_18000315D
0x1800030ad  mov     rcx, [rbp+pptlib]
0x1800030b1  mov     rdx, [rbp+arg_18]
0x1800030b5  mov     rax, [rcx]
0x1800030b8  mov     r13d, [rdx+10h]
0x1800030bc  mov     rax, [rax+60h]
0x1800030c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c5  mov     rax, [rbp+pptlib]
0x1800030c9  lea     r15, [rsi+18h]
0x1800030cd  test    rax, rax
0x1800030d0  mov     [rbp+pptlib], rbx
0x1800030d4  mov     [rbp+var_8], r13d
0x1800030d8  cmovnz  rbx, rax
0x1800030dc  mov     [rbp+var_10], rbx
0x1800030e0  test    r15, r15
0x1800030e3  jz      short loc_1800030F3
0x1800030e5  mov     rcx, r15
0x1800030e8  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x1800030ed  mov     r12d, 1
0x1800030f3  lea     r8, [rbp+szFile]
0x1800030f7  mov     dword ptr [rbp+szFile], 0
0x1800030fe  mov     edx, r13d
0x180003101  lea     rcx, [rsi+8]
0x180003105  xor     edi, edi
0x180003107  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18000310c  movzx   r13d, al
0x180003110  test    al, al
0x180003112  jnz     short loc_18000313D
0x180003114  mov     edx, dword ptr [rbp+szFile]
0x180003117  lea     r8, [rbp+var_10]
0x18000311b  lea     rcx, [rsi+8]
0x18000311f  call    ?Insert@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHAEBUCTypeInfoItem@?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@@Z; CArray<CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Insert(int,CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem const &)
0x180003124  mov     edi, eax
0x180003126  test    eax, eax
0x180003128  jns     short loc_180003139
0x18000312a  xor     esi, esi
0x18000312c  mov     ecx, eax
0x18000312e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003133  mov     rbx, [rbp+var_10]
0x180003137  jmp     short loc_180003143
0x180003139  mov     rbx, [rbp+var_10]
0x18000313d  mov     esi, r13d
0x180003140  xor     esi, 1
0x180003143  mov     ecx, edi
0x180003145  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000314a  test    edi, edi
0x18000314c  jns     short loc_180003152
0x18000314e  mov     ecx, edi
0x180003150  jmp     short loc_18000315F
0x180003152  test    esi, esi
0x180003154  jnz     short loc_180003164
0x180003156  mov     edi, 8000FFFFh
0x18000315b  jmp     short loc_18000314E
0x18000315d  mov     ecx, eax
0x18000315f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180003164  mov     ecx, edi
0x180003166  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000316b  test    r15, r15
0x18000316e  jz      short loc_18000317D
0x180003170  test    r12d, r12d
0x180003173  jz      short loc_18000317D
0x180003175  mov     rcx, r15
0x180003178  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18000317d  test    rbx, rbx
0x180003180  jz      short loc_180003191
0x180003182  mov     rax, [rbx]
0x180003185  mov     rcx, rbx
0x180003188  mov     rax, [rax+10h]
0x18000318c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003191  mov     rcx, [rbp+pptlib]
0x180003195  test    rcx, rcx
0x180003198  jz      short loc_1800031AE
0x18000319a  mov     rax, [rcx]
0x18000319d  mov     rax, [rax+10h]
0x1800031a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a6  mov     [rbp+pptlib], 0
0x1800031ae  test    r14, r14
0x1800031b1  jz      short loc_1800031DB
0x1800031b3  call    cs:__imp_GetProcessHeap
0x1800031ba  nop     dword ptr [rax+rax+00h]
0x1800031bf  lea     r8, [r14-4]; lpMem
0x1800031c3  xor     edx, edx; dwFlags
0x1800031c5  mov     rcx, rax; hHeap
0x1800031c8  call    cs:__imp_HeapFree
0x1800031cf  nop     dword ptr [rax+rax+00h]
0x1800031d4  xor     ecx, ecx
0x1800031d6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800031db  mov     rbx, [rsp+30h+arg_0]
0x1800031e0  mov     eax, edi
0x1800031e2  add     rsp, 30h
0x1800031e6  pop     r15
0x1800031e8  pop     r14
0x1800031ea  pop     r13
0x1800031ec  pop     r12
0x1800031ee  pop     rdi
0x1800031ef  pop     rsi
0x1800031f0  pop     rbp
0x1800031f1  retn
```
