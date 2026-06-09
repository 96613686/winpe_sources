# CmRegUtilCreateUcKey

- ea: `0x14001941c`
- end: `0x1400194c0`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400194c8`

## callees

- `0x14001941c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140019484`
- `ntoskrnl!ZwCreateKey` at `0x140019484`

## pseudocode

```c
__int64 __fastcall CmRegUtilCreateUcKey(
        void *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS v7; // r8d
  void *v8; // rdx
  ULONG v9; // ecx
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp+28h] BYREF

  ObjectAttributes.RootDirectory = a1;
  Disposition = 0;
  KeyHandle = 0;
  ObjectAttributes.SecurityDescriptor = a5;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  v7 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( v7 >= 0 )
  {
    v9 = Disposition;
    v8 = KeyHandle;
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  *a7 = v8;
  if ( a6 )
    *a6 = v9;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001941c  mov     [rsp-8+arg_18], r9d
0x140019421  push    rbp
0x140019422  mov     rbp, rsp
0x140019425  sub     rsp, 70h
0x140019429  xor     eax, eax
0x14001942b  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14001942f  mov     [rbp+arg_18], eax
0x140019432  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140019436  mov     [rbp+KeyHandle], rax
0x14001943a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001943e  mov     rax, [rbp+arg_20]
0x140019442  xor     r9d, r9d; TitleIndex
0x140019445  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140019449  lea     rax, [rbp+arg_18]
0x14001944d  mov     [rsp+70h+Disposition], rax; Disposition
0x140019452  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x140019456  mov     edx, 0F003Fh; DesiredAccess
0x14001945b  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x140019463  mov     [rsp+70h+Class], 0; Class
0x14001946c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140019474  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14001947c  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140019484  call    cs:__imp_ZwCreateKey
0x14001948b  nop     dword ptr [rax+rax+00h]
0x140019490  mov     r8d, eax
0x140019493  test    eax, eax
0x140019495  jns     short loc_14001949D
0x140019497  xor     edx, edx
0x140019499  xor     ecx, ecx
0x14001949b  jmp     short loc_1400194A4
0x14001949d  mov     ecx, [rbp+arg_18]
0x1400194a0  mov     rdx, [rbp+KeyHandle]
0x1400194a4  mov     rax, [rbp+arg_30]
0x1400194a8  mov     [rax], rdx
0x1400194ab  mov     rax, [rbp+arg_28]
0x1400194af  test    rax, rax
0x1400194b2  jz      short loc_1400194B6
0x1400194b4  mov     [rax], ecx
0x1400194b6  mov     eax, r8d
0x1400194b9  add     rsp, 70h
0x1400194bd  pop     rbp
0x1400194be  retn
```
