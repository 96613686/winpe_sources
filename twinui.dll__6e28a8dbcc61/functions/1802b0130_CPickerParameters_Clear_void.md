# CPickerParameters::Clear(void)

- ea: `0x1802b0130`
- end: `0x1802b0267`
- name: `?Clear@CPickerParameters@@QEAAXXZ`
- size: `311`
- prototype: `void __fastcall(CPickerParameters *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180133220`
- `0x1802af3b8`
- `0x1802af6a0`

## callees

- `0x18016101c`
- `0x1802b0130`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b020e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b01f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b020e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0250`

## pseudocode

```c
void __fastcall CPickerParameters::Clear(CPickerParameters *this)
{
  __int64 v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx
  HSTRING v5; // rcx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx

  SafeRelease<IShellItemArray>((char *)this + 32);
  SafeRelease<IShellItemArray>((char *)this + 40);
  SafeRelease<IShellItemArray>((char *)this + 48);
  SafeRelease<IShellItemArray>((char *)this + 56);
  SafeRelease<IShellItemArray>((char *)this + 64);
  SafeRelease<IShellItemArray>((char *)this + 72);
  SafeRelease<IShellItemArray>((char *)this + 80);
  SafeRelease<IShellItemArray>((char *)this + 88);
  v2 = *((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  SafeRelease<IShellItemArray>((char *)this + 96);
  WindowsDeleteString(*((HSTRING *)this + 18));
  v3 = (HSTRING)*((_QWORD *)this + 19);
  *((_QWORD *)this + 18) = 0;
  WindowsDeleteString(v3);
  v4 = (HSTRING)*((_QWORD *)this + 20);
  *((_QWORD *)this + 19) = 0;
  WindowsDeleteString(v4);
  v5 = (HSTRING)*((_QWORD *)this + 21);
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(v5);
  v6 = (HSTRING)*((_QWORD *)this + 22);
  *((_QWORD *)this + 21) = 0;
  WindowsDeleteString(v6);
  v7 = (HSTRING)*((_QWORD *)this + 15);
  *((_QWORD *)this + 22) = 0;
  WindowsDeleteString(v7);
  v8 = (HSTRING)*((_QWORD *)this + 16);
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(v8);
  v9 = (HSTRING)*((_QWORD *)this + 17);
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(v9);
  *((_QWORD *)this + 17) = 0;
}

```

## disassembly

```asm
0x1802b0130  push    rbx
0x1802b0132  sub     rsp, 20h
0x1802b0136  mov     rbx, rcx
0x1802b0139  add     rcx, 20h ; ' '
0x1802b013d  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b0142  lea     rcx, [rbx+28h]
0x1802b0146  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b014b  lea     rcx, [rbx+30h]
0x1802b014f  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b0154  lea     rcx, [rbx+38h]
0x1802b0158  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b015d  lea     rcx, [rbx+40h]
0x1802b0161  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b0166  lea     rcx, [rbx+48h]
0x1802b016a  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b016f  lea     rcx, [rbx+50h]
0x1802b0173  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b0178  lea     rcx, [rbx+58h]
0x1802b017c  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b0181  mov     rcx, [rbx+68h]
0x1802b0185  mov     qword ptr [rbx+68h], 0
0x1802b018d  test    rcx, rcx
0x1802b0190  jz      short loc_1802B019E
0x1802b0192  mov     rax, [rcx]
0x1802b0195  mov     rax, [rax+10h]
0x1802b0199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b019e  lea     rcx, [rbx+60h]
0x1802b01a2  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802b01a7  mov     rcx, [rbx+90h]; string
0x1802b01ae  call    cs:__imp_WindowsDeleteString
0x1802b01b4  mov     rcx, [rbx+98h]; string
0x1802b01bb  mov     qword ptr [rbx+90h], 0
0x1802b01c6  call    cs:__imp_WindowsDeleteString
0x1802b01cc  mov     rcx, [rbx+0A0h]; string
0x1802b01d3  mov     qword ptr [rbx+98h], 0
0x1802b01de  call    cs:__imp_WindowsDeleteString
0x1802b01e4  mov     rcx, [rbx+0A8h]; string
0x1802b01eb  mov     qword ptr [rbx+0A0h], 0
0x1802b01f6  call    cs:__imp_WindowsDeleteString
0x1802b01fc  mov     rcx, [rbx+0B0h]; string
0x1802b0203  mov     qword ptr [rbx+0A8h], 0
0x1802b020e  call    cs:__imp_WindowsDeleteString
0x1802b0214  mov     rcx, [rbx+78h]; string
0x1802b0218  mov     qword ptr [rbx+0B0h], 0
0x1802b0223  call    cs:__imp_WindowsDeleteString
0x1802b0229  mov     rcx, [rbx+80h]; string
0x1802b0230  mov     qword ptr [rbx+78h], 0
0x1802b0238  call    cs:__imp_WindowsDeleteString
0x1802b023e  mov     rcx, [rbx+88h]; string
0x1802b0245  mov     qword ptr [rbx+80h], 0
0x1802b0250  call    cs:__imp_WindowsDeleteString
0x1802b0256  mov     qword ptr [rbx+88h], 0
0x1802b0261  add     rsp, 20h
0x1802b0265  pop     rbx
0x1802b0266  retn
```
