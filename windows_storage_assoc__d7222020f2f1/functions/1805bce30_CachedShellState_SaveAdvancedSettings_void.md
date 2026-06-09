# CachedShellState::SaveAdvancedSettings(void)

- ea: `0x1805bce30`
- end: `0x1805bd228`
- name: `?SaveAdvancedSettings@CachedShellState@@QEAAXXZ`
- size: `1016`
- prototype: `void __fastcall(CachedShellState *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049d70`
- `0x1805bcde0`

## callees

- `0x1803b1f60`
- `0x1805bce30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcec6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bceff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcf39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcf75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcfb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcfed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd029`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd065`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd0a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd0dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd113`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd14c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd185`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd1be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd1f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcec6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bceff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcf39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcf75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcfb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bcfed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd029`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd065`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd0a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd0dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd113`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd14c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd185`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd1be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805bd1f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805bd206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805bd206`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1805bce71`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1805bce71`

## string_xrefs

- `0x1805bced6`: `ShowCompColor`
- `0x1805bcf49`: `DontPrettyPath`

## pseudocode

```c
void __fastcall CachedShellState::SaveAdvancedSettings(CachedShellState *this)
{
  HKEY v2; // rdi
  __int64 v3; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF

  if ( this != (CachedShellState *)&CachedShellState::s_cssDefault )
  {
    v2 = (HKEY)SHGetShellKeyEx(1, L"Advanced");
    if ( v2 )
    {
      v3 = *((_QWORD *)this + 1);
      *(_DWORD *)Data = 0;
      *(_DWORD *)Data = 2 - ((*(_BYTE *)(v3 + 4) & 1) != 0);
      RegSetValueExW(v2, L"Hidden", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x10u) >> 4;
      RegSetValueExW(v2, L"ShowCompColor", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (unsigned __int8)(~(unsigned __int8)*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 2) >> 1;
      RegSetValueExW(v2, L"HideFileExt", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x100u) >> 8;
      RegSetValueExW(v2, L"DontPrettyPath", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x800u) >> 11;
      RegSetValueExW(v2, L"ShowInfoTip", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x1000u) >> 12;
      RegSetValueExW(v2, L"HideIcons", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x400u) >> 10;
      RegSetValueExW(v2, L"MapNetDrvBtn", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x2000u) >> 13;
      RegSetValueExW(v2, L"WebView", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x4000u) >> 14;
      RegSetValueExW(v2, L"Filter", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x8000u) >> 15;
      RegSetValueExW(v2, L"ShowSuperHidden", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 1;
      RegSetValueExW(v2, L"SeparateProcess", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 8u) >> 3;
      RegSetValueExW(v2, L"AutoCheckSelect", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 0x10u) >> 4;
      RegSetValueExW(v2, L"IconsOnly", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 0x20u) >> 5;
      RegSetValueExW(v2, L"ShowTypeOverlay", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 0x40u) >> 6;
      RegSetValueExW(v2, L"ShowStatusBar", 0, 4u, Data, 4u);
      RegCloseKey(v2);
    }
  }
}

```

## disassembly

```asm
0x1805bce30  push    rbp
0x1805bce32  push    rbx
0x1805bce33  push    rsi
0x1805bce34  push    rdi
0x1805bce35  mov     rbp, rsp
0x1805bce38  sub     rsp, 48h
0x1805bce3c  mov     rax, cs:__security_cookie
0x1805bce43  xor     rax, rsp
0x1805bce46  mov     [rbp+var_10], rax
0x1805bce4a  lea     rax, ?s_cssDefault@CachedShellState@@0V1@A; CachedShellState CachedShellState::s_cssDefault
0x1805bce51  mov     rbx, rcx
0x1805bce54  cmp     rcx, rax
0x1805bce57  jz      loc_1805BD212
0x1805bce5d  mov     r9d, 2
0x1805bce63  lea     rdx, aAdvanced; "Advanced"
0x1805bce6a  lea     r8d, [r9-1]
0x1805bce6e  mov     ecx, r8d
0x1805bce71  call    cs:__imp_SHGetShellKeyEx
0x1805bce78  nop     dword ptr [rax+rax+00h]
0x1805bce7d  mov     rdi, rax
0x1805bce80  test    rax, rax
0x1805bce83  jz      loc_1805BD212
0x1805bce89  mov     rcx, [rbx+8]
0x1805bce8d  lea     rax, [rbp+Data]
0x1805bce91  mov     dword ptr [rbp+Data], 0
0x1805bce98  mov     esi, 4
0x1805bce9d  mov     [rsp+48h+cbData], esi; cbData
0x1805bcea1  mov     r9d, esi; dwType
0x1805bcea4  mov     [rsp+48h+lpData], rax; lpData
0x1805bcea9  mov     dl, [rcx+4]
0x1805bceac  and     dl, 1
0x1805bceaf  neg     dl
0x1805bceb1  lea     rdx, aHidden; "Hidden"
0x1805bceb8  sbb     ecx, ecx
0x1805bceba  xor     r8d, r8d; Reserved
0x1805bcebd  add     ecx, 2
0x1805bcec0  mov     dword ptr [rbp+Data], ecx
0x1805bcec3  mov     rcx, rdi; hKey
0x1805bcec6  call    cs:__imp_RegSetValueExW
0x1805bcecd  nop     dword ptr [rax+rax+00h]
0x1805bced2  mov     rax, [rbx+8]
0x1805bced6  lea     rdx, aShowcompcolor; "ShowCompColor"
0x1805bcedd  mov     [rsp+48h+cbData], esi; cbData
0x1805bcee1  mov     r9d, esi; dwType
0x1805bcee4  xor     r8d, r8d; Reserved
0x1805bcee7  mov     ecx, [rax+4]
0x1805bceea  lea     rax, [rbp+Data]
0x1805bceee  and     ecx, 10h
0x1805bcef1  mov     [rsp+48h+lpData], rax; lpData
0x1805bcef6  shr     ecx, 4
0x1805bcef9  mov     dword ptr [rbp+Data], ecx
0x1805bcefc  mov     rcx, rdi; hKey
0x1805bceff  call    cs:__imp_RegSetValueExW
0x1805bcf06  nop     dword ptr [rax+rax+00h]
0x1805bcf0b  mov     rax, [rbx+8]
0x1805bcf0f  lea     rdx, aHidefileext; "HideFileExt"
0x1805bcf16  mov     [rsp+48h+cbData], esi; cbData
0x1805bcf1a  mov     r9d, esi; dwType
0x1805bcf1d  xor     r8d, r8d; Reserved
0x1805bcf20  mov     ecx, [rax+4]
0x1805bcf23  lea     rax, [rbp+Data]
0x1805bcf27  not     ecx
0x1805bcf29  mov     [rsp+48h+lpData], rax; lpData
0x1805bcf2e  and     ecx, 2
0x1805bcf31  shr     ecx, 1
0x1805bcf33  mov     dword ptr [rbp+Data], ecx
0x1805bcf36  mov     rcx, rdi; hKey
0x1805bcf39  call    cs:__imp_RegSetValueExW
0x1805bcf40  nop     dword ptr [rax+rax+00h]
0x1805bcf45  mov     rax, [rbx+8]
0x1805bcf49  lea     rdx, aDontprettypath; "DontPrettyPath"
0x1805bcf50  mov     [rsp+48h+cbData], esi; cbData
0x1805bcf54  mov     r9d, esi; dwType
0x1805bcf57  xor     r8d, r8d; Reserved
0x1805bcf5a  mov     ecx, [rax+4]
0x1805bcf5d  lea     rax, [rbp+Data]
0x1805bcf61  and     ecx, 100h
0x1805bcf67  mov     [rsp+48h+lpData], rax; lpData
0x1805bcf6c  shr     ecx, 8
0x1805bcf6f  mov     dword ptr [rbp+Data], ecx
0x1805bcf72  mov     rcx, rdi; hKey
0x1805bcf75  call    cs:__imp_RegSetValueExW
0x1805bcf7c  nop     dword ptr [rax+rax+00h]
0x1805bcf81  mov     rax, [rbx+8]
0x1805bcf85  lea     rdx, aShowinfotip; "ShowInfoTip"
0x1805bcf8c  mov     [rsp+48h+cbData], esi; cbData
0x1805bcf90  mov     r9d, esi; dwType
0x1805bcf93  xor     r8d, r8d; Reserved
0x1805bcf96  mov     ecx, [rax+4]
0x1805bcf99  lea     rax, [rbp+Data]
0x1805bcf9d  and     ecx, 800h
0x1805bcfa3  mov     [rsp+48h+lpData], rax; lpData
0x1805bcfa8  shr     ecx, 0Bh
0x1805bcfab  mov     dword ptr [rbp+Data], ecx
0x1805bcfae  mov     rcx, rdi; hKey
0x1805bcfb1  call    cs:__imp_RegSetValueExW
0x1805bcfb8  nop     dword ptr [rax+rax+00h]
0x1805bcfbd  mov     rax, [rbx+8]
0x1805bcfc1  lea     rdx, aHideicons; "HideIcons"
0x1805bcfc8  mov     [rsp+48h+cbData], esi; cbData
0x1805bcfcc  mov     r9d, esi; dwType
0x1805bcfcf  mov     ecx, [rax+4]
0x1805bcfd2  lea     rax, [rbp+Data]
0x1805bcfd6  and     ecx, 1000h
0x1805bcfdc  mov     [rsp+48h+lpData], rax; lpData
0x1805bcfe1  shr     ecx, 0Ch
0x1805bcfe4  mov     dword ptr [rbp+Data], ecx
0x1805bcfe7  xor     r8d, r8d; Reserved
0x1805bcfea  mov     rcx, rdi; hKey
0x1805bcfed  call    cs:__imp_RegSetValueExW
0x1805bcff4  nop     dword ptr [rax+rax+00h]
0x1805bcff9  mov     rax, [rbx+8]
0x1805bcffd  lea     rdx, aMapnetdrvbtn; "MapNetDrvBtn"
0x1805bd004  mov     [rsp+48h+cbData], esi; cbData
0x1805bd008  mov     r9d, esi; dwType
0x1805bd00b  xor     r8d, r8d; Reserved
0x1805bd00e  mov     ecx, [rax+4]
0x1805bd011  lea     rax, [rbp+Data]
0x1805bd015  and     ecx, 400h
0x1805bd01b  mov     [rsp+48h+lpData], rax; lpData
0x1805bd020  shr     ecx, 0Ah
0x1805bd023  mov     dword ptr [rbp+Data], ecx
0x1805bd026  mov     rcx, rdi; hKey
0x1805bd029  call    cs:__imp_RegSetValueExW
0x1805bd030  nop     dword ptr [rax+rax+00h]
0x1805bd035  mov     rax, [rbx+8]
0x1805bd039  lea     rdx, aWebview; "WebView"
0x1805bd040  mov     [rsp+48h+cbData], esi; cbData
0x1805bd044  mov     r9d, esi; dwType
0x1805bd047  xor     r8d, r8d; Reserved
0x1805bd04a  mov     ecx, [rax+4]
0x1805bd04d  lea     rax, [rbp+Data]
0x1805bd051  and     ecx, 2000h
0x1805bd057  mov     [rsp+48h+lpData], rax; lpData
0x1805bd05c  shr     ecx, 0Dh
0x1805bd05f  mov     dword ptr [rbp+Data], ecx
0x1805bd062  mov     rcx, rdi; hKey
0x1805bd065  call    cs:__imp_RegSetValueExW
0x1805bd06c  nop     dword ptr [rax+rax+00h]
0x1805bd071  mov     rax, [rbx+8]
0x1805bd075  lea     rdx, aFilter; "Filter"
0x1805bd07c  mov     [rsp+48h+cbData], esi; cbData
0x1805bd080  mov     r9d, esi; dwType
0x1805bd083  xor     r8d, r8d; Reserved
0x1805bd086  mov     ecx, [rax+4]
0x1805bd089  lea     rax, [rbp+Data]
0x1805bd08d  and     ecx, 4000h
0x1805bd093  mov     [rsp+48h+lpData], rax; lpData
0x1805bd098  shr     ecx, 0Eh
0x1805bd09b  mov     dword ptr [rbp+Data], ecx
0x1805bd09e  mov     rcx, rdi; hKey
0x1805bd0a1  call    cs:__imp_RegSetValueExW
0x1805bd0a8  nop     dword ptr [rax+rax+00h]
0x1805bd0ad  mov     rax, [rbx+8]
0x1805bd0b1  lea     rdx, aShowsuperhidde_0; "ShowSuperHidden"
0x1805bd0b8  mov     [rsp+48h+cbData], esi; cbData
0x1805bd0bc  mov     r9d, esi; dwType
0x1805bd0bf  xor     r8d, r8d; Reserved
0x1805bd0c2  mov     ecx, [rax+4]
0x1805bd0c5  lea     rax, [rbp+Data]
0x1805bd0c9  and     ecx, 8000h
0x1805bd0cf  mov     [rsp+48h+lpData], rax; lpData
0x1805bd0d4  shr     ecx, 0Fh
0x1805bd0d7  mov     dword ptr [rbp+Data], ecx
0x1805bd0da  mov     rcx, rdi; hKey
0x1805bd0dd  call    cs:__imp_RegSetValueExW
0x1805bd0e4  nop     dword ptr [rax+rax+00h]
0x1805bd0e9  mov     rax, [rbx+8]
0x1805bd0ed  lea     rdx, aSeparateproces; "SeparateProcess"
0x1805bd0f4  mov     [rsp+48h+cbData], esi; cbData
0x1805bd0f8  mov     r9d, esi; dwType
0x1805bd0fb  xor     r8d, r8d; Reserved
0x1805bd0fe  mov     ecx, [rax+20h]
0x1805bd101  lea     rax, [rbp+Data]
0x1805bd105  and     ecx, 1
0x1805bd108  mov     [rsp+48h+lpData], rax; lpData
0x1805bd10d  mov     dword ptr [rbp+Data], ecx
0x1805bd110  mov     rcx, rdi; hKey
0x1805bd113  call    cs:__imp_RegSetValueExW
0x1805bd11a  nop     dword ptr [rax+rax+00h]
0x1805bd11f  mov     rax, [rbx+8]
0x1805bd123  lea     rdx, aAutocheckselec; "AutoCheckSelect"
0x1805bd12a  mov     [rsp+48h+cbData], esi; cbData
0x1805bd12e  mov     r9d, esi; dwType
0x1805bd131  xor     r8d, r8d; Reserved
0x1805bd134  mov     ecx, [rax+20h]
0x1805bd137  lea     rax, [rbp+Data]
0x1805bd13b  and     ecx, 8
0x1805bd13e  mov     [rsp+48h+lpData], rax; lpData
0x1805bd143  shr     ecx, 3
0x1805bd146  mov     dword ptr [rbp+Data], ecx
0x1805bd149  mov     rcx, rdi; hKey
0x1805bd14c  call    cs:__imp_RegSetValueExW
0x1805bd153  nop     dword ptr [rax+rax+00h]
0x1805bd158  mov     rax, [rbx+8]
0x1805bd15c  mov     ecx, [rax+20h]
0x1805bd15f  and     ecx, 10h
0x1805bd162  mov     [rsp+48h+cbData], esi; cbData
0x1805bd166  shr     ecx, 4
0x1805bd169  lea     rax, [rbp+Data]
0x1805bd16d  mov     dword ptr [rbp+Data], ecx
0x1805bd170  lea     rdx, aIconsonly; "IconsOnly"
0x1805bd177  mov     rcx, rdi; hKey
0x1805bd17a  mov     [rsp+48h+lpData], rax; lpData
0x1805bd17f  mov     r9d, esi; dwType
0x1805bd182  xor     r8d, r8d; Reserved
0x1805bd185  call    cs:__imp_RegSetValueExW
0x1805bd18c  nop     dword ptr [rax+rax+00h]
0x1805bd191  mov     rax, [rbx+8]
0x1805bd195  lea     rdx, aShowtypeoverla; "ShowTypeOverlay"
0x1805bd19c  mov     [rsp+48h+cbData], esi; cbData
0x1805bd1a0  mov     r9d, esi; dwType
0x1805bd1a3  xor     r8d, r8d; Reserved
0x1805bd1a6  mov     ecx, [rax+20h]
0x1805bd1a9  lea     rax, [rbp+Data]
0x1805bd1ad  and     ecx, 20h
0x1805bd1b0  mov     [rsp+48h+lpData], rax; lpData
0x1805bd1b5  shr     ecx, 5
0x1805bd1b8  mov     dword ptr [rbp+Data], ecx
0x1805bd1bb  mov     rcx, rdi; hKey
0x1805bd1be  call    cs:__imp_RegSetValueExW
0x1805bd1c5  nop     dword ptr [rax+rax+00h]
0x1805bd1ca  mov     rax, [rbx+8]
0x1805bd1ce  lea     rdx, aShowstatusbar; "ShowStatusBar"
0x1805bd1d5  mov     [rsp+48h+cbData], esi; cbData
0x1805bd1d9  mov     r9d, esi; dwType
0x1805bd1dc  xor     r8d, r8d; Reserved
0x1805bd1df  mov     ecx, [rax+20h]
0x1805bd1e2  lea     rax, [rbp+Data]
0x1805bd1e6  and     ecx, 40h
0x1805bd1e9  mov     [rsp+48h+lpData], rax; lpData
0x1805bd1ee  shr     ecx, 6
0x1805bd1f1  mov     dword ptr [rbp+Data], ecx
0x1805bd1f4  mov     rcx, rdi; hKey
0x1805bd1f7  call    cs:__imp_RegSetValueExW
0x1805bd1fe  nop     dword ptr [rax+rax+00h]
0x1805bd203  mov     rcx, rdi; hKey
0x1805bd206  call    cs:__imp_RegCloseKey
0x1805bd20d  nop     dword ptr [rax+rax+00h]
0x1805bd212  mov     rcx, [rbp+var_10]
0x1805bd216  xor     rcx, rsp; StackCookie
0x1805bd219  call    __security_check_cookie
0x1805bd21e  add     rsp, 48h
0x1805bd222  pop     rdi
0x1805bd223  pop     rsi
0x1805bd224  pop     rbx
0x1805bd225  pop     rbp
0x1805bd226  retn
```
