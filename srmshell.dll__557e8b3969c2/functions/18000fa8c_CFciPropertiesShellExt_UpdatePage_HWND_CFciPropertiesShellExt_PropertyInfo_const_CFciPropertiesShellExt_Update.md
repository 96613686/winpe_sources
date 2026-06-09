# CFciPropertiesShellExt::UpdatePage(HWND__ *,CFciPropertiesShellExt::PropertyInfo const *,CFciPropertiesShellExt::UpdatePageReason)

- ea: `0x18000fa8c`
- end: `0x18000fcf6`
- name: `?UpdatePage@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@PEBUPropertyInfo@1@W4UpdatePageReason@1@@Z`
- size: `618`
- prototype: `char __fastcall(__int64, HWND, const struct CFciPropertiesShellExt::PropertyInfo *, unsigned int)`
- caller_count: `11`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180007290`
- `0x18000ace8`
- `0x18000b328`
- `0x18000b4f8`
- `0x18000b668`
- `0x18000b95c`
- `0x18000ba34`
- `0x18000bc10`
- `0x18000be1c`
- `0x18000c588`
- `0x18000e224`

## callees

- `0x18000ce98`
- `0x18000f910`
- `0x18000fa8c`
- `0x18000fcfc`
- `0x180020010`

## import_xrefs

- `USER32!GetParent` at `0x18000fca5`
- `USER32!GetParent` at `0x18000fcb5`
- `USER32!GetParent` at `0x18000fca5`
- `USER32!GetParent` at `0x18000fcb5`
- `USER32!GetDlgItem` at `0x18000fad9`
- `USER32!GetDlgItem` at `0x18000fb7e`
- `USER32!GetDlgItem` at `0x18000fbb3`
- `USER32!GetDlgItem` at `0x18000fbf2`
- `USER32!GetDlgItem` at `0x18000fc69`
- `USER32!GetDlgItem` at `0x18000fad9`
- `USER32!GetDlgItem` at `0x18000fb7e`
- `USER32!GetDlgItem` at `0x18000fbb3`
- `USER32!GetDlgItem` at `0x18000fbf2`
- `USER32!GetDlgItem` at `0x18000fc69`
- `USER32!ShowWindow` at `0x18000fbbe`
- `USER32!ShowWindow` at `0x18000fc77`
- `USER32!ShowWindow` at `0x18000fbbe`
- `USER32!ShowWindow` at `0x18000fc77`
- `USER32!SendMessageW` at `0x18000fb31`
- `USER32!SendMessageW` at `0x18000fb45`
- `USER32!SendMessageW` at `0x18000fcc9`
- `USER32!SendMessageW` at `0x18000fb31`
- `USER32!SendMessageW` at `0x18000fb45`
- `USER32!SendMessageW` at `0x18000fcc9`
- `USER32!EnableWindow` at `0x18000fbfd`
- `USER32!EnableWindow` at `0x18000fbfd`

## pseudocode

```c
char __fastcall CFciPropertiesShellExt::UpdatePage(
        __int64 a1,
        HWND a2,
        const struct CFciPropertiesShellExt::PropertyInfo *a3,
        unsigned int a4)
{
  __int64 v6; // r15
  const struct CFciPropertiesShellExt::PropertyInfo *v7; // rbp
  HWND DlgItem; // rbx
  int v9; // r13d
  unsigned __int64 i; // r12
  struct CFciPropertiesShellExt::ValueControlInfo near **v11; // r14
  HWND v12; // rbx
  unsigned __int64 m; // rbx
  int v14; // edx
  HWND v15; // rax
  unsigned __int64 j; // r15
  int v17; // edx
  BOOL v18; // ebx
  HWND v19; // rax
  unsigned __int64 k; // rbx
  int v21; // edx
  HWND v22; // rax
  unsigned int v23; // edi
  unsigned int v24; // edi
  HWND Parent; // rax
  UINT v26; // edx
  char result; // al
  HWND v28; // [rsp+30h] [rbp-58h]
  HWND v30; // [rsp+A0h] [rbp+18h]
  char v31; // [rsp+A8h] [rbp+20h]

  v6 = a1;
  v7 = 0;
  if ( a4 != 3 )
    v7 = a3;
  v31 = *(_BYTE *)(a1 + 217);
  *(_BYTE *)(a1 + 217) = 1;
  DlgItem = GetDlgItem(a2, 1001);
  v28 = DlgItem;
  if ( !a4 || a4 == 3 )
  {
    CFciPropertiesShellExt::UpdateInformationControls(a2, 0, 0, 0, 0);
    CFciPropertiesShellExt::UpdatePropertyInfoControls(a2, v7);
    if ( a4 == 3 )
    {
      *(_DWORD *)(v6 + 220) = 9322;
      SendMessageW(DlgItem, 0x1054u, 0, 0);
      SendMessageW(DlgItem, 0x1009u, 0, 0);
    }
  }
  v9 = 0;
  if ( v7 )
  {
    v9 = *((_DWORD *)v7 + 20);
    if ( !v9 )
      v9 = 5;
  }
  for ( i = 0; i < 8; ++i )
  {
    v11 = &CFciPropertiesShellExt::s_valueControls + 6 * i;
    v12 = GetDlgItem(a2, *((_DWORD *)v11 + 1));
    v30 = v12;
    if ( *(_DWORD *)v11 == v9 )
    {
      if ( a4 <= 1 )
      {
        for ( j = 0; j < 3; ++j )
        {
          v17 = *((_DWORD *)v11 + j + 1);
          if ( !v17 )
            break;
          v18 = *((_DWORD *)v7 + 20) != 0;
          v19 = GetDlgItem(a2, v17);
          EnableWindow(v19, v18);
        }
        v12 = v30;
        v6 = a1;
      }
      if ( a4 == 1 || a4 == 2 )
        CFciPropertiesShellExt::SetDisplayValue((CFciPropertiesShellExt *)v6, v28, v7);
      if ( a4 <= 1 )
        ((void (__fastcall *)(__int64, HWND, const struct CFciPropertiesShellExt::PropertyInfo *))v11[4])(
          v6 + *((int *)v11 + 10),
          v12,
          v7);
      if ( !a4 )
      {
        for ( k = 0; k < 3; ++k )
        {
          v21 = *((_DWORD *)v11 + k + 1);
          if ( !v21 )
            break;
          v22 = GetDlgItem(a2, v21);
          ShowWindow(v22, 5);
        }
      }
    }
    else if ( !a4 || a4 == 3 )
    {
      for ( m = 0; m < 3; ++m )
      {
        v14 = *((_DWORD *)v11 + m + 1);
        if ( !v14 )
          break;
        v15 = GetDlgItem(a2, v14);
        ShowWindow(v15, 0);
      }
    }
  }
  v23 = a4 - 1;
  if ( !v23 || (v24 = v23 - 1) == 0 )
  {
    Parent = GetParent(a2);
    v26 = 1128;
    goto LABEL_38;
  }
  if ( v24 == 1 )
  {
    Parent = GetParent(a2);
    v26 = 1133;
LABEL_38:
    SendMessageW(Parent, v26, (WPARAM)a2, 0);
  }
  result = v31;
  *(_BYTE *)(v6 + 217) = v31;
  return result;
}

```

## disassembly

```asm
0x18000fa8c  mov     r11, rsp
0x18000fa8f  mov     [r11+10h], rbx
0x18000fa93  mov     [r11+8], rcx
0x18000fa97  push    rbp
0x18000fa98  push    rsi
0x18000fa99  push    rdi
0x18000fa9a  push    r12
0x18000fa9c  push    r13
0x18000fa9e  push    r14
0x18000faa0  push    r15
0x18000faa2  sub     rsp, 50h
0x18000faa6  mov     edi, r9d
0x18000faa9  mov     rsi, rdx
0x18000faac  mov     r15, rcx
0x18000faaf  xor     ebp, ebp
0x18000fab1  cmp     r9d, 3
0x18000fab5  cmovnz  rbp, r8
0x18000fab9  lea     rax, [rcx+0D9h]
0x18000fac0  mov     [r11-50h], rax
0x18000fac4  mov     cl, [rax]
0x18000fac6  mov     [r11+20h], cl
0x18000faca  mov     [rsp+88h+var_48], cl
0x18000face  mov     byte ptr [rax], 1
0x18000fad1  mov     edx, 3E9h; nIDDlgItem
0x18000fad6  mov     rcx, rsi; hDlg
0x18000fad9  call    cs:__imp_GetDlgItem
0x18000fadf  mov     rbx, rax
0x18000fae2  mov     [rsp+88h+var_58], rax
0x18000fae7  test    edi, edi
0x18000fae9  jz      short loc_18000FAF0
0x18000faeb  cmp     edi, 3
0x18000faee  jnz     short loc_18000FB4B
0x18000faf0  mov     [rsp+88h+var_68], 0; int
0x18000faf8  xor     r9d, r9d
0x18000fafb  xor     r8d, r8d
0x18000fafe  xor     edx, edx; unsigned int
0x18000fb00  mov     rcx, rsi; hDlg
0x18000fb03  call    ?UpdateInformationControls@CFciPropertiesShellExt@@CAXPEAUHWND__@@HPEBGW4ControlState@?$CFciDialogBase@VCFciPropertiesShellExt@@@@2@Z; CFciPropertiesShellExt::UpdateInformationControls(HWND__ *,int,ushort const *,CFciDialogBase<CFciPropertiesShellExt>::ControlState,CFciDialogBase<CFciPropertiesShellExt>::ControlState)
0x18000fb08  mov     rdx, rbp; struct CFciPropertiesShellExt::PropertyInfo *
0x18000fb0b  mov     rcx, rsi; hDlg
0x18000fb0e  call    ?UpdatePropertyInfoControls@CFciPropertiesShellExt@@CAXPEAUHWND__@@PEBUPropertyInfo@1@@Z; CFciPropertiesShellExt::UpdatePropertyInfoControls(HWND__ *,CFciPropertiesShellExt::PropertyInfo const *)
0x18000fb13  cmp     edi, 3
0x18000fb16  jnz     short loc_18000FB4B
0x18000fb18  mov     dword ptr [r15+0DCh], 246Ah
0x18000fb23  xor     r9d, r9d; lParam
0x18000fb26  xor     r8d, r8d; wParam
0x18000fb29  mov     edx, 1054h; Msg
0x18000fb2e  mov     rcx, rbx; hWnd
0x18000fb31  call    cs:__imp_SendMessageW
0x18000fb37  xor     r9d, r9d; lParam
0x18000fb3a  xor     r8d, r8d; wParam
0x18000fb3d  mov     edx, 1009h; Msg
0x18000fb42  mov     rcx, rbx; hWnd
0x18000fb45  call    cs:__imp_SendMessageW
0x18000fb4b  xor     r13d, r13d
0x18000fb4e  lea     eax, [r13+5]
0x18000fb52  test    rbp, rbp
0x18000fb55  jz      short loc_18000FB62
0x18000fb57  mov     r13d, [rbp+50h]
0x18000fb5b  test    r13d, r13d
0x18000fb5e  cmovz   r13d, eax
0x18000fb62  xor     r12d, r12d
0x18000fb65  lea     r14, [r12+r12*2]
0x18000fb69  shl     r14, 4
0x18000fb6d  lea     rcx, ?s_valueControls@CFciPropertiesShellExt@@0PAUValueControlInfo@1@A; CFciPropertiesShellExt::ValueControlInfo near * CFciPropertiesShellExt::s_valueControls
0x18000fb74  add     r14, rcx
0x18000fb77  mov     edx, [r14+4]; nIDDlgItem
0x18000fb7b  mov     rcx, rsi; hDlg
0x18000fb7e  call    cs:__imp_GetDlgItem
0x18000fb84  mov     rbx, rax
0x18000fb87  mov     [rsp+88h+arg_10], rax
0x18000fb8f  cmp     [r14], r13d
0x18000fb92  jz      short loc_18000FBD2
0x18000fb94  test    edi, edi
0x18000fb96  jz      short loc_18000FBA1
0x18000fb98  cmp     edi, 3
0x18000fb9b  jnz     loc_18000FC86
0x18000fba1  xor     ebx, ebx
0x18000fba3  mov     edx, [r14+rbx*4+4]; nIDDlgItem
0x18000fba8  test    edx, edx
0x18000fbaa  jz      loc_18000FC86
0x18000fbb0  mov     rcx, rsi; hDlg
0x18000fbb3  call    cs:__imp_GetDlgItem
0x18000fbb9  xor     edx, edx; nCmdShow
0x18000fbbb  mov     rcx, rax; hWnd
0x18000fbbe  call    cs:__imp_ShowWindow
0x18000fbc4  inc     rbx
0x18000fbc7  cmp     rbx, 3
0x18000fbcb  jb      short loc_18000FBA3
0x18000fbcd  jmp     loc_18000FC86
0x18000fbd2  test    edi, edi
0x18000fbd4  jz      short loc_18000FBDB
0x18000fbd6  cmp     edi, 1
0x18000fbd9  jnz     short loc_18000FC1C
0x18000fbdb  xor     r15d, r15d
0x18000fbde  mov     edx, [r14+r15*4+4]; nIDDlgItem
0x18000fbe3  test    edx, edx
0x18000fbe5  jz      short loc_18000FC0C
0x18000fbe7  xor     ebx, ebx
0x18000fbe9  cmp     [rbp+50h], ebx
0x18000fbec  setnz   bl
0x18000fbef  mov     rcx, rsi; hDlg
0x18000fbf2  call    cs:__imp_GetDlgItem
0x18000fbf8  mov     edx, ebx; bEnable
0x18000fbfa  mov     rcx, rax; hWnd
0x18000fbfd  call    cs:__imp_EnableWindow
0x18000fc03  inc     r15
0x18000fc06  cmp     r15, 3
0x18000fc0a  jb      short loc_18000FBDE
0x18000fc0c  mov     rbx, [rsp+88h+arg_10]
0x18000fc14  mov     r15, [rsp+88h+arg_0]
0x18000fc1c  mov     ecx, edi
0x18000fc1e  sub     ecx, 1
0x18000fc21  jz      short loc_18000FC28
0x18000fc23  cmp     ecx, 1
0x18000fc26  jnz     short loc_18000FC38
0x18000fc28  mov     r8, rbp; struct CFciPropertiesShellExt::PropertyInfo *
0x18000fc2b  mov     rdx, [rsp+88h+var_58]; HWND
0x18000fc30  mov     rcx, r15; this
0x18000fc33  call    ?SetDisplayValue@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@AEBUPropertyInfo@1@@Z; CFciPropertiesShellExt::SetDisplayValue(HWND__ *,CFciPropertiesShellExt::PropertyInfo const &)
0x18000fc38  test    edi, edi
0x18000fc3a  jz      short loc_18000FC41
0x18000fc3c  cmp     edi, 1
0x18000fc3f  jnz     short loc_18000FC57
0x18000fc41  movsxd  rcx, dword ptr [r14+28h]
0x18000fc45  add     rcx, r15
0x18000fc48  mov     r8, rbp
0x18000fc4b  mov     rdx, rbx
0x18000fc4e  mov     rax, [r14+20h]
0x18000fc52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc57  test    edi, edi
0x18000fc59  jnz     short loc_18000FC86
0x18000fc5b  xor     ebx, ebx
0x18000fc5d  mov     edx, [r14+rbx*4+4]; nIDDlgItem
0x18000fc62  test    edx, edx
0x18000fc64  jz      short loc_18000FC86
0x18000fc66  mov     rcx, rsi; hDlg
0x18000fc69  call    cs:__imp_GetDlgItem
0x18000fc6f  mov     edx, 5; nCmdShow
0x18000fc74  mov     rcx, rax; hWnd
0x18000fc77  call    cs:__imp_ShowWindow
0x18000fc7d  inc     rbx
0x18000fc80  cmp     rbx, 3
0x18000fc84  jb      short loc_18000FC5D
0x18000fc86  inc     r12
0x18000fc89  cmp     r12, 8
0x18000fc8d  jb      loc_18000FB65
0x18000fc93  sub     edi, 1
0x18000fc96  jz      short loc_18000FCB2
0x18000fc98  sub     edi, 1
0x18000fc9b  jz      short loc_18000FCB2
0x18000fc9d  cmp     edi, 1
0x18000fca0  jnz     short loc_18000FCD0
0x18000fca2  mov     rcx, rsi; hWnd
0x18000fca5  call    cs:__imp_GetParent
0x18000fcab  mov     edx, 46Dh
0x18000fcb0  jmp     short loc_18000FCC0
0x18000fcb2  mov     rcx, rsi; hWnd
0x18000fcb5  call    cs:__imp_GetParent
0x18000fcbb  mov     edx, 468h; Msg
0x18000fcc0  xor     r9d, r9d; lParam
0x18000fcc3  mov     r8, rsi; wParam
0x18000fcc6  mov     rcx, rax; hWnd
0x18000fcc9  call    cs:__imp_SendMessageW
0x18000fccf  nop
0x18000fcd0  mov     al, [rsp+88h+arg_18]
0x18000fcd7  mov     [r15+0D9h], al
0x18000fcde  mov     rbx, [rsp+88h+arg_8]
0x18000fce6  add     rsp, 50h
0x18000fcea  pop     r15
0x18000fcec  pop     r14
0x18000fcee  pop     r13
0x18000fcf0  pop     r12
0x18000fcf2  pop     rdi
0x18000fcf3  pop     rsi
0x18000fcf4  pop     rbp
0x18000fcf5  retn
```
