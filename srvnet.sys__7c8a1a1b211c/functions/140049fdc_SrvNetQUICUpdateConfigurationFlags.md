# SrvNetQUICUpdateConfigurationFlags

- ea: `0x140049fdc`
- end: `0x14004a10c`
- name: `SrvNetQUICUpdateConfigurationFlags`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140053eb0`

## callees

- `0x14001c58c`
- `0x14001dff8`
- `0x14001e5b0`
- `0x14002a3e0`
- `0x1400494f4`
- `0x140049fdc`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x14004a07f`
- `ntoskrnl!RtlHashUnicodeString` at `0x14004a07f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004a09b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004a09b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a0dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a0dc`

## pseudocode

```c
__int64 __fastcall SrvNetQUICUpdateConfigurationFlags(_DWORD *a1, unsigned int a2, int a3)
{
  int ServerName; // ebx
  _DWORD *v6; // rax
  ULONG HashValue; // [rsp+30h] [rbp-238h] BYREF
  UNICODE_STRING String; // [rsp+38h] [rbp-230h] BYREF
  char v10; // [rsp+50h] [rbp-218h] BYREF

  HashValue = 0;
  String.Buffer = (PWSTR)&v10;
  *(_QWORD *)&String.Length = 0x2000000;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ds(WPP_GLOBAL_Control->AttachedDevice, 82, a3, a1[34], (__int64)(a1 + 2));
  }
  ServerName = ValidateSrvNetQUICActionBufferAndGetServerName(a1, a2, &String);
  if ( ServerName >= 0 )
  {
    RtlHashUnicodeString(&String, 1u, 0, &HashValue);
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840), 1u);
    v6 = (_DWORD *)SrvNetQUICFindConfHelper(&String);
    if ( v6 )
    {
      v6[9] = *a1;
      SrvNetQUICDereferenceCertEntry(v6);
    }
    else
    {
      ServerName = -1073741275;
    }
    ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840));
  }
  return (unsigned int)ServerName;
}

```

## disassembly

```asm
0x140049fdc  mov     [rsp+arg_8], rbx
0x140049fe1  push    rdi
0x140049fe2  sub     rsp, 260h
0x140049fe9  mov     rax, cs:__security_cookie
0x140049ff0  xor     rax, rsp
0x140049ff3  mov     [rsp+268h+var_18], rax
0x140049ffb  lea     rax, [rsp+268h+var_218]
0x14004a000  mov     [rsp+268h+HashValue], 0
0x14004a008  mov     [rsp+268h+String.Buffer], rax
0x14004a00d  mov     ebx, edx
0x14004a00f  mov     rdi, rcx
0x14004a012  mov     qword ptr [rsp+268h+String.Length], 2000000h
0x14004a01b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a022  lea     rax, WPP_GLOBAL_Control
0x14004a029  cmp     rcx, rax
0x14004a02c  jz      short loc_14004A05B
0x14004a02e  test    dword ptr [rcx+2Ch], 200000h
0x14004a035  jz      short loc_14004A05B
0x14004a037  cmp     byte ptr [rcx+29h], 2
0x14004a03b  jb      short loc_14004A05B
0x14004a03d  mov     r9d, [rdi+88h]
0x14004a044  lea     rax, [rdi+8]
0x14004a048  mov     rcx, [rcx+18h]
0x14004a04c  mov     edx, 52h ; 'R'
0x14004a051  mov     [rsp+268h+var_248], rax
0x14004a056  call    WPP_SF_ds
0x14004a05b  lea     r8, [rsp+268h+String]
0x14004a060  mov     edx, ebx
0x14004a062  mov     rcx, rdi
0x14004a065  call    ValidateSrvNetQUICActionBufferAndGetServerName
0x14004a06a  mov     ebx, eax
0x14004a06c  test    eax, eax
0x14004a06e  js      short loc_14004A0E8
0x14004a070  lea     r9, [rsp+268h+HashValue]; HashValue
0x14004a075  xor     r8d, r8d; HashAlgorithm
0x14004a078  mov     dl, 1; CaseInSensitive
0x14004a07a  lea     rcx, [rsp+268h+String]; String
0x14004a07f  call    cs:__imp_RtlHashUnicodeString
0x14004a086  nop     dword ptr [rax+rax+00h]
0x14004a08b  mov     rcx, cs:SrvNetDeviceExtension
0x14004a092  mov     dl, 1; Wait
0x14004a094  add     rcx, 348h; Resource
0x14004a09b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004a0a2  nop     dword ptr [rax+rax+00h]
0x14004a0a7  mov     edx, [rsp+268h+HashValue]
0x14004a0ab  lea     rcx, [rsp+268h+String]; String2
0x14004a0b0  call    SrvNetQUICFindConfHelper
0x14004a0b5  test    rax, rax
0x14004a0b8  jz      short loc_14004A0C9
0x14004a0ba  mov     ecx, [rdi]
0x14004a0bc  mov     [rax+24h], ecx
0x14004a0bf  mov     rcx, rax; P
0x14004a0c2  call    SrvNetQUICDereferenceCertEntry
0x14004a0c7  jmp     short loc_14004A0CE
0x14004a0c9  mov     ebx, 0C0000225h
0x14004a0ce  mov     rcx, cs:SrvNetDeviceExtension
0x14004a0d5  add     rcx, 348h; Resource
0x14004a0dc  call    cs:__imp_ExReleaseResourceLite
0x14004a0e3  nop     dword ptr [rax+rax+00h]
0x14004a0e8  mov     eax, ebx
0x14004a0ea  mov     rcx, [rsp+268h+var_18]
0x14004a0f2  xor     rcx, rsp; StackCookie
0x14004a0f5  call    __security_check_cookie
0x14004a0fa  mov     rbx, [rsp+268h+arg_8]
0x14004a102  add     rsp, 260h
0x14004a109  pop     rdi
0x14004a10a  retn
```
