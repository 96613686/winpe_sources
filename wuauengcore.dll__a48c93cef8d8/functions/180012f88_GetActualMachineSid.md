# GetActualMachineSid

- ea: `0x180012f88`
- end: `0x180013149`
- name: `GetActualMachineSid`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800106d0`

## callees

- `0x180012f88`
- `0x180113a10`
- `0x180113ae8`
- `0x18012b618`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001307f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001307f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013039`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013039`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001304d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001304d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013075`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013075`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800130ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800130ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001310b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001310b`
- `ntdll!RtlNtStatusToDosError` at `0x180012ffe`
- `ntdll!RtlNtStatusToDosError` at `0x180012ffe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800130a6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800130a6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800130b5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800130b5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180012ff2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180012ff2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180013024`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180013024`

## string_xrefs

- `0x1800130e5`: `Machine SID %ws`

## pseudocode

```c
__int64 __fastcall GetActualMachineSid(_QWORD *a1, _DWORD *a2)
{
  signed int v2; // ebx
  void *v5; // rdi
  unsigned __int64 LengthSid; // r14
  NTSTATUS v7; // eax
  signed int v8; // eax
  void *v9; // rsi
  void *v10; // rax
  signed int LastError; // eax
  PVOID Buffer; // [rsp+40h] [rbp-19h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-11h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-9h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-1h] BYREF

  v2 = 0;
  *a1 = 0;
  *a2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Buffer = 0;
  ObjectAttributes.Length = 48;
  v5 = 0;
  LODWORD(LengthSid) = 0;
  v7 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v7 || (v7 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer)) != 0 )
  {
    v8 = RtlNtStatusToDosError(v7);
    v2 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v2 = v8;
  }
  else
  {
    v9 = (void *)*((_QWORD *)Buffer + 2);
    if ( IsValidSid(v9) )
    {
      LengthSid = GetLengthSid(v9);
      v10 = SusAlloc(LengthSid);
      v5 = v10;
      if ( v10 )
      {
        if ( !CopySid(LengthSid, v10, v9) )
        {
          LastError = GetLastError();
          v2 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v2 = LastError;
          if ( v2 >= 0 )
            v2 = -2147418113;
        }
      }
      else
      {
        v2 = -2147024882;
      }
    }
    else
    {
      v2 = -2147024883;
    }
  }
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v2 < 0 )
  {
    SusFree(v5);
  }
  else
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(v5, &StringSid) )
    {
      WUTrace(0, 0, 1, 5, 0, L"Machine SID %ws", StringSid);
      LocalFree(StringSid);
    }
    *a1 = v5;
    *a2 = LengthSid;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180012f88  mov     [rsp-8+arg_10], rbx
0x180012f8d  mov     [rsp-8+arg_18], rsi
0x180012f92  push    rbp
0x180012f93  push    rdi
0x180012f94  push    r12
0x180012f96  push    r14
0x180012f98  push    r15
0x180012f9a  lea     rbp, [rsp-37h]
0x180012f9f  sub     rsp, 90h
0x180012fa6  mov     rax, cs:__security_cookie
0x180012fad  xor     rax, rsp
0x180012fb0  mov     [rbp+57h+var_28], rax
0x180012fb4  xor     ebx, ebx
0x180012fb6  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180012fba  xorps   xmm0, xmm0
0x180012fbd  mov     [rcx], rbx
0x180012fc0  mov     r12, rdx
0x180012fc3  mov     [rdx], ebx
0x180012fc5  mov     r15, rcx
0x180012fc8  mov     [rbp+57h+PolicyHandle], rbx
0x180012fcc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180012fd0  lea     r8d, [rbx+1]; DesiredAccess
0x180012fd4  mov     [rbp+57h+Buffer], rbx
0x180012fd8  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180012fdc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180012fe3  xor     ecx, ecx; SystemName
0x180012fe5  xor     edi, edi
0x180012fe7  xor     r14d, r14d
0x180012fea  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180012fee  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180012ff2  call    cs:__imp_LsaOpenPolicy
0x180012ff8  test    eax, eax
0x180012ffa  jz      short loc_180013017
0x180012ffc  mov     ecx, eax; Status
0x180012ffe  call    cs:__imp_RtlNtStatusToDosError
0x180013004  movzx   ebx, ax
0x180013007  or      ebx, 80070000h
0x18001300d  test    eax, eax
0x18001300f  cmovle  ebx, eax
0x180013012  jmp     loc_18001309D
0x180013017  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18001301b  lea     r8, [rbp+57h+Buffer]; Buffer
0x18001301f  mov     edx, 5; InformationClass
0x180013024  call    cs:__imp_LsaQueryInformationPolicy
0x18001302a  test    eax, eax
0x18001302c  jnz     short loc_180012FFC
0x18001302e  mov     rax, [rbp+57h+Buffer]
0x180013032  mov     rsi, [rax+10h]
0x180013036  mov     rcx, rsi; pSid
0x180013039  call    cs:__imp_IsValidSid
0x18001303f  test    eax, eax
0x180013041  jnz     short loc_18001304A
0x180013043  mov     ebx, 8007000Dh
0x180013048  jmp     short loc_18001309D
0x18001304a  mov     rcx, rsi; pSid
0x18001304d  call    cs:__imp_GetLengthSid
0x180013053  mov     ecx, eax; unsigned __int64
0x180013055  mov     r14d, eax
0x180013058  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18001305d  mov     rdi, rax
0x180013060  test    rax, rax
0x180013063  jnz     short loc_18001306C
0x180013065  mov     ebx, 8007000Eh
0x18001306a  jmp     short loc_18001309D
0x18001306c  mov     r8, rsi; pSourceSid
0x18001306f  mov     rdx, rax; pDestinationSid
0x180013072  mov     ecx, r14d; nDestinationSidLength
0x180013075  call    cs:__imp_CopySid
0x18001307b  test    eax, eax
0x18001307d  jnz     short loc_18001309D
0x18001307f  call    cs:__imp_GetLastError
0x180013085  movzx   ebx, ax
0x180013088  or      ebx, 80070000h
0x18001308e  test    eax, eax
0x180013090  cmovle  ebx, eax
0x180013093  mov     eax, 8000FFFFh
0x180013098  test    ebx, ebx
0x18001309a  cmovns  ebx, eax
0x18001309d  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800130a1  test    rcx, rcx
0x1800130a4  jz      short loc_1800130AC
0x1800130a6  call    cs:__imp_LsaFreeMemory
0x1800130ac  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x1800130b0  test    rcx, rcx
0x1800130b3  jz      short loc_1800130BB
0x1800130b5  call    cs:__imp_LsaClose
0x1800130bb  mov     rcx, rdi; lpMem
0x1800130be  test    ebx, ebx
0x1800130c0  js      short loc_18001311A
0x1800130c2  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800130c6  mov     [rbp+57h+StringSid], 0
0x1800130ce  call    cs:__imp_ConvertSidToStringSidW
0x1800130d4  test    eax, eax
0x1800130d6  jz      short loc_180013111
0x1800130d8  mov     rax, [rbp+57h+StringSid]
0x1800130dc  xor     edx, edx
0x1800130de  mov     [rsp+0B0h+var_80], rax
0x1800130e3  xor     ecx, ecx
0x1800130e5  lea     rax, aMachineSidWs; "Machine SID %ws"
0x1800130ec  mov     [rsp+0B0h+var_88], rax
0x1800130f1  lea     r9d, [rdx+5]
0x1800130f5  mov     [rsp+0B0h+var_90], 0
0x1800130fe  lea     r8d, [rdx+1]
0x180013102  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013107  mov     rcx, [rbp+57h+StringSid]; hMem
0x18001310b  call    cs:__imp_LocalFree
0x180013111  mov     [r15], rdi
0x180013114  mov     [r12], r14d
0x180013118  jmp     short loc_18001311F
0x18001311a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18001311f  mov     eax, ebx
0x180013121  mov     rcx, [rbp+57h+var_28]
0x180013125  xor     rcx, rsp; StackCookie
0x180013128  call    __security_check_cookie
0x18001312d  lea     r11, [rsp+0B0h+var_20]
0x180013135  mov     rbx, [r11+40h]
0x180013139  mov     rsi, [r11+48h]
0x18001313d  mov     rsp, r11
0x180013140  pop     r15
0x180013142  pop     r14
0x180013144  pop     r12
0x180013146  pop     rdi
0x180013147  pop     rbp
0x180013148  retn
```
