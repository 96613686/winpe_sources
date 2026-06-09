# Sched_RemoveSchedule(HWND__ *)

- ea: `0x18001419c`
- end: `0x180014314`
- name: `?Sched_RemoveSchedule@@YAHPEAUHWND__@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013e38`

## callees

- `0x1800130dc`
- `0x180013194`
- `0x180013238`
- `0x1800132bc`
- `0x18001419c`
- `0x18001d1f4`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `USER32!GetDlgItem` at `0x1800141c2`
- `USER32!GetDlgItem` at `0x1800141f6`
- `USER32!GetDlgItem` at `0x1800142dc`
- `USER32!GetDlgItem` at `0x1800141c2`
- `USER32!GetDlgItem` at `0x1800141f6`
- `USER32!GetDlgItem` at `0x1800142dc`
- `USER32!SendMessageW` at `0x1800141dd`
- `USER32!SendMessageW` at `0x1800142f0`
- `USER32!SendMessageW` at `0x1800141dd`
- `USER32!SendMessageW` at `0x1800142f0`
- `ole32!CoCreateInstance` at `0x180014283`
- `ole32!CoCreateInstance` at `0x180014283`
- `ole32!CoUninitialize` at `0x1800142ce`
- `ole32!CoUninitialize` at `0x1800142ce`
- `ole32!CoInitialize` at `0x180014252`
- `ole32!CoInitialize` at `0x180014252`

## pseudocode

```c
__int64 __fastcall Sched_RemoveSchedule(HWND hWnd)
{
  HWND DlgItem; // rdi
  int v3; // esi
  HWND v4; // rax
  struct SCHED_LIST_DATA *Data; // rbp
  int v6; // r9d
  HWND v7; // rax
  LPVOID ppv; // [rsp+30h] [rbp-258h] BYREF
  char v10[2]; // [rsp+40h] [rbp-248h] BYREF

  DlgItem = GetDlgItem(hWnd, 2105);
  v3 = SendMessageW(DlgItem, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
  if ( v3 >= 0 )
  {
    v4 = GetDlgItem(hWnd, 2105);
    Data = SchedList_GetData(v4, v3);
    if ( Data )
    {
      SchedList_GetName(DlgItem, v3, (unsigned __int16 *)v10, v6);
      if ( (unsigned int)WCMessageBox(hWnd, (char)v10) == 6 && CoInitialize(0) >= 0 )
      {
        ppv = 0;
        if ( CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv) >= 0 )
        {
          if ( (*(int (__fastcall **)(LPVOID, struct SCHED_LIST_DATA *))(*(_QWORD *)ppv + 48LL))(ppv, Data) >= 0 )
          {
            SchedList_DeleteData(DlgItem, -1, 1);
            SchedList_Select(DlgItem, 0);
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        CoUninitialize();
      }
      v7 = GetDlgItem(hWnd, 2105);
      SendMessageW(hWnd, 0x28u, (WPARAM)v7, 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001419c  push    rbx
0x18001419e  push    rbp
0x18001419f  push    rsi
0x1800141a0  push    rdi
0x1800141a1  sub     rsp, 268h
0x1800141a8  mov     rax, cs:__security_cookie
0x1800141af  xor     rax, rsp
0x1800141b2  mov     [rsp+288h+var_38], rax
0x1800141ba  mov     edx, 839h; nIDDlgItem
0x1800141bf  mov     rbx, rcx
0x1800141c2  call    cs:__imp_GetDlgItem
0x1800141c8  mov     r9d, 2; lParam
0x1800141ce  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800141d2  mov     rcx, rax; hWnd
0x1800141d5  mov     edx, 100Ch; Msg
0x1800141da  mov     rdi, rax
0x1800141dd  call    cs:__imp_SendMessageW
0x1800141e3  mov     rsi, rax
0x1800141e6  test    eax, eax
0x1800141e8  js      loc_1800142F6
0x1800141ee  mov     edx, 839h; nIDDlgItem
0x1800141f3  mov     rcx, rbx; hDlg
0x1800141f6  call    cs:__imp_GetDlgItem
0x1800141fc  mov     rcx, rax; HWND
0x1800141ff  mov     edx, esi; int
0x180014201  call    ?SchedList_GetData@@YAPEAUSCHED_LIST_DATA@@PEAUHWND__@@H@Z; SchedList_GetData(HWND__ *,int)
0x180014206  mov     rbp, rax
0x180014209  test    rax, rax
0x18001420c  jz      loc_1800142F6
0x180014212  lea     r8, [rsp+288h+var_248]; unsigned __int16 *
0x180014217  mov     edx, esi; int
0x180014219  mov     rcx, rdi; HWND
0x18001421c  call    ?SchedList_GetName@@YAXPEAUHWND__@@HPEAGH@Z; SchedList_GetName(HWND__ *,int,ushort *,int)
0x180014221  mov     edx, 2026h
0x180014226  lea     rax, [rsp+288h+var_248]
0x18001422b  mov     r9d, 34h ; '4'
0x180014231  mov     [rsp+288h+ppv], rax; char
0x180014236  mov     rcx, rbx; hWnd
0x180014239  lea     r8d, [rdx+9]
0x18001423d  call    WCMessageBox
0x180014242  mov     esi, 1
0x180014247  cmp     eax, 6
0x18001424a  jnz     loc_1800142D4
0x180014250  xor     ecx, ecx; pvReserved
0x180014252  call    cs:__imp_CoInitialize
0x180014258  test    eax, eax
0x18001425a  js      short loc_1800142D4
0x18001425c  lea     rax, [rsp+288h+var_258]
0x180014261  mov     [rsp+288h+var_258], 0
0x18001426a  lea     r9, IID_ISyncScheduleMgr; riid
0x180014271  mov     [rsp+288h+ppv], rax; ppv
0x180014276  xor     edx, edx; pUnkOuter
0x180014278  lea     r8d, [rsi+16h]; dwClsContext
0x18001427c  lea     rcx, CLSID_SyncMgr; rclsid
0x180014283  call    cs:__imp_CoCreateInstance
0x180014289  test    eax, eax
0x18001428b  js      short loc_1800142CE
0x18001428d  mov     rcx, [rsp+288h+var_258]
0x180014292  mov     rdx, rbp
0x180014295  mov     rax, [rcx]
0x180014298  mov     rax, [rax+30h]
0x18001429c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142a1  test    eax, eax
0x1800142a3  js      short loc_1800142BD
0x1800142a5  mov     r8d, esi; int
0x1800142a8  or      edx, 0FFFFFFFFh; int
0x1800142ab  mov     rcx, rdi; HWND
0x1800142ae  call    ?SchedList_DeleteData@@YAXPEAUHWND__@@HH@Z; SchedList_DeleteData(HWND__ *,int,int)
0x1800142b3  xor     edx, edx; int
0x1800142b5  mov     rcx, rdi; hWnd
0x1800142b8  call    ?SchedList_Select@@YAXPEAUHWND__@@H@Z; SchedList_Select(HWND__ *,int)
0x1800142bd  mov     rcx, [rsp+288h+var_258]
0x1800142c2  mov     rax, [rcx]
0x1800142c5  mov     rax, [rax+10h]
0x1800142c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ce  call    cs:__imp_CoUninitialize
0x1800142d4  mov     edx, 839h; nIDDlgItem
0x1800142d9  mov     rcx, rbx; hDlg
0x1800142dc  call    cs:__imp_GetDlgItem
0x1800142e2  mov     r9, rsi; lParam
0x1800142e5  mov     edx, 28h ; '('; Msg
0x1800142ea  mov     r8, rax; wParam
0x1800142ed  mov     rcx, rbx; hWnd
0x1800142f0  call    cs:__imp_SendMessageW
0x1800142f6  xor     eax, eax
0x1800142f8  mov     rcx, [rsp+288h+var_38]
0x180014300  xor     rcx, rsp; StackCookie
0x180014303  call    __security_check_cookie
0x180014308  add     rsp, 268h
0x18001430f  pop     rdi
0x180014310  pop     rsi
0x180014311  pop     rbp
0x180014312  pop     rbx
0x180014313  retn
```
