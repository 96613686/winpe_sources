# TpmRegistry::DeleteKey(_UNICODE_STRING *,int)

- ea: `0x14002fe48`
- end: `0x140030054`
- name: `?DeleteKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@H@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002f0b0`
- `0x14002fe48`
- `0x14003005c`

## callees

- `0x14001a37c`
- `0x14002fe48`
- `0x140039840`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14002feaa`
- `ntoskrnl!ZwOpenKey` at `0x14002feaa`
- `ntoskrnl!ZwEnumerateKey` at `0x14002fee5`
- `ntoskrnl!ZwEnumerateKey` at `0x14002ff43`
- `ntoskrnl!ZwEnumerateKey` at `0x14002fee5`
- `ntoskrnl!ZwEnumerateKey` at `0x14002ff43`
- `ntoskrnl!ZwDeleteKey` at `0x140030003`
- `ntoskrnl!ZwDeleteKey` at `0x140030003`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002ffcf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002ffcf`

## pseudocode

```c
__int64 __fastcall TpmRegistry::DeleteKey(struct _UNICODE_STRING *a1, int a2)
{
  unsigned int *v3; // rdi
  NTSTATUS v5; // ebx
  NTSTATUS v6; // eax
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rax
  const WCHAR *v9; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 retaddr; // [rsp+88h] [rbp+18h]
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+28h] BYREF

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  v3 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, a2 != 0 ? 65544 : 0x10000, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    if ( !a2 )
      goto LABEL_13;
    do
    {
      v6 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, 0, 0, &ResultLength);
      if ( v6 != -1073741789 )
        break;
      if ( v3 )
        TpmFree(v3);
      v7 = TpmAlloc(1, ResultLength + 2LL, retaddr);
      v3 = (unsigned int *)v7;
      if ( !v7 )
        goto LABEL_19;
      v5 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, v7, ResultLength, &ResultLength);
      if ( v5 < 0 )
        goto LABEL_14;
      ResultLength += 2;
      *((_WORD *)v3 + ((unsigned __int64)v3[3] >> 1) + 8) = 0;
      v8 = TpmAlloc(1, a1->Length + 4LL + v3[3], retaddr);
      v9 = (const WCHAR *)v8;
      if ( !v8 )
      {
LABEL_19:
        v5 = -1073741670;
        goto LABEL_14;
      }
      memmove(v8, a1->Buffer, a1->Length);
      v9[(unsigned __int64)a1->Length >> 1] = 92;
      memmove((char *)v9 + a1->Length + 2, v3 + 4, v3[3] + 2LL);
      RtlInitUnicodeString(&DestinationString, v9);
      v6 = TpmRegistry::DeleteKey(&DestinationString, 1);
    }
    while ( !v6 );
    v5 = 0;
    if ( v6 != -2147483622 )
      v5 = v6;
    if ( v5 >= 0 )
LABEL_13:
      v5 = ZwDeleteKey(KeyHandle);
  }
LABEL_14:
  if ( DestinationString.Buffer )
    TpmFree(DestinationString.Buffer);
  if ( v3 )
    TpmFree(v3);
  TpmRegistry::CloseKey(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002fe48  mov     [rsp-18h+arg_10], rbx
0x14002fe4d  mov     [rsp-18h+arg_18], rsi
0x14002fe52  push    rbp
0x14002fe53  push    rdi
0x14002fe54  push    r14
0x14002fe56  mov     rbp, rsp
0x14002fe59  sub     rsp, 70h
0x14002fe5d  mov     eax, edx
0x14002fe5f  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x14002fe63  mov     esi, edx
0x14002fe65  mov     [rbp+KeyHandle], 0
0x14002fe6d  xor     edi, edi
0x14002fe6f  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002fe77  xorps   xmm0, xmm0
0x14002fe7a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14002fe82  neg     eax
0x14002fe84  mov     [rbp+arg_8], edi
0x14002fe87  mov     r14, rcx
0x14002fe8a  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x14002fe8e  sbb     edx, edx
0x14002fe90  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002fe94  and     edx, 8
0x14002fe97  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14002fe9b  add     edx, 10000h; DesiredAccess
0x14002fea1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002fea5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002feaa  call    cs:__imp_ZwOpenKey
0x14002feb1  nop     dword ptr [rax+rax+00h]
0x14002feb6  mov     ebx, eax
0x14002feb8  test    eax, eax
0x14002feba  js      loc_140030011
0x14002fec0  test    esi, esi
0x14002fec2  jz      loc_14002FFFF
0x14002fec8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002fecc  lea     rax, [rbp+arg_8]
0x14002fed0  mov     [rsp+70h+ResultLength], rax; ResultLength
0x14002fed5  xor     r9d, r9d; KeyInformation
0x14002fed8  xor     r8d, r8d; KeyInformationClass
0x14002fedb  mov     [rsp+70h+Length], 0; Length
0x14002fee3  xor     edx, edx; Index
0x14002fee5  call    cs:__imp_ZwEnumerateKey
0x14002feec  nop     dword ptr [rax+rax+00h]
0x14002fef1  cmp     eax, 0C0000023h
0x14002fef6  jnz     loc_14002FFF1
0x14002fefc  test    rdi, rdi
0x14002feff  jz      short loc_14002FF09
0x14002ff01  mov     rcx, rdi; void *
0x14002ff04  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002ff09  mov     edx, [rbp+arg_8]
0x14002ff0c  mov     cl, 1; bool
0x14002ff0e  mov     r8, [rbp+18h]; unsigned __int64
0x14002ff12  add     rdx, 2; unsigned __int64
0x14002ff16  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002ff1b  mov     rdi, rax
0x14002ff1e  test    rax, rax
0x14002ff21  jz      loc_14003004D
0x14002ff27  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002ff2b  lea     rax, [rbp+arg_8]
0x14002ff2f  mov     [rsp+70h+ResultLength], rax; ResultLength
0x14002ff34  mov     r9, rdi; KeyInformation
0x14002ff37  mov     eax, [rbp+arg_8]
0x14002ff3a  xor     r8d, r8d; KeyInformationClass
0x14002ff3d  xor     edx, edx; Index
0x14002ff3f  mov     [rsp+70h+Length], eax; Length
0x14002ff43  call    cs:__imp_ZwEnumerateKey
0x14002ff4a  nop     dword ptr [rax+rax+00h]
0x14002ff4f  mov     ebx, eax
0x14002ff51  test    eax, eax
0x14002ff53  js      loc_140030011
0x14002ff59  add     [rbp+arg_8], 2
0x14002ff5d  xor     eax, eax
0x14002ff5f  mov     ecx, [rdi+0Ch]
0x14002ff62  mov     r8, [rbp+18h]; unsigned __int64
0x14002ff66  shr     rcx, 1
0x14002ff69  mov     [rdi+rcx*2+10h], ax
0x14002ff6e  movzx   ecx, word ptr [r14]
0x14002ff72  mov     edx, [rdi+0Ch]
0x14002ff75  add     rcx, 4
0x14002ff79  add     rdx, rcx; unsigned __int64
0x14002ff7c  mov     cl, 1; bool
0x14002ff7e  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002ff83  mov     rbx, rax
0x14002ff86  test    rax, rax
0x14002ff89  jz      loc_14003004D
0x14002ff8f  movzx   r8d, word ptr [r14]; Size
0x14002ff93  mov     rcx, rax; void *
0x14002ff96  mov     rdx, [r14+8]; Src
0x14002ff9a  call    memmove
0x14002ff9f  movzx   ecx, word ptr [r14]
0x14002ffa3  lea     rdx, [rdi+10h]; Src
0x14002ffa7  shr     rcx, 1
0x14002ffaa  mov     word ptr [rbx+rcx*2], 5Ch ; '\'
0x14002ffb0  movzx   ecx, word ptr [r14]
0x14002ffb4  mov     r8d, [rdi+0Ch]
0x14002ffb8  add     rcx, 2
0x14002ffbc  add     rcx, rbx; void *
0x14002ffbf  add     r8, 2; Size
0x14002ffc3  call    memmove
0x14002ffc8  mov     rdx, rbx; SourceString
0x14002ffcb  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002ffcf  call    cs:__imp_RtlInitUnicodeString
0x14002ffd6  nop     dword ptr [rax+rax+00h]
0x14002ffdb  mov     edx, 1; int
0x14002ffe0  lea     rcx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x14002ffe4  call    ?DeleteKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@H@Z; TpmRegistry::DeleteKey(_UNICODE_STRING *,int)
0x14002ffe9  test    eax, eax
0x14002ffeb  jz      loc_14002FEC8
0x14002fff1  xor     ebx, ebx
0x14002fff3  cmp     eax, 8000001Ah
0x14002fff8  cmovnz  ebx, eax
0x14002fffb  test    ebx, ebx
0x14002fffd  js      short loc_140030011
0x14002ffff  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140030003  call    cs:__imp_ZwDeleteKey
0x14003000a  nop     dword ptr [rax+rax+00h]
0x14003000f  mov     ebx, eax
0x140030011  mov     rcx, [rbp+DestinationString.Buffer]; void *
0x140030015  test    rcx, rcx
0x140030018  jz      short loc_14003001F
0x14003001a  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14003001f  test    rdi, rdi
0x140030022  jz      short loc_14003002C
0x140030024  mov     rcx, rdi; void *
0x140030027  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14003002c  mov     rcx, [rbp+KeyHandle]; void *
0x140030030  call    ?CloseKey@TpmRegistry@@CAXPEAX@Z; TpmRegistry::CloseKey(void *)
0x140030035  lea     r11, [rsp+70h+var_s0]
0x14003003a  mov     eax, ebx
0x14003003c  mov     rbx, [r11+30h]
0x140030040  mov     rsi, [r11+38h]
0x140030044  mov     rsp, r11
0x140030047  pop     r14
0x140030049  pop     rdi
0x14003004a  pop     rbp
0x14003004b  retn
0x14003004d  mov     ebx, 0C000009Ah
0x140030052  jmp     short loc_140030011
```
