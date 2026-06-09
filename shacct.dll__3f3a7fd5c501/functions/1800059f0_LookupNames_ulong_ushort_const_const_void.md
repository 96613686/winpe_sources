# LookupNames(ulong,ushort const * const *,void * * *)

- ea: `0x1800059f0`
- end: `0x180005d76`
- name: `?LookupNames@@YAJKPEBQEBGPEAPEAPEAX@Z`
- size: `902`
- prototype: `__int64 __fastcall(ULONG Count, const unsigned __int16 *const *, void ***)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004c90`
- `0x180005060`
- `0x180005980`
- `0x18000f918`

## callees

- `0x1800059f0`
- `0x180005d80`
- `0x180012ee8`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c86`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005c6b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005c6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005c37`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005c37`
- `ntdll!RtlInitUnicodeString` at `0x180005aa8`
- `ntdll!RtlInitUnicodeString` at `0x180005aa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c42`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180005ac6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180005ac6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005b43`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005d04`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005b43`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005d04`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x180005b10`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x180005b10`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005b25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005b33`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005ce6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005cf4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005b25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005b33`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005ce6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005cf4`

## pseudocode

```c
__int64 __fastcall LookupNames(void *Count, const unsigned __int16 *const *a2, void ***a3)
{
  unsigned __int64 v3; // rsi
  int v7; // ebx
  unsigned int v8; // ebx
  struct _LSA_UNICODE_STRING *i; // rbp
  NTSTATUS v10; // ebx
  NTSTATUS v11; // eax
  void *v12; // rcx
  unsigned int j; // r14d
  __int64 v14; // r12
  DWORD LengthSid; // r13d
  void *v16; // rdx
  signed int LastError; // eax
  __int64 k; // r14
  void *v19; // rcx
  PVOID PolicyHandle; // [rsp+30h] [rbp-78h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-68h] BYREF
  PLSA_UNICODE_STRING Names; // [rsp+C0h] [rbp+18h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+C8h] [rbp+20h] BYREF

  v3 = (unsigned int)Count;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  Names = 0;
  ReferencedDomains = 0;
  if ( !is_mul_ok((unsigned int)Count, 0x10u) )
    return (unsigned int)-2147024362;
  v7 = CTCoAllocPolicy::Alloc(Count, 1u, 16LL * (unsigned int)Count, (void **)&Names);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v8 = 0;
  for ( i = Names; v8 < (unsigned int)v3; ++v8 )
    RtlInitUnicodeString((PUNICODE_STRING)&i[v8], a2[v8]);
  v10 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v10 < 0 )
  {
    v7 = v10 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
        (unsigned int)v7);
    goto LABEL_44;
  }
  ReferencedDomains = 0;
  Names = 0;
  v11 = LsaLookupNames2(PolicyHandle, 0x80000000, v3, i, &ReferencedDomains, (PLSA_TRANSLATED_SID2 *)&Names);
  if ( v11 == -1073741709 )
  {
    LsaFreeMemory(ReferencedDomains);
    LsaFreeMemory(Names);
    v7 = -805306253;
    LsaClose(PolicyHandle);
    goto LABEL_44;
  }
  if ( v11 < 0 )
  {
    v7 = v11 | 0x10000000;
    if ( v11 == -1073741427 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
        (unsigned int)v7);
    }
    goto LABEL_40;
  }
  *a3 = 0;
  if ( !is_mul_ok(v3, 8u) )
  {
    v7 = -2147024362;
    goto LABEL_39;
  }
  v7 = CTCoAllocPolicy::Alloc(v12, 1u, 8 * v3, (void **)a3);
  if ( v7 < 0 )
    goto LABEL_39;
  for ( j = 0; ; ++j )
  {
    if ( j >= (unsigned int)v3 )
      goto LABEL_39;
    v14 = 24LL * j;
    if ( (unsigned int)(*(_DWORD *)((char *)&Names->Length + v14) - 7) <= 1 )
    {
      (*a3)[j] = 0;
      continue;
    }
    LengthSid = GetLengthSid(*(PSID *)((char *)&Names->Buffer + v14));
    (*a3)[j] = CoTaskMemAlloc(LengthSid);
    v16 = (*a3)[j];
    if ( !v16 )
    {
      v7 = -2147024882;
LABEL_33:
      for ( k = 0; (unsigned int)k < (unsigned int)v3; k = (unsigned int)(k + 1) )
      {
        v19 = (*a3)[k];
        if ( v19 )
          CoTaskMemFree(v19);
      }
      CoTaskMemFree(*a3);
      *a3 = 0;
      goto LABEL_39;
    }
    if ( !CopySid(LengthSid, v16, *(PSID *)((char *)&Names->Buffer + v14)) )
      break;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_33;
LABEL_39:
  LsaFreeMemory(ReferencedDomains);
  LsaFreeMemory(Names);
LABEL_40:
  LsaClose(PolicyHandle);
LABEL_44:
  CoTaskMemFree(i);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800059f0  push    rsi
0x1800059f2  push    rdi
0x1800059f3  push    r13
0x1800059f5  push    r15
0x1800059f7  sub     rsp, 88h
0x1800059fe  xorps   xmm0, xmm0
0x180005a01  mov     esi, ecx
0x180005a03  xor     r13d, r13d
0x180005a06  mov     rdi, r8
0x180005a09  mov     [rsp+0A8h+PolicyHandle], r13
0x180005a0e  mov     r15, rdx
0x180005a11  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180005a16  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x180005a1b  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005a20  test    r8, r8
0x180005a23  jnz     short loc_180005A2F
0x180005a25  mov     eax, 80004003h
0x180005a2a  jmp     loc_180005D68
0x180005a2f  mov     eax, 10h
0x180005a34  mov     [rsp+0A8h+arg_0], rbx
0x180005a3c  mul     rsi
0x180005a3f  mov     [rsp+0A8h+var_38], r14
0x180005a44  mov     r14, rsi
0x180005a47  mov     [r8], r13
0x180005a4a  mov     [rsp+0A8h+Names], r13
0x180005a52  mov     [rsp+0A8h+arg_18], r13
0x180005a5a  test    rdx, rdx
0x180005a5d  jnz     loc_180005D54
0x180005a63  lea     r9, [rsp+0A8h+Names]; void **
0x180005a6b  mov     r8, rax; unsigned __int64
0x180005a6e  mov     edx, 1; unsigned int
0x180005a73  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180005a78  mov     ebx, eax
0x180005a7a  test    eax, eax
0x180005a7c  js      loc_180005D59
0x180005a82  mov     [rsp+0A8h+var_28], rbp
0x180005a8a  mov     ebx, r13d
0x180005a8d  mov     rbp, [rsp+0A8h+Names]
0x180005a95  test    esi, esi
0x180005a97  jz      short loc_180005AB4
0x180005a99  mov     edx, ebx
0x180005a9b  mov     ecx, ebx
0x180005a9d  shl     rcx, 4
0x180005aa1  add     rcx, rbp; DestinationString
0x180005aa4  mov     rdx, [r15+rdx*8]; SourceString
0x180005aa8  call    cs:__imp_RtlInitUnicodeString
0x180005aae  inc     ebx
0x180005ab0  cmp     ebx, esi
0x180005ab2  jb      short loc_180005A99
0x180005ab4  lea     r9, [rsp+0A8h+PolicyHandle]; PolicyHandle
0x180005ab9  mov     r8d, 800h; DesiredAccess
0x180005abf  lea     rdx, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180005ac4  xor     ecx, ecx; SystemName
0x180005ac6  call    cs:__imp_LsaOpenPolicy
0x180005acc  mov     ebx, eax
0x180005ace  test    eax, eax
0x180005ad0  js      loc_180005D0C
0x180005ad6  mov     rcx, [rsp+0A8h+PolicyHandle]; PolicyHandle
0x180005adb  lea     rax, [rsp+0A8h+Names]
0x180005ae3  mov     [rsp+0A8h+Sids], rax; Sids
0x180005ae8  mov     r9, rbp; Names
0x180005aeb  lea     rax, [rsp+0A8h+arg_18]
0x180005af3  mov     [rsp+0A8h+arg_18], r13
0x180005afb  mov     r8d, esi; Count
0x180005afe  mov     [rsp+0A8h+ReferencedDomains], rax; ReferencedDomains
0x180005b03  mov     edx, 80000000h; Flags
0x180005b08  mov     [rsp+0A8h+Names], r13
0x180005b10  call    cs:__imp_LsaLookupNames2
0x180005b16  cmp     eax, 0C0000073h
0x180005b1b  jnz     short loc_180005B4E
0x180005b1d  mov     rcx, [rsp+0A8h+arg_18]; Buffer
0x180005b25  call    cs:__imp_LsaFreeMemory
0x180005b2b  mov     rcx, [rsp+0A8h+Names]; Buffer
0x180005b33  call    cs:__imp_LsaFreeMemory
0x180005b39  mov     rcx, [rsp+0A8h+PolicyHandle]; ObjectHandle
0x180005b3e  mov     ebx, 0D0000073h
0x180005b43  call    cs:__imp_LsaClose
0x180005b49  jmp     loc_180005D41
0x180005b4e  test    eax, eax
0x180005b50  jns     short loc_180005BD1
0x180005b52  mov     ebx, eax
0x180005b54  bts     ebx, 1Ch
0x180005b58  cmp     eax, 0C000018Dh
0x180005b5d  jnz     short loc_180005B93
0x180005b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b66  lea     rax, WPP_GLOBAL_Control
0x180005b6d  cmp     rcx, rax
0x180005b70  jz      loc_180005CFF
0x180005b76  test    byte ptr [rcx+1Ch], 4
0x180005b7a  jz      loc_180005CFF
0x180005b80  mov     rcx, [rcx+10h]
0x180005b84  mov     edx, 28h ; '('
0x180005b89  call    WPP_SF_
0x180005b8e  jmp     loc_180005CFF
0x180005b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b9a  lea     rax, WPP_GLOBAL_Control
0x180005ba1  cmp     rcx, rax
0x180005ba4  jz      loc_180005CFF
0x180005baa  test    byte ptr [rcx+1Ch], 2
0x180005bae  jz      loc_180005CFF
0x180005bb4  mov     rcx, [rcx+10h]
0x180005bb8  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180005bbf  mov     edx, 29h ; ')'
0x180005bc4  mov     r9d, ebx
0x180005bc7  call    WPP_SF_d
0x180005bcc  jmp     loc_180005CFF
0x180005bd1  mov     eax, 8
0x180005bd6  mov     [rsp+0A8h+var_30], r12
0x180005bdb  mul     r14
0x180005bde  mov     [rdi], r13
0x180005be1  test    rdx, rdx
0x180005be4  jnz     loc_180005CD9
0x180005bea  mov     r9, rdi; void **
0x180005bed  mov     r8, rax; unsigned __int64
0x180005bf0  mov     edx, 1; unsigned int
0x180005bf5  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180005bfa  mov     ebx, eax
0x180005bfc  test    eax, eax
0x180005bfe  js      loc_180005CDE
0x180005c04  mov     r14d, r13d
0x180005c07  cmp     r14d, esi
0x180005c0a  jnb     loc_180005CDE
0x180005c10  mov     rcx, [rsp+0A8h+Names]
0x180005c18  mov     r15d, r14d
0x180005c1b  lea     rax, [r15+r15*2]
0x180005c1f  lea     r12, ds:0[rax*8]
0x180005c27  mov     eax, [rcx+rax*8]
0x180005c2a  sub     eax, 7
0x180005c2d  cmp     eax, 1
0x180005c30  jbe     short loc_180005C7A
0x180005c32  mov     rcx, [rcx+r12+8]; pSid
0x180005c37  call    cs:__imp_GetLengthSid
0x180005c3d  mov     ecx, eax; cb
0x180005c3f  mov     r13d, eax
0x180005c42  call    cs:__imp_CoTaskMemAlloc
0x180005c48  mov     rcx, [rdi]
0x180005c4b  mov     [rcx+r15*8], rax
0x180005c4f  mov     rcx, [rdi]
0x180005c52  mov     rdx, [rcx+r15*8]; pDestinationSid
0x180005c56  test    rdx, rdx
0x180005c59  jz      short loc_180005CA1
0x180005c5b  mov     r8, [rsp+0A8h+Names]
0x180005c63  mov     ecx, r13d; nDestinationSidLength
0x180005c66  mov     r8, [r12+r8+8]; pSourceSid
0x180005c6b  call    cs:__imp_CopySid
0x180005c71  test    eax, eax
0x180005c73  jz      short loc_180005C86
0x180005c75  xor     r13d, r13d
0x180005c78  jmp     short loc_180005C81
0x180005c7a  mov     rax, [rdi]
0x180005c7d  mov     [rax+r15*8], r13
0x180005c81  inc     r14d
0x180005c84  jmp     short loc_180005C07
0x180005c86  call    cs:__imp_GetLastError
0x180005c8c  mov     ebx, eax
0x180005c8e  test    eax, eax
0x180005c90  jle     short loc_180005C9B
0x180005c92  movzx   ebx, ax
0x180005c95  or      ebx, 80070000h
0x180005c9b  test    ebx, ebx
0x180005c9d  jns     short loc_180005CDE
0x180005c9f  jmp     short loc_180005CA6
0x180005ca1  mov     ebx, 8007000Eh
0x180005ca6  xor     r14d, r14d
0x180005ca9  test    esi, esi
0x180005cab  jz      short loc_180005CC7
0x180005cad  mov     rax, [rdi]
0x180005cb0  mov     rcx, [rax+r14*8]; pv
0x180005cb4  test    rcx, rcx
0x180005cb7  jz      short loc_180005CBF
0x180005cb9  call    cs:__imp_CoTaskMemFree
0x180005cbf  inc     r14d
0x180005cc2  cmp     r14d, esi
0x180005cc5  jb      short loc_180005CAD
0x180005cc7  mov     rcx, [rdi]; pv
0x180005cca  call    cs:__imp_CoTaskMemFree
0x180005cd0  mov     qword ptr [rdi], 0
0x180005cd7  jmp     short loc_180005CDE
0x180005cd9  mov     ebx, 80070216h
0x180005cde  mov     rcx, [rsp+0A8h+arg_18]; Buffer
0x180005ce6  call    cs:__imp_LsaFreeMemory
0x180005cec  mov     rcx, [rsp+0A8h+Names]; Buffer
0x180005cf4  call    cs:__imp_LsaFreeMemory
0x180005cfa  mov     r12, [rsp+0A8h+var_30]
0x180005cff  mov     rcx, [rsp+0A8h+PolicyHandle]; ObjectHandle
0x180005d04  call    cs:__imp_LsaClose
0x180005d0a  jmp     short loc_180005D41
0x180005d0c  bts     ebx, 1Ch
0x180005d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d17  lea     rax, WPP_GLOBAL_Control
0x180005d1e  cmp     rcx, rax
0x180005d21  jz      short loc_180005D41
0x180005d23  test    byte ptr [rcx+1Ch], 2
0x180005d27  jz      short loc_180005D41
0x180005d29  mov     rcx, [rcx+10h]
0x180005d2d  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180005d34  mov     edx, 2Ah ; '*'
0x180005d39  mov     r9d, ebx
0x180005d3c  call    WPP_SF_d
0x180005d41  mov     rcx, rbp; pv
0x180005d44  call    cs:__imp_CoTaskMemFree
0x180005d4a  mov     rbp, [rsp+0A8h+var_28]
0x180005d52  jmp     short loc_180005D59
0x180005d54  mov     ebx, 80070216h
0x180005d59  mov     r14, [rsp+0A8h+var_38]
0x180005d5e  mov     eax, ebx
0x180005d60  mov     rbx, [rsp+0A8h+arg_0]
0x180005d68  add     rsp, 88h
0x180005d6f  pop     r15
0x180005d71  pop     r13
0x180005d73  pop     rdi
0x180005d74  pop     rsi
0x180005d75  retn
```
