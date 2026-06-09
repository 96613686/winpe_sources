# SrvNetQUICUpdateOrAddCertificates

- ea: `0x14004a114`
- end: `0x14004a261`
- name: `SrvNetQUICUpdateOrAddCertificates`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x140053eb0`

## callees

- `0x14001c58c`
- `0x14001dff8`
- `0x14001e5b0`
- `0x14002a3e0`
- `0x140048ca8`
- `0x1400494f4`
- `0x140049db0`
- `0x14004a114`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x14004a1bd`
- `ntoskrnl!RtlHashUnicodeString` at `0x14004a1bd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004a1d9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004a1d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a22f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a22f`

## pseudocode

```c
__int64 __fastcall SrvNetQUICUpdateOrAddCertificates(__int64 a1, unsigned int a2, int a3)
{
  int ServerName; // ebx
  __int64 v6; // rax
  void *v7; // rbp
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
    WPP_SF_ds(WPP_GLOBAL_Control->AttachedDevice, 84, a3, *(_DWORD *)(a1 + 136), a1 + 8);
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
      ServerName = SrvNetQUICAddCertHelper(a1, a2);
    }
    ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 840));
  }
  return (unsigned int)ServerName;
}

```

## disassembly

```asm
0x14004a114  mov     [rsp+arg_10], rbx
0x14004a119  push    rbp
0x14004a11a  push    rsi
0x14004a11b  push    rdi
0x14004a11c  sub     rsp, 260h
0x14004a123  mov     rax, cs:__security_cookie
0x14004a12a  xor     rax, rsp
0x14004a12d  mov     [rsp+278h+var_28], rax
0x14004a135  lea     rax, [rsp+278h+var_228]
0x14004a13a  mov     [rsp+278h+HashValue], 0
0x14004a142  mov     [rsp+278h+String.Buffer], rax
0x14004a147  mov     esi, edx
0x14004a149  mov     rdi, rcx
0x14004a14c  mov     qword ptr [rsp+278h+String.Length], 2000000h
0x14004a155  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a15c  lea     rax, WPP_GLOBAL_Control
0x14004a163  cmp     rcx, rax
0x14004a166  jz      short loc_14004A195
0x14004a168  test    dword ptr [rcx+2Ch], 200000h
0x14004a16f  jz      short loc_14004A195
0x14004a171  cmp     byte ptr [rcx+29h], 2
0x14004a175  jb      short loc_14004A195
0x14004a177  mov     r9d, [rdi+88h]
0x14004a17e  lea     rax, [rdi+8]
0x14004a182  mov     rcx, [rcx+18h]
0x14004a186  mov     edx, 54h ; 'T'
0x14004a18b  mov     [rsp+278h+var_258], rax
0x14004a190  call    WPP_SF_ds
0x14004a195  lea     r8, [rsp+278h+String]
0x14004a19a  mov     edx, esi
0x14004a19c  mov     rcx, rdi
0x14004a19f  call    ValidateSrvNetQUICActionBufferAndGetServerName
0x14004a1a4  mov     ebx, eax
0x14004a1a6  test    eax, eax
0x14004a1a8  js      loc_14004A23B
0x14004a1ae  lea     r9, [rsp+278h+HashValue]; HashValue
0x14004a1b3  xor     r8d, r8d; HashAlgorithm
0x14004a1b6  mov     dl, 1; CaseInSensitive
0x14004a1b8  lea     rcx, [rsp+278h+String]; String
0x14004a1bd  call    cs:__imp_RtlHashUnicodeString
0x14004a1c4  nop     dword ptr [rax+rax+00h]
0x14004a1c9  mov     rcx, cs:SrvNetDeviceExtension
0x14004a1d0  mov     dl, 1; Wait
0x14004a1d2  add     rcx, 348h; Resource
0x14004a1d9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004a1e0  nop     dword ptr [rax+rax+00h]
0x14004a1e5  mov     edx, [rsp+278h+HashValue]
0x14004a1e9  lea     rcx, [rsp+278h+String]; String2
0x14004a1ee  call    SrvNetQUICFindConfHelper
0x14004a1f3  mov     rbp, rax
0x14004a1f6  test    rax, rax
0x14004a1f9  jnz     short loc_14004A209
0x14004a1fb  mov     edx, esi
0x14004a1fd  mov     rcx, rdi
0x14004a200  call    SrvNetQUICAddCertHelper
0x14004a205  mov     ebx, eax
0x14004a207  jmp     short loc_14004A221
0x14004a209  mov     r8d, esi
0x14004a20c  mov     rdx, rdi
0x14004a20f  mov     rcx, rbp
0x14004a212  call    SrvNetQUICUpdateConfHelper
0x14004a217  mov     rcx, rbp; P
0x14004a21a  mov     ebx, eax
0x14004a21c  call    SrvNetQUICDereferenceCertEntry
0x14004a221  mov     rcx, cs:SrvNetDeviceExtension
0x14004a228  add     rcx, 348h; Resource
0x14004a22f  call    cs:__imp_ExReleaseResourceLite
0x14004a236  nop     dword ptr [rax+rax+00h]
0x14004a23b  mov     eax, ebx
0x14004a23d  mov     rcx, [rsp+278h+var_28]
0x14004a245  xor     rcx, rsp; StackCookie
0x14004a248  call    __security_check_cookie
0x14004a24d  mov     rbx, [rsp+278h+arg_10]
0x14004a255  add     rsp, 260h
0x14004a25c  pop     rdi
0x14004a25d  pop     rsi
0x14004a25e  pop     rbp
0x14004a25f  retn
```
