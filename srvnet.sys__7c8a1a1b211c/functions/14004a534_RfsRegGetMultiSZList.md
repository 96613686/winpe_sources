# RfsRegGetMultiSZList

- ea: `0x14004a534`
- end: `0x14004a861`
- name: `RfsRegGetMultiSZList`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004a490`

## callees

- `0x14002a540`
- `0x14004a534`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004a643`
- `ntoskrnl!ExAllocatePool2` at `0x14004a748`
- `ntoskrnl!ExAllocatePool2` at `0x14004a643`
- `ntoskrnl!ExAllocatePool2` at `0x14004a748`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a585`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a598`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a585`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a598`
- `ntoskrnl!ZwQueryValueKey` at `0x14004a60b`
- `ntoskrnl!ZwQueryValueKey` at `0x14004a67c`
- `ntoskrnl!ZwQueryValueKey` at `0x14004a60b`
- `ntoskrnl!ZwQueryValueKey` at `0x14004a67c`
- `ntoskrnl!ZwOpenKey` at `0x14004a5d5`
- `ntoskrnl!ZwOpenKey` at `0x14004a5d5`
- `ntoskrnl!ZwClose` at `0x14004a624`
- `ntoskrnl!ZwClose` at `0x14004a68e`
- `ntoskrnl!ZwClose` at `0x14004a624`
- `ntoskrnl!ZwClose` at `0x14004a68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a789`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a832`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a789`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a832`

## pseudocode

```c
__int64 __fastcall RfsRegGetMultiSZList(__int64 *a1, const WCHAR *a2, const WCHAR *a3, unsigned __int64 a4, char a5)
{
  unsigned __int64 *v5; // rdi
  __int64 v6; // r14
  NTSTATUS v9; // ebx
  void *v10; // rcx
  unsigned int *Pool2; // rax
  unsigned int *v12; // rsi
  ULONG v13; // edx
  ULONG v14; // eax
  _WORD *v15; // rcx
  unsigned int v16; // r15d
  unsigned int v17; // edi
  ULONG v18; // ecx
  _WORD *v19; // rdi
  __int64 v20; // r10
  _QWORD *v21; // rdx
  unsigned int i; // r8d
  __int64 v23; // rax
  ULONG v24; // ecx
  ULONG v25; // eax
  unsigned int v26; // r8d
  ULONG ResultLength; // [rsp+30h] [rbp-61h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-59h] BYREF
  void *Src; // [rsp+40h] [rbp-51h]
  __int64 v31; // [rsp+48h] [rbp-49h]
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-1h] BYREF

  v5 = (unsigned __int64 *)a1;
  LODWORD(v6) = 0;
  KeyHandle = 0;
  ValueName = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&ValueName, a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( v9 < 0 )
    goto LABEL_43;
  v9 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v9 != -1073741789 )
  {
    v10 = KeyHandle;
LABEL_4:
    ZwClose(v10);
LABEL_43:
    *v5 = a4 & -(__int64)(a5 != 0);
    return (unsigned int)v9;
  }
  Pool2 = (unsigned int *)ExAllocatePool2(258, ResultLength, 1383294546);
  v10 = KeyHandle;
  v12 = Pool2;
  if ( !Pool2 )
  {
    v9 = -1073741670;
    goto LABEL_4;
  }
  v9 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
  ZwClose(KeyHandle);
  if ( v9 < 0 )
    goto LABEL_42;
  v13 = v12[3];
  ResultLength = v13;
  if ( v13 < 2 )
    goto LABEL_42;
  v14 = 0;
  v15 = (_WORD *)((char *)v12 + v12[2]);
  v16 = 0;
  Src = v15;
  do
  {
    v14 += 2;
    if ( *v15 )
    {
      ++v16;
      ++v15;
      if ( v14 >= v13 )
        break;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        v14 += 2;
      }
      while ( v14 < v13 );
    }
    else
    {
      ++v15;
    }
  }
  while ( v14 < v13 );
  if ( !v16 )
  {
LABEL_42:
    ExFreePoolWithTag(v12, 0x52736652u);
    goto LABEL_43;
  }
  if ( a5 && a4 && *(_QWORD *)a4 )
  {
    do
      v6 = (unsigned int)(v6 + 1);
    while ( *(_QWORD *)(a4 + 8 * v6) );
  }
  v17 = v6 + v16;
  if ( (unsigned int)v6 + v16 > 0x1000 || v17 < v16 || (v18 = v13 + 8 * v17, v18 + 8 < v13) )
  {
    v9 = -1073741675;
    goto LABEL_41;
  }
  v31 = ExAllocatePool2(256, v18 + 10, 1383294546);
  if ( !v31 )
  {
    v9 = -1073741670;
LABEL_41:
    v5 = (unsigned __int64 *)a1;
    goto LABEL_42;
  }
  v19 = (_WORD *)(v31 + 8LL * (v17 + 1));
  memmove(v19, Src, ResultLength);
  ExFreePoolWithTag(v12, 0x52736652u);
  v20 = v31;
  v21 = (_QWORD *)v31;
  *(_WORD *)((char *)v19 + ResultLength) = 0;
  if ( a5 )
  {
    for ( i = 0; i < (unsigned int)v6; ++v21 )
    {
      v23 = i++;
      *v21 = *(_QWORD *)(a4 + 8 * v23);
    }
  }
  v24 = ResultLength;
  v25 = 0;
  v26 = 0;
  while ( v25 < v24 )
  {
    if ( v26 >= v16 )
      break;
    v25 += 2;
    if ( *v19 )
    {
      *v21 = v19;
      ++v26;
      v24 = ResultLength;
      ++v21;
      ++v19;
      if ( v25 >= ResultLength )
        break;
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        v25 += 2;
      }
      while ( v25 < ResultLength );
    }
    else
    {
      ++v19;
    }
  }
  *v21 = 0;
  *a1 = v20;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004a534  mov     [rsp-8+arg_0], rcx
0x14004a539  push    rbp
0x14004a53a  push    rbx
0x14004a53b  push    rsi
0x14004a53c  push    rdi
0x14004a53d  push    r12
0x14004a53f  push    r13
0x14004a541  push    r14
0x14004a543  push    r15
0x14004a545  lea     rbp, [rsp-17h]
0x14004a54a  sub     rsp, 0A8h
0x14004a551  xorps   xmm0, xmm0
0x14004a554  mov     rdi, rcx
0x14004a557  xorps   xmm1, xmm1
0x14004a55a  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14004a55e  xor     r14d, r14d
0x14004a561  xor     eax, eax
0x14004a563  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14004a567  mov     r12, r9
0x14004a56a  mov     rbx, r8
0x14004a56d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14004a571  mov     [rbp+4Fh+KeyHandle], r14
0x14004a575  movups  xmmword ptr [rbp+4Fh+ValueName.Length], xmm0
0x14004a579  mov     [rbp+4Fh+var_B0], r14d
0x14004a57d  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x14004a581  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14004a585  call    cs:__imp_RtlInitUnicodeString
0x14004a58c  nop     dword ptr [rax+rax+00h]
0x14004a591  mov     rdx, rbx; SourceString
0x14004a594  lea     rcx, [rbp+4Fh+ValueName]; DestinationString
0x14004a598  call    cs:__imp_RtlInitUnicodeString
0x14004a59f  nop     dword ptr [rax+rax+00h]
0x14004a5a4  lea     rax, [rbp+4Fh+DestinationString]
0x14004a5a8  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14004a5af  xorps   xmm0, xmm0
0x14004a5b2  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14004a5b6  lea     r15d, [r14+1]
0x14004a5ba  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r14
0x14004a5be  mov     edx, r15d; DesiredAccess
0x14004a5c1  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x14004a5c8  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14004a5cc  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14004a5d0  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14004a5d5  call    cs:__imp_ZwOpenKey
0x14004a5dc  nop     dword ptr [rax+rax+00h]
0x14004a5e1  mov     r13b, [rbp+4Fh+arg_20]
0x14004a5e5  mov     ebx, eax
0x14004a5e7  test    eax, eax
0x14004a5e9  js      loc_14004A83E
0x14004a5ef  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14004a5f3  lea     rax, [rbp+4Fh+var_B0]
0x14004a5f7  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14004a5fc  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x14004a600  xor     r9d, r9d; KeyValueInformation
0x14004a603  mov     [rsp+0E0h+Length], r14d; Length
0x14004a608  mov     r8d, r15d; KeyValueInformationClass
0x14004a60b  call    cs:__imp_ZwQueryValueKey
0x14004a612  nop     dword ptr [rax+rax+00h]
0x14004a617  mov     ebx, eax
0x14004a619  cmp     eax, 0C0000023h
0x14004a61e  jz      short loc_14004A635
0x14004a620  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x14004a624  call    cs:__imp_ZwClose
0x14004a62b  nop     dword ptr [rax+rax+00h]
0x14004a630  jmp     loc_14004A83E
0x14004a635  mov     edx, [rbp+4Fh+var_B0]
0x14004a638  mov     ecx, 102h
0x14004a63d  mov     r8d, 52736652h
0x14004a643  call    cs:__imp_ExAllocatePool2
0x14004a64a  nop     dword ptr [rax+rax+00h]
0x14004a64f  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14004a653  mov     rsi, rax
0x14004a656  test    rax, rax
0x14004a659  jnz     short loc_14004A662
0x14004a65b  mov     ebx, 0C000009Ah
0x14004a660  jmp     short loc_14004A624
0x14004a662  lea     rax, [rbp+4Fh+var_B0]
0x14004a666  mov     r9, rsi; KeyValueInformation
0x14004a669  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14004a66e  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x14004a672  mov     eax, [rbp+4Fh+var_B0]
0x14004a675  mov     r8d, r15d; KeyValueInformationClass
0x14004a678  mov     [rsp+0E0h+Length], eax; Length
0x14004a67c  call    cs:__imp_ZwQueryValueKey
0x14004a683  nop     dword ptr [rax+rax+00h]
0x14004a688  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x14004a68c  mov     ebx, eax
0x14004a68e  call    cs:__imp_ZwClose
0x14004a695  nop     dword ptr [rax+rax+00h]
0x14004a69a  test    ebx, ebx
0x14004a69c  js      loc_14004A82A
0x14004a6a2  mov     edx, [rsi+0Ch]
0x14004a6a5  mov     [rbp+4Fh+var_B0], edx
0x14004a6a8  cmp     edx, 2
0x14004a6ab  jb      loc_14004A82A
0x14004a6b1  mov     ecx, [rsi+8]
0x14004a6b4  mov     eax, r14d
0x14004a6b7  add     rcx, rsi
0x14004a6ba  mov     r15d, r14d
0x14004a6bd  mov     [rbp+4Fh+Src], rcx
0x14004a6c1  add     eax, 2
0x14004a6c4  cmp     [rcx], r14w
0x14004a6c8  jz      short loc_14004A6E8
0x14004a6ca  inc     r15d
0x14004a6cd  add     rcx, 2
0x14004a6d1  cmp     eax, edx
0x14004a6d3  jnb     short loc_14004A6F0
0x14004a6d5  cmp     [rcx], r14w
0x14004a6d9  jz      short loc_14004A6EC
0x14004a6db  add     rcx, 2
0x14004a6df  add     eax, 2
0x14004a6e2  cmp     eax, edx
0x14004a6e4  jb      short loc_14004A6D5
0x14004a6e6  jmp     short loc_14004A6EC
0x14004a6e8  add     rcx, 2
0x14004a6ec  cmp     eax, edx
0x14004a6ee  jb      short loc_14004A6C1
0x14004a6f0  test    r15d, r15d
0x14004a6f3  jz      loc_14004A82A
0x14004a6f9  test    r13b, r13b
0x14004a6fc  jz      short loc_14004A713
0x14004a6fe  test    r12, r12
0x14004a701  jz      short loc_14004A713
0x14004a703  cmp     [r12], r14
0x14004a707  jz      short loc_14004A713
0x14004a709  inc     r14d
0x14004a70c  cmp     qword ptr [r12+r14*8], 0
0x14004a711  jnz     short loc_14004A709
0x14004a713  lea     edi, [r14+r15]
0x14004a717  cmp     edi, 1000h
0x14004a71d  ja      loc_14004A821
0x14004a723  cmp     edi, r15d
0x14004a726  jb      loc_14004A821
0x14004a72c  lea     ecx, [rdx+rdi*8]
0x14004a72f  lea     eax, [rcx+8]
0x14004a732  cmp     eax, edx
0x14004a734  jb      loc_14004A821
0x14004a73a  lea     edx, [rcx+0Ah]
0x14004a73d  mov     r8d, 52736652h
0x14004a743  mov     ecx, 100h
0x14004a748  call    cs:__imp_ExAllocatePool2
0x14004a74f  nop     dword ptr [rax+rax+00h]
0x14004a754  mov     [rbp+4Fh+var_98], rax
0x14004a758  mov     rdx, rax
0x14004a75b  test    rax, rax
0x14004a75e  jnz     short loc_14004A76A
0x14004a760  mov     ebx, 0C000009Ah
0x14004a765  jmp     loc_14004A826
0x14004a76a  mov     r8d, [rbp+4Fh+var_B0]; Size
0x14004a76e  lea     eax, [rdi+1]
0x14004a771  lea     rdi, [rdx+rax*8]
0x14004a775  mov     rdx, [rbp+4Fh+Src]; Src
0x14004a779  mov     rcx, rdi; void *
0x14004a77c  call    memmove
0x14004a781  mov     edx, 52736652h; Tag
0x14004a786  mov     rcx, rsi; P
0x14004a789  call    cs:__imp_ExFreePoolWithTag
0x14004a790  nop     dword ptr [rax+rax+00h]
0x14004a795  mov     ecx, [rbp+4Fh+var_B0]
0x14004a798  xor     r11d, r11d
0x14004a79b  mov     r10, [rbp+4Fh+var_98]
0x14004a79f  mov     rdx, r10
0x14004a7a2  mov     [rcx+rdi], r11w
0x14004a7a7  test    r13b, r13b
0x14004a7aa  jz      short loc_14004A7CA
0x14004a7ac  mov     r8d, r11d
0x14004a7af  test    r14d, r14d
0x14004a7b2  jz      short loc_14004A7CA
0x14004a7b4  mov     eax, r8d
0x14004a7b7  inc     r8d
0x14004a7ba  mov     rcx, [r12+rax*8]
0x14004a7be  mov     [rdx], rcx
0x14004a7c1  add     rdx, 8
0x14004a7c5  cmp     r8d, r14d
0x14004a7c8  jb      short loc_14004A7B4
0x14004a7ca  mov     ecx, [rbp+4Fh+var_B0]
0x14004a7cd  mov     eax, r11d
0x14004a7d0  mov     r8d, r11d
0x14004a7d3  test    ecx, ecx
0x14004a7d5  jz      short loc_14004A815
0x14004a7d7  cmp     r8d, r15d
0x14004a7da  jnb     short loc_14004A815
0x14004a7dc  add     eax, 2
0x14004a7df  cmp     [rdi], r11w
0x14004a7e3  jz      short loc_14004A80D
0x14004a7e5  mov     [rdx], rdi
0x14004a7e8  inc     r8d
0x14004a7eb  mov     ecx, [rbp+4Fh+var_B0]
0x14004a7ee  add     rdx, 8
0x14004a7f2  add     rdi, 2
0x14004a7f6  cmp     eax, ecx
0x14004a7f8  jnb     short loc_14004A815
0x14004a7fa  cmp     [rdi], r11w
0x14004a7fe  jz      short loc_14004A811
0x14004a800  add     rdi, 2
0x14004a804  add     eax, 2
0x14004a807  cmp     eax, ecx
0x14004a809  jb      short loc_14004A7FA
0x14004a80b  jmp     short loc_14004A811
0x14004a80d  add     rdi, 2
0x14004a811  cmp     eax, ecx
0x14004a813  jb      short loc_14004A7D7
0x14004a815  mov     rax, [rbp+4Fh+arg_0]
0x14004a819  mov     [rdx], r11
0x14004a81c  mov     [rax], r10
0x14004a81f  jmp     short loc_14004A84A
0x14004a821  mov     ebx, 0C0000095h
0x14004a826  mov     rdi, [rbp+4Fh+arg_0]
0x14004a82a  mov     edx, 52736652h; Tag
0x14004a82f  mov     rcx, rsi; P
0x14004a832  call    cs:__imp_ExFreePoolWithTag
0x14004a839  nop     dword ptr [rax+rax+00h]
0x14004a83e  neg     r13b
0x14004a841  sbb     rax, rax
0x14004a844  and     rax, r12
0x14004a847  mov     [rdi], rax
0x14004a84a  mov     eax, ebx
0x14004a84c  add     rsp, 0A8h
0x14004a853  pop     r15
0x14004a855  pop     r14
0x14004a857  pop     r13
0x14004a859  pop     r12
0x14004a85b  pop     rdi
0x14004a85c  pop     rsi
0x14004a85d  pop     rbx
0x14004a85e  pop     rbp
0x14004a85f  retn
```
