# filterReadLong

- ea: `0x140003634`
- end: `0x14000384c`
- name: `filterReadLong`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000204c`
- `0x140002c90`
- `0x140004d70`

## callees

- `0x140003634`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f110`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140003710`
- `ntoskrnl!ZwQueryValueKey` at `0x140003710`
- `ntoskrnl!ZwOpenKey` at `0x1400036c4`
- `ntoskrnl!ZwOpenKey` at `0x1400036c4`
- `ntoskrnl!ZwClose` at `0x14000383b`
- `ntoskrnl!ZwClose` at `0x14000383b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400036e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400036e1`

## pseudocode

```c
__int64 __fastcall filterReadLong(__int64 a1, const WCHAR *a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v8; // rdx
  void *KeyHandle; // [rsp+30h] [rbp-39h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-31h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp+17h] BYREF
  int v14; // [rsp+90h] [rbp+27h]

  KeyHandle = 0;
  ResultLength = 0;
  v14 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  if ( !a1 )
  {
    KeyHandle = Handle;
LABEL_3:
    RtlInitUnicodeString(&DestinationString, a2);
    v5 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x14u,
           &ResultLength);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v8 = 242;
        goto LABEL_14;
      }
    }
    else if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      *a3 = HIDWORD(KeyValueInformation);
    }
    else
    {
      v5 = -1073741306;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 243, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
    goto LABEL_5;
  }
  ObjectAttributes.RootDirectory = Handle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 2232);
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( !v5 )
    goto LABEL_3;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v8 = 241;
LABEL_14:
    WPP_SF_d(v6->AttachedDevice, v8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  }
LABEL_5:
  if ( KeyHandle && KeyHandle != Handle )
    ZwClose(KeyHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 244, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x140003634  push    rbp
0x140003636  push    rbx
0x140003637  push    rsi
0x140003638  push    rdi
0x140003639  push    r14
0x14000363b  lea     rbp, [rsp-37h]
0x140003640  sub     rsp, 0A0h
0x140003647  mov     rax, cs:__security_cookie
0x14000364e  xor     rax, rsp
0x140003651  mov     [rbp+57h+var_28], rax
0x140003655  xorps   xmm0, xmm0
0x140003658  lea     r14, WPP_GLOBAL_Control
0x14000365f  xor     eax, eax
0x140003661  mov     rdi, r8
0x140003664  mov     [rbp+57h+KeyHandle], rax
0x140003668  mov     rsi, rdx
0x14000366b  mov     [rbp+57h+var_88], eax
0x14000366e  mov     [rbp+57h+var_30], eax
0x140003671  mov     rax, cs:Handle
0x140003678  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000367c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140003680  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140003684  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140003688  movups  [rbp+57h+KeyValueInformation], xmm0
0x14000368c  test    rcx, rcx
0x14000368f  jz      loc_14000378D
0x140003695  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140003699  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000369d  lea     rax, [rcx+8B8h]
0x1400036a4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400036ab  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400036af  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400036b3  mov     edx, 1; DesiredAccess
0x1400036b8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400036bf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400036c4  call    cs:__imp_ZwOpenKey
0x1400036cb  nop     dword ptr [rax+rax+00h]
0x1400036d0  mov     ebx, eax
0x1400036d2  test    eax, eax
0x1400036d4  jnz     loc_140003796
0x1400036da  mov     rdx, rsi; SourceString
0x1400036dd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400036e1  call    cs:__imp_RtlInitUnicodeString
0x1400036e8  nop     dword ptr [rax+rax+00h]
0x1400036ed  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400036f1  lea     rax, [rbp+57h+var_88]
0x1400036f5  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1400036fa  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400036fe  mov     r8d, 2; KeyValueInformationClass
0x140003704  mov     [rsp+0C0h+Length], 14h; Length
0x14000370c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140003710  call    cs:__imp_ZwQueryValueKey
0x140003717  nop     dword ptr [rax+rax+00h]
0x14000371c  mov     ebx, eax
0x14000371e  test    eax, eax
0x140003720  jz      loc_1400037DE
0x140003726  mov     rcx, cs:WPP_GLOBAL_Control
0x14000372d  cmp     rcx, r14
0x140003730  jnz     loc_1400037D1
0x140003736  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000373a  test    rcx, rcx
0x14000373d  jnz     loc_14000382E
0x140003743  mov     rcx, cs:WPP_GLOBAL_Control
0x14000374a  cmp     rcx, r14
0x14000374d  jnz     short loc_14000376C
0x14000374f  mov     eax, ebx
0x140003751  mov     rcx, [rbp+57h+var_28]
0x140003755  xor     rcx, rsp; StackCookie
0x140003758  call    __security_check_cookie
0x14000375d  add     rsp, 0A0h
0x140003764  pop     r14
0x140003766  pop     rdi
0x140003767  pop     rsi
0x140003768  pop     rbx
0x140003769  pop     rbp
0x14000376a  retn
0x14000376c  mov     eax, [rcx+2Ch]
0x14000376f  test    al, 20h
0x140003771  jz      short loc_14000374F
0x140003773  mov     rcx, [rcx+18h]
0x140003777  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000377e  mov     edx, 0F4h
0x140003783  mov     r9d, ebx
0x140003786  call    WPP_SF_d
0x14000378b  jmp     short loc_14000374F
0x14000378d  mov     [rbp+57h+KeyHandle], rax
0x140003791  jmp     loc_1400036DA
0x140003796  mov     rcx, cs:WPP_GLOBAL_Control
0x14000379d  cmp     rcx, r14
0x1400037a0  jz      short loc_140003736
0x1400037a2  mov     edx, [rcx+2Ch]
0x1400037a5  test    dl, 1
0x1400037a8  jz      short loc_140003736
0x1400037aa  mov     edx, 0F1h
0x1400037af  mov     r9d, eax
0x1400037b2  jmp     short loc_1400037BC
0x1400037b4  mov     edx, 0F2h
0x1400037b9  mov     r9d, ebx
0x1400037bc  mov     rcx, [rcx+18h]
0x1400037c0  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400037c7  call    WPP_SF_d
0x1400037cc  jmp     loc_140003736
0x1400037d1  mov     eax, [rcx+2Ch]
0x1400037d4  test    al, 1
0x1400037d6  jz      loc_140003736
0x1400037dc  jmp     short loc_1400037B4
0x1400037de  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1400037e2  jnz     short loc_1400037F4
0x1400037e4  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x1400037e8  jnz     short loc_1400037F4
0x1400037ea  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1400037ed  mov     [rdi], eax
0x1400037ef  jmp     loc_140003736
0x1400037f4  mov     ebx, 0C0000206h
0x1400037f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003800  cmp     rcx, r14
0x140003803  jz      loc_140003736
0x140003809  mov     eax, [rcx+2Ch]
0x14000380c  test    al, 1
0x14000380e  jz      loc_140003736
0x140003814  mov     rcx, [rcx+18h]
0x140003818  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000381f  mov     edx, 0F3h
0x140003824  call    WPP_SF_
0x140003829  jmp     loc_140003736
0x14000382e  cmp     rcx, cs:Handle
0x140003835  jz      loc_140003743
0x14000383b  call    cs:__imp_ZwClose
0x140003842  nop     dword ptr [rax+rax+00h]
0x140003847  jmp     loc_140003743
```
