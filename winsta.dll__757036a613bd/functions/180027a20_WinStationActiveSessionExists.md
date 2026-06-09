# WinStationActiveSessionExists

- ea: `0x180027a20`
- end: `0x180027b2a`
- name: `WinStationActiveSessionExists`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800245b4`
- `0x180027984`
- `0x180027a20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027b0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a62`

## string_xrefs

- `0x180027a53`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationActiveSessionExists(__int64 a1)
{
  char v2; // di
  signed int LastError; // eax
  int v4; // ecx
  DWORD v5; // ecx
  void *v6; // rax
  int active; // ebx
  unsigned __int16 v9[16]; // [rsp+28h] [rbp-20h] BYREF

  v2 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v9, 0, 0);
  if ( !CSmartPublicBinding::operator void *(v9) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError;
    goto LABEL_10;
  }
  if ( !a1 )
  {
    v5 = 87;
LABEL_11:
    SetLastError(v5);
    goto LABEL_12;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetImpl'::`2'::impl);
  v6 = CSmartPublicBinding::operator void *(v9);
  active = RpcActiveSessionExists(v6, a1);
  if ( active < 0 )
  {
    v4 = active;
LABEL_10:
    v5 = ConvertHRESULT2WIN32(v4);
    goto LABEL_11;
  }
  v2 = 1;
LABEL_12:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
  return v2;
}

```

## disassembly

```asm
0x180027a20  mov     [rsp+arg_0], rbx
0x180027a25  push    rdi
0x180027a26  sub     rsp, 40h
0x180027a2a  mov     rbx, rcx
0x180027a2d  xor     dil, dil
0x180027a30  mov     [rsp+48h+arg_8], dil
0x180027a35  xor     r8d, r8d; int
0x180027a38  xor     edx, edx; void *
0x180027a3a  lea     rcx, [rsp+48h+var_20]; this
0x180027a3f  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180027a44  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180027a49  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180027a4e  test    rax, rax
0x180027a51  jnz     short loc_180027A7B
0x180027a53  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180027a5a  lea     ecx, [rax+8]; int
0x180027a5d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027a62  call    cs:__imp_GetLastError
0x180027a68  test    eax, eax
0x180027a6a  jle     short loc_180027A74
0x180027a6c  movzx   eax, ax
0x180027a6f  or      eax, 80070000h
0x180027a74  mov     ecx, eax
0x180027a76  jmp     loc_180027B05
0x180027a7b  test    rbx, rbx
0x180027a7e  jnz     short loc_180027A88
0x180027a80  lea     ecx, [rbx+57h]
0x180027a83  jmp     loc_180027B0C
0x180027a88  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug> `wil::Feature<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetImpl(void)'::`2'::impl
0x180027a8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::__private_IsEnabled(void)
0x180027a94  test    al, al
0x180027a96  jz      short loc_180027AE3
0x180027a98  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180027a9d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180027aa2  mov     rcx, rax
0x180027aa5  mov     rdx, rbx
0x180027aa8  call    RpcActiveSessionExists
0x180027aad  mov     ebx, eax
0x180027aaf  mov     [rsp+48h+var_28], eax
0x180027ab3  jmp     short loc_180027AFA
0x180027ab5  mov     ebx, eax
0x180027ab7  test    eax, eax
0x180027ab9  jle     short loc_180027AC4
0x180027abb  movzx   ebx, ax
0x180027abe  or      ebx, 80070000h
0x180027ac4  mov     [rsp+48h+var_28], ebx
0x180027ac8  mov     r8d, ebx
0x180027acb  lea     rdx, aRpcactivesessi; "RpcActiveSessionExists threw an excepti"...
0x180027ad2  mov     ecx, 8; int
0x180027ad7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027adc  mov     dil, [rsp+48h+arg_8]
0x180027ae1  jmp     short loc_180027AFA
0x180027ae3  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180027ae8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180027aed  mov     rcx, rax
0x180027af0  mov     rdx, rbx
0x180027af3  call    RpcActiveSessionExists
0x180027af8  mov     ebx, eax
0x180027afa  test    ebx, ebx
0x180027afc  js      short loc_180027B03
0x180027afe  mov     dil, 1
0x180027b01  jmp     short loc_180027B12
0x180027b03  mov     ecx, ebx; int
0x180027b05  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180027b0a  mov     ecx, eax; dwErrCode
0x180027b0c  call    cs:__imp_SetLastError
0x180027b12  lea     rcx, [rsp+48h+var_20]; this
0x180027b17  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180027b1c  mov     al, dil
0x180027b1f  mov     rbx, [rsp+48h+arg_0]
0x180027b24  add     rsp, 40h
0x180027b28  pop     rdi
0x180027b29  retn
0x18003082f  push    rbp
0x180030831  sub     rsp, 20h
0x180030835  mov     rbp, rdx
0x180030838  mov     rcx, [rcx]
0x18003083b  mov     ecx, [rcx]; ExceptionCode
0x18003083d  call    cs:__imp_I_RpcExceptionFilter
0x180030843  nop
0x180030844  add     rsp, 20h
0x180030848  pop     rbp
0x180030849  retn
```
