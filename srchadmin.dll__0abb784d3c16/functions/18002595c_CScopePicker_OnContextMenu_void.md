# CScopePicker::_OnContextMenu(void)

- ea: `0x18002595c`
- end: `0x180025b1c`
- name: `?_OnContextMenu@CScopePicker@@AEAA_JXZ`
- size: `448`
- prototype: `__int64 __fastcall(CScopePicker *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180026d90`

## callees

- `0x1800248f0`
- `0x1800251d0`
- `0x18002595c`
- `0x18002d324`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180025add`
- `SHELL32!ShellExecuteExW` at `0x180025add`
- `SHELL32!__imp_ILFree` at `0x180025af7`
- `SHELL32!__imp_ILFree` at `0x180025af7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ae7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x1800259a8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x1800259a8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessagePos` at `0x18002597f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessagePos` at `0x18002597f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800259be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025a18`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800259be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025a18`
- `USER32!TrackPopupMenuEx` at `0x180025a49`
- `USER32!TrackPopupMenuEx` at `0x180025a49`
- `USER32!GetSubMenu` at `0x180025a27`
- `USER32!GetSubMenu` at `0x180025a27`

## pseudocode

```c
__int64 __fastcall CScopePicker::_OnContextMenu(CScopePicker *this)
{
  __int64 v2; // rbx
  DWORD MessagePos; // eax
  HWND v4; // rcx
  LONG v5; // r15d
  int v6; // r12d
  struct _TREEITEM *v7; // rax
  struct _TREEITEM *v8; // r14
  int PidlAbs; // eax
  ITEMIDLIST *v10; // rsi
  HMENU SubMenu; // rax
  int v12; // eax
  CShellWrappers *v13; // rcx
  struct tagPOINT Point; // [rsp+30h] [rbp-59h] BYREF
  __int128 v16; // [rsp+38h] [rbp-51h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+50h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+F0h] [rbp+67h] BYREF

  v2 = 0;
  MessagePos = GetMessagePos();
  v4 = (HWND)*((_QWORD *)this + 3);
  v5 = (__int16)MessagePos;
  MessagePos >>= 16;
  v6 = (__int16)MessagePos;
  Point.y = (__int16)MessagePos;
  v16 = 0;
  Point.x = v5;
  ScreenToClient(v4, &Point);
  v7 = (struct _TREEITEM *)SendMessageW(*((HWND *)this + 3), 0x1111u, 0, (LPARAM)&Point);
  v8 = v7;
  if ( v7 && (*((_DWORD *)TreeView_GetParam(*((HWND *)this + 3), v7) + 5) & 0x2000) != 0 )
  {
    pv = 0;
    PidlAbs = CScopePicker::_GetPidlAbs(this, v8, (struct _ITEMIDLIST_ABSOLUTE **)&pv);
    v10 = (ITEMIDLIST *)pv;
    if ( PidlAbs >= 0 )
    {
      SendMessageW(*((HWND *)this + 3), 0x110Bu, 9u, (LPARAM)v8);
      SubMenu = GetSubMenu(*((HMENU *)this + 414), 0);
      v12 = TrackPopupMenuEx(SubMenu, 0x180u, v5, v6, *((HWND *)this + 1), 0);
      if ( v12 )
      {
        if ( v12 == 1202 )
        {
          pv = 0;
          v2 = 1;
          if ( CShellWrappers::GetPathFromAbsPidl(
                 v13,
                 (const struct _ITEMIDLIST_ABSOLUTE *)v10,
                 (unsigned __int16 **)&pv) >= 0 )
          {
            pExecInfo.hwnd = (HWND)*((_QWORD *)this + 1);
            pExecInfo.cbSize = 112;
            pExecInfo.lpVerb = L"properties";
            pExecInfo.fMask = 12;
            memset(&pExecInfo.lpFile, 0, 24);
            *(_QWORD *)&pExecInfo.nShow = 1;
            pExecInfo.hInstApp = 0;
            pExecInfo.lpIDList = v10;
            memset(&pExecInfo.lpClass, 0, 40);
            ShellExecuteExW(&pExecInfo);
          }
          CoTaskMemFree(pv);
        }
      }
      else
      {
        v2 = 1;
      }
    }
    ILFree(v10);
  }
  return v2;
}

```

## disassembly

```asm
0x18002595c  mov     [rsp-8+arg_8], rbx
0x180025961  mov     [rsp-8+arg_10], rsi
0x180025966  push    rbp
0x180025967  push    rdi
0x180025968  push    r12
0x18002596a  push    r14
0x18002596c  push    r15
0x18002596e  lea     rbp, [rsp-37h]
0x180025973  sub     rsp, 0C0h
0x18002597a  mov     rdi, rcx
0x18002597d  xor     ebx, ebx
0x18002597f  call    cs:__imp_GetMessagePos
0x180025985  mov     rcx, [rdi+18h]; hWnd
0x180025989  lea     rdx, [rbp+57h+Point]; lpPoint
0x18002598d  movsx   r15d, ax
0x180025991  xorps   xmm0, xmm0
0x180025994  shr     eax, 10h
0x180025997  movsx   r12d, ax
0x18002599b  mov     [rbp+57h+Point.y], r12d
0x18002599f  movdqu  [rbp+57h+var_A8], xmm0
0x1800259a4  mov     [rbp+57h+Point.x], r15d
0x1800259a8  call    cs:__imp_ScreenToClient
0x1800259ae  mov     rcx, [rdi+18h]; hWnd
0x1800259b2  lea     r9, [rbp+57h+Point]; lParam
0x1800259b6  xor     r8d, r8d; wParam
0x1800259b9  mov     edx, 1111h; Msg
0x1800259be  call    cs:__imp_SendMessageW
0x1800259c4  mov     r14, rax
0x1800259c7  test    rax, rax
0x1800259ca  jz      loc_180025AFD
0x1800259d0  mov     rcx, [rdi+18h]; HWND
0x1800259d4  mov     rdx, rax; struct _TREEITEM *
0x1800259d7  call    ?TreeView_GetParam@@YAPEAUSTreeNodeState@@PEAUHWND__@@PEAU_TREEITEM@@@Z; TreeView_GetParam(HWND__ *,_TREEITEM *)
0x1800259dc  test    dword ptr [rax+14h], 2000h
0x1800259e3  jz      loc_180025AFD
0x1800259e9  lea     r8, [rbp+57h+pv]; struct _ITEMIDLIST_ABSOLUTE **
0x1800259ed  mov     [rbp+57h+pv], rbx
0x1800259f1  mov     rdx, r14; struct _TREEITEM *
0x1800259f4  mov     rcx, rdi; this
0x1800259f7  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x1800259fc  mov     rsi, [rbp+57h+pv]
0x180025a00  test    eax, eax
0x180025a02  js      loc_180025AF4
0x180025a08  mov     rcx, [rdi+18h]; hWnd
0x180025a0c  lea     r8d, [rbx+9]; wParam
0x180025a10  mov     r9, r14; lParam
0x180025a13  mov     edx, 110Bh; Msg
0x180025a18  call    cs:__imp_SendMessageW
0x180025a1e  mov     rcx, [rdi+0CF0h]; hMenu
0x180025a25  xor     edx, edx; nPos
0x180025a27  call    cs:__imp_GetSubMenu
0x180025a2d  mov     [rsp+0E0h+lptpm], rbx; lptpm
0x180025a32  mov     r9d, r12d; y
0x180025a35  mov     rcx, rax; hMenu
0x180025a38  mov     r8d, r15d; x
0x180025a3b  mov     rax, [rdi+8]
0x180025a3f  mov     edx, 180h; uFlags
0x180025a44  mov     [rsp+0E0h+hwnd], rax; hwnd
0x180025a49  call    cs:__imp_TrackPopupMenuEx
0x180025a4f  test    eax, eax
0x180025a51  jz      loc_180025AEF
0x180025a57  cmp     eax, 4B2h
0x180025a5c  jnz     loc_180025AF4
0x180025a62  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x180025a66  mov     [rbp+57h+pv], rbx
0x180025a6a  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180025a6d  call    ?GetPathFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAG@Z; CShellWrappers::GetPathFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort * *)
0x180025a72  mov     ebx, 1
0x180025a77  test    eax, eax
0x180025a79  js      short loc_180025AE3
0x180025a7b  mov     rax, [rdi+8]
0x180025a7f  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x180025a83  xorps   xmm0, xmm0
0x180025a86  mov     [rbp+57h+pExecInfo.hwnd], rax
0x180025a8a  lea     rax, aProperties; "properties"
0x180025a91  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180025a98  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x180025a9c  mov     [rbp+57h+pExecInfo.fMask], 0Ch
0x180025aa3  mov     [rbp+57h+pExecInfo.lpFile], 0
0x180025aab  movdqa  xmmword ptr [rbp+57h+pExecInfo.lpParameters], xmm0
0x180025ab0  mov     qword ptr [rbp+57h+pExecInfo.nShow], rbx
0x180025ab4  mov     [rbp+57h+pExecInfo.hInstApp], 0
0x180025abc  mov     [rbp+57h+pExecInfo.lpIDList], rsi
0x180025ac0  mov     [rbp+57h+pExecInfo.lpClass], 0
0x180025ac8  mov     [rbp+57h+pExecInfo.hkeyClass], 0
0x180025ad0  mov     qword ptr [rbp+57h+pExecInfo.dwHotKey], 0
0x180025ad8  movdqa  xmmword ptr [rbp+57h+pExecInfo.60h], xmm0
0x180025add  call    cs:__imp_ShellExecuteExW
0x180025ae3  mov     rcx, [rbp+57h+pv]; pv
0x180025ae7  call    cs:__imp_CoTaskMemFree
0x180025aed  jmp     short loc_180025AF4
0x180025aef  mov     ebx, 1
0x180025af4  mov     rcx, rsi; pidl
0x180025af7  call    cs:__imp_ILFree
0x180025afd  lea     r11, [rsp+0E0h+var_20]
0x180025b05  mov     rax, rbx
0x180025b08  mov     rbx, [r11+38h]
0x180025b0c  mov     rsi, [r11+40h]
0x180025b10  mov     rsp, r11
0x180025b13  pop     r15
0x180025b15  pop     r14
0x180025b17  pop     r12
0x180025b19  pop     rdi
0x180025b1a  pop     rbp
0x180025b1b  retn
```
