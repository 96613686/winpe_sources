# CStorageFolder::CompareIDs(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x18000a470`
- end: `0x18000a8cb`
- name: `?CompareIDs@CStorageFolder@@UEAAJ_JPEFBU_ITEMIDLIST@@1@Z`
- size: `1115`
- prototype: `int(CStorageFolder *__hidden this, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180009890`
- `0x18000a470`
- `0x180021cec`
- `0x18002e224`
- `0x18002ff5c`
- `0x180035590`
- `0x180039dd4`
- `0x1800671e8`
- `0x18007559c`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000a530`
- `SHLWAPI!PathFindFileNameW` at `0x18000a580`
- `SHLWAPI!PathFindFileNameW` at `0x18000a530`
- `SHLWAPI!PathFindFileNameW` at `0x18000a580`
- `SHLWAPI!StrCmpW` at `0x18000a834`
- `SHLWAPI!StrCmpW` at `0x18000a834`
- `SHLWAPI!StrCmpLogicalW` at `0x18000a853`
- `SHLWAPI!StrCmpLogicalW` at `0x18000a86f`
- `SHLWAPI!StrCmpLogicalW` at `0x18000a853`
- `SHLWAPI!StrCmpLogicalW` at `0x18000a86f`

## pseudocode

```c
__int64 __fastcall CStorageFolder::CompareIDs(
        CStorageFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST *a3,
        const struct _ITEMIDLIST *a4)
{
  const struct STORAGEITEM *v8; // rsi
  CStorageFolder *v9; // rcx
  const struct STORAGEITEM *v10; // rax
  const struct STORAGEITEM *v11; // rdi
  unsigned int FreeSpace; // ebx
  __int64 v13; // r14
  WCHAR *v14; // r8
  __int64 v15; // rbx
  WCHAR *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  WCHAR *v19; // rcx
  __int64 v20; // rcx
  WCHAR *v21; // r8
  __int64 v22; // rdx
  WCHAR *v23; // rax
  WCHAR *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  WCHAR *v27; // r9
  WCHAR *v28; // rax
  WCHAR *v29; // rcx
  WCHAR *v30; // rcx
  WCHAR *v31; // rax
  WCHAR *v32; // rcx
  PVOID *v33; // rcx
  int v34; // eax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  unsigned __int16 v39; // ax
  unsigned __int64 v40; // rax
  CStorageFolder *v41; // rcx
  unsigned int v42; // r9d
  int v43; // eax
  unsigned __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v45; // [rsp+38h] [rbp-C8h] BYREF
  const struct _ITEMIDLIST *v46; // [rsp+40h] [rbp-C0h]
  WCHAR v47[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v49[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR v50[264]; // [rsp+680h] [rbp+580h] BYREF
  WCHAR psz2[264]; // [rsp+890h] [rbp+790h] BYREF
  WCHAR psz1[264]; // [rsp+AA0h] [rbp+9A0h] BYREF

  v46 = a4;
  v8 = CStorageFolder::_IsValid(this, a3);
  v10 = CStorageFolder::_IsValid(v9, a4);
  v11 = v10;
  if ( !v8 || !v10 )
    return (unsigned int)-2147024809;
  v13 = 2147483646;
  v14 = (WCHAR *)((char *)v8 + 54);
  v15 = 260;
  v16 = pszPath;
  v17 = 2147483646;
  v18 = 260;
  do
  {
    if ( !v17 )
      break;
    if ( !*v14 )
      break;
    *v16++ = *v14++;
    --v17;
    --v18;
  }
  while ( v18 );
  v19 = v16 - 1;
  if ( v18 )
    v19 = v16;
  *v19 = 0;
  PathFindFileNameW(pszPath);
  v20 = 2147483646;
  v21 = (WCHAR *)((char *)v11 + 54);
  v22 = 260;
  v23 = v47;
  do
  {
    if ( !v20 )
      break;
    if ( !*v21 )
      break;
    *v23++ = *v21++;
    --v20;
    --v22;
  }
  while ( v22 );
  v24 = v23 - 1;
  if ( v22 )
    v24 = v23;
  *v24 = 0;
  PathFindFileNameW(v47);
  v25 = 2147483646;
  v26 = 260;
  v27 = (WCHAR *)((char *)v8 + 2 * *(unsigned int *)((char *)v8 + 38) + 54);
  v28 = v50;
  do
  {
    if ( !v25 )
      break;
    if ( !*v27 )
      break;
    *v28++ = *v27++;
    --v25;
    --v26;
  }
  while ( v26 );
  v29 = v28 - 1;
  if ( v26 )
    v29 = v28;
  *v29 = 0;
  v30 = (WCHAR *)((char *)v11 + 2 * *(unsigned int *)((char *)v11 + 38) + 54);
  v31 = v49;
  do
  {
    if ( !v13 )
      break;
    if ( !*v30 )
      break;
    *v31++ = *v30++;
    --v13;
    --v15;
  }
  while ( v15 );
  v32 = v31 - 1;
  if ( v15 )
    v32 = v31;
  *v32 = 0;
  v33 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
        (unsigned int)pszPath,
        (__int64)v50);
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 0x40) != 0 )
      WPP_SF_SS(
        (unsigned int)v33[2],
        23,
        (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
        (unsigned int)v47,
        (__int64)v49);
  }
  if ( (*((_BYTE *)v8 + 10) & 2) != 0 )
  {
    if ( (*((_BYTE *)v11 + 10) & 2) == 0 )
    {
LABEL_36:
      LOWORD(v34) = -1;
      return (unsigned __int16)v34;
    }
  }
  else if ( (*((_BYTE *)v11 + 10) & 2) != 0 )
  {
    goto LABEL_40;
  }
  if ( (unsigned __int16)a2 == 1 )
  {
    CStorageFolder::_Type((CStorageFolder *)v33, v8, psz1, (unsigned int)v27);
    CStorageFolder::_Type(v41, v11, psz2, v42);
    v34 = StrCmpW(psz1, psz2);
    if ( v34 )
      return (unsigned __int16)v34;
    goto LABEL_56;
  }
  if ( (unsigned __int16)a2 == 2 )
  {
    v40 = *(_QWORD *)((char *)v8 + 18);
    if ( v40 < *(_QWORD *)((char *)v11 + 18) )
      goto LABEL_36;
    if ( v40 > *(_QWORD *)((char *)v11 + 18) )
      goto LABEL_40;
    goto LABEL_56;
  }
  if ( (unsigned __int16)a2 != 3 )
    goto LABEL_56;
  v44 = 0;
  v45 = 0;
  FreeSpace = CStorageFolder::_GetFreeSpace((CStorageFolder *)((char *)this - 16), v8, &v44);
  if ( (FreeSpace & 0x80000000) != 0 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v37 = 24;
LABEL_48:
      v38 = FreeSpace;
LABEL_49:
      WPP_SF_d(v36[2], v37, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v38);
      return FreeSpace;
    }
    return FreeSpace;
  }
  FreeSpace = CStorageFolder::_GetFreeSpace((CStorageFolder *)((char *)this - 16), v11, &v45);
  if ( (FreeSpace & 0x80000000) == 0 )
  {
    if ( v44 < v45 )
      goto LABEL_36;
    if ( v44 > v45 )
      goto LABEL_40;
LABEL_56:
    if ( (a2 & 0x10000000) == 0 )
    {
      if ( (a2 & 0x80000000) != 0 )
      {
        v39 = *((_WORD *)v11 + 2);
        if ( *((_WORD *)v8 + 2) < v39 )
          goto LABEL_36;
        if ( *((_WORD *)v8 + 2) <= v39 )
        {
          v34 = memcmp_0(v8, v11, *((unsigned __int16 *)v8 + 2));
          goto LABEL_68;
        }
LABEL_40:
        LOWORD(v34) = 1;
        return (unsigned __int16)v34;
      }
      v34 = StrCmpLogicalW(pszPath, v47);
      if ( v34 )
        return (unsigned __int16)v34;
    }
    v34 = StrCmpLogicalW(v50, v49);
LABEL_68:
    if ( v34 )
      return (unsigned __int16)v34;
    v43 = ILCompareRelIDs((unsigned __int64)this & -(__int64)(this != (CStorageFolder *)16), a3, v46, a2);
    FreeSpace = v43;
    if ( v43 < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v37 = 26;
        v38 = (unsigned int)v43;
        goto LABEL_49;
      }
    }
    return FreeSpace;
  }
  v36 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v37 = 25;
    goto LABEL_48;
  }
  return FreeSpace;
}

```

## disassembly

```asm
0x18000a470  push    rbp
0x18000a472  push    rbx
0x18000a473  push    rsi
0x18000a474  push    rdi
0x18000a475  push    r12
0x18000a477  push    r13
0x18000a479  push    r14
0x18000a47b  push    r15
0x18000a47d  lea     rbp, [rsp-0BC8h]
0x18000a485  sub     rsp, 0CC8h
0x18000a48c  mov     rax, cs:__security_cookie
0x18000a493  xor     rax, rsp
0x18000a496  mov     [rbp+0C00h+var_50], rax
0x18000a49d  mov     rbx, r9
0x18000a4a0  mov     r15, rdx
0x18000a4a3  mov     rdx, r8; struct _ITEMIDLIST *
0x18000a4a6  mov     [rsp+0D00h+var_CC0], rbx
0x18000a4ab  mov     r12, r8
0x18000a4ae  mov     r13, rcx
0x18000a4b1  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x18000a4b6  mov     rdx, rbx; struct _ITEMIDLIST *
0x18000a4b9  mov     rsi, rax
0x18000a4bc  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x18000a4c1  xor     r10d, r10d
0x18000a4c4  mov     rdi, rax
0x18000a4c7  test    rsi, rsi
0x18000a4ca  jnz     short loc_18000A4D6
0x18000a4cc  mov     ebx, 80070057h
0x18000a4d1  jmp     loc_18000A6A1
0x18000a4d6  test    rdi, rdi
0x18000a4d9  jz      short loc_18000A4CC
0x18000a4db  mov     r14d, 7FFFFFFEh
0x18000a4e1  lea     r8, [rsi+36h]
0x18000a4e5  mov     ebx, 104h
0x18000a4ea  lea     rax, [rbp+0C00h+pszPath]
0x18000a4f1  mov     ecx, r14d
0x18000a4f4  mov     edx, ebx
0x18000a4f6  test    rcx, rcx
0x18000a4f9  jz      short loc_18000A51A
0x18000a4fb  movzx   r9d, word ptr [r8]
0x18000a4ff  test    r9w, r9w
0x18000a503  jz      short loc_18000A51A
0x18000a505  mov     [rax], r9w
0x18000a509  add     r8, 2
0x18000a50d  add     rax, 2
0x18000a511  dec     rcx
0x18000a514  sub     rdx, 1
0x18000a518  jnz     short loc_18000A4F6
0x18000a51a  test    rdx, rdx
0x18000a51d  lea     rcx, [rax-2]
0x18000a521  cmovnz  rcx, rax
0x18000a525  mov     [rcx], r10w
0x18000a529  lea     rcx, [rbp+0C00h+pszPath]; pszPath
0x18000a530  call    cs:__imp_PathFindFileNameW
0x18000a536  mov     rcx, r14
0x18000a539  lea     r8, [rdi+36h]
0x18000a53d  mov     rdx, rbx
0x18000a540  lea     rax, [rsp+0D00h+var_CB0]
0x18000a545  xor     r10d, r10d
0x18000a548  test    rcx, rcx
0x18000a54b  jz      short loc_18000A56C
0x18000a54d  movzx   r9d, word ptr [r8]
0x18000a551  test    r9w, r9w
0x18000a555  jz      short loc_18000A56C
0x18000a557  mov     [rax], r9w
0x18000a55b  add     r8, 2
0x18000a55f  add     rax, 2
0x18000a563  dec     rcx
0x18000a566  sub     rdx, 1
0x18000a56a  jnz     short loc_18000A548
0x18000a56c  test    rdx, rdx
0x18000a56f  lea     rcx, [rax-2]
0x18000a573  cmovnz  rcx, rax
0x18000a577  mov     [rcx], r10w
0x18000a57b  lea     rcx, [rsp+0D00h+var_CB0]; pszPath
0x18000a580  call    cs:__imp_PathFindFileNameW
0x18000a586  mov     eax, [rsi+26h]
0x18000a589  mov     rcx, r14
0x18000a58c  add     rax, 1Bh
0x18000a590  mov     rdx, rbx
0x18000a593  xor     r10d, r10d
0x18000a596  lea     r9, [rsi+rax*2]
0x18000a59a  lea     rax, [rbp+0C00h+var_680]
0x18000a5a1  test    rcx, rcx
0x18000a5a4  jz      short loc_18000A5C5
0x18000a5a6  movzx   r8d, word ptr [r9]
0x18000a5aa  test    r8w, r8w
0x18000a5ae  jz      short loc_18000A5C5
0x18000a5b0  mov     [rax], r8w
0x18000a5b4  add     r9, 2
0x18000a5b8  add     rax, 2
0x18000a5bc  dec     rcx
0x18000a5bf  sub     rdx, 1
0x18000a5c3  jnz     short loc_18000A5A1
0x18000a5c5  lea     rcx, [rax-2]
0x18000a5c9  test    rdx, rdx
0x18000a5cc  cmovnz  rcx, rax
0x18000a5d0  mov     [rcx], r10w
0x18000a5d4  mov     eax, [rdi+26h]
0x18000a5d7  add     rax, 1Bh
0x18000a5db  lea     rcx, [rdi+rax*2]
0x18000a5df  lea     rax, [rbp+0C00h+var_890]
0x18000a5e6  test    r14, r14
0x18000a5e9  jz      short loc_18000A607
0x18000a5eb  movzx   edx, word ptr [rcx]
0x18000a5ee  test    dx, dx
0x18000a5f1  jz      short loc_18000A607
0x18000a5f3  mov     [rax], dx
0x18000a5f6  add     rcx, 2
0x18000a5fa  add     rax, 2
0x18000a5fe  dec     r14
0x18000a601  sub     rbx, 1
0x18000a605  jnz     short loc_18000A5E6
0x18000a607  test    rbx, rbx
0x18000a60a  lea     rcx, [rax-2]
0x18000a60e  cmovnz  rcx, rax
0x18000a612  mov     [rcx], r10w
0x18000a616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a61d  lea     r14, WPP_GLOBAL_Control
0x18000a624  cmp     rcx, r14
0x18000a627  jz      short loc_18000A68F
0x18000a629  test    byte ptr [rcx+1Ch], 40h
0x18000a62d  jz      short loc_18000A65E
0x18000a62f  mov     rcx, [rcx+10h]
0x18000a633  lea     rax, [rbp+0C00h+var_680]
0x18000a63a  mov     edx, 16h
0x18000a63f  mov     [rsp+0D00h+var_CE0], rax
0x18000a644  lea     r9, [rbp+0C00h+pszPath]
0x18000a64b  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18000a652  call    WPP_SF_SS
0x18000a657  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a65e  cmp     rcx, r14
0x18000a661  jz      short loc_18000A68F
0x18000a663  test    byte ptr [rcx+1Ch], 40h
0x18000a667  jz      short loc_18000A68F
0x18000a669  mov     rcx, [rcx+10h]
0x18000a66d  lea     rax, [rbp+0C00h+var_890]
0x18000a674  mov     edx, 17h
0x18000a679  mov     [rsp+0D00h+var_CE0], rax
0x18000a67e  lea     r9, [rsp+0D00h+var_CB0]
0x18000a683  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18000a68a  call    WPP_SF_SS
0x18000a68f  test    byte ptr [rsi+0Ah], 2
0x18000a693  jz      short loc_18000A6C6
0x18000a695  test    byte ptr [rdi+0Ah], 2
0x18000a699  jnz     short loc_18000A6D3
0x18000a69b  or      eax, 0FFFFFFFFh
0x18000a69e  movzx   ebx, ax
0x18000a6a1  mov     eax, ebx
0x18000a6a3  mov     rcx, [rbp+0C00h+var_50]
0x18000a6aa  xor     rcx, rsp; StackCookie
0x18000a6ad  call    __security_check_cookie
0x18000a6b2  add     rsp, 0CC8h
0x18000a6b9  pop     r15
0x18000a6bb  pop     r14
0x18000a6bd  pop     r13
0x18000a6bf  pop     r12
0x18000a6c1  pop     rdi
0x18000a6c2  pop     rsi
0x18000a6c3  pop     rbx
0x18000a6c4  pop     rbp
0x18000a6c5  retn
0x18000a6c6  test    byte ptr [rdi+0Ah], 2
0x18000a6ca  jz      short loc_18000A6D3
0x18000a6cc  mov     eax, 1
0x18000a6d1  jmp     short loc_18000A69E
0x18000a6d3  movzx   eax, r15w
0x18000a6d7  sub     rax, 1
0x18000a6db  jz      loc_18000A808
0x18000a6e1  sub     rax, 1
0x18000a6e5  jz      loc_18000A7F3
0x18000a6eb  cmp     rax, 1
0x18000a6ef  jnz     loc_18000A7B8
0x18000a6f5  lea     r8, [rsp+0D00h+var_CD0]; unsigned __int64 *
0x18000a6fa  mov     [rsp+0D00h+var_CD0], 0
0x18000a703  mov     rdx, rsi; struct STORAGEITEM *
0x18000a706  mov     [rsp+0D00h+var_CC8], 0
0x18000a70f  lea     rcx, [r13-10h]; this
0x18000a713  call    ?_GetFreeSpace@CStorageFolder@@AEAAJPEFBUSTORAGEITEM@@PEA_K@Z; CStorageFolder::_GetFreeSpace(STORAGEITEM const *,unsigned __int64 *)
0x18000a718  mov     ebx, eax
0x18000a71a  test    eax, eax
0x18000a71c  jns     short loc_18000A75C
0x18000a71e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a725  lea     rax, WPP_GLOBAL_Control
0x18000a72c  cmp     rcx, rax
0x18000a72f  jz      loc_18000A6A1
0x18000a735  test    byte ptr [rcx+1Ch], 2
0x18000a739  jz      loc_18000A6A1
0x18000a73f  mov     edx, 18h
0x18000a744  mov     r9d, ebx
0x18000a747  mov     rcx, [rcx+10h]
0x18000a74b  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18000a752  call    WPP_SF_d
0x18000a757  jmp     loc_18000A6A1
0x18000a75c  lea     r8, [rsp+0D00h+var_CC8]; unsigned __int64 *
0x18000a761  mov     rdx, rdi; struct STORAGEITEM *
0x18000a764  lea     rcx, [r13-10h]; this
0x18000a768  call    ?_GetFreeSpace@CStorageFolder@@AEAAJPEFBUSTORAGEITEM@@PEA_K@Z; CStorageFolder::_GetFreeSpace(STORAGEITEM const *,unsigned __int64 *)
0x18000a76d  mov     ebx, eax
0x18000a76f  test    eax, eax
0x18000a771  jns     short loc_18000A79B
0x18000a773  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a77a  lea     rax, WPP_GLOBAL_Control
0x18000a781  cmp     rcx, rax
0x18000a784  jz      loc_18000A6A1
0x18000a78a  test    byte ptr [rcx+1Ch], 2
0x18000a78e  jz      loc_18000A6A1
0x18000a794  mov     edx, 19h
0x18000a799  jmp     short loc_18000A744
0x18000a79b  mov     rax, [rsp+0D00h+var_CC8]
0x18000a7a0  cmp     [rsp+0D00h+var_CD0], rax
0x18000a7a5  jb      loc_18000A69B
0x18000a7ab  ja      loc_18000A6CC
0x18000a7b1  lea     r14, WPP_GLOBAL_Control
0x18000a7b8  bt      r15, 1Ch
0x18000a7bd  jb      loc_18000A861
0x18000a7c3  bt      r15, 1Fh
0x18000a7c8  jnb     short loc_18000A847
0x18000a7ca  movzx   eax, word ptr [rdi+4]
0x18000a7ce  cmp     [rsi+4], ax
0x18000a7d2  jb      loc_18000A69B
0x18000a7d8  ja      loc_18000A6CC
0x18000a7de  movzx   r8d, word ptr [rsi+4]; Size
0x18000a7e3  mov     rdx, rdi; Buf2
0x18000a7e6  mov     rcx, rsi; Buf1
0x18000a7e9  call    memcmp_0
0x18000a7ee  jmp     loc_18000A875
0x18000a7f3  mov     rax, [rsi+12h]
0x18000a7f7  cmp     rax, [rdi+12h]
0x18000a7fb  jb      loc_18000A69B
0x18000a801  jbe     short loc_18000A7B8
0x18000a803  jmp     loc_18000A6CC
0x18000a808  lea     r8, [rbp+0C00h+psz1]; unsigned __int16 *
0x18000a80f  mov     rdx, rsi; struct STORAGEITEM *
0x18000a812  call    ?_Type@CStorageFolder@@AEAAPEBGPEFBUSTORAGEITEM@@PEAGI@Z; CStorageFolder::_Type(STORAGEITEM const *,ushort *,uint)
0x18000a817  lea     r8, [rbp+0C00h+psz2]; unsigned __int16 *
0x18000a81e  mov     rdx, rdi; struct STORAGEITEM *
0x18000a821  call    ?_Type@CStorageFolder@@AEAAPEBGPEFBUSTORAGEITEM@@PEAGI@Z; CStorageFolder::_Type(STORAGEITEM const *,ushort *,uint)
0x18000a826  lea     rdx, [rbp+0C00h+psz2]; psz2
0x18000a82d  lea     rcx, [rbp+0C00h+psz1]; psz1
0x18000a834  call    cs:__imp_StrCmpW
0x18000a83a  test    eax, eax
0x18000a83c  jz      loc_18000A7B8
0x18000a842  jmp     loc_18000A69E
0x18000a847  lea     rdx, [rsp+0D00h+var_CB0]; psz2
0x18000a84c  lea     rcx, [rbp+0C00h+pszPath]; psz1
0x18000a853  call    cs:__imp_StrCmpLogicalW
0x18000a859  test    eax, eax
0x18000a85b  jnz     loc_18000A69E
0x18000a861  lea     rdx, [rbp+0C00h+var_890]; psz2
0x18000a868  lea     rcx, [rbp+0C00h+var_680]; psz1
0x18000a86f  call    cs:__imp_StrCmpLogicalW
0x18000a875  test    eax, eax
0x18000a877  jnz     loc_18000A69E
0x18000a87d  mov     r8, [rsp+0D00h+var_CC0]
0x18000a882  lea     rax, [r13-10h]
0x18000a886  neg     rax
0x18000a889  mov     r9, r15
0x18000a88c  mov     rdx, r12
0x18000a88f  sbb     rcx, rcx
0x18000a892  and     rcx, r13
0x18000a895  call    ILCompareRelIDs
0x18000a89a  mov     ebx, eax
0x18000a89c  test    eax, eax
0x18000a89e  jns     loc_18000A6A1
0x18000a8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8ab  cmp     rcx, r14
0x18000a8ae  jz      loc_18000A6A1
0x18000a8b4  test    byte ptr [rcx+1Ch], 2
0x18000a8b8  jz      loc_18000A6A1
0x18000a8be  mov     edx, 1Ah
0x18000a8c3  mov     r9d, eax
0x18000a8c6  jmp     loc_18000A747
```
