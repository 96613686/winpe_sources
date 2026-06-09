# SampRegistryLookupNameInDomain(_SAMP_OBJECT *,ulong,_UNICODE_STRING *,ulong *,ulong *,ulong *)

- ea: `0x180004d20`
- end: `0x180004f94`
- name: `?SampRegistryLookupNameInDomain@@YAJPEAU_SAMP_OBJECT@@KPEAU_UNICODE_STRING@@PEAK22@Z`
- size: `628`
- prototype: `int(struct _SAMP_OBJECT *, unsigned int, struct _UNICODE_STRING *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002b40`

## callees

- `0x180004d20`
- `0x180004fa0`
- `0x180027e24`

## import_xrefs

- `ntdll!NtClose` at `0x180004eef`
- `ntdll!NtClose` at `0x180004eef`
- `ntdll!RtlpNtQueryValueKey` at `0x180004ee3`
- `ntdll!RtlpNtQueryValueKey` at `0x180004ee3`
- `ntdll!RtlpNtOpenKey` at `0x180004dbd`
- `ntdll!RtlpNtOpenKey` at `0x180004e2e`
- `ntdll!RtlpNtOpenKey` at `0x180004e9f`
- `ntdll!RtlpNtOpenKey` at `0x180004dbd`
- `ntdll!RtlpNtOpenKey` at `0x180004e2e`
- `ntdll!RtlpNtOpenKey` at `0x180004e9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f4f`

## pseudocode

```c
__int64 __fastcall SampRegistryLookupNameInDomain(
        struct _SAMP_OBJECT *a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  NTSTATUS v8; // ebx
  NTSTATUS v9; // ebx
  NTSTATUS v10; // ebx
  ULONG v12[2]; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem[2]; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+20h] BYREF
  ULONG DataLength; // [rsp+A8h] [rbp+28h] BYREF

  KeyHandle = 0;
  *(_OWORD *)hMem = 0;
  *(_QWORD *)v12 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DataLength = 0;
  v8 = SampBuildAccountKeyName(2, hMem, a3);
  if ( v8 >= 0 )
  {
    ObjectAttributes.RootDirectory = SampKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)hMem;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      hMem[1] = 0;
    }
    if ( v9 >= 0 )
    {
      --*a6;
      *a5 = 2;
      goto LABEL_14;
    }
    v8 = SampBuildAccountKeyName(3, hMem, a3);
    if ( v8 < 0 )
      goto LABEL_15;
    ObjectAttributes.RootDirectory = SampKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)hMem;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      hMem[1] = 0;
    }
    if ( v10 >= 0 )
    {
      --*a6;
      *a5 = 4;
      goto LABEL_14;
    }
    v8 = SampBuildAccountKeyName(4, hMem, a3);
    if ( v8 >= 0 )
    {
      ObjectAttributes.RootDirectory = SampKey;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)hMem;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
      if ( hMem[1] )
      {
        LocalFree(hMem[1]);
        hMem[1] = 0;
      }
      if ( v8 >= 0 )
      {
        --*a6;
        *a5 = 1;
LABEL_14:
        DataLength = 0;
        v8 = RtlpNtQueryValueKey(KeyHandle, a4, 0, &DataLength, (ULONG)v12);
        NtClose(KeyHandle);
      }
    }
  }
LABEL_15:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 121, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, (unsigned int)v8, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004d20  mov     [rsp-18h+arg_10], rbx
0x180004d25  mov     [rsp-18h+arg_18], rsi
0x180004d2a  mov     [rsp-18h+DataLength], edx
0x180004d2e  mov     [rsp-18h+KeyHandle], rcx
0x180004d33  push    rbp
0x180004d34  push    rdi
0x180004d35  push    r14
0x180004d37  mov     rbp, rsp
0x180004d3a  sub     rsp, 80h
0x180004d41  xorps   xmm1, xmm1
0x180004d44  lea     rdx, [rbp+hMem]
0x180004d48  xor     r14d, r14d
0x180004d4b  xorps   xmm0, xmm0
0x180004d4e  mov     ecx, 2
0x180004d53  mov     [rbp+KeyHandle], r14
0x180004d57  movups  xmmword ptr [rbp+hMem], xmm0
0x180004d5b  mov     qword ptr [rbp+var_50], r14
0x180004d5f  mov     rsi, r9
0x180004d62  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x180004d66  mov     [rbp+DataLength], r14d
0x180004d6a  mov     rdi, r8
0x180004d6d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180004d71  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180004d75  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180004d7a  mov     ebx, eax
0x180004d7c  test    eax, eax
0x180004d7e  js      loc_180004EF5
0x180004d84  mov     rax, cs:SampKey
0x180004d8b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180004d8f  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180004d93  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180004d97  lea     rax, [rbp+hMem]
0x180004d9b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180004da2  xorps   xmm0, xmm0
0x180004da5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180004da9  xor     r9d, r9d; Unused
0x180004dac  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180004db3  mov     edx, 20019h; DesiredAccess
0x180004db8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180004dbd  call    cs:__imp_RtlpNtOpenKey
0x180004dc3  mov     rcx, [rbp+hMem+8]; hMem
0x180004dc7  mov     ebx, eax
0x180004dc9  test    rcx, rcx
0x180004dcc  jnz     loc_180004F31
0x180004dd2  test    ebx, ebx
0x180004dd4  jns     loc_180004F1F
0x180004dda  mov     r8, rdi
0x180004ddd  lea     rdx, [rbp+hMem]
0x180004de1  mov     ecx, 3
0x180004de6  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180004deb  mov     ebx, eax
0x180004ded  test    eax, eax
0x180004def  js      loc_180004EF5
0x180004df5  mov     rax, cs:SampKey
0x180004dfc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180004e00  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180004e04  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180004e08  lea     rax, [rbp+hMem]
0x180004e0c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180004e13  xorps   xmm0, xmm0
0x180004e16  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180004e1a  xor     r9d, r9d; Unused
0x180004e1d  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180004e24  mov     edx, 20019h; DesiredAccess
0x180004e29  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180004e2e  call    cs:__imp_RtlpNtOpenKey
0x180004e34  mov     rcx, [rbp+hMem+8]; hMem
0x180004e38  mov     ebx, eax
0x180004e3a  test    rcx, rcx
0x180004e3d  jnz     loc_180004F40
0x180004e43  test    ebx, ebx
0x180004e45  jns     loc_180004F5E
0x180004e4b  mov     r8, rdi
0x180004e4e  lea     rdx, [rbp+hMem]
0x180004e52  mov     ecx, 4
0x180004e57  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180004e5c  mov     ebx, eax
0x180004e5e  test    eax, eax
0x180004e60  js      loc_180004EF5
0x180004e66  mov     rax, cs:SampKey
0x180004e6d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180004e71  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180004e75  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180004e79  lea     rax, [rbp+hMem]
0x180004e7d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180004e84  xorps   xmm0, xmm0
0x180004e87  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180004e8b  xor     r9d, r9d; Unused
0x180004e8e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180004e95  mov     edx, 20019h; DesiredAccess
0x180004e9a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180004e9f  call    cs:__imp_RtlpNtOpenKey
0x180004ea5  mov     rcx, [rbp+hMem+8]; hMem
0x180004ea9  mov     ebx, eax
0x180004eab  test    rcx, rcx
0x180004eae  jnz     loc_180004F4F
0x180004eb4  test    ebx, ebx
0x180004eb6  js      short loc_180004EF5
0x180004eb8  mov     rax, [rbp+arg_28]
0x180004ebc  dec     dword ptr [rax]
0x180004ebe  mov     rax, [rbp+arg_20]
0x180004ec2  mov     dword ptr [rax], 1
0x180004ec8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180004ecc  lea     rax, [rbp+var_50]
0x180004ed0  lea     r9, [rbp+DataLength]; DataLength
0x180004ed4  mov     qword ptr [rsp+80h+Unused], rax; Unused
0x180004ed9  xor     r8d, r8d; Data
0x180004edc  mov     [rbp+DataLength], r14d
0x180004ee0  mov     rdx, rsi; Type
0x180004ee3  call    cs:__imp_RtlpNtQueryValueKey
0x180004ee9  mov     rcx, [rbp+KeyHandle]; Handle
0x180004eed  mov     ebx, eax
0x180004eef  call    cs:__imp_NtClose
0x180004ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004efc  test    dword ptr [rcx+44h], 20000h
0x180004f03  jnz     short loc_180004F73
0x180004f05  lea     r11, [rsp+80h+var_s0]
0x180004f0d  mov     eax, ebx
0x180004f0f  mov     rbx, [r11+30h]
0x180004f13  mov     rsi, [r11+38h]
0x180004f17  mov     rsp, r11
0x180004f1a  pop     r14
0x180004f1c  pop     rdi
0x180004f1d  pop     rbp
0x180004f1e  retn
0x180004f1f  mov     rax, [rbp+arg_28]
0x180004f23  dec     dword ptr [rax]
0x180004f25  mov     rax, [rbp+arg_20]
0x180004f29  mov     dword ptr [rax], 2
0x180004f2f  jmp     short loc_180004EC8
0x180004f31  call    cs:__imp_LocalFree
0x180004f37  mov     [rbp+hMem+8], r14
0x180004f3b  jmp     loc_180004DD2
0x180004f40  call    cs:__imp_LocalFree
0x180004f46  mov     [rbp+hMem+8], r14
0x180004f4a  jmp     loc_180004E43
0x180004f4f  call    cs:__imp_LocalFree
0x180004f55  mov     [rbp+hMem+8], r14
0x180004f59  jmp     loc_180004EB4
0x180004f5e  mov     rax, [rbp+arg_28]
0x180004f62  dec     dword ptr [rax]
0x180004f64  mov     rax, [rbp+arg_20]
0x180004f68  mov     dword ptr [rax], 4
0x180004f6e  jmp     loc_180004EC8
0x180004f73  mov     rcx, [rcx+38h]
0x180004f77  lea     r8, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x180004f7e  mov     edx, 79h ; 'y'
0x180004f83  mov     [rsp+80h+Unused], ebx
0x180004f87  mov     r9d, ebx
0x180004f8a  call    WPP_SF_Dd
0x180004f8f  jmp     loc_180004F05
```
