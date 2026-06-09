# VhdmpiCleanupPartMgrKey(void *,_UNICODE_STRING *)

- ea: `0x1400b7464`
- end: `0x1400b7621`
- name: `?VhdmpiCleanupPartMgrKey@@YAJPEAXPEAU_UNICODE_STRING@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400b7bbc`

## callees

- `0x1400b7464`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400b74b8`
- `ntoskrnl!ZwOpenKey` at `0x1400b74b8`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b7555`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400b7555`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7591`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7591`
- `ntoskrnl!ZwDeleteValueKey` at `0x1400b75b0`
- `ntoskrnl!ZwDeleteValueKey` at `0x1400b75b0`
- `ntoskrnl!ZwClose` at `0x1400b75e7`
- `ntoskrnl!ZwClose` at `0x1400b75e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b74ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b75fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b74ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b75fd`
- `ntoskrnl!ExAllocatePool2` at `0x1400b750d`
- `ntoskrnl!ExAllocatePool2` at `0x1400b750d`

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
0x1400b7464  mov     [rsp-18h+arg_10], rbx
0x1400b7469  mov     [rsp-18h+arg_18], rsi
0x1400b746e  push    rbp
0x1400b746f  push    rdi
0x1400b7470  push    r14
0x1400b7472  mov     rbp, rsp
0x1400b7475  sub     rsp, 70h
0x1400b7479  xor     edi, edi
0x1400b747b  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1400b747f  xorps   xmm0, xmm0
0x1400b7482  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x1400b7486  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400b748a  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400b7492  mov     edx, 30019h; DesiredAccess
0x1400b7497  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400b749f  lea     r14d, [rdi+10h]
0x1400b74a3  mov     [rbp+KeyHandle], rdi
0x1400b74a7  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400b74ab  mov     [rbp+arg_0], r14d
0x1400b74af  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1400b74b3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b74b8  call    cs:__imp_ZwOpenKey
0x1400b74bf  nop     dword ptr [rax+rax+00h]
0x1400b74c4  mov     ebx, eax
0x1400b74c6  test    eax, eax
0x1400b74c8  js      loc_1400B75D3
0x1400b74ce  xor     esi, esi
0x1400b74d0  cmp     ebx, 80000005h
0x1400b74d6  jz      short loc_1400B74E5
0x1400b74d8  cmp     ebx, 0C0000023h
0x1400b74de  jz      short loc_1400B74E5
0x1400b74e0  test    rdi, rdi
0x1400b74e3  jnz     short loc_1400B753B
0x1400b74e5  test    rdi, rdi
0x1400b74e8  jz      short loc_1400B74FF
0x1400b74ea  xor     edx, edx; Tag
0x1400b74ec  mov     rcx, rdi; P
0x1400b74ef  call    cs:__imp_ExFreePoolWithTag
0x1400b74f6  nop     dword ptr [rax+rax+00h]
0x1400b74fb  mov     r14d, [rbp+arg_0]
0x1400b74ff  mov     edx, r14d
0x1400b7502  mov     ecx, 100h
0x1400b7507  mov     r8d, 4F444856h
0x1400b750d  call    cs:__imp_ExAllocatePool2
0x1400b7514  nop     dword ptr [rax+rax+00h]
0x1400b7519  mov     rdi, rax
0x1400b751c  test    rax, rax
0x1400b751f  jz      loc_1400B75CE
0x1400b7525  add     rax, 0Ch
0x1400b7529  mov     [rbp+String1.Buffer], rax
0x1400b752d  xor     eax, eax
0x1400b752f  mov     [rbp+String1.Length], ax
0x1400b7533  lea     eax, [r14-0Eh]
0x1400b7537  mov     [rbp+String1.MaximumLength], ax
0x1400b753b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400b753f  lea     rax, [rbp+arg_0]
0x1400b7543  mov     [rsp+70h+ResultLength], rax; ResultLength
0x1400b7548  mov     r9, rdi; KeyValueInformation
0x1400b754b  xor     r8d, r8d; KeyValueInformationClass
0x1400b754e  mov     [rsp+70h+Length], r14d; Length
0x1400b7553  mov     edx, esi; Index
0x1400b7555  call    cs:__imp_ZwEnumerateValueKey
0x1400b755c  nop     dword ptr [rax+rax+00h]
0x1400b7561  mov     ebx, eax
0x1400b7563  cmp     eax, 80000005h
0x1400b7568  jz      short loc_1400B75C1
0x1400b756a  cmp     eax, 0C0000023h
0x1400b756f  jz      short loc_1400B75C1
0x1400b7571  test    eax, eax
0x1400b7573  js      short loc_1400B75D3
0x1400b7575  movzx   eax, word ptr [rdi+8]
0x1400b7579  mov     [rbp+String1.Length], ax
0x1400b757d  cmp     dword ptr [rdi+4], 1
0x1400b7581  jnz     short loc_1400B75A8
0x1400b7583  mov     r8b, 1; CaseInSensitive
0x1400b7586  lea     rdx, String2; String2
0x1400b758d  lea     rcx, [rbp+String1]; String1
0x1400b7591  call    cs:__imp_RtlCompareUnicodeString
0x1400b7598  nop     dword ptr [rax+rax+00h]
0x1400b759d  test    eax, eax
0x1400b759f  jnz     short loc_1400B75A8
0x1400b75a1  inc     esi
0x1400b75a3  jmp     loc_1400B74D0
0x1400b75a8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400b75ac  lea     rdx, [rbp+String1]; ValueName
0x1400b75b0  call    cs:__imp_ZwDeleteValueKey
0x1400b75b7  nop     dword ptr [rax+rax+00h]
0x1400b75bc  jmp     loc_1400B74C4
0x1400b75c1  cmp     eax, 8000001Ah
0x1400b75c6  jnz     loc_1400B74D0
0x1400b75cc  jmp     short loc_1400B75D3
0x1400b75ce  mov     ebx, 0C000009Ah
0x1400b75d3  mov     rcx, [rbp+KeyHandle]; Handle
0x1400b75d7  xor     esi, esi
0x1400b75d9  cmp     ebx, 8000001Ah
0x1400b75df  cmovnz  esi, ebx
0x1400b75e2  test    rcx, rcx
0x1400b75e5  jz      short loc_1400B75F3
0x1400b75e7  call    cs:__imp_ZwClose
0x1400b75ee  nop     dword ptr [rax+rax+00h]
0x1400b75f3  test    rdi, rdi
0x1400b75f6  jz      short loc_1400B7609
0x1400b75f8  xor     edx, edx; Tag
0x1400b75fa  mov     rcx, rdi; P
0x1400b75fd  call    cs:__imp_ExFreePoolWithTag
0x1400b7604  nop     dword ptr [rax+rax+00h]
0x1400b7609  lea     r11, [rsp+70h+var_s0]
0x1400b760e  mov     eax, esi
0x1400b7610  mov     rbx, [r11+30h]
0x1400b7614  mov     rsi, [r11+38h]
0x1400b7618  mov     rsp, r11
0x1400b761b  pop     r14
0x1400b761d  pop     rdi
0x1400b761e  pop     rbp
0x1400b761f  retn
```
