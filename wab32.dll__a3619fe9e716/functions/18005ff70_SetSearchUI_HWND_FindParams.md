# SetSearchUI(HWND__ *,_FindParams *)

- ea: `0x18005ff70`
- end: `0x18006037a`
- name: `?SetSearchUI@@YAHPEAUHWND__@@PEAU_FindParams@@@Z`
- size: `1034`
- prototype: `__int64 __fastcall(HWND hWnd, struct _FindParams *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180060850`

## callees

- `0x180001d18`
- `0x1800045e4`
- `0x18001d778`
- `0x18001dc44`
- `0x180033ae0`
- `0x18005ce28`
- `0x18005f8ac`
- `0x18005ff70`
- `0x180067570`
- `0x180068c4c`
- `0x18006a750`
- `0x180091e92`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `GDI32!RectVisible` at `0x180060265`
- `GDI32!RectVisible` at `0x180060265`
- `USER32!LoadStringW` at `0x18006031f`
- `USER32!LoadStringW` at `0x18006031f`
- `USER32!SendMessageW` at `0x180060004`
- `USER32!SendMessageW` at `0x18006002d`
- `USER32!SendMessageW` at `0x18006006d`
- `USER32!SendMessageW` at `0x180060089`
- `USER32!SendMessageW` at `0x18006009f`
- `USER32!SendMessageW` at `0x1800602ef`
- `USER32!SendMessageW` at `0x180060004`
- `USER32!SendMessageW` at `0x18006002d`
- `USER32!SendMessageW` at `0x18006006d`
- `USER32!SendMessageW` at `0x180060089`
- `USER32!SendMessageW` at `0x18006009f`
- `USER32!SendMessageW` at `0x1800602ef`
- `USER32!EnableWindow` at `0x18006013b`
- `USER32!EnableWindow` at `0x18006013b`
- `USER32!GetDlgItem` at `0x18005fff2`
- `USER32!GetDlgItem` at `0x18006001b`
- `USER32!GetDlgItem` at `0x18006003d`
- `USER32!GetDlgItem` at `0x180060057`
- `USER32!GetDlgItem` at `0x1800600cc`
- `USER32!GetDlgItem` at `0x180060117`
- `USER32!GetDlgItem` at `0x1800602db`
- `USER32!GetDlgItem` at `0x18006033a`
- `USER32!GetDlgItem` at `0x18005fff2`
- `USER32!GetDlgItem` at `0x18006001b`
- `USER32!GetDlgItem` at `0x18006003d`
- `USER32!GetDlgItem` at `0x180060057`
- `USER32!GetDlgItem` at `0x1800600cc`
- `USER32!GetDlgItem` at `0x180060117`
- `USER32!GetDlgItem` at `0x1800602db`
- `USER32!GetDlgItem` at `0x18006033a`
- `USER32!SetWindowTextW` at `0x18006020f`
- `USER32!SetWindowTextW` at `0x18006032c`
- `USER32!SetWindowTextW` at `0x18006020f`
- `USER32!SetWindowTextW` at `0x18006032c`
- `USER32!ShowWindow` at `0x18006012d`
- `USER32!ShowWindow` at `0x18006012d`
- `USER32!GetDC` at `0x180060254`
- `USER32!GetDC` at `0x180060254`
- `USER32!ReleaseDC` at `0x180060272`
- `USER32!ReleaseDC` at `0x180060272`
- `USER32!GetWindowLongW` at `0x1800600df`
- `USER32!GetWindowLongW` at `0x1800600df`
- `USER32!SetWindowLongW` at `0x1800600f0`
- `USER32!SetWindowLongW` at `0x1800600f0`
- `USER32!MoveWindow` at `0x1800602bd`
- `USER32!MoveWindow` at `0x1800602bd`
- `IMM32!ImmAssociateContext` at `0x180060345`
- `IMM32!ImmAssociateContext` at `0x180060345`

## pseudocode

```c
__int64 __fastcall SetSearchUI(HWND hWnd, struct _FindParams *a2)
{
  __int64 i; // rbx
  HWND DlgItem; // rax
  HWND v6; // rax
  HWND v7; // rax
  HWND v8; // rbx
  __int64 *v9; // rax
  __int64 v10; // r15
  HWND v11; // rbx
  LONG WindowLongW; // eax
  int j; // r12d
  __int64 v14; // rbx
  __int64 v15; // rdi
  CHAR *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rbx
  size_t v19; // r8
  __int64 v20; // rcx
  HDC DC; // rdi
  BOOL v22; // ebx
  int v23; // r9d
  LONG left; // edx
  LONG top; // r8d
  int v26; // ecx
  WPARAM v27; // rbx
  HWND v28; // rax
  HWND v29; // rax
  HWND hWnda; // [rsp+30h] [rbp-D0h]
  void *v32; // [rsp+38h] [rbp-C8h] BYREF
  RECT rect; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+84h] [rbp-7Ch]
  WCHAR String[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF

  rect.left = 0;
  memset_0(&rect.top, 0, 0x48u);
  AddTabItem(hWnd, 0);
  AddTabItem(hWnd, 1);
  for ( i = 0; i != 5; ++i )
  {
    DlgItem = GetDlgItem(hWnd, *((_DWORD *)&rgSearchEditID + i));
    SendMessageW(DlgItem, 0xC5u, 0xB8u, 0);
  }
  v6 = GetDlgItem(hWnd, 2792);
  SendMessageW(v6, 0xC5u, 0xB8u, 0);
  v7 = GetDlgItem(hWnd, 1168);
  HrInitListView(v7, 1u, 1);
  v8 = GetDlgItem(hWnd, 1170);
  if ( (unsigned int)SendMessageW(v8, 0x467u, 0, 1171) && (unsigned int)SendMessageW(v8, 0x465u, 0, 0x10000) )
    SendMessageW(v8, 0x466u, 0, 0);
  v9 = (__int64 *)*((_QWORD *)a2 + 305);
  if ( v9 )
  {
    v10 = *v9;
    if ( *v9 )
    {
      if ( *((_DWORD *)v9 + 8) == 1 )
      {
        v11 = GetDlgItem(hWnd, 1168);
        WindowLongW = GetWindowLongW(v11, -16);
        SetWindowLongW(v11, -16, WindowLongW | 4);
      }
      for ( j = 0; j < *(_DWORD *)(v10 + 96); ++j )
      {
        v14 = j;
        hWnda = GetDlgItem(hWnd, *((_DWORD *)&rgAdrParmButtonID + j));
        ShowWindow(hWnda, 1);
        EnableWindow(hWnda, 1);
        v15 = *(_QWORD *)(v10 + 104);
        if ( v15 )
        {
          v16 = *(CHAR **)(v15 + 8LL * j);
          if ( *(int *)(v10 + 16) >= 0 )
            v16 = (CHAR *)ConvertAtoW(v16);
          v32 = v16;
          if ( v16 )
          {
            v17 = -1;
            do
              ++v17;
            while ( *(_WORD *)&v16[2 * v17] );
            if ( (unsigned int)v17 <= 0x1C )
            {
              StringCchCopyW(String, 0x20u, (const unsigned __int16 *)v16);
            }
            else
            {
              v18 = TruncatePos((unsigned __int16 *)v16, 0x1Cu);
              v19 = 64;
              if ( (unsigned __int64)(2 * v18) < 0x40 )
                v19 = 2 * v18;
              memcpy_0(String, v16, v19);
              if ( (unsigned int)v18 >= 0x1C )
              {
                v20 = 28;
              }
              else
              {
                v20 = v18;
                if ( (unsigned __int64)(2 * v18) >= 0x40 )
                  _report_rangecheckfailure();
              }
              v14 = j;
              String[v20] = 0;
            }
            StringCchCatW(String, 0x20u, L" ->");
            SetWindowTextW(hWnda, String);
            if ( v16 != *(CHAR **)(*(_QWORD *)(v10 + 104) + 8 * v14) )
              LocalFreeAndNull(&v32);
          }
        }
      }
    }
  }
  if ( (unsigned int)ReadRegistryPositionInfo(
                       (struct AddressBook *)(-(__int64)(*(_QWORD *)a2 != 0) & (*(_QWORD *)a2 - 632LL)),
                       (BYTE *)&rect,
                       (const unsigned __int16 *)-(__int64)(*(_QWORD *)a2 != 0)) )
  {
    DC = GetDC(0);
    v22 = RectVisible(DC, &rect);
    ReleaseDC(0, DC);
    if ( !v22 )
      goto LABEL_37;
    v23 = *((_DWORD *)a2 + 618);
    left = rect.left;
    top = rect.top;
    if ( rect.right - rect.left >= v23 )
      v23 = rect.right - rect.left;
  }
  else
  {
    v23 = *((_DWORD *)a2 + 618);
    left = 20;
    top = 20;
  }
  MoveWindow(hWnd, left, top, v23, *((_DWORD *)a2 + 619), 0);
LABEL_37:
  v26 = v34;
  if ( v34 > 2 )
    v26 = 0;
  v34 = v26;
  v27 = v26;
  v28 = GetDlgItem(hWnd, 100);
  SendMessageW(v28, 0x130Cu, v27, 0);
  if ( *((_DWORD *)a2 + 612) )
    ResizeSearchDlg(hWnd, a2);
  LoadStringW(hinstMapiX, 0x10B9u, Buffer, 260);
  SetWindowTextW(hWnd, Buffer);
  v29 = GetDlgItem(hWnd, 1159);
  ImmAssociateContext(v29, 0);
  return 1;
}

```

## disassembly

```asm
0x18005ff70  mov     [rsp-8+arg_10], rbx
0x18005ff75  push    rbp
0x18005ff76  push    rsi
0x18005ff77  push    rdi
0x18005ff78  push    r12
0x18005ff7a  push    r13
0x18005ff7c  push    r14
0x18005ff7e  push    r15
0x18005ff80  lea     rbp, [rsp-1F0h]
0x18005ff88  sub     rsp, 2F0h
0x18005ff8f  mov     rax, cs:__security_cookie
0x18005ff96  xor     rax, rsp
0x18005ff99  mov     [rbp+220h+var_40], rax
0x18005ffa0  xor     r13d, r13d
0x18005ffa3  mov     r14, rdx
0x18005ffa6  mov     rsi, rcx
0x18005ffa9  mov     [rsp+320h+rect.left], r13d
0x18005ffae  xor     edx, edx; Val
0x18005ffb0  lea     rcx, [rsp+320h+rect.top]; void *
0x18005ffb5  lea     r8d, [r13+48h]; Size
0x18005ffb9  call    memset_0
0x18005ffbe  xor     edx, edx; int
0x18005ffc0  mov     rcx, rsi; HWND
0x18005ffc3  call    ?AddTabItem@@YAXPEAUHWND__@@H@Z; AddTabItem(HWND__ *,int)
0x18005ffc8  lea     edx, [r13+1]; int
0x18005ffcc  mov     rcx, rsi; HWND
0x18005ffcf  call    ?AddTabItem@@YAXPEAUHWND__@@H@Z; AddTabItem(HWND__ *,int)
0x18005ffd4  mov     edi, 0B8h
0x18005ffd9  mov     ebx, r13d
0x18005ffdc  lea     r13, __ImageBase
0x18005ffe3  lea     r15d, [rdi+0Dh]
0x18005ffe7  mov     edx, ds:rva ?rgSearchEditID@@3PAHA[r13+rbx*4]; nIDDlgItem
0x18005ffef  mov     rcx, rsi; hDlg
0x18005fff2  call    cs:__imp_GetDlgItem
0x18005fff8  xor     r9d, r9d; lParam
0x18005fffb  mov     r8, rdi; wParam
0x18005fffe  mov     rcx, rax; hWnd
0x180060001  mov     edx, r15d; Msg
0x180060004  call    cs:__imp_SendMessageW
0x18006000a  inc     rbx
0x18006000d  cmp     rbx, 5
0x180060011  jnz     short loc_18005FFE7
0x180060013  mov     edx, 0AE8h; nIDDlgItem
0x180060018  mov     rcx, rsi; hDlg
0x18006001b  call    cs:__imp_GetDlgItem
0x180060021  xor     r9d, r9d; lParam
0x180060024  mov     r8, rdi; wParam
0x180060027  mov     rcx, rax; hWnd
0x18006002a  mov     edx, r15d; Msg
0x18006002d  call    cs:__imp_SendMessageW
0x180060033  mov     edi, 490h
0x180060038  mov     rcx, rsi; hDlg
0x18006003b  mov     edx, edi; nIDDlgItem
0x18006003d  call    cs:__imp_GetDlgItem
0x180060043  lea     edx, [rbx-4]; unsigned int
0x180060046  mov     rcx, rax; hWnd
0x180060049  mov     r8d, edx; int
0x18006004c  call    ?HrInitListView@@YAJPEAUHWND__@@KH@Z; HrInitListView(HWND__ *,ulong,int)
0x180060051  lea     edx, [rdi+2]; nIDDlgItem
0x180060054  mov     rcx, rsi; hDlg
0x180060057  call    cs:__imp_GetDlgItem
0x18006005d  lea     r9d, [rdi+3]; lParam
0x180060061  xor     r8d, r8d; wParam
0x180060064  mov     rcx, rax; hWnd
0x180060067  lea     edx, [rdi-29h]; Msg
0x18006006a  mov     rbx, rax
0x18006006d  call    cs:__imp_SendMessageW
0x180060073  xor     r13d, r13d
0x180060076  test    eax, eax
0x180060078  jz      short loc_1800600A5
0x18006007a  mov     r9d, 10000h; lParam
0x180060080  lea     edx, [rdi-2Bh]; Msg
0x180060083  xor     r8d, r8d; wParam
0x180060086  mov     rcx, rbx; hWnd
0x180060089  call    cs:__imp_SendMessageW
0x18006008f  test    eax, eax
0x180060091  jz      short loc_1800600A5
0x180060093  xor     r9d, r9d; lParam
0x180060096  lea     edx, [rdi-2Ah]; Msg
0x180060099  xor     r8d, r8d; wParam
0x18006009c  mov     rcx, rbx; hWnd
0x18006009f  call    cs:__imp_SendMessageW
0x1800600a5  mov     rax, [r14+988h]
0x1800600ac  test    rax, rax
0x1800600af  jz      loc_180060231
0x1800600b5  mov     r15, [rax]
0x1800600b8  test    r15, r15
0x1800600bb  jz      loc_180060231
0x1800600c1  cmp     dword ptr [rax+20h], 1
0x1800600c5  jnz     short loc_1800600F6
0x1800600c7  mov     edx, edi; nIDDlgItem
0x1800600c9  mov     rcx, rsi; hDlg
0x1800600cc  call    cs:__imp_GetDlgItem
0x1800600d2  mov     edi, 0FFFFFFF0h
0x1800600d7  mov     rcx, rax; hWnd
0x1800600da  mov     edx, edi; nIndex
0x1800600dc  mov     rbx, rax
0x1800600df  call    cs:__imp_GetWindowLongW
0x1800600e5  mov     edx, edi; nIndex
0x1800600e7  mov     rcx, rbx; hWnd
0x1800600ea  or      eax, 4
0x1800600ed  mov     r8d, eax; dwNewLong
0x1800600f0  call    cs:__imp_SetWindowLongW
0x1800600f6  mov     r12d, r13d
0x1800600f9  cmp     r12d, [r15+60h]
0x1800600fd  jge     loc_180060231
0x180060103  lea     rax, __ImageBase
0x18006010a  movsxd  rbx, r12d
0x18006010d  mov     rcx, rsi; hDlg
0x180060110  mov     edx, ds:rva ?rgAdrParmButtonID@@3PAHA[rax+rbx*4]; nIDDlgItem
0x180060117  call    cs:__imp_GetDlgItem
0x18006011d  mov     rcx, rax; hWnd
0x180060120  mov     [rsp+320h+hWnd], rax
0x180060125  mov     edx, 1; nCmdShow
0x18006012a  mov     rdi, rax
0x18006012d  call    cs:__imp_ShowWindow
0x180060133  mov     edx, 1; bEnable
0x180060138  mov     rcx, rdi; hWnd
0x18006013b  call    cs:__imp_EnableWindow
0x180060141  mov     rdi, [r15+68h]
0x180060145  test    rdi, rdi
0x180060148  jz      loc_180060229
0x18006014e  mov     rdi, [rdi+rbx*8]
0x180060152  cmp     [r15+10h], r13d
0x180060156  jl      short loc_180060163
0x180060158  mov     rcx, rdi; lpMultiByteStr
0x18006015b  call    ?ConvertAtoW@@YAPEAGPEBD@Z; ConvertAtoW(char const *)
0x180060160  mov     rdi, rax
0x180060163  mov     [rsp+320h+var_2E8], rdi
0x180060168  test    rdi, rdi
0x18006016b  jz      loc_180060229
0x180060171  or      rax, 0FFFFFFFFFFFFFFFFh
0x180060175  inc     rax
0x180060178  cmp     [rdi+rax*2], r13w
0x18006017d  jnz     short loc_180060175
0x18006017f  cmp     eax, 1Ch
0x180060182  jbe     short loc_1800601E0
0x180060184  mov     edx, 1Ch; unsigned int
0x180060189  mov     rcx, rdi; unsigned __int16 *
0x18006018c  call    ?TruncatePos@@YAKPEAGK@Z; TruncatePos(ushort *,ulong)
0x180060191  mov     ebx, eax
0x180060193  lea     rcx, [rbp+220h+String]; void *
0x180060197  mov     r8d, 40h ; '@'
0x18006019d  mov     rdx, rdi; Src
0x1800601a0  lea     rax, ds:0[rbx*2]
0x1800601a8  cmp     rax, r8
0x1800601ab  cmovb   r8, rax; Size
0x1800601af  call    memcpy_0
0x1800601b4  cmp     ebx, 1Ch
0x1800601b7  jnb     short loc_1800601CD
0x1800601b9  lea     rcx, ds:0[rbx*2]
0x1800601c1  cmp     rcx, 40h ; '@'
0x1800601c5  jb      short loc_1800601D2
0x1800601c7  call    __report_rangecheckfailure
0x1800601cd  mov     ecx, 38h ; '8'
0x1800601d2  xor     r13d, r13d
0x1800601d5  movsxd  rbx, r12d
0x1800601d8  mov     [rbp+rcx+220h+String], r13w
0x1800601de  jmp     short loc_1800601F1
0x1800601e0  mov     r8, rdi; unsigned __int16 *
0x1800601e3  lea     rcx, [rbp+220h+String]; unsigned __int16 *
0x1800601e7  mov     edx, 20h ; ' '; unsigned __int64
0x1800601ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800601f1  lea     r8, asc_18009D8B8; " ->"
0x1800601f8  mov     edx, 20h ; ' '; unsigned __int64
0x1800601fd  lea     rcx, [rbp+220h+String]; unsigned __int16 *
0x180060201  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180060206  mov     rcx, [rsp+320h+hWnd]; hWnd
0x18006020b  lea     rdx, [rbp+220h+String]; lpString
0x18006020f  call    cs:__imp_SetWindowTextW
0x180060215  mov     rax, [r15+68h]
0x180060219  cmp     rdi, [rax+rbx*8]
0x18006021d  jz      short loc_180060229
0x18006021f  lea     rcx, [rsp+320h+var_2E8]; void **
0x180060224  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180060229  inc     r12d
0x18006022c  jmp     loc_1800600F9
0x180060231  mov     rax, [r14]
0x180060234  lea     rdx, [rsp+320h+rect]; struct _AddressBookPosColSize *
0x180060239  lea     rcx, [rax-278h]
0x180060240  neg     rax
0x180060243  sbb     r8, r8; unsigned __int16 *
0x180060246  and     rcx, r8; struct AddressBook *
0x180060249  call    ?ReadRegistryPositionInfo@@YAHPEAVAddressBook@@PEAU_AddressBookPosColSize@@PEBG@Z; ReadRegistryPositionInfo(AddressBook *,_AddressBookPosColSize *,ushort const *)
0x18006024e  test    eax, eax
0x180060250  jz      short loc_18006029B
0x180060252  xor     ecx, ecx; hWnd
0x180060254  call    cs:__imp_GetDC
0x18006025a  mov     rcx, rax; hdc
0x18006025d  lea     rdx, [rsp+320h+rect]; lprect
0x180060262  mov     rdi, rax
0x180060265  call    cs:__imp_RectVisible
0x18006026b  mov     rdx, rdi; hDC
0x18006026e  xor     ecx, ecx; hWnd
0x180060270  mov     ebx, eax
0x180060272  call    cs:__imp_ReleaseDC
0x180060278  test    ebx, ebx
0x18006027a  jz      short loc_1800602C3
0x18006027c  mov     r9d, [r14+9A8h]
0x180060283  mov     eax, [rsp+320h+rect.right]
0x180060287  mov     edx, [rsp+320h+rect.left]
0x18006028b  sub     eax, edx
0x18006028d  mov     r8d, [rsp+320h+rect.top]
0x180060292  cmp     eax, r9d
0x180060295  cmovge  r9d, eax
0x180060299  jmp     short loc_1800602AA
0x18006029b  mov     r9d, [r14+9A8h]; nWidth
0x1800602a2  mov     edx, 14h; X
0x1800602a7  mov     r8d, edx; Y
0x1800602aa  mov     eax, [r14+9ACh]
0x1800602b1  mov     rcx, rsi; hWnd
0x1800602b4  mov     [rsp+320h+bRepaint], r13d; bRepaint
0x1800602b9  mov     [rsp+320h+nHeight], eax; nHeight
0x1800602bd  call    cs:__imp_MoveWindow
0x1800602c3  mov     ecx, [rbp+220h+var_29C]
0x1800602c6  mov     edx, 64h ; 'd'; nIDDlgItem
0x1800602cb  cmp     ecx, 2
0x1800602ce  cmovg   ecx, r13d
0x1800602d2  mov     [rbp+220h+var_29C], ecx
0x1800602d5  movsxd  rbx, ecx
0x1800602d8  mov     rcx, rsi; hDlg
0x1800602db  call    cs:__imp_GetDlgItem
0x1800602e1  xor     r9d, r9d; lParam
0x1800602e4  mov     r8, rbx; wParam
0x1800602e7  mov     rcx, rax; hWnd
0x1800602ea  mov     edx, 130Ch; Msg
0x1800602ef  call    cs:__imp_SendMessageW
0x1800602f5  cmp     [r14+990h], r13d
0x1800602fc  jz      short loc_180060309
0x1800602fe  mov     rdx, r14; struct _FindParams *
0x180060301  mov     rcx, rsi; hWnd
0x180060304  call    ?ResizeSearchDlg@@YAXPEAUHWND__@@PEAU_FindParams@@@Z; ResizeSearchDlg(HWND__ *,_FindParams *)
0x180060309  mov     rcx, cs:hinstMapiX; hInstance
0x180060310  lea     r8, [rbp+220h+Buffer]; lpBuffer
0x180060314  mov     r9d, 104h; cchBufferMax
0x18006031a  mov     edx, 10B9h; uID
0x18006031f  call    cs:__imp_LoadStringW
0x180060325  lea     rdx, [rbp+220h+Buffer]; lpString
0x180060329  mov     rcx, rsi; hWnd
0x18006032c  call    cs:__imp_SetWindowTextW
0x180060332  mov     edx, 487h; nIDDlgItem
0x180060337  mov     rcx, rsi; hDlg
0x18006033a  call    cs:__imp_GetDlgItem
0x180060340  mov     rcx, rax; HWND
0x180060343  xor     edx, edx; HIMC
0x180060345  call    cs:__imp_ImmAssociateContext
0x18006034b  mov     eax, 1
0x180060350  mov     rcx, [rbp+220h+var_40]
0x180060357  xor     rcx, rsp; StackCookie
0x18006035a  call    __security_check_cookie
0x18006035f  mov     rbx, [rsp+320h+arg_10]
0x180060367  add     rsp, 2F0h
0x18006036e  pop     r15
0x180060370  pop     r14
0x180060372  pop     r13
0x180060374  pop     r12
0x180060376  pop     rdi
0x180060377  pop     rsi
0x180060378  pop     rbp
0x180060379  retn
```
