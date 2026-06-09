# CmRegUtilCreateWstrKey

- ea: `0x14002161c`
- end: `0x1400216e7`
- name: `CmRegUtilCreateWstrKey`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140020eb8`
- `0x1400213a0`

## callees

- `0x140007dc4`
- `0x14002161c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x1400216a8`
- `ntoskrnl!ZwCreateKey` at `0x1400216a8`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilCreateWstrKey(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        ULONG a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS result; // eax
  void *v8; // r10
  NTSTATUS v9; // r8d
  void *v10; // rdx
  ULONG v11; // ecx
  void *KeyHandle; // [rsp+40h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+7h] BYREF
  ULONG Disposition; // [rsp+B8h] [rbp+67h] BYREF

  Disposition = a4;
  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    Disposition = 0;
    KeyHandle = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = a5;
    ObjectAttributes.RootDirectory = v8;
    ObjectAttributes.SecurityQualityOfService = 0;
    v9 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( v9 >= 0 )
    {
      v11 = Disposition;
      v10 = KeyHandle;
    }
    else
    {
      v10 = 0;
      v11 = 0;
    }
    *a7 = v10;
    if ( a6 )
      *a6 = v11;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x14002161c  mov     [rsp-8+arg_18], r9d
0x140021621  push    rbp
0x140021622  lea     rbp, [rsp-3Fh]
0x140021627  sub     rsp, 90h
0x14002162e  mov     r10, rcx
0x140021631  xorps   xmm0, xmm0
0x140021634  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140021638  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x14002163c  call    WdmlibRtlInitUnicodeStringEx
0x140021641  test    eax, eax
0x140021643  js      loc_1400216DD
0x140021649  xor     eax, eax
0x14002164b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140021653  mov     [rbp+3Fh+arg_18], eax
0x140021656  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14002165a  mov     [rbp+3Fh+KeyHandle], rax
0x14002165e  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140021662  lea     rax, [rbp+3Fh+DestinationString]
0x140021666  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x14002166e  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140021672  xor     r9d, r9d; TitleIndex
0x140021675  mov     rax, [rbp+3Fh+arg_20]
0x140021679  mov     edx, 0F003Fh; DesiredAccess
0x14002167e  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x140021682  lea     rax, [rbp+3Fh+arg_18]
0x140021686  mov     [rsp+90h+Disposition], rax; Disposition
0x14002168b  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x140021693  mov     [rsp+90h+Class], 0; Class
0x14002169c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r10
0x1400216a0  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x1400216a8  call    cs:__imp_ZwCreateKey
0x1400216af  nop     dword ptr [rax+rax+00h]
0x1400216b4  mov     r8d, eax
0x1400216b7  test    eax, eax
0x1400216b9  jns     short loc_1400216C1
0x1400216bb  xor     edx, edx
0x1400216bd  xor     ecx, ecx
0x1400216bf  jmp     short loc_1400216C8
0x1400216c1  mov     ecx, [rbp+3Fh+arg_18]
0x1400216c4  mov     rdx, [rbp+3Fh+KeyHandle]
0x1400216c8  mov     rax, [rbp+3Fh+arg_30]
0x1400216cc  mov     [rax], rdx
0x1400216cf  mov     rax, [rbp+3Fh+arg_28]
0x1400216d3  test    rax, rax
0x1400216d6  jz      short loc_1400216DA
0x1400216d8  mov     [rax], ecx
0x1400216da  mov     eax, r8d
0x1400216dd  add     rsp, 90h
0x1400216e4  pop     rbp
0x1400216e5  retn
```
