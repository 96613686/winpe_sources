# CLocalAccounts::FindByRID(ulong,IPropertyStore * *)

- ea: `0x180001940`
- end: `0x180001e5d`
- name: `?FindByRID@CLocalAccounts@@UEAAJKPEAPEAUIPropertyStore@@@Z`
- size: `1309`
- prototype: `__int64 __fastcall(CLocalAccounts *__hidden this, unsigned int, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001940`
- `0x180002f90`
- `0x180002ff0`
- `0x18000c240`
- `0x18000d740`
- `0x180012f18`
- `0x180013580`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c9c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001a3f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001c87`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001a3f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001c87`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001a0f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001a31`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001c54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001c75`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001a0f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001a31`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001c54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001c75`
- `ntdll!RtlSubAuthoritySid` at `0x180001c41`
- `ntdll!RtlSubAuthoritySid` at `0x180001c41`
- `ntdll!RtlInitializeSid` at `0x180001c32`
- `ntdll!RtlInitializeSid` at `0x180001c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001bf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001bf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001c5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001c5c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800019c6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800019c6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001a7a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001aa2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001add`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001a7a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001aa2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180001add`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800019ea`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800019ea`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180001a6f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180001a97`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180001a6f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180001a97`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::FindByRID(CLocalAccounts *this, unsigned int a2, struct IPropertyStore **a3)
{
  unsigned int v4; // r12d
  _BYTE *v6; // rcx
  unsigned int v7; // ebx
  void *v8; // r14
  NTSTATUS v9; // edi
  NTSTATUS v10; // edi
  void *v11; // rcx
  DWORD LengthSid; // eax
  void *v13; // rdi
  DWORD v14; // eax
  signed int LastError; // eax
  int v16; // edi
  int v17; // eax
  int v18; // r12d
  CSamPropStore *v19; // rax
  CSamPropStore *v20; // rax
  CSamPropStore *v21; // rdi
  int v22; // eax
  int v23; // ebp
  int v24; // eax
  DWORD v26; // eax
  void *v27; // rbp
  DWORD v28; // eax
  signed int v29; // eax
  int v30; // eax
  int v31; // r14d
  CSamPropStore *v32; // rax
  CSamPropStore *v33; // rax
  CSamPropStore *v34; // rdi
  int v35; // eax
  CSamPropStore *v36; // rcx
  void (__fastcall *v37)(CSamPropStore *); // rax
  bool v38; // sf
  int v39; // eax
  PVOID Buffer; // [rsp+30h] [rbp-88h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-80h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-78h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-48h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = a2;
  v4 = a2;
  if ( !a3 )
  {
    v6 = WPP_GLOBAL_Control;
    v7 = -2147467261;
    goto LABEL_59;
  }
  *a3 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  v7 = -2147024882;
  if ( v9 < 0 )
  {
    v16 = v9 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
        (unsigned int)v16);
  }
  else
  {
    v10 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    if ( v10 < 0 )
    {
      v16 = v10 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
          (unsigned int)v16);
      LsaClose(PolicyHandle);
    }
    else
    {
      v11 = (void *)*((_QWORD *)Buffer + 2);
      if ( v11 )
      {
        LengthSid = GetLengthSid(v11);
        v8 = CoTaskMemAlloc(LengthSid);
        if ( v8 )
        {
          v13 = (void *)*((_QWORD *)Buffer + 2);
          v14 = GetLengthSid(v13);
          if ( CopySid(v14, v8, v13) )
          {
            v16 = 0;
          }
          else
          {
            CoTaskMemFree(v8);
            v8 = 0;
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError > 0 )
            {
              v16 = (unsigned __int16)LastError | 0x80070000;
              LsaFreeMemory(Buffer);
              LsaClose(PolicyHandle);
              goto LABEL_21;
            }
          }
        }
        else
        {
          v16 = -2147024882;
        }
      }
      else
      {
        v16 = -2147467259;
      }
      LsaFreeMemory(Buffer);
      LsaClose(PolicyHandle);
    }
  }
LABEL_21:
  if ( v16 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
    *a3 = 0;
    v18 = v17;
    v19 = (CSamPropStore *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v19 && (v20 = CSamPropStore::CSamPropStore(v19), (v21 = v20) != 0) )
    {
      v22 = CSamPropStore::_Init(v20, v8, 0, *(unsigned int *)IdentifierAuthority.Value, v18, 0);
      v23 = v22;
      if ( v22 >= 0 )
      {
        v24 = (**(__int64 (__fastcall ***)(CSamPropStore *, GUID *, struct IPropertyStore **))v21)(
                v21,
                &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                a3);
        if ( v24 < 0 )
          v23 = v24;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_7df418057efb386bc095915f6151cd01_Traceguids,
          *(unsigned int *)IdentifierAuthority.Value,
          v18,
          v22);
      }
      (*(void (__fastcall **)(CSamPropStore *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    else
    {
      v23 = -2147024882;
    }
    CoTaskMemFree(v8);
    if ( v23 >= 0 )
      return (unsigned int)v23;
    v4 = *(_DWORD *)IdentifierAuthority.Value;
  }
  if ( !byte_1800204C0 )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(&byte_1800204C0, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(&byte_1800204C0, 0) = 32;
  }
  v26 = GetLengthSid(&byte_1800204C0);
  v27 = CoTaskMemAlloc(v26);
  if ( v27 )
  {
    v28 = GetLengthSid(&byte_1800204C0);
    if ( CopySid(v28, v27, &byte_1800204C0) )
      goto LABEL_42;
    CoTaskMemFree(v27);
    v27 = 0;
    v29 = GetLastError();
    v7 = v29;
    if ( v29 > 0 )
      v7 = (unsigned __int16)v29 | 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
    {
LABEL_42:
      v30 = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
      *a3 = 0;
      v31 = v30;
      v32 = (CSamPropStore *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v32 )
      {
        v33 = CSamPropStore::CSamPropStore(v32);
        v34 = v33;
        if ( v33 )
        {
          v35 = CSamPropStore::_Init(v33, v27, 0, v4, v31, 0);
          v7 = v35;
          if ( v35 >= 0 )
          {
            v38 = (**(int (__fastcall ***)(CSamPropStore *, GUID *, struct IPropertyStore **))v34)(
                    v34,
                    &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                    a3) < 0;
            v36 = v34;
            v37 = *(void (__fastcall **)(CSamPropStore *))(*(_QWORD *)v34 + 16LL);
            if ( !v38 )
            {
              v37(v34);
              CoTaskMemFree(v27);
              goto LABEL_56;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_ddD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                v4,
                v31,
                v35);
            v36 = v34;
            v37 = *(void (__fastcall **)(CSamPropStore *))(*(_QWORD *)v34 + 16LL);
          }
          v37(v36);
        }
      }
      *a3 = 0;
      v7 = -2147024809;
      CoTaskMemFree(v27);
LABEL_56:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_57;
    }
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v7);
    goto LABEL_56;
  }
LABEL_57:
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024809 )
  {
LABEL_59:
    if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (v6[28] & 2) != 0 )
    {
      v39 = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
      WPP_SF_ddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v4, v39, v7);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180001940  mov     [rsp+arg_18], rbx
0x180001945  push    rbp
0x180001946  push    rsi
0x180001947  push    rdi
0x180001948  push    r12
0x18000194a  push    r13
0x18000194c  push    r14
0x18000194e  push    r15
0x180001950  sub     rsp, 80h
0x180001957  mov     rax, cs:__security_cookie
0x18000195e  xor     rax, rsp
0x180001961  mov     [rsp+0B8h+var_40], rax
0x180001966  mov     dword ptr [rsp+0B8h+IdentifierAuthority.Value], edx
0x18000196a  mov     rsi, r8
0x18000196d  mov     r12d, edx
0x180001970  mov     r13, rcx
0x180001973  test    r8, r8
0x180001976  jnz     short loc_180001990
0x180001978  mov     rcx, cs:WPP_GLOBAL_Control
0x18000197f  lea     r15, WPP_GLOBAL_Control
0x180001986  mov     ebx, 80004003h
0x18000198b  jmp     loc_180001DEE
0x180001990  xor     ebp, ebp
0x180001992  lea     r9, [rsp+0B8h+PolicyHandle]; PolicyHandle
0x180001997  xorps   xmm0, xmm0
0x18000199a  mov     [r8], rbp
0x18000199d  mov     r8d, 1; DesiredAccess
0x1800019a3  mov     [rsp+0B8h+PolicyHandle], rbp
0x1800019a8  lea     rdx, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1800019ad  mov     [rsp+0B8h+Buffer], rbp
0x1800019b2  xor     ecx, ecx; SystemName
0x1800019b4  mov     r14d, ebp
0x1800019b7  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x1800019bc  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x1800019c1  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800019c6  call    cs:__imp_LsaOpenPolicy
0x1800019cc  mov     edi, eax
0x1800019ce  mov     ebx, 8007000Eh
0x1800019d3  test    eax, eax
0x1800019d5  js      loc_180001AE5
0x1800019db  mov     rcx, [rsp+0B8h+PolicyHandle]; PolicyHandle
0x1800019e0  lea     r8, [rsp+0B8h+Buffer]; Buffer
0x1800019e5  mov     edx, 5; InformationClass
0x1800019ea  call    cs:__imp_LsaQueryInformationPolicy
0x1800019f0  lea     r15, WPP_GLOBAL_Control
0x1800019f7  mov     edi, eax
0x1800019f9  test    eax, eax
0x1800019fb  js      loc_180001AAA
0x180001a01  mov     rax, [rsp+0B8h+Buffer]
0x180001a06  mov     rcx, [rax+10h]; pSid
0x180001a0a  test    rcx, rcx
0x180001a0d  jz      short loc_180001A8D
0x180001a0f  call    cs:__imp_GetLengthSid
0x180001a15  mov     ecx, eax; cb
0x180001a17  call    cs:__imp_CoTaskMemAlloc
0x180001a1d  mov     r14, rax
0x180001a20  test    rax, rax
0x180001a23  jz      short loc_180001A89
0x180001a25  mov     rax, [rsp+0B8h+Buffer]
0x180001a2a  mov     rdi, [rax+10h]
0x180001a2e  mov     rcx, rdi; pSid
0x180001a31  call    cs:__imp_GetLengthSid
0x180001a37  mov     r8, rdi; pSourceSid
0x180001a3a  mov     rdx, r14; pDestinationSid
0x180001a3d  mov     ecx, eax; nDestinationSidLength
0x180001a3f  call    cs:__imp_CopySid
0x180001a45  test    eax, eax
0x180001a47  jnz     short loc_180001A85
0x180001a49  mov     rcx, r14; pv
0x180001a4c  call    cs:__imp_CoTaskMemFree
0x180001a52  mov     r14d, ebp
0x180001a55  call    cs:__imp_GetLastError
0x180001a5b  mov     edi, eax
0x180001a5d  test    eax, eax
0x180001a5f  jle     short loc_180001A92
0x180001a61  mov     rcx, [rsp+0B8h+Buffer]; Buffer
0x180001a66  movzx   edi, ax
0x180001a69  or      edi, 80070000h
0x180001a6f  call    cs:__imp_LsaFreeMemory
0x180001a75  mov     rcx, [rsp+0B8h+PolicyHandle]; ObjectHandle
0x180001a7a  call    cs:__imp_LsaClose
0x180001a80  jmp     loc_180001B1A
0x180001a85  mov     edi, ebp
0x180001a87  jmp     short loc_180001A92
0x180001a89  mov     edi, ebx
0x180001a8b  jmp     short loc_180001A92
0x180001a8d  mov     edi, 80004005h
0x180001a92  mov     rcx, [rsp+0B8h+Buffer]; Buffer
0x180001a97  call    cs:__imp_LsaFreeMemory
0x180001a9d  mov     rcx, [rsp+0B8h+PolicyHandle]; ObjectHandle
0x180001aa2  call    cs:__imp_LsaClose
0x180001aa8  jmp     short loc_180001B1A
0x180001aaa  bts     edi, 1Ch
0x180001aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ab5  cmp     rcx, r15
0x180001ab8  jz      short loc_180001AD8
0x180001aba  test    byte ptr [rcx+1Ch], 2
0x180001abe  jz      short loc_180001AD8
0x180001ac0  mov     rcx, [rcx+10h]
0x180001ac4  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180001acb  mov     edx, 1Dh
0x180001ad0  mov     r9d, edi
0x180001ad3  call    WPP_SF_d
0x180001ad8  mov     rcx, [rsp+0B8h+PolicyHandle]; ObjectHandle
0x180001add  call    cs:__imp_LsaClose
0x180001ae3  jmp     short loc_180001B1A
0x180001ae5  bts     edi, 1Ch
0x180001ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001af0  lea     r15, WPP_GLOBAL_Control
0x180001af7  cmp     rcx, r15
0x180001afa  jz      short loc_180001B1A
0x180001afc  test    byte ptr [rcx+1Ch], 2
0x180001b00  jz      short loc_180001B1A
0x180001b02  mov     rcx, [rcx+10h]
0x180001b06  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180001b0d  mov     edx, 1Eh
0x180001b12  mov     r9d, edi
0x180001b15  call    WPP_SF_d
0x180001b1a  test    edi, edi
0x180001b1c  js      loc_180001C0B
0x180001b22  mov     rax, [r13+0]
0x180001b26  mov     rcx, r13
0x180001b29  mov     rax, [rax+88h]
0x180001b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001b3c  mov     [rsi], rbp
0x180001b3f  mov     ecx, 70h ; 'p'; unsigned __int64
0x180001b44  mov     r12d, eax
0x180001b47  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001b4c  test    rax, rax
0x180001b4f  jz      loc_180001BF0
0x180001b55  mov     rcx, rax; this
0x180001b58  call    ??0CSamPropStore@@QEAA@XZ; CSamPropStore::CSamPropStore(void)
0x180001b5d  mov     rdi, rax
0x180001b60  test    rax, rax
0x180001b63  jz      loc_180001BF0
0x180001b69  mov     r9d, dword ptr [rsp+0B8h+IdentifierAuthority.Value]
0x180001b6e  xor     r8d, r8d
0x180001b71  mov     [rsp+0B8h+var_90], ebp
0x180001b75  mov     rdx, r14
0x180001b78  mov     rcx, rax
0x180001b7b  mov     [rsp+0B8h+var_98], r12d
0x180001b80  call    ?_Init@CSamPropStore@@QEAAJPEAXPEBGKW4_ACCOUNT_OBJECT_TYPE@@H@Z; CSamPropStore::_Init(void *,ushort const *,ulong,_ACCOUNT_OBJECT_TYPE,int)
0x180001b85  mov     ebp, eax
0x180001b87  test    eax, eax
0x180001b89  jns     short loc_180001BC2
0x180001b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b92  cmp     rcx, r15
0x180001b95  jz      short loc_180001BDF
0x180001b97  test    byte ptr [rcx+1Ch], 2
0x180001b9b  jz      short loc_180001BDF
0x180001b9d  mov     r9d, dword ptr [rsp+0B8h+IdentifierAuthority.Value]
0x180001ba2  lea     r8, WPP_7df418057efb386bc095915f6151cd01_Traceguids
0x180001ba9  mov     rcx, [rcx+10h]
0x180001bad  mov     edx, 1Bh
0x180001bb2  mov     [rsp+0B8h+var_90], eax
0x180001bb6  mov     [rsp+0B8h+var_98], r12d
0x180001bbb  call    WPP_SF_ddD
0x180001bc0  jmp     short loc_180001BDF
0x180001bc2  mov     rax, [rdi]
0x180001bc5  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180001bcc  mov     r8, rsi
0x180001bcf  mov     rcx, rdi
0x180001bd2  mov     rax, [rax]
0x180001bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bda  test    eax, eax
0x180001bdc  cmovs   ebp, eax
0x180001bdf  mov     rax, [rdi]
0x180001be2  mov     rcx, rdi
0x180001be5  mov     rax, [rax+10h]
0x180001be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bee  jmp     short loc_180001BF2
0x180001bf0  mov     ebp, ebx
0x180001bf2  mov     rcx, r14; pv
0x180001bf5  call    cs:__imp_CoTaskMemFree
0x180001bfb  test    ebp, ebp
0x180001bfd  js      short loc_180001C06
0x180001bff  mov     eax, ebp
0x180001c01  jmp     loc_180001E35
0x180001c06  mov     r12d, dword ptr [rsp+0B8h+IdentifierAuthority.Value]
0x180001c0b  cmp     cs:byte_1800204C0, 0
0x180001c12  jnz     short loc_180001C4D
0x180001c14  mov     r8b, 1; SubAuthorityCount
0x180001c17  mov     dword ptr [rsp+0B8h+IdentifierAuthority.Value], 0
0x180001c1f  lea     rdx, [rsp+0B8h+IdentifierAuthority]; IdentifierAuthority
0x180001c24  mov     word ptr [rsp+0B8h+IdentifierAuthority.Value+4], 500h
0x180001c2b  lea     rcx, byte_1800204C0; Sid
0x180001c32  call    cs:__imp_RtlInitializeSid
0x180001c38  xor     edx, edx; SubAuthority
0x180001c3a  lea     rcx, byte_1800204C0; Sid
0x180001c41  call    cs:__imp_RtlSubAuthoritySid
0x180001c47  mov     dword ptr [rax], 20h ; ' '
0x180001c4d  lea     rcx, byte_1800204C0; pSid
0x180001c54  call    cs:__imp_GetLengthSid
0x180001c5a  mov     ecx, eax; cb
0x180001c5c  call    cs:__imp_CoTaskMemAlloc
0x180001c62  mov     rbp, rax
0x180001c65  test    rax, rax
0x180001c68  jz      loc_180001DA9
0x180001c6e  lea     rcx, byte_1800204C0; pSid
0x180001c75  call    cs:__imp_GetLengthSid
0x180001c7b  lea     r8, byte_1800204C0; pSourceSid
0x180001c82  mov     rdx, rbp; pDestinationSid
0x180001c85  mov     ecx, eax; nDestinationSidLength
0x180001c87  call    cs:__imp_CopySid
0x180001c8d  test    eax, eax
0x180001c8f  jnz     short loc_180001CB9
0x180001c91  mov     rcx, rbp; pv
0x180001c94  call    cs:__imp_CoTaskMemFree
0x180001c9a  xor     ebp, ebp
0x180001c9c  call    cs:__imp_GetLastError
0x180001ca2  mov     ebx, eax
0x180001ca4  test    eax, eax
0x180001ca6  jle     short loc_180001CB1
0x180001ca8  movzx   ebx, ax
0x180001cab  or      ebx, 80070000h
0x180001cb1  test    ebx, ebx
0x180001cb3  js      loc_180001DA9
0x180001cb9  mov     rax, [r13+0]
0x180001cbd  mov     rcx, r13
0x180001cc0  mov     rax, [rax+88h]
0x180001cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ccc  xor     ebx, ebx
0x180001cce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001cd5  mov     ecx, 70h ; 'p'; unsigned __int64
0x180001cda  mov     [rsi], rbx
0x180001cdd  mov     r14d, eax
0x180001ce0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001ce5  test    rax, rax
0x180001ce8  jz      short loc_180001D5C
0x180001cea  mov     rcx, rax; this
0x180001ced  call    ??0CSamPropStore@@QEAA@XZ; CSamPropStore::CSamPropStore(void)
0x180001cf2  mov     rdi, rax
0x180001cf5  test    rax, rax
0x180001cf8  jz      short loc_180001D5C
0x180001cfa  mov     [rsp+0B8h+var_90], ebx
0x180001cfe  mov     r9d, r12d
0x180001d01  xor     r8d, r8d
0x180001d04  mov     [rsp+0B8h+var_98], r14d
0x180001d09  mov     rdx, rbp
0x180001d0c  mov     rcx, rax
0x180001d0f  call    ?_Init@CSamPropStore@@QEAAJPEAXPEBGKW4_ACCOUNT_OBJECT_TYPE@@H@Z; CSamPropStore::_Init(void *,ushort const *,ulong,_ACCOUNT_OBJECT_TYPE,int)
0x180001d14  mov     ebx, eax
0x180001d16  test    eax, eax
0x180001d18  jns     short loc_180001D73
0x180001d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d21  cmp     rcx, r15
0x180001d24  jz      short loc_180001D4D
0x180001d26  test    byte ptr [rcx+1Ch], 2
0x180001d2a  jz      short loc_180001D4D
0x180001d2c  mov     rcx, [rcx+10h]
0x180001d30  lea     r8, WPP_7df418057efb386bc095915f6151cd01_Traceguids
0x180001d37  mov     [rsp+0B8h+var_90], eax
0x180001d3b  mov     edx, 1Bh
0x180001d40  mov     r9d, r12d
0x180001d43  mov     [rsp+0B8h+var_98], r14d
0x180001d48  call    WPP_SF_ddD
0x180001d4d  mov     rax, [rdi]
0x180001d50  mov     rcx, rdi
0x180001d53  mov     rax, [rax+10h]
0x180001d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d5c  mov     rcx, rbp; pv
0x180001d5f  mov     qword ptr [rsi], 0
0x180001d66  mov     ebx, 80070057h
0x180001d6b  call    cs:__imp_CoTaskMemFree
0x180001d71  jmp     short loc_180001DD3
0x180001d73  mov     rax, [rdi]
0x180001d76  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180001d7d  mov     r8, rsi
0x180001d80  mov     rcx, rdi
0x180001d83  mov     rax, [rax]
0x180001d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d8b  test    eax, eax
0x180001d8d  mov     rcx, rdi
0x180001d90  mov     rax, [rdi]
0x180001d93  mov     rax, [rax+10h]
0x180001d97  js      short loc_180001D57
0x180001d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d9e  mov     rcx, rbp; pv
0x180001da1  call    cs:__imp_CoTaskMemFree
0x180001da7  jmp     short loc_180001DD3
0x180001da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001db0  cmp     rcx, r15
0x180001db3  jz      short loc_180001DDA
0x180001db5  test    byte ptr [rcx+1Ch], 2
0x180001db9  jz      short loc_180001DDA
0x180001dbb  mov     rcx, [rcx+10h]
0x180001dbf  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180001dc6  mov     edx, 1Fh
0x180001dcb  mov     r9d, ebx
0x180001dce  call    WPP_SF_d
0x180001dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001dda  mov     edx, 80000000h
0x180001ddf  lea     eax, [rbx+rdx]
0x180001de2  test    edx, eax
0x180001de4  jnz     short loc_180001E33
0x180001de6  cmp     ebx, 80070057h
0x180001dec  jz      short loc_180001E33
0x180001dee  cmp     rcx, r15
0x180001df1  jz      short loc_180001E33
  ... truncated ...
```
