# DisplayLDAPCancelDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180026090`
- end: `0x1800266c2`
- name: `?DisplayLDAPCancelDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1586`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x1800253b8`
- `0x180025750`
- `0x180026018`
- `0x180026090`
- `0x1800286e8`
- `0x180029834`
- `0x18002ae08`
- `0x18002c818`
- `0x180033ae0`
- `0x180064e84`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180026365`
- `KERNEL32!FormatMessageW` at `0x180026365`
- `USER32!LoadStringW` at `0x180026336`
- `USER32!LoadStringW` at `0x1800263fb`
- `USER32!LoadStringW` at `0x1800264d9`
- `USER32!LoadStringW` at `0x180026336`
- `USER32!LoadStringW` at `0x1800263fb`
- `USER32!LoadStringW` at `0x1800264d9`
- `USER32!SendMessageW` at `0x18002626a`
- `USER32!SendMessageW` at `0x18002627c`
- `USER32!SendMessageW` at `0x1800262a9`
- `USER32!SendMessageW` at `0x180026586`
- `USER32!SendMessageW` at `0x1800265a1`
- `USER32!SendMessageW` at `0x1800265b4`
- `USER32!SendMessageW` at `0x1800265d4`
- `USER32!SendMessageW` at `0x180026621`
- `USER32!SendMessageW` at `0x18002626a`
- `USER32!SendMessageW` at `0x18002627c`
- `USER32!SendMessageW` at `0x1800262a9`
- `USER32!SendMessageW` at `0x180026586`
- `USER32!SendMessageW` at `0x1800265a1`
- `USER32!SendMessageW` at `0x1800265b4`
- `USER32!SendMessageW` at `0x1800265d4`
- `USER32!SendMessageW` at `0x180026621`
- `USER32!EnableWindow` at `0x1800261a7`
- `USER32!EnableWindow` at `0x1800262e3`
- `USER32!EnableWindow` at `0x18002667f`
- `USER32!EnableWindow` at `0x1800261a7`
- `USER32!EnableWindow` at `0x1800262e3`
- `USER32!EnableWindow` at `0x18002667f`
- `USER32!GetDlgItem` at `0x180026256`
- `USER32!GetDlgItem` at `0x1800263c6`
- `USER32!GetDlgItem` at `0x1800263d9`
- `USER32!GetDlgItem` at `0x1800264a4`
- `USER32!GetDlgItem` at `0x1800264b7`
- `USER32!GetDlgItem` at `0x18002656d`
- `USER32!GetDlgItem` at `0x18002660d`
- `USER32!GetDlgItem` at `0x180026256`
- `USER32!GetDlgItem` at `0x1800263c6`
- `USER32!GetDlgItem` at `0x1800263d9`
- `USER32!GetDlgItem` at `0x1800264a4`
- `USER32!GetDlgItem` at `0x1800264b7`
- `USER32!GetDlgItem` at `0x18002656d`
- `USER32!GetDlgItem` at `0x18002660d`
- `USER32!UpdateWindow` at `0x180026412`
- `USER32!UpdateWindow` at `0x1800264f0`
- `USER32!UpdateWindow` at `0x180026412`
- `USER32!UpdateWindow` at `0x1800264f0`
- `USER32!SetWindowLongPtrW` at `0x1800262f2`
- `USER32!SetWindowLongPtrW` at `0x1800262f2`
- `USER32!GetWindowLongPtrW` at `0x180026104`
- `USER32!GetWindowLongPtrW` at `0x180026290`
- `USER32!GetWindowLongPtrW` at `0x1800265e4`
- `USER32!GetWindowLongPtrW` at `0x180026104`
- `USER32!GetWindowLongPtrW` at `0x180026290`
- `USER32!GetWindowLongPtrW` at `0x1800265e4`
- `USER32!SetWindowTextW` at `0x180026409`
- `USER32!SetWindowTextW` at `0x1800264e7`
- `USER32!SetWindowTextW` at `0x180026409`
- `USER32!SetWindowTextW` at `0x1800264e7`
- `USER32!GetParent` at `0x1800262cb`
- `USER32!GetParent` at `0x18002630c`
- `USER32!GetParent` at `0x1800263b2`
- `USER32!GetParent` at `0x18002648e`
- `USER32!GetParent` at `0x18002666f`
- `USER32!GetParent` at `0x1800262cb`
- `USER32!GetParent` at `0x18002630c`
- `USER32!GetParent` at `0x1800263b2`
- `USER32!GetParent` at `0x18002648e`
- `USER32!GetParent` at `0x18002666f`
- `USER32!DestroyWindow` at `0x18002668f`
- `USER32!DestroyWindow` at `0x18002668f`
- `USER32!SetDlgItemTextW` at `0x18002637c`
- `USER32!SetDlgItemTextW` at `0x18002637c`
- `USER32!SetTimer` at `0x180026532`
- `USER32!SetTimer` at `0x180026532`
- `USER32!ShowWindow` at `0x18002619c`
- `USER32!ShowWindow` at `0x18002619c`
- `USER32!KillTimer` at `0x1800261be`
- `USER32!KillTimer` at `0x180026222`
- `USER32!KillTimer` at `0x18002623f`
- `USER32!KillTimer` at `0x1800265f3`
- `USER32!KillTimer` at `0x1800261be`
- `USER32!KillTimer` at `0x180026222`
- `USER32!KillTimer` at `0x18002623f`
- `USER32!KillTimer` at `0x1800265f3`

## pseudocode

```c
__int64 __fastcall DisplayLDAPCancelDlgProc(HWND a1, int a2, UINT_PTR a3, LONG_PTR a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  LONG_PTR v10; // rax
  LONG_PTR v11; // r14
  int v12; // eax
  unsigned int v13; // eax
  struct _tagPerThreadGlobalData *v14; // rax
  BOOL v15; // edx
  int v16; // r12d
  HWND v18; // rax
  LONG_PTR v19; // rax
  struct _tagPerThreadGlobalData *v20; // rsi
  HWND v21; // rax
  HWND v22; // rax
  unsigned __int16 **v23; // r12
  HWND v24; // rax
  HWND v25; // r15
  struct ldap **v26; // rdx
  unsigned __int16 *v27; // rcx
  int v28; // eax
  unsigned int v29; // eax
  HWND v30; // rax
  HWND v31; // r15
  HWND v32; // rdi
  LONG_PTR WindowLongPtrW; // r14
  HWND DlgItem; // rax
  bool v35; // zf
  struct _tagPerThreadGlobalData *ThreadStoragePointer; // r14
  HWND Parent; // rax
  unsigned __int16 *Arguments; // [rsp+30h] [rbp-D0h]
  unsigned int v39; // [rsp+38h] [rbp-C8h]
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR lpBuffer[4]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[200]; // [rsp+260h] [rbp+160h] BYREF

  v7 = a2 - 16;
  if ( !v7 )
  {
    WindowLongPtrW = GetWindowLongPtrW(a1, 16);
    KillTimer(a1, *(unsigned int *)(WindowLongPtrW + 100));
    if ( (*(_BYTE *)(WindowLongPtrW + 128) & 1) != 0 )
    {
      DlgItem = GetDlgItem(a1, 30);
      SendMessageW(DlgItem, 0x466u, 0, 0);
    }
    if ( (*(_BYTE *)(WindowLongPtrW + 128) & 0x10) != 0 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))gpfnLDAPAbandon)(
        **(_QWORD **)(WindowLongPtrW + 24),
        *(unsigned int *)(WindowLongPtrW + 8));
      *(_DWORD *)(WindowLongPtrW + 16) = 88;
    }
    v35 = (*(_BYTE *)(WindowLongPtrW + 128) & 8) == 0;
    *(_QWORD *)(WindowLongPtrW + 120) = 0;
    if ( !v35 )
      DeinitLDAPClientLib();
    ThreadStoragePointer = GetThreadStoragePointer();
    Parent = GetParent(a1);
    if ( Parent )
      EnableWindow(Parent, 1);
    *((_QWORD *)ThreadStoragePointer + 305) = 0;
    DestroyWindow(a1);
    return 1;
  }
  v8 = v7 - 256;
  if ( !v8 )
  {
    *(_QWORD *)lpBuffer = 0;
    v20 = GetThreadStoragePointer();
    v21 = GetParent(a1);
    if ( v21 && !*((_DWORD *)v20 + 612) )
      EnableWindow(v21, 0);
    SetWindowLongPtrW(a1, 16, a4);
    if ( (unsigned int)InitLDAPClientLib() )
      *(_DWORD *)(a4 + 128) |= 8u;
    v22 = GetParent(a1);
    CenterWindow(a1, v22);
    LoadStringW(hinstMapiX, 0x1091u, Buffer, 200);
    v23 = (unsigned __int16 **)(a4 + 88);
    if ( FormatMessageW(0x2500u, Buffer, 0, 0, lpBuffer, 0, (va_list *)(a4 + 88)) )
    {
      SetDlgItemTextW(a1, 54, *(LPCWSTR *)lpBuffer);
      LocalFreeAndNull((void **)lpBuffer);
    }
    if ( (unsigned int)bIsSimpleSearch(*v23) )
      *(_DWORD *)(a4 + 128) |= 0x20u;
    if ( (*(_BYTE *)(a4 + 128) & 1) == 0 )
    {
      v24 = GetParent(a1);
      v25 = v24;
      if ( v24 )
      {
        if ( GetDlgItem(v24, 100) && GetDlgItem(v25, 1170) )
        {
          LoadStringW(hinstMapiX, 0x10DBu, String, 260);
          SetWindowTextW(v25, String);
          UpdateWindow(v25);
        }
      }
    }
    v26 = *(struct ldap ***)(a4 + 24);
    v27 = *v23;
    v40 = *(_DWORD *)(a4 + 128) & 4;
    v39 = *(_DWORD *)(a4 + 144);
    Arguments = *(unsigned __int16 **)(a4 + 136);
    *(_DWORD *)(a4 + 132) = 0;
    *(_DWORD *)(a4 + 16) = OpenConnection(
                             v27,
                             v26,
                             (unsigned int *)a4,
                             (unsigned int *)(a4 + 8),
                             &v40,
                             0,
                             Arguments,
                             v39);
    v28 = *(_DWORD *)(a4 + 128);
    if ( v40 )
      v29 = v28 | 4;
    else
      v29 = v28 & 0xFFFFFFFB;
    *(_DWORD *)(a4 + 128) = v29;
    if ( (v29 & 1) == 0 )
    {
      v30 = GetParent(a1);
      v31 = v30;
      if ( v30 )
      {
        if ( GetDlgItem(v30, 100) && GetDlgItem(v31, 1170) )
        {
          LoadStringW(hinstMapiX, 0x10B9u, String, 260);
          SetWindowTextW(v31, String);
          UpdateWindow(v31);
        }
      }
    }
    if ( *(_DWORD *)(a4 + 16) )
      goto LABEL_29;
    if ( (*(_BYTE *)(a4 + 128) & 4) != 0 )
    {
      if ( !(unsigned int)BindProcessResults((struct _LDAPSEARCHPARAMS *)a4, a1, 0) )
        goto LABEL_29;
    }
    else
    {
      if ( SetTimer(a1, 2u, 0x64u, 0) != 2 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD))gpfnLDAPAbandon)(**(_QWORD **)(a4 + 24), *(unsigned int *)(a4 + 8));
        *(_DWORD *)(a4 + 16) = 82;
LABEL_29:
        SendMessageW(a1, 0x10u, 0, 0);
        return 1;
      }
      *(_DWORD *)(a4 + 100) = 2;
    }
    v32 = GetDlgItem(a1, 30);
    SendMessageW(v32, 0x467u, 0, 1171);
    SendMessageW(v32, 0x465u, 0, 0x10000);
    SendMessageW(v32, 0x466u, 0, 0);
    if ( (*(_BYTE *)(a4 + 128) & 1) != 0 )
      SendMessageW(v32, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, -65536);
    v15 = 0;
LABEL_13:
    EnableWindow(a1, v15);
    return 1;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( (_WORD)a3 == 2 )
    {
      v19 = GetWindowLongPtrW(a1, 16);
      *(_DWORD *)(v19 + 128) |= 0x10u;
      SendMessageW(a1, 0x10u, 0, 0);
      return 1;
    }
    return 0;
  }
  if ( v9 != 2 )
    return 0;
  *(_QWORD *)lpBuffer = 0;
  v10 = GetWindowLongPtrW(a1, 16);
  v11 = v10;
  if ( *(_DWORD *)(v10 + 100) != a3 )
  {
    KillTimer(a1, a3);
    goto LABEL_27;
  }
  *(_QWORD *)lpBuffer = 0;
  v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, WCHAR *, _QWORD))gpfnLDAPResult)(
          **(_QWORD **)(v10 + 24),
          *(unsigned int *)(v10 + 8),
          1,
          lpBuffer,
          *(_QWORD *)(v10 + 80));
  *(_DWORD *)(v11 + 12) = v12;
  if ( !v12 )
  {
    *(_DWORD *)(v11 + 4) += 100;
    v13 = *(_DWORD *)(v11 + 4);
    if ( v13 >= *(_DWORD *)v11 )
    {
      *(_DWORD *)(v11 + 16) = 85;
      goto LABEL_27;
    }
    if ( v13 < 0x7D0 )
      return 1;
    v14 = GetThreadStoragePointer();
    if ( !*((_QWORD *)v14 + 304) || *((_DWORD *)v14 + 612) )
      return 1;
    ShowWindow(a1, 5);
    v15 = 1;
    goto LABEL_13;
  }
  if ( *(_DWORD *)(v11 + 100) != 1 )
  {
    if ( *(_DWORD *)(v11 + 100) == 2 )
    {
      v40 = 1;
      v16 = BindProcessResults((struct _LDAPSEARCHPARAMS *)v11, a1, &v40);
      if ( v40 )
        KillTimer(a1, 2u);
      if ( v16 == 1 )
        return 1;
      goto LABEL_27;
    }
    return 0;
  }
  KillTimer(a1, 1u);
  if ( (*(_BYTE *)(v11 + 128) & 2) == 0 )
  {
    if ( *(_DWORD *)(v11 + 12) == -1 )
      *(_DWORD *)(v11 + 16) = *(_DWORD *)(**(_QWORD **)(v11 + 24) + 116LL);
    goto LABEL_27;
  }
  if ( !(unsigned int)ResolveProcessResults((struct _LDAPSEARCHPARAMS *)v11, a1) )
  {
LABEL_27:
    if ( (*(_BYTE *)(v11 + 128) & 1) != 0 )
    {
      v18 = GetDlgItem(a1, 30);
      SendMessageW(v18, 0x466u, 0, 0);
    }
    goto LABEL_29;
  }
  return 1;
}

```

## disassembly

```asm
0x180026090  mov     [rsp-8+arg_8], rbx
0x180026095  push    rbp
0x180026096  push    rsi
0x180026097  push    rdi
0x180026098  push    r12
0x18002609a  push    r13
0x18002609c  push    r14
0x18002609e  push    r15
0x1800260a0  lea     rbp, [rsp-300h]
0x1800260a8  sub     rsp, 400h
0x1800260af  mov     rax, cs:__security_cookie
0x1800260b6  xor     rax, rsp
0x1800260b9  mov     [rbp+330h+var_40], rax
0x1800260c0  mov     r13d, 10h
0x1800260c6  mov     r14, r9
0x1800260c9  mov     r12, r8
0x1800260cc  mov     rbx, rcx
0x1800260cf  sub     edx, r13d
0x1800260d2  jz      loc_1800265E1
0x1800260d8  sub     edx, 100h
0x1800260de  jz      loc_1800262B9
0x1800260e4  lea     r15d, [r13-0Eh]
0x1800260e8  sub     edx, 1
0x1800260eb  jz      loc_180026287
0x1800260f1  cmp     edx, r15d
0x1800260f4  jnz     loc_180026232
0x1800260fa  xor     edi, edi
0x1800260fc  mov     edx, r13d; nIndex
0x1800260ff  mov     qword ptr [rsp+430h+var_3E8], rdi
0x180026104  call    cs:__imp_GetWindowLongPtrW
0x18002610a  mov     r14, rax
0x18002610d  lea     esi, [rdi+1]
0x180026110  mov     ecx, [rax+64h]
0x180026113  cmp     rcx, r12
0x180026116  jnz     loc_180026239
0x18002611c  mov     qword ptr [rsp+430h+var_3E8], rdi
0x180026121  lea     r9, [rsp+430h+var_3E8]
0x180026126  mov     rcx, [rax+50h]
0x18002612a  mov     r8d, esi
0x18002612d  mov     r10, [rax+18h]
0x180026131  mov     edx, [rax+8]
0x180026134  mov     rax, cs:?gpfnLDAPResult@@3P6AKPEAUldap@@KKPEAUl_timeval@@PEAPEAUldapmsg@@@ZEA; ulong (*gpfnLDAPResult)(ldap *,ulong,ulong,l_timeval *,ldapmsg * *)
0x18002613b  mov     [rsp+430h+lpBuffer], rcx
0x180026140  mov     rcx, [r10]
0x180026143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026148  mov     [r14+0Ch], eax
0x18002614c  test    eax, eax
0x18002614e  jnz     short loc_1800261B2
0x180026150  add     dword ptr [r14+4], 64h ; 'd'
0x180026155  mov     eax, [r14+4]
0x180026159  cmp     eax, [r14]
0x18002615c  jb      short loc_18002616B
0x18002615e  mov     dword ptr [r14+10h], 55h ; 'U'
0x180026166  jmp     loc_180026245
0x18002616b  cmp     eax, 7D0h
0x180026170  jb      loc_180026695
0x180026176  call    ?GetThreadStoragePointer@@YAPEAU_tagPerThreadGlobalData@@XZ; GetThreadStoragePointer(void)
0x18002617b  cmp     [rax+980h], rdi
0x180026182  jz      loc_180026695
0x180026188  cmp     [rax+990h], edi
0x18002618e  jnz     loc_180026695
0x180026194  mov     edx, 5; nCmdShow
0x180026199  mov     rcx, rbx; hWnd
0x18002619c  call    cs:__imp_ShowWindow
0x1800261a2  mov     edx, esi; bEnable
0x1800261a4  mov     rcx, rbx; hWnd
0x1800261a7  call    cs:__imp_EnableWindow
0x1800261ad  jmp     loc_180026695
0x1800261b2  cmp     [r14+64h], esi
0x1800261b6  jnz     short loc_1800261F9
0x1800261b8  mov     rdx, rsi; uIDEvent
0x1800261bb  mov     rcx, rbx; hWnd
0x1800261be  call    cs:__imp_KillTimer
0x1800261c4  test    [r14+80h], r15b
0x1800261cb  jz      short loc_1800261E2
0x1800261cd  mov     rdx, rbx; HWND
0x1800261d0  mov     rcx, r14; struct _LDAPSEARCHPARAMS *
0x1800261d3  call    ?ResolveProcessResults@@YAHPEAU_LDAPSEARCHPARAMS@@PEAUHWND__@@@Z; ResolveProcessResults(_LDAPSEARCHPARAMS *,HWND__ *)
0x1800261d8  test    eax, eax
0x1800261da  jnz     loc_180026695
0x1800261e0  jmp     short loc_180026245
0x1800261e2  cmp     dword ptr [r14+0Ch], 0FFFFFFFFh
0x1800261e7  jnz     short loc_180026245
0x1800261e9  mov     rax, [r14+18h]
0x1800261ed  mov     rcx, [rax]
0x1800261f0  mov     eax, [rcx+74h]
0x1800261f3  mov     [r14+10h], eax
0x1800261f7  jmp     short loc_180026245
0x1800261f9  cmp     [r14+64h], r15d
0x1800261fd  jnz     short loc_180026232
0x1800261ff  lea     r8, [rsp+430h+var_3F0]; int *
0x180026204  mov     [rsp+430h+var_3F0], esi
0x180026208  mov     rdx, rbx; HWND
0x18002620b  mov     rcx, r14; struct _LDAPSEARCHPARAMS *
0x18002620e  call    ?BindProcessResults@@YAHPEAU_LDAPSEARCHPARAMS@@PEAUHWND__@@PEAH@Z; BindProcessResults(_LDAPSEARCHPARAMS *,HWND__ *,int *)
0x180026213  mov     r12d, eax
0x180026216  cmp     [rsp+430h+var_3F0], edi
0x18002621a  jz      short loc_180026228
0x18002621c  mov     rdx, r15; uIDEvent
0x18002621f  mov     rcx, rbx; hWnd
0x180026222  call    cs:__imp_KillTimer
0x180026228  cmp     r12d, esi
0x18002622b  jnz     short loc_180026245
0x18002622d  jmp     loc_180026695
0x180026232  xor     eax, eax
0x180026234  jmp     loc_180026698
0x180026239  mov     rdx, r12; uIDEvent
0x18002623c  mov     rcx, rbx; hWnd
0x18002623f  call    cs:__imp_KillTimer
0x180026245  test    [r14+80h], sil
0x18002624c  jz      short loc_180026270
0x18002624e  mov     edx, 1Eh; nIDDlgItem
0x180026253  mov     rcx, rbx; hDlg
0x180026256  call    cs:__imp_GetDlgItem
0x18002625c  xor     r9d, r9d; lParam
0x18002625f  xor     r8d, r8d; wParam
0x180026262  mov     rcx, rax; hWnd
0x180026265  mov     edx, 466h; Msg
0x18002626a  call    cs:__imp_SendMessageW
0x180026270  xor     r9d, r9d; lParam
0x180026273  xor     r8d, r8d; wParam
0x180026276  mov     edx, r13d; Msg
0x180026279  mov     rcx, rbx; hWnd
0x18002627c  call    cs:__imp_SendMessageW
0x180026282  jmp     loc_180026695
0x180026287  cmp     r12w, r15w
0x18002628b  jnz     short loc_180026232
0x18002628d  mov     edx, r13d; nIndex
0x180026290  call    cs:__imp_GetWindowLongPtrW
0x180026296  xor     r9d, r9d; lParam
0x180026299  xor     r8d, r8d; wParam
0x18002629c  mov     edx, r13d; Msg
0x18002629f  mov     rcx, rbx; hWnd
0x1800262a2  or      [rax+80h], r13d
0x1800262a9  call    cs:__imp_SendMessageW
0x1800262af  mov     eax, 1
0x1800262b4  jmp     loc_180026698
0x1800262b9  xor     edi, edi
0x1800262bb  mov     qword ptr [rsp+430h+var_3E8], rdi
0x1800262c0  call    ?GetThreadStoragePointer@@YAPEAU_tagPerThreadGlobalData@@XZ; GetThreadStoragePointer(void)
0x1800262c5  mov     rcx, rbx; hWnd
0x1800262c8  mov     rsi, rax
0x1800262cb  call    cs:__imp_GetParent
0x1800262d1  test    rax, rax
0x1800262d4  jz      short loc_1800262E9
0x1800262d6  cmp     [rsi+990h], edi
0x1800262dc  jnz     short loc_1800262E9
0x1800262de  xor     edx, edx; bEnable
0x1800262e0  mov     rcx, rax; hWnd
0x1800262e3  call    cs:__imp_EnableWindow
0x1800262e9  mov     r8, r14; dwNewLong
0x1800262ec  mov     edx, r13d; nIndex
0x1800262ef  mov     rcx, rbx; hWnd
0x1800262f2  call    cs:__imp_SetWindowLongPtrW
0x1800262f8  call    ?InitLDAPClientLib@@YAHXZ; InitLDAPClientLib(void)
0x1800262fd  test    eax, eax
0x1800262ff  jz      short loc_180026309
0x180026301  or      dword ptr [r14+80h], 8
0x180026309  mov     rcx, rbx; hWnd
0x18002630c  call    cs:__imp_GetParent
0x180026312  mov     rdx, rax; HWND
0x180026315  mov     rcx, rbx; hWnd
0x180026318  call    ?CenterWindow@@YAHPEAUHWND__@@0@Z; CenterWindow(HWND__ *,HWND__ *)
0x18002631d  mov     rcx, cs:hinstMapiX; hInstance
0x180026324  lea     r8, [rbp+330h+Buffer]; lpBuffer
0x18002632b  mov     r9d, 0C8h; cchBufferMax
0x180026331  mov     edx, 1091h; uID
0x180026336  call    cs:__imp_LoadStringW
0x18002633c  lea     rax, [rsp+430h+var_3E8]
0x180026341  xor     r9d, r9d; dwLanguageId
0x180026344  lea     r12, [r14+58h]
0x180026348  xor     r8d, r8d; dwMessageId
0x18002634b  mov     [rsp+430h+Arguments], r12; Arguments
0x180026350  lea     rdx, [rbp+330h+Buffer]; lpSource
0x180026357  mov     [rsp+430h+nSize], edi; nSize
0x18002635b  mov     ecx, 2500h; dwFlags
0x180026360  mov     [rsp+430h+lpBuffer], rax; lpBuffer
0x180026365  call    cs:__imp_FormatMessageW
0x18002636b  test    eax, eax
0x18002636d  jz      short loc_18002638C
0x18002636f  mov     r8, qword ptr [rsp+430h+var_3E8]; lpString
0x180026374  mov     edx, 36h ; '6'; nIDDlgItem
0x180026379  mov     rcx, rbx; hDlg
0x18002637c  call    cs:__imp_SetDlgItemTextW
0x180026382  lea     rcx, [rsp+430h+var_3E8]; void **
0x180026387  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18002638c  mov     rcx, [r12]; unsigned __int16 *
0x180026390  call    ?bIsSimpleSearch@@YAHPEAG@Z; bIsSimpleSearch(ushort *)
0x180026395  test    eax, eax
0x180026397  jz      short loc_1800263A1
0x180026399  or      dword ptr [r14+80h], 20h
0x1800263a1  mov     esi, 1
0x1800263a6  test    [r14+80h], sil
0x1800263ad  jnz     short loc_180026418
0x1800263af  mov     rcx, rbx; hWnd
0x1800263b2  call    cs:__imp_GetParent
0x1800263b8  mov     r15, rax
0x1800263bb  test    rax, rax
0x1800263be  jz      short loc_180026418
0x1800263c0  lea     edx, [rsi+63h]; nIDDlgItem
0x1800263c3  mov     rcx, rax; hDlg
0x1800263c6  call    cs:__imp_GetDlgItem
0x1800263cc  test    rax, rax
0x1800263cf  jz      short loc_180026418
0x1800263d1  mov     edx, 492h; nIDDlgItem
0x1800263d6  mov     rcx, r15; hDlg
0x1800263d9  call    cs:__imp_GetDlgItem
0x1800263df  test    rax, rax
0x1800263e2  jz      short loc_180026418
0x1800263e4  mov     rcx, cs:hinstMapiX; hInstance
0x1800263eb  lea     r8, [rsp+430h+String]; lpBuffer
0x1800263f0  mov     r9d, 104h; cchBufferMax
0x1800263f6  mov     edx, 10DBh; uID
0x1800263fb  call    cs:__imp_LoadStringW
0x180026401  lea     rdx, [rsp+430h+String]; lpString
0x180026406  mov     rcx, r15; hWnd
0x180026409  call    cs:__imp_SetWindowTextW
0x18002640f  mov     rcx, r15; hWnd
0x180026412  call    cs:__imp_UpdateWindow
0x180026418  mov     eax, [r14+80h]
0x18002641f  lea     r9, [r14+8]; unsigned int *
0x180026423  mov     rdx, [r14+18h]; struct ldap **
0x180026427  and     eax, 4
0x18002642a  mov     rcx, [r12]; unsigned __int16 *
0x18002642e  mov     r8, r14; unsigned int *
0x180026431  mov     [rsp+430h+var_3F0], eax
0x180026435  mov     eax, [r14+90h]
0x18002643c  mov     [rsp+430h+var_3F8], eax; unsigned int
0x180026440  mov     rax, [r14+88h]
0x180026447  mov     [rsp+430h+Arguments], rax; unsigned __int16 *
0x18002644c  lea     rax, [rsp+430h+var_3F0]
0x180026451  mov     [rsp+430h+nSize], edi; unsigned int
0x180026455  mov     [rsp+430h+lpBuffer], rax; int *
0x18002645a  mov     [r14+84h], edi
0x180026461  call    ?OpenConnection@@YAKPEAGPEAPEAUldap@@PEAK2PEAHK0K@Z; OpenConnection(ushort *,ldap * *,ulong *,ulong *,int *,ulong,ushort *,ulong)
0x180026466  mov     [r14+10h], eax
0x18002646a  mov     eax, [r14+80h]
0x180026471  cmp     [rsp+430h+var_3F0], edi
0x180026475  jz      short loc_18002647C
0x180026477  or      eax, 4
0x18002647a  jmp     short loc_18002647F
0x18002647c  and     eax, 0FFFFFFFBh
0x18002647f  mov     [r14+80h], eax
0x180026486  test    sil, al
0x180026489  jnz     short loc_1800264F6
0x18002648b  mov     rcx, rbx; hWnd
0x18002648e  call    cs:__imp_GetParent
0x180026494  mov     r15, rax
0x180026497  test    rax, rax
0x18002649a  jz      short loc_1800264F6
0x18002649c  mov     edx, 64h ; 'd'; nIDDlgItem
0x1800264a1  mov     rcx, rax; hDlg
0x1800264a4  call    cs:__imp_GetDlgItem
0x1800264aa  test    rax, rax
0x1800264ad  jz      short loc_1800264F6
0x1800264af  mov     edx, 492h; nIDDlgItem
0x1800264b4  mov     rcx, r15; hDlg
0x1800264b7  call    cs:__imp_GetDlgItem
0x1800264bd  test    rax, rax
0x1800264c0  jz      short loc_1800264F6
0x1800264c2  mov     rcx, cs:hinstMapiX; hInstance
0x1800264c9  lea     r8, [rsp+430h+String]; lpBuffer
0x1800264ce  mov     r9d, 104h; cchBufferMax
0x1800264d4  mov     edx, 10B9h; uID
0x1800264d9  call    cs:__imp_LoadStringW
0x1800264df  lea     rdx, [rsp+430h+String]; lpString
0x1800264e4  mov     rcx, r15; hWnd
0x1800264e7  call    cs:__imp_SetWindowTextW
0x1800264ed  mov     rcx, r15; hWnd
0x1800264f0  call    cs:__imp_UpdateWindow
0x1800264f6  cmp     [r14+10h], edi
0x1800264fa  jnz     loc_180026270
0x180026500  test    byte ptr [r14+80h], 4
0x180026508  jz      short loc_180026521
0x18002650a  xor     r8d, r8d; int *
0x18002650d  mov     rdx, rbx; HWND
0x180026510  mov     rcx, r14; struct _LDAPSEARCHPARAMS *
0x180026513  call    ?BindProcessResults@@YAHPEAU_LDAPSEARCHPARAMS@@PEAUHWND__@@PEAH@Z; BindProcessResults(_LDAPSEARCHPARAMS *,HWND__ *,int *)
0x180026518  test    eax, eax
0x18002651a  jnz     short loc_180026565
0x18002651c  jmp     loc_180026270
0x180026521  xor     r9d, r9d; lpTimerFunc
0x180026524  mov     rcx, rbx; hWnd
0x180026527  lea     r15d, [r9+2]
0x18002652b  mov     edx, r15d; nIDEvent
0x18002652e  lea     r8d, [r9+64h]; uElapse
0x180026532  call    cs:__imp_SetTimer
0x180026538  cmp     rax, r15
0x18002653b  jz      short loc_180026561
0x18002653d  mov     rcx, [r14+18h]
0x180026541  mov     edx, [r14+8]
0x180026545  mov     rax, cs:?gpfnLDAPAbandon@@3P6AKPEAUldap@@K@ZEA; ulong (*gpfnLDAPAbandon)(ldap *,ulong)
0x18002654c  mov     rcx, [rcx]
0x18002654f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026554  mov     dword ptr [r14+10h], 52h ; 'R'
0x18002655c  jmp     loc_180026270
0x180026561  mov     [r14+64h], r15d
0x180026565  mov     edx, 1Eh; nIDDlgItem
0x18002656a  mov     rcx, rbx; hDlg
0x18002656d  call    cs:__imp_GetDlgItem
  ... truncated ...
```
