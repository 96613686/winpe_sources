# SrvNetQUICUpdateConfiguration

- ea: `0x140049e90`
- end: `0x140049fd6`
- name: `SrvNetQUICUpdateConfiguration`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140053eb0`

## callees

- `0x14001c58c`
- `0x14001dff8`
- `0x14001e5b0`
- `0x14002a3e0`
- `0x1400494f4`
- `0x140049db0`
- `0x140049e90`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x140049f39`
- `ntoskrnl!RtlHashUnicodeString` at `0x140049f39`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049f55`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049f55`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049fa4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049fa4`

## pseudocode

```c
__int64 __fastcall SrvNetQUICUpdateConfiguration(__int64 a1, unsigned int a2, int a3)
{
  int ServerName; // ebx
  __int64 v6; // rax
  void *v7; // rsi
  ULONG HashValue; // [rsp+30h] [rbp-248h] BYREF
  UNICODE_STRING String; // [rsp+38h] [rbp-240h] BYREF
  char v11; // [rsp+50h] [rbp-228h] BYREF

  HashValue = 0;
  String.Buffer = (PWSTR)&v11;
  *(_QWORD *)&String.Length = 0x2000000;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ds(WPP_GLOBAL_Control->AttachedDevice, 83, a3, *(_DWORD *)(a1 + 136), a1 + 8);
  }
  ServerName = ValidateSrvNetQUICActionBufferAndGetServerName(a1, a2, &String);
  if ( ServerName >= 0 )
  {
    RtlHashUnicodeString(&String, 1u, 0, &HashValue);
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840), 1u);
    v6 = SrvNetQUICFindConfHelper(&String);
    v7 = (void *)v6;
    if ( v6 )
    {
      ServerName = SrvNetQUICUpdateConfHelper(v6, a1, a2);
      SrvNetQUICDereferenceCertEntry(v7);
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
0x140049e90  mov     [rsp+arg_10], rbx
0x140049e95  push    rbp
0x140049e96  push    rsi
0x140049e97  push    rdi
0x140049e98  sub     rsp, 260h
0x140049e9f  mov     rax, cs:__security_cookie
0x140049ea6  xor     rax, rsp
0x140049ea9  mov     [rsp+278h+var_28], rax
0x140049eb1  lea     rax, [rsp+278h+var_228]
0x140049eb6  mov     [rsp+278h+HashValue], 0
0x140049ebe  mov     [rsp+278h+String.Buffer], rax
0x140049ec3  mov     ebp, edx
0x140049ec5  mov     rdi, rcx
0x140049ec8  mov     qword ptr [rsp+278h+String.Length], 2000000h
0x140049ed1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049ed8  lea     rax, WPP_GLOBAL_Control
0x140049edf  cmp     rcx, rax
0x140049ee2  jz      short loc_140049F11
0x140049ee4  test    dword ptr [rcx+2Ch], 200000h
0x140049eeb  jz      short loc_140049F11
0x140049eed  cmp     byte ptr [rcx+29h], 2
0x140049ef1  jb      short loc_140049F11
0x140049ef3  mov     r9d, [rdi+88h]
0x140049efa  lea     rax, [rdi+8]
0x140049efe  mov     rcx, [rcx+18h]
0x140049f02  mov     edx, 53h ; 'S'
0x140049f07  mov     [rsp+278h+var_258], rax
0x140049f0c  call    WPP_SF_ds
0x140049f11  lea     r8, [rsp+278h+String]
0x140049f16  mov     edx, ebp
0x140049f18  mov     rcx, rdi
0x140049f1b  call    ValidateSrvNetQUICActionBufferAndGetServerName
0x140049f20  mov     ebx, eax
0x140049f22  test    eax, eax
0x140049f24  js      loc_140049FB0
0x140049f2a  lea     r9, [rsp+278h+HashValue]; HashValue
0x140049f2f  xor     r8d, r8d; HashAlgorithm
0x140049f32  mov     dl, 1; CaseInSensitive
0x140049f34  lea     rcx, [rsp+278h+String]; String
0x140049f39  call    cs:__imp_RtlHashUnicodeString
0x140049f40  nop     dword ptr [rax+rax+00h]
0x140049f45  mov     rcx, cs:SrvNetDeviceExtension
0x140049f4c  mov     dl, 1; Wait
0x140049f4e  add     rcx, 348h; Resource
0x140049f55  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140049f5c  nop     dword ptr [rax+rax+00h]
0x140049f61  mov     edx, [rsp+278h+HashValue]
0x140049f65  lea     rcx, [rsp+278h+String]; String2
0x140049f6a  call    SrvNetQUICFindConfHelper
0x140049f6f  mov     rsi, rax
0x140049f72  test    rax, rax
0x140049f75  jnz     short loc_140049F7E
0x140049f77  mov     ebx, 0C0000225h
0x140049f7c  jmp     short loc_140049F96
0x140049f7e  mov     r8d, ebp
0x140049f81  mov     rdx, rdi
0x140049f84  mov     rcx, rsi
0x140049f87  call    SrvNetQUICUpdateConfHelper
0x140049f8c  mov     rcx, rsi; P
0x140049f8f  mov     ebx, eax
0x140049f91  call    SrvNetQUICDereferenceCertEntry
0x140049f96  mov     rcx, cs:SrvNetDeviceExtension
0x140049f9d  add     rcx, 348h; Resource
0x140049fa4  call    cs:__imp_ExReleaseResourceLite
0x140049fab  nop     dword ptr [rax+rax+00h]
0x140049fb0  mov     eax, ebx
0x140049fb2  mov     rcx, [rsp+278h+var_28]
0x140049fba  xor     rcx, rsp; StackCookie
0x140049fbd  call    __security_check_cookie
0x140049fc2  mov     rbx, [rsp+278h+arg_10]
0x140049fca  add     rsp, 260h
0x140049fd1  pop     rdi
0x140049fd2  pop     rsi
0x140049fd3  pop     rbp
0x140049fd4  retn
```
