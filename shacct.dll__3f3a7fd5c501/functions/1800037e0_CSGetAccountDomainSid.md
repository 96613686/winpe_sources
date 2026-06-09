# CSGetAccountDomainSid

- ea: `0x1800037e0`
- end: `0x1800039d7`
- name: `CSGetAccountDomainSid`
- size: `503`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180001e70`
- `0x1800020d0`
- `0x180002bf0`
- `0x180002ff0`
- `0x180003660`
- `0x180003b10`
- `0x180003c30`
- `0x180003e20`
- `0x180008ad0`
- `0x18000fe00`
- `0x180010230`
- `0x180011150`
- `0x180011640`
- `0x180011e80`

## callees

- `0x1800037e0`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038c3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800038ad`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800038ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000387a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000389f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000387a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000389f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800038ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800038ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003882`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180003834`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180003834`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800038ed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180003929`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000397a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800038ed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180003929`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000397a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180003853`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180003853`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800038dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180003919`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800038dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180003919`

## pseudocode

```c
__int64 __fastcall CSGetAccountDomainSid(LPVOID *a1)
{
  NTSTATUS v3; // ebx
  NTSTATUS v4; // ebx
  void *v5; // rcx
  DWORD LengthSid; // eax
  LPVOID v7; // rax
  void *v8; // rsi
  void *v9; // rbx
  DWORD v10; // eax
  signed int LastError; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-48h] BYREF
  PVOID Buffer; // [rsp+70h] [rbp+8h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp+10h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v3 < 0 )
  {
    v15 = v3 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v15);
    return v15;
  }
  else
  {
    v4 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    if ( v4 < 0 )
    {
      v14 = v4 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v14);
      LsaClose(PolicyHandle);
      return v14;
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
            v12 = 0;
          }
          else
          {
            CoTaskMemFree(*a1);
            *a1 = 0;
            LastError = GetLastError();
            v12 = LastError;
            if ( LastError > 0 )
            {
              v13 = (unsigned __int16)LastError | 0x80070000;
              LsaFreeMemory(Buffer);
              LsaClose(PolicyHandle);
              return v13;
            }
          }
        }
        else
        {
          v12 = -2147024882;
        }
      }
      else
      {
        v12 = -2147467259;
      }
      LsaFreeMemory(Buffer);
      LsaClose(PolicyHandle);
      return v12;
    }
  }
}

```

## disassembly

```asm
0x1800037e0  push    rbp
0x1800037e2  push    rdi
0x1800037e3  sub     rsp, 58h
0x1800037e7  xor     ebp, ebp
0x1800037e9  xorps   xmm0, xmm0
0x1800037ec  mov     [rsp+68h+PolicyHandle], rbp
0x1800037f1  mov     rdi, rcx
0x1800037f4  mov     [rsp+68h+Buffer], rbp
0x1800037f9  movups  xmmword ptr [rsp+68h+ObjectAttributes.Length], xmm0
0x1800037fe  movups  xmmword ptr [rsp+68h+ObjectAttributes.ObjectName], xmm0
0x180003803  movups  xmmword ptr [rsp+68h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003808  test    rcx, rcx
0x18000380b  jnz     short loc_180003817
0x18000380d  mov     eax, 80004003h
0x180003812  jmp     loc_1800039D0
0x180003817  mov     [rcx], rbp
0x18000381a  lea     r9, [rsp+68h+PolicyHandle]; PolicyHandle
0x18000381f  xor     ecx, ecx; SystemName
0x180003821  mov     [rsp+68h+arg_10], rbx
0x180003829  mov     r8d, 1; DesiredAccess
0x18000382f  lea     rdx, [rsp+68h+ObjectAttributes]; ObjectAttributes
0x180003834  call    cs:__imp_LsaOpenPolicy
0x18000383a  mov     ebx, eax
0x18000383c  test    eax, eax
0x18000383e  js      loc_180003991
0x180003844  mov     rcx, [rsp+68h+PolicyHandle]; PolicyHandle
0x180003849  lea     r8, [rsp+68h+Buffer]; Buffer
0x18000384e  mov     edx, 5; InformationClass
0x180003853  call    cs:__imp_LsaQueryInformationPolicy
0x180003859  mov     ebx, eax
0x18000385b  test    eax, eax
0x18000385d  js      loc_180003940
0x180003863  mov     rax, [rsp+68h+Buffer]
0x180003868  mov     [rsp+68h+var_18], rsi
0x18000386d  mov     rcx, [rax+10h]; pSid
0x180003871  test    rcx, rcx
0x180003874  jz      loc_18000390F
0x18000387a  call    cs:__imp_GetLengthSid
0x180003880  mov     ecx, eax; cb
0x180003882  call    cs:__imp_CoTaskMemAlloc
0x180003888  mov     [rdi], rax
0x18000388b  mov     rsi, rax
0x18000388e  test    rax, rax
0x180003891  jz      short loc_180003908
0x180003893  mov     rcx, [rsp+68h+Buffer]
0x180003898  mov     rbx, [rcx+10h]
0x18000389c  mov     rcx, rbx; pSid
0x18000389f  call    cs:__imp_GetLengthSid
0x1800038a5  mov     r8, rbx; pSourceSid
0x1800038a8  mov     rdx, rsi; pDestinationSid
0x1800038ab  mov     ecx, eax; nDestinationSidLength
0x1800038ad  call    cs:__imp_CopySid
0x1800038b3  test    eax, eax
0x1800038b5  jnz     short loc_180003904
0x1800038b7  mov     rcx, [rdi]; pv
0x1800038ba  call    cs:__imp_CoTaskMemFree
0x1800038c0  mov     [rdi], rbp
0x1800038c3  call    cs:__imp_GetLastError
0x1800038c9  mov     ebx, eax
0x1800038cb  test    eax, eax
0x1800038cd  jle     short loc_180003914
0x1800038cf  mov     rcx, [rsp+68h+Buffer]; Buffer
0x1800038d4  movzx   ebx, ax
0x1800038d7  or      ebx, 80070000h
0x1800038dd  call    cs:__imp_LsaFreeMemory
0x1800038e3  mov     rcx, [rsp+68h+PolicyHandle]; ObjectHandle
0x1800038e8  mov     rsi, [rsp+68h+var_18]
0x1800038ed  call    cs:__imp_LsaClose
0x1800038f3  mov     eax, ebx
0x1800038f5  mov     rbx, [rsp+68h+arg_10]
0x1800038fd  add     rsp, 58h
0x180003901  pop     rdi
0x180003902  pop     rbp
0x180003903  retn
0x180003904  mov     ebx, ebp
0x180003906  jmp     short loc_180003914
0x180003908  mov     ebx, 8007000Eh
0x18000390d  jmp     short loc_180003914
0x18000390f  mov     ebx, 80004005h
0x180003914  mov     rcx, [rsp+68h+Buffer]; Buffer
0x180003919  call    cs:__imp_LsaFreeMemory
0x18000391f  mov     rcx, [rsp+68h+PolicyHandle]; ObjectHandle
0x180003924  mov     rsi, [rsp+68h+var_18]
0x180003929  call    cs:__imp_LsaClose
0x18000392f  mov     eax, ebx
0x180003931  mov     rbx, [rsp+68h+arg_10]
0x180003939  add     rsp, 58h
0x18000393d  pop     rdi
0x18000393e  pop     rbp
0x18000393f  retn
0x180003940  bts     ebx, 1Ch
0x180003944  mov     rcx, cs:WPP_GLOBAL_Control
0x18000394b  lea     rax, WPP_GLOBAL_Control
0x180003952  cmp     rcx, rax
0x180003955  jz      short loc_180003975
0x180003957  test    byte ptr [rcx+1Ch], 2
0x18000395b  jz      short loc_180003975
0x18000395d  mov     rcx, [rcx+10h]
0x180003961  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180003968  mov     edx, 1Dh
0x18000396d  mov     r9d, ebx
0x180003970  call    WPP_SF_d
0x180003975  mov     rcx, [rsp+68h+PolicyHandle]; ObjectHandle
0x18000397a  call    cs:__imp_LsaClose
0x180003980  mov     eax, ebx
0x180003982  mov     rbx, [rsp+68h+arg_10]
0x18000398a  add     rsp, 58h
0x18000398e  pop     rdi
0x18000398f  pop     rbp
0x180003990  retn
0x180003991  bts     ebx, 1Ch
0x180003995  mov     rcx, cs:WPP_GLOBAL_Control
0x18000399c  lea     rax, WPP_GLOBAL_Control
0x1800039a3  cmp     rcx, rax
0x1800039a6  jz      short loc_1800039C6
0x1800039a8  test    byte ptr [rcx+1Ch], 2
0x1800039ac  jz      short loc_1800039C6
0x1800039ae  mov     rcx, [rcx+10h]
0x1800039b2  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x1800039b9  mov     edx, 1Eh
0x1800039be  mov     r9d, ebx
0x1800039c1  call    WPP_SF_d
0x1800039c6  mov     eax, ebx
0x1800039c8  mov     rbx, [rsp+68h+arg_10]
0x1800039d0  add     rsp, 58h
0x1800039d4  pop     rdi
0x1800039d5  pop     rbp
0x1800039d6  retn
```
