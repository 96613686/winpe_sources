# CLibrarySharingCustomizeDlg::OnCommand(uint,HWND__ *,uint)

- ea: `0x1800057a0`
- end: `0x180005865`
- name: `?OnCommand@CLibrarySharingCustomizeDlg@@QEAA_JIPEAUHWND__@@I@Z`
- size: `197`
- prototype: `__int64 __fastcall(CLibrarySharingCustomizeDlg *__hidden this, unsigned int, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007270`

## callees

- `0x180003860`
- `0x1800055f4`
- `0x180005660`
- `0x1800057a0`
- `0x180005d90`

## import_xrefs

- `USER32!EndDialog` at `0x180005851`
- `USER32!EndDialog` at `0x180005851`

## pseudocode

```c
__int64 __fastcall CLibrarySharingCustomizeDlg::OnCommand(HWND *this, int a2, HWND a3)
{
  __int64 v3; // rdi
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
    CLibrarySharingCustomizeDlg::OnOK((CLibrarySharingCustomizeDlg *)this);
    v12 = 1;
LABEL_17:
    EndDialog(this[1], v12);
    return v3;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v11 = (CLibrarySharingFilterDlg *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    CLibrarySharingFilterDlg::OnCancel(v11);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
    v3 = 1;
    v12 = 0;
    goto LABEL_17;
  }
  v7 = v6 - 305;
  if ( !v7 || (v8 = v7 - 1) == 0 || (v9 = v8 - 3) == 0 || (v10 = v9 - 1) == 0 || v10 == 3 )
    CLibrarySharingCustomizeDlg::OnCheckboxClicked((CLibrarySharingCustomizeDlg *)this);
  return v3;
}

```

## disassembly

```asm
0x1800057a0  mov     [rsp+arg_0], rbx
0x1800057a5  push    rdi
0x1800057a6  sub     rsp, 20h
0x1800057aa  xor     edi, edi
0x1800057ac  mov     rbx, rcx
0x1800057af  sub     edx, 1
0x1800057b2  jz      loc_180005843
0x1800057b8  sub     edx, 1
0x1800057bb  jz      short loc_1800057E0
0x1800057bd  sub     edx, 131h
0x1800057c3  jz      short loc_1800057D9
0x1800057c5  sub     edx, 1
0x1800057c8  jz      short loc_1800057D9
0x1800057ca  sub     edx, 3
0x1800057cd  jz      short loc_1800057D9
0x1800057cf  sub     edx, 1
0x1800057d2  jz      short loc_1800057D9
0x1800057d4  cmp     edx, 3
0x1800057d7  jnz     short loc_180005857
0x1800057d9  call    ?OnCheckboxClicked@CLibrarySharingCustomizeDlg@@QEAA_JXZ; CLibrarySharingCustomizeDlg::OnCheckboxClicked(void)
0x1800057de  jmp     short loc_180005857
0x1800057e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057e7  lea     rdi, WPP_GLOBAL_Control
0x1800057ee  cmp     rcx, rdi
0x1800057f1  jz      short loc_18000580E
0x1800057f3  test    byte ptr [rcx+1Ch], 20h
0x1800057f7  jz      short loc_18000580E
0x1800057f9  mov     rcx, [rcx+10h]
0x1800057fd  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005804  mov     edx, 74h ; 't'
0x180005809  call    WPP_SF_
0x18000580e  call    ?OnCancel@CLibrarySharingFilterDlg@@IEAA_JXZ; CLibrarySharingFilterDlg::OnCancel(void)
0x180005813  mov     rcx, cs:WPP_GLOBAL_Control
0x18000581a  cmp     rcx, rdi
0x18000581d  jz      short loc_18000583A
0x18000581f  test    byte ptr [rcx+1Ch], 20h
0x180005823  jz      short loc_18000583A
0x180005825  mov     rcx, [rcx+10h]
0x180005829  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180005830  mov     edx, 75h ; 'u'
0x180005835  call    WPP_SF_
0x18000583a  mov     edi, 1
0x18000583f  xor     edx, edx
0x180005841  jmp     short loc_18000584D
0x180005843  call    ?OnOK@CLibrarySharingCustomizeDlg@@QEAA_JXZ; CLibrarySharingCustomizeDlg::OnOK(void)
0x180005848  mov     edx, 1; nResult
0x18000584d  mov     rcx, [rbx+8]; hDlg
0x180005851  call    cs:__imp_EndDialog
0x180005857  mov     rbx, [rsp+28h+arg_0]
0x18000585c  mov     rax, rdi
0x18000585f  add     rsp, 20h
0x180005863  pop     rdi
0x180005864  retn
```
