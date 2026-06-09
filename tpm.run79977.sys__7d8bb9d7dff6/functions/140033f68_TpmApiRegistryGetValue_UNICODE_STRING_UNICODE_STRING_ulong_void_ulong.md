# TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)

- ea: `0x140033f68`
- end: `0x1400340e4`
- name: `?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z`
- size: `380`
- prototype: `int(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140033ce4`
- `0x140033e18`

## callees

- `0x140032c60`
- `0x140032c88`
- `0x140033f68`
- `0x140039840`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140033fc9`
- `ntoskrnl!ZwOpenKey` at `0x140033fc9`
- `ntoskrnl!ZwQueryValueKey` at `0x140033ffe`
- `ntoskrnl!ZwQueryValueKey` at `0x140034063`
- `ntoskrnl!ZwQueryValueKey` at `0x140033ffe`
- `ntoskrnl!ZwQueryValueKey` at `0x140034063`
- `ntoskrnl!NtClose` at `0x1400340c8`
- `ntoskrnl!NtClose` at `0x1400340c8`

## pseudocode

```c
__int64 __fastcall TpmApiRegistryGetValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  _DWORD *v9; // rdi
  unsigned int v10; // eax
  PVOID KeyValueInformation; // [rsp+30h] [rbp-48h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+38h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ResultLength = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      TpmApiCallbackAlloc(0, ResultLength, &KeyValueInformation);
      if ( KeyValueInformation )
      {
        v9 = KeyValueInformation;
        v8 = ZwQueryValueKey(
               KeyHandle,
               a2,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v9[1] == a3 )
          {
            if ( a4 && (v10 = v9[2], *a5 >= v10) )
            {
              *a5 = v10;
              memmove(a4, v9 + 3, v10);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v9[2];
            }
          }
          else
          {
            v8 = -1073741438;
          }
        }
      }
      else
      {
        v8 = -1073741801;
      }
    }
  }
  TpmApiCallbackFree(0, ResultLength, KeyValueInformation);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140033f68  push    rbp
0x140033f6a  push    rbx
0x140033f6b  push    rsi
0x140033f6c  push    rdi
0x140033f6d  push    r14
0x140033f6f  push    r15
0x140033f71  mov     rbp, rsp
0x140033f74  sub     rsp, 78h
0x140033f78  mov     r14d, r8d
0x140033f7b  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140033f7f  mov     r15, rdx
0x140033f82  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140033f8a  xorps   xmm0, xmm0
0x140033f8d  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140033f95  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140033f99  mov     [rbp+arg_0], 0
0x140033fa0  mov     edx, 20019h; DesiredAccess
0x140033fa5  mov     [rbp+KeyHandle], 0
0x140033fad  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140033fb1  mov     [rbp+KeyValueInformation], 0
0x140033fb9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140033fbe  mov     rsi, r9
0x140033fc1  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140033fc9  call    cs:__imp_ZwOpenKey
0x140033fd0  nop     dword ptr [rax+rax+00h]
0x140033fd5  mov     ebx, eax
0x140033fd7  test    eax, eax
0x140033fd9  js      loc_1400340B1
0x140033fdf  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140033fe3  lea     rax, [rbp+arg_0]
0x140033fe7  xor     r9d, r9d; KeyValueInformation
0x140033fea  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140033fef  mov     rdx, r15; ValueName
0x140033ff2  mov     [rsp+78h+Length], 0; Length
0x140033ffa  lea     r8d, [r9+2]; KeyValueInformationClass
0x140033ffe  call    cs:__imp_ZwQueryValueKey
0x140034005  nop     dword ptr [rax+rax+00h]
0x14003400a  mov     ecx, 80000000h
0x14003400f  mov     ebx, eax
0x140034011  add     eax, ecx
0x140034013  test    ecx, eax
0x140034015  jnz     short loc_140034023
0x140034017  cmp     ebx, 0C0000023h
0x14003401d  jnz     loc_1400340B1
0x140034023  mov     edx, [rbp+arg_0]
0x140034026  lea     r8, [rbp+KeyValueInformation]
0x14003402a  xor     ecx, ecx
0x14003402c  call    TpmApiCallbackAlloc
0x140034031  cmp     [rbp+KeyValueInformation], 0
0x140034036  jnz     short loc_14003403F
0x140034038  mov     ebx, 0C0000017h
0x14003403d  jmp     short loc_1400340B1
0x14003403f  mov     rdi, [rbp+KeyValueInformation]
0x140034043  lea     rax, [rbp+arg_0]
0x140034047  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14003404b  mov     r9, rdi; KeyValueInformation
0x14003404e  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140034053  mov     r8d, 2; KeyValueInformationClass
0x140034059  mov     eax, [rbp+arg_0]
0x14003405c  mov     rdx, r15; ValueName
0x14003405f  mov     [rsp+78h+Length], eax; Length
0x140034063  call    cs:__imp_ZwQueryValueKey
0x14003406a  nop     dword ptr [rax+rax+00h]
0x14003406f  mov     ebx, eax
0x140034071  test    eax, eax
0x140034073  js      short loc_1400340B1
0x140034075  cmp     [rdi+4], r14d
0x140034079  jz      short loc_140034082
0x14003407b  mov     ebx, 0C0000182h
0x140034080  jmp     short loc_1400340B1
0x140034082  mov     rcx, [rbp+arg_20]
0x140034086  test    rsi, rsi
0x140034089  jz      short loc_1400340A7
0x14003408b  mov     eax, [rdi+8]
0x14003408e  cmp     [rcx], eax
0x140034090  jb      short loc_1400340A7
0x140034092  mov     [rcx], eax
0x140034094  lea     rdx, [rdi+0Ch]; Src
0x140034098  mov     rcx, rsi; void *
0x14003409b  mov     r8d, eax; Size
0x14003409e  call    memmove
0x1400340a3  xor     ebx, ebx
0x1400340a5  jmp     short loc_1400340B1
0x1400340a7  mov     eax, [rdi+8]
0x1400340aa  mov     ebx, 0C0000023h
0x1400340af  mov     [rcx], eax
0x1400340b1  mov     r8, [rbp+KeyValueInformation]
0x1400340b5  xor     ecx, ecx
0x1400340b7  mov     edx, [rbp+arg_0]
0x1400340ba  call    TpmApiCallbackFree
0x1400340bf  mov     rcx, [rbp+KeyHandle]; Handle
0x1400340c3  test    rcx, rcx
0x1400340c6  jz      short loc_1400340D4
0x1400340c8  call    cs:__imp_NtClose
0x1400340cf  nop     dword ptr [rax+rax+00h]
0x1400340d4  mov     eax, ebx
0x1400340d6  add     rsp, 78h
0x1400340da  pop     r15
0x1400340dc  pop     r14
0x1400340de  pop     rdi
0x1400340df  pop     rsi
0x1400340e0  pop     rbx
0x1400340e1  pop     rbp
0x1400340e2  retn
```
