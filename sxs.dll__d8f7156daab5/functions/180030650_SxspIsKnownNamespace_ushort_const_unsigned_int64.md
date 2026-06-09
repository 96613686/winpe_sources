# SxspIsKnownNamespace(ushort const *,unsigned __int64)

- ea: `0x180030650`
- end: `0x180030811`
- name: `?SxspIsKnownNamespace@@YA_NPEBG_K@Z`
- size: `449`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180031260`

## callees

- `0x180030650`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800306b9`
- `ntdll!RtlCompareUnicodeString` at `0x180030725`
- `ntdll!RtlCompareUnicodeString` at `0x18003076d`
- `ntdll!RtlCompareUnicodeString` at `0x1800307b4`
- `ntdll!RtlCompareUnicodeString` at `0x1800307f6`
- `ntdll!RtlCompareUnicodeString` at `0x1800306b9`
- `ntdll!RtlCompareUnicodeString` at `0x180030725`
- `ntdll!RtlCompareUnicodeString` at `0x18003076d`
- `ntdll!RtlCompareUnicodeString` at `0x1800307b4`
- `ntdll!RtlCompareUnicodeString` at `0x1800307f6`

## string_xrefs

- `0x1800306f7`: `urn:schemas-microsoft-com:winrt.v1`
- `0x18003069b`: `urn:schemas-microsoft-com:asm.v1`
- `0x180030786`: `urn:schemas-microsoft-com:asm.v2`
- `0x1800307c8`: `urn:schemas-microsoft-com:asm.v3`
- `0x18003073f`: `urn:schemas-microsoft-com:msix.v1`

## pseudocode

```c
bool __fastcall SxspIsKnownNamespace(WCHAR *a1, __int64 a2)
{
  USHORT v2; // di
  UNICODE_STRING String2; // [rsp+20h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-20h] BYREF

  v2 = 2 * a2;
  if ( a2 != 32 )
  {
    if ( a2 != 34
      || (*(&String2.MaximumLength + 2) = 0,
          String1.Buffer = L"urn:schemas-microsoft-com:winrt.v1",
          *(_QWORD *)&String1.Length = 4456516,
          String2.Buffer = a1,
          String2.Length = 68,
          *(_DWORD *)&String2.MaximumLength = 68,
          RtlCompareUnicodeString(&String2, &String1, 0)) )
    {
      if ( a2 != 33 )
        return 0;
      *(_DWORD *)(&String2.MaximumLength + 1) = 0;
      String1.Buffer = L"urn:schemas-microsoft-com:msix.v1";
      *(_QWORD *)&String1.Length = 4325442;
      String2.Buffer = a1;
      String2.Length = v2;
      String2.MaximumLength = v2;
      if ( RtlCompareUnicodeString(&String2, &String1, 0) )
        return 0;
    }
    return 1;
  }
  *(_QWORD *)&String2.Length = 4194368;
  *(&String1.MaximumLength + 2) = 0;
  String1.Buffer = a1;
  String1.Length = 64;
  *(_DWORD *)&String1.MaximumLength = 64;
  String2.Buffer = L"urn:schemas-microsoft-com:asm.v1";
  if ( !RtlCompareUnicodeString(&String1, &String2, 0) )
    return 1;
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String1.Buffer = L"urn:schemas-microsoft-com:asm.v2";
  *(_QWORD *)&String1.Length = 4194368;
  String2.Buffer = a1;
  String2.Length = v2;
  String2.MaximumLength = v2;
  if ( !RtlCompareUnicodeString(&String2, &String1, 0) )
    return 1;
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String1.Buffer = L"urn:schemas-microsoft-com:asm.v3";
  *(_QWORD *)&String1.Length = 4194368;
  String2.Buffer = a1;
  String2.Length = v2;
  String2.MaximumLength = v2;
  return !RtlCompareUnicodeString(&String2, &String1, 0);
}

```

## disassembly

```asm
0x180030650  mov     [rsp-18h+arg_10], rbx
0x180030655  mov     [rsp-18h+arg_18], rsi
0x18003065a  push    rbp
0x18003065b  push    rdi
0x18003065c  push    r14
0x18003065e  mov     rbp, rsp
0x180030661  sub     rsp, 50h
0x180030665  mov     rax, cs:__security_cookie
0x18003066c  xor     rax, rsp
0x18003066f  mov     [rbp+var_10], rax
0x180030673  movzx   edi, dx
0x180030676  xor     r14d, r14d
0x180030679  add     di, di
0x18003067c  mov     rbx, rdx
0x18003067f  mov     rsi, rcx
0x180030682  cmp     rdx, 20h ; ' '
0x180030686  jnz     short loc_1800306F1
0x180030688  xorps   xmm0, xmm0
0x18003068b  mov     qword ptr [rbp+String2.Length], 400040h
0x180030693  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180030697  mov     [rbp+String1.Buffer], rcx
0x18003069b  lea     rax, aUrnSchemasMicr_2; "urn:schemas-microsoft-com:asm.v1"
0x1800306a2  lea     rcx, [rbp+String1]; String1
0x1800306a6  mov     [rbp+String1.Length], di
0x1800306aa  xor     r8d, r8d; CaseInsensitive
0x1800306ad  mov     [rbp+String1.MaximumLength], di
0x1800306b1  lea     rdx, [rbp+String2]; String2
0x1800306b5  mov     [rbp+String2.Buffer], rax
0x1800306b9  call    cs:__imp_RtlCompareUnicodeString
0x1800306c0  nop     dword ptr [rax+rax+00h]
0x1800306c5  test    eax, eax
0x1800306c7  jnz     loc_180030786
0x1800306cd  mov     al, 1
0x1800306cf  mov     rcx, [rbp+var_10]
0x1800306d3  xor     rcx, rsp; StackCookie
0x1800306d6  call    __security_check_cookie
0x1800306db  lea     r11, [rsp+50h+var_s0]
0x1800306e0  mov     rbx, [r11+30h]
0x1800306e4  mov     rsi, [r11+38h]
0x1800306e8  mov     rsp, r11
0x1800306eb  pop     r14
0x1800306ed  pop     rdi
0x1800306ee  pop     rbp
0x1800306ef  retn
0x1800306f1  cmp     rbx, 22h ; '"'
0x1800306f5  jnz     short loc_180030735
0x1800306f7  lea     rax, aUrnSchemasMicr_11; "urn:schemas-microsoft-com:winrt.v1"
0x1800306fe  mov     dword ptr [rbp+String2+4], r14d
0x180030702  xor     r8d, r8d; CaseInsensitive
0x180030705  mov     [rbp+String1.Buffer], rax
0x180030709  lea     rdx, [rbp+String1]; String2
0x18003070d  mov     qword ptr [rbp+String1.Length], 440044h
0x180030715  lea     rcx, [rbp+String2]; String1
0x180030719  mov     [rbp+String2.Buffer], rsi
0x18003071d  mov     [rbp+String2.Length], di
0x180030721  mov     [rbp+String2.MaximumLength], di
0x180030725  call    cs:__imp_RtlCompareUnicodeString
0x18003072c  nop     dword ptr [rax+rax+00h]
0x180030731  test    eax, eax
0x180030733  jz      short loc_1800306CD
0x180030735  cmp     rbx, 21h ; '!'
0x180030739  jnz     loc_18003080A
0x18003073f  lea     rax, aUrnSchemasMicr_8; "urn:schemas-microsoft-com:msix.v1"
0x180030746  mov     dword ptr [rbp+String2+4], r14d
0x18003074a  xor     r8d, r8d; CaseInsensitive
0x18003074d  mov     [rbp+String1.Buffer], rax
0x180030751  lea     rdx, [rbp+String1]; String2
0x180030755  mov     qword ptr [rbp+String1.Length], 420042h
0x18003075d  lea     rcx, [rbp+String2]; String1
0x180030761  mov     [rbp+String2.Buffer], rsi
0x180030765  mov     [rbp+String2.Length], di
0x180030769  mov     [rbp+String2.MaximumLength], di
0x18003076d  call    cs:__imp_RtlCompareUnicodeString
0x180030774  nop     dword ptr [rax+rax+00h]
0x180030779  test    eax, eax
0x18003077b  jnz     loc_18003080A
0x180030781  jmp     loc_1800306CD
0x180030786  lea     rax, aUrnSchemasMicr_4; "urn:schemas-microsoft-com:asm.v2"
0x18003078d  mov     dword ptr [rbp+String2+4], r14d
0x180030791  xor     r8d, r8d; CaseInsensitive
0x180030794  mov     [rbp+String1.Buffer], rax
0x180030798  lea     rdx, [rbp+String1]; String2
0x18003079c  mov     qword ptr [rbp+String1.Length], 400040h
0x1800307a4  lea     rcx, [rbp+String2]; String1
0x1800307a8  mov     [rbp+String2.Buffer], rsi
0x1800307ac  mov     [rbp+String2.Length], di
0x1800307b0  mov     [rbp+String2.MaximumLength], di
0x1800307b4  call    cs:__imp_RtlCompareUnicodeString
0x1800307bb  nop     dword ptr [rax+rax+00h]
0x1800307c0  test    eax, eax
0x1800307c2  jz      loc_1800306CD
0x1800307c8  lea     rax, aUrnSchemasMicr_14; "urn:schemas-microsoft-com:asm.v3"
0x1800307cf  mov     dword ptr [rbp+String2+4], r14d
0x1800307d3  xor     r8d, r8d; CaseInsensitive
0x1800307d6  mov     [rbp+String1.Buffer], rax
0x1800307da  lea     rdx, [rbp+String1]; String2
0x1800307de  mov     qword ptr [rbp+String1.Length], 400040h
0x1800307e6  lea     rcx, [rbp+String2]; String1
0x1800307ea  mov     [rbp+String2.Buffer], rsi
0x1800307ee  mov     [rbp+String2.Length], di
0x1800307f2  mov     [rbp+String2.MaximumLength], di
0x1800307f6  call    cs:__imp_RtlCompareUnicodeString
0x1800307fd  nop     dword ptr [rax+rax+00h]
0x180030802  test    eax, eax
0x180030804  jz      loc_1800306CD
0x18003080a  xor     al, al
0x18003080c  jmp     loc_1800306CF
```
