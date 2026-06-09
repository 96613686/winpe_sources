# DontEnumerateForLogon(IPropertyStore *)

- ea: `0x18000b410`
- end: `0x18000b591`
- name: `?DontEnumerateForLogon@@YA_NPEAUIPropertyStore@@@Z`
- size: `385`
- prototype: `bool __fastcall(struct IPropertyStore *)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003e20`
- `0x1800063b0`
- `0x180007070`
- `0x18000ed10`

## callees

- `0x18000a3c0`
- `0x18000b410`
- `0x18000c240`
- `0x1800109d8`
- `0x180010a3c`
- `0x180010b88`
- `0x180016880`
- `0x180017010`

## import_xrefs

- `PROPSYS!PropVariantToBoolean` at `0x18000b47f`
- `PROPSYS!PropVariantToBoolean` at `0x18000b47f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b50b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b48a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b48a`

## pseudocode

```c
bool __fastcall DontEnumerateForLogon(struct IPropertyStore *a1)
{
  struct IPropertyStoreVtbl *lpVtbl; // rax
  bool v4; // [rsp+20h] [rbp-E0h] BYREF
  BOOL pfRet; // [rsp+24h] [rbp-DCh] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v8; // [rsp+40h] [rbp-C0h]
  _WORD v9[1032]; // [rsp+50h] [rbp-B0h] BYREF

  pfRet = 0;
  v8 = 0;
  lpVtbl = a1->lpVtbl;
  *(_OWORD *)propvarIn = 0;
  if ( ((int (__fastcall *)(struct IPropertyStore *, __int128 *, PROPVARIANT *))lpVtbl->GetValue)(
         a1,
         &PKEY_SAM_DontShowInLogonUI,
         propvarIn) >= 0 )
  {
    if ( LOWORD(propvarIn[0]) )
      PropVariantToBoolean(propvarIn, &pfRet);
    PropVariantClear(propvarIn);
  }
  if ( pfRet )
    return 1;
  pfRet = 0;
  if ( (int)IPropertyStore_GetUInt32(a1, &PKEY_LOGON_Status, &pfRet) >= 0 )
    return (pfRet & 0xFFFFFFFB) != 0;
  if ( !IsUserAllowedLogon(a1) )
    return 1;
  pv = 0;
  if ( (int)IPropertyStore_GetString(a1, &PKEY_SAM_FullName, &pv) < 0 )
    return 1;
  CoTaskMemFree(pv);
  v9[0] = 0;
  v9[257] = 0;
  v9[514] = 0;
  v9[771] = 0;
  CKnownGroups::Init((CKnownGroups *)v9);
  v4 = 0;
  return (int)CKnownGroups::IsUserInAnyKnownGroup((CKnownGroups *)v9, a1, &v4) >= 0 && !v4;
}

```

## disassembly

```asm
0x18000b410  mov     [rsp-8+arg_10], rbx
0x18000b415  push    rbp
0x18000b416  lea     rbp, [rsp-770h]
0x18000b41e  sub     rsp, 870h
0x18000b425  mov     rax, cs:__security_cookie
0x18000b42c  xor     rax, rsp
0x18000b42f  mov     [rbp+770h+var_10], rax
0x18000b436  xor     eax, eax
0x18000b438  mov     [rsp+870h+pfRet], 0
0x18000b440  mov     [rsp+870h+var_830], rax
0x18000b445  lea     r8, [rsp+870h+propvarIn]
0x18000b44a  mov     rax, [rcx]
0x18000b44d  lea     rdx, PKEY_SAM_DontShowInLogonUI
0x18000b454  xorps   xmm0, xmm0
0x18000b457  mov     rbx, rcx
0x18000b45a  movups  xmmword ptr [rsp+870h+propvarIn], xmm0
0x18000b45f  mov     rax, [rax+28h]
0x18000b463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b468  test    eax, eax
0x18000b46a  js      short loc_18000B490
0x18000b46c  xor     eax, eax
0x18000b46e  cmp     ax, word ptr [rsp+870h+propvarIn]
0x18000b473  jz      short loc_18000B485
0x18000b475  lea     rdx, [rsp+870h+pfRet]; pfRet
0x18000b47a  lea     rcx, [rsp+870h+propvarIn]; propvarIn
0x18000b47f  call    cs:__imp_PropVariantToBoolean
0x18000b485  lea     rcx, [rsp+870h+propvarIn]; pvar
0x18000b48a  call    cs:__imp_PropVariantClear
0x18000b490  cmp     [rsp+870h+pfRet], 0
0x18000b495  jnz     short loc_18000B4D3
0x18000b497  lea     r8, [rsp+870h+pfRet]
0x18000b49c  mov     [rsp+870h+pfRet], 0
0x18000b4a4  lea     rdx, PKEY_LOGON_Status
0x18000b4ab  mov     rcx, rbx
0x18000b4ae  call    IPropertyStore_GetUInt32
0x18000b4b3  test    eax, eax
0x18000b4b5  js      short loc_18000B4C7
0x18000b4b7  test    [rsp+870h+pfRet], 0FFFFFFFBh
0x18000b4bf  setnz   al
0x18000b4c2  jmp     loc_18000B571
0x18000b4c7  mov     rcx, rbx; struct IPropertyStore *
0x18000b4ca  call    ?IsUserAllowedLogon@@YA_NPEAUIPropertyStore@@@Z; IsUserAllowedLogon(IPropertyStore *)
0x18000b4cf  test    al, al
0x18000b4d1  jnz     short loc_18000B4DA
0x18000b4d3  mov     al, 1
0x18000b4d5  jmp     loc_18000B571
0x18000b4da  lea     r8, [rsp+870h+pv]
0x18000b4df  mov     [rsp+870h+pv], 0
0x18000b4e8  lea     rdx, PKEY_SAM_FullName
0x18000b4ef  mov     rcx, rbx
0x18000b4f2  call    IPropertyStore_GetString
0x18000b4f7  test    eax, eax
0x18000b4f9  js      short loc_18000B4D3
0x18000b4fb  mov     rcx, [rsp+870h+pv]; pv
0x18000b500  mov     [rsp+870h+arg_8], rsi
0x18000b508  xor     sil, sil
0x18000b50b  call    cs:__imp_CoTaskMemFree
0x18000b511  xor     eax, eax
0x18000b513  lea     rcx, [rsp+870h+var_820]; this
0x18000b518  mov     [rsp+870h+var_820], ax
0x18000b51d  mov     [rbp+770h+var_61E], ax
0x18000b524  mov     [rbp+770h+var_41C], ax
0x18000b52b  mov     [rbp+770h+var_21A], ax
0x18000b532  call    ?Init@CKnownGroups@@QEAAJXZ; CKnownGroups::Init(void)
0x18000b537  lea     r8, [rsp+870h+var_850]; bool *
0x18000b53c  mov     [rsp+870h+var_850], sil
0x18000b541  mov     rdx, rbx; struct IPropertyStore *
0x18000b544  lea     rcx, [rsp+870h+var_820]; this
0x18000b549  call    ?IsUserInAnyKnownGroup@CKnownGroups@@QEBAJPEAUIPropertyStore@@PEA_N@Z; CKnownGroups::IsUserInAnyKnownGroup(IPropertyStore *,bool *)
0x18000b54e  test    eax, eax
0x18000b550  js      short loc_18000B565
0x18000b552  cmp     [rsp+870h+var_850], sil
0x18000b557  mov     ecx, 1
0x18000b55c  movzx   eax, sil
0x18000b560  cmovz   eax, ecx
0x18000b563  jmp     short loc_18000B569
0x18000b565  movzx   eax, sil
0x18000b569  mov     rsi, [rsp+870h+arg_8]
0x18000b571  mov     rcx, [rbp+770h+var_10]
0x18000b578  xor     rcx, rsp; StackCookie
0x18000b57b  call    __security_check_cookie
0x18000b580  mov     rbx, [rsp+870h+arg_10]
0x18000b588  add     rsp, 870h
0x18000b58f  pop     rbp
0x18000b590  retn
```
