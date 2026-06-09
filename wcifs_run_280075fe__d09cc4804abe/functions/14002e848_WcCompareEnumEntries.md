# WcCompareEnumEntries

- ea: `0x14002e848`
- end: `0x14002e93c`
- name: `WcCompareEnumEntries`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140030708`

## callees

- `0x140014198`
- `0x14002e848`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002e904`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002e904`

## pseudocode

```c
LONG __fastcall WcCompareEnumEntries(__int64 a1, __int64 a2)
{
  int v3; // edx
  __int64 EnumEntry; // rax
  int v5; // edi
  WCHAR *v6; // rbx
  int v7; // edx
  __int64 v8; // rax
  WCHAR *v9; // rcx
  int v10; // eax
  UNICODE_STRING String2; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+20h] BYREF
  int v15; // [rsp+78h] [rbp+28h] BYREF
  char v16; // [rsp+80h] [rbp+30h] BYREF

  v14 = 0;
  v3 = *(_DWORD *)(a1 + 56);
  v15 = 0;
  String1 = 0;
  String2 = 0;
  EnumEntry = WcGetEnumEntry(a1, v3, (unsigned int)&v14, (unsigned int)&v15, (__int64)&v16);
  if ( EnumEntry )
  {
    v5 = v15;
    v6 = (WCHAR *)(EnumEntry + v14);
  }
  else
  {
    v6 = 0;
    v5 = 0;
  }
  v7 = *(_DWORD *)(a2 + 56);
  v14 = 0;
  v15 = 0;
  v8 = WcGetEnumEntry(a2, v7, (unsigned int)&v14, (unsigned int)&v15, (__int64)&v16);
  if ( v8 )
  {
    v9 = (WCHAR *)(v8 + v14);
    v10 = v15;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  if ( !v5 )
    return -1;
  if ( !v10 )
    return 1;
  String2.Buffer = v9;
  String1.MaximumLength = v5;
  String1.Length = v5;
  String1.Buffer = v6;
  String2.MaximumLength = v10;
  String2.Length = v10;
  return RtlCompareUnicodeString(&String1, &String2, 1u);
}

```

## disassembly

```asm
0x14002e848  mov     [rsp-18h+arg_18], rbx
0x14002e84d  push    rbp
0x14002e84e  push    rsi
0x14002e84f  push    rdi
0x14002e850  mov     rbp, rsp
0x14002e853  sub     rsp, 50h
0x14002e857  mov     rsi, rdx
0x14002e85a  mov     [rbp+arg_0], 0
0x14002e861  mov     edx, [rcx+38h]
0x14002e864  lea     rax, [rbp+arg_10]
0x14002e868  xorps   xmm0, xmm0
0x14002e86b  mov     [rsp+50h+var_30], rax
0x14002e870  xorps   xmm1, xmm1
0x14002e873  mov     [rbp+arg_8], 0
0x14002e87a  lea     r9, [rbp+arg_8]
0x14002e87e  lea     r8, [rbp+arg_0]
0x14002e882  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14002e886  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14002e88a  call    WcGetEnumEntry
0x14002e88f  test    rax, rax
0x14002e892  jz      loc_14002E921
0x14002e898  mov     ebx, [rbp+arg_0]
0x14002e89b  mov     edi, [rbp+arg_8]
0x14002e89e  add     rbx, rax
0x14002e8a1  mov     edx, [rsi+38h]
0x14002e8a4  lea     rax, [rbp+arg_10]
0x14002e8a8  lea     r9, [rbp+arg_8]
0x14002e8ac  mov     [rsp+50h+var_30], rax
0x14002e8b1  lea     r8, [rbp+arg_0]
0x14002e8b5  mov     [rbp+arg_0], 0
0x14002e8bc  mov     rcx, rsi
0x14002e8bf  mov     [rbp+arg_8], 0
0x14002e8c6  call    WcGetEnumEntry
0x14002e8cb  test    rax, rax
0x14002e8ce  jz      short loc_14002E92A
0x14002e8d0  mov     ecx, [rbp+arg_0]
0x14002e8d3  add     rcx, rax
0x14002e8d6  mov     eax, [rbp+arg_8]
0x14002e8d9  test    edi, edi
0x14002e8db  jz      short loc_14002E930
0x14002e8dd  test    eax, eax
0x14002e8df  jz      short loc_14002E935
0x14002e8e1  mov     [rbp+String2.Buffer], rcx
0x14002e8e5  lea     rdx, [rbp+String2]; String2
0x14002e8e9  lea     rcx, [rbp+String1]; String1
0x14002e8ed  mov     [rbp+String1.MaximumLength], di
0x14002e8f1  mov     r8b, 1; CaseInSensitive
0x14002e8f4  mov     [rbp+String1.Length], di
0x14002e8f8  mov     [rbp+String1.Buffer], rbx
0x14002e8fc  mov     [rbp+String2.MaximumLength], ax
0x14002e900  mov     [rbp+String2.Length], ax
0x14002e904  call    cs:__imp_RtlCompareUnicodeString
0x14002e90b  nop     dword ptr [rax+rax+00h]
0x14002e910  mov     rbx, [rsp+50h+arg_18]
0x14002e918  add     rsp, 50h
0x14002e91c  pop     rdi
0x14002e91d  pop     rsi
0x14002e91e  pop     rbp
0x14002e91f  retn
0x14002e921  xor     ebx, ebx
0x14002e923  xor     edi, edi
0x14002e925  jmp     loc_14002E8A1
0x14002e92a  xor     ecx, ecx
0x14002e92c  xor     eax, eax
0x14002e92e  jmp     short loc_14002E8D9
0x14002e930  or      eax, 0FFFFFFFFh
0x14002e933  jmp     short loc_14002E910
0x14002e935  mov     eax, 1
0x14002e93a  jmp     short loc_14002E910
```
