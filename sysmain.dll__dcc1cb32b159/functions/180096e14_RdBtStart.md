# RdBtStart

- ea: `0x180096e14`
- end: `0x180096fd9`
- name: `RdBtStart`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006a020`

## callees

- `0x18003cbe4`
- `0x18003cffc`
- `0x180055800`
- `0x180056b04`
- `0x180056dd4`
- `0x180096e14`
- `0x1800b23a8`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180096efb`
- `ntdll!NtOpenKey` at `0x180096efb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096fc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096fc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180096f30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180096f30`

## string_xrefs

- `0x180096e8e`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`
- `0x180096f29`: `ReadyBootTrainingMode`

## pseudocode

```c
__int64 __fastcall RdBtStart(__int64 a1)
{
  int v2; // ebx
  const WCHAR *v3; // rax
  __int64 v4; // rcx
  __int16 v5; // cx
  __int64 v6; // rcx
  unsigned int v7; // edi
  struct _RTL_CRITICAL_SECTION *v8; // r10
  void *KeyHandle; // [rsp+30h] [rbp-50h] BYREF
  __int64 v11; // [rsp+38h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+C0h] [rbp+40h] BYREF
  int Data; // [rsp+C8h] [rbp+48h] BYREF

  Data = 0;
  Type = 0;
  v12 = 0;
  cbData = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  v2 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 872LL) >= 0x19000u
    && (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 0x1000000) == 0;
  if ( *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 332LL) == 3 && v2 )
  {
    v2 = 0;
    v3 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
    v4 = 0x7FFF;
    while ( *v3 )
    {
      ++v3;
      if ( !--v4 )
        goto LABEL_11;
    }
    v5 = 2 * v4;
    *((_QWORD *)&v12 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
    LOWORD(v12) = -2 - v5;
    WORD1(v12) = -v5;
LABEL_11:
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v12;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
    {
      cbData = 4;
      if ( !RegQueryValueExW((HKEY)KeyHandle, L"ReadyBootTrainingMode", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4
        && Data )
      {
        v2 = 1;
      }
    }
  }
  v7 = RdBtEnable((const BYTE **)a1, v2);
  if ( !v7 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 1600LL) & 0x10) != 0 )
    {
      v11 = PfsActionItemGetCurrentTime(v6) + 100000000;
      PfsActionItemQueueEx(v8 + 43, v7 + 26, (unsigned __int64 *)&v11, 0);
    }
    else
    {
      RdBtStop();
    }
    if ( v2 )
    {
      if ( (unsigned int)EcbDiskHasAssessmentResults() )
        PfXpTaskRegister((LPCRITICAL_SECTION)(a1 + 56));
      v7 = 0;
    }
    else
    {
      v7 = 1058;
    }
  }
  if ( KeyHandle )
    RegCloseKey((HKEY)KeyHandle);
  return v7;
}

```

## disassembly

```asm
0x180096e14  push    rbp
0x180096e16  push    rbx
0x180096e17  push    rsi
0x180096e18  push    rdi
0x180096e19  push    r14
0x180096e1b  mov     rbp, rsp
0x180096e1e  sub     rsp, 80h
0x180096e25  xor     r14d, r14d
0x180096e28  xorps   xmm0, xmm0
0x180096e2b  xor     eax, eax
0x180096e2d  mov     [rbp+Data], r14d
0x180096e31  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180096e35  mov     rsi, rcx
0x180096e38  mov     [rbp+Type], r14d
0x180096e3c  movups  [rbp+var_40], xmm0
0x180096e40  lea     edi, [rax+1]
0x180096e43  mov     [rbp+cbData], r14d
0x180096e47  mov     rax, cs:PfSvcGlobals
0x180096e4e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180096e52  mov     [rbp+KeyHandle], r14
0x180096e56  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180096e5a  cmp     qword ptr [rax+368h], 19000h
0x180096e65  jnb     short loc_180096E6C
0x180096e67  mov     ebx, r14d
0x180096e6a  jmp     short loc_180096E79
0x180096e6c  mov     ebx, [rax+0F4h]
0x180096e72  shr     ebx, 18h
0x180096e75  not     ebx
0x180096e77  and     ebx, edi
0x180096e79  cmp     dword ptr [rax+14Ch], 3
0x180096e80  jnz     loc_180096F4D
0x180096e86  test    ebx, ebx
0x180096e88  jz      loc_180096F4D
0x180096e8e  lea     r8, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180096e95  mov     ebx, r14d
0x180096e98  mov     rax, r8
0x180096e9b  mov     ecx, 7FFFh
0x180096ea0  mov     edx, 2
0x180096ea5  cmp     [rax], r14w
0x180096ea9  jz      short loc_180096EB5
0x180096eab  add     rax, rdx
0x180096eae  sub     rcx, rdi
0x180096eb1  jnz     short loc_180096EA5
0x180096eb3  jmp     short loc_180096ECF
0x180096eb5  add     cx, cx
0x180096eb8  mov     qword ptr [rbp+var_40+8], r8
0x180096ebc  mov     eax, 0FFFEh
0x180096ec1  sub     ax, cx
0x180096ec4  mov     word ptr [rbp+var_40], ax
0x180096ec8  add     ax, dx
0x180096ecb  mov     word ptr [rbp+var_40+2], ax
0x180096ecf  lea     rax, [rbp+var_40]
0x180096ed3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180096eda  xorps   xmm0, xmm0
0x180096edd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180096ee1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180096ee5  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x180096ee9  mov     edx, edi; DesiredAccess
0x180096eeb  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180096ef2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180096ef6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180096efb  call    cs:__imp_NtOpenKey
0x180096f01  test    eax, eax
0x180096f03  js      short loc_180096F4D
0x180096f05  mov     rcx, [rbp+KeyHandle]; hKey
0x180096f09  lea     rax, [rbp+cbData]
0x180096f0d  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180096f12  lea     r9, [rbp+Type]; lpType
0x180096f16  lea     rax, [rbp+Data]
0x180096f1a  mov     [rbp+cbData], 4
0x180096f21  xor     r8d, r8d; lpReserved
0x180096f24  mov     [rsp+80h+lpData], rax; lpData
0x180096f29  lea     rdx, aReadyboottrain_0; "ReadyBootTrainingMode"
0x180096f30  call    cs:__imp_RegQueryValueExW
0x180096f36  test    eax, eax
0x180096f38  jnz     short loc_180096F4D
0x180096f3a  cmp     [rbp+Type], 4
0x180096f3e  jnz     short loc_180096F4D
0x180096f40  cmp     [rbp+cbData], 4
0x180096f44  jnz     short loc_180096F4D
0x180096f46  cmp     [rbp+Data], r14d
0x180096f4a  cmovnz  ebx, edi
0x180096f4d  mov     edx, ebx
0x180096f4f  mov     rcx, rsi
0x180096f52  call    RdBtEnable
0x180096f57  mov     edi, eax
0x180096f59  test    eax, eax
0x180096f5b  jnz     short loc_180096FBA
0x180096f5d  mov     r10, cs:PfSvcGlobals
0x180096f64  test    byte ptr [r10+640h], 10h
0x180096f6c  jz      short loc_180096F95
0x180096f6e  call    PfsActionItemGetCurrentTime
0x180096f73  add     rax, 5F5E100h
0x180096f79  lea     r8, [rbp+var_48]
0x180096f7d  xor     r9d, r9d
0x180096f80  mov     [rbp+var_48], rax
0x180096f84  lea     edx, [rdi+1Ah]
0x180096f87  lea     rcx, [r10+6B8h]; lpCriticalSection
0x180096f8e  call    PfsActionItemQueueEx
0x180096f93  jmp     short loc_180096F9A
0x180096f95  call    RdBtStop
0x180096f9a  test    ebx, ebx
0x180096f9c  jnz     short loc_180096FA5
0x180096f9e  mov     edi, 422h
0x180096fa3  jmp     short loc_180096FBA
0x180096fa5  call    EcbDiskHasAssessmentResults
0x180096faa  test    eax, eax
0x180096fac  jz      short loc_180096FB7
0x180096fae  lea     rcx, [rsi+38h]; lpCriticalSection
0x180096fb2  call    PfXpTaskRegister
0x180096fb7  mov     edi, r14d
0x180096fba  mov     rcx, [rbp+KeyHandle]; hKey
0x180096fbe  test    rcx, rcx
0x180096fc1  jz      short loc_180096FC9
0x180096fc3  call    cs:__imp_RegCloseKey
0x180096fc9  mov     eax, edi
0x180096fcb  add     rsp, 80h
0x180096fd2  pop     r14
0x180096fd4  pop     rdi
0x180096fd5  pop     rsi
0x180096fd6  pop     rbx
0x180096fd7  pop     rbp
0x180096fd8  retn
```
