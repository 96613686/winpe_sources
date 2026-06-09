# fnOrgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800571d0`
- end: `0x18005735e`
- name: `?fnOrgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `398`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18004d808`
- `0x18004e2d8`
- `0x1800571d0`
- `0x180067570`
- `0x180068088`

## import_xrefs

- `USER32!SendMessageW` at `0x180057229`
- `USER32!SendMessageW` at `0x1800572ee`
- `USER32!SendMessageW` at `0x180057229`
- `USER32!SendMessageW` at `0x1800572ee`
- `USER32!GetDlgItem` at `0x18005724f`
- `USER32!GetDlgItem` at `0x18005726e`
- `USER32!GetDlgItem` at `0x18005731b`
- `USER32!GetDlgItem` at `0x180057331`
- `USER32!GetDlgItem` at `0x18005724f`
- `USER32!GetDlgItem` at `0x18005726e`
- `USER32!GetDlgItem` at `0x18005731b`
- `USER32!GetDlgItem` at `0x180057331`
- `USER32!UpdateWindow` at `0x180057284`
- `USER32!UpdateWindow` at `0x180057284`
- `USER32!SetWindowLongPtrW` at `0x180057241`
- `USER32!SetWindowLongPtrW` at `0x180057241`
- `USER32!GetWindowLongPtrW` at `0x1800571eb`
- `USER32!GetWindowLongPtrW` at `0x1800571eb`
- `USER32!GetParent` at `0x180057215`
- `USER32!GetParent` at `0x180057215`

## pseudocode

```c
__int64 __fastcall fnOrgProc(HWND hDlg, int a2, WPARAM a3, LONG_PTR a4)
{
  LONG_PTR WindowLongPtrW; // r14
  int v9; // edi
  int v10; // edi
  HWND Parent; // rax
  HWND v13; // rax
  HWND v14; // rax
  int v15; // eax
  WPARAM v16; // rbx
  struct _FILETIME *v17; // r9
  HWND DlgItem; // rax
  HWND v19; // rax
  __int64 v20; // rcx

  WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
  v9 = a2 - 78;
  if ( !v9 )
  {
    v15 = *(_DWORD *)(a4 + 16);
    if ( v15 != -203 )
    {
      if ( v15 != -202 )
      {
        if ( v15 == -155 )
        {
          if ( *(_WORD *)(a4 + 24) != 13 )
            return 1;
        }
        else if ( v15 != -3 )
        {
          return 1;
        }
        v16 = a3 - 2801;
        if ( (!v16 || v16 == 2) && (unsigned int)SendMessageW(*(HWND *)a4, 0x1032u, 0, 0) == 1 )
          HrShowLVEntryProperties(*(HWND *)a4, 0, *(struct IAddrBook **)(*(_QWORD *)(WindowLongPtrW + 48) + 96LL), v17);
        return 1;
      }
      *(_DWORD *)(*(_QWORD *)(WindowLongPtrW + 48) + 32LL) = 1;
    }
    DlgItem = GetDlgItem(hDlg, 2801);
    FreeOrgLVData(DlgItem);
    v19 = GetDlgItem(hDlg, 2803);
    FreeOrgLVData(v19);
    v20 = *(_QWORD *)(WindowLongPtrW + 48);
    if ( !*(_DWORD *)(v20 + 32) )
      *(_DWORD *)(v20 + 32) = 2;
    return 1;
  }
  v10 = v9 - 194;
  if ( !v10 )
  {
    SetWindowLongPtrW(hDlg, 16, a4);
    v13 = GetDlgItem(hDlg, 2801);
    HrInitListView(v13, 1u, 0);
    v14 = GetDlgItem(hDlg, 2803);
    HrInitListView(v14, 1u, 0);
    UpdateWindow(hDlg);
    FillOrgData(hDlg, *(struct _PropArrayInfo **)(a4 + 48));
    return 1;
  }
  if ( v10 == 1 && (_WORD)a3 == 2 )
  {
    Parent = GetParent(hDlg);
    SendMessageW(Parent, 0x111u, a3, a4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800571d0  push    rbx
0x1800571d2  push    rbp
0x1800571d3  push    rsi
0x1800571d4  push    rdi
0x1800571d5  push    r14
0x1800571d7  sub     rsp, 20h
0x1800571db  mov     edi, edx
0x1800571dd  mov     rsi, r9
0x1800571e0  mov     edx, 10h; nIndex
0x1800571e5  mov     rbx, r8
0x1800571e8  mov     rbp, rcx
0x1800571eb  call    cs:__imp_GetWindowLongPtrW
0x1800571f1  mov     r14, rax
0x1800571f4  sub     edi, 4Eh ; 'N'
0x1800571f7  jz      loc_18005729B
0x1800571fd  sub     edi, 0C2h
0x180057203  jz      short loc_180057236
0x180057205  cmp     edi, 1
0x180057208  jnz     short loc_18005722F
0x18005720a  lea     eax, [rdi+1]
0x18005720d  cmp     bx, ax
0x180057210  jnz     short loc_18005722F
0x180057212  mov     rcx, rbp; hWnd
0x180057215  call    cs:__imp_GetParent
0x18005721b  mov     r9, rsi; lParam
0x18005721e  mov     r8, rbx; wParam
0x180057221  mov     rcx, rax; hWnd
0x180057224  mov     edx, 111h; Msg
0x180057229  call    cs:__imp_SendMessageW
0x18005722f  xor     eax, eax
0x180057231  jmp     loc_180057353
0x180057236  mov     r8, rsi; dwNewLong
0x180057239  mov     edx, 10h; nIndex
0x18005723e  mov     rcx, rbp; hWnd
0x180057241  call    cs:__imp_SetWindowLongPtrW
0x180057247  mov     edx, 0AF1h; nIDDlgItem
0x18005724c  mov     rcx, rbp; hDlg
0x18005724f  call    cs:__imp_GetDlgItem
0x180057255  xor     r8d, r8d; int
0x180057258  mov     rcx, rax; hWnd
0x18005725b  lea     edi, [r8+1]
0x18005725f  mov     edx, edi; unsigned int
0x180057261  call    ?HrInitListView@@YAJPEAUHWND__@@KH@Z; HrInitListView(HWND__ *,ulong,int)
0x180057266  mov     edx, 0AF3h; nIDDlgItem
0x18005726b  mov     rcx, rbp; hDlg
0x18005726e  call    cs:__imp_GetDlgItem
0x180057274  xor     r8d, r8d; int
0x180057277  mov     edx, edi; unsigned int
0x180057279  mov     rcx, rax; hWnd
0x18005727c  call    ?HrInitListView@@YAJPEAUHWND__@@KH@Z; HrInitListView(HWND__ *,ulong,int)
0x180057281  mov     rcx, rbp; hWnd
0x180057284  call    cs:__imp_UpdateWindow
0x18005728a  mov     rdx, [rsi+30h]; struct _PropArrayInfo *
0x18005728e  mov     rcx, rbp; hDlg
0x180057291  call    ?FillOrgData@@YAXPEAUHWND__@@PEAU_PropArrayInfo@@@Z; FillOrgData(HWND__ *,_PropArrayInfo *)
0x180057296  jmp     loc_180057350
0x18005729b  mov     eax, [rsi+10h]
0x18005729e  mov     edi, 1
0x1800572a3  cmp     eax, 0FFFFFF35h
0x1800572a8  jz      short loc_180057313
0x1800572aa  cmp     eax, 0FFFFFF36h
0x1800572af  jz      short loc_18005730C
0x1800572b1  cmp     eax, 0FFFFFF65h
0x1800572b6  jz      short loc_1800572C2
0x1800572b8  cmp     eax, 0FFFFFFFDh
0x1800572bb  jz      short loc_1800572CD
0x1800572bd  jmp     loc_180057350
0x1800572c2  cmp     word ptr [rsi+18h], 0Dh
0x1800572c7  jnz     loc_180057350
0x1800572cd  sub     rbx, 0AF1h
0x1800572d4  jz      short loc_1800572E0
0x1800572d6  mov     eax, 2
0x1800572db  cmp     rbx, rax
0x1800572de  jnz     short loc_180057350
0x1800572e0  mov     rcx, [rsi]; hWnd
0x1800572e3  xor     r9d, r9d; lParam
0x1800572e6  xor     r8d, r8d; wParam
0x1800572e9  mov     edx, 1032h; Msg
0x1800572ee  call    cs:__imp_SendMessageW
0x1800572f4  cmp     eax, edi
0x1800572f6  jnz     short loc_180057350
0x1800572f8  mov     r8, [r14+30h]
0x1800572fc  xor     edx, edx; unsigned int
0x1800572fe  mov     rcx, [rsi]; hWnd
0x180057301  mov     r8, [r8+60h]; struct IAddrBook *
0x180057305  call    ?HrShowLVEntryProperties@@YAJPEAUHWND__@@KPEAUIAddrBook@@PEAU_FILETIME@@@Z; HrShowLVEntryProperties(HWND__ *,ulong,IAddrBook *,_FILETIME *)
0x18005730a  jmp     short loc_180057350
0x18005730c  mov     rax, [r14+30h]
0x180057310  mov     [rax+20h], edi
0x180057313  mov     edx, 0AF1h; nIDDlgItem
0x180057318  mov     rcx, rbp; hDlg
0x18005731b  call    cs:__imp_GetDlgItem
0x180057321  mov     rcx, rax; hWnd
0x180057324  call    ?FreeOrgLVData@@YAXPEAUHWND__@@@Z; FreeOrgLVData(HWND__ *)
0x180057329  mov     edx, 0AF3h; nIDDlgItem
0x18005732e  mov     rcx, rbp; hDlg
0x180057331  call    cs:__imp_GetDlgItem
0x180057337  mov     rcx, rax; hWnd
0x18005733a  call    ?FreeOrgLVData@@YAXPEAUHWND__@@@Z; FreeOrgLVData(HWND__ *)
0x18005733f  mov     rcx, [r14+30h]
0x180057343  cmp     dword ptr [rcx+20h], 0
0x180057347  jnz     short loc_180057350
0x180057349  mov     dword ptr [rcx+20h], 2
0x180057350  mov     rax, rdi
0x180057353  add     rsp, 20h
0x180057357  pop     r14
0x180057359  pop     rdi
0x18005735a  pop     rsi
0x18005735b  pop     rbp
0x18005735c  pop     rbx
0x18005735d  retn
```
