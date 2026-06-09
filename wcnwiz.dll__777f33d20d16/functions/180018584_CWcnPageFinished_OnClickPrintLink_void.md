# CWcnPageFinished::OnClickPrintLink(void)

- ea: `0x180018584`
- end: `0x1800187b9`
- name: `?OnClickPrintLink@CWcnPageFinished@@QEAAXXZ`
- size: `565`
- prototype: `void __fastcall(CWcnPageFinished *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000baa0`

## callees

- `0x180002294`
- `0x18000d630`
- `0x18000e1dc`
- `0x180018584`
- `0x180018c14`
- `0x180019858`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186ec`
- `KERNEL32!GlobalFree` at `0x180018755`
- `KERNEL32!GlobalFree` at `0x18001876b`
- `KERNEL32!GlobalFree` at `0x180018755`
- `KERNEL32!GlobalFree` at `0x18001876b`
- `USER32!GetDlgItem` at `0x180018601`
- `USER32!GetDlgItem` at `0x180018601`
- `GDI32!DeleteDC` at `0x18001873f`
- `GDI32!DeleteDC` at `0x18001873f`

## pseudocode

```c
void __fastcall CWcnPageFinished::OnClickPrintLink(CWcnPageFinished *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  HWND v4; // rcx
  HWND DlgItem; // rax
  int v6; // ebx
  _BYTE *v7; // r10
  const char *v8; // rax
  __int64 v9; // r10
  unsigned int v10; // eax
  char v11; // r10
  unsigned int v12; // eax
  __int64 v13; // r10
  int v14; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v15[4]; // [rsp+34h] [rbp-55h] BYREF
  HWND v16; // [rsp+38h] [rbp-51h]
  HGLOBAL hMem[2]; // [rsp+40h] [rbp-49h]
  HDC hdc; // [rsp+50h] [rbp-39h]
  __int64 v19; // [rsp+58h] [rbp-31h]
  __int64 v20; // [rsp+60h] [rbp-29h]
  int v21; // [rsp+68h] [rbp-21h]
  __int64 *v22; // [rsp+70h] [rbp-19h]
  int v23; // [rsp+78h] [rbp-11h]
  int v24; // [rsp+7Ch] [rbp-Dh]
  int v25; // [rsp+80h] [rbp-9h]
  __int64 v26; // [rsp+88h] [rbp-1h]
  __int128 v27; // [rsp+90h] [rbp+7h]
  int v28; // [rsp+A0h] [rbp+17h]
  __int64 v29; // [rsp+A8h] [rbp+1Fh]
  int v30; // [rsp+B0h] [rbp+27h]
  int v31; // [rsp+B4h] [rbp+2Bh]
  __int64 v32; // [rsp+F0h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 18, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, Indent);
  }
  v32 = 0;
  memset_0(v15, 0, 0x84u);
  v4 = (HWND)*((_QWORD *)this + 21);
  v14 = 136;
  DlgItem = GetDlgItem(v4, 1618);
  hdc = 0;
  v16 = DlgItem;
  *(_OWORD *)hMem = 0;
  v22 = &v32;
  v19 = 9437452;
  v20 = 0;
  v21 = 10;
  v23 = 1;
  v24 = 1000;
  v25 = 1;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = -1;
  v31 = 0;
  v6 = IsolationAwarePrintDlgExW(&v14);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      GetLastError();
      v10 = (unsigned int)GetIndent(0);
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids,
        v10,
        v11);
      goto LABEL_13;
    }
  }
  else
  {
    if ( v31 == 1 )
    {
      v6 = CWcnPageFinished::SendDataToPrinter(this, hdc);
LABEL_13:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v9 + 16), 19, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v8);
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( hdc )
  {
    DeleteDC(hdc);
    v7 = WPP_GLOBAL_Control;
  }
  if ( hMem[0] )
  {
    GlobalFree(hMem[0]);
    v7 = WPP_GLOBAL_Control;
  }
  if ( hMem[1] )
  {
    GlobalFree(hMem[1]);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v6 < 0 || v7[25] >= 6u) )
  {
    v12 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v13 + 16), 21, (unsigned int)WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids, v12, v6);
  }
}

```

## disassembly

```asm
0x180018584  push    rbp
0x180018586  push    rbx
0x180018587  push    rdi
0x180018588  push    r14
0x18001858a  lea     rbp, [rsp-3Fh]
0x18001858f  sub     rsp, 0C8h
0x180018596  mov     rdi, rcx
0x180018599  mov     r10, cs:WPP_GLOBAL_Control
0x1800185a0  lea     r14, WPP_GLOBAL_Control
0x1800185a7  cmp     r10, r14
0x1800185aa  jz      short loc_1800185D5
0x1800185ac  cmp     byte ptr [r10+19h], 6
0x1800185b1  jb      short loc_1800185D5
0x1800185b3  mov     ecx, 1; int
0x1800185b8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800185bd  mov     rcx, [r10+10h]
0x1800185c1  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x1800185c8  mov     edx, 12h
0x1800185cd  mov     r9, rax
0x1800185d0  call    WPP_SF_s
0x1800185d5  xor     edx, edx; Val
0x1800185d7  mov     [rbp+57h+arg_0], 0
0x1800185df  mov     r8d, 84h; Size
0x1800185e5  lea     rcx, [rbp+57h+var_AC]; void *
0x1800185e9  call    memset_0
0x1800185ee  mov     rcx, [rdi+0A8h]; hDlg
0x1800185f5  mov     edx, 652h; nIDDlgItem
0x1800185fa  mov     [rbp+57h+var_B0], 88h
0x180018601  call    cs:__imp_GetDlgItem
0x180018607  xorps   xmm0, xmm0
0x18001860a  mov     [rbp+57h+hdc], 0
0x180018612  mov     [rbp+57h+var_A8], rax
0x180018616  lea     rcx, [rbp+57h+var_B0]
0x18001861a  lea     rax, [rbp+57h+arg_0]
0x18001861e  movdqa  xmmword ptr [rbp+57h+hMem], xmm0
0x180018623  mov     [rbp+57h+var_70], rax
0x180018627  mov     [rbp+57h+var_88], 90010Ch
0x18001862f  mov     [rbp+57h+var_80], 0
0x180018637  mov     [rbp+57h+var_78], 0Ah
0x18001863e  mov     [rbp+57h+var_68], 1
0x180018645  mov     [rbp+57h+var_64], 3E8h
0x18001864c  mov     [rbp+57h+var_60], 1
0x180018653  mov     [rbp+57h+var_58], 0
0x18001865b  movdqa  [rbp+57h+var_50], xmm0
0x180018660  mov     [rbp+57h+var_40], 0
0x180018667  mov     [rbp+57h+var_38], 0
0x18001866f  mov     [rbp+57h+var_30], 0FFFFFFFFh
0x180018676  mov     [rbp+57h+var_2C], 0
0x18001867d  call    IsolationAwarePrintDlgExW
0x180018682  mov     ebx, eax
0x180018684  test    eax, eax
0x180018686  jnz     short loc_1800186D9
0x180018688  cmp     [rbp+57h+var_2C], 1
0x18001868c  jnz     short loc_1800186A1
0x18001868e  mov     rdx, [rbp+57h+hdc]; HDC
0x180018692  mov     rcx, rdi; this
0x180018695  call    ?SendDataToPrinter@CWcnPageFinished@@QEAAJPEAUHDC__@@@Z; CWcnPageFinished::SendDataToPrinter(HDC__ *)
0x18001869a  mov     ebx, eax
0x18001869c  jmp     loc_18001872F
0x1800186a1  mov     r10, cs:WPP_GLOBAL_Control
0x1800186a8  cmp     r10, r14
0x1800186ab  jz      loc_180018736
0x1800186b1  cmp     byte ptr [r10+19h], 4
0x1800186b6  jb      short loc_180018736
0x1800186b8  xor     ecx, ecx; int
0x1800186ba  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800186bf  mov     rcx, [r10+10h]
0x1800186c3  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x1800186ca  mov     edx, 13h
0x1800186cf  mov     r9, rax
0x1800186d2  call    WPP_SF_s
0x1800186d7  jmp     short loc_18001872F
0x1800186d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800186e0  cmp     r10, r14
0x1800186e3  jz      short loc_180018736
0x1800186e5  cmp     byte ptr [r10+19h], 2
0x1800186ea  jb      short loc_180018736
0x1800186ec  call    cs:__imp_GetLastError
0x1800186f2  mov     r10d, eax
0x1800186f5  test    eax, eax
0x1800186f7  jle     short loc_180018704
0x1800186f9  movzx   r10d, ax
0x1800186fd  or      r10d, 80070000h
0x180018704  xor     ecx, ecx; int
0x180018706  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001870b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018712  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x180018719  mov     edx, 14h
0x18001871e  mov     [rsp+0E0h+var_C0], r10d
0x180018723  mov     r9, rax
0x180018726  mov     rcx, [rcx+10h]
0x18001872a  call    WPP_SF_sd
0x18001872f  mov     r10, cs:WPP_GLOBAL_Control
0x180018736  mov     rcx, [rbp+57h+hdc]; hdc
0x18001873a  test    rcx, rcx
0x18001873d  jz      short loc_18001874C
0x18001873f  call    cs:__imp_DeleteDC
0x180018745  mov     r10, cs:WPP_GLOBAL_Control
0x18001874c  mov     rcx, [rbp+57h+hMem]; hMem
0x180018750  test    rcx, rcx
0x180018753  jz      short loc_180018762
0x180018755  call    cs:__imp_GlobalFree
0x18001875b  mov     r10, cs:WPP_GLOBAL_Control
0x180018762  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180018766  test    rcx, rcx
0x180018769  jz      short loc_180018778
0x18001876b  call    cs:__imp_GlobalFree
0x180018771  mov     r10, cs:WPP_GLOBAL_Control
0x180018778  cmp     r10, r14
0x18001877b  jz      short loc_1800187AC
0x18001877d  test    ebx, ebx
0x18001877f  js      short loc_180018788
0x180018781  cmp     byte ptr [r10+19h], 6
0x180018786  jb      short loc_1800187AC
0x180018788  or      ecx, 0FFFFFFFFh; int
0x18001878b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018790  mov     rcx, [r10+10h]
0x180018794  lea     r8, WPP_15f39820a7e83d8bb98e95b5e6b8c3e1_Traceguids
0x18001879b  mov     edx, 15h
0x1800187a0  mov     [rsp+0E0h+var_C0], ebx
0x1800187a4  mov     r9, rax
0x1800187a7  call    WPP_SF_sd
0x1800187ac  add     rsp, 0C8h
0x1800187b3  pop     r14
0x1800187b5  pop     rdi
0x1800187b6  pop     rbx
0x1800187b7  pop     rbp
0x1800187b8  retn
```
