# VhdmpiCleanupPartMgrKey(void *,_UNICODE_STRING *)

- ea: `0x1400b744c`
- end: `0x1400b7609`
- name: `?VhdmpiCleanupPartMgrKey@@YAJPEAXPEAU_UNICODE_STRING@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400b7ba4`

## callees

- `0x1400b744c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400b74a0`
- `ntoskrnl!ZwOpenKey` at `0x1400b74a0`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b753d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b753d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7579`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7579`
- `ntoskrnl!ZwDeleteValueKey` at `0x1400b7598`
- `ntoskrnl!ZwDeleteValueKey` at `0x1400b7598`
- `ntoskrnl!ZwClose` at `0x1400b75cf`
- `ntoskrnl!ZwClose` at `0x1400b75cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b74d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b75e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b74d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b75e5`
- `ntoskrnl!ExAllocatePool2` at `0x1400b74f5`
- `ntoskrnl!ExAllocatePool2` at `0x1400b74f5`

## pseudocode

```c
__int64 __fastcall VhdmpiCleanupPartMgrKey(void *a1, struct _UNICODE_STRING *a2)
{
  __int64 v2; // rdi
  ULONG Length; // r14d
  NTSTATUS v4; // eax
  int v5; // ebx
  ULONG v6; // esi
  __int64 Pool2; // rax
  NTSTATUS v8; // eax
  unsigned int v9; // esi
  UNICODE_STRING String1; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+90h] [rbp+20h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+28h] BYREF

  v2 = 0;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  Length = 16;
  KeyHandle = 0;
  ResultLength = 16;
  String1 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x30019u, &ObjectAttributes);
LABEL_2:
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = 0;
    while ( 1 )
    {
      if ( v5 == -2147483643 || v5 == -1073741789 || !v2 )
      {
        if ( v2 )
        {
          ExFreePoolWithTag((PVOID)v2, 0);
          Length = ResultLength;
        }
        Pool2 = ExAllocatePool2(256, Length, 1329875030);
        v2 = Pool2;
        if ( !Pool2 )
        {
          v5 = -1073741670;
          break;
        }
        String1.Buffer = (PWSTR)(Pool2 + 12);
        String1.Length = 0;
        String1.MaximumLength = Length - 14;
      }
      v8 = ZwEnumerateValueKey(KeyHandle, v6, KeyValueBasicInformation, (PVOID)v2, Length, &ResultLength);
      v5 = v8;
      if ( v8 != -2147483643 && v8 != -1073741789 )
      {
        if ( v8 < 0 )
          break;
        String1.Length = *(_WORD *)(v2 + 8);
        if ( *(_DWORD *)(v2 + 4) != 1 || RtlCompareUnicodeString(&String1, &String2, 1u) )
        {
          v4 = ZwDeleteValueKey(KeyHandle, &String1);
          goto LABEL_2;
        }
        ++v6;
      }
    }
  }
  v9 = 0;
  if ( v5 != -2147483622 )
    v9 = v5;
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v2 )
    ExFreePoolWithTag((PVOID)v2, 0);
  return v9;
}

```

## disassembly

```asm
0x1400b744c  mov     [rsp-18h+arg_10], rbx
0x1400b7451  mov     [rsp-18h+arg_18], rsi
0x1400b7456  push    rbp
0x1400b7457  push    rdi
0x1400b7458  push    r14
0x1400b745a  mov     rbp, rsp
0x1400b745d  sub     rsp, 70h
0x1400b7461  xor     edi, edi
0x1400b7463  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1400b7467  xorps   xmm0, xmm0
0x1400b746a  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x1400b746e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400b7472  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400b747a  mov     edx, 30019h; DesiredAccess
0x1400b747f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400b7487  lea     r14d, [rdi+10h]
0x1400b748b  mov     [rbp+KeyHandle], rdi
0x1400b748f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400b7493  mov     [rbp+arg_0], r14d
0x1400b7497  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1400b749b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b74a0  call    cs:__imp_ZwOpenKey
0x1400b74a7  nop     dword ptr [rax+rax+00h]
0x1400b74ac  mov     ebx, eax
0x1400b74ae  test    eax, eax
0x1400b74b0  js      loc_1400B75BB
0x1400b74b6  xor     esi, esi
0x1400b74b8  cmp     ebx, 80000005h
0x1400b74be  jz      short loc_1400B74CD
0x1400b74c0  cmp     ebx, 0C0000023h
0x1400b74c6  jz      short loc_1400B74CD
0x1400b74c8  test    rdi, rdi
0x1400b74cb  jnz     short loc_1400B7523
0x1400b74cd  test    rdi, rdi
0x1400b74d0  jz      short loc_1400B74E7
0x1400b74d2  xor     edx, edx; Tag
0x1400b74d4  mov     rcx, rdi; P
0x1400b74d7  call    cs:__imp_ExFreePoolWithTag
0x1400b74de  nop     dword ptr [rax+rax+00h]
0x1400b74e3  mov     r14d, [rbp+arg_0]
0x1400b74e7  mov     edx, r14d
0x1400b74ea  mov     ecx, 100h
0x1400b74ef  mov     r8d, 4F444856h
0x1400b74f5  call    cs:__imp_ExAllocatePool2
0x1400b74fc  nop     dword ptr [rax+rax+00h]
0x1400b7501  mov     rdi, rax
0x1400b7504  test    rax, rax
0x1400b7507  jz      loc_1400B75B6
0x1400b750d  add     rax, 0Ch
0x1400b7511  mov     [rbp+String1.Buffer], rax
0x1400b7515  xor     eax, eax
0x1400b7517  mov     [rbp+String1.Length], ax
0x1400b751b  lea     eax, [r14-0Eh]
0x1400b751f  mov     [rbp+String1.MaximumLength], ax
0x1400b7523  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400b7527  lea     rax, [rbp+arg_0]
0x1400b752b  mov     [rsp+70h+ResultLength], rax; ResultLength
0x1400b7530  mov     r9, rdi; KeyValueInformation
0x1400b7533  xor     r8d, r8d; KeyValueInformationClass
0x1400b7536  mov     [rsp+70h+Length], r14d; Length
0x1400b753b  mov     edx, esi; Index
0x1400b753d  call    cs:__imp_ZwEnumerateValueKey
0x1400b7544  nop     dword ptr [rax+rax+00h]
0x1400b7549  mov     ebx, eax
0x1400b754b  cmp     eax, 80000005h
0x1400b7550  jz      short loc_1400B75A9
0x1400b7552  cmp     eax, 0C0000023h
0x1400b7557  jz      short loc_1400B75A9
0x1400b7559  test    eax, eax
0x1400b755b  js      short loc_1400B75BB
0x1400b755d  movzx   eax, word ptr [rdi+8]
0x1400b7561  mov     [rbp+String1.Length], ax
0x1400b7565  cmp     dword ptr [rdi+4], 1
0x1400b7569  jnz     short loc_1400B7590
0x1400b756b  mov     r8b, 1; CaseInSensitive
0x1400b756e  lea     rdx, String2; String2
0x1400b7575  lea     rcx, [rbp+String1]; String1
0x1400b7579  call    cs:__imp_RtlCompareUnicodeString
0x1400b7580  nop     dword ptr [rax+rax+00h]
0x1400b7585  test    eax, eax
0x1400b7587  jnz     short loc_1400B7590
0x1400b7589  inc     esi
0x1400b758b  jmp     loc_1400B74B8
0x1400b7590  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400b7594  lea     rdx, [rbp+String1]; ValueName
0x1400b7598  call    cs:__imp_ZwDeleteValueKey
0x1400b759f  nop     dword ptr [rax+rax+00h]
0x1400b75a4  jmp     loc_1400B74AC
0x1400b75a9  cmp     eax, 8000001Ah
0x1400b75ae  jnz     loc_1400B74B8
0x1400b75b4  jmp     short loc_1400B75BB
0x1400b75b6  mov     ebx, 0C000009Ah
0x1400b75bb  mov     rcx, [rbp+KeyHandle]; Handle
0x1400b75bf  xor     esi, esi
0x1400b75c1  cmp     ebx, 8000001Ah
0x1400b75c7  cmovnz  esi, ebx
0x1400b75ca  test    rcx, rcx
0x1400b75cd  jz      short loc_1400B75DB
0x1400b75cf  call    cs:__imp_ZwClose
0x1400b75d6  nop     dword ptr [rax+rax+00h]
0x1400b75db  test    rdi, rdi
0x1400b75de  jz      short loc_1400B75F1
0x1400b75e0  xor     edx, edx; Tag
0x1400b75e2  mov     rcx, rdi; P
0x1400b75e5  call    cs:__imp_ExFreePoolWithTag
0x1400b75ec  nop     dword ptr [rax+rax+00h]
0x1400b75f1  lea     r11, [rsp+70h+var_s0]
0x1400b75f6  mov     eax, esi
0x1400b75f8  mov     rbx, [r11+30h]
0x1400b75fc  mov     rsi, [r11+38h]
0x1400b7600  mov     rsp, r11
0x1400b7603  pop     r14
0x1400b7605  pop     rdi
0x1400b7606  pop     rbp
0x1400b7607  retn
```
