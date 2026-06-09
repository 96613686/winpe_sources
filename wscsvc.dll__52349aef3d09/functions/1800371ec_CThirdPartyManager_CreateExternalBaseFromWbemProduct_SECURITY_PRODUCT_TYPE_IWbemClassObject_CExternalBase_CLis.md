# CThirdPartyManager::CreateExternalBaseFromWbemProduct(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)

- ea: `0x1800371ec`
- end: `0x1800372b1`
- name: `?CreateExternalBaseFromWbemProduct@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(CSecurityVerificationManager **this, unsigned int, __int64 *, CExternalBase **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180037460`
- `0x180038b20`

## callees

- `0x180036adc`
- `0x1800371ec`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180037228`
- `OLEAUT32!__imp_VariantInit` at `0x180037228`
- `OLEAUT32!__imp_VariantClear` at `0x180037297`
- `OLEAUT32!__imp_VariantClear` at `0x180037297`

## string_xrefs

- `0x18003723f`: `pathToSignedReportingExe`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::CreateExternalBaseFromWbemProduct(
        CSecurityVerificationManager **this,
        unsigned int a2,
        __int64 *a3,
        CExternalBase **a4,
        __int64 a5)
{
  int ExternalBaseFromNewStore; // ebx
  VARIANTARG pvarg; // [rsp+40h] [rbp-48h] BYREF

  if ( !a3 || !a4 )
    return 2147942487LL;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  ExternalBaseFromNewStore = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*a3 + 32))(
                               a3,
                               L"pathToSignedReportingExe",
                               0,
                               &pvarg,
                               0,
                               0);
  if ( ExternalBaseFromNewStore >= 0 )
  {
    if ( pvarg.vt == 1 )
      ExternalBaseFromNewStore = -2147418113;
    else
      ExternalBaseFromNewStore = CThirdPartyManager::CreateExternalBaseFromNewStore(this, a2, a3, a4, a5);
  }
  VariantClear(&pvarg);
  return (unsigned int)ExternalBaseFromNewStore;
}

```

## disassembly

```asm
0x1800371ec  push    rbx
0x1800371ee  push    rbp
0x1800371ef  push    rsi
0x1800371f0  push    rdi
0x1800371f1  push    r14
0x1800371f3  sub     rsp, 60h
0x1800371f7  mov     rsi, r9
0x1800371fa  mov     rdi, r8
0x1800371fd  mov     ebp, edx
0x1800371ff  mov     r14, rcx
0x180037202  test    r8, r8
0x180037205  jz      loc_1800372A1
0x18003720b  test    r9, r9
0x18003720e  jz      loc_1800372A1
0x180037214  xorps   xmm0, xmm0
0x180037217  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18003721c  xor     eax, eax
0x18003721e  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180037223  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x180037228  call    cs:__imp_VariantInit
0x18003722e  mov     rax, [rdi]
0x180037231  lea     r9, [rsp+88h+pvarg]
0x180037236  mov     [rsp+88h+var_60], 0
0x18003723f  lea     rdx, aPathtosignedre_0; "pathToSignedReportingExe"
0x180037246  xor     r8d, r8d
0x180037249  mov     [rsp+88h+var_68], 0
0x180037252  mov     rcx, rdi
0x180037255  mov     rax, [rax+20h]
0x180037259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003725e  mov     ebx, eax
0x180037260  test    eax, eax
0x180037262  js      short loc_180037292
0x180037264  cmp     word ptr [rsp+88h+pvarg], 1
0x18003726a  jz      short loc_18003728D
0x18003726c  mov     rax, [rsp+88h+arg_20]
0x180037274  mov     r9, rsi
0x180037277  mov     r8, rdi
0x18003727a  mov     [rsp+88h+var_68], rax; __int64
0x18003727f  mov     edx, ebp; enum _SECURITY_PRODUCT_TYPE
0x180037281  mov     rcx, r14; this
0x180037284  call    ?CreateExternalBaseFromNewStore@CThirdPartyManager@@IEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z; CThirdPartyManager::CreateExternalBaseFromNewStore(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)
0x180037289  mov     ebx, eax
0x18003728b  jmp     short loc_180037292
0x18003728d  mov     ebx, 8000FFFFh
0x180037292  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180037297  call    cs:__imp_VariantClear
0x18003729d  mov     eax, ebx
0x18003729f  jmp     short loc_1800372A6
0x1800372a1  mov     eax, 80070057h
0x1800372a6  add     rsp, 60h
0x1800372aa  pop     r14
0x1800372ac  pop     rdi
0x1800372ad  pop     rsi
0x1800372ae  pop     rbp
0x1800372af  pop     rbx
0x1800372b0  retn
```
