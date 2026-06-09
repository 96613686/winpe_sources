# SclDosPathToNtPath

- ea: `0x180007ac4`
- end: `0x180007b2a`
- name: `SclDosPathToNtPath`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180002b98`
- `0x180004428`
- `0x180004844`
- `0x180004c88`
- `0x1800051d8`
- `0x18000548c`
- `0x180007cac`
- `0x18000d220`
- `0x18000deec`

## callees

- `0x180007ac4`
- `0x18000a75c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180007b17`
- `ntdll!RtlFreeUnicodeString` at `0x180007b17`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180007ae4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180007ae4`

## pseudocode

```c
__int64 __fastcall SclDosPathToNtPath(__int64 a1, _QWORD *a2)
{
  int v3; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  UnicodeString = 0;
  v3 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
  if ( v3 >= 0 )
    v3 = SclCloneString(UnicodeString.Buffer, (unsigned __int64)UnicodeString.Length >> 1, a2, 0);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007ac4  mov     [rsp+arg_0], rbx
0x180007ac9  push    rdi
0x180007aca  sub     rsp, 30h
0x180007ace  mov     rdi, rdx
0x180007ad1  xorps   xmm0, xmm0
0x180007ad4  lea     rdx, [rsp+38h+UnicodeString]
0x180007ad9  xor     r9d, r9d
0x180007adc  xor     r8d, r8d
0x180007adf  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x180007ae4  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180007aea  mov     ebx, eax
0x180007aec  test    eax, eax
0x180007aee  js      short loc_180007B0A
0x180007af0  movzx   edx, [rsp+38h+UnicodeString.Length]
0x180007af5  xor     r9d, r9d
0x180007af8  mov     rcx, [rsp+38h+UnicodeString.Buffer]
0x180007afd  mov     r8, rdi
0x180007b00  shr     rdx, 1
0x180007b03  call    SclCloneString
0x180007b08  mov     ebx, eax
0x180007b0a  cmp     [rsp+38h+UnicodeString.Buffer], 0
0x180007b10  jz      short loc_180007B1D
0x180007b12  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180007b17  call    cs:__imp_RtlFreeUnicodeString
0x180007b1d  mov     eax, ebx
0x180007b1f  mov     rbx, [rsp+38h+arg_0]
0x180007b24  add     rsp, 30h
0x180007b28  pop     rdi
0x180007b29  retn
```
