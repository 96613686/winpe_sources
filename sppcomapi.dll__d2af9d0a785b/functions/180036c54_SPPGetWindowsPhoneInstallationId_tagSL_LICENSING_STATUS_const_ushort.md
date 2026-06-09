# SPPGetWindowsPhoneInstallationId(_tagSL_LICENSING_STATUS const *,ushort * *)

- ea: `0x180036c54`
- end: `0x180036d5c`
- name: `?SPPGetWindowsPhoneInstallationId@@YAJPEBU_tagSL_LICENSING_STATUS@@PEAPEAG@Z`
- size: `264`
- prototype: `__int64 __fastcall(SLID *pProductSkuId, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180020b70`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x180036c54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d12`
- `SLC!SLGenerateOfflineInstallationId` at `0x180036c9e`
- `SLC!SLGenerateOfflineInstallationId` at `0x180036c9e`
- `SLC!SLOpen` at `0x180036c7d`
- `SLC!SLOpen` at `0x180036c7d`
- `SLC!SLClose` at `0x180036cf5`
- `SLC!SLClose` at `0x180036cf5`

## pseudocode

```c
__int64 __fastcall SPPGetWindowsPhoneInstallationId(SLID *pProductSkuId, unsigned __int16 **a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  PWSTR v6; // rdi
  int StringCch; // eax
  PWSTR ppwszInstallationId; // [rsp+20h] [rbp-10h] BYREF
  int v10; // [rsp+60h] [rbp+30h] BYREF
  HSLC phSLC; // [rsp+68h] [rbp+38h] BYREF

  ppwszInstallationId = 0;
  phSLC = 0;
  v3 = SLOpen(&phSLC);
  v4 = v3;
  if ( v3 < 0 || (v3 = SLGenerateOfflineInstallationId(phSLC, pProductSkuId, &ppwszInstallationId), v4 = v3, v3 < 0) )
  {
    v5 = (unsigned int)v3;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_10;
  }
  v6 = ppwszInstallationId;
  if ( ppwszInstallationId
    && (v10 = 0,
        StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(ppwszInstallationId, &v10),
        v4 = StringCch,
        StringCch < 0)
    || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v6),
        v4 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
  {
    v5 = v4;
    goto LABEL_9;
  }
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( phSLC )
  {
    SLClose(phSLC);
    phSLC = 0;
  }
  if ( ppwszInstallationId )
    LocalFree(ppwszInstallationId);
  return v4;
}

```

## disassembly

```asm
0x180036c54  mov     [rsp-18h+arg_0], rbx
0x180036c59  push    rbp
0x180036c5a  push    rsi
0x180036c5b  push    rdi
0x180036c5c  mov     rbp, rsp
0x180036c5f  sub     rsp, 30h
0x180036c63  mov     rdi, rcx
0x180036c66  mov     [rbp+ppwszInstallationId], 0
0x180036c6e  lea     rcx, [rbp+phSLC]; phSLC
0x180036c72  mov     [rbp+phSLC], 0
0x180036c7a  mov     rsi, rdx
0x180036c7d  call    cs:__imp_SLOpen
0x180036c84  nop     dword ptr [rax+rax+00h]
0x180036c89  mov     ebx, eax
0x180036c8b  test    eax, eax
0x180036c8d  jns     short loc_180036C93
0x180036c8f  mov     ecx, eax
0x180036c91  jmp     short loc_180036CE0
0x180036c93  mov     rcx, [rbp+phSLC]; hSLC
0x180036c97  lea     r8, [rbp+ppwszInstallationId]; ppwszInstallationId
0x180036c9b  mov     rdx, rdi; pProductSkuId
0x180036c9e  call    cs:__imp_SLGenerateOfflineInstallationId
0x180036ca5  nop     dword ptr [rax+rax+00h]
0x180036caa  mov     ebx, eax
0x180036cac  test    eax, eax
0x180036cae  js      short loc_180036C8F
0x180036cb0  mov     rdi, [rbp+ppwszInstallationId]
0x180036cb4  test    rdi, rdi
0x180036cb7  jnz     short loc_180036D2E
0x180036cb9  xor     edx, edx
0x180036cbb  mov     r8, rsi
0x180036cbe  mov     rcx, rdi; Src
0x180036cc1  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180036cc6  mov     ebx, eax
0x180036cc8  test    eax, eax
0x180036cca  jns     short loc_180036CD3
0x180036ccc  mov     ecx, eax
0x180036cce  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180036cd3  mov     ecx, ebx
0x180036cd5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180036cda  test    ebx, ebx
0x180036cdc  jns     short loc_180036CE5
0x180036cde  mov     ecx, ebx
0x180036ce0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180036ce5  mov     ecx, ebx
0x180036ce7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180036cec  mov     rcx, [rbp+phSLC]; hSLC
0x180036cf0  test    rcx, rcx
0x180036cf3  jz      short loc_180036D09
0x180036cf5  call    cs:__imp_SLClose
0x180036cfc  nop     dword ptr [rax+rax+00h]
0x180036d01  mov     [rbp+phSLC], 0
0x180036d09  mov     rcx, [rbp+ppwszInstallationId]; hMem
0x180036d0d  test    rcx, rcx
0x180036d10  jz      short loc_180036D1E
0x180036d12  call    cs:__imp_LocalFree
0x180036d19  nop     dword ptr [rax+rax+00h]
0x180036d1e  mov     eax, ebx
0x180036d20  mov     rbx, [rsp+30h+arg_0]
0x180036d25  add     rsp, 30h
0x180036d29  pop     rdi
0x180036d2a  pop     rsi
0x180036d2b  pop     rbp
0x180036d2c  retn
0x180036d2e  mov     [rbp+arg_10], 0
0x180036d35  test    rdi, rdi
0x180036d38  jz      loc_180036CB9
0x180036d3e  lea     rdx, [rbp+arg_10]
0x180036d42  mov     rcx, rdi
0x180036d45  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180036d4a  mov     ebx, eax
0x180036d4c  test    eax, eax
0x180036d4e  js      loc_180036CCC
0x180036d54  mov     edx, [rbp+arg_10]
0x180036d57  jmp     loc_180036CBB
```
