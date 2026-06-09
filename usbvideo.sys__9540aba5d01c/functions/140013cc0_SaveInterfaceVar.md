# SaveInterfaceVar

- ea: `0x140013cc0`
- end: `0x140013dc0`
- name: `SaveInterfaceVar`
- size: `256`
- prototype: `__int64 __fastcall(PCWCH String1, ULONG Type, PVOID Data, ULONG DataSize, HANDLE KeyHandle, PCWSTR SourceString)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140013cc0`
- `0x140023040`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x140013da4`
- `ntoskrnl!ZwSetValueKey` at `0x140013da4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013cfc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013d10`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013d6f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013cfc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013d10`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013d6f`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140013d45`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140013d45`

## pseudocode

```c
__int64 __fastcall SaveInterfaceVar(
        PCWCH String1,
        ULONG Type,
        PVOID Data,
        ULONG DataSize,
        HANDLE KeyHandle,
        PCWSTR SourceString)
{
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-10h] BYREF

  v11 = 0;
  DestinationString = 0;
  if ( KeyHandle )
  {
    RtlInitUnicodeString(&DestinationString, String1);
    RtlInitUnicodeString(&v11, SourceString);
    if ( SourceString )
    {
      if ( DestinationString.Length >= v11.Length
        && !RtlCompareUnicodeStrings(
              String1,
              (unsigned __int64)v11.Length >> 1,
              v11.Buffer,
              (unsigned __int64)v11.Length >> 1,
              1u) )
      {
        ValueName = 0;
        RtlInitUnicodeString(&ValueName, &DestinationString.Buffer[(unsigned __int64)v11.Length >> 1]);
        if ( !(unsigned __int8)IsRegValuePresent(KeyHandle) )
          ZwSetValueKey(KeyHandle, &ValueName, 0, Type, Data, DataSize);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140013cc0  push    rbp
0x140013cc2  push    rsi
0x140013cc3  push    r12
0x140013cc5  push    r14
0x140013cc7  push    r15
0x140013cc9  mov     rbp, rsp
0x140013ccc  sub     rsp, 60h
0x140013cd0  cmp     [rbp+KeyHandle], 0
0x140013cd5  xorps   xmm0, xmm0
0x140013cd8  xorps   xmm1, xmm1
0x140013cdb  mov     r14d, r9d
0x140013cde  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x140013ce2  mov     r15, r8
0x140013ce5  mov     r12d, edx
0x140013ce8  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140013cec  mov     rsi, rcx
0x140013cef  jz      loc_140013DB0
0x140013cf5  mov     rdx, rcx; SourceString
0x140013cf8  lea     rcx, [rbp+DestinationString]; DestinationString
0x140013cfc  call    cs:__imp_RtlInitUnicodeString
0x140013d03  nop     dword ptr [rax+rax+00h]
0x140013d08  mov     rdx, [rbp+SourceString]; SourceString
0x140013d0c  lea     rcx, [rbp+var_30]; DestinationString
0x140013d10  call    cs:__imp_RtlInitUnicodeString
0x140013d17  nop     dword ptr [rax+rax+00h]
0x140013d1c  cmp     [rbp+SourceString], 0
0x140013d21  jz      loc_140013DB0
0x140013d27  movzx   eax, [rbp+var_30.Length]
0x140013d2b  cmp     [rbp+DestinationString.Length], ax
0x140013d2f  jb      short loc_140013DB0
0x140013d31  mov     r8, [rbp+var_30.Buffer]; String2
0x140013d35  mov     edx, eax
0x140013d37  shr     rdx, 1; String1Length
0x140013d3a  mov     rcx, rsi; String1
0x140013d3d  mov     r9, rdx; String2Length
0x140013d40  mov     [rsp+60h+CaseInSensitive], 1; CaseInSensitive
0x140013d45  call    cs:__imp_RtlCompareUnicodeStrings
0x140013d4c  nop     dword ptr [rax+rax+00h]
0x140013d51  test    eax, eax
0x140013d53  jnz     short loc_140013DB0
0x140013d55  movzx   ecx, [rbp+var_30.Length]
0x140013d59  xorps   xmm0, xmm0
0x140013d5c  mov     rax, [rbp+DestinationString.Buffer]
0x140013d60  shr     rcx, 1
0x140013d63  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140013d67  lea     rdx, [rax+rcx*2]; SourceString
0x140013d6b  lea     rcx, [rbp+ValueName]; DestinationString
0x140013d6f  call    cs:__imp_RtlInitUnicodeString
0x140013d76  nop     dword ptr [rax+rax+00h]
0x140013d7b  mov     rdx, [rbp+ValueName.Buffer]
0x140013d7f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013d83  call    IsRegValuePresent
0x140013d88  test    al, al
0x140013d8a  jnz     short loc_140013DB0
0x140013d8c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013d90  lea     rdx, [rbp+ValueName]; ValueName
0x140013d94  mov     [rsp+60h+DataSize], r14d; DataSize
0x140013d99  mov     r9d, r12d; Type
0x140013d9c  xor     r8d, r8d; TitleIndex
0x140013d9f  mov     qword ptr [rsp+60h+CaseInSensitive], r15; Data
0x140013da4  call    cs:__imp_ZwSetValueKey
0x140013dab  nop     dword ptr [rax+rax+00h]
0x140013db0  xor     eax, eax
0x140013db2  add     rsp, 60h
0x140013db6  pop     r15
0x140013db8  pop     r14
0x140013dba  pop     r12
0x140013dbc  pop     rsi
0x140013dbd  pop     rbp
0x140013dbe  retn
```
