# CSGetAccountDomainSid

- ea: `0x180008cac`
- end: `0x180008e44`
- name: `CSGetAccountDomainSid`
- size: `408`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008b48`

## callees

- `0x180008cac`
- `0x1800090dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d89`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008d3d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008d61`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008d3d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008d61`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008d6f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008d6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d7c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180008df5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180008df5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180008db4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180008db4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180008d20`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180008d20`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180008d03`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180008d03`

## pseudocode

```c
__int64 __fastcall CSGetAccountDomainSid(LPVOID *a1)
{
  unsigned int v2; // ebx
  NTSTATUS v3; // ebx
  NTSTATUS v4; // ebx
  void *v5; // rcx
  DWORD LengthSid; // eax
  LPVOID v7; // rax
  void *v8; // rsi
  void *v9; // rbx
  DWORD v10; // eax
  signed int LastError; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+70h] [rbp+20h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp+28h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 )
  {
    *a1 = 0;
    v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
    if ( v3 < 0 )
    {
      v2 = v3 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v2);
    }
    else
    {
      v4 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
      if ( v4 < 0 )
      {
        v2 = v4 | 0x10000000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v2);
      }
      else
      {
        v5 = (void *)*((_QWORD *)Buffer + 2);
        if ( v5 )
        {
          LengthSid = GetLengthSid(v5);
          v7 = CoTaskMemAlloc(LengthSid);
          *a1 = v7;
          v8 = v7;
          if ( v7 )
          {
            v9 = (void *)*((_QWORD *)Buffer + 2);
            v10 = GetLengthSid(v9);
            if ( CopySid(v10, v8, v9) )
            {
              v2 = 0;
            }
            else
            {
              CoTaskMemFree(*a1);
              *a1 = 0;
              LastError = GetLastError();
              v2 = LastError;
              if ( LastError > 0 )
                v2 = (unsigned __int16)LastError | 0x80070000;
            }
          }
          else
          {
            v2 = -2147024882;
          }
        }
        else
        {
          v2 = -2147467259;
        }
        LsaFreeMemory(Buffer);
      }
      LsaClose(PolicyHandle);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v2;
}

```

## disassembly

```asm
0x180008cac  mov     [rsp-18h+arg_10], rbx
0x180008cb1  push    rbp
0x180008cb2  push    rsi
0x180008cb3  push    rdi
0x180008cb4  mov     rbp, rsp
0x180008cb7  sub     rsp, 50h
0x180008cbb  mov     [rbp+PolicyHandle], 0
0x180008cc3  xorps   xmm0, xmm0
0x180008cc6  mov     [rbp+Buffer], 0
0x180008cce  mov     rdi, rcx
0x180008cd1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180008cd5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180008cd9  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008cdd  test    rcx, rcx
0x180008ce0  jnz     short loc_180008CEC
0x180008ce2  mov     ebx, 80004003h
0x180008ce7  jmp     loc_180008E32
0x180008cec  mov     qword ptr [rcx], 0
0x180008cf3  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180008cf7  xor     ecx, ecx; SystemName
0x180008cf9  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180008cfd  mov     r8d, 1; DesiredAccess
0x180008d03  call    cs:__imp_LsaOpenPolicy
0x180008d09  mov     ebx, eax
0x180008d0b  test    eax, eax
0x180008d0d  js      loc_180008DFD
0x180008d13  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180008d17  lea     r8, [rbp+Buffer]; Buffer
0x180008d1b  mov     edx, 5; InformationClass
0x180008d20  call    cs:__imp_LsaQueryInformationPolicy
0x180008d26  mov     ebx, eax
0x180008d28  test    eax, eax
0x180008d2a  js      loc_180008DBC
0x180008d30  mov     rax, [rbp+Buffer]
0x180008d34  mov     rcx, [rax+10h]; pSid
0x180008d38  test    rcx, rcx
0x180008d3b  jz      short loc_180008DAB
0x180008d3d  call    cs:__imp_GetLengthSid
0x180008d43  mov     ecx, eax; cb
0x180008d45  call    cs:__imp_CoTaskMemAlloc
0x180008d4b  mov     [rdi], rax
0x180008d4e  mov     rsi, rax
0x180008d51  test    rax, rax
0x180008d54  jz      short loc_180008DA4
0x180008d56  mov     rax, [rbp+Buffer]
0x180008d5a  mov     rbx, [rax+10h]
0x180008d5e  mov     rcx, rbx; pSid
0x180008d61  call    cs:__imp_GetLengthSid
0x180008d67  mov     r8, rbx; pSourceSid
0x180008d6a  mov     rdx, rsi; pDestinationSid
0x180008d6d  mov     ecx, eax; nDestinationSidLength
0x180008d6f  call    cs:__imp_CopySid
0x180008d75  test    eax, eax
0x180008d77  jnz     short loc_180008DA0
0x180008d79  mov     rcx, [rdi]; pv
0x180008d7c  call    cs:__imp_CoTaskMemFree
0x180008d82  mov     qword ptr [rdi], 0
0x180008d89  call    cs:__imp_GetLastError
0x180008d8f  mov     ebx, eax
0x180008d91  test    eax, eax
0x180008d93  jle     short loc_180008DB0
0x180008d95  movzx   ebx, ax
0x180008d98  or      ebx, 80070000h
0x180008d9e  jmp     short loc_180008DB0
0x180008da0  xor     ebx, ebx
0x180008da2  jmp     short loc_180008DB0
0x180008da4  mov     ebx, 8007000Eh
0x180008da9  jmp     short loc_180008DB0
0x180008dab  mov     ebx, 80004005h
0x180008db0  mov     rcx, [rbp+Buffer]; Buffer
0x180008db4  call    cs:__imp_LsaFreeMemory
0x180008dba  jmp     short loc_180008DF1
0x180008dbc  bts     ebx, 1Ch
0x180008dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dc7  lea     rax, WPP_GLOBAL_Control
0x180008dce  cmp     rcx, rax
0x180008dd1  jz      short loc_180008DF1
0x180008dd3  test    byte ptr [rcx+1Ch], 2
0x180008dd7  jz      short loc_180008DF1
0x180008dd9  mov     rcx, [rcx+10h]
0x180008ddd  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180008de4  mov     edx, 1Dh
0x180008de9  mov     r9d, ebx
0x180008dec  call    WPP_SF_D
0x180008df1  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180008df5  call    cs:__imp_LsaClose
0x180008dfb  jmp     short loc_180008E32
0x180008dfd  bts     ebx, 1Ch
0x180008e01  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e08  lea     rax, WPP_GLOBAL_Control
0x180008e0f  cmp     rcx, rax
0x180008e12  jz      short loc_180008E32
0x180008e14  test    byte ptr [rcx+1Ch], 2
0x180008e18  jz      short loc_180008E32
0x180008e1a  mov     rcx, [rcx+10h]
0x180008e1e  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180008e25  mov     edx, 1Eh
0x180008e2a  mov     r9d, ebx
0x180008e2d  call    WPP_SF_D
0x180008e32  mov     eax, ebx
0x180008e34  mov     rbx, [rsp+50h+arg_10]
0x180008e3c  add     rsp, 50h
0x180008e40  pop     rdi
0x180008e41  pop     rsi
0x180008e42  pop     rbp
0x180008e43  retn
```
