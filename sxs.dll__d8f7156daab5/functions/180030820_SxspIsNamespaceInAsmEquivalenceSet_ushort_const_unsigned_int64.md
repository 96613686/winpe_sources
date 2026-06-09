# SxspIsNamespaceInAsmEquivalenceSet(ushort const *,unsigned __int64)

- ea: `0x180030820`
- end: `0x180030947`
- name: `?SxspIsNamespaceInAsmEquivalenceSet@@YA_NPEBG_K@Z`
- size: `295`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ee20`
- `0x180031260`

## callees

- `0x180030820`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18003088a`
- `ntdll!RtlCompareUnicodeString` at `0x1800308ec`
- `ntdll!RtlCompareUnicodeString` at `0x18003092e`
- `ntdll!RtlCompareUnicodeString` at `0x18003088a`
- `ntdll!RtlCompareUnicodeString` at `0x1800308ec`
- `ntdll!RtlCompareUnicodeString` at `0x18003092e`

## string_xrefs

- `0x180030866`: `urn:schemas-microsoft-com:asm.v1`
- `0x180030900`: `urn:schemas-microsoft-com:asm.v2`
- `0x1800308be`: `urn:schemas-microsoft-com:asm.v3`

## pseudocode

```c
bool __fastcall SxspIsNamespaceInAsmEquivalenceSet(WCHAR *a1, __int64 a2)
{
  UNICODE_STRING String2; // [rsp+20h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-20h] BYREF

  if ( a2 != 32 )
    return 0;
  *(_QWORD *)&String2.Length = 4194368;
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  String1.Buffer = a1;
  String2.Buffer = L"urn:schemas-microsoft-com:asm.v1";
  String1.Length = 64;
  String1.MaximumLength = 64;
  if ( !RtlCompareUnicodeString(&String1, &String2, 0) )
    return 1;
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String1.Buffer = L"urn:schemas-microsoft-com:asm.v2";
  *(_QWORD *)&String1.Length = 4194368;
  String2.Buffer = a1;
  String2.Length = 64;
  String2.MaximumLength = 64;
  if ( !RtlCompareUnicodeString(&String2, &String1, 0) )
    return 1;
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String1.Buffer = L"urn:schemas-microsoft-com:asm.v3";
  *(_QWORD *)&String1.Length = 4194368;
  String2.Buffer = a1;
  String2.Length = 64;
  String2.MaximumLength = 64;
  return !RtlCompareUnicodeString(&String2, &String1, 0);
}

```

## disassembly

```asm
0x180030820  mov     [rsp-18h+arg_10], rbx
0x180030825  mov     [rsp-18h+arg_18], rsi
0x18003082a  push    rbp
0x18003082b  push    rdi
0x18003082c  push    r14
0x18003082e  mov     rbp, rsp
0x180030831  sub     rsp, 50h
0x180030835  mov     rax, cs:__security_cookie
0x18003083c  xor     rax, rsp
0x18003083f  mov     [rbp+var_10], rax
0x180030843  mov     rbx, rdx
0x180030846  mov     rdi, rcx
0x180030849  cmp     rdx, 20h ; ' '
0x18003084d  jnz     loc_1800308FC
0x180030853  xorps   xmm0, xmm0
0x180030856  mov     qword ptr [rbp+String2.Length], 400040h
0x18003085e  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180030862  mov     [rbp+String1.Buffer], rcx
0x180030866  lea     rax, aUrnSchemasMicr_2; "urn:schemas-microsoft-com:asm.v1"
0x18003086d  add     bx, bx
0x180030870  mov     [rbp+String2.Buffer], rax
0x180030874  lea     rcx, [rbp+String1]; String1
0x180030878  mov     [rbp+String1.Length], bx
0x18003087c  xor     r8d, r8d; CaseInsensitive
0x18003087f  mov     [rbp+String1.MaximumLength], bx
0x180030883  lea     rdx, [rbp+String2]; String2
0x180030887  xor     r14d, r14d
0x18003088a  call    cs:__imp_RtlCompareUnicodeString
0x180030891  nop     dword ptr [rax+rax+00h]
0x180030896  test    eax, eax
0x180030898  jnz     short loc_180030900
0x18003089a  mov     al, 1
0x18003089c  mov     rcx, [rbp+var_10]
0x1800308a0  xor     rcx, rsp; StackCookie
0x1800308a3  call    __security_check_cookie
0x1800308a8  lea     r11, [rsp+50h+var_s0]
0x1800308ad  mov     rbx, [r11+30h]
0x1800308b1  mov     rsi, [r11+38h]
0x1800308b5  mov     rsp, r11
0x1800308b8  pop     r14
0x1800308ba  pop     rdi
0x1800308bb  pop     rbp
0x1800308bc  retn
0x1800308be  lea     rax, aUrnSchemasMicr_14; "urn:schemas-microsoft-com:asm.v3"
0x1800308c5  mov     dword ptr [rbp+String2+4], r14d
0x1800308c9  xor     r8d, r8d; CaseInsensitive
0x1800308cc  mov     [rbp+String1.Buffer], rax
0x1800308d0  lea     rdx, [rbp+String1]; String2
0x1800308d4  mov     qword ptr [rbp+String1.Length], 400040h
0x1800308dc  lea     rcx, [rbp+String2]; String1
0x1800308e0  mov     [rbp+String2.Buffer], rdi
0x1800308e4  mov     [rbp+String2.Length], bx
0x1800308e8  mov     [rbp+String2.MaximumLength], bx
0x1800308ec  call    cs:__imp_RtlCompareUnicodeString
0x1800308f3  nop     dword ptr [rax+rax+00h]
0x1800308f8  test    eax, eax
0x1800308fa  jz      short loc_18003089A
0x1800308fc  xor     al, al
0x1800308fe  jmp     short loc_18003089C
0x180030900  lea     rax, aUrnSchemasMicr_4; "urn:schemas-microsoft-com:asm.v2"
0x180030907  mov     dword ptr [rbp+String2+4], r14d
0x18003090b  xor     r8d, r8d; CaseInsensitive
0x18003090e  mov     [rbp+String1.Buffer], rax
0x180030912  lea     rdx, [rbp+String1]; String2
0x180030916  mov     qword ptr [rbp+String1.Length], 400040h
0x18003091e  lea     rcx, [rbp+String2]; String1
0x180030922  mov     [rbp+String2.Buffer], rdi
0x180030926  mov     [rbp+String2.Length], bx
0x18003092a  mov     [rbp+String2.MaximumLength], bx
0x18003092e  call    cs:__imp_RtlCompareUnicodeString
0x180030935  nop     dword ptr [rax+rax+00h]
0x18003093a  test    eax, eax
0x18003093c  jz      loc_18003089A
0x180030942  jmp     loc_1800308BE
```
