# winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupFormats(void)

- ea: `0x1800f5cd4`
- end: `0x1800f5e53`
- name: `?SetupFormats@VirtualMicrophoneDevice@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXXZ`
- size: `383`
- prototype: `void __fastcall(winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800f5a98`

## callees

- `0x1800f5e5c`
- `0x18015cb00`
- `0x1802e4990`

## import_xrefs

- `Apx01000!imp_ApxDataFormatListAddDataFormat` at `0x1800f5e11`
- `Apx01000!imp_ApxDataFormatListAddDataFormat` at `0x1800f5e11`
- `Apx01000!imp_ApxDataFormatCreate` at `0x1800f5ddb`
- `Apx01000!imp_ApxDataFormatCreate` at `0x1800f5ddb`
- `Apx01000!imp_ApxDataFormatListCreate` at `0x1800f5d14`
- `Apx01000!imp_ApxDataFormatListCreate` at `0x1800f5d14`

## string_xrefs

- `0x1800f5d2a`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f5df1`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f5e27`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f5d1e`: `ApxDataFormatListCreate failed`
- `0x1800f5de5`: `ApxDataFormatCreate failed`

## pseudocode

```c
void __fastcall winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupFormats(
        winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *this)
{
  _QWORD *v1; // rdi
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  const char *v6; // [rsp+28h] [rbp-D8h]
  const char *v7; // [rsp+28h] [rbp-D8h]
  const char *v8; // [rsp+28h] [rbp-D8h]
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-C8h] BYREF
  WAVEFORMATEXTENSIBLE v11; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v12[2]; // [rsp+80h] [rbp-80h] BYREF
  int v13; // [rsp+90h] [rbp-70h]
  int v14; // [rsp+94h] [rbp-6Ch]
  int v15; // [rsp+98h] [rbp-68h]
  int v16; // [rsp+9Ch] [rbp-64h]
  GUID SubFormat; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+B0h] [rbp-50h]
  int v19; // [rsp+B4h] [rbp-4Ch]
  int v20; // [rsp+B8h] [rbp-48h]
  int v21; // [rsp+BCh] [rbp-44h]
  __int128 v22; // [rsp+C0h] [rbp-40h]
  __int128 v23; // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+E0h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  v1 = (_QWORD *)((char *)this + 232);
  v9 = 8;
  v3 = imp_ApxDataFormatListCreate(0, 0, &v9, (char *)this + 232);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1CE,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v3,
    (int)"ApxDataFormatListCreate failed",
    v6);
  winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::CreateWaveFormat(this, &v11);
  v12[0] = 104;
  SubFormat = v11.SubFormat;
  v12[1] = 0;
  v24 = *(_OWORD *)&_mm_unpackhi_pd((__m128d)SubFormat, (__m128d)SubFormat);
  v13 = 1935963489;
  v14 = 0x100000;
  v15 = -1442840448;
  v16 = 1905997824;
  v18 = 89694081;
  v19 = 298763094;
  v20 = -1442840129;
  v21 = 1515803904;
  v22 = *(_OWORD *)&v11.Format.wFormatTag;
  v23 = *(_OWORD *)&v11.Format.cbSize;
  v10[1] = 0;
  v10[0] = 24;
  v10[2] = v12;
  v4 = imp_ApxDataFormatCreate(0, 0, v10, (char *)this + 240);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1E7,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v4,
    (int)"ApxDataFormatCreate failed",
    v7);
  v5 = imp_ApxDataFormatListAddDataFormat(0, *v1, *((_QWORD *)this + 30));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1EB,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v5,
    (int)"ApxDataFormatListAddDataFormat failed",
    v8);
}

```

## disassembly

```asm
0x1800f5cd4  push    rbp
0x1800f5cd6  push    rbx
0x1800f5cd7  push    rsi
0x1800f5cd8  push    rdi
0x1800f5cd9  lea     rbp, [rsp-8]
0x1800f5cde  sub     rsp, 108h
0x1800f5ce5  mov     rax, cs:__security_cookie
0x1800f5cec  xor     rax, rsp
0x1800f5cef  mov     [rbp+20h+var_30], rax
0x1800f5cf3  lea     rdi, [rcx+0E8h]
0x1800f5cfa  mov     [rsp+120h+var_F0], 8
0x1800f5d03  mov     rbx, rcx
0x1800f5d06  lea     r8, [rsp+120h+var_F0]
0x1800f5d0b  mov     r9, rdi
0x1800f5d0e  xor     edx, edx
0x1800f5d10  xor     ecx, ecx
0x1800f5d12  xor     esi, esi
0x1800f5d14  call    cs:__imp_imp_ApxDataFormatListCreate
0x1800f5d1a  mov     rcx, [rbp+28h]; this
0x1800f5d1e  lea     rdx, aApxdataformatl_0; "ApxDataFormatListCreate failed"
0x1800f5d25  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1800f5d2a  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f5d31  mov     edx, 1CEh; void *
0x1800f5d36  mov     r9d, eax; char *
0x1800f5d39  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f5d3e  lea     rdx, [rsp+120h+var_D0]; retstr
0x1800f5d43  mov     rcx, rbx; this
0x1800f5d46  call    ?CreateWaveFormat@VirtualMicrophoneDevice@implementation@Devices@Media@WindowsUdk@winrt@@AEAA?AUWAVEFORMATEXTENSIBLE@@XZ; winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::CreateWaveFormat(void)
0x1800f5d4b  movups  xmm2, xmmword ptr [rsp+120h+var_D0.SubFormat.Data1]
0x1800f5d50  lea     rax, [rbp+20h+var_A0]
0x1800f5d54  xor     edx, edx
0x1800f5d56  movups  xmm0, xmmword ptr [rsp+120h+var_D0.Format.wFormatTag]
0x1800f5d5b  lea     r9, [rbx+0F0h]
0x1800f5d62  xor     ecx, ecx
0x1800f5d64  movups  xmm1, xmmword ptr [rsp+60h]
0x1800f5d69  lea     r8, [rsp+120h+var_E8]
0x1800f5d6e  mov     [rbp+20h+var_A0], 68h ; 'h'
0x1800f5d76  movdqu  [rbp+20h+var_80], xmm2
0x1800f5d7b  mov     [rbp+20h+var_98], rsi
0x1800f5d7f  unpckhpd xmm2, xmm2
0x1800f5d83  movsd   [rbp+20h+var_40], xmm2
0x1800f5d88  mov     [rbp+20h+var_90], 73647561h
0x1800f5d8f  mov     [rbp+20h+var_8C], 100000h
0x1800f5d96  mov     [rbp+20h+var_88], 0AA000080h
0x1800f5d9d  mov     [rbp+20h+var_84], 719B3800h
0x1800f5da4  mov     [rbp+20h+var_70], 5589F81h
0x1800f5dab  mov     [rbp+20h+var_6C], 11CEC356h
0x1800f5db2  mov     [rbp+20h+var_68], 0AA0001BFh
0x1800f5db9  mov     [rbp+20h+var_64], 5A595500h
0x1800f5dc0  movaps  [rbp+20h+var_60], xmm0
0x1800f5dc4  movaps  [rbp+20h+var_50], xmm1
0x1800f5dc8  mov     [rsp+120h+var_E0], rsi
0x1800f5dcd  mov     [rsp+120h+var_E8], 18h
0x1800f5dd6  mov     [rsp+120h+var_D8], rax
0x1800f5ddb  call    cs:__imp_imp_ApxDataFormatCreate
0x1800f5de1  mov     rcx, [rbp+28h]; this
0x1800f5de5  lea     rdx, aApxdataformatc; "ApxDataFormatCreate failed"
0x1800f5dec  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1800f5df1  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f5df8  mov     edx, 1E7h; void *
0x1800f5dfd  mov     r9d, eax; char *
0x1800f5e00  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f5e05  mov     r8, [rbx+0F0h]
0x1800f5e0c  xor     ecx, ecx
0x1800f5e0e  mov     rdx, [rdi]
0x1800f5e11  call    cs:__imp_imp_ApxDataFormatListAddDataFormat
0x1800f5e17  mov     rcx, [rbp+28h]; this
0x1800f5e1b  lea     rdx, aApxdataformatl; "ApxDataFormatListAddDataFormat failed"
0x1800f5e22  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1800f5e27  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f5e2e  mov     edx, 1EBh; void *
0x1800f5e33  mov     r9d, eax; char *
0x1800f5e36  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f5e3b  mov     rcx, [rbp+20h+var_30]
0x1800f5e3f  xor     rcx, rsp; StackCookie
0x1800f5e42  call    __security_check_cookie
0x1800f5e47  add     rsp, 108h
0x1800f5e4e  pop     rdi
0x1800f5e4f  pop     rsi
0x1800f5e50  pop     rbx
0x1800f5e51  pop     rbp
0x1800f5e52  retn
```
