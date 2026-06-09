# GetNvmeHostUuid

- ea: `0x14009a354`
- end: `0x14009a5fb`
- name: `GetNvmeHostUuid`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14009a084`

## callees

- `0x14009a354`
- `0x14014b400`
- `0x14014bd20`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14009a403`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a461`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a403`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a461`
- `ntoskrnl!ExUuidCreate` at `0x14009a4c9`
- `ntoskrnl!ExUuidCreate` at `0x14009a4c9`
- `ntoskrnl!ZwClose` at `0x14009a512`
- `ntoskrnl!ZwClose` at `0x14009a512`
- `ntoskrnl!ZwOpenKey` at `0x14009a43f`
- `ntoskrnl!ZwOpenKey` at `0x14009a43f`
- `ntoskrnl!ZwQueryValueKey` at `0x14009a492`
- `ntoskrnl!ZwQueryValueKey` at `0x14009a492`
- `ntoskrnl!sprintf_s` at `0x14009a5b4`
- `ntoskrnl!sprintf_s` at `0x14009a5b4`
- `ntoskrnl!ZwSetValueKey` at `0x14009a4f7`
- `ntoskrnl!ZwSetValueKey` at `0x14009a4f7`

## string_xrefs

- `0x14009a3f8`: `\Registry\Machine\System\CurrentControlSet\Control\StorPort\`

## pseudocode

```c
__int64 __fastcall GetNvmeHostUuid(__int64 a1)
{
  NTSTATUS v2; // r14d
  int v3; // eax
  __int128 v4; // xmm1
  void *KeyHandle; // [rsp+70h] [rbp-90h] BYREF
  ULONG ResultLength; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  __int128 Buf2; // [rsp+D0h] [rbp-30h] BYREF
  char DstBuf[16]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v13[2]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+110h] [rbp+10h] BYREF
  int v15; // [rsp+114h] [rbp+14h]
  int v16; // [rsp+118h] [rbp+18h]
  UUID v17; // [rsp+11Ch] [rbp+1Ch]

  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  KeyHandle = 0;
  memset(v13, 0, 21);
  ResultLength = 0;
  v2 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  ValueName = 0;
  Buf2 = 0;
  *(_OWORD *)DstBuf = 0;
  if ( memcmp(&NvmeHostUuid, &Buf2, 0x10u) )
    goto LABEL_13;
  if ( NvmeHostUuidChecked )
    return (unsigned int)-1073741275;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\StorPort\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"NvmeHostUuid");
    v2 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x110u, &ResultLength);
    if ( v2 < 0 )
    {
      v2 = ExUuidCreate(&NvmeHostUuid);
      if ( v2 >= 0 )
        v2 = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, (PVOID)&NvmeHostUuid, 0x10u);
    }
    else if ( v15 == 3 && v16 == 16 )
    {
      NvmeHostUuid = v17;
    }
    else
    {
      v2 = -1073739509;
    }
    NvmeHostUuidChecked = 1;
    ZwClose(KeyHandle);
    if ( v2 >= 0 )
    {
LABEL_13:
      sprintf_s(
        DstBuf,
        0x25u,
        "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
        NvmeHostUuid.Data1,
        NvmeHostUuid.Data2,
        NvmeHostUuid.Data3,
        NvmeHostUuid.Data4[0],
        NvmeHostUuid.Data4[1],
        NvmeHostUuid.Data4[2],
        NvmeHostUuid.Data4[3],
        NvmeHostUuid.Data4[4],
        NvmeHostUuid.Data4[5],
        NvmeHostUuid.Data4[6],
        NvmeHostUuid.Data4[7]);
      v3 = v13[1];
      v4 = v13[0];
      *(_OWORD *)a1 = *(_OWORD *)DstBuf;
      *(_OWORD *)(a1 + 16) = v4;
      *(_DWORD *)(a1 + 32) = v3;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14009a354  push    rbp
0x14009a356  push    rbx
0x14009a357  push    rsi
0x14009a358  push    rdi
0x14009a359  push    r14
0x14009a35b  push    r15
0x14009a35d  lea     rbp, [rsp-138h]
0x14009a365  sub     rsp, 238h
0x14009a36c  mov     rax, cs:__security_cookie
0x14009a373  xor     rax, rsp
0x14009a376  mov     [rbp+160h+var_40], rax
0x14009a37d  xorps   xmm0, xmm0
0x14009a380  lea     rsi, NvmeHostUuid
0x14009a387  xor     eax, eax
0x14009a389  lea     rdx, [rbp+160h+Buf2]; Buf2
0x14009a38d  movups  xmmword ptr [rcx], xmm0
0x14009a390  xor     ebx, ebx
0x14009a392  mov     r15, rcx
0x14009a395  movups  xmmword ptr [rcx+10h], xmm0
0x14009a399  lea     edi, [rax+10h]
0x14009a39c  mov     [rcx+20h], eax
0x14009a39f  xorps   xmm1, xmm1
0x14009a3a2  mov     [rsp+260h+KeyHandle], rbx
0x14009a3a7  movups  xmmword ptr [rbp+160h+ObjectAttributes.ObjectName], xmm0
0x14009a3ab  mov     r8d, edi; Size
0x14009a3ae  mov     rcx, rsi; Buf1
0x14009a3b1  movups  [rbp+160h+var_170], xmm0
0x14009a3b5  mov     [rsp+260h+var_1E8], ebx
0x14009a3b9  mov     r14d, ebx
0x14009a3bc  movups  xmmword ptr [rbp+160h+DestinationString.Length], xmm0
0x14009a3c0  mov     qword ptr [rbp+160h+var_170+0Dh], rax
0x14009a3c4  movups  xmmword ptr [rbp+160h+ObjectAttributes.Length], xmm0
0x14009a3c8  movups  xmmword ptr [rbp+160h+ObjectAttributes+1Ch], xmm0
0x14009a3cc  movups  xmmword ptr [rbp+160h+ValueName.Length], xmm0
0x14009a3d0  movups  [rbp+160h+Buf2], xmm1
0x14009a3d4  movups  xmmword ptr [rbp+160h+DstBuf], xmm0
0x14009a3d8  call    memcmp
0x14009a3dd  test    eax, eax
0x14009a3df  jnz     loc_14009A527
0x14009a3e5  cmp     cs:NvmeHostUuidChecked, bl
0x14009a3eb  jz      short loc_14009A3F8
0x14009a3ed  mov     r14d, 0C0000225h
0x14009a3f3  jmp     loc_14009A5D8
0x14009a3f8  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x14009a3ff  lea     rcx, [rbp+160h+DestinationString]; DestinationString
0x14009a403  call    cs:__imp_RtlInitUnicodeString
0x14009a40a  nop     dword ptr [rax+rax+00h]
0x14009a40f  lea     rax, [rbp+160h+DestinationString]
0x14009a413  mov     [rbp+160h+ObjectAttributes.Length], 30h ; '0'
0x14009a41a  xorps   xmm0, xmm0
0x14009a41d  mov     [rbp+160h+ObjectAttributes.ObjectName], rax
0x14009a421  lea     r8, [rbp+160h+ObjectAttributes]; ObjectAttributes
0x14009a425  mov     [rbp+160h+ObjectAttributes.RootDirectory], rbx
0x14009a429  mov     edx, 2001Fh; DesiredAccess
0x14009a42e  mov     [rbp+160h+ObjectAttributes.Attributes], 240h
0x14009a435  lea     rcx, [rsp+260h+KeyHandle]; KeyHandle
0x14009a43a  movdqu  xmmword ptr [rbp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009a43f  call    cs:__imp_ZwOpenKey
0x14009a446  nop     dword ptr [rax+rax+00h]
0x14009a44b  mov     r14d, eax
0x14009a44e  test    eax, eax
0x14009a450  js      loc_14009A5D8
0x14009a456  lea     rdx, aNvmehostuuid; "NvmeHostUuid"
0x14009a45d  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x14009a461  call    cs:__imp_RtlInitUnicodeString
0x14009a468  nop     dword ptr [rax+rax+00h]
0x14009a46d  mov     rcx, [rsp+260h+KeyHandle]; KeyHandle
0x14009a472  lea     rax, [rsp+260h+var_1E8]
0x14009a477  mov     [rsp+260h+ResultLength], rax; ResultLength
0x14009a47c  lea     r9, [rbp+160h+KeyValueInformation]; KeyValueInformation
0x14009a480  mov     r8d, 2; KeyValueInformationClass
0x14009a486  mov     [rsp+260h+Length], 110h; Length
0x14009a48e  lea     rdx, [rbp+160h+ValueName]; ValueName
0x14009a492  call    cs:__imp_ZwQueryValueKey
0x14009a499  nop     dword ptr [rax+rax+00h]
0x14009a49e  mov     r14d, eax
0x14009a4a1  test    eax, eax
0x14009a4a3  js      short loc_14009A4C6
0x14009a4a5  cmp     [rbp+160h+var_14C], 3
0x14009a4a9  jnz     short loc_14009A4BE
0x14009a4ab  cmp     [rbp+160h+var_148], edi
0x14009a4ae  jnz     short loc_14009A4BE
0x14009a4b0  movups  xmm0, [rbp+160h+var_144]
0x14009a4b4  movdqu  xmmword ptr cs:NvmeHostUuid.Data1, xmm0
0x14009a4bc  jmp     short loc_14009A506
0x14009a4be  mov     r14d, 0C000090Bh
0x14009a4c4  jmp     short loc_14009A506
0x14009a4c6  mov     rcx, rsi; Uuid
0x14009a4c9  call    cs:__imp_ExUuidCreate
0x14009a4d0  nop     dword ptr [rax+rax+00h]
0x14009a4d5  mov     r14d, eax
0x14009a4d8  test    eax, eax
0x14009a4da  js      short loc_14009A506
0x14009a4dc  mov     rcx, [rsp+260h+KeyHandle]; KeyHandle
0x14009a4e1  lea     rdx, [rbp+160h+ValueName]; ValueName
0x14009a4e5  mov     dword ptr [rsp+260h+ResultLength], edi; DataSize
0x14009a4e9  mov     r9d, 3; Type
0x14009a4ef  xor     r8d, r8d; TitleIndex
0x14009a4f2  mov     qword ptr [rsp+260h+Length], rsi; Data
0x14009a4f7  call    cs:__imp_ZwSetValueKey
0x14009a4fe  nop     dword ptr [rax+rax+00h]
0x14009a503  mov     r14d, eax
0x14009a506  mov     rcx, [rsp+260h+KeyHandle]; Handle
0x14009a50b  mov     cs:NvmeHostUuidChecked, 1
0x14009a512  call    cs:__imp_ZwClose
0x14009a519  nop     dword ptr [rax+rax+00h]
0x14009a51e  test    r14d, r14d
0x14009a521  js      loc_14009A5D8
0x14009a527  movzx   ecx, cs:NvmeHostUuid.Data4+6
0x14009a52e  movzx   edx, cs:NvmeHostUuid.Data4+5
0x14009a535  movzx   r8d, cs:NvmeHostUuid.Data4+4
0x14009a53d  movzx   r9d, cs:NvmeHostUuid.Data4+3
0x14009a545  movzx   eax, cs:NvmeHostUuid.Data4+7
0x14009a54c  movzx   r10d, cs:NvmeHostUuid.Data4+2
0x14009a554  movzx   r11d, cs:NvmeHostUuid.Data4+1
0x14009a55c  movzx   ebx, cs:NvmeHostUuid.Data4
0x14009a563  movzx   edi, cs:NvmeHostUuid.Data3
0x14009a56a  movzx   esi, cs:NvmeHostUuid.Data2
0x14009a571  mov     [rsp+260h+var_1F8], eax
0x14009a575  mov     [rsp+260h+var_200], ecx
0x14009a579  lea     rcx, [rbp+160h+DstBuf]; DstBuf
0x14009a57d  mov     [rsp+260h+var_208], edx
0x14009a581  mov     edx, 25h ; '%'; SizeInBytes
0x14009a586  mov     [rsp+260h+var_210], r8d
0x14009a58b  lea     r8, Format; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x14009a592  mov     [rsp+260h+var_218], r9d
0x14009a597  mov     r9d, cs:NvmeHostUuid.Data1
0x14009a59e  mov     [rsp+260h+var_220], r10d
0x14009a5a3  mov     [rsp+260h+var_228], r11d
0x14009a5a8  mov     [rsp+260h+var_230], ebx
0x14009a5ac  mov     dword ptr [rsp+260h+ResultLength], edi
0x14009a5b0  mov     [rsp+260h+Length], esi
0x14009a5b4  call    cs:__imp_sprintf_s
0x14009a5bb  nop     dword ptr [rax+rax+00h]
0x14009a5c0  movups  xmm0, xmmword ptr [rbp+160h+DstBuf]
0x14009a5c4  mov     eax, [rbp+160h+var_160]
0x14009a5c7  movups  xmm1, [rbp+160h+var_170]
0x14009a5cb  movups  xmmword ptr [r15], xmm0
0x14009a5cf  movups  xmmword ptr [r15+10h], xmm1
0x14009a5d4  mov     [r15+20h], eax
0x14009a5d8  mov     eax, r14d
0x14009a5db  mov     rcx, [rbp+160h+var_40]
0x14009a5e2  xor     rcx, rsp; StackCookie
0x14009a5e5  call    __security_check_cookie
0x14009a5ea  add     rsp, 238h
0x14009a5f1  pop     r15
0x14009a5f3  pop     r14
0x14009a5f5  pop     rdi
0x14009a5f6  pop     rsi
0x14009a5f7  pop     rbx
0x14009a5f8  pop     rbp
0x14009a5f9  retn
```
