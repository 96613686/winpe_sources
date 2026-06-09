# SrvNetQUICGetConfiguration

- ea: `0x14001c5e0`
- end: `0x14001c6f9`
- name: `SrvNetQUICGetConfiguration`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14001d2c0`

## callees

- `0x14001389c`
- `0x14001c5e0`
- `0x14001c754`
- `0x14002a3e0`
- `0x1400494f4`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x14001c671`
- `ntoskrnl!RtlHashUnicodeString` at `0x14001c671`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c6d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c6d0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c699`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c699`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c67d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c67d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c6c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c6c4`

## pseudocode

```c
__int64 __fastcall SrvNetQUICGetConfiguration(const CHAR *a1)
{
  int v1; // eax
  __int64 v3; // rbx
  ULONG HashValue; // [rsp+20h] [rbp-238h] BYREF
  UNICODE_STRING String; // [rsp+28h] [rbp-230h] BYREF
  char v6; // [rsp+40h] [rbp-218h] BYREF

  HashValue = 0;
  String.Buffer = (PWSTR)&v6;
  *(_QWORD *)&String.Length = 0x2000000;
  v1 = SrvNetQUICGetUnicodeServerName(a1);
  if ( v1 >= 0 )
  {
    RtlHashUnicodeString(&String, 1u, 0, &HashValue);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840), 1u);
    v3 = SrvNetQUICFindConfHelper(&String);
    ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840));
    KeLeaveCriticalRegion();
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          76,
          WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids,
          (unsigned int)v1);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14001c5e0  push    rbx
0x14001c5e2  sub     rsp, 250h
0x14001c5e9  mov     rax, cs:__security_cookie
0x14001c5f0  xor     rax, rsp
0x14001c5f3  mov     [rsp+258h+var_18], rax
0x14001c5fb  lea     rax, [rsp+258h+var_218]
0x14001c600  mov     [rsp+258h+HashValue], 0
0x14001c608  lea     r8, [rsp+258h+String]
0x14001c60d  mov     [rsp+258h+String.Buffer], rax
0x14001c612  mov     qword ptr [rsp+258h+String.Length], 2000000h
0x14001c61b  call    SrvNetQUICGetUnicodeServerName
0x14001c620  test    eax, eax
0x14001c622  jns     short loc_14001C662
0x14001c624  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001c62b  lea     rdx, WPP_GLOBAL_Control
0x14001c632  cmp     rcx, rdx
0x14001c635  jz      short loc_14001C65E
0x14001c637  test    dword ptr [rcx+2Ch], 200000h
0x14001c63e  jz      short loc_14001C65E
0x14001c640  cmp     byte ptr [rcx+29h], 1
0x14001c644  jb      short loc_14001C65E
0x14001c646  mov     rcx, [rcx+18h]
0x14001c64a  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14001c651  mov     edx, 4Ch ; 'L'
0x14001c656  mov     r9d, eax
0x14001c659  call    WPP_SF_d
0x14001c65e  xor     eax, eax
0x14001c660  jmp     short loc_14001C6DF
0x14001c662  lea     r9, [rsp+258h+HashValue]; HashValue
0x14001c667  xor     r8d, r8d; HashAlgorithm
0x14001c66a  mov     dl, 1; CaseInSensitive
0x14001c66c  lea     rcx, [rsp+258h+String]; String
0x14001c671  call    cs:__imp_RtlHashUnicodeString
0x14001c678  nop     dword ptr [rax+rax+00h]
0x14001c67d  call    cs:__imp_KeEnterCriticalRegion
0x14001c684  nop     dword ptr [rax+rax+00h]
0x14001c689  mov     rcx, cs:SrvNetDeviceExtension
0x14001c690  mov     dl, 1; Wait
0x14001c692  add     rcx, 348h; Resource
0x14001c699  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c6a0  nop     dword ptr [rax+rax+00h]
0x14001c6a5  mov     edx, [rsp+258h+HashValue]
0x14001c6a9  lea     rcx, [rsp+258h+String]; String2
0x14001c6ae  call    SrvNetQUICFindConfHelper
0x14001c6b3  mov     rcx, cs:SrvNetDeviceExtension
0x14001c6ba  mov     rbx, rax
0x14001c6bd  add     rcx, 348h; Resource
0x14001c6c4  call    cs:__imp_ExReleaseResourceLite
0x14001c6cb  nop     dword ptr [rax+rax+00h]
0x14001c6d0  call    cs:__imp_KeLeaveCriticalRegion
0x14001c6d7  nop     dword ptr [rax+rax+00h]
0x14001c6dc  mov     rax, rbx
0x14001c6df  mov     rcx, [rsp+258h+var_18]
0x14001c6e7  xor     rcx, rsp; StackCookie
0x14001c6ea  call    __security_check_cookie
0x14001c6ef  add     rsp, 250h
0x14001c6f6  pop     rbx
0x14001c6f7  retn
```
