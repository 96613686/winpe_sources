# CContentDropTarget::_DeviceSideMoveObject(IPortableDevice *,IPortableDeviceContent *,_ITEMIDLIST const *,_ITEMIDLIST const *,ushort const *,COPY_THREAD_DATA *)

- ea: `0x18003cce4`
- end: `0x18003d4ed`
- name: `?_DeviceSideMoveObject@CContentDropTarget@@AEAAJPEAUIPortableDevice@@PEAUIPortableDeviceContent@@PEFBU_ITEMIDLIST@@2PEBGPEAVCOPY_THREAD_DATA@@@Z`
- size: `2057`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, struct IPortableDevice *, struct IPortableDeviceContent *, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, const unsigned __int16 *, struct COPY_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation`

## callers

- `0x18003e1c0`

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
- `0x18003c878`
- `0x18003cce4`
- `0x180054524`
- `0x1800545c8`
- `0x180062f88`
- `0x18006b954`
- `0x180075530`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003ce66`
- `KERNEL32!Sleep` at `0x18003cf62`
- `KERNEL32!Sleep` at `0x18003ce66`
- `KERNEL32!Sleep` at `0x18003cf62`
- `SHLWAPI!StrCmpIW` at `0x18003d270`
- `SHLWAPI!StrCmpIW` at `0x18003d270`
- `SHLWAPI!StrStrW` at `0x18003d062`
- `SHLWAPI!StrStrW` at `0x18003d062`
- `USER32!LoadStringW` at `0x18003d08e`
- `USER32!LoadStringW` at `0x18003d08e`
- `SHELL32!__imp_ILFindLastID` at `0x18003cd95`
- `SHELL32!__imp_ILFindLastID` at `0x18003d1f8`
- `SHELL32!__imp_ILFindLastID` at `0x18003cd95`
- `SHELL32!__imp_ILFindLastID` at `0x18003d1f8`
- `SHELL32!__imp_ILRemoveLastID` at `0x18003d27d`
- `SHELL32!__imp_ILRemoveLastID` at `0x18003d27d`
- `SHELL32!__imp_ILFree` at `0x18003d486`
- `SHELL32!__imp_ILFree` at `0x18003d494`
- `SHELL32!__imp_ILFree` at `0x18003d486`
- `SHELL32!__imp_ILFree` at `0x18003d494`

## pseudocode

```c
__int64 __fastcall CContentDropTarget::_DeviceSideMoveObject(
        CContentDropTarget *this,
        struct IPortableDevice *a2,
        struct IPortableDeviceContent *a3,
        const struct _ITEMIDLIST *a4,
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
  int v34; // edi
  int v35; // eax
  int v36; // r14d
  int v37; // esi
  const struct _ITEMIDLIST *v38; // rax
  CContentFolder *v39; // rcx
  const struct CONTENTITEM *v40; // rax
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r9
  struct IPortableDevice *v44; // r12
  int CanCreateObject; // eax
  int v46; // eax
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  CContentDropTarget *v49; // [rsp+58h] [rbp-A8h]
  int v50; // [rsp+60h] [rbp-A0h] BYREF
  struct COPY_THREAD_DATA *v51; // [rsp+68h] [rbp-98h]
  LPCITEMIDLIST pidl; // [rsp+70h] [rbp-90h] BYREF
  struct IPortableDevice *v53; // [rsp+78h] [rbp-88h]
  LPCITEMIDLIST v54; // [rsp+80h] [rbp-80h]
  LPCVOID dwItem1; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v56; // [rsp+90h] [rbp-70h]
  struct IPortableDeviceContent *v57; // [rsp+98h] [rbp-68h]
  LPITEMIDLIST v58[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v59[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v60[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v61[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR psz2[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  WCHAR pszFirst[264]; // [rsp+8F0h] [rbp+7F0h] BYREF
  WCHAR psz1[264]; // [rsp+B00h] [rbp+A00h] BYREF
  WCHAR Buffer[264]; // [rsp+D10h] [rbp+C10h] BYREF
  unsigned __int16 v66[264]; // [rsp+F20h] [rbp+E20h] BYREF
  unsigned __int16 v67[520]; // [rsp+1130h] [rbp+1030h] BYREF

  v8 = (struct COPY_THREAD_DATA *)a7;
  v9 = this;
  v54 = a5;
  v56 = a6;
  v10 = a7[557];
  v11 = 0;
  v57 = a3;
  v53 = a2;
  v49 = this;
  v58[0] = 0;
  pidl = 0;
  v48 = 0;
  v50 = 0;
  dwItem1 = a4;
  v51 = (struct COPY_THREAD_DATA *)a7;
  memset_0(v59, 0, 0x208u);
  memset_0(v60, 0, 0x208u);
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
        ObjectID = CBaseFolder::_GetObjectID(*((CBaseFolder **)v49 + 10), psz2, v61, 0x104u);
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
      v9 = v49;
    }
    else
    {
      ObjectID = CBaseFolder::_GetObjectID(*((CBaseFolder **)v9 + 10), psz2, v61, 0x104u);
    }
    if ( ObjectID < 0 )
    {
LABEL_19:
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 45;
      goto LABEL_22;
    }
    if ( v10 )
    {
      v24 = 0;
      v25 = 0;
      while ( !*v15 )
      {
        ObjectID = CContentFolder::_GetDisplayName(*((CContentFolder **)v49 + 10), v61, v59, v18, &v48);
        if ( ObjectID != -2147024726 )
          goto LABEL_35;
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
LABEL_35:
      if ( v25 )
        CProgressUI::_StopMarquee(v10);
      if ( *v15 )
      {
        ObjectID = -2147023673;
        goto LABEL_41;
      }
      v9 = v49;
    }
    else
    {
      ObjectID = CContentFolder::_GetDisplayName(*((CContentFolder **)v9 + 10), v61, v59, v18, &v48);
    }
    if ( ObjectID < 0 )
    {
LABEL_41:
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 46;
LABEL_22:
      v23 = (unsigned int)ObjectID;
LABEL_23:
      WPP_SF_d(v21[2], v22, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v23);
LABEL_24:
      v8 = v51;
      goto LABEL_64;
    }
    v26 = SHILCloneParent(dwItem1, v58);
    ObjectID = v26;
    if ( v26 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 47;
      goto LABEL_48;
    }
    v26 = SHGetNameAndFlagsW(v54, 0);
    ObjectID = v26;
    if ( v26 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v22 = 48;
LABEL_48:
      v23 = (unsigned int)v26;
      goto LABEL_23;
    }
    v8 = v51;
    v27 = StrStrW(pszFirst, (PCWSTR)v51 + 1704);
    v28 = pszFirst;
    if ( v27 )
      v28 = v27;
    LoadStringW(g_hInst, 0xE4u, Buffer, 260);
    v29 = StringCchPrintfW(v67, 0x208u, Buffer, v28);
    ObjectID = v29;
    if ( v29 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_64;
      v31 = 49;
      goto LABEL_63;
    }
    v29 = CProgressUI::_ShowFileName(v10, v59, v67);
    ObjectID = v29;
    if ( v29 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_64;
      v31 = 50;
LABEL_63:
      WPP_SF_d(v30[2], v31, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v29);
      goto LABEL_64;
    }
    CContentFolder::_Name(v32, v16, v66, v33);
    v34 = v48;
    if ( v48 )
    {
      v35 = SHILClone(v54, &pidl);
      ObjectID = v35;
      if ( v35 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
            (unsigned int)v35);
        v11 = (ITEMIDLIST *)pidl;
        goto LABEL_103;
      }
      v11 = (ITEMIDLIST *)pidl;
      if ( *(_DWORD *)(*((_QWORD *)v8 + 4) + 16LL) )
      {
        v36 = 1;
        v37 = 1;
        while ( v36 )
        {
          v38 = ILFindLastID(v11);
          v40 = CContentFolder::_IsValid(v39, v38);
          if ( v40 )
          {
            StringCchCopyW(
              psz1,
              0x104u,
              (const unsigned __int16 *)v40
            + *(unsigned int *)((char *)v40 + 62)
            + *(unsigned int *)((char *)v40 + 66)
            + 37);
          }
          else
          {
            v36 = 0;
            if ( (*(int (__fastcall **)(_QWORD, ITEMIDLIST *, WCHAR *, __int64))(**((_QWORD **)v49 + 10) + 184LL))(
                   *((_QWORD *)v49 + 10),
                   v11,
                   psz1,
                   260) < 0 )
              break;
          }
          if ( !StrCmpIW(psz1, psz2) )
          {
            ObjectID = v37 - 2147483297;
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v42 = 52;
              v43 = (unsigned int)ObjectID;
              goto LABEL_86;
            }
            goto LABEL_103;
          }
          ILRemoveLastID(v11);
          v37 = 0;
        }
      }
      v44 = v53;
    }
    else
    {
      v44 = v53;
      CanCreateObject = CContentDropTarget::_CanCreateObject(
                          v9,
                          v66,
                          v56,
                          v53,
                          v57,
                          (CProgressUI **)v8,
                          v60,
                          0x104u,
                          &v50);
      ObjectID = CanCreateObject;
      if ( CanCreateObject < 0 )
      {
        if ( CanCreateObject != -2147024816 && CanCreateObject != -2147024713 )
          goto LABEL_103;
        if ( *((_DWORD *)v8 + 17) )
          goto LABEL_99;
        v46 = CContentDropTarget::_ConfirmReplace(v9, v44, v8, v59, v60, (LPITEMIDLIST)dwItem1, v54, v34, v50);
        ObjectID = v46;
        if ( v46 < 0 )
        {
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v42 = 53;
            goto LABEL_95;
          }
LABEL_103:
          ObjectID = CContentDropTarget::_DisplayErrorMessageWithSkip(v49, ObjectID, v59, v51, v34);
          goto LABEL_105;
        }
      }
    }
    if ( ObjectID == 1 )
      goto LABEL_105;
    v9 = v49;
LABEL_99:
    v46 = CContentDropTarget::_DeviceSideMoveItemOnDevice(
            v9,
            v44,
            v57,
            v54,
            v56,
            v61,
            (const unsigned __int16 *)((unsigned __int64)v60 & -(__int64)(v60[0] != 0)),
            v50,
            v10);
    ObjectID = v46;
    if ( v46 >= 0 )
    {
      ChangeNotify(v34 != 0 ? 16 : 4, 0, dwItem1, 0);
      goto LABEL_105;
    }
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v42 = 54;
LABEL_95:
      v43 = (unsigned int)v46;
LABEL_86:
      WPP_SF_d(v41[2], v42, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v43);
      goto LABEL_103;
    }
    goto LABEL_103;
  }
  ObjectID = -2147418113;
LABEL_64:
  if ( v10 )
  {
    if ( *v15 )
      ObjectID = -2147023673;
    CProgressUI::_EndProgressUI(v10);
  }
  CContentDropTarget::_DisplayErrorMessage(
    v49,
    ObjectID,
    (const unsigned __int16 *)((unsigned __int64)v59 & -(__int64)(v59[0] != 0)),
    v8,
    v48);
LABEL_105:
  if ( v58[0] )
    ILFree(v58[0]);
  if ( v11 )
    ILFree(v11);
  if ( ObjectID < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
      (unsigned int)ObjectID);
  return (unsigned int)ObjectID;
}

```

## disassembly

```asm
0x18003cce4  push    rbp
0x18003cce6  push    rbx
0x18003cce7  push    rsi
0x18003cce8  push    rdi
0x18003cce9  push    r12
0x18003cceb  push    r13
0x18003cced  push    r14
0x18003ccef  push    r15
0x18003ccf1  lea     rbp, [rsp-1458h]
0x18003ccf9  mov     eax, 1558h
0x18003ccfe  call    _alloca_probe
0x18003cd03  sub     rsp, rax
0x18003cd06  mov     rax, cs:__security_cookie
0x18003cd0d  xor     rax, rsp
0x18003cd10  mov     [rbp+1490h+var_50], rax
0x18003cd17  mov     rax, [rbp+1490h+arg_20]
0x18003cd1e  mov     rbx, r9
0x18003cd21  mov     r14, [rbp+1490h+arg_30]
0x18003cd28  mov     rsi, rcx
0x18003cd2b  mov     [rbp+1490h+var_1510], rax
0x18003cd2f  mov     edi, 208h
0x18003cd34  mov     rax, [rbp+1490h+arg_28]
0x18003cd3b  mov     [rbp+1490h+var_1500], rax
0x18003cd3f  xor     eax, eax
0x18003cd41  mov     r13, [r14+1168h]
0x18003cd48  mov     r15d, eax
0x18003cd4b  mov     [rbp+1490h+var_14F8], r8
0x18003cd4f  mov     r8d, edi; Size
0x18003cd52  mov     [rsp+1590h+var_1518], rdx
0x18003cd57  xor     edx, edx; Val
0x18003cd59  mov     [rsp+1590h+var_1538], rcx
0x18003cd5e  lea     rcx, [rbp+1490h+var_14E0]; void *
0x18003cd62  mov     [rbp+1490h+var_14F0], rax
0x18003cd66  mov     [rsp+1590h+pidl], rax
0x18003cd6b  mov     [rsp+1590h+var_1540], eax
0x18003cd6f  mov     [rsp+1590h+var_1530], eax
0x18003cd73  mov     [rbp+1490h+dwItem1], rbx
0x18003cd77  mov     [rsp+1590h+var_1528], r14
0x18003cd7c  call    memset_0
0x18003cd81  mov     r8d, edi; Size
0x18003cd84  lea     rcx, [rbp+1490h+var_12D0]; void *
0x18003cd8b  xor     edx, edx; Val
0x18003cd8d  call    memset_0
0x18003cd92  mov     rcx, rbx; pidl
0x18003cd95  call    cs:__imp_ILFindLastID
0x18003cd9b  mov     rdx, rax; struct _ITEMIDLIST *
0x18003cd9e  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18003cda3  lea     rdi, [r13+68h]
0x18003cda7  mov     r12, rax
0x18003cdaa  mov     r10d, 800704C7h
0x18003cdb0  test    rax, rax
0x18003cdb3  jnz     short loc_18003CDC6
0x18003cdb5  mov     ebx, 8000FFFFh
0x18003cdba  lea     rsi, WPP_GLOBAL_Control
0x18003cdc1  jmp     loc_18003D125
0x18003cdc6  mov     ecx, [rax+42h]
0x18003cdc9  mov     edx, 104h; unsigned __int64
0x18003cdce  mov     eax, [rax+3Eh]
0x18003cdd1  add     rax, 25h ; '%'
0x18003cdd5  add     rcx, rax
0x18003cdd8  lea     r8, [r12+rcx*2]; unsigned __int16 *
0x18003cddc  lea     rcx, [rbp+1490h+psz2]; unsigned __int16 *
0x18003cde3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003cde8  test    r13, r13
0x18003cdeb  jnz     short loc_18003CE11
0x18003cded  mov     rcx, [rsi+50h]; this
0x18003cdf1  lea     r8, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003cdf8  mov     r9d, 104h; unsigned int
0x18003cdfe  lea     rdx, [rbp+1490h+psz2]; unsigned __int16 *
0x18003ce05  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x18003ce0a  mov     ebx, eax
0x18003ce0c  jmp     loc_18003CEA3
0x18003ce11  xor     r14d, r14d
0x18003ce14  xor     esi, esi
0x18003ce16  cmp     [rdi], r15d
0x18003ce19  jnz     short loc_18003CE93
0x18003ce1b  mov     rax, [rsp+1590h+var_1538]
0x18003ce20  lea     r8, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003ce27  mov     r9d, 104h; unsigned int
0x18003ce2d  lea     rdx, [rbp+1490h+psz2]; unsigned __int16 *
0x18003ce34  mov     rcx, [rax+50h]; this
0x18003ce38  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x18003ce3d  mov     ebx, eax
0x18003ce3f  cmp     eax, 800700AAh
0x18003ce44  jnz     short loc_18003CE71
0x18003ce46  test    r14d, r14d
0x18003ce49  jnz     short loc_18003CE5C
0x18003ce4b  lea     eax, [r14+1]
0x18003ce4f  mov     rcx, r13; this
0x18003ce52  mov     r14d, eax
0x18003ce55  mov     esi, eax
0x18003ce57  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003ce5c  cmp     [rdi], r15d
0x18003ce5f  jnz     short loc_18003CE93
0x18003ce61  mov     ecx, 5DCh; dwMilliseconds
0x18003ce66  call    cs:__imp_Sleep
0x18003ce6c  test    r14d, r14d
0x18003ce6f  jnz     short loc_18003CE16
0x18003ce71  mov     r10d, 800704C7h
0x18003ce77  test    esi, esi
0x18003ce79  jz      short loc_18003CE89
0x18003ce7b  mov     rcx, r13; this
0x18003ce7e  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003ce83  mov     r10d, 800704C7h
0x18003ce89  cmp     [rdi], r15d
0x18003ce8c  jz      short loc_18003CE9E
0x18003ce8e  mov     ebx, r10d
0x18003ce91  jmp     short loc_18003CEA7
0x18003ce93  mov     r10d, 800704C7h
0x18003ce99  mov     ebx, r10d
0x18003ce9c  jmp     short loc_18003CE77
0x18003ce9e  mov     rsi, [rsp+1590h+var_1538]
0x18003cea3  test    ebx, ebx
0x18003cea5  jns     short loc_18003CEE2
0x18003cea7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ceae  lea     rsi, WPP_GLOBAL_Control
0x18003ceb5  cmp     rcx, rsi
0x18003ceb8  jz      short loc_18003CED8
0x18003ceba  test    byte ptr [rcx+1Ch], 2
0x18003cebe  jz      short loc_18003CED8
0x18003cec0  mov     edx, 2Dh ; '-'
0x18003cec5  mov     r9d, ebx
0x18003cec8  mov     rcx, [rcx+10h]
0x18003cecc  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003ced3  call    WPP_SF_d
0x18003ced8  mov     r14, [rsp+1590h+var_1528]
0x18003cedd  jmp     loc_18003D11F
0x18003cee2  test    r13, r13
0x18003cee5  jnz     short loc_18003CF0C
0x18003cee7  mov     rcx, [rsi+50h]; this
0x18003ceeb  lea     rax, [rsp+1590h+var_1540]
0x18003cef0  lea     r8, [rbp+1490h+var_14E0]; unsigned __int16 *
0x18003cef4  mov     [rsp+1590h+var_1570], rax; int *
0x18003cef9  lea     rdx, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003cf00  call    ?_GetDisplayName@CContentFolder@@AEAAJPEBGPEAGIPEAH@Z; CContentFolder::_GetDisplayName(ushort const *,ushort *,uint,int *)
0x18003cf05  mov     ebx, eax
0x18003cf07  jmp     loc_18003CF91
0x18003cf0c  xor     r14d, r14d
0x18003cf0f  xor     esi, esi
0x18003cf11  cmp     [rdi], r15d
0x18003cf14  jnz     short loc_18003CF6F
0x18003cf16  lea     rax, [rsp+1590h+var_1540]
0x18003cf1b  mov     [rsp+1590h+var_1570], rax; int *
0x18003cf20  lea     r8, [rbp+1490h+var_14E0]; unsigned __int16 *
0x18003cf24  mov     rax, [rsp+1590h+var_1538]
0x18003cf29  lea     rdx, [rbp+1490h+var_10C0]; unsigned __int16 *
0x18003cf30  mov     rcx, [rax+50h]; this
0x18003cf34  call    ?_GetDisplayName@CContentFolder@@AEAAJPEBGPEAGIPEAH@Z; CContentFolder::_GetDisplayName(ushort const *,ushort *,uint,int *)
0x18003cf39  mov     ebx, eax
0x18003cf3b  cmp     eax, 800700AAh
0x18003cf40  jnz     short loc_18003CF74
0x18003cf42  test    r14d, r14d
0x18003cf45  jnz     short loc_18003CF58
0x18003cf47  lea     eax, [r14+1]
0x18003cf4b  mov     rcx, r13; this
0x18003cf4e  mov     r14d, eax
0x18003cf51  mov     esi, eax
0x18003cf53  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003cf58  cmp     [rdi], r15d
0x18003cf5b  jnz     short loc_18003CF6F
0x18003cf5d  mov     ecx, 5DCh; dwMilliseconds
0x18003cf62  call    cs:__imp_Sleep
0x18003cf68  test    r14d, r14d
0x18003cf6b  jz      short loc_18003CF74
0x18003cf6d  jmp     short loc_18003CF11
0x18003cf6f  mov     ebx, 800704C7h
0x18003cf74  test    esi, esi
0x18003cf76  jz      short loc_18003CF80
0x18003cf78  mov     rcx, r13; this
0x18003cf7b  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003cf80  cmp     [rdi], r15d
0x18003cf83  jz      short loc_18003CF8C
0x18003cf85  mov     ebx, 800704C7h
0x18003cf8a  jmp     short loc_18003CF95
0x18003cf8c  mov     rsi, [rsp+1590h+var_1538]
0x18003cf91  test    ebx, ebx
0x18003cf93  jns     short loc_18003CFC0
0x18003cf95  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf9c  lea     rsi, WPP_GLOBAL_Control
0x18003cfa3  cmp     rcx, rsi
0x18003cfa6  jz      loc_18003CED8
0x18003cfac  test    byte ptr [rcx+1Ch], 2
0x18003cfb0  jz      loc_18003CED8
0x18003cfb6  mov     edx, 2Eh ; '.'
0x18003cfbb  jmp     loc_18003CEC5
0x18003cfc0  mov     rcx, [rbp+1490h+dwItem1]
0x18003cfc4  lea     rdx, [rbp+1490h+var_14F0]
0x18003cfc8  call    SHILCloneParent
0x18003cfcd  mov     ebx, eax
0x18003cfcf  test    eax, eax
0x18003cfd1  jns     short loc_18003D001
0x18003cfd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfda  lea     rsi, WPP_GLOBAL_Control
0x18003cfe1  cmp     rcx, rsi
0x18003cfe4  jz      loc_18003CED8
0x18003cfea  test    byte ptr [rcx+1Ch], 2
0x18003cfee  jz      loc_18003CED8
0x18003cff4  mov     edx, 2Fh ; '/'
0x18003cff9  mov     r9d, eax
0x18003cffc  jmp     loc_18003CEC8
0x18003d001  mov     rcx, [rbp+1490h+var_1510]; pidl
0x18003d005  lea     r8, [rbp+1490h+pszFirst]
0x18003d00c  mov     r9d, 104h
0x18003d012  mov     [rsp+1590h+var_1570], r15; __int64
0x18003d017  mov     edx, 0C000h
0x18003d01c  call    SHGetNameAndFlagsW
0x18003d021  mov     ebx, eax
0x18003d023  test    eax, eax
0x18003d025  jns     short loc_18003D04F
0x18003d027  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d02e  lea     rsi, WPP_GLOBAL_Control
0x18003d035  cmp     rcx, rsi
0x18003d038  jz      loc_18003CED8
0x18003d03e  test    byte ptr [rcx+1Ch], 2
0x18003d042  jz      loc_18003CED8
0x18003d048  mov     edx, 30h ; '0'
0x18003d04d  jmp     short loc_18003CFF9
0x18003d04f  mov     r14, [rsp+1590h+var_1528]
0x18003d054  lea     rcx, [rbp+1490h+pszFirst]; pszFirst
0x18003d05b  lea     rdx, [r14+0D50h]; pszSrch
0x18003d062  call    cs:__imp_StrStrW
0x18003d068  mov     rcx, cs:g_hInst; hInstance
0x18003d06f  lea     rbx, [rbp+1490h+pszFirst]
0x18003d076  mov     r9d, 104h; cchBufferMax
0x18003d07c  lea     r8, [rbp+1490h+Buffer]; lpBuffer
0x18003d083  test    rax, rax
0x18003d086  cmovnz  rbx, rax
0x18003d08a  lea     edx, [r9-20h]; uID
0x18003d08e  call    cs:__imp_LoadStringW
0x18003d094  mov     r9, rbx
0x18003d097  lea     r8, [rbp+1490h+Buffer]; unsigned __int16 *
0x18003d09e  mov     edx, 208h; unsigned __int64
0x18003d0a3  lea     rcx, [rbp+1490h+var_460]; unsigned __int16 *
0x18003d0aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d0af  mov     ebx, eax
0x18003d0b1  test    eax, eax
0x18003d0b3  jns     short loc_18003D0D5
0x18003d0b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0bc  lea     rsi, WPP_GLOBAL_Control
0x18003d0c3  cmp     rcx, rsi
0x18003d0c6  jz      short loc_18003D11F
0x18003d0c8  test    byte ptr [rcx+1Ch], 2
0x18003d0cc  jz      short loc_18003D11F
0x18003d0ce  mov     edx, 31h ; '1'
0x18003d0d3  jmp     short loc_18003D10C
0x18003d0d5  lea     r8, [rbp+1490h+var_460]; unsigned __int16 *
0x18003d0dc  mov     rcx, r13; this
0x18003d0df  lea     rdx, [rbp+1490h+var_14E0]; unsigned __int16 *
0x18003d0e3  call    ?_ShowFileName@CProgressUI@@QEAAJPEBG0@Z; CProgressUI::_ShowFileName(ushort const *,ushort const *)
0x18003d0e8  mov     ebx, eax
0x18003d0ea  test    eax, eax
0x18003d0ec  jns     short loc_18003D166
0x18003d0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0f5  lea     rsi, WPP_GLOBAL_Control
0x18003d0fc  cmp     rcx, rsi
0x18003d0ff  jz      short loc_18003D11F
0x18003d101  test    byte ptr [rcx+1Ch], 2
0x18003d105  jz      short loc_18003D11F
0x18003d107  mov     edx, 32h ; '2'
0x18003d10c  mov     rcx, [rcx+10h]
0x18003d110  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003d117  mov     r9d, eax
0x18003d11a  call    WPP_SF_d
0x18003d11f  mov     r10d, 800704C7h
0x18003d125  test    r13, r13
0x18003d128  jz      short loc_18003D139
0x18003d12a  cmp     [rdi], r15d
0x18003d12d  mov     rcx, r13; this
0x18003d130  cmovnz  ebx, r10d
0x18003d134  call    ?_EndProgressUI@CProgressUI@@QEAAJXZ; CProgressUI::_EndProgressUI(void)
0x18003d139  movzx   eax, [rbp+1490h+var_14E0]
0x18003d13d  mov     r9, r14; struct COPY_THREAD_DATA *
0x18003d140  mov     rcx, [rsp+1590h+var_1538]; this
0x18003d145  neg     ax
0x18003d148  lea     rax, [rbp+1490h+var_14E0]
0x18003d14c  mov     edx, ebx; int
0x18003d14e  sbb     r8, r8
0x18003d151  and     r8, rax; unsigned __int16 *
0x18003d154  mov     eax, [rsp+1590h+var_1540]
0x18003d158  mov     dword ptr [rsp+1590h+var_1570], eax; int
0x18003d15c  call    ?_DisplayErrorMessage@CContentDropTarget@@AEAAXJPEBGPEAVCOPY_THREAD_DATA@@H@Z; CContentDropTarget::_DisplayErrorMessage(long,ushort const *,COPY_THREAD_DATA *,int)
0x18003d161  jmp     loc_18003D47D
0x18003d166  lea     r8, [rbp+1490h+var_670]; unsigned __int16 *
0x18003d16d  mov     rdx, r12; struct CONTENTITEM *
0x18003d170  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x18003d175  mov     edi, [rsp+1590h+var_1540]
0x18003d179  test    edi, edi
0x18003d17b  jz      loc_18003D2CE
0x18003d181  mov     rcx, [rbp+1490h+var_1510]
0x18003d185  lea     rdx, [rsp+1590h+pidl]
0x18003d18a  call    SHILClone
0x18003d18f  mov     ebx, eax
0x18003d191  test    eax, eax
0x18003d193  jns     short loc_18003D1D0
0x18003d195  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d19c  lea     rsi, WPP_GLOBAL_Control
0x18003d1a3  cmp     rcx, rsi
0x18003d1a6  jz      short loc_18003D1C6
0x18003d1a8  test    byte ptr [rcx+1Ch], 2
0x18003d1ac  jz      short loc_18003D1C6
  ... truncated ...
```
