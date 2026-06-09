# EcbBootPlanSaveToRegistry

- ea: `0x180066cac`
- end: `0x180066ee4`
- name: `EcbBootPlanSaveToRegistry`
- size: `568`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c230`

## callees

- `0x180023480`
- `0x180066cac`
- `0x1800b3a78`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180066de0`
- `ntdll!NtCreateKey` at `0x180066de0`
- `ntdll!RtlNtStatusToDosError` at `0x180066d44`
- `ntdll!RtlNtStatusToDosError` at `0x180066dec`
- `ntdll!RtlNtStatusToDosError` at `0x180066d44`
- `ntdll!RtlNtStatusToDosError` at `0x180066dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066eb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066eb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066e1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066e4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066e8f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066e1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066e4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180066e8f`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180066ea8`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180066ea8`

## string_xrefs

- `0x180066d57`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`
- `0x180066e42`: `ReadyBootPlanAge`

## pseudocode

```c
__int64 __fastcall EcbBootPlanSaveToRegistry(UCHAR *a1, ULONG a2)
{
  NTSTATUS v3; // eax
  ULONG v4; // ebx
  const WCHAR *v5; // rax
  __int64 v6; // rcx
  __int16 v7; // cx
  int v8; // eax
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  void *KeyHandle[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  __int64 v14[3]; // [rsp+98h] [rbp-68h] BYREF
  BYTE v15[128]; // [rsp+B0h] [rbp-50h] BYREF

  *(_DWORD *)Data = 0;
  v14[0] = (__int64)PfsCompressAlloc;
  KeyHandle[1] = 0;
  v14[1] = (__int64)PfsCompressFree;
  KeyHandle[0] = 0;
  v12 = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = SmCompressBuffer(a1, a2, (__int64)v14, 0);
  if ( v3 >= 0 || (v4 = RtlNtStatusToDosError(v3)) == 0 )
  {
    v12 = 0;
    v5 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
    v6 = 0x7FFF;
    while ( *v5 )
    {
      ++v5;
      if ( !--v6 )
        goto LABEL_8;
    }
    v7 = 2 * v6;
    *((_QWORD *)&v12 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
    LOWORD(v12) = -2 - v7;
    WORD1(v12) = -v7;
LABEL_8:
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v12;
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    v8 = NtCreateKey(KeyHandle, 2u, &ObjectAttributes, 0, 0, 0, 0);
    if ( v8 >= 0 )
    {
      v4 = RegSetValueExW((HKEY)KeyHandle[0], L"BootPlan", 0, 3u, 0, 0);
      if ( !v4 )
      {
        *(_DWORD *)Data = 0;
        v4 = RegSetValueExW((HKEY)KeyHandle[0], L"ReadyBootPlanAge", 0, 4u, Data, 4u);
        if ( !v4 )
        {
          if ( !(unsigned int)EcbUtilsGetReadableTimeString(a1 + 24, v15) )
            RegSetValueExW((HKEY)KeyHandle[0], L"LastBootPlanUserTime", 0, v4 + 1, v15, 0x80u);
          v4 = 0;
        }
      }
    }
    else
    {
      v4 = RtlNtStatusToDosError(v8);
    }
  }
  if ( KeyHandle[0] )
    RegCloseKey((HKEY)KeyHandle[0]);
  return v4;
}

```

## disassembly

```asm
0x180066cac  mov     [rsp-8+arg_10], rbx
0x180066cb1  mov     [rsp-8+arg_18], rsi
0x180066cb6  push    rbp
0x180066cb7  push    rdi
0x180066cb8  push    r14
0x180066cba  lea     rbp, [rsp-40h]
0x180066cbf  sub     rsp, 140h
0x180066cc6  mov     rax, cs:__security_cookie
0x180066ccd  xor     rax, rsp
0x180066cd0  mov     [rbp+50h+var_20], rax
0x180066cd4  xor     r14d, r14d
0x180066cd7  lea     r9, [rsp+150h+cbData]
0x180066cdc  xorps   xmm0, xmm0
0x180066cdf  mov     [rsp+150h+CreateOptions], r14d; int
0x180066ce4  xor     eax, eax
0x180066ce6  mov     [rsp+150h+cbData], r14d
0x180066ceb  lea     rax, PfsCompressAlloc
0x180066cf2  mov     dword ptr [rsp+150h+Data], r14d
0x180066cf7  mov     [rbp+50h+var_B8], rax
0x180066cfb  lea     r8, [rsp+150h+lpData]
0x180066d00  lea     rax, PfsCompressFree
0x180066d07  mov     [rsp+150h+lpData], r14
0x180066d0c  mov     [rbp+50h+var_B0], rax
0x180066d10  mov     rsi, rcx
0x180066d13  lea     rax, [rbp+50h+var_B8]
0x180066d17  mov     [rsp+150h+KeyHandle], r14
0x180066d1c  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x180066d21  mov     [rsp+150h+Class], rax; __int64
0x180066d26  movups  [rsp+150h+var_F8], xmm0
0x180066d2b  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x180066d30  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x180066d34  call    SmCompressBuffer
0x180066d39  mov     rdi, [rsp+150h+lpData]
0x180066d3e  test    eax, eax
0x180066d40  jns     short loc_180066D54
0x180066d42  mov     ecx, eax; Status
0x180066d44  call    cs:__imp_RtlNtStatusToDosError
0x180066d4a  mov     ebx, eax
0x180066d4c  test    eax, eax
0x180066d4e  jnz     loc_180066E98
0x180066d54  xorps   xmm0, xmm0
0x180066d57  lea     r8, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180066d5e  movups  [rsp+150h+var_F8], xmm0
0x180066d63  mov     rax, r8
0x180066d66  mov     ecx, 7FFFh
0x180066d6b  mov     edx, 2; DesiredAccess
0x180066d70  cmp     [rax], r14w
0x180066d74  jz      short loc_180066D81
0x180066d76  add     rax, rdx
0x180066d79  sub     rcx, 1
0x180066d7d  jnz     short loc_180066D70
0x180066d7f  jmp     short loc_180066D9E
0x180066d81  add     cx, cx
0x180066d84  mov     qword ptr [rsp+150h+var_F8+8], r8
0x180066d89  mov     eax, 0FFFEh
0x180066d8e  sub     ax, cx
0x180066d91  mov     word ptr [rsp+150h+var_F8], ax
0x180066d96  add     ax, dx
0x180066d99  mov     word ptr [rsp+150h+var_F8+2], ax
0x180066d9e  lea     rax, [rsp+150h+var_F8]
0x180066da3  mov     [rsp+150h+Disposition], r14; Disposition
0x180066da8  xorps   xmm0, xmm0
0x180066dab  mov     [rsp+150h+CreateOptions], r14d; CreateOptions
0x180066db0  xor     r9d, r9d; TitleIndex
0x180066db3  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x180066db8  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x180066dbd  mov     [rsp+150h+Class], r14; Class
0x180066dc2  lea     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x180066dc7  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x180066dcf  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x180066dd4  mov     [rsp+150h+ObjectAttributes.RootDirectory], r14
0x180066dd9  mov     [rbp+50h+ObjectAttributes.Attributes], 40h ; '@'
0x180066de0  call    cs:__imp_NtCreateKey
0x180066de6  test    eax, eax
0x180066de8  jns     short loc_180066DF9
0x180066dea  mov     ecx, eax; Status
0x180066dec  call    cs:__imp_RtlNtStatusToDosError
0x180066df2  mov     ebx, eax
0x180066df4  jmp     loc_180066E98
0x180066df9  mov     eax, [rsp+150h+cbData]
0x180066dfd  lea     rdx, aBootplan; "BootPlan"
0x180066e04  mov     rcx, [rsp+150h+KeyHandle]; hKey
0x180066e09  mov     r9d, 3; dwType
0x180066e0f  mov     [rsp+150h+CreateOptions], eax; cbData
0x180066e13  xor     r8d, r8d; Reserved
0x180066e16  mov     [rsp+150h+Class], rdi; lpData
0x180066e1b  call    cs:__imp_RegSetValueExW
0x180066e21  mov     ebx, eax
0x180066e23  test    eax, eax
0x180066e25  jnz     short loc_180066E98
0x180066e27  mov     rcx, [rsp+150h+KeyHandle]; hKey
0x180066e2c  lea     r9d, [rax+4]; dwType
0x180066e30  lea     rax, [rsp+150h+Data]
0x180066e35  mov     [rsp+150h+CreateOptions], r9d; cbData
0x180066e3a  xor     r8d, r8d; Reserved
0x180066e3d  mov     [rsp+150h+Class], rax; lpData
0x180066e42  lea     rdx, aReadybootplana; "ReadyBootPlanAge"
0x180066e49  mov     dword ptr [rsp+150h+Data], r14d
0x180066e4e  call    cs:__imp_RegSetValueExW
0x180066e54  mov     ebx, eax
0x180066e56  test    eax, eax
0x180066e58  jnz     short loc_180066E98
0x180066e5a  lea     rcx, [rsi+18h]
0x180066e5e  lea     rdx, [rbp+50h+var_A0]
0x180066e62  call    EcbUtilsGetReadableTimeString
0x180066e67  test    eax, eax
0x180066e69  jnz     short loc_180066E95
0x180066e6b  mov     rcx, [rsp+150h+KeyHandle]; hKey
0x180066e70  lea     rax, [rbp+50h+var_A0]
0x180066e74  mov     [rsp+150h+CreateOptions], 80h; cbData
0x180066e7c  lea     r9d, [rbx+1]; dwType
0x180066e80  xor     r8d, r8d; Reserved
0x180066e83  mov     [rsp+150h+Class], rax; lpData
0x180066e88  lea     rdx, aLastbootplanus; "LastBootPlanUserTime"
0x180066e8f  call    cs:__imp_RegSetValueExW
0x180066e95  mov     ebx, r14d
0x180066e98  test    rdi, rdi
0x180066e9b  jz      short loc_180066EAE
0x180066e9d  xor     edx, edx; dwSize
0x180066e9f  mov     r8d, 8000h; dwFreeType
0x180066ea5  mov     rcx, rdi; lpAddress
0x180066ea8  call    cs:__imp_VirtualFree
0x180066eae  mov     rcx, [rsp+150h+KeyHandle]; hKey
0x180066eb3  test    rcx, rcx
0x180066eb6  jz      short loc_180066EBE
0x180066eb8  call    cs:__imp_RegCloseKey
0x180066ebe  mov     eax, ebx
0x180066ec0  mov     rcx, [rbp+50h+var_20]
0x180066ec4  xor     rcx, rsp; StackCookie
0x180066ec7  call    __security_check_cookie
0x180066ecc  lea     r11, [rsp+150h+var_10]
0x180066ed4  mov     rbx, [r11+30h]
0x180066ed8  mov     rsi, [r11+38h]
0x180066edc  mov     rsp, r11
0x180066edf  pop     r14
0x180066ee1  pop     rdi
0x180066ee2  pop     rbp
0x180066ee3  retn
```
