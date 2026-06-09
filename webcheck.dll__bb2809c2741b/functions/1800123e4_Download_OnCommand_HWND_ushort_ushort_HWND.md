# Download_OnCommand(HWND__ *,ushort,ushort,HWND__ *)

- ea: `0x1800123e4`
- end: `0x1800125c8`
- name: `?Download_OnCommand@@YAHPEAUHWND__@@GG0@Z`
- size: `484`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned __int16, unsigned __int16, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012140`

## callees

- `0x18000c370`
- `0x18000e110`
- `0x180012314`
- `0x18001234c`
- `0x1800123ac`
- `0x1800123e4`

## import_xrefs

- `USER32!GetParent` at `0x18001259f`
- `USER32!GetParent` at `0x18001259f`
- `USER32!SendDlgItemMessageW` at `0x1800124b0`
- `USER32!SendDlgItemMessageW` at `0x1800124b0`
- `USER32!GetWindowLongPtrW` at `0x180012403`
- `USER32!GetWindowLongPtrW` at `0x180012403`
- `USER32!SendMessageW` at `0x1800125b3`
- `USER32!SendMessageW` at `0x1800125b3`

## pseudocode

```c
__int64 __fastcall Download_OnCommand(HWND hDlg, __int16 a2, unsigned __int16 a3, HWND a4)
{
  int v5; // edi
  unsigned int v6; // ebp
  LONG_PTR WindowLongPtrW; // rax
  __int64 v9; // rcx
  __int64 (*v10)(HWND, unsigned int, unsigned __int64, __int64); // r9
  __int64 v11; // rdx
  BOOL v12; // edi
  bool v13; // zf
  HWND Parent; // rax

  v5 = a3;
  v6 = 1;
  WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
  if ( WindowLongPtrW )
  {
    switch ( v5 )
    {
      case 2000:
        if ( a2 )
          return v6;
        v10 = AdvancedDownloadDlgProc;
        v11 = 6013;
LABEL_31:
        if ( DialogBoxParam(v9, v11, hDlg, v10, WindowLongPtrW) != 1 )
          return v6;
        goto LABEL_32;
      case 2063:
        goto LABEL_25;
      case 2065:
        if ( a2 )
          return v6;
        Download_EnableEmailControls(hDlg);
        goto LABEL_32;
      case 2066:
LABEL_25:
        v13 = a2 == 768;
        break;
      case 2068:
        v13 = a2 == 0;
        break;
      case 2078:
        if ( a2 != 1024 )
          return v6;
        v12 = *(_DWORD *)(WindowLongPtrW + 28) != KeepSpinNumberInRange(hDlg, 2078, 2079, 0, 3);
        Download_EnableFollowLinks(hDlg);
LABEL_27:
        if ( !v12 )
          return v6;
        goto LABEL_32;
      case 2081:
        if ( a2 )
          return v6;
        Download_EnableLimitSpaceControls(hDlg);
LABEL_32:
        Parent = GetParent(hDlg);
        SendMessageW(Parent, 0x468u, (WPARAM)hDlg, 0);
        return v6;
      case 2082:
        if ( a2 == 768 )
        {
          v12 = *(_DWORD *)(WindowLongPtrW + 20) != (unsigned __int16)SendDlgItemMessageW(hDlg, 2083, 0x468u, 0, 0);
        }
        else
        {
          if ( a2 != 512 )
            return v6;
          v12 = 0;
          KeepSpinNumberInRange(hDlg, 2082, 2083, 0x32u, 0x7FFF);
        }
        goto LABEL_27;
      case 2087:
        if ( a2 )
          return v6;
        v10 = LoginOptionDlgProc;
        v11 = 6014;
        goto LABEL_31;
      default:
        return 0;
    }
    v12 = v13;
    goto LABEL_27;
  }
  return v6;
}

```

## disassembly

```asm
0x1800123e4  push    rbx
0x1800123e6  push    rbp
0x1800123e7  push    rsi
0x1800123e8  push    rdi
0x1800123e9  push    r14
0x1800123eb  push    r15
0x1800123ed  sub     rsp, 38h
0x1800123f1  movzx   ebx, dx
0x1800123f4  movzx   edi, r8w
0x1800123f8  mov     ebp, 1
0x1800123fd  mov     rsi, rcx
0x180012400  lea     edx, [rbp+0Fh]; nIndex
0x180012403  call    cs:__imp_GetWindowLongPtrW
0x180012409  xor     r15d, r15d
0x18001240c  mov     r14, rax
0x18001240f  test    rax, rax
0x180012412  jz      loc_1800125B9
0x180012418  mov     r8d, edi
0x18001241b  sub     r8d, 7D0h
0x180012422  jz      loc_180012579
0x180012428  sub     r8d, 3Fh ; '?'
0x18001242c  jz      loc_180012564
0x180012432  sub     r8d, 2
0x180012436  jz      loc_180012555
0x18001243c  sub     r8d, ebp
0x18001243f  jz      loc_180012564
0x180012445  sub     r8d, 2
0x180012449  jz      loc_180012550
0x18001244f  sub     r8d, 0Ah
0x180012453  jz      loc_180012511
0x180012459  sub     r8d, 3
0x18001245d  jz      loc_1800124FB
0x180012463  sub     r8d, ebp
0x180012466  jz      short loc_180012490
0x180012468  cmp     r8d, 5
0x18001246c  jz      short loc_180012476
0x18001246e  mov     ebp, r15d
0x180012471  jmp     loc_1800125B9
0x180012476  test    bx, bx
0x180012479  jnz     loc_1800125B9
0x18001247f  lea     r9, ?LoginOptionDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; LoginOptionDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180012486  mov     edx, 177Eh
0x18001248b  jmp     loc_18001258A
0x180012490  mov     eax, 300h
0x180012495  cmp     bx, ax
0x180012498  jnz     short loc_1800124C9
0x18001249a  xor     r9d, r9d; wParam
0x18001249d  mov     [rsp+68h+lParam], r15; lParam
0x1800124a2  mov     edx, 823h; nIDDlgItem
0x1800124a7  mov     r8d, 468h; Msg
0x1800124ad  mov     rcx, rsi; hDlg
0x1800124b0  call    cs:__imp_SendDlgItemMessageW
0x1800124b6  movzx   ecx, ax
0x1800124b9  mov     edi, r15d
0x1800124bc  cmp     [r14+14h], ecx
0x1800124c0  setnz   dil
0x1800124c4  jmp     loc_180012573
0x1800124c9  mov     eax, 200h
0x1800124ce  cmp     bx, ax
0x1800124d1  jnz     loc_1800125B9
0x1800124d7  mov     edx, 822h; nIDDlgItem
0x1800124dc  mov     dword ptr [rsp+68h+lParam], 7FFFh; int
0x1800124e4  mov     r9d, 32h ; '2'; uValue
0x1800124ea  mov     rcx, rsi; hDlg
0x1800124ed  mov     edi, r15d
0x1800124f0  lea     r8d, [rdx+1]; int
0x1800124f4  call    ?KeepSpinNumberInRange@@YAHPEAUHWND__@@HHHH@Z; KeepSpinNumberInRange(HWND__ *,int,int,int,int)
0x1800124f9  jmp     short loc_180012573
0x1800124fb  test    bx, bx
0x1800124fe  jnz     loc_1800125B9
0x180012504  mov     rcx, rsi; hDlg
0x180012507  call    ?Download_EnableLimitSpaceControls@@YAXPEAUHWND__@@@Z; Download_EnableLimitSpaceControls(HWND__ *)
0x18001250c  jmp     loc_18001259C
0x180012511  mov     eax, 400h
0x180012516  cmp     bx, ax
0x180012519  jnz     loc_1800125B9
0x18001251f  mov     edx, 81Eh; nIDDlgItem
0x180012524  mov     dword ptr [rsp+68h+lParam], 3; int
0x18001252c  xor     r9d, r9d; uValue
0x18001252f  mov     rcx, rsi; hDlg
0x180012532  lea     r8d, [rdx+1]; int
0x180012536  call    ?KeepSpinNumberInRange@@YAHPEAUHWND__@@HHHH@Z; KeepSpinNumberInRange(HWND__ *,int,int,int,int)
0x18001253b  cmp     [r14+1Ch], eax
0x18001253f  mov     edi, r15d
0x180012542  mov     rcx, rsi; hDlg
0x180012545  setnz   dil
0x180012549  call    ?Download_EnableFollowLinks@@YAXPEAUHWND__@@@Z; Download_EnableFollowLinks(HWND__ *)
0x18001254e  jmp     short loc_180012573
0x180012550  test    bx, bx
0x180012553  jmp     short loc_18001256C
0x180012555  test    bx, bx
0x180012558  jnz     short loc_1800125B9
0x18001255a  mov     rcx, rsi; hDlg
0x18001255d  call    ?Download_EnableEmailControls@@YAXPEAUHWND__@@@Z; Download_EnableEmailControls(HWND__ *)
0x180012562  jmp     short loc_18001259C
0x180012564  mov     eax, 300h
0x180012569  cmp     bx, ax
0x18001256c  mov     edi, r15d
0x18001256f  setz    dil
0x180012573  test    edi, edi
0x180012575  jz      short loc_1800125B9
0x180012577  jmp     short loc_18001259C
0x180012579  test    bx, bx
0x18001257c  jnz     short loc_1800125B9
0x18001257e  lea     r9, ?AdvancedDownloadDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; AdvancedDownloadDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180012585  mov     edx, 177Dh
0x18001258a  mov     r8, rsi
0x18001258d  mov     [rsp+68h+lParam], r14
0x180012592  call    DialogBoxParam
0x180012597  cmp     rax, rbp
0x18001259a  jnz     short loc_1800125B9
0x18001259c  mov     rcx, rsi; hWnd
0x18001259f  call    cs:__imp_GetParent
0x1800125a5  xor     r9d, r9d; lParam
0x1800125a8  mov     r8, rsi; wParam
0x1800125ab  mov     rcx, rax; hWnd
0x1800125ae  mov     edx, 468h; Msg
0x1800125b3  call    cs:__imp_SendMessageW
0x1800125b9  mov     eax, ebp
0x1800125bb  add     rsp, 38h
0x1800125bf  pop     r15
0x1800125c1  pop     r14
0x1800125c3  pop     rdi
0x1800125c4  pop     rsi
0x1800125c5  pop     rbp
0x1800125c6  pop     rbx
0x1800125c7  retn
```
