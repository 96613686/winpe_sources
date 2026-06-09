# WcCompareEnumEntries

- ea: `0x14002e898`
- end: `0x14002e98c`
- name: `WcCompareEnumEntries`
- size: `244`
- prototype: `LONG __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140030758`

## callees

- `0x140014198`
- `0x14002e898`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002e954`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002e954`

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
0x14002e898  mov     [rsp-18h+arg_18], rbx
0x14002e89d  push    rbp
0x14002e89e  push    rsi
0x14002e89f  push    rdi
0x14002e8a0  mov     rbp, rsp
0x14002e8a3  sub     rsp, 50h
0x14002e8a7  mov     rsi, rdx
0x14002e8aa  mov     [rbp+arg_0], 0
0x14002e8b1  mov     edx, [rcx+38h]
0x14002e8b4  lea     rax, [rbp+arg_10]
0x14002e8b8  xorps   xmm0, xmm0
0x14002e8bb  mov     [rsp+50h+var_30], rax
0x14002e8c0  xorps   xmm1, xmm1
0x14002e8c3  mov     [rbp+arg_8], 0
0x14002e8ca  lea     r9, [rbp+arg_8]
0x14002e8ce  lea     r8, [rbp+arg_0]
0x14002e8d2  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14002e8d6  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14002e8da  call    WcGetEnumEntry
0x14002e8df  test    rax, rax
0x14002e8e2  jz      loc_14002E971
0x14002e8e8  mov     ebx, [rbp+arg_0]
0x14002e8eb  mov     edi, [rbp+arg_8]
0x14002e8ee  add     rbx, rax
0x14002e8f1  mov     edx, [rsi+38h]
0x14002e8f4  lea     rax, [rbp+arg_10]
0x14002e8f8  lea     r9, [rbp+arg_8]
0x14002e8fc  mov     [rsp+50h+var_30], rax
0x14002e901  lea     r8, [rbp+arg_0]
0x14002e905  mov     [rbp+arg_0], 0
0x14002e90c  mov     rcx, rsi
0x14002e90f  mov     [rbp+arg_8], 0
0x14002e916  call    WcGetEnumEntry
0x14002e91b  test    rax, rax
0x14002e91e  jz      short loc_14002E97A
0x14002e920  mov     ecx, [rbp+arg_0]
0x14002e923  add     rcx, rax
0x14002e926  mov     eax, [rbp+arg_8]
0x14002e929  test    edi, edi
0x14002e92b  jz      short loc_14002E980
0x14002e92d  test    eax, eax
0x14002e92f  jz      short loc_14002E985
0x14002e931  mov     [rbp+String2.Buffer], rcx
0x14002e935  lea     rdx, [rbp+String2]; String2
0x14002e939  lea     rcx, [rbp+String1]; String1
0x14002e93d  mov     [rbp+String1.MaximumLength], di
0x14002e941  mov     r8b, 1; CaseInSensitive
0x14002e944  mov     [rbp+String1.Length], di
0x14002e948  mov     [rbp+String1.Buffer], rbx
0x14002e94c  mov     [rbp+String2.MaximumLength], ax
0x14002e950  mov     [rbp+String2.Length], ax
0x14002e954  call    cs:__imp_RtlCompareUnicodeString
0x14002e95b  nop     dword ptr [rax+rax+00h]
0x14002e960  mov     rbx, [rsp+50h+arg_18]
0x14002e968  add     rsp, 50h
0x14002e96c  pop     rdi
0x14002e96d  pop     rsi
0x14002e96e  pop     rbp
0x14002e96f  retn
0x14002e971  xor     ebx, ebx
0x14002e973  xor     edi, edi
0x14002e975  jmp     loc_14002E8F1
0x14002e97a  xor     ecx, ecx
0x14002e97c  xor     eax, eax
0x14002e97e  jmp     short loc_14002E929
0x14002e980  or      eax, 0FFFFFFFFh
0x14002e983  jmp     short loc_14002E960
0x14002e985  mov     eax, 1
0x14002e98a  jmp     short loc_14002E960
```
