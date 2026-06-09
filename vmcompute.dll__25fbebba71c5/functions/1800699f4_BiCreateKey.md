# BiCreateKey

- ea: `0x1800699f4`
- end: `0x180069d0d`
- name: `BiCreateKey`
- size: `793`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180063dcc`
- `0x1800650c8`

## callees

- `0x1800699f4`
- `0x180069d14`
- `0x18006a2d4`
- `0x18006b6fc`
- `0x18006fbc0`
- `0x18006fc48`
- `0x1800724f0`

## import_xrefs

- `ntdll!ZwClose` at `0x180069c1c`
- `ntdll!ZwClose` at `0x180069c7d`
- `ntdll!ZwClose` at `0x180069c1c`
- `ntdll!ZwClose` at `0x180069c7d`
- `ntdll!ZwCreateKey` at `0x180069b8f`
- `ntdll!ZwCreateKey` at `0x180069b8f`
- `ntdll!ZwSetSecurityObject` at `0x180069bd6`
- `ntdll!ZwSetSecurityObject` at `0x180069bd6`
- `ntdll!RtlFreeHeap` at `0x180069ca0`
- `ntdll!RtlFreeHeap` at `0x180069ca0`
- `ntdll!RtlInitUnicodeString` at `0x180069a5b`
- `ntdll!RtlInitUnicodeString` at `0x180069a5b`

## pseudocode

```c
__int64 __fastcall BiCreateKey(
        unsigned __int64 a1,
        const WCHAR *a2,
        ACCESS_MASK a3,
        unsigned int a4,
        void **a5,
        bool *a6)
{
  char v6; // r14
  const WCHAR *v8; // rax
  ULONG v10; // edi
  ACCESS_MASK v11; // r15d
  char v12; // r13
  struct _ACL *KeySecurityDescriptor; // r14
  NTSTATUS v14; // edi
  unsigned int v15; // eax
  unsigned int v16; // eax
  NTSTATUS v17; // eax
  __int64 v19; // [rsp+40h] [rbp-A8h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-A0h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-90h]
  void *v23; // [rsp+60h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-70h] BYREF

  v6 = a4;
  v8 = a2;
  Disposition = 0;
  v23 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v22 = 0;
  while ( 1 )
  {
    KeyHandle = 0;
    RtlInitUnicodeString(&DestinationString, v8);
    a1 &= ~2uLL;
    a3 |= 0x40000u;
    v10 = 64;
    v11 = a3;
    v12 = 0;
    if ( (v6 & 1) != 0 )
    {
      v10 = 192;
      if ( (a3 & 0x60019) != a3 )
      {
        v11 = 0x40000;
        v12 = 1;
      }
    }
    KeySecurityDescriptor = BiCreateKeySecurityDescriptor(0xF003Fu);
    if ( KeySecurityDescriptor )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = (HANDLE)a1;
      ObjectAttributes.Attributes = v10;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.SecurityDescriptor = KeySecurityDescriptor;
      ObjectAttributes.SecurityQualityOfService = 0;
      v19 = 0;
      if ( (a1 & 1) != 0 )
      {
        v15 = ORCreateKey(
                a1 & 0xFFFFFFFFFFFFFFFEuLL,
                DestinationString.Buffer,
                0,
                (a4 >> 1) & 1,
                KeySecurityDescriptor,
                &v19,
                &Disposition);
        v14 = BiDosErrorToNtStatus(v15);
        if ( v14 >= 0 )
          KeyHandle = (void *)(v19 | 1);
      }
      else
      {
        v14 = ZwCreateKey(&KeyHandle, v11, &ObjectAttributes, 0, 0, (a4 >> 1) & 1, &Disposition);
      }
      LODWORD(v19) = v14;
      if ( v14 < 0 )
        goto LABEL_26;
      if ( v12 )
      {
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        {
          v16 = ORSetKeySecurity((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL, 4, KeySecurityDescriptor);
          v17 = BiDosErrorToNtStatus(v16);
        }
        else
        {
          v17 = ZwSetSecurityObject(KeyHandle, 4u, KeySecurityDescriptor);
        }
        v14 = v17;
        if ( v17 < 0 )
        {
          LODWORD(v19) = v17;
          goto LABEL_25;
        }
        v14 = BiZwOpenKey(&v23);
        LODWORD(v19) = v14;
        if ( v14 < 0 )
          goto LABEL_25;
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
          ORCloseKey((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL);
        else
          ZwClose(KeyHandle);
        KeyHandle = v23;
      }
      if ( a6 )
        *a6 = Disposition == 1;
      *a5 = KeyHandle;
LABEL_25:
      if ( v14 >= 0 )
        goto LABEL_31;
      goto LABEL_26;
    }
    v14 = -1073741703;
    LODWORD(v19) = -1073741703;
LABEL_26:
    if ( KeyHandle )
    {
      if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        ORCloseKey((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL);
      else
        ZwClose(KeyHandle);
    }
LABEL_31:
    if ( KeySecurityDescriptor )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, KeySecurityDescriptor);
    if ( v14 != -1073741443 )
      break;
    __debugbreak();
    if ( v22 >= 5 )
      break;
    ++v22;
    v6 = a4;
    v8 = a2;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800699f4  mov     r11, rsp
0x1800699f7  mov     [r11+20h], r9d
0x1800699fb  mov     [r11+10h], rdx
0x1800699ff  push    rsi
0x180069a00  push    rdi
0x180069a01  push    r12
0x180069a03  push    r13
0x180069a05  push    r14
0x180069a07  push    r15
0x180069a09  sub     rsp, 0B8h
0x180069a10  mov     r14d, r9d
0x180069a13  mov     esi, r8d
0x180069a16  mov     rax, rdx
0x180069a19  mov     r12, rcx
0x180069a1c  mov     [rsp+0E8h+var_A0], 0
0x180069a24  mov     [rsp+0E8h+var_88], 0
0x180069a2d  xorps   xmm0, xmm0
0x180069a30  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x180069a35  xor     ecx, ecx
0x180069a37  movups  xmmword ptr [rsp+0E8h+ObjectAttributes.Length], xmm0
0x180069a3c  movups  xmmword ptr [r11-60h], xmm0
0x180069a41  movups  xmmword ptr [r11-54h], xmm0
0x180069a46  mov     [rsp+0E8h+var_90], ecx
0x180069a4a  mov     [rsp+0E8h+KeyHandle], 0
0x180069a53  mov     rdx, rax; SourceString
0x180069a56  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x180069a5b  call    cs:__imp_RtlInitUnicodeString
0x180069a62  nop     dword ptr [rax+rax+00h]
0x180069a67  and     r12, 0FFFFFFFFFFFFFFFDh
0x180069a6b  mov     [rsp+0E8h+arg_0], r12
0x180069a73  bts     esi, 12h
0x180069a77  mov     [rsp+0E8h+arg_10], esi
0x180069a7e  mov     edi, 40h ; '@'
0x180069a83  mov     r15d, esi
0x180069a86  xor     r13b, r13b
0x180069a89  test    r14b, 1
0x180069a8d  jz      short loc_180069AA8
0x180069a8f  mov     edi, 0C0h
0x180069a94  mov     eax, esi
0x180069a96  and     eax, 60019h
0x180069a9b  cmp     eax, esi
0x180069a9d  jz      short loc_180069AA8
0x180069a9f  mov     r15d, 40000h
0x180069aa5  mov     r13b, 1
0x180069aa8  mov     ecx, 0F003Fh; AccessMask
0x180069aad  call    BiCreateKeySecurityDescriptor
0x180069ab2  mov     r14, rax
0x180069ab5  test    rax, rax
0x180069ab8  jnz     short loc_180069AC8
0x180069aba  mov     edi, 0C0000079h
0x180069abf  mov     dword ptr [rsp+0E8h+var_A8], edi
0x180069ac3  jmp     loc_180069C5D
0x180069ac8  mov     eax, [rsp+0E8h+arg_18]
0x180069acf  shr     eax, 1
0x180069ad1  and     eax, 1
0x180069ad4  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x180069adc  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], r12
0x180069ae4  mov     [rsp+0E8h+ObjectAttributes.Attributes], edi
0x180069aeb  lea     rcx, [rsp+0E8h+DestinationString]
0x180069af0  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rcx
0x180069af8  mov     [rsp+0E8h+ObjectAttributes.SecurityDescriptor], r14
0x180069b00  mov     [rsp+0E8h+ObjectAttributes.SecurityQualityOfService], 0
0x180069b0c  mov     [rsp+0E8h+var_A8], 0
0x180069b15  test    r12b, 1
0x180069b19  jz      short loc_180069B68
0x180069b1b  mov     rcx, r12
0x180069b1e  and     rcx, 0FFFFFFFFFFFFFFFEh; int
0x180069b22  lea     rdx, [rsp+0E8h+var_A0]
0x180069b27  mov     [rsp+0E8h+Disposition], rdx; __int64
0x180069b2c  lea     rdx, [rsp+0E8h+var_A8]
0x180069b31  mov     qword ptr [rsp+0E8h+CreateOptions], rdx; __int64
0x180069b36  mov     [rsp+0E8h+Class], r14; pSecurityDescriptor
0x180069b3b  mov     r9d, eax; int
0x180069b3e  xor     r8d, r8d; int
0x180069b41  mov     rdx, [rsp+0E8h+DestinationString.Buffer]; int
0x180069b46  call    ORCreateKey
0x180069b4b  mov     ecx, eax
0x180069b4d  call    BiDosErrorToNtStatus
0x180069b52  mov     edi, eax
0x180069b54  test    eax, eax
0x180069b56  js      short loc_180069B9D
0x180069b58  mov     rax, [rsp+0E8h+var_A8]
0x180069b5d  or      rax, 1
0x180069b61  mov     [rsp+0E8h+KeyHandle], rax
0x180069b66  jmp     short loc_180069B9D
0x180069b68  lea     rcx, [rsp+0E8h+var_A0]
0x180069b6d  mov     [rsp+0E8h+Disposition], rcx; Disposition
0x180069b72  mov     [rsp+0E8h+CreateOptions], eax; CreateOptions
0x180069b76  mov     [rsp+0E8h+Class], 0; Class
0x180069b7f  xor     r9d, r9d; TitleIndex
0x180069b82  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x180069b87  mov     edx, r15d; DesiredAccess
0x180069b8a  lea     rcx, [rsp+0E8h+KeyHandle]; KeyHandle
0x180069b8f  call    cs:__imp_ZwCreateKey
0x180069b96  nop     dword ptr [rax+rax+00h]
0x180069b9b  mov     edi, eax
0x180069b9d  mov     dword ptr [rsp+0E8h+var_A8], edi
0x180069ba1  test    edi, edi
0x180069ba3  js      loc_180069C5D
0x180069ba9  test    r13b, r13b
0x180069bac  jz      loc_180069C32
0x180069bb2  mov     rcx, [rsp+0E8h+KeyHandle]; Handle
0x180069bb7  mov     r8, r14; SecurityDescriptor
0x180069bba  mov     edx, 4; SecurityInformation
0x180069bbf  test    cl, 1
0x180069bc2  jz      short loc_180069BD6
0x180069bc4  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180069bc8  call    ORSetKeySecurity
0x180069bcd  mov     ecx, eax
0x180069bcf  call    BiDosErrorToNtStatus
0x180069bd4  jmp     short loc_180069BE2
0x180069bd6  call    cs:__imp_ZwSetSecurityObject
0x180069bdd  nop     dword ptr [rax+rax+00h]
0x180069be2  mov     edi, eax
0x180069be4  test    eax, eax
0x180069be6  js      loc_180069C77
0x180069bec  lea     r8, [rsp+0E8h+ObjectAttributes]
0x180069bf1  mov     edx, esi
0x180069bf3  lea     rcx, [rsp+0E8h+var_88]; KeyHandle
0x180069bf8  call    BiZwOpenKey
0x180069bfd  mov     edi, eax
0x180069bff  mov     dword ptr [rsp+0E8h+var_A8], eax
0x180069c03  test    eax, eax
0x180069c05  js      short loc_180069C59
0x180069c07  mov     rcx, [rsp+0E8h+KeyHandle]; Handle
0x180069c0c  test    cl, 1
0x180069c0f  jz      short loc_180069C1C
0x180069c11  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180069c15  call    ORCloseKey
0x180069c1a  jmp     short loc_180069C28
0x180069c1c  call    cs:__imp_ZwClose
0x180069c23  nop     dword ptr [rax+rax+00h]
0x180069c28  mov     rax, [rsp+0E8h+var_88]
0x180069c2d  mov     [rsp+0E8h+KeyHandle], rax
0x180069c32  mov     rcx, [rsp+0E8h+arg_28]
0x180069c3a  test    rcx, rcx
0x180069c3d  jz      short loc_180069C49
0x180069c3f  cmp     [rsp+0E8h+var_A0], 1
0x180069c44  setz    al
0x180069c47  mov     [rcx], al
0x180069c49  mov     rcx, [rsp+0E8h+arg_20]
0x180069c51  mov     rax, [rsp+0E8h+KeyHandle]
0x180069c56  mov     [rcx], rax
0x180069c59  test    edi, edi
0x180069c5b  jns     short loc_180069C89
0x180069c5d  mov     rcx, [rsp+0E8h+KeyHandle]; Handle
0x180069c62  test    rcx, rcx
0x180069c65  jz      short loc_180069C89
0x180069c67  test    cl, 1
0x180069c6a  jz      short loc_180069C7D
0x180069c6c  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180069c70  call    ORCloseKey
0x180069c75  jmp     short loc_180069C89
0x180069c77  mov     dword ptr [rsp+0E8h+var_A8], edi
0x180069c7b  jmp     short loc_180069C59
0x180069c7d  call    cs:__imp_ZwClose
0x180069c84  nop     dword ptr [rax+rax+00h]
0x180069c89  test    r14, r14
0x180069c8c  jz      short loc_180069CAC
0x180069c8e  mov     rcx, gs:60h
0x180069c97  mov     r8, r14; P
0x180069c9a  xor     edx, edx; Flags
0x180069c9c  mov     rcx, [rcx+30h]; HeapHandle
0x180069ca0  call    cs:__imp_RtlFreeHeap
0x180069ca7  nop     dword ptr [rax+rax+00h]
0x180069cac  cmp     edi, 0C000017Dh
0x180069cb2  jnz     short loc_180069CF8
0x180069cb4  int     3; Trap to Debugger
0x180069cb5  mov     r14d, [rsp+0E8h+var_90]
0x180069cba  jmp     short loc_180069CD5
0x180069cbc  mov     r14d, 5
0x180069cc2  mov     esi, [rsp+0E8h+arg_10]
0x180069cc9  mov     r12, [rsp+0E8h+arg_0]
0x180069cd1  mov     edi, dword ptr [rsp+0E8h+var_A8]
0x180069cd5  cmp     r14d, 5
0x180069cd9  jnb     short loc_180069CF8
0x180069cdb  inc     r14d
0x180069cde  mov     [rsp+0E8h+var_90], r14d
0x180069ce3  mov     r14d, [rsp+0E8h+arg_18]
0x180069ceb  mov     rax, [rsp+0E8h+arg_8]
0x180069cf3  jmp     loc_180069A4A
0x180069cf8  mov     eax, edi
0x180069cfa  add     rsp, 0B8h
0x180069d01  pop     r15
0x180069d03  pop     r14
0x180069d05  pop     r13
0x180069d07  pop     r12
0x180069d09  pop     rdi
0x180069d0a  pop     rsi
0x180069d0b  retn
```
