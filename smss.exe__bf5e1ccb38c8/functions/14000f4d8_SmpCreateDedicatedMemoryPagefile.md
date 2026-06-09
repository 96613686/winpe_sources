# SmpCreateDedicatedMemoryPagefile

- ea: `0x14000f4d8`
- end: `0x14000f5a9`
- name: `SmpCreateDedicatedMemoryPagefile`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000fcf8`

## callees

- `0x14000f4d8`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x14000f554`
- `ntdll!NtQueryValueKey` at `0x14000f554`
- `ntdll!NtCreatePagingFile` at `0x14000f587`
- `ntdll!NtCreatePagingFile` at `0x14000f587`

## pseudocode

```c
int SmpCreateDedicatedMemoryPagefile()
{
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-50h] BYREF
  union _LARGE_INTEGER InitialSize; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+50h] [rbp-30h] BYREF
  __int128 KeyValueInformation; // [rsp+60h] [rbp-20h] BYREF

  ValueName.Buffer = L"DedicatedMemoryPagefileSizeMB";
  ResultLength = 0;
  FileName.Buffer = L"Dedicated memory pagefile";
  InitialSize.QuadPart = 0;
  *(_QWORD *)&ValueName.Length = 3932218;
  *(_QWORD *)&FileName.Length = 3407922;
  KeyValueInformation = 0;
  result = NtQueryValueKey(
             SmpMmKey,
             &ValueName,
             KeyValuePartialInformationAlign64,
             &KeyValueInformation,
             0x10u,
             &ResultLength);
  if ( result >= 0 )
  {
    if ( (_QWORD)KeyValueInformation == 0x400000004LL )
    {
      InitialSize.QuadPart = (unsigned __int64)DWORD2(KeyValueInformation) << 20;
      return NtCreatePagingFile(&FileName, &InitialSize, &InitialSize, 0x800000u);
    }
    else
    {
      return -1073741811;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000f4d8  push    rbp
0x14000f4da  mov     rbp, rsp
0x14000f4dd  sub     rsp, 80h
0x14000f4e4  mov     rax, cs:__security_cookie
0x14000f4eb  xor     rax, rsp
0x14000f4ee  mov     [rbp+var_10], rax
0x14000f4f2  mov     rcx, cs:SmpMmKey; KeyHandle
0x14000f4f9  lea     rax, aDedicatedmemor; "DedicatedMemoryPagefileSizeMB"
0x14000f500  mov     [rbp+ValueName.Buffer], rax
0x14000f504  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x14000f508  lea     rax, aDedicatedMemor; "Dedicated memory pagefile"
0x14000f50f  mov     [rbp+var_50], 0
0x14000f516  mov     [rbp+FileName.Buffer], rax
0x14000f51a  lea     rdx, [rbp+ValueName]; ValueName
0x14000f51e  lea     rax, [rbp+var_50]
0x14000f522  mov     qword ptr [rbp+InitialSize], 0
0x14000f52a  xorps   xmm0, xmm0
0x14000f52d  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14000f532  mov     r8d, 4; KeyValueInformationClass
0x14000f538  mov     [rsp+80h+Length], 10h; Length
0x14000f540  mov     qword ptr [rbp+ValueName.Length], 3C003Ah
0x14000f548  mov     qword ptr [rbp+FileName.Length], 340032h
0x14000f550  movups  [rbp+KeyValueInformation], xmm0
0x14000f554  call    cs:__imp_NtQueryValueKey
0x14000f55a  test    eax, eax
0x14000f55c  js      short loc_14000F594
0x14000f55e  cmp     dword ptr [rbp+KeyValueInformation], 4
0x14000f562  jnz     short loc_14000F58F
0x14000f564  cmp     dword ptr [rbp+KeyValueInformation+4], 4
0x14000f568  jnz     short loc_14000F58F
0x14000f56a  mov     eax, dword ptr [rbp+KeyValueInformation+8]
0x14000f56d  lea     r8, [rbp+InitialSize]; MaxiumSize
0x14000f571  shl     rax, 14h
0x14000f575  lea     rdx, [rbp+InitialSize]; InitialSize
0x14000f579  mov     r9d, 800000h; Reserved
0x14000f57f  mov     qword ptr [rbp+InitialSize], rax
0x14000f583  lea     rcx, [rbp+FileName]; FileName
0x14000f587  call    cs:__imp_NtCreatePagingFile
0x14000f58d  jmp     short loc_14000F594
0x14000f58f  mov     eax, 0C000000Dh
0x14000f594  mov     rcx, [rbp+var_10]
0x14000f598  xor     rcx, rsp; StackCookie
0x14000f59b  call    __security_check_cookie
0x14000f5a0  add     rsp, 80h
0x14000f5a7  pop     rbp
0x14000f5a8  retn
```
