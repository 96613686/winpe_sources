# DeviceDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18005a1f0`
- end: `0x18005a4ca`
- name: `?DeviceDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `730`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800285c8`
- `0x180035590`
- `0x1800361ba`
- `0x1800496b4`
- `0x180049850`
- `0x18005a1f0`
- `0x18005a99c`
- `0x18005d2a4`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18005a35b`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18005a35b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005a385`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005a385`
- `USER32!SendMessageW` at `0x18005a3b9`
- `USER32!SendMessageW` at `0x18005a3b9`
- `USER32!SetDlgItemTextW` at `0x18005a397`
- `USER32!SetDlgItemTextW` at `0x18005a397`
- `USER32!GetDlgItem` at `0x18005a324`
- `USER32!GetDlgItem` at `0x18005a3a5`
- `USER32!GetDlgItem` at `0x18005a45b`
- `USER32!GetDlgItem` at `0x18005a324`
- `USER32!GetDlgItem` at `0x18005a3a5`
- `USER32!GetDlgItem` at `0x18005a45b`
- `USER32!GetWindowLongPtrW` at `0x18005a22f`
- `USER32!GetWindowLongPtrW` at `0x18005a22f`
- `USER32!SetWindowLongPtrW` at `0x18005a26a`
- `USER32!SetWindowLongPtrW` at `0x18005a41b`
- `USER32!SetWindowLongPtrW` at `0x18005a469`
- `USER32!SetWindowLongPtrW` at `0x18005a26a`
- `USER32!SetWindowLongPtrW` at `0x18005a41b`
- `USER32!SetWindowLongPtrW` at `0x18005a469`
- `USER32!GetWindowTextW` at `0x18005a338`
- `USER32!GetWindowTextW` at `0x18005a338`
- `ole32!CoTaskMemFree` at `0x18005a3c9`
- `ole32!CoTaskMemFree` at `0x18005a3de`
- `ole32!CoTaskMemFree` at `0x18005a3c9`
- `ole32!CoTaskMemFree` at `0x18005a3de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeviceDlgProc(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  LONG_PTR WindowLongPtrW; // rax
  LONG_PTR v8; // rdi
  LONG_PTR v10; // rbx
  LONG_PTR v11; // rbx
  int v12; // r12d
  HWND v13; // rax
  size_t v14; // r14
  HWND v15; // rax
  LONG_PTR v16; // r8
  HWND DlgItem; // rax
  PropSheetAccAnnotation *v18; // rcx
  unsigned int v19; // edx
  PropSheetAccAnnotation *v20; // rcx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Control; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[526]; // [rsp+52h] [rbp-AEh] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hWnd, 16);
  v8 = WindowLongPtrW;
  switch ( a2 )
  {
    case 2:
      v18 = *(PropSheetAccAnnotation **)(WindowLongPtrW + 1120);
      if ( v18 )
      {
        PropSheetAccAnnotation::ClearAllHwndAccProperties(v18);
        v20 = *(PropSheetAccAnnotation **)(v8 + 1120);
        if ( v20 )
          PropSheetAccAnnotation::`scalar deleting destructor'(v20, v19);
        *(_QWORD *)(v8 + 1120) = 0;
      }
      break;
    case 78:
      switch ( *(_DWORD *)(a4 + 16) )
      {
        case 0xFFFFFF2B:
          DlgItem = GetDlgItem(hWnd, 812);
          SetWindowLongPtrW(hWnd, 0, (LONG_PTR)DlgItem);
          break;
        case 0xFFFFFF36:
          _ApplyRename(
            *(struct _ITEMIDLIST **)(WindowLongPtrW + 32),
            *(HWND *)(WindowLongPtrW + 16),
            810,
            (LPCWSTR)(WindowLongPtrW + 40),
            1,
            0);
          break;
        case 0xFFFFFF37:
          v11 = 0;
          v23[0] = 0;
          if ( (***(int (__fastcall ****)(_QWORD, GUID *, _QWORD *))(WindowLongPtrW + 8))(
                 *(_QWORD *)(WindowLongPtrW + 8),
                 &GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4,
                 v23) < 0 )
            goto LABEL_21;
          v12 = 0;
          pv = 0;
          Control = 0;
          String = 0;
          memset_0(v25, 0, 0x206u);
          if ( (*(int (__fastcall **)(_QWORD, LPVOID *, wchar_t **))(*(_QWORD *)v23[0] + 24LL))(v23[0], &pv, &Control) >= 0 )
          {
            v13 = GetDlgItem(hWnd, 810);
            GetWindowTextW(v13, &String, 260);
            v14 = -1;
            do
              ++v14;
            while ( *(_WORD *)&v25[2 * v14 - 2] );
            if ( wcscspn(&String, Control) < v14 )
            {
              v12 = 1;
              ShellMessageBoxW(g_hInst, hWnd, (LPCWSTR)0xC3, (LPCWSTR)0xC4, 0x10010u);
              SetDlgItemTextW(hWnd, 810, (LPCWSTR)(v8 + 40));
              v15 = GetDlgItem(hWnd, 810);
              SendMessageW(v15, 0xB1u, 0, 0);
            }
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( Control )
            CoTaskMemFree(Control);
          if ( v12 )
          {
            v16 = 1;
          }
          else
          {
LABEL_21:
            LOBYTE(v11) = (unsigned int)_ApplyRename(
                                          *(struct _ITEMIDLIST **)(v8 + 32),
                                          *(HWND *)(v8 + 16),
                                          810,
                                          (LPCWSTR)(v8 + 40),
                                          0,
                                          0) == 0;
            v16 = v11;
          }
          SetWindowLongPtrW(hWnd, 0, v16);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v23);
          break;
      }
      break;
    case 272:
      v10 = *(_QWORD *)(a4 + 48);
      SetWindowLongPtrW(hWnd, 16, v10);
      *(_QWORD *)(v10 + 16) = hWnd;
      _InitDevicePropSheet((struct DEVICEPROPINFO *)v10);
      break;
    default:
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18005a1f0  mov     [rsp-8+arg_8], rbx
0x18005a1f5  mov     [rsp-8+arg_10], rsi
0x18005a1fa  push    rbp
0x18005a1fb  push    rdi
0x18005a1fc  push    r12
0x18005a1fe  push    r13
0x18005a200  push    r14
0x18005a202  lea     rbp, [rsp-170h]
0x18005a20a  sub     rsp, 270h
0x18005a211  mov     rax, cs:__security_cookie
0x18005a218  xor     rax, rsp
0x18005a21b  mov     [rbp+190h+var_30], rax
0x18005a222  mov     r14, r9
0x18005a225  mov     ebx, edx
0x18005a227  mov     rsi, rcx
0x18005a22a  mov     edx, 10h; nIndex
0x18005a22f  call    cs:__imp_GetWindowLongPtrW
0x18005a235  mov     rdi, rax
0x18005a238  mov     r13d, 1
0x18005a23e  cmp     ebx, 2
0x18005a241  jz      loc_18005A471
0x18005a247  cmp     ebx, 4Eh ; 'N'
0x18005a24a  jz      short loc_18005A281
0x18005a24c  cmp     ebx, 110h
0x18005a252  jz      short loc_18005A25B
0x18005a254  xor     eax, eax
0x18005a256  jmp     loc_18005A49F
0x18005a25b  mov     rbx, [r14+30h]
0x18005a25f  mov     r8, rbx; dwNewLong
0x18005a262  mov     edx, 10h; nIndex
0x18005a267  mov     rcx, rsi; hWnd
0x18005a26a  call    cs:__imp_SetWindowLongPtrW
0x18005a270  mov     [rbx+10h], rsi
0x18005a274  mov     rcx, rbx; struct DEVICEPROPINFO *
0x18005a277  call    ?_InitDevicePropSheet@@YAXPEAUDEVICEPROPINFO@@@Z; _InitDevicePropSheet(DEVICEPROPINFO *)
0x18005a27c  jmp     loc_18005A49C
0x18005a281  cmp     dword ptr [r14+10h], 0FFFFFF2Bh
0x18005a289  jz      loc_18005A453
0x18005a28f  cmp     dword ptr [r14+10h], 0FFFFFF36h
0x18005a297  jz      loc_18005A42E
0x18005a29d  cmp     dword ptr [r14+10h], 0FFFFFF37h
0x18005a2a5  jnz     loc_18005A49C
0x18005a2ab  xor     ebx, ebx
0x18005a2ad  mov     [rsp+290h+var_250], rbx
0x18005a2b2  mov     rcx, [rax+8]
0x18005a2b6  mov     rax, [rcx]
0x18005a2b9  lea     r8, [rsp+290h+var_250]
0x18005a2be  lea     rdx, _GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4
0x18005a2c5  mov     rax, [rax]
0x18005a2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2cd  test    eax, eax
0x18005a2cf  js      loc_18005A3EE
0x18005a2d5  mov     r12d, ebx
0x18005a2d8  mov     [rsp+290h+pv], rbx
0x18005a2dd  mov     [rsp+290h+Control], rbx
0x18005a2e2  mov     [rsp+290h+String], bx
0x18005a2e7  xor     edx, edx; Val
0x18005a2e9  mov     r8d, 206h; Size
0x18005a2ef  lea     rcx, [rsp+290h+var_23E]; void *
0x18005a2f4  call    memset_0
0x18005a2f9  mov     rcx, [rsp+290h+var_250]
0x18005a2fe  mov     rax, [rcx]
0x18005a301  lea     r8, [rsp+290h+Control]
0x18005a306  lea     rdx, [rsp+290h+pv]
0x18005a30b  mov     rax, [rax+18h]
0x18005a30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a314  test    eax, eax
0x18005a316  js      loc_18005A3BF
0x18005a31c  mov     edx, 32Ah; nIDDlgItem
0x18005a321  mov     rcx, rsi; hDlg
0x18005a324  call    cs:__imp_GetDlgItem
0x18005a32a  mov     rcx, rax; hWnd
0x18005a32d  mov     r8d, 104h; nMaxCount
0x18005a333  lea     rdx, [rsp+290h+String]; lpString
0x18005a338  call    cs:__imp_GetWindowTextW
0x18005a33e  lea     rax, [rsp+290h+String]
0x18005a343  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005a347  inc     r14
0x18005a34a  cmp     [rax+r14*2], bx
0x18005a34f  jnz     short loc_18005A347
0x18005a351  mov     rdx, [rsp+290h+Control]; Control
0x18005a356  lea     rcx, [rsp+290h+String]; String
0x18005a35b  call    cs:__imp_wcscspn
0x18005a361  cmp     rax, r14
0x18005a364  jnb     short loc_18005A3BF
0x18005a366  mov     r12d, r13d
0x18005a369  mov     [rsp+290h+fuStyle], 10010h; fuStyle
0x18005a371  mov     r9d, 0C4h; lpcTitle
0x18005a377  lea     r8d, [r9-1]; lpcText
0x18005a37b  mov     rdx, rsi; hWnd
0x18005a37e  mov     rcx, cs:g_hInst; hAppInst
0x18005a385  call    cs:__imp_ShellMessageBoxW
0x18005a38b  lea     r8, [rdi+28h]; lpString
0x18005a38f  mov     edx, 32Ah; nIDDlgItem
0x18005a394  mov     rcx, rsi; hDlg
0x18005a397  call    cs:__imp_SetDlgItemTextW
0x18005a39d  mov     edx, 32Ah; nIDDlgItem
0x18005a3a2  mov     rcx, rsi; hDlg
0x18005a3a5  call    cs:__imp_GetDlgItem
0x18005a3ab  mov     rcx, rax; hWnd
0x18005a3ae  xor     r9d, r9d; lParam
0x18005a3b1  xor     r8d, r8d; wParam
0x18005a3b4  mov     edx, 0B1h; Msg
0x18005a3b9  call    cs:__imp_SendMessageW
0x18005a3bf  mov     rcx, [rsp+290h+pv]; pv
0x18005a3c4  test    rcx, rcx
0x18005a3c7  jz      short loc_18005A3D4
0x18005a3c9  call    cs:__imp_CoTaskMemFree
0x18005a3cf  mov     [rsp+290h+pv], rbx
0x18005a3d4  mov     rcx, [rsp+290h+Control]; pv
0x18005a3d9  test    rcx, rcx
0x18005a3dc  jz      short loc_18005A3E4
0x18005a3de  call    cs:__imp_CoTaskMemFree
0x18005a3e4  test    r12d, r12d
0x18005a3e7  jz      short loc_18005A3EE
0x18005a3e9  mov     r8, r13
0x18005a3ec  jmp     short loc_18005A416
0x18005a3ee  lea     r9, [rdi+28h]; lpString
0x18005a3f2  mov     [rsp+290h+var_268], rbx; struct CContentFolder *
0x18005a3f7  mov     [rsp+290h+fuStyle], ebx; int
0x18005a3fb  mov     r8d, 32Ah; nIDDlgItem
0x18005a401  mov     rdx, [rdi+10h]; HWND
0x18005a405  mov     rcx, [rdi+20h]; struct _ITEMIDLIST *
0x18005a409  call    ?_ApplyRename@@YAHPEFAU_ITEMIDLIST@@PEAUHWND__@@HPEBGHPEAVCContentFolder@@@Z; _ApplyRename(_ITEMIDLIST *,HWND__ *,int,ushort const *,int,CContentFolder *)
0x18005a40e  test    eax, eax
0x18005a410  setz    bl
0x18005a413  mov     r8, rbx; dwNewLong
0x18005a416  xor     edx, edx; nIndex
0x18005a418  mov     rcx, rsi; hWnd
0x18005a41b  call    cs:__imp_SetWindowLongPtrW
0x18005a421  nop
0x18005a422  lea     rcx, [rsp+290h+var_250]
0x18005a427  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a42c  jmp     short loc_18005A49C
0x18005a42e  lea     r9, [rax+28h]; lpString
0x18005a432  xor     ebx, ebx
0x18005a434  mov     [rsp+290h+var_268], rbx; struct CContentFolder *
0x18005a439  mov     [rsp+290h+fuStyle], r13d; int
0x18005a43e  mov     r8d, 32Ah; nIDDlgItem
0x18005a444  mov     rdx, [rax+10h]; HWND
0x18005a448  mov     rcx, [rax+20h]; struct _ITEMIDLIST *
0x18005a44c  call    ?_ApplyRename@@YAHPEFAU_ITEMIDLIST@@PEAUHWND__@@HPEBGHPEAVCContentFolder@@@Z; _ApplyRename(_ITEMIDLIST *,HWND__ *,int,ushort const *,int,CContentFolder *)
0x18005a451  jmp     short loc_18005A49C
0x18005a453  mov     edx, 32Ch; nIDDlgItem
0x18005a458  mov     rcx, rsi; hDlg
0x18005a45b  call    cs:__imp_GetDlgItem
0x18005a461  mov     r8, rax; dwNewLong
0x18005a464  xor     edx, edx; nIndex
0x18005a466  mov     rcx, rsi; hWnd
0x18005a469  call    cs:__imp_SetWindowLongPtrW
0x18005a46f  jmp     short loc_18005A49C
0x18005a471  mov     rcx, [rax+460h]; this
0x18005a478  xor     ebx, ebx
0x18005a47a  test    rcx, rcx
0x18005a47d  jz      short loc_18005A49C
0x18005a47f  call    ?ClearAllHwndAccProperties@PropSheetAccAnnotation@@QEAAXXZ; PropSheetAccAnnotation::ClearAllHwndAccProperties(void)
0x18005a484  mov     rcx, [rdi+460h]; this
0x18005a48b  test    rcx, rcx
0x18005a48e  jz      short loc_18005A495
0x18005a490  call    ??_GPropSheetAccAnnotation@@QEAAPEAXI@Z; PropSheetAccAnnotation::`scalar deleting destructor'(uint)
0x18005a495  mov     [rdi+460h], rbx
0x18005a49c  mov     rax, r13
0x18005a49f  mov     rcx, [rbp+190h+var_30]
0x18005a4a6  xor     rcx, rsp; StackCookie
0x18005a4a9  call    __security_check_cookie
0x18005a4ae  lea     r11, [rsp+290h+var_20]
0x18005a4b6  mov     rbx, [r11+38h]
0x18005a4ba  mov     rsi, [r11+40h]
0x18005a4be  mov     rsp, r11
0x18005a4c1  pop     r14
0x18005a4c3  pop     r13
0x18005a4c5  pop     r12
0x18005a4c7  pop     rdi
0x18005a4c8  pop     rbp
0x18005a4c9  retn
```
