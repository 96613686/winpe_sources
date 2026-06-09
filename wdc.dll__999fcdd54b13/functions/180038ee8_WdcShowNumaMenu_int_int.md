# WdcShowNumaMenu(int,int)

- ea: `0x180038ee8`
- end: `0x18003912e`
- name: `?WdcShowNumaMenu@@YAJHH@Z`
- size: `582`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f6cc`
- `0x18006ef0c`

## callees

- `0x180006a80`
- `0x18000b854`
- `0x180038ee8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180038f28`
- `KERNEL32!GetLastError` at `0x180038f8d`
- `KERNEL32!GetLastError` at `0x180038ff6`
- `KERNEL32!GetLastError` at `0x18003902f`
- `KERNEL32!GetLastError` at `0x180039057`
- `KERNEL32!GetLastError` at `0x180039072`
- `KERNEL32!GetLastError` at `0x1800390c8`
- `KERNEL32!GetLastError` at `0x180039103`
- `KERNEL32!GetLastError` at `0x180038f28`
- `KERNEL32!GetLastError` at `0x180038f8d`
- `KERNEL32!GetLastError` at `0x180038ff6`
- `KERNEL32!GetLastError` at `0x18003902f`
- `KERNEL32!GetLastError` at `0x180039057`
- `KERNEL32!GetLastError` at `0x180039072`
- `KERNEL32!GetLastError` at `0x1800390c8`
- `KERNEL32!GetLastError` at `0x180039103`
- `USER32!DeleteMenu` at `0x18003904d`
- `USER32!DeleteMenu` at `0x180039068`
- `USER32!DeleteMenu` at `0x1800390f9`
- `USER32!DeleteMenu` at `0x18003904d`
- `USER32!DeleteMenu` at `0x180039068`
- `USER32!DeleteMenu` at `0x1800390f9`
- `USER32!AppendMenuW` at `0x180038fec`
- `USER32!AppendMenuW` at `0x180039025`
- `USER32!AppendMenuW` at `0x1800390be`
- `USER32!AppendMenuW` at `0x180038fec`
- `USER32!AppendMenuW` at `0x180039025`
- `USER32!AppendMenuW` at `0x1800390be`
- `USER32!GetMenuItemID` at `0x180038fb5`
- `USER32!GetMenuItemID` at `0x180038fc5`
- `USER32!GetMenuItemID` at `0x180038fb5`
- `USER32!GetMenuItemID` at `0x180038fc5`
- `USER32!GetMenu` at `0x180038f14`
- `USER32!GetMenu` at `0x180038f14`
- `USER32!GetSubMenu` at `0x180038f7f`
- `USER32!GetSubMenu` at `0x180038f7f`

## pseudocode

```c
__int64 __fastcall WdcShowNumaMenu(int a1, int a2)
{
  HMENU Menu; // rax
  HMENU v5; // rdi
  signed int LastError; // eax
  signed int v7; // ebx
  int StringW; // eax
  HMENU SubMenu; // rax
  HMENU v10; // rdi
  signed int v11; // eax
  UINT MenuItemID; // esi
  WdcStringMap *v13; // rcx
  UINT v14; // ebp
  WdcStringMap *v15; // rcx
  signed int v16; // eax
  LPCWSTR lpNewItem; // [rsp+70h] [rbp+18h] BYREF

  lpNewItem = 0;
  Menu = GetMenu(g_MainWindow);
  v5 = Menu;
  if ( !Menu || (v7 = 0, Menu == (HMENU)-1LL) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( !LastError )
      goto LABEL_7;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_8;
  }
  SubMenu = GetSubMenu(v5, 1);
  v10 = SubMenu;
  if ( SubMenu && SubMenu != (HMENU)-1LL )
    goto LABEL_18;
  v11 = GetLastError();
  v7 = v11;
  if ( !v11 )
  {
LABEL_7:
    v7 = -2147467259;
LABEL_8:
    StringW = v7;
LABEL_9:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\monitor.cpp",
      "WdcShowNumaMenu",
      0,
      L"FAILURE: 0x%08x",
      StringW);
    return (unsigned int)v7;
  }
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_8;
LABEL_18:
  MenuItemID = GetMenuItemID(v10, 5);
  v14 = GetMenuItemID(v10, 6);
  if ( a1 )
  {
    if ( MenuItemID == 30427 )
      goto LABEL_31;
    if ( !AppendMenuW(v10, 0x800u, 0, 0) )
      GetLastError();
    StringW = WdcStringMap::LoadStringW(v15, 0x8124u, (unsigned __int16 **)&lpNewItem);
    v7 = StringW;
    if ( StringW < 0 )
      goto LABEL_9;
    if ( AppendMenuW(v10, 0, 0x76DBu, lpNewItem) )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( MenuItemID != 30427 )
    goto LABEL_31;
  if ( !DeleteMenu(v10, 4u, 0x400u) )
    GetLastError();
  if ( !DeleteMenu(v10, 0x76DBu, 0) )
LABEL_29:
    GetLastError();
LABEL_30:
  v7 = 0;
LABEL_31:
  if ( !a2 )
  {
    if ( v14 != 30428 )
      return (unsigned int)v7;
    if ( !DeleteMenu(v10, 0x76DCu, 0) )
      GetLastError();
    return 0;
  }
  if ( v14 == 30428 )
    return (unsigned int)v7;
  StringW = WdcStringMap::LoadStringW(v13, 0x8123u, (unsigned __int16 **)&lpNewItem);
  v7 = StringW;
  if ( StringW < 0 )
    goto LABEL_9;
  if ( AppendMenuW(v10, 0, 0x76DCu, lpNewItem) )
    return 0;
  v16 = GetLastError();
  v7 = v16;
  if ( !v16 )
    goto LABEL_7;
  if ( v16 > 0 )
    v7 = (unsigned __int16)v16 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_8;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038ee8  mov     [rsp+arg_0], rbx
0x180038eed  mov     [rsp+arg_8], rbp
0x180038ef2  push    rsi
0x180038ef3  push    rdi
0x180038ef4  push    r12
0x180038ef6  push    r14
0x180038ef8  push    r15
0x180038efa  sub     rsp, 30h
0x180038efe  mov     r14d, ecx
0x180038f01  mov     [rsp+58h+lpNewItem], 0
0x180038f0a  mov     rcx, cs:?g_MainWindow@@3PEAUHWND__@@EA; hWnd
0x180038f11  mov     r15d, edx
0x180038f14  call    cs:__imp_GetMenu
0x180038f1a  mov     rdi, rax
0x180038f1d  mov     r12d, 80070000h
0x180038f23  test    rax, rax
0x180038f26  jnz     short loc_180038F6F
0x180038f28  call    cs:__imp_GetLastError
0x180038f2e  mov     ebx, eax
0x180038f30  test    eax, eax
0x180038f32  jz      short loc_180038F42
0x180038f34  jle     short loc_180038F3C
0x180038f36  movzx   ebx, ax
0x180038f39  or      ebx, r12d
0x180038f3c  test    ebx, ebx
0x180038f3e  jns     short loc_180038F77
0x180038f40  jmp     short loc_180038F47
0x180038f42  mov     ebx, 80004005h
0x180038f47  mov     eax, ebx
0x180038f49  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180038f50  mov     [rsp+58h+var_38], eax
0x180038f54  xor     r8d, r8d; int
0x180038f57  lea     rdx, aWdcshownumamen; "WdcShowNumaMenu"
0x180038f5e  lea     rcx, aBaseDiagnosisP_4; "base\\diagnosis\\pdui\\perfmon\\mon\\mo"...
0x180038f65  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180038f6a  jmp     loc_180039115
0x180038f6f  xor     ebx, ebx
0x180038f71  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180038f75  jz      short loc_180038F28
0x180038f77  mov     edx, 1; nPos
0x180038f7c  mov     rcx, rdi; hMenu
0x180038f7f  call    cs:__imp_GetSubMenu
0x180038f85  mov     rdi, rax
0x180038f88  test    rax, rax
0x180038f8b  jnz     short loc_180038FA7
0x180038f8d  call    cs:__imp_GetLastError
0x180038f93  mov     ebx, eax
0x180038f95  test    eax, eax
0x180038f97  jz      short loc_180038F42
0x180038f99  jle     short loc_180038FA1
0x180038f9b  movzx   ebx, ax
0x180038f9e  or      ebx, r12d
0x180038fa1  test    ebx, ebx
0x180038fa3  jns     short loc_180038FAD
0x180038fa5  jmp     short loc_180038F47
0x180038fa7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180038fab  jz      short loc_180038F8D
0x180038fad  mov     edx, 5; nPos
0x180038fb2  mov     rcx, rdi; hMenu
0x180038fb5  call    cs:__imp_GetMenuItemID
0x180038fbb  mov     edx, 6; nPos
0x180038fc0  mov     rcx, rdi; hMenu
0x180038fc3  mov     esi, eax
0x180038fc5  call    cs:__imp_GetMenuItemID
0x180038fcb  mov     ebp, eax
0x180038fcd  test    r14d, r14d
0x180038fd0  jz      short loc_180039037
0x180038fd2  cmp     esi, 76DBh
0x180038fd8  jz      loc_180039084
0x180038fde  xor     r9d, r9d; lpNewItem
0x180038fe1  xor     r8d, r8d; uIDNewItem
0x180038fe4  mov     edx, 800h; uFlags
0x180038fe9  mov     rcx, rdi; hMenu
0x180038fec  call    cs:__imp_AppendMenuW
0x180038ff2  test    eax, eax
0x180038ff4  jnz     short loc_180038FFC
0x180038ff6  call    cs:__imp_GetLastError
0x180038ffc  lea     r8, [rsp+58h+lpNewItem]; unsigned __int16 **
0x180039001  mov     edx, 8124h; unsigned int
0x180039006  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x18003900b  mov     ebx, eax
0x18003900d  test    eax, eax
0x18003900f  js      loc_180038F49
0x180039015  mov     r9, [rsp+58h+lpNewItem]; lpNewItem
0x18003901a  xor     edx, edx; uFlags
0x18003901c  mov     r8d, 76DBh; uIDNewItem
0x180039022  mov     rcx, rdi; hMenu
0x180039025  call    cs:__imp_AppendMenuW
0x18003902b  test    eax, eax
0x18003902d  jnz     short loc_180039082
0x18003902f  call    cs:__imp_GetLastError
0x180039035  jmp     short loc_180039082
0x180039037  cmp     esi, 76DBh
0x18003903d  jnz     short loc_180039084
0x18003903f  mov     edx, 4; uPosition
0x180039044  mov     r8d, 400h; uFlags
0x18003904a  mov     rcx, rdi; hMenu
0x18003904d  call    cs:__imp_DeleteMenu
0x180039053  test    eax, eax
0x180039055  jnz     short loc_18003905D
0x180039057  call    cs:__imp_GetLastError
0x18003905d  xor     r8d, r8d; uFlags
0x180039060  mov     edx, 76DBh; uPosition
0x180039065  mov     rcx, rdi; hMenu
0x180039068  call    cs:__imp_DeleteMenu
0x18003906e  test    eax, eax
0x180039070  jnz     short loc_180039082
0x180039072  call    cs:__imp_GetLastError
0x180039078  test    eax, eax
0x18003907a  jle     short loc_180039082
0x18003907c  movzx   eax, ax
0x18003907f  or      eax, r12d
0x180039082  xor     ebx, ebx
0x180039084  test    r15d, r15d
0x180039087  jz      short loc_1800390E9
0x180039089  cmp     ebp, 76DCh
0x18003908f  jz      loc_180039115
0x180039095  lea     r8, [rsp+58h+lpNewItem]; unsigned __int16 **
0x18003909a  mov     edx, 8123h; unsigned int
0x18003909f  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x1800390a4  mov     ebx, eax
0x1800390a6  test    eax, eax
0x1800390a8  js      loc_180038F49
0x1800390ae  mov     r9, [rsp+58h+lpNewItem]; lpNewItem
0x1800390b3  xor     edx, edx; uFlags
0x1800390b5  mov     r8d, 76DCh; uIDNewItem
0x1800390bb  mov     rcx, rdi; hMenu
0x1800390be  call    cs:__imp_AppendMenuW
0x1800390c4  test    eax, eax
0x1800390c6  jnz     short loc_180039113
0x1800390c8  call    cs:__imp_GetLastError
0x1800390ce  mov     ebx, eax
0x1800390d0  test    eax, eax
0x1800390d2  jz      loc_180038F42
0x1800390d8  jle     short loc_1800390E0
0x1800390da  movzx   ebx, ax
0x1800390dd  or      ebx, r12d
0x1800390e0  test    ebx, ebx
0x1800390e2  jns     short loc_180039115
0x1800390e4  jmp     loc_180038F47
0x1800390e9  cmp     ebp, 76DCh
0x1800390ef  jnz     short loc_180039115
0x1800390f1  xor     r8d, r8d; uFlags
0x1800390f4  mov     edx, ebp; uPosition
0x1800390f6  mov     rcx, rdi; hMenu
0x1800390f9  call    cs:__imp_DeleteMenu
0x1800390ff  test    eax, eax
0x180039101  jnz     short loc_180039113
0x180039103  call    cs:__imp_GetLastError
0x180039109  test    eax, eax
0x18003910b  jle     short loc_180039113
0x18003910d  movzx   eax, ax
0x180039110  or      eax, r12d
0x180039113  xor     ebx, ebx
0x180039115  mov     rbp, [rsp+58h+arg_8]
0x18003911a  mov     eax, ebx
0x18003911c  mov     rbx, [rsp+58h+arg_0]
0x180039121  add     rsp, 30h
0x180039125  pop     r15
0x180039127  pop     r14
0x180039129  pop     r12
0x18003912b  pop     rdi
0x18003912c  pop     rsi
0x18003912d  retn
```
