# CLibrarySharingDefaultsDlg::OnCommand(uint,HWND__ *,uint)

- ea: `0x18000586c`
- end: `0x1800059a1`
- name: `?OnCommand@CLibrarySharingDefaultsDlg@@QEAA_JIPEAUHWND__@@I@Z`
- size: `309`
- prototype: `__int64 __fastcall(CLibrarySharingDefaultsDlg *__hidden this, unsigned int, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000735c`

## callees

- `0x180003860`
- `0x1800055f4`
- `0x18000571c`
- `0x18000586c`
- `0x180005e74`

## import_xrefs

- `USER32!EndDialog` at `0x180005988`
- `USER32!EndDialog` at `0x180005988`

## pseudocode

```c
__int64 __fastcall CLibrarySharingDefaultsDlg::OnCommand(HWND *this, int a2, HWND a3)
{
  __int64 v3; // rsi
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  CLibrarySharingFilterDlg *v11; // rcx
  INT_PTR v12; // rdx

  v3 = 0;
  v5 = a2 - 1;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    CLibrarySharingFilterDlg::OnOK((CLibrarySharingFilterDlg *)this);
    g_bfSqm_USAGE |= 0x10u;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v12 = 1;
    goto LABEL_23;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v11 = (CLibrarySharingFilterDlg *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    CLibrarySharingFilterDlg::OnCancel(v11);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v3 = 1;
    v12 = 0;
LABEL_23:
    EndDialog(this[1], v12);
    return v3;
  }
  v7 = v6 - 305;
  if ( !v7 || (v8 = v7 - 1) == 0 || (v9 = v8 - 3) == 0 || (v10 = v9 - 1) == 0 || v10 == 3 )
    CLibrarySharingFilterDlg::OnCheckboxClicked((CLibrarySharingFilterDlg *)this);
  return v3;
}

```

## disassembly

```asm
0x18000586c  mov     [rsp+arg_0], rbx
0x180005871  mov     [rsp+arg_8], rsi
0x180005876  push    rdi
0x180005877  sub     rsp, 20h
0x18000587b  xor     esi, esi
0x18000587d  mov     rdi, rcx
0x180005880  sub     edx, 1
0x180005883  jz      loc_18000591B
0x180005889  sub     edx, 1
0x18000588c  jz      short loc_1800058B8
0x18000588e  sub     edx, 131h
0x180005894  jz      short loc_1800058AE
0x180005896  sub     edx, 1
0x180005899  jz      short loc_1800058AE
0x18000589b  sub     edx, 3
0x18000589e  jz      short loc_1800058AE
0x1800058a0  sub     edx, 1
0x1800058a3  jz      short loc_1800058AE
0x1800058a5  cmp     edx, 3
0x1800058a8  jnz     loc_18000598E
0x1800058ae  call    ?OnCheckboxClicked@CLibrarySharingFilterDlg@@IEAA_JXZ; CLibrarySharingFilterDlg::OnCheckboxClicked(void)
0x1800058b3  jmp     loc_18000598E
0x1800058b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058bf  lea     rbx, WPP_GLOBAL_Control
0x1800058c6  cmp     rcx, rbx
0x1800058c9  jz      short loc_1800058E6
0x1800058cb  test    byte ptr [rcx+1Ch], 20h
0x1800058cf  jz      short loc_1800058E6
0x1800058d1  mov     rcx, [rcx+10h]
0x1800058d5  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800058dc  mov     edx, 66h ; 'f'
0x1800058e1  call    WPP_SF_
0x1800058e6  call    ?OnCancel@CLibrarySharingFilterDlg@@IEAA_JXZ; CLibrarySharingFilterDlg::OnCancel(void)
0x1800058eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058f2  cmp     rcx, rbx
0x1800058f5  jz      short loc_180005912
0x1800058f7  test    byte ptr [rcx+1Ch], 20h
0x1800058fb  jz      short loc_180005912
0x1800058fd  mov     rcx, [rcx+10h]
0x180005901  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005908  mov     edx, 67h ; 'g'
0x18000590d  call    WPP_SF_
0x180005912  mov     esi, 1
0x180005917  xor     edx, edx
0x180005919  jmp     short loc_180005984
0x18000591b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005922  lea     rbx, WPP_GLOBAL_Control
0x180005929  cmp     rcx, rbx
0x18000592c  jz      short loc_180005949
0x18000592e  test    byte ptr [rcx+1Ch], 20h
0x180005932  jz      short loc_180005949
0x180005934  mov     rcx, [rcx+10h]
0x180005938  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000593f  mov     edx, 64h ; 'd'
0x180005944  call    WPP_SF_
0x180005949  mov     rcx, rdi; this
0x18000594c  call    ?OnOK@CLibrarySharingFilterDlg@@IEAA_JXZ; CLibrarySharingFilterDlg::OnOK(void)
0x180005951  or      cs:?g_bfSqm_USAGE@@3KA, 10h; ulong g_bfSqm_USAGE
0x180005958  mov     rcx, cs:WPP_GLOBAL_Control
0x18000595f  cmp     rcx, rbx
0x180005962  jz      short loc_18000597F
0x180005964  test    byte ptr [rcx+1Ch], 20h
0x180005968  jz      short loc_18000597F
0x18000596a  mov     rcx, [rcx+10h]
0x18000596e  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005975  mov     edx, 65h ; 'e'
0x18000597a  call    WPP_SF_
0x18000597f  mov     edx, 1; nResult
0x180005984  mov     rcx, [rdi+8]; hDlg
0x180005988  call    cs:__imp_EndDialog
0x18000598e  mov     rbx, [rsp+28h+arg_0]
0x180005993  mov     rax, rsi
0x180005996  mov     rsi, [rsp+28h+arg_8]
0x18000599b  add     rsp, 20h
0x18000599f  pop     rdi
0x1800059a0  retn
```
