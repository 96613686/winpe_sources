# SsRefreshParameters

- ea: `0x180025e94`
- end: `0x180025fbd`
- name: `SsRefreshParameters`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180001764`
- `0x180014880`

## callees

- `0x18000a880`
- `0x180025e94`

## string_xrefs

- `0x180025ea0`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x180025f09`: `EnableIpV6LinkLocal`
- `0x180025ede`: `EnableIpV4LinkLocal`
- `0x180025f90`: `AuditClientCertificateAccess`

## pseudocode

```c
__int64 SsRefreshParameters()
{
  __int64 result; // rax
  int v1; // [rsp+50h] [rbp+28h] BYREF

  v1 = 0;
  if ( (unsigned int)QueryRegDWord(
                       L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                       L"EnableCaAlways",
                       &v1)
    || (dword_18005E4B8 = 1, !v1) )
  {
    dword_18005E4B8 = 0;
  }
  v1 = 0;
  if ( (unsigned int)QueryRegDWord(
                       L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                       L"EnableIpV4LinkLocal",
                       &v1)
    || (dword_18005E4BC = 0, v1) )
  {
    dword_18005E4BC = 1;
  }
  v1 = 0;
  if ( (unsigned int)QueryRegDWord(
                       L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                       L"EnableIpV6LinkLocal",
                       &v1)
    || (dword_18005E4C4 = 0, v1) )
  {
    dword_18005E4C4 = 1;
  }
  v1 = 0;
  if ( (unsigned int)QueryRegDWord(
                       L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                       L"CertificateExpirationWarningThreshold",
                       &v1)
    || (dword_18005E4C0 = v1) == 0 )
  {
    dword_18005E4C0 = 5184000;
  }
  v1 = 0;
  if ( (unsigned int)QueryRegDWord(
                       L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                       L"EnforceNonClusteredShareOnClusteredDisk",
                       &v1)
    || (dword_18005E4C8 = 1, !v1) )
  {
    dword_18005E4C8 = 0;
  }
  v1 = 0;
  result = QueryRegDWord(
             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
             L"AuditClientCertificateAccess",
             &v1);
  if ( (_DWORD)result || (dword_18005E4CC = 1, !v1) )
    dword_18005E4CC = 0;
  return result;
}

```

## disassembly

```asm
0x180025e94  push    rbp
0x180025e96  push    rbx
0x180025e97  push    rsi
0x180025e98  push    rdi
0x180025e99  mov     rbp, rsp
0x180025e9c  sub     rsp, 28h
0x180025ea0  lea     rsi, aRegistryMachin_1; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180025ea7  xor     ebx, ebx
0x180025ea9  mov     rcx, rsi; SourceString
0x180025eac  mov     [rbp+arg_0], ebx
0x180025eaf  lea     r8, [rbp+arg_0]
0x180025eb3  lea     rdx, aEnablecaalways; "EnableCaAlways"
0x180025eba  call    QueryRegDWord
0x180025ebf  lea     edi, [rbx+1]
0x180025ec2  test    eax, eax
0x180025ec4  jnz     short loc_180025ED1
0x180025ec6  mov     cs:dword_18005E4B8, edi
0x180025ecc  cmp     [rbp+arg_0], ebx
0x180025ecf  jnz     short loc_180025ED7
0x180025ed1  mov     cs:dword_18005E4B8, ebx
0x180025ed7  lea     r8, [rbp+arg_0]
0x180025edb  mov     [rbp+arg_0], ebx
0x180025ede  lea     rdx, aEnableipv4link; "EnableIpV4LinkLocal"
0x180025ee5  mov     rcx, rsi; SourceString
0x180025ee8  call    QueryRegDWord
0x180025eed  test    eax, eax
0x180025eef  jnz     short loc_180025EFC
0x180025ef1  mov     cs:dword_18005E4BC, ebx
0x180025ef7  cmp     [rbp+arg_0], ebx
0x180025efa  jz      short loc_180025F02
0x180025efc  mov     cs:dword_18005E4BC, edi
0x180025f02  lea     r8, [rbp+arg_0]
0x180025f06  mov     [rbp+arg_0], ebx
0x180025f09  lea     rdx, aEnableipv6link; "EnableIpV6LinkLocal"
0x180025f10  mov     rcx, rsi; SourceString
0x180025f13  call    QueryRegDWord
0x180025f18  test    eax, eax
0x180025f1a  jnz     short loc_180025F27
0x180025f1c  mov     cs:dword_18005E4C4, ebx
0x180025f22  cmp     [rbp+arg_0], ebx
0x180025f25  jz      short loc_180025F2D
0x180025f27  mov     cs:dword_18005E4C4, edi
0x180025f2d  lea     r8, [rbp+arg_0]
0x180025f31  mov     [rbp+arg_0], ebx
0x180025f34  lea     rdx, aCertificateexp; "CertificateExpirationWarningThreshold"
0x180025f3b  mov     rcx, rsi; SourceString
0x180025f3e  call    QueryRegDWord
0x180025f43  test    eax, eax
0x180025f45  jnz     short loc_180025F54
0x180025f47  mov     eax, [rbp+arg_0]
0x180025f4a  mov     cs:dword_18005E4C0, eax
0x180025f50  test    eax, eax
0x180025f52  jnz     short loc_180025F5E
0x180025f54  mov     cs:dword_18005E4C0, 4F1A00h
0x180025f5e  lea     r8, [rbp+arg_0]
0x180025f62  mov     [rbp+arg_0], ebx
0x180025f65  lea     rdx, aEnforcenonclus; "EnforceNonClusteredShareOnClusteredDisk"
0x180025f6c  mov     rcx, rsi; SourceString
0x180025f6f  call    QueryRegDWord
0x180025f74  test    eax, eax
0x180025f76  jnz     short loc_180025F83
0x180025f78  mov     cs:dword_18005E4C8, edi
0x180025f7e  cmp     [rbp+arg_0], ebx
0x180025f81  jnz     short loc_180025F89
0x180025f83  mov     cs:dword_18005E4C8, ebx
0x180025f89  lea     r8, [rbp+arg_0]
0x180025f8d  mov     [rbp+arg_0], ebx
0x180025f90  lea     rdx, aAuditclientcer; "AuditClientCertificateAccess"
0x180025f97  mov     rcx, rsi; SourceString
0x180025f9a  call    QueryRegDWord
0x180025f9f  test    eax, eax
0x180025fa1  jnz     short loc_180025FAE
0x180025fa3  mov     cs:dword_18005E4CC, edi
0x180025fa9  cmp     [rbp+arg_0], ebx
0x180025fac  jnz     short loc_180025FB4
0x180025fae  mov     cs:dword_18005E4CC, ebx
0x180025fb4  add     rsp, 28h
0x180025fb8  pop     rdi
0x180025fb9  pop     rsi
0x180025fba  pop     rbx
0x180025fbb  pop     rbp
0x180025fbc  retn
```
