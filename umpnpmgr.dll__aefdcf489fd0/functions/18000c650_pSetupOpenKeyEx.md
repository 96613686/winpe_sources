# pSetupOpenKeyEx

- ea: `0x18000c650`
- end: `0x18000c76a`
- name: `pSetupOpenKeyEx`
- size: `282`
- prototype: `__int64 __fastcall(void *, const WCHAR *, ACCESS_MASK, _QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bf60`
- `0x18000c050`
- `0x18000c180`
- `0x18000c944`
- `0x1800103f8`
- `0x180016f7c`
- `0x180017058`
- `0x1800170f0`
- `0x180017500`

## callees

- `0x18000c650`
- `0x18000c944`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000c70c`
- `ntdll!NtOpenKey` at `0x18000c70c`
- `ntdll!RtlInitUnicodeString` at `0x18000c6cb`
- `ntdll!RtlInitUnicodeString` at `0x18000c6cb`
- `ntdll!RtlNtStatusToDosError` at `0x18000c757`
- `ntdll!RtlNtStatusToDosError` at `0x18000c757`
- `ntdll!NtClose` at `0x18000c74d`
- `ntdll!NtClose` at `0x18000c74d`

## pseudocode

```c
__int64 __fastcall pSetupOpenKeyEx(void *a1, const WCHAR *a2, ACCESS_MASK a3, _QWORD *a4)
{
  HANDLE v4; // rdi
  void *v8; // rbx
  ULONG v9; // eax
  ULONG v10; // r15d
  int v11; // eax
  void *KeyHandle; // [rsp+20h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+8h] BYREF

  KeyHandle = 0;
  v4 = 0;
  Handle = 0;
  v8 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 > 7 )
  {
    v10 = 0;
  }
  else
  {
    v9 = pSetupOpenPredefinedKey(a1, &Handle);
    v4 = Handle;
    v10 = v9;
    if ( v9 )
      goto LABEL_7;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  if ( v4 )
    v8 = v4;
  ObjectAttributes.RootDirectory = v8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenKey(&KeyHandle, a3, &ObjectAttributes);
  if ( v11 < 0 )
    v10 = RtlNtStatusToDosError(v11);
  else
    *a4 = (int)KeyHandle;
LABEL_7:
  if ( v4 )
    NtClose((HANDLE)(unsigned int)v4);
  return v10;
}

```

## disassembly

```asm
0x18000c650  mov     r11, rsp
0x18000c653  push    rdi
0x18000c654  push    r15
0x18000c656  sub     rsp, 78h
0x18000c65a  xor     eax, eax
0x18000c65c  mov     [r11+10h], rbx
0x18000c660  xorps   xmm0, xmm0
0x18000c663  mov     [r11+18h], rbp
0x18000c667  mov     [r11-68h], rax
0x18000c66b  xor     edi, edi
0x18000c66d  mov     [r11+20h], rsi
0x18000c671  mov     eax, 80000000h
0x18000c676  add     rax, rcx
0x18000c679  mov     [r11-18h], r14
0x18000c67d  mov     [r11+8], rdi
0x18000c681  mov     rsi, r9
0x18000c684  mov     ebp, r8d
0x18000c687  mov     r14, rdx
0x18000c68a  mov     rbx, rcx
0x18000c68d  movups  xmmword ptr [rsp+88h+ObjectAttributes.ObjectName], xmm0
0x18000c692  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18000c697  movups  xmmword ptr [rsp+88h+ObjectAttributes.Length], xmm0
0x18000c69c  movups  xmmword ptr [rsp+88h+ObjectAttributes+1Ch], xmm0
0x18000c6a1  cmp     rax, 7
0x18000c6a5  ja      loc_18000C762
0x18000c6ab  lea     rdx, [r11+8]
0x18000c6af  call    pSetupOpenPredefinedKey
0x18000c6b4  mov     rdi, [rsp+88h+Handle]
0x18000c6bc  mov     r15d, eax
0x18000c6bf  test    eax, eax
0x18000c6c1  jnz     short loc_18000C71E
0x18000c6c3  mov     rdx, r14; SourceString
0x18000c6c6  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18000c6cb  call    cs:__imp_RtlInitUnicodeString
0x18000c6d1  lea     rax, [rsp+88h+DestinationString]
0x18000c6d6  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x18000c6de  xorps   xmm0, xmm0
0x18000c6e1  mov     [rsp+88h+ObjectAttributes.Attributes], 40h ; '@'
0x18000c6e9  test    rdi, rdi
0x18000c6ec  mov     [rsp+88h+ObjectAttributes.ObjectName], rax
0x18000c6f1  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x18000c6f6  mov     edx, ebp; DesiredAccess
0x18000c6f8  cmovnz  rbx, rdi
0x18000c6fc  lea     rcx, [rsp+88h+KeyHandle]; KeyHandle
0x18000c701  mov     [rsp+88h+ObjectAttributes.RootDirectory], rbx
0x18000c706  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c70c  call    cs:__imp_NtOpenKey
0x18000c712  test    eax, eax
0x18000c714  js      short loc_18000C755
0x18000c716  movsxd  rax, dword ptr [rsp+88h+KeyHandle]
0x18000c71b  mov     [rsi], rax
0x18000c71e  mov     r14, [rsp+88h+var_18]
0x18000c723  mov     rsi, [rsp+88h+arg_18]
0x18000c72b  mov     rbp, [rsp+88h+arg_10]
0x18000c733  mov     rbx, [rsp+88h+arg_8]
0x18000c73b  test    rdi, rdi
0x18000c73e  jnz     short loc_18000C74B
0x18000c740  mov     eax, r15d
0x18000c743  add     rsp, 78h
0x18000c747  pop     r15
0x18000c749  pop     rdi
0x18000c74a  retn
0x18000c74b  mov     ecx, edi; Handle
0x18000c74d  call    cs:__imp_NtClose
0x18000c753  jmp     short loc_18000C740
0x18000c755  mov     ecx, eax; Status
0x18000c757  call    cs:__imp_RtlNtStatusToDosError
0x18000c75d  mov     r15d, eax
0x18000c760  jmp     short loc_18000C71E
0x18000c762  xor     r15d, r15d
0x18000c765  jmp     loc_18000C6C3
```
