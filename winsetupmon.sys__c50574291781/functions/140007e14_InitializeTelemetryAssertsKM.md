# InitializeTelemetryAssertsKM

- ea: `0x140007e14`
- end: `0x140007fe4`
- name: `InitializeTelemetryAssertsKM`
- size: `464`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140022078`

## callees

- `0x140007e14`
- `0x140007fec`
- `0x14000fa40`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007f4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007f4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fc7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007e70`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007e70`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007ec7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007ec7`
- `ntoskrnl!RtlFreeAnsiString` at `0x140007fb3`
- `ntoskrnl!RtlFreeAnsiString` at `0x140007fb3`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140007f39`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140007f39`
- `ntoskrnl!RtlInitAnsiString` at `0x140007e51`
- `ntoskrnl!RtlInitAnsiString` at `0x140007f8f`
- `ntoskrnl!RtlInitAnsiString` at `0x140007e51`
- `ntoskrnl!RtlInitAnsiString` at `0x140007f8f`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140007f18`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140007f18`

## string_xrefs

- `0x140007ee2`: `ImagePath`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKM(const void **a1)
{
  NTSTATUS RegistryValues; // edi
  __int64 v4; // rsi
  PVOID PoolWithTag; // rax
  void *v6; // rbx
  __int64 v7; // rcx
  bool v8; // zf
  _STRING DestinationString; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-69h] BYREF
  struct _STRING v11; // [rsp+50h] [rbp-59h] BYREF
  struct _STRING v12; // [rsp+60h] [rbp-49h] BYREF
  _RTL_QUERY_REGISTRY_TABLE QueryTable[2]; // [rsp+70h] [rbp-39h] BYREF

  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RegistryValues = -1073741801;
  RtlInitAnsiString(&DestinationString, 0);
  v4 = *(unsigned __int16 *)a1;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, v4 + 2, 0x74727341u);
  v6 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
LABEL_7:
      memmove(v6, a1[1], *(unsigned __int16 *)a1);
      SourceString = 0;
      RtlInitUnicodeString(&SourceString, 0);
      memset(QueryTable, 0, sizeof(QueryTable));
      QueryTable[0].Flags = 32;
      QueryTable[0].Name = L"ImagePath";
      QueryTable[0].DefaultType = 2;
      QueryTable[0].EntryContext = &SourceString;
      RegistryValues = RtlQueryRegistryValues(0, (PCWSTR)v6, QueryTable, 0, 0);
      if ( RegistryValues >= 0 )
      {
        RegistryValues = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 1u);
        ExFreePoolWithTag(SourceString.Buffer, 0);
        if ( RegistryValues >= 0 )
        {
          v7 = (unsigned int)DestinationString.Length - 1;
          if ( DestinationString.Length != 1 )
          {
            while ( DestinationString.Buffer[v7] != 92 )
            {
              v8 = (_DWORD)v7 == 1;
              v7 = (unsigned int)(v7 - 1);
              if ( v8 )
                goto LABEL_15;
            }
            if ( (_DWORD)v7 != DestinationString.Length )
            {
              v11 = 0;
              RtlInitAnsiString(&v11, &DestinationString.Buffer[(unsigned int)(v7 + 1)]);
              v12 = v11;
              RegistryValues = InitializeTelemetryAssertsKMWorkerInternal(&v12);
            }
          }
LABEL_15:
          RtlFreeAnsiString(&DestinationString);
        }
      }
      ExFreePoolWithTag(v6, 0x74727341u);
    }
  }
  else if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, v4 + 2);
    goto LABEL_7;
  }
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x140007e14  push    rbp
0x140007e16  push    rbx
0x140007e17  push    rsi
0x140007e18  push    rdi
0x140007e19  push    r14
0x140007e1b  lea     rbp, [rsp-37h]
0x140007e20  sub     rsp, 0E0h
0x140007e27  xorps   xmm0, xmm0
0x140007e2a  mov     r14, rcx
0x140007e2d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140007e31  xor     eax, eax
0x140007e33  lock xadd cs:g_AssertsOperational, eax
0x140007e3b  test    eax, eax
0x140007e3d  jz      short loc_140007E46
0x140007e3f  xor     eax, eax
0x140007e41  jmp     loc_140007FD5
0x140007e46  xor     edx, edx; SourceString
0x140007e48  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007e4c  mov     edi, 0C0000017h
0x140007e51  call    cs:__imp_RtlInitAnsiString
0x140007e58  nop     dword ptr [rax+rax+00h]
0x140007e5d  movzx   esi, word ptr [r14]
0x140007e61  mov     r8d, 74727341h; Tag
0x140007e67  mov     ecx, 600h; PoolType
0x140007e6c  lea     rdx, [rsi+2]; NumberOfBytes
0x140007e70  call    cs:__imp_ExAllocatePoolWithTag
0x140007e77  nop     dword ptr [rax+rax+00h]
0x140007e7c  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140007e83  mov     rbx, rax
0x140007e86  jnz     short loc_140007EA1
0x140007e88  test    rax, rax
0x140007e8b  jz      loc_140007FD3
0x140007e91  lea     r8, [rsi+2]; Size
0x140007e95  xor     edx, edx; Val
0x140007e97  mov     rcx, rax; void *
0x140007e9a  call    memset
0x140007e9f  jmp     short loc_140007EAA
0x140007ea1  test    rbx, rbx
0x140007ea4  jz      loc_140007FD3
0x140007eaa  movzx   r8d, word ptr [r14]; Size
0x140007eae  mov     rcx, rbx; void *
0x140007eb1  mov     rdx, [r14+8]; Src
0x140007eb5  call    memmove
0x140007eba  xorps   xmm0, xmm0
0x140007ebd  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x140007ec1  xor     edx, edx; SourceString
0x140007ec3  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140007ec7  call    cs:__imp_RtlInitUnicodeString
0x140007ece  nop     dword ptr [rax+rax+00h]
0x140007ed3  xor     edx, edx; Val
0x140007ed5  lea     rcx, [rbp+57h+QueryTable]; void *
0x140007ed9  lea     r8d, [rdx+70h]; Size
0x140007edd  call    memset
0x140007ee2  lea     rax, aImagepath; "ImagePath"
0x140007ee9  mov     [rbp+57h+QueryTable.Flags], 20h ; ' '
0x140007ef0  mov     [rbp+57h+QueryTable.Name], rax
0x140007ef4  lea     r8, [rbp+57h+QueryTable]; QueryTable
0x140007ef8  lea     rax, [rbp+57h+SourceString]
0x140007efc  mov     [rbp+57h+QueryTable.DefaultType], 2
0x140007f03  xor     r9d, r9d; Context
0x140007f06  mov     [rbp+57h+QueryTable.EntryContext], rax
0x140007f0a  mov     rdx, rbx; Path
0x140007f0d  mov     [rsp+100h+Environment], 0; Environment
0x140007f16  xor     ecx, ecx; RelativeTo
0x140007f18  call    cs:__imp_RtlQueryRegistryValues
0x140007f1f  nop     dword ptr [rax+rax+00h]
0x140007f24  mov     edi, eax
0x140007f26  test    eax, eax
0x140007f28  js      loc_140007FBF
0x140007f2e  mov     r8b, 1; AllocateDestinationString
0x140007f31  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140007f35  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007f39  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140007f40  nop     dword ptr [rax+rax+00h]
0x140007f45  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x140007f49  xor     edx, edx; Tag
0x140007f4b  mov     edi, eax
0x140007f4d  call    cs:__imp_ExFreePoolWithTag
0x140007f54  nop     dword ptr [rax+rax+00h]
0x140007f59  test    edi, edi
0x140007f5b  js      short loc_140007FBF
0x140007f5d  movzx   edx, [rbp+57h+DestinationString.Length]
0x140007f61  lea     ecx, [rdx-1]
0x140007f64  test    ecx, ecx
0x140007f66  jz      short loc_140007FAF
0x140007f68  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140007f6c  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140007f71  jz      short loc_140007F7A
0x140007f73  add     ecx, 0FFFFFFFFh
0x140007f76  jnz     short loc_140007F6C
0x140007f78  jmp     short loc_140007FAF
0x140007f7a  cmp     ecx, edx
0x140007f7c  jz      short loc_140007FAF
0x140007f7e  lea     edx, [rcx+1]
0x140007f81  xorps   xmm0, xmm0
0x140007f84  add     rdx, r8; SourceString
0x140007f87  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x140007f8b  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm0
0x140007f8f  call    cs:__imp_RtlInitAnsiString
0x140007f96  nop     dword ptr [rax+rax+00h]
0x140007f9b  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Length]
0x140007f9f  lea     rcx, [rbp+57h+var_A0]
0x140007fa3  movdqa  [rbp+57h+var_A0], xmm0
0x140007fa8  call    InitializeTelemetryAssertsKMWorkerInternal
0x140007fad  mov     edi, eax
0x140007faf  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x140007fb3  call    cs:__imp_RtlFreeAnsiString
0x140007fba  nop     dword ptr [rax+rax+00h]
0x140007fbf  mov     edx, 74727341h; Tag
0x140007fc4  mov     rcx, rbx; P
0x140007fc7  call    cs:__imp_ExFreePoolWithTag
0x140007fce  nop     dword ptr [rax+rax+00h]
0x140007fd3  mov     eax, edi
0x140007fd5  add     rsp, 0E0h
0x140007fdc  pop     r14
0x140007fde  pop     rdi
0x140007fdf  pop     rsi
0x140007fe0  pop     rbx
0x140007fe1  pop     rbp
0x140007fe2  retn
```
