# CShellContextMenuForContacts::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x18003c690`
- end: `0x18003cbae`
- name: `?QueryContextMenu@CShellContextMenuForContacts@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `1310`
- prototype: `int(CShellContextMenuForContacts *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005d08`
- `0x180006f7c`
- `0x180008f74`
- `0x180009aec`
- `0x180018e6c`
- `0x18003c690`
- `0x18003ce80`
- `0x180063840`
- `0x18006403c`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18003c7a8`
- `GDI32!DeleteObject` at `0x18003c7a8`
- `KERNEL32!GetLastError` at `0x18003ca1a`
- `KERNEL32!GetLastError` at `0x18003ca1a`
- `USER32!LoadStringW` at `0x18003ca10`
- `USER32!LoadStringW` at `0x18003ca10`
- `USER32!CreatePopupMenu` at `0x18003c6f8`
- `USER32!CreatePopupMenu` at `0x18003c717`
- `USER32!CreatePopupMenu` at `0x18003c6f8`
- `USER32!CreatePopupMenu` at `0x18003c717`
- `USER32!LoadIconW` at `0x18003c786`
- `USER32!LoadIconW` at `0x18003c786`
- `USER32!SetMenuInfo` at `0x18003c7eb`
- `USER32!SetMenuInfo` at `0x18003c7eb`
- `USER32!InsertMenuW` at `0x18003ca81`
- `USER32!InsertMenuW` at `0x18003cae1`
- `USER32!InsertMenuW` at `0x18003ca81`
- `USER32!InsertMenuW` at `0x18003cae1`
- `USER32!DestroyMenu` at `0x18003cb75`
- `USER32!DestroyMenu` at `0x18003cb83`
- `USER32!DestroyMenu` at `0x18003cb75`
- `USER32!DestroyMenu` at `0x18003cb83`
- `iertutil!__imp_DPA_GetPtr` at `0x18003c9d9`
- `iertutil!__imp_DPA_GetPtr` at `0x18003cabd`
- `iertutil!__imp_DPA_GetPtr` at `0x18003c9d9`
- `iertutil!__imp_DPA_GetPtr` at `0x18003cabd`

## pseudocode

```c
__int64 __fastcall CShellContextMenuForContacts::QueryContextMenu(
        CShellContextMenuForContacts *this,
        HMENU a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  int LastError; // ebx
  HMENU PopupMenu; // r12
  HMENU v12; // r13
  CShellContextMenuBase *v13; // rcx
  unsigned int v14; // edx
  char *v15; // r15
  HICON IconW; // rax
  HICON v17; // rbx
  int v18; // eax
  CShellContextMenuBase *v19; // rcx
  __int64 v20; // rcx
  CShellContextMenuBase *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  int v24; // ebx
  const unsigned __int16 *Ptr; // rax
  const unsigned __int16 *ActualEmailAddress; // rax
  DWORD v27; // eax
  const WCHAR *lpNewItem; // rcx
  unsigned int v29; // eax
  const unsigned __int16 *v30; // rax
  const WCHAR *v31; // rax
  int v32; // eax
  unsigned int v33; // r8d
  int ContextMenu; // eax
  INT_PTR i; // [rsp+40h] [rbp-C0h] BYREF
  MENUINFO v37; // [rsp+48h] [rbp-B8h] BYREF
  HMENU v38; // [rsp+70h] [rbp-90h]
  struct tagSIZE v39; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v41[264]; // [rsp+290h] [rbp+190h] BYREF

  v38 = a2;
  if ( (a6 & 1) != 0 )
    return 0;
  if ( a5 - a4 < 7 )
    return (unsigned int)-2147024809;
  PopupMenu = CreatePopupMenu();
  if ( !PopupMenu )
  {
    v12 = 0;
LABEL_7:
    LastError = HrGetLastError();
    goto LABEL_45;
  }
  v12 = CreatePopupMenu();
  if ( !v12 )
    goto LABEL_7;
  LastError = CShellContextMenuBase::_AddCommandToMenu(v13, a2, dword_1800AAA94, a3, a4, PopupMenu, 0, 1);
  if ( LastError >= 0 )
  {
    v14 = a3 + 1;
    v15 = (char *)this - 8;
    LODWORD(i) = v14;
    if ( !*((_QWORD *)this + 14) )
    {
      v39.cx = 16;
      v39.cy = 16;
      IconW = LoadIconW(hinstMapiX, (LPCWSTR)0x787);
      v17 = IconW;
      if ( IconW )
      {
        CreateBitmapFromIcon(IconW, &v39, (HBITMAP *)this + 14);
        DeleteObject(v17);
      }
      v14 = i;
    }
    if ( *((_DWORD *)this + 9) )
    {
      memset(&v37.cyMax, 0, 28);
      v37.cbSize = 40;
      v37.fMask = 16;
      v37.dwStyle = 0x4000000;
      SetMenuInfo(v38, &v37);
      v18 = CShellContextMenuBase::_AddCommandToMenu(
              (CShellContextMenuBase *)(a4 + 1),
              v38,
              0x1185u,
              i,
              a4 + 1,
              0,
              *((HBITMAP *)this + 14),
              1);
    }
    else
    {
      if ( *((_DWORD *)this + 8) != 1 || (v20 = 1, !*((_DWORD *)this + 10)) )
        v20 = 0;
      v18 = CShellContextMenuBase::_AddCommandToMenu((CShellContextMenuBase *)v20, v38, 0x1174u, v14, a4 + 1, 0, 0, v20);
    }
    LastError = v18;
    if ( v18 >= 0 )
    {
      LastError = CShellContextMenuBase::_AddCommandToMenu(v19, v38, dword_1800AAB04, i + 1, a4 + 2, 0, 0, 1);
      if ( LastError >= 0 )
      {
        LastError = CShellContextMenuBase::_AddCommandToMenu(v21, PopupMenu, dword_1800AAB3C, 0, a4 + 3, 0, 0, 1);
        if ( LastError >= 0 )
        {
          if ( *((_DWORD *)this + 8) != 1
            || (v22 = *(_QWORD *)v15,
                LODWORD(i) = 0,
                LastError = (*(__int64 (__fastcall **)(char *, char *, INT_PTR *, char *))(v22 + 64))(
                              (char *)this - 8,
                              (char *)this + 104,
                              &i,
                              (char *)this + 96),
                LastError >= 0) )
          {
            v23 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 56LL))((char *)this - 8);
            LastError = CShellContextMenuBase::_AddCommandToMenu(
                          (CShellContextMenuBase *)(v23 > 1),
                          PopupMenu,
                          dword_1800AAB74,
                          1u,
                          a4 + 4,
                          v12,
                          0,
                          v23 > 1);
            if ( LastError >= 0 )
            {
              LastError = CShellContextMenuBase::_AddCommandToMenu(
                            (CShellContextMenuBase *)(a4 + 5),
                            PopupMenu,
                            dword_1800AABAC,
                            2u,
                            a4 + 5,
                            0,
                            0,
                            *((_DWORD *)this + 8) == 1);
              if ( LastError >= 0 )
              {
                v24 = 6;
                if ( (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v15 + 56LL))((char *)this - 8) > 1 )
                {
                  memset_0(Buffer, 0, 0x208u);
                  STRW::STRW((STRW *)&v37, v41, 0x104u);
                  Ptr = (const unsigned __int16 *)DPA_GetPtr(*((HDPA *)this + 12), 0);
                  ActualEmailAddress = FindActualEmailAddress(Ptr);
                  LastError = STRW::Append((STRW *)&v37, ActualEmailAddress);
                  if ( LastError < 0 )
                    goto LABEL_33;
                  if ( !LoadStringW(hinstMapiX, 0x1178u, Buffer, 260) )
                  {
                    v27 = GetLastError();
LABEL_31:
                    v37.cbSize = 0;
                    LastError = v27;
                    BUFFER::ReleaseStorage((BUFFER *)&v37.dwStyle);
                    goto LABEL_45;
                  }
                  LastError = STRW::Append((STRW *)&v37, Buffer);
                  if ( LastError < 0 )
                  {
LABEL_33:
                    v37.cbSize = 0;
                    BUFFER::ReleaseStorage((BUFFER *)&v37.dwStyle);
                    goto LABEL_47;
                  }
                  lpNewItem = &Str;
                  if ( v37.cbSize )
                    lpNewItem = *(const WCHAR **)&v37.dwStyle;
                  if ( !InsertMenuW(v12, 0, 0x400u, a4 + 6, lpNewItem) )
                  {
LABEL_37:
                    v27 = HrGetLastError();
                    goto LABEL_31;
                  }
                  v24 = 7;
                  for ( LODWORD(i) = 1; ; LODWORD(i) = i + 1 )
                  {
                    v29 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 56LL))((char *)this - 8);
                    if ( (unsigned int)i >= v29 )
                      break;
                    v30 = (const unsigned __int16 *)DPA_GetPtr(*((HDPA *)this + 12), (unsigned int)i);
                    v31 = FindActualEmailAddress(v30);
                    if ( !InsertMenuW(v12, i, 0x400u, a4 + v24, v31) )
                      goto LABEL_37;
                    ++v24;
                  }
                  v37.cbSize = 0;
                  BUFFER::ReleaseStorage((BUFFER *)&v37.dwStyle);
                }
                v32 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 56LL))((char *)this - 8);
                ContextMenu = CExtensionContextMenus::QueryContextMenu(
                                (CShellContextMenuForContacts *)((char *)this + 48),
                                PopupMenu,
                                v33,
                                v32 + 6,
                                a4 + v24,
                                a5,
                                a6);
                LastError = ContextMenu;
                if ( ContextMenu >= 0 )
                {
                  *((_DWORD *)this + 22) = (unsigned __int16)ContextMenu;
                  LastError = (unsigned __int16)(ContextMenu
                                               + (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 56LL))((char *)this - 8)
                                               + 6);
LABEL_45:
                  if ( LastError >= 0 )
                    return (unsigned int)LastError;
                  if ( !PopupMenu )
                    goto LABEL_48;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_47:
  DestroyMenu(PopupMenu);
LABEL_48:
  if ( v12 )
    DestroyMenu(v12);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18003c690  push    rbp
0x18003c692  push    rbx
0x18003c693  push    rsi
0x18003c694  push    rdi
0x18003c695  push    r12
0x18003c697  push    r13
0x18003c699  push    r14
0x18003c69b  push    r15
0x18003c69d  lea     rbp, [rsp-3B8h]
0x18003c6a5  sub     rsp, 4B8h
0x18003c6ac  mov     rax, cs:__security_cookie
0x18003c6b3  xor     rax, rsp
0x18003c6b6  mov     [rbp+3F0h+var_50], rax
0x18003c6bd  test    byte ptr [rbp+3F0h+arg_28], 1
0x18003c6c4  mov     r14d, r9d
0x18003c6c7  mov     r15d, r8d
0x18003c6ca  mov     [rsp+4F0h+var_480], rdx
0x18003c6cf  mov     rbx, rdx
0x18003c6d2  mov     rsi, rcx
0x18003c6d5  jz      short loc_18003C6E0
0x18003c6d7  xor     edi, edi
0x18003c6d9  mov     ebx, edi
0x18003c6db  jmp     loc_18003CB89
0x18003c6e0  mov     eax, [rbp+3F0h+arg_20]
0x18003c6e6  sub     eax, r14d
0x18003c6e9  cmp     eax, 7
0x18003c6ec  jnb     short loc_18003C6F8
0x18003c6ee  mov     ebx, 80070057h
0x18003c6f3  jmp     loc_18003CB89
0x18003c6f8  call    cs:__imp_CreatePopupMenu
0x18003c6fe  xor     edi, edi
0x18003c700  mov     r12, rax
0x18003c703  test    rax, rax
0x18003c706  jnz     short loc_18003C717
0x18003c708  mov     r13d, edi
0x18003c70b  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18003c710  mov     ebx, eax
0x18003c712  jmp     loc_18003CB69
0x18003c717  call    cs:__imp_CreatePopupMenu
0x18003c71d  mov     r13, rax
0x18003c720  test    rax, rax
0x18003c723  jz      short loc_18003C70B
0x18003c725  mov     r8d, cs:dword_1800AAA94; unsigned int
0x18003c72c  mov     r9d, r15d; unsigned int
0x18003c72f  mov     [rsp+4F0h+var_4B8], 1; int
0x18003c737  mov     rdx, rbx; HMENU
0x18003c73a  mov     [rsp+4F0h+var_4C0], rdi; HBITMAP
0x18003c73f  mov     [rsp+4F0h+var_4C8], r12; HMENU
0x18003c744  mov     dword ptr [rsp+4F0h+lpNewItem], r14d; unsigned int
0x18003c749  call    ?_AddCommandToMenu@CShellContextMenuBase@@IEAAJPEAUHMENU__@@III0PEAUHBITMAP__@@H@Z; CShellContextMenuBase::_AddCommandToMenu(HMENU__ *,uint,uint,uint,HMENU__ *,HBITMAP__ *,int)
0x18003c74e  mov     ebx, eax
0x18003c750  test    eax, eax
0x18003c752  js      loc_18003CB72
0x18003c758  lea     edx, [r15+1]
0x18003c75c  lea     r15, [rsi-8]
0x18003c760  mov     dword ptr [rsp+4F0h+i], edx
0x18003c764  cmp     [r15+78h], rdi
0x18003c768  jnz     short loc_18003C7B2
0x18003c76a  mov     rcx, cs:hinstMapiX; hInstance
0x18003c771  mov     edx, 787h; lpIconName
0x18003c776  mov     [rsp+4F0h+var_478.cx], 10h
0x18003c77e  mov     [rsp+4F0h+var_478.cy], 10h
0x18003c786  call    cs:__imp_LoadIconW
0x18003c78c  mov     rbx, rax
0x18003c78f  test    rax, rax
0x18003c792  jz      short loc_18003C7AE
0x18003c794  lea     r8, [rsi+70h]; HBITMAP *
0x18003c798  mov     rcx, rax; hicon
0x18003c79b  lea     rdx, [rsp+4F0h+var_478]; struct tagSIZE *
0x18003c7a0  call    ?CreateBitmapFromIcon@@YAJPEAUHICON__@@PEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CreateBitmapFromIcon(HICON__ *,tagSIZE const *,HBITMAP__ * *)
0x18003c7a5  mov     rcx, rbx; ho
0x18003c7a8  call    cs:__imp_DeleteObject
0x18003c7ae  mov     edx, dword ptr [rsp+4F0h+i]
0x18003c7b2  cmp     [rsi+24h], edi
0x18003c7b5  jz      short loc_18003C81C
0x18003c7b7  mov     rcx, [rsp+4F0h+var_480]; HMENU
0x18003c7bc  lea     rdx, [rsp+4F0h+var_4A8]; LPCMENUINFO
0x18003c7c1  xorps   xmm0, xmm0
0x18003c7c4  mov     qword ptr [rsp+4F0h+var_4A8+1Ch], rdi
0x18003c7c9  movdqu  xmmword ptr [rsp+4F0h+var_4A8.cyMax], xmm0
0x18003c7cf  mov     dword ptr [rsp+4F0h+var_4A8.dwMenuData+4], edi
0x18003c7d3  mov     [rsp+4F0h+var_4A8.cbSize], 28h ; '('
0x18003c7db  mov     [rsp+4F0h+var_4A8.fMask], 10h
0x18003c7e3  mov     [rsp+4F0h+var_4A8.dwStyle], 4000000h
0x18003c7eb  call    cs:__imp_SetMenuInfo
0x18003c7f1  mov     rax, [rsi+70h]
0x18003c7f5  lea     ecx, [r14+1]
0x18003c7f9  mov     r9d, dword ptr [rsp+4F0h+i]
0x18003c7fe  mov     r8d, 1185h
0x18003c804  mov     [rsp+4F0h+var_4B8], 1
0x18003c80c  mov     [rsp+4F0h+var_4C0], rax
0x18003c811  mov     [rsp+4F0h+var_4C8], rdi
0x18003c816  mov     dword ptr [rsp+4F0h+lpNewItem], ecx
0x18003c81a  jmp     short loc_18003C84D
0x18003c81c  cmp     dword ptr [rsi+20h], 1
0x18003c820  jnz     short loc_18003C82C
0x18003c822  mov     ecx, 1
0x18003c827  cmp     [rsi+28h], edi
0x18003c82a  jnz     short loc_18003C82E
0x18003c82c  mov     ecx, edi; this
0x18003c82e  mov     [rsp+4F0h+var_4B8], ecx; int
0x18003c832  lea     eax, [r14+1]
0x18003c836  mov     [rsp+4F0h+var_4C0], rdi; HBITMAP
0x18003c83b  mov     r9d, edx; unsigned int
0x18003c83e  mov     [rsp+4F0h+var_4C8], rdi; HMENU
0x18003c843  mov     r8d, 1174h; unsigned int
0x18003c849  mov     dword ptr [rsp+4F0h+lpNewItem], eax; unsigned int
0x18003c84d  mov     rdx, [rsp+4F0h+var_480]; HMENU
0x18003c852  call    ?_AddCommandToMenu@CShellContextMenuBase@@IEAAJPEAUHMENU__@@III0PEAUHBITMAP__@@H@Z; CShellContextMenuBase::_AddCommandToMenu(HMENU__ *,uint,uint,uint,HMENU__ *,HBITMAP__ *,int)
0x18003c857  mov     ebx, eax
0x18003c859  test    eax, eax
0x18003c85b  js      loc_18003CB72
0x18003c861  mov     r9d, dword ptr [rsp+4F0h+i]
0x18003c866  lea     eax, [r14+2]
0x18003c86a  mov     r8d, cs:dword_1800AAB04; unsigned int
0x18003c871  inc     r9d; unsigned int
0x18003c874  mov     rdx, [rsp+4F0h+var_480]; HMENU
0x18003c879  mov     [rsp+4F0h+var_4B8], 1; int
0x18003c881  mov     [rsp+4F0h+var_4C0], rdi; HBITMAP
0x18003c886  mov     [rsp+4F0h+var_4C8], rdi; HMENU
0x18003c88b  mov     dword ptr [rsp+4F0h+lpNewItem], eax; unsigned int
0x18003c88f  call    ?_AddCommandToMenu@CShellContextMenuBase@@IEAAJPEAUHMENU__@@III0PEAUHBITMAP__@@H@Z; CShellContextMenuBase::_AddCommandToMenu(HMENU__ *,uint,uint,uint,HMENU__ *,HBITMAP__ *,int)
0x18003c894  mov     ebx, eax
0x18003c896  test    eax, eax
0x18003c898  js      loc_18003CB72
0x18003c89e  mov     r8d, cs:dword_1800AAB3C; unsigned int
0x18003c8a5  lea     eax, [r14+3]
0x18003c8a9  mov     [rsp+4F0h+var_4B8], 1; int
0x18003c8b1  xor     r9d, r9d; unsigned int
0x18003c8b4  mov     [rsp+4F0h+var_4C0], rdi; HBITMAP
0x18003c8b9  mov     rdx, r12; HMENU
0x18003c8bc  mov     [rsp+4F0h+var_4C8], rdi; HMENU
0x18003c8c1  mov     dword ptr [rsp+4F0h+lpNewItem], eax; unsigned int
0x18003c8c5  call    ?_AddCommandToMenu@CShellContextMenuBase@@IEAAJPEAUHMENU__@@III0PEAUHBITMAP__@@H@Z; CShellContextMenuBase::_AddCommandToMenu(HMENU__ *,uint,uint,uint,HMENU__ *,HBITMAP__ *,int)
0x18003c8ca  mov     ebx, eax
0x18003c8cc  test    eax, eax
0x18003c8ce  js      loc_18003CB72
0x18003c8d4  cmp     dword ptr [rsi+20h], 1
0x18003c8d8  jnz     short loc_18003C904
0x18003c8da  mov     rax, [r15]
0x18003c8dd  lea     r9, [rsi+60h]
0x18003c8e1  lea     rdx, [rsi+68h]
0x18003c8e5  mov     dword ptr [rsp+4F0h+i], edi
0x18003c8e9  lea     r8, [rsp+4F0h+i]
0x18003c8ee  mov     rcx, r15
0x18003c8f1  mov     rax, [rax+40h]
0x18003c8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8fa  mov     ebx, eax
0x18003c8fc  test    eax, eax
0x18003c8fe  js      loc_18003CB72
0x18003c904  mov     rax, [r15]
0x18003c907  mov     rcx, r15
0x18003c90a  mov     rax, [rax+38h]
0x18003c90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c913  mov     r8d, cs:dword_1800AAB74; unsigned int
0x18003c91a  cmp     eax, 1
0x18003c91d  mov     ecx, edi
0x18003c91f  lea     eax, [r14+4]
0x18003c923  setnbe  cl; this
0x18003c926  mov     r9d, 1; unsigned int
0x18003c92c  mov     [rsp+4F0h+var_4B8], ecx; int
0x18003c930  mov     rdx, r12; HMENU
0x18003c933  mov     [rsp+4F0h+var_4C0], rdi; HBITMAP
0x18003c938  mov     [rsp+4F0h+var_4C8], r13; HMENU
0x18003c93d  mov     dword ptr [rsp+4F0h+lpNewItem], eax; unsigned int
0x18003c941  call    ?_AddCommandToMenu@CShellContextMenuBase@@IEAAJPEAUHMENU__@@III0PEAUHBITMAP__@@H@Z; CShellContextMenuBase::_AddCommandToMenu(HMENU__ *,uint,uint,uint,HMENU__ *,HBITMAP__ *,int)
0x18003c946  mov     ebx, eax
0x18003c948  test    eax, eax
0x18003c94a  js      loc_18003CB72
0x18003c950  cmp     dword ptr [rsi+20h], 1
0x18003c954  lea     ecx, [r14+5]; this
0x18003c958  mov     r8d, cs:dword_1800AABAC; unsigned int
0x18003c95f  mov     eax, edi
0x18003c961  setz    al
0x18003c964  mov     r9d, 2; unsigned int
0x18003c96a  mov     [rsp+4F0h+var_4B8], eax; int
0x18003c96e  mov     rdx, r12; HMENU
0x18003c971  mov     [rsp+4F0h+var_4C0], rdi; HBITMAP
0x18003c976  mov     [rsp+4F0h+var_4C8], rdi; HMENU
0x18003c97b  mov     dword ptr [rsp+4F0h+lpNewItem], ecx; unsigned int
0x18003c97f  call    ?_AddCommandToMenu@CShellContextMenuBase@@IEAAJPEAUHMENU__@@III0PEAUHBITMAP__@@H@Z; CShellContextMenuBase::_AddCommandToMenu(HMENU__ *,uint,uint,uint,HMENU__ *,HBITMAP__ *,int)
0x18003c984  mov     ebx, eax
0x18003c986  test    eax, eax
0x18003c988  js      loc_18003CB72
0x18003c98e  mov     rax, [r15]
0x18003c991  mov     rcx, r15
0x18003c994  mov     ebx, 6
0x18003c999  mov     rax, [rax+38h]
0x18003c99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9a2  cmp     eax, 1
0x18003c9a5  jbe     loc_18003CB01
0x18003c9ab  xor     edx, edx; Val
0x18003c9ad  lea     rcx, [rbp+3F0h+Buffer]; void *
0x18003c9b1  mov     r8d, 208h; Size
0x18003c9b7  call    memset_0
0x18003c9bc  mov     r8d, 104h; unsigned int
0x18003c9c2  lea     rdx, [rbp+3F0h+var_260]; unsigned __int16 *
0x18003c9c9  lea     rcx, [rsp+4F0h+var_4A8]; this
0x18003c9ce  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18003c9d3  mov     rcx, [rsi+60h]; hdpa
0x18003c9d7  xor     edx, edx; i
0x18003c9d9  call    cs:__imp_DPA_GetPtr
0x18003c9df  mov     rcx, rax; unsigned __int16 *
0x18003c9e2  call    ?FindActualEmailAddress@@YAPEBGPEBG@Z; FindActualEmailAddress(ushort const *)
0x18003c9e7  mov     rdx, rax; unsigned __int16 *
0x18003c9ea  lea     rcx, [rsp+4F0h+var_4A8]; this
0x18003c9ef  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x18003c9f4  mov     ebx, eax
0x18003c9f6  test    eax, eax
0x18003c9f8  js      short loc_18003CA49
0x18003c9fa  mov     rcx, cs:hinstMapiX; hInstance
0x18003ca01  lea     r8, [rbp+3F0h+Buffer]; lpBuffer
0x18003ca05  mov     r9d, 104h; cchBufferMax
0x18003ca0b  mov     edx, 1178h; uID
0x18003ca10  call    cs:__imp_LoadStringW
0x18003ca16  test    eax, eax
0x18003ca18  jnz     short loc_18003CA35
0x18003ca1a  call    cs:__imp_GetLastError
0x18003ca20  lea     rcx, [rsp+4F0h+var_4A8.dwStyle]; this
0x18003ca25  mov     [rsp+4F0h+var_4A8.cbSize], edi
0x18003ca29  mov     ebx, eax
0x18003ca2b  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18003ca30  jmp     loc_18003CB69
0x18003ca35  lea     rdx, [rbp+3F0h+Buffer]; unsigned __int16 *
0x18003ca39  lea     rcx, [rsp+4F0h+var_4A8]; this
0x18003ca3e  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x18003ca43  mov     ebx, eax
0x18003ca45  test    eax, eax
0x18003ca47  jns     short loc_18003CA5C
0x18003ca49  lea     rcx, [rsp+4F0h+var_4A8.dwStyle]; this
0x18003ca4e  mov     [rsp+4F0h+var_4A8.cbSize], edi
0x18003ca52  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18003ca57  jmp     loc_18003CB72
0x18003ca5c  cmp     [rsp+4F0h+var_4A8.cbSize], edi
0x18003ca60  lea     rcx, Str
0x18003ca67  lea     r9d, [r14+6]; uIDNewItem
0x18003ca6b  mov     r8d, 400h; uFlags
0x18003ca71  cmovnz  rcx, qword ptr [rsp+4F0h+var_4A8.dwStyle]
0x18003ca77  xor     edx, edx; uPosition
0x18003ca79  mov     [rsp+4F0h+lpNewItem], rcx; lpNewItem
0x18003ca7e  mov     rcx, r13; hMenu
0x18003ca81  call    cs:__imp_InsertMenuW
0x18003ca87  test    eax, eax
0x18003ca89  jnz     short loc_18003CA92
0x18003ca8b  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18003ca90  jmp     short loc_18003CA20
0x18003ca92  mov     ebx, 7
0x18003ca97  mov     dword ptr [rsp+4F0h+i], 1
0x18003ca9f  mov     rax, [rsi-8]
0x18003caa3  mov     rcx, r15
0x18003caa6  mov     rax, [rax+38h]
0x18003caaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003caaf  mov     ecx, dword ptr [rsp+4F0h+i]
0x18003cab3  cmp     ecx, eax
0x18003cab5  jnb     short loc_18003CAF3
0x18003cab7  mov     edx, ecx; i
0x18003cab9  mov     rcx, [rsi+60h]; hdpa
0x18003cabd  call    cs:__imp_DPA_GetPtr
0x18003cac3  mov     rcx, rax; unsigned __int16 *
0x18003cac6  call    ?FindActualEmailAddress@@YAPEBGPEBG@Z; FindActualEmailAddress(ushort const *)
0x18003cacb  mov     edx, dword ptr [rsp+4F0h+i]; uPosition
0x18003cacf  lea     r9d, [r14+rbx]; uIDNewItem
0x18003cad3  mov     r8d, 400h; uFlags
0x18003cad9  mov     [rsp+4F0h+lpNewItem], rax; lpNewItem
0x18003cade  mov     rcx, r13; hMenu
0x18003cae1  call    cs:__imp_InsertMenuW
0x18003cae7  test    eax, eax
0x18003cae9  jz      short loc_18003CA8B
0x18003caeb  inc     ebx
0x18003caed  inc     dword ptr [rsp+4F0h+i]
0x18003caf1  jmp     short loc_18003CA9F
0x18003caf3  lea     rcx, [rsp+4F0h+var_4A8.dwStyle]; this
0x18003caf8  mov     [rsp+4F0h+var_4A8.cbSize], edi
0x18003cafc  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18003cb01  mov     rax, [r15]
0x18003cb04  mov     rcx, r15
0x18003cb07  add     ebx, r14d
0x18003cb0a  mov     rax, [rax+38h]
0x18003cb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb13  mov     edx, [rbp+3F0h+arg_28]
0x18003cb19  lea     rcx, [rsi+30h]; this
0x18003cb1d  mov     dword ptr [rsp+4F0h+var_4C0], edx; unsigned int
0x18003cb21  mov     r14d, 6
0x18003cb27  mov     edx, [rbp+3F0h+arg_20]
0x18003cb2d  mov     dword ptr [rsp+4F0h+var_4C8], edx; unsigned int
0x18003cb31  mov     rdx, r12; HMENU
0x18003cb34  mov     dword ptr [rsp+4F0h+lpNewItem], ebx; unsigned int
0x18003cb38  lea     r9d, [r14+rax]; unsigned int
0x18003cb3c  call    ?QueryContextMenu@CExtensionContextMenus@@QEAAJPEAUHMENU__@@IIIII@Z; CExtensionContextMenus::QueryContextMenu(HMENU__ *,uint,uint,uint,uint,uint)
0x18003cb41  mov     ebx, eax
0x18003cb43  test    eax, eax
0x18003cb45  js      short loc_18003CB72
0x18003cb47  movzx   eax, ax
0x18003cb4a  mov     rcx, r15
0x18003cb4d  mov     [rsi+58h], eax
0x18003cb50  movzx   ebx, ax
0x18003cb53  mov     rax, [r15]
0x18003cb56  mov     rax, [rax+38h]
0x18003cb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb5f  add     ax, bx
  ... truncated ...
```
