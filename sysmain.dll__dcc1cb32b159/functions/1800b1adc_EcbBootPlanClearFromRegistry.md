# EcbBootPlanClearFromRegistry

- ea: `0x1800b1adc`
- end: `0x1800b1c18`
- name: `EcbBootPlanClearFromRegistry`
- size: `316`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c230`

## callees

- `0x1800b1adc`

## import_xrefs

- `ntdll!NtCreateKey` at `0x1800b1b7e`
- `ntdll!NtCreateKey` at `0x1800b1b7e`
- `ntdll!RtlNtStatusToDosError` at `0x1800b1b8a`
- `ntdll!RtlNtStatusToDosError` at `0x1800b1b8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1bfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1bfb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1bea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1bea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b1b9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b1bae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b1bbf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b1b9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b1bae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b1bbf`

## string_xrefs

- `0x1800b1af3`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`
- `0x1800b1bdb`: `ReadyBootPlanAge`

## pseudocode

```c
__int64 EcbBootPlanClearFromRegistry()
{
  __int64 v0; // rcx
  const WCHAR *v1; // rax
  __int16 v2; // cx
  int v3; // eax
  ULONG v4; // eax
  ULONG v5; // ebx
  __int128 v7; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+90h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+18h] BYREF

  Data = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v0 = 0x7FFF;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v1 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  KeyHandle = 0;
  v7 = 0;
  while ( *v1 )
  {
    ++v1;
    if ( !--v0 )
      goto LABEL_6;
  }
  v2 = 2 * v0;
  *((_QWORD *)&v7 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  LOWORD(v7) = -2 - v2;
  WORD1(v7) = -v2;
LABEL_6:
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v7;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v3 = NtCreateKey(&KeyHandle, 2u, &ObjectAttributes, 0, 0, 0, 0);
  if ( v3 >= 0 )
  {
    RegDeleteValueW((HKEY)KeyHandle, L"BootPlan");
    RegDeleteValueW((HKEY)KeyHandle, L"EffectivePends");
    RegDeleteValueW((HKEY)KeyHandle, L"BootCountwithPends");
    Data = 0;
    v4 = RegSetValueExW((HKEY)KeyHandle, L"ReadyBootPlanAge", 0, 4u, (const BYTE *)&Data, 4u);
  }
  else
  {
    v4 = RtlNtStatusToDosError(v3);
  }
  v5 = v4;
  if ( KeyHandle )
    RegCloseKey((HKEY)KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x1800b1adc  mov     [rsp-8+arg_10], rbx
0x1800b1ae1  mov     [rsp-8+arg_18], rdi
0x1800b1ae6  push    rbp
0x1800b1ae7  mov     rbp, rsp
0x1800b1aea  sub     rsp, 80h
0x1800b1af1  xor     edi, edi
0x1800b1af3  lea     r8, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800b1afa  xorps   xmm0, xmm0
0x1800b1afd  mov     [rbp+Data], edi
0x1800b1b00  mov     dword ptr [rbp+ObjectAttributes+4], edi
0x1800b1b03  mov     ecx, 7FFFh
0x1800b1b08  mov     dword ptr [rbp+ObjectAttributes+1Ch], edi
0x1800b1b0b  mov     rax, r8
0x1800b1b0e  lea     edx, [rdi+2]; DesiredAccess
0x1800b1b11  mov     [rbp+KeyHandle], rdi
0x1800b1b15  movups  [rbp+var_40], xmm0
0x1800b1b19  cmp     [rax], di
0x1800b1b1c  jz      short loc_1800B1B29
0x1800b1b1e  add     rax, rdx
0x1800b1b21  sub     rcx, 1
0x1800b1b25  jnz     short loc_1800B1B19
0x1800b1b27  jmp     short loc_1800B1B43
0x1800b1b29  add     cx, cx
0x1800b1b2c  mov     qword ptr [rbp+var_40+8], r8
0x1800b1b30  mov     eax, 0FFFEh
0x1800b1b35  sub     ax, cx
0x1800b1b38  mov     word ptr [rbp+var_40], ax
0x1800b1b3c  add     ax, dx
0x1800b1b3f  mov     word ptr [rbp+var_40+2], ax
0x1800b1b43  lea     rax, [rbp+var_40]
0x1800b1b47  mov     [rsp+80h+Disposition], rdi; Disposition
0x1800b1b4c  xorps   xmm0, xmm0
0x1800b1b4f  mov     [rsp+80h+CreateOptions], edi; CreateOptions
0x1800b1b53  xor     r9d, r9d; TitleIndex
0x1800b1b56  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800b1b5a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800b1b5e  mov     [rsp+80h+Class], rdi; Class
0x1800b1b63  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800b1b67  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800b1b6e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b1b73  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x1800b1b77  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800b1b7e  call    cs:__imp_NtCreateKey
0x1800b1b84  test    eax, eax
0x1800b1b86  jns     short loc_1800B1B92
0x1800b1b88  mov     ecx, eax; Status
0x1800b1b8a  call    cs:__imp_RtlNtStatusToDosError
0x1800b1b90  jmp     short loc_1800B1BF0
0x1800b1b92  mov     rcx, [rbp+KeyHandle]; hKey
0x1800b1b96  lea     rdx, aBootplan; "BootPlan"
0x1800b1b9d  call    cs:__imp_RegDeleteValueW
0x1800b1ba3  mov     rcx, [rbp+KeyHandle]; hKey
0x1800b1ba7  lea     rdx, aEffectivepends; "EffectivePends"
0x1800b1bae  call    cs:__imp_RegDeleteValueW
0x1800b1bb4  mov     rcx, [rbp+KeyHandle]; hKey
0x1800b1bb8  lea     rdx, aBootcountwithp; "BootCountwithPends"
0x1800b1bbf  call    cs:__imp_RegDeleteValueW
0x1800b1bc5  mov     rcx, [rbp+KeyHandle]; hKey
0x1800b1bc9  lea     rax, [rbp+Data]
0x1800b1bcd  mov     r9d, 4; dwType
0x1800b1bd3  mov     [rbp+Data], edi
0x1800b1bd6  mov     [rsp+80h+CreateOptions], r9d; cbData
0x1800b1bdb  lea     rdx, aReadybootplana; "ReadyBootPlanAge"
0x1800b1be2  xor     r8d, r8d; Reserved
0x1800b1be5  mov     [rsp+80h+Class], rax; lpData
0x1800b1bea  call    cs:__imp_RegSetValueExW
0x1800b1bf0  mov     ebx, eax
0x1800b1bf2  mov     rcx, [rbp+KeyHandle]; hKey
0x1800b1bf6  test    rcx, rcx
0x1800b1bf9  jz      short loc_1800B1C01
0x1800b1bfb  call    cs:__imp_RegCloseKey
0x1800b1c01  lea     r11, [rsp+80h+var_s0]
0x1800b1c09  mov     eax, ebx
0x1800b1c0b  mov     rbx, [r11+20h]
0x1800b1c0f  mov     rdi, [r11+28h]
0x1800b1c13  mov     rsp, r11
0x1800b1c16  pop     rbp
0x1800b1c17  retn
```
