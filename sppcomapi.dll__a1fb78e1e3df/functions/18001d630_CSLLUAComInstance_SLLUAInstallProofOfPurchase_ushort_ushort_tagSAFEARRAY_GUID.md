# CSLLUAComInstance::SLLUAInstallProofOfPurchase(ushort *,ushort *,tagSAFEARRAY *,_GUID *)

- ea: `0x18001d630`
- end: `0x18001d737`
- name: `?SLLUAInstallProofOfPurchase@CSLLUAComInstance@@UEAAJPEAG0PEAUtagSAFEARRAY@@PEAU_GUID@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(CSLLUAComInstance *this, unsigned __int16 *, unsigned __int16 *, struct tagSAFEARRAY *, struct _GUID *pPkeyId)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001c0b0`
- `0x18001d630`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d6f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d6f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d706`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d706`
- `SLC!SLInstallProofOfPurchase` at `0x18001d6cd`
- `SLC!SLInstallProofOfPurchase` at `0x18001d6cd`
- `SLC!SLOpen` at `0x18001d69f`
- `SLC!SLOpen` at `0x18001d69f`
- `SLC!SLClose` at `0x18001d71b`
- `SLC!SLClose` at `0x18001d71b`

## pseudocode

```c
__int64 __fastcall CSLLUAComInstance::SLLUAInstallProofOfPurchase(
        CSLLUAComInstance *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct tagSAFEARRAY *a4,
        struct _GUID *pPkeyId)
{
  __int64 v7; // rcx
  unsigned int v8; // ebx
  HRESULT v9; // eax
  HRESULT v10; // eax
  HSLC phSLC; // [rsp+38h] [rbp-10h] BYREF

  phSLC = 0;
  if ( !a2 || !a3 || !a4 || !pPkeyId )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_12;
  }
  v9 = CSafeArrayHelperT<CEmptyType>::ExtractFromSafeArray(a4);
  v8 = v9;
  if ( v9 < 0 || (v9 = SLOpen(&phSLC), v8 = v9, v9 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    goto LABEL_12;
  }
  v10 = SLInstallProofOfPurchase(phSLC, a2, a3, 0, 0, pPkeyId);
  v8 = v10;
  if ( v10 < 0 )
  {
    v7 = (unsigned int)v10;
    goto LABEL_11;
  }
LABEL_12:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( phSLC )
    SLClose(phSLC);
  return v8;
}

```

## disassembly

```asm
0x18001d630  push    rbp
0x18001d632  push    rbx
0x18001d633  push    rsi
0x18001d634  push    rdi
0x18001d635  push    r14
0x18001d637  push    r15
0x18001d639  mov     rbp, rsp
0x18001d63c  sub     rsp, 48h
0x18001d640  xor     edi, edi
0x18001d642  mov     [rbp+phSLC], 0
0x18001d64a  mov     [rbp+var_18], rdi
0x18001d64e  mov     r14, r8
0x18001d651  mov     [rbp+cbPKeySpecificData], edi
0x18001d654  mov     r15, rdx
0x18001d657  test    rdx, rdx
0x18001d65a  jnz     short loc_18001D665
0x18001d65c  mov     ecx, 80070057h
0x18001d661  mov     ebx, ecx
0x18001d663  jmp     short loc_18001D6E1
0x18001d665  test    r14, r14
0x18001d668  jz      short loc_18001D65C
0x18001d66a  test    r9, r9
0x18001d66d  jz      short loc_18001D65C
0x18001d66f  mov     rsi, [rbp+arg_20]
0x18001d673  test    rsi, rsi
0x18001d676  jz      short loc_18001D65C
0x18001d678  lea     r8, [rbp+cbPKeySpecificData]
0x18001d67c  mov     rcx, r9; psa
0x18001d67f  lea     rdx, [rbp+var_18]
0x18001d683  call    ?ExtractFromSafeArray@?$CSafeArrayHelperT@VCEmptyType@@@@SAJPEAUtagSAFEARRAY@@PEAPEAEPEAK@Z; CSafeArrayHelperT<CEmptyType>::ExtractFromSafeArray(tagSAFEARRAY *,uchar * *,ulong *)
0x18001d688  mov     ebx, eax
0x18001d68a  test    eax, eax
0x18001d68c  jns     short loc_18001D69B
0x18001d68e  mov     ecx, eax
0x18001d690  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d695  mov     rdi, [rbp+var_18]
0x18001d699  jmp     short loc_18001D6E6
0x18001d69b  lea     rcx, [rbp+phSLC]; phSLC
0x18001d69f  call    cs:__imp_SLOpen
0x18001d6a6  nop     dword ptr [rax+rax+00h]
0x18001d6ab  mov     ebx, eax
0x18001d6ad  test    eax, eax
0x18001d6af  js      short loc_18001D68E
0x18001d6b1  mov     rdi, [rbp+var_18]
0x18001d6b5  mov     r8, r14; pwszPKeyString
0x18001d6b8  mov     r9d, [rbp+cbPKeySpecificData]; cbPKeySpecificData
0x18001d6bc  mov     rdx, r15; pwszPKeyAlgorithm
0x18001d6bf  mov     rcx, [rbp+phSLC]; hSLC
0x18001d6c3  mov     [rsp+48h+pPkeyId], rsi; pPkeyId
0x18001d6c8  mov     [rsp+48h+pbPKeySpecificData], rdi; pbPKeySpecificData
0x18001d6cd  call    cs:__imp_SLInstallProofOfPurchase
0x18001d6d4  nop     dword ptr [rax+rax+00h]
0x18001d6d9  mov     ebx, eax
0x18001d6db  test    eax, eax
0x18001d6dd  jns     short loc_18001D6E6
0x18001d6df  mov     ecx, eax
0x18001d6e1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d6e6  mov     ecx, ebx
0x18001d6e8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d6ed  test    rdi, rdi
0x18001d6f0  jz      short loc_18001D712
0x18001d6f2  call    cs:__imp_GetProcessHeap
0x18001d6f9  nop     dword ptr [rax+rax+00h]
0x18001d6fe  mov     r8, rdi; lpMem
0x18001d701  xor     edx, edx; dwFlags
0x18001d703  mov     rcx, rax; hHeap
0x18001d706  call    cs:__imp_HeapFree
0x18001d70d  nop     dword ptr [rax+rax+00h]
0x18001d712  mov     rcx, [rbp+phSLC]; hSLC
0x18001d716  test    rcx, rcx
0x18001d719  jz      short loc_18001D727
0x18001d71b  call    cs:__imp_SLClose
0x18001d722  nop     dword ptr [rax+rax+00h]
0x18001d727  mov     eax, ebx
0x18001d729  add     rsp, 48h
0x18001d72d  pop     r15
0x18001d72f  pop     r14
0x18001d731  pop     rdi
0x18001d732  pop     rsi
0x18001d733  pop     rbx
0x18001d734  pop     rbp
0x18001d735  retn
```
