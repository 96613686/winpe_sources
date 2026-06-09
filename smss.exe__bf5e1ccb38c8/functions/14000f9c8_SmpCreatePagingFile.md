# SmpCreatePagingFile

- ea: `0x14000f9c8`
- end: `0x14000fa6d`
- name: `SmpCreatePagingFile`
- size: `165`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000b4ac`
- `0x14000f6f4`

## callees

- `0x1400010ec`
- `0x14000d494`
- `0x14000f9c8`

## import_xrefs

- `ntdll!NtCreatePagingFile` at `0x14000f9ee`
- `ntdll!NtCreatePagingFile` at `0x14000f9ee`
- `ntdll!RtlCompareUnicodeString` at `0x14000fa17`
- `ntdll!RtlCompareUnicodeString` at `0x14000fa17`

## string_xrefs

- `0x14000fa47`: `SmpCreatePagingFile`

## pseudocode

```c
__int64 __fastcall SmpCreatePagingFile(
        UNICODE_STRING *String2,
        union _LARGE_INTEGER a2,
        union _LARGE_INTEGER a3,
        ULONG a4)
{
  NTSTATUS v5; // eax
  unsigned int v6; // esi
  __int64 v7; // rbx
  LONG v8; // eax
  __int64 *v9; // rbp
  PWSTR Buffer; // r8
  union _LARGE_INTEGER v12; // [rsp+48h] [rbp+10h] BYREF
  union _LARGE_INTEGER v13; // [rsp+50h] [rbp+18h] BYREF

  v13 = a2;
  v12 = a3;
  v5 = NtCreatePagingFile(String2, &v13, &v12, a4);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( String2 )
      Buffer = String2->Buffer;
    else
      Buffer = 0;
    SmpLogFailureString("SmpCreatePagingFile", 2046, Buffer, (unsigned int)v5);
  }
  else
  {
    v7 = SmpExistingPageFilesList;
    if ( (__int64 *)SmpExistingPageFilesList != &SmpExistingPageFilesList )
    {
      do
      {
        v8 = RtlCompareUnicodeString((PCUNICODE_STRING)(v7 + 16), String2, 1u);
        v9 = *(__int64 **)v7;
        if ( !v8 )
          SmpFreeSavedRegistryEntry(v7);
        v7 = (__int64)v9;
      }
      while ( v9 != &SmpExistingPageFilesList );
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14000f9c8  mov     rax, rsp
0x14000f9cb  mov     [rax+8], rbx
0x14000f9cf  mov     [rax+20h], rbp
0x14000f9d3  push    rsi
0x14000f9d4  push    rdi
0x14000f9d5  push    r14
0x14000f9d7  sub     rsp, 20h
0x14000f9db  mov     [rax+18h], rdx
0x14000f9df  mov     rdi, rcx
0x14000f9e2  mov     [rax+10h], r8
0x14000f9e6  lea     rdx, [rax+18h]; InitialSize
0x14000f9ea  lea     r8, [rax+10h]; MaxiumSize
0x14000f9ee  call    cs:__imp_NtCreatePagingFile
0x14000f9f4  mov     esi, eax
0x14000f9f6  test    eax, eax
0x14000f9f8  js      short loc_14000FA36
0x14000f9fa  mov     rbx, cs:SmpExistingPageFilesList
0x14000fa01  lea     r14, SmpExistingPageFilesList
0x14000fa08  cmp     rbx, r14
0x14000fa0b  jz      short loc_14000FA58
0x14000fa0d  lea     rcx, [rbx+10h]; String1
0x14000fa11  mov     r8b, 1; CaseInSensitive
0x14000fa14  mov     rdx, rdi; String2
0x14000fa17  call    cs:__imp_RtlCompareUnicodeString
0x14000fa1d  mov     rbp, [rbx]
0x14000fa20  test    eax, eax
0x14000fa22  jnz     short loc_14000FA2C
0x14000fa24  mov     rcx, rbx
0x14000fa27  call    SmpFreeSavedRegistryEntry
0x14000fa2c  mov     rbx, rbp
0x14000fa2f  cmp     rbp, r14
0x14000fa32  jnz     short loc_14000FA0D
0x14000fa34  jmp     short loc_14000FA58
0x14000fa36  test    rdi, rdi
0x14000fa39  jz      short loc_14000FA41
0x14000fa3b  mov     r8, [rdi+8]
0x14000fa3f  jmp     short loc_14000FA44
0x14000fa41  xor     r8d, r8d
0x14000fa44  mov     r9d, esi
0x14000fa47  lea     rcx, aSmpcreatepagin; "SmpCreatePagingFile"
0x14000fa4e  mov     edx, 7FEh
0x14000fa53  call    SmpLogFailureString
0x14000fa58  mov     rbx, [rsp+38h+arg_0]
0x14000fa5d  mov     eax, esi
0x14000fa5f  mov     rbp, [rsp+38h+arg_18]
0x14000fa64  add     rsp, 20h
0x14000fa68  pop     r14
0x14000fa6a  pop     rdi
0x14000fa6b  pop     rsi
0x14000fa6c  retn
```
