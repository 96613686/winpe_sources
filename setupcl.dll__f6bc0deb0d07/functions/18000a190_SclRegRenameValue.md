# SclRegRenameValue

- ea: `0x18000a190`
- end: `0x18000a32b`
- name: `SclRegRenameValue`
- size: `411`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, const WCHAR *, const WCHAR *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180009668`
- `0x18000a190`
- `0x18000a4a0`
- `0x18000a524`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a1e9`
- `ntdll!RtlInitUnicodeString` at `0x18000a1f6`
- `ntdll!RtlInitUnicodeString` at `0x18000a1e9`
- `ntdll!RtlInitUnicodeString` at `0x18000a1f6`
- `ntdll!RtlFreeHeap` at `0x18000a303`
- `ntdll!RtlFreeHeap` at `0x18000a303`
- `ntdll!NtDeleteValueKey` at `0x18000a2a8`
- `ntdll!NtDeleteValueKey` at `0x18000a2a8`
- `ntdll!NtSetValueKey` at `0x18000a295`
- `ntdll!NtSetValueKey` at `0x18000a295`

## string_xrefs

- `0x18000a227`: `Can't rename reg value [%ws] to [%ws]; the target already exists`
- `0x18000a20b`: `SclRegRenameValue`
- `0x18000a2b9`: `(%lx): Failed to rename value [%ws] to [%ws]`

## pseudocode

```c
__int64 __fastcall SclRegRenameValue(HANDLE KeyHandle, const WCHAR *a2, const WCHAR *a3)
{
  PVOID v3; // rdi
  NTSTATUS v7; // ebx
  int Value; // eax
  ULONG Data; // [rsp+20h] [rbp-50h]
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  PVOID P; // [rsp+B8h] [rbp+48h] BYREF

  v3 = 0;
  P = 0;
  DestinationString = 0;
  ValueName = 0;
  if ( !KeyHandle || !a2 || !a3 )
    return 3221225485LL;
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&ValueName, a3);
  v7 = SclRegValueExists(KeyHandle);
  if ( v7 < 0
    || (Value = SclRegGetValue(KeyHandle, a2, 0, &P, Data), v3 = P, v7 = Value, Value < 0)
    || (v7 = NtSetValueKey(KeyHandle, &ValueName, 0, *((_DWORD *)P + 1), (char *)P + 12, *((_DWORD *)P + 2)), v7 < 0)
    || (v7 = NtDeleteValueKey(KeyHandle, &DestinationString), v7 < 0) )
  {
    SclLogGenericMessage(
      0,
      3,
      (int)SclEvent_Generic_Error,
      2259,
      (__int64)"SclRegRenameValue",
      "(%lx): Failed to rename value [%ws] to [%ws]",
      v7,
      a2,
      a3);
  }
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a190  mov     [rsp-28h+arg_8], rbx
0x18000a195  mov     [rsp-28h+arg_10], rsi
0x18000a19a  push    rbp
0x18000a19b  push    rdi
0x18000a19c  push    r13
0x18000a19e  push    r14
0x18000a1a0  push    r15
0x18000a1a2  mov     rbp, rsp
0x18000a1a5  sub     rsp, 70h
0x18000a1a9  xor     edi, edi
0x18000a1ab  xorps   xmm0, xmm0
0x18000a1ae  mov     [rbp+P], rdi
0x18000a1b2  xorps   xmm1, xmm1
0x18000a1b5  mov     [rbp+arg_0], dil
0x18000a1b9  mov     r15, r8
0x18000a1bc  mov     rsi, rdx
0x18000a1bf  mov     r14, rcx
0x18000a1c2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a1c6  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x18000a1ca  test    rcx, rcx
0x18000a1cd  jz      loc_18000A30D
0x18000a1d3  test    rdx, rdx
0x18000a1d6  jz      loc_18000A30D
0x18000a1dc  test    r8, r8
0x18000a1df  jz      loc_18000A30D
0x18000a1e5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a1e9  call    cs:__imp_RtlInitUnicodeString
0x18000a1ef  mov     rdx, r15; SourceString
0x18000a1f2  lea     rcx, [rbp+ValueName]; DestinationString
0x18000a1f6  call    cs:__imp_RtlInitUnicodeString
0x18000a1fc  lea     r8, [rbp+arg_0]
0x18000a200  mov     rdx, r15
0x18000a203  mov     rcx, r14; KeyHandle
0x18000a206  call    SclRegValueExists
0x18000a20b  lea     r13, aSclregrenameva; "SclRegRenameValue"
0x18000a212  mov     ebx, eax
0x18000a214  test    eax, eax
0x18000a216  js      loc_18000A2B4
0x18000a21c  cmp     [rbp+arg_0], dil
0x18000a220  jz      short loc_18000A25B
0x18000a222  mov     [rsp+70h+var_38], r15
0x18000a227  lea     rax, aCanTRenameRegV; "Can't rename reg value [%ws] to [%ws]; "...
0x18000a22e  mov     [rsp+70h+var_40], rsi
0x18000a233  lea     r8, SclEvent_Generic_Error
0x18000a23a  mov     qword ptr [rsp+70h+DataSize], rax
0x18000a23f  lea     edx, [rdi+3]
0x18000a242  mov     r9d, 8B9h
0x18000a248  mov     [rsp+70h+Data], r13
0x18000a24d  xor     ecx, ecx
0x18000a24f  mov     ebx, 0C0000035h
0x18000a254  call    SclLogGenericMessage
0x18000a259  jmp     short loc_18000A2B4
0x18000a25b  lea     r9, [rbp+P]
0x18000a25f  xor     r8d, r8d
0x18000a262  mov     rdx, rsi
0x18000a265  mov     rcx, r14; KeyHandle
0x18000a268  call    SclRegGetValue
0x18000a26d  mov     rdi, [rbp+P]
0x18000a271  mov     ebx, eax
0x18000a273  test    eax, eax
0x18000a275  js      short loc_18000A2B4
0x18000a277  mov     eax, [rdi+8]
0x18000a27a  lea     rcx, [rdi+0Ch]
0x18000a27e  mov     r9d, [rdi+4]; Type
0x18000a282  lea     rdx, [rbp+ValueName]; ValueName
0x18000a286  mov     [rsp+70h+DataSize], eax; DataSize
0x18000a28a  xor     r8d, r8d; TitleIndex
0x18000a28d  mov     [rsp+70h+Data], rcx; Data
0x18000a292  mov     rcx, r14; KeyHandle
0x18000a295  call    cs:__imp_NtSetValueKey
0x18000a29b  mov     ebx, eax
0x18000a29d  test    eax, eax
0x18000a29f  js      short loc_18000A2B4
0x18000a2a1  lea     rdx, [rbp+DestinationString]; ValueName
0x18000a2a5  mov     rcx, r14; KeyHandle
0x18000a2a8  call    cs:__imp_NtDeleteValueKey
0x18000a2ae  mov     ebx, eax
0x18000a2b0  test    eax, eax
0x18000a2b2  jns     short loc_18000A2EC
0x18000a2b4  mov     [rsp+70h+var_30], r15
0x18000a2b9  lea     rax, aLxFailedToRena; "(%lx): Failed to rename value [%ws] to "...
0x18000a2c0  mov     [rsp+70h+var_38], rsi
0x18000a2c5  lea     r8, SclEvent_Generic_Error
0x18000a2cc  mov     dword ptr [rsp+70h+var_40], ebx
0x18000a2d0  mov     r9d, 8D3h
0x18000a2d6  mov     qword ptr [rsp+70h+DataSize], rax
0x18000a2db  mov     edx, 3
0x18000a2e0  xor     ecx, ecx
0x18000a2e2  mov     [rsp+70h+Data], r13
0x18000a2e7  call    SclLogGenericMessage
0x18000a2ec  test    rdi, rdi
0x18000a2ef  jz      short loc_18000A309
0x18000a2f1  mov     rcx, gs:60h
0x18000a2fa  mov     r8, rdi; P
0x18000a2fd  xor     edx, edx; Flags
0x18000a2ff  mov     rcx, [rcx+30h]; HeapHandle
0x18000a303  call    cs:__imp_RtlFreeHeap
0x18000a309  mov     eax, ebx
0x18000a30b  jmp     short loc_18000A312
0x18000a30d  mov     eax, 0C000000Dh
0x18000a312  lea     r11, [rsp+70h+var_s0]
0x18000a317  mov     rbx, [r11+38h]
0x18000a31b  mov     rsi, [r11+40h]
0x18000a31f  mov     rsp, r11
0x18000a322  pop     r15
0x18000a324  pop     r14
0x18000a326  pop     r13
0x18000a328  pop     rdi
0x18000a329  pop     rbp
0x18000a32a  retn
```
