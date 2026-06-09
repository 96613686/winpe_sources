# BaseSrvSxsGetCacheKey

- ea: `0x180001110`
- end: `0x180001340`
- name: `BaseSrvSxsGetCacheKey`
- size: `560`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003310`

## callees

- `0x180001110`
- `0x180006270`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800011dd`
- `ntdll!RtlInitUnicodeString` at `0x1800012ba`
- `ntdll!RtlInitUnicodeString` at `0x1800011dd`
- `ntdll!RtlInitUnicodeString` at `0x1800012ba`
- `ntdll!NtOpenKey` at `0x180001303`
- `ntdll!NtOpenKey` at `0x180001303`
- `ntdll!NtQueryValueKey` at `0x180001212`
- `ntdll!NtQueryValueKey` at `0x180001212`

## string_xrefs

- `0x1800012ae`: `\Registry\MACHINE\Software\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvSxsGetCacheKey(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  NTSTATUS v4; // edx
  __int64 v5; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-78h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-70h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-60h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+78h] [rbp-30h] BYREF
  int v10; // [rsp+7Ch] [rbp-2Ch]
  int v11; // [rsp+80h] [rbp-28h]
  __int64 v12; // [rsp+84h] [rbp-24h]

  ResultLength = 0;
  DestinationString = 0;
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
    *(_WORD *)(a3 + 66) |= 1u;
  else
    *(_WORD *)(a3 + 66) &= ~1u;
  if ( (*(_DWORD *)a1 & 0x400) != 0 )
    *(_WORD *)(a3 + 66) |= 2u;
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
    v4 = result;
    if ( result < 0 )
    {
      result = 0;
      if ( v4 != -1073741772 )
        return v4;
    }
    else
    {
      v5 = 0;
      if ( v10 == 11 && v11 == 8 )
        v5 = v12;
      if ( _InterlockedExchange64(&g_SxsPublihserPolicyChangeTime, v5) != v5 )
        return BaseClearSrvActivationContextCache(v5, (unsigned int)result);
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
0x180001110  sub     rsp, 0A8h
0x180001117  mov     rax, cs:__security_cookie
0x18000111e  xor     rax, rsp
0x180001121  mov     [rsp+0A8h+var_18], rax
0x180001129  xorps   xmm0, xmm0
0x18000112c  xor     eax, eax
0x18000112e  mov     [rsp+0A8h+var_78], eax
0x180001132  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x180001137  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x18000113c  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x180001141  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180001146  movups  xmm0, xmmword ptr [rcx+20h]
0x18000114a  movups  xmmword ptr [r8], xmm0
0x18000114e  movups  xmm0, xmmword ptr [rcx+88h]
0x180001155  movups  xmmword ptr [r8+18h], xmm0
0x18000115a  mov     rax, [rcx+0B0h]
0x180001161  mov     [r8+28h], rax
0x180001165  movups  xmm0, xmmword ptr [rcx+8]
0x180001169  movups  xmmword ptr [r8+30h], xmm0
0x18000116e  movzx   eax, word ptr [rcx+4]
0x180001172  mov     [r8+40h], ax
0x180001177  mov     rax, [rcx+0A8h]
0x18000117e  mov     [r8+10h], rax
0x180001182  test    rdx, rdx
0x180001185  jz      short loc_18000119A
0x180001187  movups  xmm0, xmmword ptr [rdx]
0x18000118a  movups  xmmword ptr [r8+48h], xmm0
0x18000118f  movsd   xmm1, qword ptr [rdx+10h]
0x180001194  movsd   qword ptr [r8+58h], xmm1
0x18000119a  cmp     qword ptr [rcx+0B0h], 1
0x1800011a2  jz      loc_18000126E
0x1800011a8  mov     eax, 0FFFEh
0x1800011ad  and     [r8+42h], ax
0x1800011b2  test    dword ptr [rcx], 400h
0x1800011b8  movzx   eax, word ptr [r8+42h]
0x1800011bd  jnz     loc_1800012A0
0x1800011c3  cmp     cs:g_SxsRegKeyHandle, 0
0x1800011cb  jz      loc_1800012AE
0x1800011d1  lea     rdx, SourceString; "PublisherPolicyChangeTime"
0x1800011d8  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1800011dd  call    cs:__imp_RtlInitUnicodeString
0x1800011e4  nop     dword ptr [rax+rax+00h]
0x1800011e9  mov     rcx, cs:g_SxsRegKeyHandle; KeyHandle
0x1800011f0  lea     rax, [rsp+0A8h+var_78]
0x1800011f5  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x1800011fa  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x1800011ff  mov     r8d, 2; KeyValueInformationClass
0x180001205  mov     [rsp+0A8h+Length], 18h; Length
0x18000120d  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x180001212  call    cs:__imp_NtQueryValueKey
0x180001219  nop     dword ptr [rax+rax+00h]
0x18000121e  mov     edx, eax
0x180001220  test    eax, eax
0x180001222  js      loc_180001330
0x180001228  xor     ecx, ecx
0x18000122a  cmp     [rsp+0A8h+var_2C], 0Bh
0x18000122f  jz      short loc_18000125B
0x180001231  mov     rax, rcx
0x180001234  xchg    rax, cs:g_SxsPublihserPolicyChangeTime
0x18000123b  cmp     rax, rcx
0x18000123e  jnz     short loc_180001282
0x180001240  mov     eax, edx
0x180001242  mov     rcx, [rsp+0A8h+var_18]
0x18000124a  xor     rcx, rsp; StackCookie
0x18000124d  call    __security_check_cookie
0x180001252  add     rsp, 0A8h
0x180001259  retn
0x18000125b  cmp     [rsp+0A8h+var_28], 8
0x180001263  cmovz   rcx, [rsp+0A8h+var_24]
0x18000126c  jmp     short loc_180001231
0x18000126e  test    byte ptr [rcx], 2
0x180001271  jz      loc_1800011A8
0x180001277  or      word ptr [r8+42h], 1
0x18000127d  jmp     loc_1800011B2
0x180001282  call    BaseClearSrvActivationContextCache
0x180001287  mov     rcx, [rsp+0A8h+var_18]
0x18000128f  xor     rcx, rsp; StackCookie
0x180001292  call    __security_check_cookie
0x180001297  add     rsp, 0A8h
0x18000129e  retn
0x1800012a0  or      ax, 2
0x1800012a4  mov     [r8+42h], ax
0x1800012a9  jmp     loc_1800011C3
0x1800012ae  lea     rdx, aRegistryMachin; "\\Registry\\MACHINE\\Software\\Microsof"...
0x1800012b5  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1800012ba  call    cs:__imp_RtlInitUnicodeString
0x1800012c1  nop     dword ptr [rax+rax+00h]
0x1800012c6  lea     rax, [rsp+0A8h+DestinationString]
0x1800012cb  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800012d3  xorps   xmm0, xmm0
0x1800012d6  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x1800012db  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800012e0  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], 0
0x1800012e9  mov     edx, 20019h; DesiredAccess
0x1800012ee  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800012f6  lea     rcx, g_SxsRegKeyHandle; KeyHandle
0x1800012fd  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001303  call    cs:__imp_NtOpenKey
0x18000130a  nop     dword ptr [rax+rax+00h]
0x18000130f  test    eax, eax
0x180001311  jns     loc_1800011D1
0x180001317  cmp     eax, 0C0000034h
0x18000131c  jz      short loc_180001329
0x18000131e  cmp     eax, 0C000003Ah
0x180001323  jnz     loc_180001242
0x180001329  xor     eax, eax
0x18000132b  jmp     loc_180001242
0x180001330  xor     eax, eax
0x180001332  cmp     edx, 0C0000034h
0x180001338  cmovnz  eax, edx
0x18000133b  jmp     loc_180001242
```
