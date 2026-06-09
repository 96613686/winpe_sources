# ZoneConfigureW

- ea: `0x1800351d0`
- end: `0x18003534d`
- name: `ZoneConfigureW`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180003400`
- `0x180012550`
- `0x180013066`
- `0x1800255c0`
- `0x1800351d0`
- `0x180036244`
- `0x1800369b9`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035320`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035320`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003522d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003522d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180035211`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180035211`

## pseudocode

```c
int __fastcall ZoneConfigureW(HWND a1, const unsigned __int16 *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rsi
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v9; // [rsp+34h] [rbp-CCh]
  __int128 v10; // [rsp+44h] [rbp-BCh]
  _BYTE v11[28]; // [rsp+54h] [rbp-ACh] BYREF
  PROPSHEETHEADERW_V2 v12; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[128]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v14[2088]; // [rsp+150h] [rbp+50h] BYREF

  LibraryW = LoadLibraryW(L"inetcpl.cpl");
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "AddInternetPropertySheetsEx");
    if ( ProcAddress )
    {
      v8 = 64;
      memset(v11, 0, sizeof(v11));
      v9 = 0;
      v10 = 0;
      StringCchCopyW(v14, 0x824u, a2);
      *(_QWORD *)((char *)&v9 + 4) = v14;
      memset_0(&v12, 0, sizeof(v12));
      memset_0(v13, 0, sizeof(v13));
      v12.hInstance = g_hinst;
      v12.dwSize = 96;
      v12.ppsp = (LPCPROPSHEETPAGEW)v13;
      v12.dwFlags = 1;
      v12.hwndParent = a1;
      v12.pszCaption = (LPCWSTR)282;
      v12.nPages = 0;
      v12.nStartPage = 0;
      LODWORD(v9) = 256;
      ((void (__fastcall *)(__int64 (__fastcall *)(struct _PSP *, __int64), PROPSHEETHEADERW_V2 *, _QWORD, _QWORD, int *))ProcAddress)(
        _ZoneAddPropSheetPage,
        &v12,
        0,
        0,
        &v8);
      if ( v12.nPages )
        PropertySheetW(&v12);
      else
        SHRestrictedMessageBox(a1);
    }
    LODWORD(LibraryW) = FreeLibrary(v5);
  }
  return (int)LibraryW;
}

```

## disassembly

```asm
0x1800351d0  mov     [rsp-8+arg_10], rbx
0x1800351d5  mov     [rsp-8+arg_18], rsi
0x1800351da  push    rbp
0x1800351db  push    rdi
0x1800351dc  push    r14
0x1800351de  lea     rbp, [rsp-10B0h]
0x1800351e6  mov     eax, 11B0h
0x1800351eb  call    __chkstk_0
0x1800351f0  sub     rsp, rax
0x1800351f3  mov     rax, cs:__security_cookie
0x1800351fa  xor     rax, rsp
0x1800351fd  mov     [rbp+10C0h+var_20], rax
0x180035204  mov     rdi, rcx
0x180035207  mov     r14, rdx
0x18003520a  lea     rcx, aInetcplCpl; "inetcpl.cpl"
0x180035211  call    cs:__imp_LoadLibraryW
0x180035217  mov     rbx, rax
0x18003521a  test    rax, rax
0x18003521d  jz      loc_180035326
0x180035223  lea     rdx, aAddinternetpro; "AddInternetPropertySheetsEx"
0x18003522a  mov     rcx, rax; hModule
0x18003522d  call    cs:__imp_GetProcAddress
0x180035233  mov     rsi, rax
0x180035236  test    rax, rax
0x180035239  jz      loc_18003531D
0x18003523f  xorps   xmm0, xmm0
0x180035242  mov     [rsp+11C0h+var_1190], 40h ; '@'
0x18003524a  movups  xmmword ptr [rsp+11C0h+var_116C], xmm0
0x18003524f  mov     r8, r14; unsigned __int16 *
0x180035252  lea     rcx, [rbp+10C0h+var_1070]; unsigned __int16 *
0x180035256  mov     edx, 824h; unsigned __int64
0x18003525b  movups  xmmword ptr [rsp+11C0h+var_116C+0Ch], xmm0
0x180035260  movups  [rsp+11C0h+var_118C], xmm0
0x180035265  movups  [rsp+11C0h+var_117C], xmm0
0x18003526a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003526f  lea     r11, [rbp+10C0h+var_1070]
0x180035273  mov     r14d, 60h ; '`'
0x180035279  mov     r8d, r14d; Size
0x18003527c  mov     qword ptr [rsp+11C0h+var_118C+4], r11
0x180035281  xor     edx, edx; Val
0x180035283  lea     rcx, [rsp+11C0h+var_1150]; void *
0x180035288  call    memset_0
0x18003528d  xor     edx, edx; Val
0x18003528f  lea     r8d, [r14+20h]; Size
0x180035293  lea     rcx, [rbp+10C0h+var_10F0]; void *
0x180035297  call    memset_0
0x18003529c  mov     rax, cs:g_hinst
0x1800352a3  lea     rdx, [rsp+11C0h+var_1150]
0x1800352a8  mov     [rbp+10C0h+var_1150.hInstance], rax
0x1800352ac  lea     rcx, ?_ZoneAddPropSheetPage@@YAHPEAU_PSP@@_J@Z; _ZoneAddPropSheetPage(_PSP *,__int64)
0x1800352b3  lea     rax, [rbp+10C0h+var_10F0]
0x1800352b7  mov     [rsp+11C0h+var_1150.dwSize], r14d
0x1800352bc  mov     qword ptr [rbp+10C0h+var_1150.38h], rax
0x1800352c0  xor     r9d, r9d
0x1800352c3  lea     rax, [rsp+11C0h+var_1190]
0x1800352c8  mov     [rsp+11C0h+var_1150.dwFlags], 1
0x1800352d0  mov     [rsp+11C0h+var_11A0], rax
0x1800352d5  xor     r8d, r8d
0x1800352d8  mov     rax, rsi
0x1800352db  mov     [rsp+11C0h+var_1150.hwndParent], rdi
0x1800352e0  mov     [rbp+10C0h+var_1150.pszCaption], 11Ah
0x1800352e8  mov     [rbp+10C0h+var_1150.nPages], 0
0x1800352ef  mov     dword ptr [rbp+10C0h+var_1150.30h], 0
0x1800352f6  mov     dword ptr [rsp+11C0h+var_118C], 100h
0x1800352fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035303  cmp     [rbp+10C0h+var_1150.nPages], 0
0x180035307  jbe     short loc_180035315
0x180035309  lea     rcx, [rsp+11C0h+var_1150]; LPCPROPSHEETHEADERW
0x18003530e  call    PropertySheetW
0x180035313  jmp     short loc_18003531D
0x180035315  mov     rcx, rdi; hWnd
0x180035318  call    SHRestrictedMessageBox
0x18003531d  mov     rcx, rbx; hLibModule
0x180035320  call    cs:__imp_FreeLibrary
0x180035326  mov     rcx, [rbp+10C0h+var_20]
0x18003532d  xor     rcx, rsp; StackCookie
0x180035330  call    __security_check_cookie
0x180035335  lea     r11, [rsp+11C0h+var_10]
0x18003533d  mov     rbx, [r11+30h]
0x180035341  mov     rsi, [r11+38h]
0x180035345  mov     rsp, r11
0x180035348  pop     r14
0x18003534a  pop     rdi
0x18003534b  pop     rbp
0x18003534c  retn
```
