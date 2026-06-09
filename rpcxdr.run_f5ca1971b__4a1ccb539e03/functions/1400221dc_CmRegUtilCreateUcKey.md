# CmRegUtilCreateUcKey

- ea: `0x1400221dc`
- end: `0x140022280`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140022288`

## callees

- `0x1400221dc`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140022244`
- `ntoskrnl!ZwCreateKey` at `0x140022244`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
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
0x1400221dc  mov     [rsp-8+arg_18], r9d
0x1400221e1  push    rbp
0x1400221e2  mov     rbp, rsp
0x1400221e5  sub     rsp, 70h
0x1400221e9  xor     eax, eax
0x1400221eb  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1400221ef  mov     [rbp+arg_18], eax
0x1400221f2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400221f6  mov     [rbp+KeyHandle], rax
0x1400221fa  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400221fe  mov     rax, [rbp+arg_20]
0x140022202  xor     r9d, r9d; TitleIndex
0x140022205  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140022209  lea     rax, [rbp+arg_18]
0x14002220d  mov     [rsp+70h+Disposition], rax; Disposition
0x140022212  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x140022216  mov     edx, 0F003Fh; DesiredAccess
0x14002221b  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x140022223  mov     [rsp+70h+Class], 0; Class
0x14002222c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140022234  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14002223c  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140022244  call    cs:__imp_ZwCreateKey
0x14002224b  nop     dword ptr [rax+rax+00h]
0x140022250  mov     r8d, eax
0x140022253  test    eax, eax
0x140022255  jns     short loc_14002225D
0x140022257  xor     edx, edx
0x140022259  xor     ecx, ecx
0x14002225b  jmp     short loc_140022264
0x14002225d  mov     ecx, [rbp+arg_18]
0x140022260  mov     rdx, [rbp+KeyHandle]
0x140022264  mov     rax, [rbp+arg_30]
0x140022268  mov     [rax], rdx
0x14002226b  mov     rax, [rbp+arg_28]
0x14002226f  test    rax, rax
0x140022272  jz      short loc_140022276
0x140022274  mov     [rax], ecx
0x140022276  mov     eax, r8d
0x140022279  add     rsp, 70h
0x14002227d  pop     rbp
0x14002227e  retn
```
