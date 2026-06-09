# CWallpaperCore::_InitializeIntervalCombobox(void)

- ea: `0x180040d48`
- end: `0x180040f81`
- name: `?_InitializeIntervalCombobox@CWallpaperCore@@AEAAJXZ`
- size: `569`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003bacc`

## callees

- `0x180002280`
- `0x180040d48`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180040ebb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180040ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f2c`
- `USER32!SendMessageW` at `0x180040f0b`
- `USER32!SendMessageW` at `0x180040f0b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180040e86`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180040e86`
- `DUI70!StrToID` at `0x180040e74`
- `DUI70!StrToID` at `0x180040e74`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x180040ed2`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x180040ed2`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180040f55`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180040f55`

## string_xrefs

- `0x180040d75`: `ComboBox_Interval`

## pseudocode

```c
signed int __fastcall CWallpaperCore::_InitializeIntervalCombobox(CWallpaperCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned __int16 v2; // ax
  struct DirectUI::Element *Descendent; // rax
  int v4; // ebx
  DirectUI::Combobox *v5; // r14
  unsigned int i; // edi
  int v7; // eax
  WPARAM v8; // rsi
  HWND v9; // rax
  unsigned int v10; // r15d
  signed int result; // eax
  LPARAM lParam; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+28h] [rbp-D8h]
  int v14; // [rsp+2Ch] [rbp-D4h]
  int v15; // [rsp+30h] [rbp-D0h]
  int v16; // [rsp+34h] [rbp-CCh]
  int v17; // [rsp+38h] [rbp-C8h]
  int v18; // [rsp+3Ch] [rbp-C4h]
  int v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+44h] [rbp-BCh]
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+4Ch] [rbp-B4h]
  int v23; // [rsp+50h] [rbp-B0h]
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  int v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+6Ch] [rbp-94h]
  int v31; // [rsp+70h] [rbp-90h]
  int v32; // [rsp+74h] [rbp-8Ch]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  int v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+84h] [rbp-7Ch]
  int v37; // [rsp+88h] [rbp-78h]
  int v38; // [rsp+8Ch] [rbp-74h]
  int v39; // [rsp+90h] [rbp-70h]
  int v40; // [rsp+94h] [rbp-6Ch]
  int v41; // [rsp+98h] [rbp-68h]
  int v42; // [rsp+9Ch] [rbp-64h]
  WCHAR Buffer[512]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 4);
  lParam = 0x1FD00002710LL;
  v13 = 30000;
  v14 = 510;
  v15 = 60000;
  v16 = 511;
  v17 = 180000;
  v18 = 512;
  v19 = 300000;
  v20 = 513;
  v21 = 600000;
  v22 = 514;
  v23 = 900000;
  v24 = 515;
  v25 = 1200000;
  v26 = 516;
  v27 = 1800000;
  v28 = 517;
  v29 = 3600000;
  v30 = 518;
  v31 = 7200000;
  v32 = 519;
  v33 = 10800000;
  v34 = 520;
  v35 = 14400000;
  v36 = 521;
  v37 = 21600000;
  v38 = 522;
  v39 = 43200000;
  v40 = 523;
  v41 = 86400000;
  v42 = 524;
  v2 = StrToID(L"ComboBox_Interval");
  Descendent = DirectUI::Element::FindDescendent(v1, v2);
  v4 = 0;
  v5 = Descendent;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x10 )
      return DirectUI::Combobox::SetSelection(v5, v4);
    if ( !LoadStringW(g_hinst, *((_DWORD *)&lParam + 2 * (int)i + 1), Buffer, 512) )
      break;
    v7 = DirectUI::Combobox::AddString(v5, Buffer);
    v8 = v7;
    if ( v7 == -1 )
      break;
    v9 = (HWND)(*(__int64 (__fastcall **)(DirectUI::Combobox *))(*(_QWORD *)v5 + 360LL))(v5);
    v10 = *((_DWORD *)&lParam + 2 * (int)i);
    if ( (int)SendMessageW(v9, 0x151u, v8, v10) < 0 )
      break;
    if ( v10 == 1800000 )
      v4 = v8;
  }
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x180040d48  push    rbp
0x180040d4a  push    rbx
0x180040d4b  push    rsi
0x180040d4c  push    rdi
0x180040d4d  push    r14
0x180040d4f  push    r15
0x180040d51  lea     rbp, [rsp-3B8h]
0x180040d59  sub     rsp, 4B8h
0x180040d60  mov     rax, cs:__security_cookie
0x180040d67  xor     rax, rsp
0x180040d6a  mov     [rbp+3E0h+var_40], rax
0x180040d71  mov     rbx, [rcx+20h]
0x180040d75  lea     rcx, aComboboxInterv; "ComboBox_Interval"
0x180040d7c  mov     dword ptr [rsp+4E0h+lParam], 2710h
0x180040d84  mov     dword ptr [rsp+4E0h+lParam+4], 1FDh
0x180040d8c  mov     [rsp+4E0h+var_4B8], 7530h
0x180040d94  mov     [rsp+4E0h+var_4B4], 1FEh
0x180040d9c  mov     [rsp+4E0h+var_4B0], 0EA60h
0x180040da4  mov     [rsp+4E0h+var_4AC], 1FFh
0x180040dac  mov     [rsp+4E0h+var_4A8], 2BF20h
0x180040db4  mov     [rsp+4E0h+var_4A4], 200h
0x180040dbc  mov     [rsp+4E0h+var_4A0], 493E0h
0x180040dc4  mov     [rsp+4E0h+var_49C], 201h
0x180040dcc  mov     [rsp+4E0h+var_498], 927C0h
0x180040dd4  mov     [rsp+4E0h+var_494], 202h
0x180040ddc  mov     [rsp+4E0h+var_490], 0DBBA0h
0x180040de4  mov     [rsp+4E0h+var_48C], 203h
0x180040dec  mov     [rsp+4E0h+var_488], 124F80h
0x180040df4  mov     [rsp+4E0h+var_484], 204h
0x180040dfc  mov     [rsp+4E0h+var_480], 1B7740h
0x180040e04  mov     [rsp+4E0h+var_47C], 205h
0x180040e0c  mov     [rsp+4E0h+var_478], 36EE80h
0x180040e14  mov     [rsp+4E0h+var_474], 206h
0x180040e1c  mov     [rsp+4E0h+var_470], 6DDD00h
0x180040e24  mov     [rsp+4E0h+var_46C], 207h
0x180040e2c  mov     [rsp+4E0h+var_468], 0A4CB80h
0x180040e34  mov     [rsp+4E0h+var_464], 208h
0x180040e3c  mov     [rbp+3E0h+var_460], 0DBBA00h
0x180040e43  mov     [rbp+3E0h+var_45C], 209h
0x180040e4a  mov     [rbp+3E0h+var_458], 1499700h
0x180040e51  mov     [rbp+3E0h+var_454], 20Ah
0x180040e58  mov     [rbp+3E0h+var_450], 2932E00h
0x180040e5f  mov     [rbp+3E0h+var_44C], 20Bh
0x180040e66  mov     [rbp+3E0h+var_448], 5265C00h
0x180040e6d  mov     [rbp+3E0h+var_444], 20Ch
0x180040e74  call    cs:__imp_StrToID
0x180040e7b  nop     dword ptr [rax+rax+00h]
0x180040e80  movzx   edx, ax
0x180040e83  mov     rcx, rbx
0x180040e86  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180040e8d  nop     dword ptr [rax+rax+00h]
0x180040e92  xor     ebx, ebx
0x180040e94  mov     r14, rax
0x180040e97  xor     edi, edi
0x180040e99  cmp     edi, 10h
0x180040e9c  jnb     loc_180040F50
0x180040ea2  mov     rcx, cs:g_hinst; hInstance
0x180040ea9  lea     r8, [rbp+3E0h+Buffer]; lpBuffer
0x180040ead  movsxd  r15, edi
0x180040eb0  mov     r9d, 200h; cchBufferMax
0x180040eb6  mov     edx, dword ptr [rsp+r15*8+4E0h+lParam+4]; uID
0x180040ebb  call    cs:__imp_LoadStringW
0x180040ec2  nop     dword ptr [rax+rax+00h]
0x180040ec7  test    eax, eax
0x180040ec9  jz      short loc_180040F2C
0x180040ecb  lea     rdx, [rbp+3E0h+Buffer]
0x180040ecf  mov     rcx, r14
0x180040ed2  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x180040ed9  nop     dword ptr [rax+rax+00h]
0x180040ede  movsxd  rsi, eax
0x180040ee1  cmp     esi, 0FFFFFFFFh
0x180040ee4  jz      short loc_180040F2C
0x180040ee6  mov     rcx, [r14]
0x180040ee9  mov     rax, [rcx+168h]
0x180040ef0  mov     rcx, r14
0x180040ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ef8  mov     r15d, dword ptr [rsp+r15*8+4E0h+lParam]
0x180040efd  mov     r8, rsi; wParam
0x180040f00  mov     r9d, r15d; lParam
0x180040f03  mov     edx, 151h; Msg
0x180040f08  mov     rcx, rax; hWnd
0x180040f0b  call    cs:__imp_SendMessageW
0x180040f12  nop     dword ptr [rax+rax+00h]
0x180040f17  test    eax, eax
0x180040f19  js      short loc_180040F2C
0x180040f1b  cmp     r15d, 1B7740h
0x180040f22  cmovz   ebx, esi
0x180040f25  inc     edi
0x180040f27  jmp     loc_180040E99
0x180040f2c  call    cs:__imp_GetLastError
0x180040f33  nop     dword ptr [rax+rax+00h]
0x180040f38  test    eax, eax
0x180040f3a  jle     short loc_180040F44
0x180040f3c  movzx   eax, ax
0x180040f3f  or      eax, 80070000h
0x180040f44  test    eax, eax
0x180040f46  mov     ecx, 80004005h
0x180040f4b  cmovns  eax, ecx
0x180040f4e  jmp     short loc_180040F61
0x180040f50  mov     edx, ebx
0x180040f52  mov     rcx, r14
0x180040f55  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x180040f5c  nop     dword ptr [rax+rax+00h]
0x180040f61  mov     rcx, [rbp+3E0h+var_40]
0x180040f68  xor     rcx, rsp; StackCookie
0x180040f6b  call    __security_check_cookie
0x180040f70  add     rsp, 4B8h
0x180040f77  pop     r15
0x180040f79  pop     r14
0x180040f7b  pop     rdi
0x180040f7c  pop     rsi
0x180040f7d  pop     rbx
0x180040f7e  pop     rbp
0x180040f7f  retn
```
