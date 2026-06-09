# CSSetAccountRights(void *,ulong)

- ea: `0x18000f64c`
- end: `0x18000f912`
- name: `?CSSetAccountRights@@YAJPEAXK@Z`
- size: `710`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800126c0`
- `0x180012acc`

## callees

- `0x180005d80`
- `0x1800087b0`
- `0x18000f64c`
- `0x180013004`
- `0x180013490`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000f7d3`
- `ntdll!RtlInitUnicodeString` at `0x18000f7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8b8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000f6a7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000f6a7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000f8c2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000f8c2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18000f860`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18000f860`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18000f809`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18000f809`

## pseudocode

```c
__int64 __fastcall CSSetAccountRights(void *a1, int a2)
{
  int v2; // r14d
  int v5; // ebx
  NTSTATUS v6; // ebx
  __int64 v7; // r8
  ULONG v8; // r15d
  ULONG v9; // r9d
  unsigned int i; // edx
  ULONG v11; // eax
  struct _LSA_UNICODE_STRING *v12; // r12
  struct _LSA_UNICODE_STRING *v13; // r13
  void *v14; // rcx
  int v15; // eax
  void *v16; // rcx
  int v17; // eax
  int v18; // edi
  unsigned int j; // esi
  struct _UNICODE_STRING *v20; // rcx
  NTSTATUS v21; // eax
  int v22; // r8d
  NTSTATUS v23; // ecx
  int v24; // r8d
  PVOID PolicyHandle; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int64 v27; // [rsp+40h] [rbp-39h] BYREF
  void *v28; // [rsp+48h] [rbp-31h] BYREF
  void *v29; // [rsp+50h] [rbp-29h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-21h] BYREF
  int v33; // [rsp+F0h] [rbp+77h]
  ULONG v34; // [rsp+F8h] [rbp+7Fh]

  v2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 )
  {
    v6 = LsaOpenPolicy(0, &ObjectAttributes, 0xF0FFFu, &PolicyHandle);
    if ( v6 < 0 )
    {
      v5 = v6 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v7, a1, v5);
    }
    else
    {
      v33 = 0;
      v8 = 0;
      v9 = 0;
      for ( i = 0; i < 0xA; ++i )
      {
        v11 = v9 + 1;
        if ( (*(_DWORD *)(&off_180018840 + 2 * (int)i + 1) & a2) != 0 )
          v11 = v9;
        v9 = v11;
        if ( (*(_DWORD *)(&off_180018840 + 2 * (int)i + 1) & a2) != 0 )
          ++v8;
      }
      v34 = v11;
      v12 = 0;
      v13 = 0;
      v28 = 0;
      v29 = 0;
      if ( !v8 )
        goto LABEL_17;
      v27 = 0;
      v33 = ULongLongMult(v8, 0x10u, &v27);
      v5 = v33;
      if ( v33 >= 0 )
      {
        v15 = CTCoAllocPolicy::Alloc(v14, 1u, v27, &v28);
        v9 = v34;
        v5 = v15;
        v12 = (struct _LSA_UNICODE_STRING *)v28;
        v33 = v15;
      }
      if ( v5 >= 0 )
      {
LABEL_17:
        if ( !v9 )
          goto LABEL_18;
        v28 = 0;
        v33 = ULongLongMult(v9, 0x10u, (unsigned __int64 *)&v28);
        v5 = v33;
        if ( v33 >= 0 )
        {
          v17 = CTCoAllocPolicy::Alloc(v16, 1u, (unsigned __int64)v28, &v29);
          v13 = (struct _LSA_UNICODE_STRING *)v29;
          v5 = v17;
          v33 = v17;
        }
        if ( v5 >= 0 )
        {
LABEL_18:
          v18 = 0;
          for ( j = 0; j < 0xA; ++j )
          {
            if ( (a2 & *(_DWORD *)(&off_180018840 + 2 * (int)j + 1)) != 0 )
              v20 = (struct _UNICODE_STRING *)&v12[v2++];
            else
              v20 = (struct _UNICODE_STRING *)&v13[v18++];
            RtlInitUnicodeString(v20, (&off_180018840)[2 * (int)j]);
          }
          v5 = v33;
          if ( !v8 )
            goto LABEL_33;
          v21 = LsaAddAccountRights(PolicyHandle, a1, v12, v8);
          if ( v21 >= 0 )
            goto LABEL_33;
          v5 = v21 | 0x10000000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_D_sid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v22, a2, a1, v21);
          if ( v5 >= 0 )
          {
LABEL_33:
            if ( v34 )
            {
              v23 = LsaRemoveAccountRights(PolicyHandle, a1, 0, v13, v34);
              if ( (int)(v23 + 0x80000000) >= 0 && v23 != -1073741772 )
              {
                v5 = v23 | 0x10000000;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_D_sid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v24, a2, a1, v23);
                }
              }
            }
          }
        }
      }
      CoTaskMemFree(v12);
      CoTaskMemFree(v13);
      LsaClose(PolicyHandle);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f64c  mov     [rsp-8+arg_8], edx
0x18000f650  mov     [rsp-8+AccountSid], rcx
0x18000f655  push    rbp
0x18000f656  push    rbx
0x18000f657  push    rsi
0x18000f658  push    rdi
0x18000f659  push    r12
0x18000f65b  push    r13
0x18000f65d  push    r14
0x18000f65f  push    r15
0x18000f661  lea     rbp, [rsp-1Fh]
0x18000f666  sub     rsp, 98h
0x18000f66d  xorps   xmm0, xmm0
0x18000f670  xor     r14d, r14d
0x18000f673  mov     [rbp+57h+PolicyHandle], r14
0x18000f677  mov     esi, edx
0x18000f679  mov     rdi, rcx
0x18000f67c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000f680  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000f684  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f688  test    rcx, rcx
0x18000f68b  jnz     short loc_18000F697
0x18000f68d  mov     ebx, 80004003h
0x18000f692  jmp     loc_18000F8FC
0x18000f697  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000f69b  mov     r8d, 0F0FFFh; DesiredAccess
0x18000f6a1  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000f6a5  xor     ecx, ecx; SystemName
0x18000f6a7  call    cs:__imp_LsaOpenPolicy
0x18000f6ad  mov     ebx, eax
0x18000f6af  test    eax, eax
0x18000f6b1  js      loc_18000F8CA
0x18000f6b7  mov     [rbp+57h+arg_10], r14d
0x18000f6bb  lea     r8, off_180018840; "SeInteractiveLogonRight"
0x18000f6c2  mov     r15d, r14d
0x18000f6c5  mov     r9d, r14d
0x18000f6c8  mov     edx, r14d
0x18000f6cb  movsxd  rax, edx
0x18000f6ce  mov     ecx, esi
0x18000f6d0  shl     rax, 4
0x18000f6d4  and     ecx, [rax+r8+8]
0x18000f6d9  lea     eax, [r9+1]
0x18000f6dd  cmovnz  eax, r9d
0x18000f6e1  test    ecx, ecx
0x18000f6e3  mov     r9d, eax
0x18000f6e6  lea     eax, [r15+1]
0x18000f6ea  cmovnz  r15d, eax
0x18000f6ee  inc     edx
0x18000f6f0  cmp     edx, 0Ah
0x18000f6f3  jb      short loc_18000F6CB
0x18000f6f5  mov     [rbp+57h+arg_18], r9d
0x18000f6f9  mov     r12, r14
0x18000f6fc  mov     [rbp+57h+CountOfRights], r15d
0x18000f700  mov     r13, r14
0x18000f703  mov     [rbp+57h+var_88], r14
0x18000f707  mov     esi, 10h
0x18000f70c  mov     [rbp+57h+var_80], r14
0x18000f710  test    r15d, r15d
0x18000f713  jz      short loc_18000F755
0x18000f715  mov     ecx, r15d; unsigned __int64
0x18000f718  lea     r8, [rbp+57h+var_90]; unsigned __int64 *
0x18000f71c  mov     edx, esi; unsigned __int64
0x18000f71e  mov     [rbp+57h+var_90], r14
0x18000f722  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000f727  mov     [rbp+57h+arg_10], eax
0x18000f72a  mov     ebx, eax
0x18000f72c  test    eax, eax
0x18000f72e  js      short loc_18000F74D
0x18000f730  mov     r8, [rbp+57h+var_90]; unsigned __int64
0x18000f734  lea     r9, [rbp+57h+var_88]; void **
0x18000f738  lea     edx, [rsi-0Fh]; unsigned int
0x18000f73b  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000f740  mov     r9d, [rbp+57h+arg_18]
0x18000f744  mov     ebx, eax
0x18000f746  mov     r12, [rbp+57h+var_88]
0x18000f74a  mov     [rbp+57h+arg_10], eax
0x18000f74d  test    ebx, ebx
0x18000f74f  js      loc_18000F8AC
0x18000f755  test    r9d, r9d
0x18000f758  jz      short loc_18000F799
0x18000f75a  mov     ecx, r9d; unsigned __int64
0x18000f75d  lea     r8, [rbp+57h+var_88]; unsigned __int64 *
0x18000f761  mov     rdx, rsi; unsigned __int64
0x18000f764  mov     [rbp+57h+var_88], r14
0x18000f768  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000f76d  mov     [rbp+57h+arg_10], eax
0x18000f770  mov     ebx, eax
0x18000f772  test    eax, eax
0x18000f774  js      short loc_18000F791
0x18000f776  mov     r8, [rbp+57h+var_88]; unsigned __int64
0x18000f77a  lea     r9, [rbp+57h+var_80]; void **
0x18000f77e  mov     edx, 1; unsigned int
0x18000f783  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000f788  mov     r13, [rbp+57h+var_80]
0x18000f78c  mov     ebx, eax
0x18000f78e  mov     [rbp+57h+arg_10], eax
0x18000f791  test    ebx, ebx
0x18000f793  js      loc_18000F8AC
0x18000f799  mov     r15d, [rbp+57h+arg_8]
0x18000f79d  lea     rbx, off_180018840; "SeInteractiveLogonRight"
0x18000f7a4  xor     edi, edi
0x18000f7a6  xor     esi, esi
0x18000f7a8  movsxd  rax, esi
0x18000f7ab  add     rax, rax
0x18000f7ae  mov     rdx, [rbx+rax*8]; SourceString
0x18000f7b2  test    [rbx+rax*8+8], r15d
0x18000f7b7  jnz     short loc_18000F7C6
0x18000f7b9  mov     ecx, edi
0x18000f7bb  shl     rcx, 4
0x18000f7bf  add     rcx, r13
0x18000f7c2  inc     edi
0x18000f7c4  jmp     short loc_18000F7D3
0x18000f7c6  mov     ecx, r14d
0x18000f7c9  shl     rcx, 4
0x18000f7cd  add     rcx, r12; DestinationString
0x18000f7d0  inc     r14d
0x18000f7d3  call    cs:__imp_RtlInitUnicodeString
0x18000f7d9  inc     esi
0x18000f7db  cmp     esi, 0Ah
0x18000f7de  jb      short loc_18000F7A8
0x18000f7e0  mov     r15d, [rbp+57h+CountOfRights]
0x18000f7e4  lea     r14, WPP_GLOBAL_Control
0x18000f7eb  mov     ebx, [rbp+57h+arg_10]
0x18000f7ee  mov     esi, 10000000h
0x18000f7f3  mov     rdi, [rbp+57h+AccountSid]
0x18000f7f7  test    r15d, r15d
0x18000f7fa  jz      short loc_18000F848
0x18000f7fc  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000f800  mov     r9d, r15d; CountOfRights
0x18000f803  mov     r8, r12; UserRights
0x18000f806  mov     rdx, rdi; AccountSid
0x18000f809  call    cs:__imp_LsaAddAccountRights
0x18000f80f  test    eax, eax
0x18000f811  jns     short loc_18000F848
0x18000f813  mov     ebx, eax
0x18000f815  or      ebx, esi
0x18000f817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f81e  cmp     rcx, r14
0x18000f821  jz      short loc_18000F844
0x18000f823  test    byte ptr [rcx+1Ch], 2
0x18000f827  jz      short loc_18000F844
0x18000f829  mov     r9d, [rbp+57h+arg_8]; int
0x18000f82d  mov     edx, 30h ; '0'; int
0x18000f832  mov     rcx, [rcx+10h]; int
0x18000f836  mov     dword ptr [rsp+0D0h+var_A8], ebx; char
0x18000f83a  mov     qword ptr [rsp+0D0h+var_B0], rdi; pSid
0x18000f83f  call    WPP_SF_D_sid_D
0x18000f844  test    ebx, ebx
0x18000f846  js      short loc_18000F8AC
0x18000f848  mov     eax, [rbp+57h+arg_18]
0x18000f84b  test    eax, eax
0x18000f84d  jz      short loc_18000F8AC
0x18000f84f  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000f853  mov     r9, r13; UserRights
0x18000f856  xor     r8d, r8d; AllRights
0x18000f859  mov     [rsp+0D0h+var_B0], eax; CountOfRights
0x18000f85d  mov     rdx, rdi; AccountSid
0x18000f860  call    cs:__imp_LsaRemoveAccountRights
0x18000f866  mov     edx, 80000000h
0x18000f86b  mov     ecx, eax
0x18000f86d  add     eax, edx
0x18000f86f  test    edx, eax
0x18000f871  jnz     short loc_18000F8AC
0x18000f873  cmp     ecx, 0C0000034h
0x18000f879  jz      short loc_18000F8AC
0x18000f87b  mov     ebx, ecx
0x18000f87d  or      ebx, esi
0x18000f87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f886  cmp     rcx, r14
0x18000f889  jz      short loc_18000F8AC
0x18000f88b  test    byte ptr [rcx+1Ch], 2
0x18000f88f  jz      short loc_18000F8AC
0x18000f891  mov     r9d, [rbp+57h+arg_8]; int
0x18000f895  mov     edx, 31h ; '1'; int
0x18000f89a  mov     rcx, [rcx+10h]; int
0x18000f89e  mov     dword ptr [rsp+0D0h+var_A8], ebx; char
0x18000f8a2  mov     qword ptr [rsp+0D0h+var_B0], rdi; pSid
0x18000f8a7  call    WPP_SF_D_sid_D
0x18000f8ac  mov     rcx, r12; pv
0x18000f8af  call    cs:__imp_CoTaskMemFree
0x18000f8b5  mov     rcx, r13; pv
0x18000f8b8  call    cs:__imp_CoTaskMemFree
0x18000f8be  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18000f8c2  call    cs:__imp_LsaClose
0x18000f8c8  jmp     short loc_18000F8FC
0x18000f8ca  bts     ebx, 1Ch
0x18000f8ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8d5  lea     r14, WPP_GLOBAL_Control
0x18000f8dc  cmp     rcx, r14
0x18000f8df  jz      short loc_18000F8FC
0x18000f8e1  test    byte ptr [rcx+1Ch], 2
0x18000f8e5  jz      short loc_18000F8FC
0x18000f8e7  mov     rcx, [rcx+10h]
0x18000f8eb  mov     edx, 32h ; '2'
0x18000f8f0  mov     r9, rdi
0x18000f8f3  mov     [rsp+0D0h+var_B0], ebx
0x18000f8f7  call    WPP_SF__sid_D
0x18000f8fc  mov     eax, ebx
0x18000f8fe  add     rsp, 98h
0x18000f905  pop     r15
0x18000f907  pop     r14
0x18000f909  pop     r13
0x18000f90b  pop     r12
0x18000f90d  pop     rdi
0x18000f90e  pop     rsi
0x18000f90f  pop     rbx
0x18000f910  pop     rbp
0x18000f911  retn
```
