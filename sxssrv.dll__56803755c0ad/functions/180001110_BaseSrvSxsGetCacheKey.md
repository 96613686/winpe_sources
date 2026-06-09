# BaseSrvSxsGetCacheKey

- ea: `0x180001110`
- end: `0x18000132e`
- name: `BaseSrvSxsGetCacheKey`
- size: `542`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003170`

## callees

- `0x180001110`
- `0x1800061b0`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800011e4`
- `ntdll!RtlInitUnicodeString` at `0x1800012ac`
- `ntdll!RtlInitUnicodeString` at `0x1800011e4`
- `ntdll!RtlInitUnicodeString` at `0x1800012ac`
- `ntdll!NtOpenKey` at `0x1800012f1`
- `ntdll!NtOpenKey` at `0x1800012f1`
- `ntdll!NtQueryValueKey` at `0x180001219`
- `ntdll!NtQueryValueKey` at `0x180001219`

## string_xrefs

- `0x1800012a0`: `\Registry\MACHINE\Software\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvSxsGetCacheKey(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int16 v4; // ax
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-78h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-70h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-60h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+78h] [rbp-30h] BYREF
  int v10; // [rsp+7Ch] [rbp-2Ch]
  int v11; // [rsp+80h] [rbp-28h]
  __int64 v12; // [rsp+84h] [rbp-24h]

  DestinationString = 0;
  v3 = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)a3 = *(_OWORD *)(a1 + 32);
  *(_OWORD *)(a3 + 24) = *(_OWORD *)(a1 + 136);
  *(_QWORD *)(a3 + 40) = *(_QWORD *)(a1 + 176);
  *(_OWORD *)(a3 + 48) = *(_OWORD *)(a1 + 8);
  *(_WORD *)(a3 + 64) = *(_WORD *)(a1 + 4);
  *(_QWORD *)(a3 + 16) = *(_QWORD *)(a1 + 168);
  if ( a2 )
  {
    *(_OWORD *)(a3 + 72) = *(_OWORD *)a2;
    *(_QWORD *)(a3 + 88) = *(_QWORD *)(a2 + 16);
  }
  if ( *(_QWORD *)(a1 + 176) == 1 && (*(_BYTE *)a1 & 2) != 0 )
    v4 = *(_WORD *)(a3 + 66) | 1;
  else
    v4 = *(_WORD *)(a3 + 66) & 0xFFFE;
  *(_WORD *)(a3 + 66) = v4;
  if ( (*(_DWORD *)a1 & 0x400) != 0 )
    *(_WORD *)(a3 + 66) = v4 | 2;
  if ( g_SxsRegKeyHandle
    || (RtlInitUnicodeString(
          &DestinationString,
          L"\\Registry\\MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide"),
        ObjectAttributes.Length = 48,
        ObjectAttributes.ObjectName = &DestinationString,
        ObjectAttributes.RootDirectory = 0,
        ObjectAttributes.Attributes = 64,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        result = NtOpenKey(&g_SxsRegKeyHandle, 0x20019u, &ObjectAttributes),
        result >= 0) )
  {
    RtlInitUnicodeString(&DestinationString, L"PublisherPolicyChangeTime");
    result = NtQueryValueKey(
               g_SxsRegKeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               KeyValueInformation,
               0x18u,
               &ResultLength);
    if ( result < 0 )
    {
      if ( result != -1073741772 )
        LODWORD(v3) = result;
      return v3;
    }
    else
    {
      if ( v10 == 11 && v11 == 8 )
        v3 = v12;
      if ( _InterlockedExchange64(&g_SxsPublihserPolicyChangeTime, v3) != v3 )
        return BaseClearSrvActivationContextCache((unsigned int)result);
    }
  }
  else if ( result == -1073741772 || result == -1073741766 )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001110  push    rbx
0x180001112  sub     rsp, 0A0h
0x180001119  mov     rax, cs:__security_cookie
0x180001120  xor     rax, rsp
0x180001123  mov     [rsp+0A8h+var_18], rax
0x18000112b  xorps   xmm0, xmm0
0x18000112e  xor     eax, eax
0x180001130  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x180001135  mov     [rsp+0A8h+ObjectAttributes.SecurityDescriptor], rax
0x18000113a  xor     ebx, ebx
0x18000113c  mov     dword ptr [rsp+0A8h+ObjectAttributes.SecurityQualityOfService], eax
0x180001140  mov     [rsp+0A8h+var_78], ebx
0x180001144  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180001149  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x18000114e  movups  xmm0, xmmword ptr [rcx+20h]
0x180001152  movups  xmmword ptr [r8], xmm0
0x180001156  movups  xmm0, xmmword ptr [rcx+88h]
0x18000115d  movups  xmmword ptr [r8+18h], xmm0
0x180001162  mov     rax, [rcx+0B0h]
0x180001169  mov     [r8+28h], rax
0x18000116d  movups  xmm0, xmmword ptr [rcx+8]
0x180001171  movups  xmmword ptr [r8+30h], xmm0
0x180001176  movzx   eax, word ptr [rcx+4]
0x18000117a  mov     [r8+40h], ax
0x18000117f  mov     rax, [rcx+0A8h]
0x180001186  mov     [r8+10h], rax
0x18000118a  test    rdx, rdx
0x18000118d  jz      short loc_1800011A2
0x18000118f  movups  xmm0, xmmword ptr [rdx]
0x180001192  movups  xmmword ptr [r8+48h], xmm0
0x180001197  movsd   xmm1, qword ptr [rdx+10h]
0x18000119c  movsd   qword ptr [r8+58h], xmm1
0x1800011a2  cmp     qword ptr [rcx+0B0h], 1
0x1800011aa  jz      loc_180001274
0x1800011b0  mov     eax, 0FFFEh
0x1800011b5  and     ax, [r8+42h]
0x1800011ba  mov     [r8+42h], ax
0x1800011bf  test    dword ptr [rcx], 400h
0x1800011c5  jnz     loc_180001292
0x1800011cb  cmp     cs:g_SxsRegKeyHandle, rbx
0x1800011d2  jz      loc_1800012A0
0x1800011d8  lea     rdx, SourceString; "PublisherPolicyChangeTime"
0x1800011df  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1800011e4  call    cs:__imp_RtlInitUnicodeString
0x1800011eb  nop     dword ptr [rax+rax+00h]
0x1800011f0  mov     rcx, cs:g_SxsRegKeyHandle; KeyHandle
0x1800011f7  lea     rax, [rsp+0A8h+var_78]
0x1800011fc  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x180001201  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x180001206  mov     r8d, 2; KeyValueInformationClass
0x18000120c  mov     [rsp+0A8h+Length], 18h; Length
0x180001214  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x180001219  call    cs:__imp_NtQueryValueKey
0x180001220  nop     dword ptr [rax+rax+00h]
0x180001225  mov     ecx, eax
0x180001227  test    eax, eax
0x180001229  js      loc_18000131E
0x18000122f  cmp     [rsp+0A8h+var_2C], 0Bh
0x180001234  jz      short loc_180001261
0x180001236  mov     rax, rbx
0x180001239  xchg    rax, cs:g_SxsPublihserPolicyChangeTime
0x180001240  cmp     rax, rbx
0x180001243  jnz     short loc_18000128B
0x180001245  mov     eax, ecx
0x180001247  mov     rcx, [rsp+0A8h+var_18]
0x18000124f  xor     rcx, rsp; StackCookie
0x180001252  call    __security_check_cookie
0x180001257  add     rsp, 0A0h
0x18000125e  pop     rbx
0x18000125f  retn
0x180001261  cmp     [rsp+0A8h+var_28], 8
0x180001269  cmovz   rbx, [rsp+0A8h+var_24]
0x180001272  jmp     short loc_180001236
0x180001274  test    byte ptr [rcx], 2
0x180001277  jz      loc_1800011B0
0x18000127d  movzx   eax, word ptr [r8+42h]
0x180001282  or      ax, 1
0x180001286  jmp     loc_1800011BA
0x18000128b  call    BaseClearSrvActivationContextCache
0x180001290  jmp     short loc_180001247
0x180001292  or      ax, 2
0x180001296  mov     [r8+42h], ax
0x18000129b  jmp     loc_1800011CB
0x1800012a0  lea     rdx, aRegistryMachin; "\\Registry\\MACHINE\\Software\\Microsof"...
0x1800012a7  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1800012ac  call    cs:__imp_RtlInitUnicodeString
0x1800012b3  nop     dword ptr [rax+rax+00h]
0x1800012b8  lea     rax, [rsp+0A8h+DestinationString]
0x1800012bd  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800012c5  xorps   xmm0, xmm0
0x1800012c8  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x1800012cd  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800012d2  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rbx
0x1800012d7  mov     edx, 20019h; DesiredAccess
0x1800012dc  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800012e4  lea     rcx, g_SxsRegKeyHandle; KeyHandle
0x1800012eb  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800012f1  call    cs:__imp_NtOpenKey
0x1800012f8  nop     dword ptr [rax+rax+00h]
0x1800012fd  test    eax, eax
0x1800012ff  jns     loc_1800011D8
0x180001305  cmp     eax, 0C0000034h
0x18000130a  jz      short loc_180001317
0x18000130c  cmp     eax, 0C000003Ah
0x180001311  jnz     loc_180001247
0x180001317  mov     eax, ebx
0x180001319  jmp     loc_180001247
0x18000131e  cmp     ecx, 0C0000034h
0x180001324  cmovnz  ebx, ecx
0x180001327  mov     eax, ebx
0x180001329  jmp     loc_180001247
```
