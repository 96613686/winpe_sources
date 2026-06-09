# Pca::MergeSdb::Utils::RegUtil::OpenRegistryKeyFromFullPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ulong)

- ea: `0x14002d10c`
- end: `0x14002d1d3`
- name: `?OpenRegistryKeyFromFullPath@RegUtil@Utils@MergeSdb@Pca@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z`
- size: `199`
- prototype: `NTSTATUS __fastcall(HKEY *KeyHandle, PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002a404`

## callees

- `0x14002d10c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002d146`
- `ADVAPI32!RegCloseKey` at `0x14002d1a1`
- `ADVAPI32!RegCloseKey` at `0x14002d146`
- `ADVAPI32!RegCloseKey` at `0x14002d1a1`
- `KERNEL32!GetLastError` at `0x14002d13b`
- `KERNEL32!GetLastError` at `0x14002d196`
- `KERNEL32!GetLastError` at `0x14002d13b`
- `KERNEL32!GetLastError` at `0x14002d196`
- `KERNEL32!SetLastError` at `0x14002d14e`
- `KERNEL32!SetLastError` at `0x14002d1a9`
- `KERNEL32!SetLastError` at `0x14002d14e`
- `KERNEL32!SetLastError` at `0x14002d1a9`
- `ntdll!RtlInitUnicodeString` at `0x14002d162`
- `ntdll!RtlInitUnicodeString` at `0x14002d162`
- `ntdll!NtOpenKey` at `0x14002d1c2`
- `ntdll!NtOpenKey` at `0x14002d1c2`

## pseudocode

```c
NTSTATUS __fastcall Pca::MergeSdb::Utils::RegUtil::OpenRegistryKeyFromFullPath(HKEY *KeyHandle, PCWSTR SourceString)
{
  HKEY v2; // rsi
  DWORD LastError; // ebx
  HKEY v6; // rsi
  DWORD v7; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  v2 = *KeyHandle;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( v2 )
  {
    LastError = GetLastError();
    RegCloseKey(v2);
    SetLastError(LastError);
  }
  *KeyHandle = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v6 = *KeyHandle;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v6 )
  {
    v7 = GetLastError();
    RegCloseKey(v6);
    SetLastError(v7);
  }
  *KeyHandle = 0;
  return NtOpenKey((PHANDLE)KeyHandle, 0x20019u, &ObjectAttributes);
}

```

## disassembly

```asm
0x14002d10c  push    rbp
0x14002d10e  push    rbx
0x14002d10f  push    rsi
0x14002d110  push    rdi
0x14002d111  push    r14
0x14002d113  mov     rbp, rsp
0x14002d116  sub     rsp, 60h
0x14002d11a  mov     rsi, [rcx]
0x14002d11d  xorps   xmm0, xmm0
0x14002d120  mov     r14, rdx
0x14002d123  mov     rdi, rcx
0x14002d126  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14002d12a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14002d12e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002d132  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002d136  test    rsi, rsi
0x14002d139  jz      short loc_14002D154
0x14002d13b  call    cs:__imp_GetLastError
0x14002d141  mov     rcx, rsi; hKey
0x14002d144  mov     ebx, eax
0x14002d146  call    cs:__imp_RegCloseKey
0x14002d14c  mov     ecx, ebx; dwErrCode
0x14002d14e  call    cs:__imp_SetLastError
0x14002d154  mov     rdx, r14; SourceString
0x14002d157  mov     qword ptr [rdi], 0
0x14002d15e  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002d162  call    cs:__imp_RtlInitUnicodeString
0x14002d168  mov     rsi, [rdi]
0x14002d16b  lea     rax, [rbp+DestinationString]
0x14002d16f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14002d173  xorps   xmm0, xmm0
0x14002d176  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002d17d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002d185  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14002d18c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002d191  test    rsi, rsi
0x14002d194  jz      short loc_14002D1AF
0x14002d196  call    cs:__imp_GetLastError
0x14002d19c  mov     rcx, rsi; hKey
0x14002d19f  mov     ebx, eax
0x14002d1a1  call    cs:__imp_RegCloseKey
0x14002d1a7  mov     ecx, ebx; dwErrCode
0x14002d1a9  call    cs:__imp_SetLastError
0x14002d1af  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002d1b3  mov     qword ptr [rdi], 0
0x14002d1ba  mov     edx, 20019h; DesiredAccess
0x14002d1bf  mov     rcx, rdi; KeyHandle
0x14002d1c2  call    cs:__imp_NtOpenKey
0x14002d1c8  add     rsp, 60h
0x14002d1cc  pop     r14
0x14002d1ce  pop     rdi
0x14002d1cf  pop     rsi
0x14002d1d0  pop     rbx
0x14002d1d1  pop     rbp
0x14002d1d2  retn
```
