# SqospGetRegistryUINT32

- ea: `0x140014040`
- end: `0x140014225`
- name: `SqospGetRegistryUINT32`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400161ec`

## callees

- `0x14000666c`
- `0x140008d20`
- `0x140014040`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400141f1`
- `ntoskrnl!ZwClose` at `0x1400141f1`
- `ntoskrnl!ZwQueryValueKey` at `0x140014179`
- `ntoskrnl!ZwQueryValueKey` at `0x140014179`
- `ntoskrnl!ZwOpenKey` at `0x140014113`
- `ntoskrnl!ZwOpenKey` at `0x140014113`

## pseudocode

```c
char __fastcall SqospGetRegistryUINT32(struct _UNICODE_STRING *a1, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  char v6; // di
  __int64 v7; // rcx
  const wchar_t *v8; // rax
  __int64 v9; // r9
  NTSTATUS v10; // eax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  int v14; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-31h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-29h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-11h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp+1Fh] BYREF
  int v21; // [rsp+84h] [rbp+23h]
  int v22; // [rsp+88h] [rbp+27h]
  unsigned int v23; // [rsp+8Ch] [rbp+2Bh]

  ResultLength = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  v7 = 0x7FFF;
  v8 = L"StorageBaseIOSize";
  ValueName = 0;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0 ? 0xC000000D : 0;
  if ( !v7 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return v6;
    }
    v12 = 10;
    goto LABEL_21;
  }
  ValueName.Buffer = L"StorageBaseIOSize";
  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.Length = 48;
  ValueName.Length = -2 - 2 * v7;
  ObjectAttributes.RootDirectory = 0;
  ValueName.MaximumLength = -2 * v7;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v9 = (unsigned int)v10;
  if ( v10 >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength) >= 0
      && v21 == 4
      && v22 == 4 )
    {
      v13 = v23;
      v14 = 4096;
      *a5 = v23;
      if ( v13 < 0x1000 || (v14 = 0x400000, v13 > 0x400000) )
        *a5 = v14;
      v6 = 1;
    }
    goto LABEL_22;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v12 = 11;
LABEL_21:
    WPP_SF_d(v11->AttachedDevice, v12, WPP_b8a405419f5733ac566e8c3690148060_Traceguids, v9);
  }
LABEL_22:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v6;
}

```

## disassembly

```asm
0x140014040  mov     [rsp-8+arg_8], rbx
0x140014045  mov     [rsp-8+arg_10], rsi
0x14001404a  push    rbp
0x14001404b  push    rdi
0x14001404c  push    r14
0x14001404e  lea     rbp, [rsp-3Fh]
0x140014053  sub     rsp, 0A0h
0x14001405a  mov     rax, cs:__security_cookie
0x140014061  xor     rax, rsp
0x140014064  mov     [rbp+4Fh+var_18], rax
0x140014068  mov     rbx, [rbp+4Fh+arg_20]
0x14001406c  lea     r8, aStoragebaseios; "StorageBaseIOSize"
0x140014073  xorps   xmm0, xmm0
0x140014076  xor     eax, eax
0x140014078  xor     esi, esi
0x14001407a  mov     rdx, rcx
0x14001407d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x140014081  mov     [rbp+4Fh+var_80], esi
0x140014084  mov     dil, sil
0x140014087  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14001408b  lea     r14d, [rsi+2]
0x14001408f  mov     [rbp+4Fh+KeyHandle], rsi
0x140014093  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x140014097  mov     ecx, 7FFFh
0x14001409c  mov     rax, r8
0x14001409f  movups  xmmword ptr [rbp+4Fh+ValueName.Length], xmm0
0x1400140a3  cmp     [rax], si
0x1400140a6  jz      short loc_1400140B1
0x1400140a8  add     rax, r14
0x1400140ab  sub     rcx, 1
0x1400140af  jnz     short loc_1400140A3
0x1400140b1  mov     rax, rcx
0x1400140b4  neg     rax
0x1400140b7  sbb     r9d, r9d
0x1400140ba  not     r9d
0x1400140bd  and     r9d, 0C000000Dh
0x1400140c4  test    rcx, rcx
0x1400140c7  jz      loc_1400141B3
0x1400140cd  add     cx, cx
0x1400140d0  mov     [rbp+4Fh+ValueName.Buffer], r8
0x1400140d4  mov     eax, 0FFFEh
0x1400140d9  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rdx
0x1400140dd  sub     ax, cx
0x1400140e0  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400140e7  mov     [rbp+4Fh+ValueName.Length], ax
0x1400140eb  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400140ef  add     ax, r14w
0x1400140f3  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x1400140f7  xorps   xmm0, xmm0
0x1400140fa  mov     [rbp+4Fh+ValueName.MaximumLength], ax
0x1400140fe  mov     edx, 20019h; DesiredAccess
0x140014103  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x14001410a  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14001410e  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140014113  call    cs:__imp_ZwOpenKey
0x14001411a  nop     dword ptr [rax+rax+00h]
0x14001411f  mov     r9d, eax
0x140014122  test    eax, eax
0x140014124  jns     short loc_140014159
0x140014126  mov     rcx, cs:WPP_GLOBAL_Control
0x14001412d  lea     rax, WPP_GLOBAL_Control
0x140014134  cmp     rcx, rax
0x140014137  jz      loc_1400141E8
0x14001413d  mov     eax, [rcx+2Ch]
0x140014140  test    al, al
0x140014142  jns     loc_1400141E8
0x140014148  cmp     [rcx+29h], r14b
0x14001414c  jb      loc_1400141E8
0x140014152  mov     edx, 0Bh
0x140014157  jmp     short loc_1400141D8
0x140014159  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14001415d  lea     rax, [rbp+4Fh+var_80]
0x140014161  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140014166  lea     r9, [rbp+4Fh+KeyValueInformation]; KeyValueInformation
0x14001416a  mov     r8d, r14d; KeyValueInformationClass
0x14001416d  mov     [rsp+0B0h+Length], 14h; Length
0x140014175  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x140014179  call    cs:__imp_ZwQueryValueKey
0x140014180  nop     dword ptr [rax+rax+00h]
0x140014185  test    eax, eax
0x140014187  js      short loc_1400141E8
0x140014189  cmp     [rbp+4Fh+var_2C], 4
0x14001418d  jnz     short loc_1400141E8
0x14001418f  cmp     [rbp+4Fh+var_28], 4
0x140014193  jnz     short loc_1400141E8
0x140014195  mov     eax, [rbp+4Fh+var_24]
0x140014198  mov     ecx, 1000h
0x14001419d  mov     [rbx], eax
0x14001419f  cmp     eax, ecx
0x1400141a1  jb      short loc_1400141AC
0x1400141a3  mov     ecx, 400000h
0x1400141a8  cmp     eax, ecx
0x1400141aa  jbe     short loc_1400141AE
0x1400141ac  mov     [rbx], ecx
0x1400141ae  mov     dil, 1
0x1400141b1  jmp     short loc_1400141E8
0x1400141b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141ba  lea     rax, WPP_GLOBAL_Control
0x1400141c1  cmp     rcx, rax
0x1400141c4  jz      short loc_1400141FD
0x1400141c6  mov     eax, [rcx+2Ch]
0x1400141c9  test    al, al
0x1400141cb  jns     short loc_1400141FD
0x1400141cd  cmp     [rcx+29h], r14b
0x1400141d1  jb      short loc_1400141FD
0x1400141d3  mov     edx, 0Ah
0x1400141d8  mov     rcx, [rcx+18h]
0x1400141dc  lea     r8, WPP_b8a405419f5733ac566e8c3690148060_Traceguids
0x1400141e3  call    WPP_SF_d
0x1400141e8  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x1400141ec  test    rcx, rcx
0x1400141ef  jz      short loc_1400141FD
0x1400141f1  call    cs:__imp_ZwClose
0x1400141f8  nop     dword ptr [rax+rax+00h]
0x1400141fd  mov     al, dil
0x140014200  mov     rcx, [rbp+4Fh+var_18]
0x140014204  xor     rcx, rsp; StackCookie
0x140014207  call    __security_check_cookie
0x14001420c  lea     r11, [rsp+0B0h+var_10]
0x140014214  mov     rbx, [r11+28h]
0x140014218  mov     rsi, [r11+30h]
0x14001421c  mov     rsp, r11
0x14001421f  pop     r14
0x140014221  pop     rdi
0x140014222  pop     rbp
0x140014223  retn
```
