# CContentDropTarget::_DeviceSideCopyObject(IPortableDevice *,IPortableDeviceContent *,_ITEMIDLIST const *,_ITEMIDLIST const *,ushort const *,COPY_THREAD_DATA *)

- ea: `0x18003c074`
- end: `0x18003c871`
- name: `?_DeviceSideCopyObject@CContentDropTarget@@AEAAJPEAUIPortableDevice@@PEAUIPortableDeviceContent@@PEFBU_ITEMIDLIST@@2PEBGPEAVCOPY_THREAD_DATA@@@Z`
- size: `2045`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, struct IPortableDevice *, struct IPortableDeviceContent *, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, const unsigned __int16 *, struct COPY_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation`

## callers

- `0x18003da14`

## callees

- `0x180003f20`
- `0x180004110`
- `0x180004190`
- `0x1800050d0`
- `0x1800082e0`
- `0x180015a90`
- `0x180019270`
- `0x1800194d8`
- `0x180019788`
- `0x180028f54`
- `0x180029730`
- `0x18002ab58`
- `0x18002ff5c`
- `0x180032298`
- `0x180035590`
- `0x1800361ba`
- `0x18003a710`
- `0x18003bc08`
- `0x18003c074`
- `0x180054524`
- `0x1800545c8`
- `0x180062f88`
- `0x180075530`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003c1f6`
- `KERNEL32!Sleep` at `0x18003c2f2`
- `KERNEL32!Sleep` at `0x18003c1f6`
- `KERNEL32!Sleep` at `0x18003c2f2`
- `SHLWAPI!StrCmpIW` at `0x18003c606`
- `SHLWAPI!StrCmpIW` at `0x18003c606`
- `SHLWAPI!StrStrW` at `0x18003c3ef`
- `SHLWAPI!StrStrW` at `0x18003c3ef`
- `USER32!LoadStringW` at `0x18003c41b`
- `USER32!LoadStringW` at `0x18003c41b`
- `SHELL32!__imp_ILFindLastID` at `0x18003c125`
- `SHELL32!__imp_ILFindLastID` at `0x18003c58f`
- `SHELL32!__imp_ILFindLastID` at `0x18003c125`
- `SHELL32!__imp_ILFindLastID` at `0x18003c58f`
- `SHELL32!__imp_ILRemoveLastID` at `0x18003c613`
- `SHELL32!__imp_ILRemoveLastID` at `0x18003c613`
- `SHELL32!__imp_ILFree` at `0x18003c80a`
- `SHELL32!__imp_ILFree` at `0x18003c818`
- `SHELL32!__imp_ILFree` at `0x18003c80a`
- `SHELL32!__imp_ILFree` at `0x18003c818`

## pseudocode

```c
__int64 __fastcall CContentDropTarget::_DeviceSideCopyObject(
        CContentDropTarget *this,
        struct IPortableDevice *a2,
        struct IPortableDeviceContent *a3,
        struct _ITEMIDLIST *a4,
        const struct _ITEMIDLIST *a5,
        unsigned __int16 *a6,
        CProgressUI **a7)
{
  struct COPY_THREAD_DATA *v8; // r14
  CContentDropTarget *v9; // rsi
  CProgressUI *v10; // r13
  ITEMIDLIST *v11; // r15
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v13; // rcx
  const struct CONTENTITEM *v14; // rax
  _DWORD *v15; // rdi
  const struct CONTENTITEM *v16; // r12
  int ObjectID; // ebx
  __int64 v18; // r9
  int v19; // r14d
  int v20; // esi
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  int v24; // r14d
  int v25; // esi
  int v26; // eax
  PWSTR v27; // rax
  WCHAR *v28; // rbx
  int v29; // eax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  CContentFolder *v32; // rcx
  unsigned int v33; // r9d
  int v34; // r14d
  int v35; // eax
  struct COPY_THREAD_DATA *v36; // r12
  int v37; // esi
  int v38; // edi
  const struct _ITEMIDLIST *v39; // rax
  CContentFolder *v40; // rcx
  const struct CONTENTITEM *v41; // rax
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r9
  struct IPortableDevice *v45; // rdi
  int CanCreateObject; // eax
  int v47; // eax
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  struct COPY_THREAD_DATA *v50; // [rsp+58h] [rbp-A8h]
  CContentDropTarget *v51; // [rsp+60h] [rbp-A0h]
  int v52; // [rsp+68h] [rbp-98h] BYREF
  LPCITEMIDLIST pidl; // [rsp+70h] [rbp-90h] BYREF
  struct IPortableDevice *v54; // [rsp+78h] [rbp-88h]
  LPCITEMIDLIST v55; // [rsp+80h] [rbp-80h]
  LPITEMIDLIST v56; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  struct IPortableDeviceContent *v58; // [rsp+98h] [rbp-68h]
  LPITEMIDLIST v59[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v60[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v61[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v62[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR psz2[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  WCHAR pszFirst[264]; // [rsp+8F0h] [rbp+7F0h] BYREF
  WCHAR psz1[264]; // [rsp+B00h] [rbp+A00h] BYREF
  WCHAR Buffer[264]; // [rsp+D10h] [rbp+C10h] BYREF
  unsigned __int16 v67[264]; // [rsp+F20h] [rbp+E20h] BYREF
  unsigned __int16 v68[520]; // [rsp+1130h] [rbp+1030h] BYREF

  v8 = (struct COPY_THREAD_DATA *)a7;
  v9 = this;
  v55 = a5;
  v57 = a6;
  v10 = a7[557];
  v11 = 0;
  v58 = a3;
  v54 = a2;
  v51 = this;
  v59[0] = 0;
  pidl = 0;
  v49 = 0;
  v52 = 0;
  v56 = a4;
  v50 = (struct COPY_THREAD_DATA *)a7;
  memset_0(v60, 0, 0x208u);
  memset_0(v61, 0, 0x208u);
  ID = ILFindLastID(a4);
  v14 = CContentFolder::_IsValid(v13, ID);
  v15 = (_DWORD *)((char *)v10 + 104);
  v16 = v14;
  if ( v14 )
  {
    StringCchCopyW(
      psz2,
      0x104u,
      (const unsigned __int16 *)v14 + *(unsigned int *)((char *)v14 + 62) + *(unsigned int *)((char *)v14 + 66) + 37);
    if ( v10 )
    {
      v19 = 0;
      v20 = 0;
      while ( !*v15 )
      {
        ObjectID = CBaseFolder::_GetObjectID(*((CBaseFolder **)v51 + 10), psz2, v62, 0x104u);
        if ( ObjectID != -2147024726 )
          goto LABEL_12;
        if ( !v19 )
        {
          v19 = 1;
          v20 = 1;
          CProgressUI::_StartMarquee(v10);
        }
        if ( *v15 )
          break;
        Sleep(0x5DCu);
      }
      ObjectID = -2147023673;
LABEL_12:
      if ( v20 )
        CProgressUI::_StopMarquee(v10);
      if ( *v15 )
      {
        ObjectID = -2147023673;
        goto LABEL_19;
      }
      v9 = v51;
    }
    else
    {
      ObjectID = CBaseFolder::_GetObjectID(*((CBaseFolder **)v9 + 10), psz2, v62, 0x104u);
    }
    if ( ObjectID < 0 )
    {
LABEL_19:
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 73;
      goto LABEL_22;
    }
    if ( v10 )
    {
      v24 = 0;
      v25 = 0;
      while ( !*v15 )
      {
        ObjectID = CContentFolder::_GetDisplayName(*((CContentFolder **)v51 + 10), v62, v60, v18, &v49);
        if ( ObjectID != -2147024726 )
          goto LABEL_36;
        if ( !v24 )
        {
          v24 = 1;
          v25 = 1;
          CProgressUI::_StartMarquee(v10);
        }
        if ( *v15 )
          break;
        Sleep(0x5DCu);
      }
      ObjectID = -2147023673;
LABEL_36:
      if ( v25 )
        CProgressUI::_StopMarquee(v10);
      if ( *v15 )
      {
        ObjectID = -2147023673;
        goto LABEL_42;
      }
      v9 = v51;
    }
    else
    {
      ObjectID = CContentFolder::_GetDisplayName(*((CContentFolder **)v9 + 10), v62, v60, v18, &v49);
    }
    if ( ObjectID < 0 )
    {
LABEL_42:
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 74;
LABEL_22:
      v23 = (unsigned int)ObjectID;
LABEL_23:
      WPP_SF_d(v21[2], v22, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v23);
LABEL_24:
      v8 = v50;
      goto LABEL_65;
    }
    v26 = SHILCloneParent(v56, v59);
    ObjectID = v26;
    if ( v26 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 75;
      goto LABEL_49;
    }
    v26 = SHGetNameAndFlagsW(v55, 0);
    ObjectID = v26;
    if ( v26 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 76;
LABEL_49:
      v23 = (unsigned int)v26;
      goto LABEL_23;
    }
    v8 = v50;
    v27 = StrStrW(pszFirst, (PCWSTR)v50 + 1704);
    v28 = pszFirst;
    if ( v27 )
      v28 = v27;
    LoadStringW(g_hInst, 0xE4u, Buffer, 260);
    v29 = StringCchPrintfW(v68, 0x208u, Buffer, v28);
    ObjectID = v29;
    if ( v29 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_65;
      v31 = 77;
      goto LABEL_64;
    }
    v29 = CProgressUI::_ShowFileName(v10, v60, v68);
    ObjectID = v29;
    if ( v29 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_65;
      v31 = 78;
LABEL_64:
      WPP_SF_d(v30[2], v31, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v29);
      goto LABEL_65;
    }
    CContentFolder::_Name(v32, v16, v67, v33);
    v34 = v49;
    if ( v49 )
    {
      v35 = SHILClone(v55, &pidl);
      ObjectID = v35;
      if ( v35 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
            (unsigned int)v35);
        v11 = (ITEMIDLIST *)pidl;
        v36 = v50;
        goto LABEL_104;
      }
      v36 = v50;
      v11 = (ITEMIDLIST *)pidl;
      if ( *(_DWORD *)(*((_QWORD *)v50 + 4) + 16LL) )
      {
        v37 = 1;
        v38 = 1;
        while ( v37 )
        {
          v39 = ILFindLastID(v11);
          v41 = CContentFolder::_IsValid(v40, v39);
          if ( v41 )
          {
            StringCchCopyW(
              psz1,
              0x104u,
              (const unsigned __int16 *)v41
            + *(unsigned int *)((char *)v41 + 62)
            + *(unsigned int *)((char *)v41 + 66)
            + 37);
          }
          else
          {
            v37 = 0;
            if ( (*(int (__fastcall **)(_QWORD, ITEMIDLIST *, WCHAR *, __int64))(**((_QWORD **)v51 + 10) + 184LL))(
                   *((_QWORD *)v51 + 10),
                   v11,
                   psz1,
                   260) < 0 )
              break;
          }
          if ( !StrCmpIW(psz1, psz2) )
          {
            ObjectID = v38 - 2147483297;
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v43 = 80;
              v44 = (unsigned int)ObjectID;
              goto LABEL_87;
            }
            goto LABEL_104;
          }
          ILRemoveLastID(v11);
          v38 = 0;
        }
      }
      v45 = v54;
      goto LABEL_98;
    }
    v36 = v50;
    v45 = v54;
    CanCreateObject = CContentDropTarget::_CanCreateObject(
                        v9,
                        v67,
                        v57,
                        v54,
                        v58,
                        (CProgressUI **)v50,
                        v61,
                        0x104u,
                        &v52);
    ObjectID = CanCreateObject;
    if ( CanCreateObject < 0 )
    {
      if ( CanCreateObject != -2147024816 && CanCreateObject != -2147024713 )
        goto LABEL_104;
      if ( *((_DWORD *)v36 + 17) )
      {
LABEL_100:
        v47 = CContentDropTarget::_DeviceSideCopyItemOnDevice(
                v9,
                v45,
                v58,
                v55,
                v57,
                v62,
                (const unsigned __int16 *)((unsigned __int64)v61 & -(__int64)(v61[0] != 0)),
                v52,
                v10);
        ObjectID = v47;
        if ( v47 >= 0 )
          goto LABEL_105;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_104;
        v43 = 82;
        goto LABEL_96;
      }
      v47 = CContentDropTarget::_ConfirmReplace(v9, v45, v36, v60, v61, v56, v55, v34, v52);
      ObjectID = v47;
      if ( v47 < 0 )
      {
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v43 = 81;
LABEL_96:
          v44 = (unsigned int)v47;
LABEL_87:
          WPP_SF_d(v42[2], v43, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v44);
        }
LABEL_104:
        ObjectID = CContentDropTarget::_DisplayErrorMessageWithSkip(v51, ObjectID, v60, v36, v34);
        goto LABEL_105;
      }
    }
LABEL_98:
    if ( ObjectID == 1 )
      goto LABEL_105;
    v9 = v51;
    goto LABEL_100;
  }
  ObjectID = -2147418113;
LABEL_65:
  if ( v10 )
  {
    if ( *v15 )
      ObjectID = -2147023673;
    CProgressUI::_EndProgressUI(v10);
  }
  CContentDropTarget::_DisplayErrorMessage(
    v51,
    ObjectID,
    (const unsigned __int16 *)((unsigned __int64)v60 & -(__int64)(v60[0] != 0)),
    v8,
    v49);
LABEL_105:
  if ( v59[0] )
    ILFree(v59[0]);
  if ( v11 )
    ILFree(v11);
  if ( ObjectID < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      83,
      WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
      (unsigned int)ObjectID);
  return (unsigned int)ObjectID;
}

```

## disassembly

```asm
0x18003c074  push    rbp
0x18003c076  push    rbx
0x18003c077  push    rsi
0x18003c078  push    rdi
0x18003c079  push    r12
0x18003c07b  push    r13
0x18003c07d  push    r14
0x18003c07f  push    r15
0x18003c081  lea     rbp, [rsp-1458h]
0x18003c089  mov     eax, 1558h
0x18003c08e  call    _alloca_probe
0x18003c093  sub     rsp, rax
0x18003c096  mov     rax, cs:__security_cookie
0x18003c09d  xor     rax, rsp
0x18003c0a0  mov     [rbp+1490h+var_50], rax
0x18003c0a7  mov     rax, [rbp+1490h+arg_20]
0x18003c0ae  mov     rbx, r9
0x18003c0b1  mov     r14, [rbp+1490h+arg_30]
0x18003c0b8  mov     rsi, rcx
0x18003c0bb  mov     [rbp+1490h+var_1510], rax
0x18003c0bf  mov     edi, 208h
0x18003c0c4  mov     rax, [rbp+1490h+arg_28]
0x18003c0cb  mov     [rbp+1490h+var_1500], rax
0x18003c0cf  xor     eax, eax
0x18003c0d1  mov     r13, [r14+1168h]
0x18003c0d8  mov     r15d, eax
0x18003c0db  mov     [rbp+1490h+var_14F8], r8
0x18003c0df  mov     r8d, edi; Size
0x18003c0e2  mov     [rsp+1590h+var_1518], rdx
0x18003c0e7  xor     edx, edx; Val
0x18003c0e9  mov     [rsp+1590h+var_1530], rcx
0x18003c0ee  lea     rcx, [rbp+1490h+var_14E0]; void *
0x18003c0f2  mov     [rbp+1490h+var_14F0], rax
0x18003c0f6  mov     [rsp+1590h+pidl], rax
0x18003c0fb  mov     [rsp+1590h+var_1540], eax
0x18003c0ff  mov     [rsp+1590h+var_1528], eax
0x18003c103  mov     [rbp+1490h+var_1508], rbx
0x18003c107  mov     [rsp+1590h+var_1538], r14
0x18003c10c  call    memset_0
0x18003c111  mov     r8d, edi; Size
0x18003c114  lea     rcx, [rbp+1490h+var_12D0]; void *
0x18003c11b  xor     edx, edx; Val
0x18003c11d  call    memset_0
0x18003c122  mov     rcx, rbx; pidl
0x18003c125  call    cs:__imp_ILFindLastID
0x18003c12b  mov     rdx, rax; struct _ITEMIDLIST *
0x18003c12e  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18003c133  lea     rdi, [r13+68h]
0x18003c137  mov     r12, rax
0x18003c13a  mov     r10d, 800704C7h
0x18003c140  test    rax, rax
0x18003c143  jnz     short loc_18003C156
0x18003c145  mov     ebx, 8000FFFFh
0x18003c14a  lea     rsi, WPP_GLOBAL_Control
0x18003c151  jmp     loc_18003C4B2
0x18003c156  mov     ecx, [rax+42h]
0x18003c159  mov     edx, 104h; unsigned __int64
0x18003c15e  mov     eax, [rax+3Eh]
0x18003c161  add     rax, 25h ; '%'
0x18003c165  add     rcx, rax
0x18003c168  lea     r8, [r12+rcx*2]; unsigned __int16 *
0x18003c16c  lea     rcx, [rbp+1490h+psz2]; unsigned __int16 *
0x18003c173  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c178  test    r13, r13
0x18003c17b  jnz     short loc_18003C1A1
0x18003c17d  mov     rcx, [rsi+50h]; this
0x18003c181  lea     r8, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003c188  mov     r9d, 104h; unsigned int
0x18003c18e  lea     rdx, [rbp+1490h+psz2]; unsigned __int16 *
0x18003c195  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x18003c19a  mov     ebx, eax
0x18003c19c  jmp     loc_18003C233
0x18003c1a1  xor     r14d, r14d
0x18003c1a4  xor     esi, esi
0x18003c1a6  cmp     [rdi], r15d
0x18003c1a9  jnz     short loc_18003C223
0x18003c1ab  mov     rax, [rsp+1590h+var_1530]
0x18003c1b0  lea     r8, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003c1b7  mov     r9d, 104h; unsigned int
0x18003c1bd  lea     rdx, [rbp+1490h+psz2]; unsigned __int16 *
0x18003c1c4  mov     rcx, [rax+50h]; this
0x18003c1c8  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x18003c1cd  mov     ebx, eax
0x18003c1cf  cmp     eax, 800700AAh
0x18003c1d4  jnz     short loc_18003C201
0x18003c1d6  test    r14d, r14d
0x18003c1d9  jnz     short loc_18003C1EC
0x18003c1db  lea     eax, [r14+1]
0x18003c1df  mov     rcx, r13; this
0x18003c1e2  mov     r14d, eax
0x18003c1e5  mov     esi, eax
0x18003c1e7  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003c1ec  cmp     [rdi], r15d
0x18003c1ef  jnz     short loc_18003C223
0x18003c1f1  mov     ecx, 5DCh; dwMilliseconds
0x18003c1f6  call    cs:__imp_Sleep
0x18003c1fc  test    r14d, r14d
0x18003c1ff  jnz     short loc_18003C1A6
0x18003c201  mov     r10d, 800704C7h
0x18003c207  test    esi, esi
0x18003c209  jz      short loc_18003C219
0x18003c20b  mov     rcx, r13; this
0x18003c20e  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003c213  mov     r10d, 800704C7h
0x18003c219  cmp     [rdi], r15d
0x18003c21c  jz      short loc_18003C22E
0x18003c21e  mov     ebx, r10d
0x18003c221  jmp     short loc_18003C237
0x18003c223  mov     r10d, 800704C7h
0x18003c229  mov     ebx, r10d
0x18003c22c  jmp     short loc_18003C207
0x18003c22e  mov     rsi, [rsp+1590h+var_1530]
0x18003c233  test    ebx, ebx
0x18003c235  jns     short loc_18003C272
0x18003c237  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c23e  lea     rsi, WPP_GLOBAL_Control
0x18003c245  cmp     rcx, rsi
0x18003c248  jz      short loc_18003C268
0x18003c24a  test    byte ptr [rcx+1Ch], 2
0x18003c24e  jz      short loc_18003C268
0x18003c250  mov     edx, 49h ; 'I'
0x18003c255  mov     r9d, ebx
0x18003c258  mov     rcx, [rcx+10h]
0x18003c25c  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003c263  call    WPP_SF_d
0x18003c268  mov     r14, [rsp+1590h+var_1538]
0x18003c26d  jmp     loc_18003C4AC
0x18003c272  test    r13, r13
0x18003c275  jnz     short loc_18003C29C
0x18003c277  mov     rcx, [rsi+50h]; this
0x18003c27b  lea     rax, [rsp+1590h+var_1540]
0x18003c280  lea     r8, [rbp+1490h+var_14E0]; unsigned __int16 *
0x18003c284  mov     [rsp+1590h+var_1570], rax; int *
0x18003c289  lea     rdx, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003c290  call    ?_GetDisplayName@CContentFolder@@AEAAJPEBGPEAGIPEAH@Z; CContentFolder::_GetDisplayName(ushort const *,ushort *,uint,int *)
0x18003c295  mov     ebx, eax
0x18003c297  jmp     loc_18003C321
0x18003c29c  xor     r14d, r14d
0x18003c29f  xor     esi, esi
0x18003c2a1  cmp     [rdi], r15d
0x18003c2a4  jnz     short loc_18003C2FF
0x18003c2a6  lea     rax, [rsp+1590h+var_1540]
0x18003c2ab  mov     [rsp+1590h+var_1570], rax; int *
0x18003c2b0  lea     r8, [rbp+1490h+var_14E0]; unsigned __int16 *
0x18003c2b4  mov     rax, [rsp+1590h+var_1530]
0x18003c2b9  lea     rdx, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003c2c0  mov     rcx, [rax+50h]; this
0x18003c2c4  call    ?_GetDisplayName@CContentFolder@@AEAAJPEBGPEAGIPEAH@Z; CContentFolder::_GetDisplayName(ushort const *,ushort *,uint,int *)
0x18003c2c9  mov     ebx, eax
0x18003c2cb  cmp     eax, 800700AAh
0x18003c2d0  jnz     short loc_18003C304
0x18003c2d2  test    r14d, r14d
0x18003c2d5  jnz     short loc_18003C2E8
0x18003c2d7  lea     eax, [r14+1]
0x18003c2db  mov     rcx, r13; this
0x18003c2de  mov     r14d, eax
0x18003c2e1  mov     esi, eax
0x18003c2e3  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003c2e8  cmp     [rdi], r15d
0x18003c2eb  jnz     short loc_18003C2FF
0x18003c2ed  mov     ecx, 5DCh; dwMilliseconds
0x18003c2f2  call    cs:__imp_Sleep
0x18003c2f8  test    r14d, r14d
0x18003c2fb  jz      short loc_18003C304
0x18003c2fd  jmp     short loc_18003C2A1
0x18003c2ff  mov     ebx, 800704C7h
0x18003c304  test    esi, esi
0x18003c306  jz      short loc_18003C310
0x18003c308  mov     rcx, r13; this
0x18003c30b  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003c310  cmp     [rdi], r15d
0x18003c313  jz      short loc_18003C31C
0x18003c315  mov     ebx, 800704C7h
0x18003c31a  jmp     short loc_18003C325
0x18003c31c  mov     rsi, [rsp+1590h+var_1530]
0x18003c321  test    ebx, ebx
0x18003c323  jns     short loc_18003C350
0x18003c325  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c32c  lea     rsi, WPP_GLOBAL_Control
0x18003c333  cmp     rcx, rsi
0x18003c336  jz      loc_18003C268
0x18003c33c  test    byte ptr [rcx+1Ch], 2
0x18003c340  jz      loc_18003C268
0x18003c346  mov     edx, 4Ah ; 'J'
0x18003c34b  jmp     loc_18003C255
0x18003c350  mov     rcx, [rbp+1490h+var_1508]
0x18003c354  lea     rdx, [rbp+1490h+var_14F0]
0x18003c358  call    SHILCloneParent
0x18003c35d  mov     ebx, eax
0x18003c35f  test    eax, eax
0x18003c361  jns     short loc_18003C391
0x18003c363  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c36a  lea     rsi, WPP_GLOBAL_Control
0x18003c371  cmp     rcx, rsi
0x18003c374  jz      loc_18003C268
0x18003c37a  test    byte ptr [rcx+1Ch], 2
0x18003c37e  jz      loc_18003C268
0x18003c384  mov     edx, 4Bh ; 'K'
0x18003c389  mov     r9d, eax
0x18003c38c  jmp     loc_18003C258
0x18003c391  mov     rcx, [rbp+1490h+var_1510]; pidl
0x18003c395  lea     r8, [rbp+1490h+pszFirst]
0x18003c39c  mov     r9d, 104h
0x18003c3a2  mov     [rsp+1590h+var_1570], r15; __int64
0x18003c3a7  xor     edx, edx
0x18003c3a9  call    SHGetNameAndFlagsW
0x18003c3ae  mov     ebx, eax
0x18003c3b0  test    eax, eax
0x18003c3b2  jns     short loc_18003C3DC
0x18003c3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c3bb  lea     rsi, WPP_GLOBAL_Control
0x18003c3c2  cmp     rcx, rsi
0x18003c3c5  jz      loc_18003C268
0x18003c3cb  test    byte ptr [rcx+1Ch], 2
0x18003c3cf  jz      loc_18003C268
0x18003c3d5  mov     edx, 4Ch ; 'L'
0x18003c3da  jmp     short loc_18003C389
0x18003c3dc  mov     r14, [rsp+1590h+var_1538]
0x18003c3e1  lea     rcx, [rbp+1490h+pszFirst]; pszFirst
0x18003c3e8  lea     rdx, [r14+0D50h]; pszSrch
0x18003c3ef  call    cs:__imp_StrStrW
0x18003c3f5  mov     rcx, cs:g_hInst; hInstance
0x18003c3fc  lea     rbx, [rbp+1490h+pszFirst]
0x18003c403  mov     r9d, 104h; cchBufferMax
0x18003c409  lea     r8, [rbp+1490h+Buffer]; lpBuffer
0x18003c410  test    rax, rax
0x18003c413  cmovnz  rbx, rax
0x18003c417  lea     edx, [r9-20h]; uID
0x18003c41b  call    cs:__imp_LoadStringW
0x18003c421  mov     r9, rbx
0x18003c424  lea     r8, [rbp+1490h+Buffer]; unsigned __int16 *
0x18003c42b  mov     edx, 208h; unsigned __int64
0x18003c430  lea     rcx, [rbp+1490h+var_460]; unsigned __int16 *
0x18003c437  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c43c  mov     ebx, eax
0x18003c43e  test    eax, eax
0x18003c440  jns     short loc_18003C462
0x18003c442  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c449  lea     rsi, WPP_GLOBAL_Control
0x18003c450  cmp     rcx, rsi
0x18003c453  jz      short loc_18003C4AC
0x18003c455  test    byte ptr [rcx+1Ch], 2
0x18003c459  jz      short loc_18003C4AC
0x18003c45b  mov     edx, 4Dh ; 'M'
0x18003c460  jmp     short loc_18003C499
0x18003c462  lea     r8, [rbp+1490h+var_460]; unsigned __int16 *
0x18003c469  mov     rcx, r13; this
0x18003c46c  lea     rdx, [rbp+1490h+var_14E0]; unsigned __int16 *
0x18003c470  call    ?_ShowFileName@CProgressUI@@QEAAJPEBG0@Z; CProgressUI::_ShowFileName(ushort const *,ushort const *)
0x18003c475  mov     ebx, eax
0x18003c477  test    eax, eax
0x18003c479  jns     short loc_18003C4F3
0x18003c47b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c482  lea     rsi, WPP_GLOBAL_Control
0x18003c489  cmp     rcx, rsi
0x18003c48c  jz      short loc_18003C4AC
0x18003c48e  test    byte ptr [rcx+1Ch], 2
0x18003c492  jz      short loc_18003C4AC
0x18003c494  mov     edx, 4Eh ; 'N'
0x18003c499  mov     rcx, [rcx+10h]
0x18003c49d  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003c4a4  mov     r9d, eax
0x18003c4a7  call    WPP_SF_d
0x18003c4ac  mov     r10d, 800704C7h
0x18003c4b2  test    r13, r13
0x18003c4b5  jz      short loc_18003C4C6
0x18003c4b7  cmp     [rdi], r15d
0x18003c4ba  mov     rcx, r13; this
0x18003c4bd  cmovnz  ebx, r10d
0x18003c4c1  call    ?_EndProgressUI@CProgressUI@@QEAAJXZ; CProgressUI::_EndProgressUI(void)
0x18003c4c6  movzx   eax, [rbp+1490h+var_14E0]
0x18003c4ca  mov     r9, r14; struct COPY_THREAD_DATA *
0x18003c4cd  mov     rcx, [rsp+1590h+var_1530]; this
0x18003c4d2  neg     ax
0x18003c4d5  lea     rax, [rbp+1490h+var_14E0]
0x18003c4d9  mov     edx, ebx; int
0x18003c4db  sbb     r8, r8
0x18003c4de  and     r8, rax; unsigned __int16 *
0x18003c4e1  mov     eax, [rsp+1590h+var_1540]
0x18003c4e5  mov     dword ptr [rsp+1590h+var_1570], eax; int
0x18003c4e9  call    ?_DisplayErrorMessage@CContentDropTarget@@AEAAXJPEBGPEAVCOPY_THREAD_DATA@@H@Z; CContentDropTarget::_DisplayErrorMessage(long,ushort const *,COPY_THREAD_DATA *,int)
0x18003c4ee  jmp     loc_18003C801
0x18003c4f3  lea     r8, [rbp+1490h+var_670]; unsigned __int16 *
0x18003c4fa  mov     rdx, r12; struct CONTENTITEM *
0x18003c4fd  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x18003c502  mov     r14d, [rsp+1590h+var_1540]
0x18003c507  test    r14d, r14d
0x18003c50a  jz      loc_18003C664
0x18003c510  mov     rcx, [rbp+1490h+var_1510]
0x18003c514  lea     rdx, [rsp+1590h+pidl]
0x18003c519  call    SHILClone
0x18003c51e  mov     ebx, eax
0x18003c520  test    eax, eax
0x18003c522  jns     short loc_18003C564
0x18003c524  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c52b  lea     rsi, WPP_GLOBAL_Control
0x18003c532  cmp     rcx, rsi
0x18003c535  jz      short loc_18003C555
0x18003c537  test    byte ptr [rcx+1Ch], 2
0x18003c53b  jz      short loc_18003C555
  ... truncated ...
```
