# RdBtBootPlanLoad

- ea: `0x18009675c`
- end: `0x180096948`
- name: `RdBtBootPlanLoad`
- size: `492`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180096a00`
- `0x1800a2318`
- `0x1800b3094`

## callees

- `0x1800236e8`
- `0x18009675c`
- `0x1800b6b18`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18009682a`
- `ntdll!NtQueryValueKey` at `0x180096890`
- `ntdll!NtQueryValueKey` at `0x18009682a`
- `ntdll!NtQueryValueKey` at `0x180096890`
- `ntdll!RtlInitUnicodeString` at `0x1800967b1`
- `ntdll!RtlInitUnicodeString` at `0x180096808`
- `ntdll!RtlInitUnicodeString` at `0x1800967b1`
- `ntdll!RtlInitUnicodeString` at `0x180096808`
- `ntdll!NtOpenKey` at `0x1800967e4`
- `ntdll!NtOpenKey` at `0x1800967e4`
- `ntdll!RtlNtStatusToDosError` at `0x1800967f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800967f0`
- `ntdll!NtClose` at `0x180096901`
- `ntdll!NtClose` at `0x180096901`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180096917`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180096917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180096932`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180096932`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009685c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009685c`

## string_xrefs

- `0x18009677b`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`

## pseudocode

```c
__int64 __fastcall RdBtBootPlanLoad(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v3; // rdi
  UCHAR *v5; // rsi
  int v6; // eax
  ULONG v7; // ebx
  ULONG Length; // ebx
  ULONG v9; // eax
  void *KeyHandle; // [rsp+30h] [rbp-29h] BYREF
  void *v12; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  __int64 v16; // [rsp+C0h] [rbp+67h] BYREF
  ULONG ResultLength; // [rsp+C8h] [rbp+6Fh] BYREF
  int v18; // [rsp+CCh] [rbp+73h]
  __int64 v19; // [rsp+D8h] [rbp+7Fh] BYREF

  v18 = HIDWORD(a2);
  v16 = a1;
  ResultLength = 0;
  v3 = 0;
  KeyHandle = 0;
  v12 = 0;
  memset(&ObjectAttributes, 0, 44);
  v5 = 0;
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( v6 < 0 )
    goto LABEL_2;
  RtlInitUnicodeString(&ValueName, L"BootPlan");
  v6 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformationAlign64, 0, 0, &ResultLength);
  if ( v6 != -1073741789 )
    goto LABEL_2;
  Length = ResultLength;
  if ( ResultLength > 0x100000 )
  {
    v7 = 223;
    goto LABEL_15;
  }
  v5 = (UCHAR *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, ResultLength);
  if ( !v5 )
  {
    v7 = 8;
    goto LABEL_15;
  }
  v6 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformationAlign64, v5, Length, &ResultLength);
  if ( v6 < 0 )
  {
LABEL_2:
    v7 = RtlNtStatusToDosError(v6);
    goto LABEL_15;
  }
  if ( *(_DWORD *)v5 == 3 )
  {
    LODWORD(v16) = *((_DWORD *)v5 + 1);
    LODWORD(v19) = 0x200000;
    v9 = PfsDecompressBuffer(v5 + 8, (unsigned int)v16, (__int64)&v12, (__int64)&v16, (__int64)&v19);
    v3 = v12;
    v7 = v9;
    if ( !v9 )
    {
      if ( (unsigned int)SmReadyBootPlanVerify(v12, (unsigned int)v16) )
      {
        v7 = 11;
      }
      else
      {
        *a3 = v3;
        v3 = 0;
        v7 = 0;
      }
    }
  }
  else
  {
    v7 = 1804;
  }
LABEL_15:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v3 )
    VirtualFree(v3, 0, 0x8000u);
  if ( v5 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v5);
  return v7;
}

```

## disassembly

```asm
0x18009675c  mov     qword ptr [rsp-8+arg_8], rdx
0x180096761  mov     [rsp-8+arg_0], rcx
0x180096766  push    rbp
0x180096767  push    rbx
0x180096768  push    rsi
0x180096769  push    rdi
0x18009676a  push    r14
0x18009676c  lea     rbp, [rsp-37h]
0x180096771  sub     rsp, 90h
0x180096778  xorps   xmm0, xmm0
0x18009677b  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180096782  xor     eax, eax
0x180096784  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180096788  xorps   xmm1, xmm1
0x18009678b  mov     [rbp+57h+arg_8], eax
0x18009678e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180096792  xor     edi, edi
0x180096794  mov     [rbp+57h+KeyHandle], rax
0x180096798  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18009679c  mov     r14, r8
0x18009679f  mov     [rbp+57h+var_78], rdi
0x1800967a3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800967a7  xor     esi, esi
0x1800967a9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800967ad  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1800967b1  call    cs:__imp_RtlInitUnicodeString
0x1800967b7  lea     rax, [rbp+57h+DestinationString]
0x1800967bb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800967c2  xorps   xmm0, xmm0
0x1800967c5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800967c9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800967cd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800967d1  lea     edx, [rdi+1]; DesiredAccess
0x1800967d4  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800967db  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800967df  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800967e4  call    cs:__imp_NtOpenKey
0x1800967ea  test    eax, eax
0x1800967ec  jns     short loc_1800967FD
0x1800967ee  mov     ecx, eax; Status
0x1800967f0  call    cs:__imp_RtlNtStatusToDosError
0x1800967f6  mov     ebx, eax
0x1800967f8  jmp     loc_1800968F8
0x1800967fd  lea     rdx, aBootplan; "BootPlan"
0x180096804  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180096808  call    cs:__imp_RtlInitUnicodeString
0x18009680e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180096812  lea     rax, [rbp+57h+arg_8]
0x180096816  xor     r9d, r9d; KeyValueInformation
0x180096819  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18009681e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180096822  mov     [rsp+0B0h+Length], esi; Length
0x180096826  lea     r8d, [r9+4]; KeyValueInformationClass
0x18009682a  call    cs:__imp_NtQueryValueKey
0x180096830  cmp     eax, 0C0000023h
0x180096835  jnz     short loc_1800967EE
0x180096837  mov     ebx, [rbp+57h+arg_8]
0x18009683a  cmp     ebx, 100000h
0x180096840  jbe     short loc_18009684C
0x180096842  mov     ebx, 0DFh
0x180096847  jmp     loc_1800968F8
0x18009684c  mov     rcx, cs:PfSvcGlobals
0x180096853  mov     r8, rbx; dwBytes
0x180096856  xor     edx, edx; dwFlags
0x180096858  mov     rcx, [rcx+58h]; hHeap
0x18009685c  call    cs:__imp_HeapAlloc
0x180096862  mov     rsi, rax
0x180096865  test    rax, rax
0x180096868  jnz     short loc_180096872
0x18009686a  lea     ebx, [rax+8]
0x18009686d  jmp     loc_1800968F8
0x180096872  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180096876  lea     rax, [rbp+57h+arg_8]
0x18009687a  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18009687f  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180096883  mov     r9, rsi; KeyValueInformation
0x180096886  mov     [rsp+0B0h+Length], ebx; Length
0x18009688a  mov     r8d, 4; KeyValueInformationClass
0x180096890  call    cs:__imp_NtQueryValueKey
0x180096896  test    eax, eax
0x180096898  js      loc_1800967EE
0x18009689e  cmp     dword ptr [rsi], 3
0x1800968a1  jz      short loc_1800968AA
0x1800968a3  mov     ebx, 70Ch
0x1800968a8  jmp     short loc_1800968F8
0x1800968aa  mov     edx, [rsi+4]
0x1800968ad  lea     rax, [rbp+57h+arg_18]
0x1800968b1  lea     rcx, [rsi+8]; Buffer
0x1800968b5  mov     qword ptr [rsp+0B0h+Length], rax; __int64
0x1800968ba  lea     r9, [rbp+57h+arg_0]
0x1800968be  mov     dword ptr [rbp+57h+arg_0], edx
0x1800968c1  lea     r8, [rbp+57h+var_78]
0x1800968c5  mov     dword ptr [rbp+57h+arg_18], 200000h
0x1800968cc  call    PfsDecompressBuffer
0x1800968d1  mov     rdi, [rbp+57h+var_78]
0x1800968d5  mov     ebx, eax
0x1800968d7  test    eax, eax
0x1800968d9  jnz     short loc_1800968F8
0x1800968db  mov     edx, dword ptr [rbp+57h+arg_0]
0x1800968de  mov     rcx, rdi
0x1800968e1  call    SmReadyBootPlanVerify
0x1800968e6  test    eax, eax
0x1800968e8  jz      short loc_1800968F1
0x1800968ea  mov     ebx, 0Bh
0x1800968ef  jmp     short loc_1800968F8
0x1800968f1  mov     [r14], rdi
0x1800968f4  xor     edi, edi
0x1800968f6  xor     ebx, ebx
0x1800968f8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800968fc  test    rcx, rcx
0x1800968ff  jz      short loc_180096907
0x180096901  call    cs:__imp_NtClose
0x180096907  test    rdi, rdi
0x18009690a  jz      short loc_18009691D
0x18009690c  xor     edx, edx; dwSize
0x18009690e  mov     r8d, 8000h; dwFreeType
0x180096914  mov     rcx, rdi; lpAddress
0x180096917  call    cs:__imp_VirtualFree
0x18009691d  test    rsi, rsi
0x180096920  jz      short loc_180096938
0x180096922  mov     rcx, cs:PfSvcGlobals
0x180096929  mov     r8, rsi; lpMem
0x18009692c  xor     edx, edx; dwFlags
0x18009692e  mov     rcx, [rcx+58h]; hHeap
0x180096932  call    cs:__imp_HeapFree
0x180096938  mov     eax, ebx
0x18009693a  add     rsp, 90h
0x180096941  pop     r14
0x180096943  pop     rdi
0x180096944  pop     rsi
0x180096945  pop     rbx
0x180096946  pop     rbp
0x180096947  retn
```
