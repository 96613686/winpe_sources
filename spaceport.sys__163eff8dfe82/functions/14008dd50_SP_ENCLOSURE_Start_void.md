# SP_ENCLOSURE::Start(void)

- ea: `0x14008dd50`
- end: `0x14008dfa9`
- name: `?Start@SP_ENCLOSURE@@QEAAJXZ`
- size: `601`
- prototype: `__int64 __fastcall(SP_ENCLOSURE *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x14008db04`
- `0x140091470`

## callees

- `0x140011970`
- `0x140019500`
- `0x140021df0`
- `0x14002ce90`
- `0x140034660`
- `0x140068110`
- `0x140068600`
- `0x14008dd50`
- `0x14008dfb0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14008dee9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14008dee9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ddc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008de2f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ddc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008de2f`
- `ntoskrnl!RtlStringFromGUID` at `0x14008ddf6`
- `ntoskrnl!RtlStringFromGUID` at `0x14008ddf6`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14008ddd7`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14008de44`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14008ddd7`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14008de44`

## pseudocode

```c
__int64 __fastcall SP_ENCLOSURE::Start(SP_ENCLOSURE *this)
{
  __int64 v2; // r9
  NTSTATUS v3; // ebx
  char *v4; // rax
  PVOID *v5; // rcx
  ULONG DeviceType; // ecx
  const char *v7; // r9
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[128]; // [rsp+50h] [rbp-B0h] BYREF

  GuidString = 0;
  memset(pszDest, 0, sizeof(pszDest));
  v2 = *((unsigned int *)this + 26);
  DestinationString = 0;
  RtlStringCbPrintfW(pszDest, 0x100u, L"\\DosDevices\\StorageEnclosure%d", v2);
  RtlInitUnicodeString(&DestinationString, pszDest);
  v3 = IoCreateSymbolicLink(&DestinationString, (PUNICODE_STRING)this + 2);
  if ( v3 >= 0 )
  {
    v3 = RtlStringFromGUID((const GUID *const)this + 1, &GuidString);
    if ( v3 >= 0 )
    {
      RtlStringCbPrintfW(pszDest, 0x100u, L"\\DosDevices\\StorageEnclosure#%wZ", &GuidString);
      RtlInitUnicodeString(&DestinationString, pszDest);
      v3 = IoCreateSymbolicLink(&DestinationString, (PUNICODE_STRING)this + 2);
      if ( v3 >= 0 )
      {
        SpAcquireResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
        if ( (PVOID)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 28) == (char *)WPP_MAIN_CB.DeviceExtension + 224 )
          SP_WORKITEM::Insert(
            (char *)WPP_MAIN_CB.DeviceExtension + 1616,
            0,
            1000 * *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 140),
            0);
        v4 = (char *)WPP_MAIN_CB.DeviceExtension + 224;
        v5 = (PVOID *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 29);
        if ( *v5 != (char *)WPP_MAIN_CB.DeviceExtension + 224 )
          __fastfail(3u);
        *((_QWORD *)this + 1) = v5;
        *(_QWORD *)this = v4;
        *v5 = this;
        *((_QWORD *)v4 + 1) = this;
        SP_ENCLOSURE::Refresh(this);
        SpReleaseResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
      }
    }
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( v3 >= 0 || v3 == -2147483643 || v3 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v7 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v7 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_fba83d071e923739d2c76d79c9d01cab_Traceguids,
      (_DWORD)v7,
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14008dd50  mov     [rsp-8+arg_8], rbx
0x14008dd55  mov     [rsp-8+arg_10], rsi
0x14008dd5a  push    rbp
0x14008dd5b  push    rdi
0x14008dd5c  push    r14
0x14008dd5e  lea     rbp, [rsp-60h]
0x14008dd63  sub     rsp, 160h
0x14008dd6a  mov     rax, cs:__security_cookie
0x14008dd71  xor     rax, rsp
0x14008dd74  mov     [rbp+70h+var_20], rax
0x14008dd78  mov     rdi, rcx
0x14008dd7b  xorps   xmm0, xmm0
0x14008dd7e  mov     r14d, 100h
0x14008dd84  lea     rcx, [rsp+170h+pszDest]; void *
0x14008dd89  mov     r8d, r14d; Size
0x14008dd8c  xor     edx, edx; Val
0x14008dd8e  movups  xmmword ptr [rsp+170h+GuidString.Length], xmm0
0x14008dd93  call    memset
0x14008dd98  mov     r9d, [rdi+68h]
0x14008dd9c  lea     r8, aDosdevicesStor; "\\DosDevices\\StorageEnclosure%d"
0x14008dda3  xorps   xmm0, xmm0
0x14008dda6  lea     rcx, [rsp+170h+pszDest]; pszDest
0x14008ddab  mov     edx, r14d; cbDest
0x14008ddae  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x14008ddb3  call    RtlStringCbPrintfW
0x14008ddb8  lea     rdx, [rsp+170h+pszDest]; SourceString
0x14008ddbd  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x14008ddc2  call    cs:__imp_RtlInitUnicodeString
0x14008ddc9  nop     dword ptr [rax+rax+00h]
0x14008ddce  lea     rdx, [rdi+20h]; DeviceName
0x14008ddd2  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x14008ddd7  call    cs:__imp_IoCreateSymbolicLink
0x14008ddde  nop     dword ptr [rax+rax+00h]
0x14008dde3  mov     ebx, eax
0x14008dde5  test    eax, eax
0x14008dde7  js      loc_14008DEDC
0x14008dded  lea     rcx, [rdi+10h]; Guid
0x14008ddf1  lea     rdx, [rsp+170h+GuidString]; GuidString
0x14008ddf6  call    cs:__imp_RtlStringFromGUID
0x14008ddfd  nop     dword ptr [rax+rax+00h]
0x14008de02  mov     ebx, eax
0x14008de04  test    eax, eax
0x14008de06  js      loc_14008DEDC
0x14008de0c  lea     r9, [rsp+170h+GuidString]
0x14008de11  mov     edx, r14d; cbDest
0x14008de14  lea     r8, aDosdevicesStor_0; "\\DosDevices\\StorageEnclosure#%wZ"
0x14008de1b  lea     rcx, [rsp+170h+pszDest]; pszDest
0x14008de20  call    RtlStringCbPrintfW
0x14008de25  lea     rdx, [rsp+170h+pszDest]; SourceString
0x14008de2a  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x14008de2f  call    cs:__imp_RtlInitUnicodeString
0x14008de36  nop     dword ptr [rax+rax+00h]
0x14008de3b  lea     rdx, [rdi+20h]; DeviceName
0x14008de3f  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x14008de44  call    cs:__imp_IoCreateSymbolicLink
0x14008de4b  nop     dword ptr [rax+rax+00h]
0x14008de50  mov     ebx, eax
0x14008de52  test    eax, eax
0x14008de54  js      loc_14008DEDC
0x14008de5a  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14008de61  add     rcx, 60h ; '`'; Resource
0x14008de65  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x14008de6a  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14008de71  lea     rax, [rcx+0E0h]
0x14008de78  cmp     [rax], rax
0x14008de7b  jnz     short loc_14008DE99
0x14008de7d  imul    r8d, [rcx+230h], 3E8h; unsigned int
0x14008de88  xor     r9d, r9d; unsigned __int8
0x14008de8b  add     rcx, 650h; Context
0x14008de92  xor     edx, edx; struct _LIST_ENTRY *
0x14008de94  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14008de99  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14008dea0  add     rax, 0E0h
0x14008dea6  mov     rcx, [rax+8]
0x14008deaa  cmp     [rcx], rax
0x14008dead  jz      short loc_14008DEB6
0x14008deaf  mov     ecx, 3
0x14008deb4  int     29h; Win8: RtlFailFast(ecx)
0x14008deb6  mov     [rdi+8], rcx
0x14008deba  mov     [rdi], rax
0x14008debd  mov     [rcx], rdi
0x14008dec0  mov     rcx, rdi; this
0x14008dec3  mov     [rax+8], rdi
0x14008dec7  call    ?Refresh@SP_ENCLOSURE@@QEAAXXZ; SP_ENCLOSURE::Refresh(void)
0x14008decc  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14008ded3  add     rcx, 60h ; '`'; Resource
0x14008ded7  call    ?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceExclusive(_ERESOURCE *)
0x14008dedc  cmp     [rsp+170h+GuidString.Buffer], 0
0x14008dee2  jz      short loc_14008DEF5
0x14008dee4  lea     rcx, [rsp+170h+GuidString]; UnicodeString
0x14008dee9  call    cs:__imp_RtlFreeUnicodeString
0x14008def0  nop     dword ptr [rax+rax+00h]
0x14008def5  test    ebx, ebx
0x14008def7  jns     short loc_14008DF28
0x14008def9  cmp     ebx, 80000005h
0x14008deff  jz      short loc_14008DF28
0x14008df01  cmp     ebx, 0C0000023h
0x14008df07  jz      short loc_14008DF28
0x14008df09  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14008df0f  cmp     ecx, 1
0x14008df12  jz      short loc_14008DF1F
0x14008df14  mov     ecx, 1
0x14008df19  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14008df1f  lea     r9, aError; "Error"
0x14008df26  jmp     short loc_14008DF45
0x14008df28  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14008df2e  cmp     ecx, 3
0x14008df31  jz      short loc_14008DF3E
0x14008df33  mov     ecx, 3
0x14008df38  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14008df3e  lea     r9, aExit; "Exit "
0x14008df45  mov     r10, cs:WPP_GLOBAL_Control
0x14008df4c  lea     rax, WPP_GLOBAL_Control
0x14008df53  cmp     r10, rax
0x14008df56  jz      short loc_14008DF82
0x14008df58  mov     eax, [r10+2Ch]
0x14008df5c  test    al, 1
0x14008df5e  jz      short loc_14008DF82
0x14008df60  movzx   eax, byte ptr [r10+29h]
0x14008df65  cmp     eax, ecx
0x14008df67  jb      short loc_14008DF82
0x14008df69  mov     rcx, [r10+18h]
0x14008df6d  lea     r8, WPP_fba83d071e923739d2c76d79c9d01cab_Traceguids
0x14008df74  mov     edx, 0Fh
0x14008df79  mov     [rsp+170h+var_150], ebx
0x14008df7d  call    WPP_SF_sd
0x14008df82  mov     eax, ebx
0x14008df84  mov     rcx, [rbp+70h+var_20]
0x14008df88  xor     rcx, rsp; StackCookie
0x14008df8b  call    __security_check_cookie
0x14008df90  lea     r11, [rsp+170h+var_10]
0x14008df98  mov     rbx, [r11+28h]
0x14008df9c  mov     rsi, [r11+30h]
0x14008dfa0  mov     rsp, r11
0x14008dfa3  pop     r14
0x14008dfa5  pop     rdi
0x14008dfa6  pop     rbp
0x14008dfa7  retn
```
