# DllGetClassObject

- ea: `0x18001deb0`
- end: `0x18001df66`
- name: `DllGetClassObject`
- size: `182`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001c1f8`
- `0x18001deb0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001df16`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001df16`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  _QWORD *v7; // rdi
  __int64 (__fastcall *v8)(const IID *const, LPVOID *); // rax
  int v9; // eax
  int v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  if ( !ppv )
  {
    v5 = -2147467261;
LABEL_3:
    v6 = v5;
    goto LABEL_8;
  }
  v7 = CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState;
  if ( !CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(
          (__int64)CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
        + 24,
          rclsid,
          &v11) )
  {
    *ppv = 0;
    v5 = -2147221231;
    goto LABEL_3;
  }
  v8 = (__int64 (__fastcall *)(const IID *const, LPVOID *))DecodePointer(*(PVOID *)(*(_QWORD *)(v7[4] + 8LL * v11) + 24LL));
  v9 = v8(riid, ppv);
  v5 = v9;
  if ( v9 >= 0 )
    goto LABEL_9;
  v6 = (unsigned int)v9;
LABEL_8:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18001deb0  mov     [rsp+arg_0], rbx
0x18001deb5  mov     [rsp+arg_8], rsi
0x18001deba  push    rdi
0x18001debb  sub     rsp, 20h
0x18001debf  mov     [rsp+28h+arg_10], 0
0x18001dec7  mov     rsi, rdx
0x18001deca  mov     rdx, rcx
0x18001decd  mov     rbx, r8
0x18001ded0  test    r8, r8
0x18001ded3  jnz     short loc_18001DEDE
0x18001ded5  mov     ebx, 80004003h
0x18001deda  mov     ecx, ebx
0x18001dedc  jmp     short loc_18001DF35
0x18001dede  mov     rdi, cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x18001dee5  lea     r8, [rsp+28h+arg_10]
0x18001deea  lea     rcx, [rdi+18h]
0x18001deee  call    ?Find@?$CSortedArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NAEBU_GUID@@PEAH@Z; CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(_GUID const &,int *)
0x18001def3  test    al, al
0x18001def5  jnz     short loc_18001DF05
0x18001def7  mov     qword ptr [rbx], 0
0x18001defe  mov     ebx, 80040111h
0x18001df03  jmp     short loc_18001DEDA
0x18001df05  mov     rcx, [rdi+20h]
0x18001df09  movsxd  rax, [rsp+28h+arg_10]
0x18001df0e  mov     rcx, [rcx+rax*8]
0x18001df12  mov     rcx, [rcx+18h]; Ptr
0x18001df16  call    cs:__imp_DecodePointer
0x18001df1d  nop     dword ptr [rax+rax+00h]
0x18001df22  mov     rdx, rbx
0x18001df25  mov     rcx, rsi
0x18001df28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df2d  mov     ebx, eax
0x18001df2f  test    eax, eax
0x18001df31  jns     short loc_18001DF3A
0x18001df33  mov     ecx, eax
0x18001df35  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001df3a  mov     ecx, ebx
0x18001df3c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001df41  test    ebx, ebx
0x18001df43  jns     short loc_18001DF4C
0x18001df45  mov     ecx, ebx
0x18001df47  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001df4c  mov     ecx, ebx
0x18001df4e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001df53  mov     rsi, [rsp+28h+arg_8]
0x18001df58  mov     eax, ebx
0x18001df5a  mov     rbx, [rsp+28h+arg_0]
0x18001df5f  add     rsp, 20h
0x18001df63  pop     rdi
0x18001df64  retn
```
