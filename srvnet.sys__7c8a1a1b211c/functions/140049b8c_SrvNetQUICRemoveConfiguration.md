# SrvNetQUICRemoveConfiguration

- ea: `0x140049b8c`
- end: `0x140049d42`
- name: `SrvNetQUICRemoveConfiguration`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140053eb0`

## callees

- `0x14001c58c`
- `0x14001dff8`
- `0x14001e5b0`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x1400494f4`
- `0x140049b8c`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x140049c38`
- `ntoskrnl!RtlHashUnicodeString` at `0x140049c38`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140049cfe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140049cfe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140049cd0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140049cd0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049c54`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049c54`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049cb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049cb2`

## pseudocode

```c
__int64 __fastcall SrvNetQUICRemoveConfiguration(__int64 a1, unsigned int a2, int a3)
{
  int ServerName; // esi
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rax
  _QWORD *v9; // rcx
  ULONG HashValue; // [rsp+30h] [rbp-238h] BYREF
  UNICODE_STRING String; // [rsp+38h] [rbp-230h] BYREF
  char v13; // [rsp+50h] [rbp-218h] BYREF

  HashValue = 0;
  String.Buffer = (PWSTR)&v13;
  *(_QWORD *)&String.Length = 0x2000000;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ds(WPP_GLOBAL_Control->AttachedDevice, 81, a3, *(_DWORD *)(a1 + 136), a1 + 8);
  }
  ServerName = ValidateSrvNetQUICActionBufferAndGetServerName(a1, a2, &String);
  if ( ServerName >= 0 )
  {
    RtlHashUnicodeString(&String, 1u, 0, &HashValue);
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840), 1u);
    v6 = (_QWORD *)SrvNetQUICFindConfHelper(&String);
    v7 = v6;
    if ( v6 )
    {
      v8 = *v6;
      if ( *(_QWORD **)(v8 + 8) != v7 || (v9 = (_QWORD *)v7[1], (_QWORD *)*v9 != v7) )
        __fastfail(3u);
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      v7[1] = v7;
      *v7 = v7;
    }
    else
    {
      ServerName = -1073741275;
    }
    ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840));
    if ( v7 )
    {
      if ( v7[6] )
      {
        ExAcquirePushLockExclusiveEx(v7 + 5, 0);
        (*(void (__fastcall **)(_QWORD))(MsQuic + 72))(v7[6]);
        v7[6] = 0;
        ExReleasePushLockExclusiveEx(v7 + 5, 0);
      }
      SrvNetQUICDereferenceCertEntry(v7);
      SrvNetQUICDereferenceCertEntry(v7);
    }
  }
  return (unsigned int)ServerName;
}

```

## disassembly

```asm
0x140049b8c  mov     [rsp+arg_8], rbx
0x140049b91  mov     [rsp+arg_10], rsi
0x140049b96  push    rdi
0x140049b97  sub     rsp, 260h
0x140049b9e  mov     rax, cs:__security_cookie
0x140049ba5  xor     rax, rsp
0x140049ba8  mov     [rsp+268h+var_18], rax
0x140049bb0  lea     rax, [rsp+268h+var_218]
0x140049bb5  mov     [rsp+268h+HashValue], 0
0x140049bbd  mov     [rsp+268h+String.Buffer], rax
0x140049bc2  mov     edi, edx
0x140049bc4  mov     rbx, rcx
0x140049bc7  mov     qword ptr [rsp+268h+String.Length], 2000000h
0x140049bd0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049bd7  lea     rax, WPP_GLOBAL_Control
0x140049bde  cmp     rcx, rax
0x140049be1  jz      short loc_140049C10
0x140049be3  test    dword ptr [rcx+2Ch], 200000h
0x140049bea  jz      short loc_140049C10
0x140049bec  cmp     byte ptr [rcx+29h], 2
0x140049bf0  jb      short loc_140049C10
0x140049bf2  mov     r9d, [rbx+88h]
0x140049bf9  lea     rax, [rbx+8]
0x140049bfd  mov     rcx, [rcx+18h]
0x140049c01  mov     edx, 51h ; 'Q'
0x140049c06  mov     [rsp+268h+var_248], rax
0x140049c0b  call    WPP_SF_ds
0x140049c10  lea     r8, [rsp+268h+String]
0x140049c15  mov     edx, edi
0x140049c17  mov     rcx, rbx
0x140049c1a  call    ValidateSrvNetQUICActionBufferAndGetServerName
0x140049c1f  mov     esi, eax
0x140049c21  test    eax, eax
0x140049c23  js      loc_140049D1A
0x140049c29  lea     r9, [rsp+268h+HashValue]; HashValue
0x140049c2e  xor     r8d, r8d; HashAlgorithm
0x140049c31  mov     dl, 1; CaseInSensitive
0x140049c33  lea     rcx, [rsp+268h+String]; String
0x140049c38  call    cs:__imp_RtlHashUnicodeString
0x140049c3f  nop     dword ptr [rax+rax+00h]
0x140049c44  mov     rcx, cs:SrvNetDeviceExtension
0x140049c4b  mov     dl, 1; Wait
0x140049c4d  add     rcx, 348h; Resource
0x140049c54  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140049c5b  nop     dword ptr [rax+rax+00h]
0x140049c60  mov     edx, [rsp+268h+HashValue]
0x140049c64  lea     rcx, [rsp+268h+String]; String2
0x140049c69  call    SrvNetQUICFindConfHelper
0x140049c6e  mov     rdi, rax
0x140049c71  test    rax, rax
0x140049c74  jz      short loc_140049C9F
0x140049c76  mov     rax, [rax]
0x140049c79  cmp     [rax+8], rdi
0x140049c7d  jnz     short loc_140049C98
0x140049c7f  mov     rcx, [rdi+8]
0x140049c83  cmp     [rcx], rdi
0x140049c86  jnz     short loc_140049C98
0x140049c88  mov     [rcx], rax
0x140049c8b  mov     [rax+8], rcx
0x140049c8f  mov     [rdi+8], rdi
0x140049c93  mov     [rdi], rdi
0x140049c96  jmp     short loc_140049CA4
0x140049c98  mov     ecx, 3
0x140049c9d  int     29h; Win8: RtlFailFast(ecx)
0x140049c9f  mov     esi, 0C0000225h
0x140049ca4  mov     rcx, cs:SrvNetDeviceExtension
0x140049cab  add     rcx, 348h; Resource
0x140049cb2  call    cs:__imp_ExReleaseResourceLite
0x140049cb9  nop     dword ptr [rax+rax+00h]
0x140049cbe  test    rdi, rdi
0x140049cc1  jz      short loc_140049D1A
0x140049cc3  cmp     qword ptr [rdi+30h], 0
0x140049cc8  jz      short loc_140049D0A
0x140049cca  xor     edx, edx
0x140049ccc  lea     rcx, [rdi+28h]
0x140049cd0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140049cd7  nop     dword ptr [rax+rax+00h]
0x140049cdc  mov     rax, cs:MsQuic
0x140049ce3  mov     rcx, [rdi+30h]
0x140049ce7  mov     rax, [rax+48h]
0x140049ceb  call    _guard_dispatch_icall
0x140049cf0  xor     edx, edx
0x140049cf2  mov     qword ptr [rdi+30h], 0
0x140049cfa  lea     rcx, [rdi+28h]
0x140049cfe  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140049d05  nop     dword ptr [rax+rax+00h]
0x140049d0a  mov     rcx, rdi; P
0x140049d0d  call    SrvNetQUICDereferenceCertEntry
0x140049d12  mov     rcx, rdi; P
0x140049d15  call    SrvNetQUICDereferenceCertEntry
0x140049d1a  mov     eax, esi
0x140049d1c  mov     rcx, [rsp+268h+var_18]
0x140049d24  xor     rcx, rsp; StackCookie
0x140049d27  call    __security_check_cookie
0x140049d2c  lea     r11, [rsp+268h+var_8]
0x140049d34  mov     rbx, [r11+18h]
0x140049d38  mov     rsi, [r11+20h]
0x140049d3c  mov     rsp, r11
0x140049d3f  pop     rdi
0x140049d40  retn
```
