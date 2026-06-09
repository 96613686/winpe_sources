# Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>(void)

- ea: `0x18006fdd8`
- end: `0x180070083`
- name: `??$InitializeSecurity@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006fb50`

## callees

- `0x1800088e8`
- `0x180061e1c`
- `0x18006fdd8`
- `0x180070e2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180070034`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180070034`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18006feab`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18006fffc`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18006feab`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18006fffc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fede`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff6e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fede`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff6e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006fecb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006fecb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ff8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006feb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006feb9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006fe57`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006fe57`

## string_xrefs

- `0x18006fefe`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18007005a`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>(
        __int64 a1)
{
  const char *v1; // r9
  __int64 v2; // rdx
  DWORD v3; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  __int64 v7; // r9
  DWORD v8; // ebx
  HANDLE v9; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  DWORD v12; // ebx
  HANDLE v13; // rax
  DWORD v14; // ebx
  HANDLE v15; // rax
  void *pPrimaryGroup; // rax
  HRESULT v17; // eax
  int lpdwDaclSize; // [rsp+20h] [rbp-79h]
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+70h] [rbp-29h] BYREF
  PSID pOwner; // [rsp+78h] [rbp-21h] BYREF
  PACL pSacl; // [rsp+80h] [rbp-19h] BYREF
  PACL pDacl; // [rsp+88h] [rbp-11h] BYREF
  void *v26; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v27[6]; // [rsp+98h] [rbp-1h] BYREF
  char v28; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  DWORD dwPrimaryGroupSize; // [rsp+100h] [rbp+67h] BYREF
  int v31; // [rsp+104h] [rbp+6Bh]
  DWORD dwOwnerSize; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD dwSaclSize; // [rsp+110h] [rbp+77h] BYREF
  DWORD dwDaclSize; // [rsp+118h] [rbp+7Fh] BYREF

  v31 = HIDWORD(a1);
  v27[0] = &pDacl;
  pDacl = 0;
  v27[1] = &pSacl;
  pSacl = 0;
  v27[2] = &pOwner;
  pOwner = 0;
  v27[3] = &v26;
  v26 = 0;
  v27[4] = &pAbsoluteSecurityDescriptor;
  v27[5] = &SecurityDescriptor;
  SecurityDescriptor = 0;
  pAbsoluteSecurityDescriptor = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:PSG:BUD:(A;;0x1F;;;AC)(A;;0x1F;;;WD)S:(ML;;NX;;;LW)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    v2 = 304;
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v2,
                  (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
                  v1);
    goto LABEL_24;
  }
  if ( MakeAbsoluteSD(
         SecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize)
    || GetLastError() != 122 )
  {
    v2 = 308;
    goto LABEL_23;
  }
  v3 = dwAbsoluteSecurityDescriptorSize;
  ProcessHeap = GetProcessHeap();
  pAbsoluteSecurityDescriptor = HeapAlloc(ProcessHeap, 8u, v3);
  if ( !pAbsoluteSecurityDescriptor )
  {
    v5 = 312;
LABEL_7:
    LastError = -2147024882;
    v7 = 2147942414LL;
    goto LABEL_8;
  }
  v8 = dwDaclSize;
  v9 = GetProcessHeap();
  pDacl = (PACL)HeapAlloc(v9, 8u, v8);
  if ( !pDacl )
  {
    v5 = 315;
    goto LABEL_7;
  }
  v10 = dwSaclSize;
  v11 = GetProcessHeap();
  pSacl = (PACL)HeapAlloc(v11, 8u, v10);
  if ( !pSacl )
  {
    v5 = 318;
    goto LABEL_7;
  }
  v12 = dwOwnerSize;
  v13 = GetProcessHeap();
  pOwner = HeapAlloc(v13, 8u, v12);
  if ( !pOwner )
  {
    v5 = 321;
    goto LABEL_7;
  }
  v14 = dwPrimaryGroupSize;
  v15 = GetProcessHeap();
  pPrimaryGroup = HeapAlloc(v15, 8u, v14);
  v26 = pPrimaryGroup;
  if ( !pPrimaryGroup )
  {
    v5 = 324;
    goto LABEL_7;
  }
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          pAbsoluteSecurityDescriptor,
          &dwAbsoluteSecurityDescriptorSize,
          pDacl,
          &dwDaclSize,
          pSacl,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    v2 = 327;
    goto LABEL_23;
  }
  v17 = CoInitializeSecurity(pAbsoluteSecurityDescriptor, -1, 0, 0, 0, 2u, 0, 0, 0);
  LastError = v17;
  if ( v17 >= 0 )
  {
    LastError = 0;
    goto LABEL_24;
  }
  v7 = (unsigned int)v17;
  v5 = 330;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)v7,
    lpdwDaclSize);
LABEL_24:
  v28 = 0;
  _lambda_bed1b5be4148163977e87fd2fb1bced4_::operator()(v27);
  return LastError;
}

```

## disassembly

```asm
0x18006fdd8  mov     qword ptr [rsp-8+dwPrimaryGroupSize], rcx
0x18006fddd  push    rbp
0x18006fdde  push    rbx
0x18006fddf  push    rsi
0x18006fde0  push    rdi
0x18006fde1  lea     rbp, [rsp-3Fh]
0x18006fde6  sub     rsp, 0D8h
0x18006fded  xor     edi, edi
0x18006fdef  lea     rax, [rbp+57h+pDacl]
0x18006fdf3  mov     [rbp+57h+var_58], rax
0x18006fdf7  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006fdfb  lea     rax, [rbp+57h+var_70]
0x18006fdff  mov     [rbp+57h+pDacl], rdi
0x18006fe03  mov     [rbp+57h+var_50], rax
0x18006fe07  lea     rcx, StringSecurityDescriptor; "O:PSG:BUD:(A;;0x1F;;;AC)(A;;0x1F;;;WD)S"...
0x18006fe0e  lea     rax, [rbp+57h+var_78]
0x18006fe12  mov     [rbp+57h+var_70], rdi
0x18006fe16  mov     [rbp+57h+var_48], rax
0x18006fe1a  lea     edx, [rdi+1]; StringSDRevision
0x18006fe1d  lea     rax, [rbp+57h+var_60]
0x18006fe21  mov     [rbp+57h+var_78], rdi
0x18006fe25  mov     [rbp+57h+var_40], rax
0x18006fe29  xor     r9d, r9d; SecurityDescriptorSize
0x18006fe2c  lea     rax, [rbp+57h+pAbsoluteSecurityDescriptor]
0x18006fe30  mov     [rbp+57h+var_60], rdi
0x18006fe34  mov     [rbp+57h+var_38], rax
0x18006fe38  lea     rax, [rbp+57h+SecurityDescriptor]
0x18006fe3c  mov     [rbp+57h+var_30], rax
0x18006fe40  mov     [rbp+57h+SecurityDescriptor], rdi
0x18006fe44  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x18006fe48  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x18006fe4b  mov     [rbp+57h+dwDaclSize], edi
0x18006fe4e  mov     [rbp+57h+dwSaclSize], edi
0x18006fe51  mov     [rbp+57h+dwOwnerSize], edi
0x18006fe54  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x18006fe57  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006fe5d  test    eax, eax
0x18006fe5f  jnz     short loc_18006FE6B
0x18006fe61  mov     edx, 130h
0x18006fe66  jmp     loc_180070056
0x18006fe6b  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18006fe6f  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18006fe73  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18006fe78  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18006fe7c  mov     [rsp+0F0h+pPrimaryGroup], rdi; pPrimaryGroup
0x18006fe81  lea     rax, [rbp+57h+dwOwnerSize]
0x18006fe85  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18006fe8a  xor     r9d, r9d; pDacl
0x18006fe8d  mov     [rsp+0F0h+pOwner], rdi; pOwner
0x18006fe92  lea     rax, [rbp+57h+dwSaclSize]
0x18006fe96  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18006fe9b  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18006fe9d  lea     rax, [rbp+57h+dwDaclSize]
0x18006fea1  mov     [rsp+0F0h+pSacl], rdi; pSacl
0x18006fea6  mov     [rsp+0F0h+lpdwDaclSize], rax; int
0x18006feab  call    cs:__imp_MakeAbsoluteSD
0x18006feb1  test    eax, eax
0x18006feb3  jnz     loc_180070051
0x18006feb9  call    cs:__imp_GetLastError
0x18006febf  cmp     eax, 7Ah ; 'z'
0x18006fec2  jnz     loc_180070051
0x18006fec8  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x18006fecb  call    cs:__imp_GetProcessHeap
0x18006fed1  mov     esi, 8
0x18006fed6  mov     r8d, ebx; dwBytes
0x18006fed9  mov     edx, esi; dwFlags
0x18006fedb  mov     rcx, rax; hHeap
0x18006fede  call    cs:__imp_HeapAlloc
0x18006fee4  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rax
0x18006fee8  test    rax, rax
0x18006feeb  jnz     short loc_18006FF0F
0x18006feed  mov     edx, 138h; void *
0x18006fef2  mov     ebx, 8007000Eh
0x18006fef7  mov     r9d, ebx; char *
0x18006fefa  mov     rcx, [rbp+5Fh]; this
0x18006fefe  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x18006ff05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ff0a  jmp     loc_180070068
0x18006ff0f  mov     ebx, [rbp+57h+dwDaclSize]
0x18006ff12  call    cs:__imp_GetProcessHeap
0x18006ff18  mov     r8d, ebx; dwBytes
0x18006ff1b  mov     edx, esi; dwFlags
0x18006ff1d  mov     rcx, rax; hHeap
0x18006ff20  call    cs:__imp_HeapAlloc
0x18006ff26  mov     [rbp+57h+pDacl], rax
0x18006ff2a  test    rax, rax
0x18006ff2d  jnz     short loc_18006FF36
0x18006ff2f  mov     edx, 13Bh
0x18006ff34  jmp     short loc_18006FEF2
0x18006ff36  mov     ebx, [rbp+57h+dwSaclSize]
0x18006ff39  call    cs:__imp_GetProcessHeap
0x18006ff3f  mov     r8d, ebx; dwBytes
0x18006ff42  mov     edx, esi; dwFlags
0x18006ff44  mov     rcx, rax; hHeap
0x18006ff47  call    cs:__imp_HeapAlloc
0x18006ff4d  mov     [rbp+57h+var_70], rax
0x18006ff51  test    rax, rax
0x18006ff54  jnz     short loc_18006FF5D
0x18006ff56  mov     edx, 13Eh
0x18006ff5b  jmp     short loc_18006FEF2
0x18006ff5d  mov     ebx, [rbp+57h+dwOwnerSize]
0x18006ff60  call    cs:__imp_GetProcessHeap
0x18006ff66  mov     r8d, ebx; dwBytes
0x18006ff69  mov     edx, esi; dwFlags
0x18006ff6b  mov     rcx, rax; hHeap
0x18006ff6e  call    cs:__imp_HeapAlloc
0x18006ff74  mov     [rbp+57h+var_78], rax
0x18006ff78  test    rax, rax
0x18006ff7b  jnz     short loc_18006FF87
0x18006ff7d  mov     edx, 141h
0x18006ff82  jmp     loc_18006FEF2
0x18006ff87  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x18006ff8a  call    cs:__imp_GetProcessHeap
0x18006ff90  mov     r8d, ebx; dwBytes
0x18006ff93  mov     edx, esi; dwFlags
0x18006ff95  mov     rcx, rax; hHeap
0x18006ff98  call    cs:__imp_HeapAlloc
0x18006ff9e  mov     [rbp+57h+var_60], rax
0x18006ffa2  test    rax, rax
0x18006ffa5  jnz     short loc_18006FFB1
0x18006ffa7  mov     edx, 144h
0x18006ffac  jmp     loc_18006FEF2
0x18006ffb1  mov     r9, [rbp+57h+pDacl]; pDacl
0x18006ffb5  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x18006ffb9  mov     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18006ffbd  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18006ffc1  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x18006ffc6  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18006ffca  mov     [rsp+0F0h+pPrimaryGroup], rax; pPrimaryGroup
0x18006ffcf  lea     rax, [rbp+57h+dwOwnerSize]
0x18006ffd3  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18006ffd8  mov     rax, [rbp+57h+var_78]
0x18006ffdc  mov     [rsp+0F0h+pOwner], rax; pOwner
0x18006ffe1  lea     rax, [rbp+57h+dwSaclSize]
0x18006ffe5  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18006ffea  mov     rax, [rbp+57h+var_70]
0x18006ffee  mov     [rsp+0F0h+pSacl], rax; pSacl
0x18006fff3  lea     rax, [rbp+57h+dwDaclSize]
0x18006fff7  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x18006fffc  call    cs:__imp_MakeAbsoluteSD
0x180070002  test    eax, eax
0x180070004  jnz     short loc_18007000D
0x180070006  mov     edx, 147h
0x18007000b  jmp     short loc_180070056
0x18007000d  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecDesc
0x180070011  xor     r9d, r9d; pReserved1
0x180070014  mov     [rsp+0F0h+lpdwOwnerSize], rdi; pReserved3
0x180070019  xor     r8d, r8d; asAuthSvc
0x18007001c  mov     dword ptr [rsp+0F0h+pOwner], edi; dwCapabilities
0x180070020  or      edx, 0FFFFFFFFh; cAuthSvc
0x180070023  mov     [rsp+0F0h+lpdwSaclSize], rdi; pAuthList
0x180070028  mov     dword ptr [rsp+0F0h+pSacl], 2; dwImpLevel
0x180070030  mov     dword ptr [rsp+0F0h+lpdwDaclSize], edi; dwAuthnLevel
0x180070034  call    cs:__imp_CoInitializeSecurity
0x18007003a  mov     ebx, eax
0x18007003c  test    eax, eax
0x18007003e  jns     short loc_18007004D
0x180070040  mov     r9d, eax
0x180070043  mov     edx, 14Ah
0x180070048  jmp     loc_18006FEFA
0x18007004d  mov     ebx, edi
0x18007004f  jmp     short loc_180070068
0x180070051  mov     edx, 134h; void *
0x180070056  mov     rcx, [rbp+5Fh]; this
0x18007005a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x180070061  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180070066  mov     ebx, eax
0x180070068  lea     rcx, [rbp+57h+var_58]
0x18007006c  mov     [rbp+57h+var_28], dil
0x180070070  call    ??R_lambda_bed1b5be4148163977e87fd2fb1bced4_@@QEBA@XZ; _lambda_bed1b5be4148163977e87fd2fb1bced4_::operator()(void)
0x180070075  mov     eax, ebx
0x180070077  add     rsp, 0D8h
0x18007007e  pop     rdi
0x18007007f  pop     rsi
0x180070080  pop     rbx
0x180070081  pop     rbp
0x180070082  retn
```
