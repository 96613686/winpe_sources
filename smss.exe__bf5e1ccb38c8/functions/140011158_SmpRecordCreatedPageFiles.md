# SmpRecordCreatedPageFiles

- ea: `0x140011158`
- end: `0x1400112bf`
- name: `SmpRecordCreatedPageFiles`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fcf8`

## callees

- `0x14000d4c0`
- `0x14000d53c`
- `0x140011158`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400112a2`
- `ntdll!RtlFreeHeap` at `0x1400112a2`
- `ntdll!NtSetValueKey` at `0x140011212`
- `ntdll!NtSetValueKey` at `0x14001125d`
- `ntdll!NtSetValueKey` at `0x140011212`
- `ntdll!NtSetValueKey` at `0x14001125d`
- `ntdll!RtlCompareMemory` at `0x1400111d6`
- `ntdll!RtlCompareMemory` at `0x1400111d6`
- `ntdll!NtDeleteValueKey` at `0x140011232`
- `ntdll!NtDeleteValueKey` at `0x140011232`
- `ntdll!NtFlushKey` at `0x140011271`
- `ntdll!NtFlushKey` at `0x140011271`

## string_xrefs

- `0x140011183`: `TempPageFile`
- `0x14001121f`: `SmpRecordCreatedPageFiles`
- `0x14001127e`: `SmpRecordCreatedPageFiles`

## pseudocode

```c
__int64 __fastcall SmpRecordCreatedPageFiles(char a1, __int64 a2)
{
  __int64 result; // rax
  char v5; // si
  __int64 v6; // rbx
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  void *Source2[2]; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v11; // [rsp+50h] [rbp-10h] BYREF
  int Data; // [rsp+90h] [rbp+30h] BYREF

  *(_QWORD *)&v11.Length = 2359330;
  v11.Buffer = L"ExistingPageFiles";
  *(_QWORD *)&ValueName.Length = 1703960;
  ValueName.Buffer = L"TempPageFile";
  *(_OWORD *)Source2 = 0;
  result = SmpBuildFilesStringFromList(&SmpPagingFileDescriptorList, Source2);
  if ( (int)result >= 0 )
  {
    v5 = 0;
    if ( a2 )
    {
      if ( *(_WORD *)a2 != LOWORD(Source2[0])
        || (v6 = LOWORD(Source2[0]), v6 != RtlCompareMemory(*(const void **)(a2 + 8), Source2[1], LOWORD(Source2[0]))) )
      {
        v5 = 1;
      }
    }
    if ( a1 )
    {
      Data = 1;
      v7 = NtSetValueKey(SmpMmKey, &ValueName, 0, 4u, &Data, 4u);
      if ( v7 < 0 )
        SmpLogFailure("SmpRecordCreatedPageFiles", 4471, (unsigned int)v7);
    }
    else
    {
      NtDeleteValueKey(SmpMmKey, &ValueName);
    }
    v8 = NtSetValueKey(SmpMmKey, &v11, 0, 7u, Source2[1], LOWORD(Source2[0]));
    if ( v5 )
      NtFlushKey(SmpMmKey);
    if ( v8 < 0 )
      SmpLogFailure("SmpRecordCreatedPageFiles", 4490, (unsigned int)v8);
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Source2[1]);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x140011158  mov     [rsp-18h+arg_0], rbx
0x14001115d  mov     [rsp-18h+arg_8], rsi
0x140011162  push    rbp
0x140011163  push    rdi
0x140011164  push    r14
0x140011166  mov     rbp, rsp
0x140011169  sub     rsp, 60h
0x14001116d  lea     rax, aExistingpagefi; "ExistingPageFiles"
0x140011174  mov     qword ptr [rbp+var_10.Length], 240022h
0x14001117c  mov     [rbp+var_10.Buffer], rax
0x140011180  mov     rdi, rdx
0x140011183  lea     rax, aTemppagefile; "TempPageFile"
0x14001118a  mov     qword ptr [rbp+ValueName.Length], 1A0018h
0x140011192  mov     r14b, cl
0x140011195  mov     [rbp+ValueName.Buffer], rax
0x140011199  xorps   xmm0, xmm0
0x14001119c  lea     rdx, [rbp+Source2]
0x1400111a0  lea     rcx, SmpPagingFileDescriptorList
0x1400111a7  movups  xmmword ptr [rbp+Source2], xmm0
0x1400111ab  call    SmpBuildFilesStringFromList
0x1400111b0  test    eax, eax
0x1400111b2  js      loc_1400112AA
0x1400111b8  xor     sil, sil
0x1400111bb  test    rdi, rdi
0x1400111be  jz      short loc_1400111E4
0x1400111c0  movzx   eax, word ptr [rbp+Source2]
0x1400111c4  cmp     [rdi], ax
0x1400111c7  jnz     short loc_1400111E1
0x1400111c9  mov     rdx, [rbp+Source2+8]; Source2
0x1400111cd  mov     r8d, eax; Length
0x1400111d0  mov     rcx, [rdi+8]; Source1
0x1400111d4  mov     ebx, eax
0x1400111d6  call    cs:__imp_RtlCompareMemory
0x1400111dc  cmp     rbx, rax
0x1400111df  jz      short loc_1400111E4
0x1400111e1  mov     sil, 1
0x1400111e4  mov     rcx, cs:SmpMmKey; KeyHandle
0x1400111eb  lea     rdx, [rbp+ValueName]; ValueName
0x1400111ef  test    r14b, r14b
0x1400111f2  jz      short loc_140011232
0x1400111f4  mov     r9d, 4; Type
0x1400111fa  mov     [rbp+arg_10], 1
0x140011201  lea     rax, [rbp+arg_10]
0x140011205  mov     [rsp+60h+DataSize], r9d; DataSize
0x14001120a  xor     r8d, r8d; TitleIndex
0x14001120d  mov     [rsp+60h+Data], rax; Data
0x140011212  call    cs:__imp_NtSetValueKey
0x140011218  test    eax, eax
0x14001121a  jns     short loc_140011238
0x14001121c  mov     r8d, eax
0x14001121f  lea     rcx, aSmprecordcreat; "SmpRecordCreatedPageFiles"
0x140011226  mov     edx, 1177h
0x14001122b  call    SmpLogFailure
0x140011230  jmp     short loc_140011238
0x140011232  call    cs:__imp_NtDeleteValueKey
0x140011238  movzx   eax, word ptr [rbp+Source2]
0x14001123c  lea     rdx, [rbp+var_10]; ValueName
0x140011240  mov     rcx, cs:SmpMmKey; KeyHandle
0x140011247  mov     r9d, 7; Type
0x14001124d  mov     [rsp+60h+DataSize], eax; DataSize
0x140011251  xor     r8d, r8d; TitleIndex
0x140011254  mov     rax, [rbp+Source2+8]
0x140011258  mov     [rsp+60h+Data], rax; Data
0x14001125d  call    cs:__imp_NtSetValueKey
0x140011263  mov     ebx, eax
0x140011265  test    sil, sil
0x140011268  jz      short loc_140011277
0x14001126a  mov     rcx, cs:SmpMmKey; KeyHandle
0x140011271  call    cs:__imp_NtFlushKey
0x140011277  test    ebx, ebx
0x140011279  jns     short loc_14001128F
0x14001127b  mov     r8d, ebx
0x14001127e  lea     rcx, aSmprecordcreat; "SmpRecordCreatedPageFiles"
0x140011285  mov     edx, 118Ah
0x14001128a  call    SmpLogFailure
0x14001128f  mov     rcx, gs:60h
0x140011298  xor     edx, edx; Flags
0x14001129a  mov     r8, [rbp+Source2+8]; BaseAddress
0x14001129e  mov     rcx, [rcx+30h]; HeapHandle
0x1400112a2  call    cs:__imp_RtlFreeHeap
0x1400112a8  mov     eax, ebx
0x1400112aa  lea     r11, [rsp+60h+var_s0]
0x1400112af  mov     rbx, [r11+20h]
0x1400112b3  mov     rsi, [r11+28h]
0x1400112b7  mov     rsp, r11
0x1400112ba  pop     r14
0x1400112bc  pop     rdi
0x1400112bd  pop     rbp
0x1400112be  retn
```
