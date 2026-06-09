# CWcnPageProfileCreateNew::GetControlHandles(void)

- ea: `0x1800141d4`
- end: `0x1800143a6`
- name: `?GetControlHandles@CWcnPageProfileCreateNew@@AEAAJXZ`
- size: `466`
- prototype: `__int64 __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180014880`

## callees

- `0x18000d630`
- `0x18000e1dc`
- `0x1800141d4`
- `0x18002de1c`

## import_xrefs

- `USER32!GetDlgItem` at `0x180014229`
- `USER32!GetDlgItem` at `0x180014242`
- `USER32!GetDlgItem` at `0x18001425b`
- `USER32!GetDlgItem` at `0x180014274`
- `USER32!GetDlgItem` at `0x18001428d`
- `USER32!GetDlgItem` at `0x1800142a6`
- `USER32!GetDlgItem` at `0x1800142bf`
- `USER32!GetDlgItem` at `0x1800142d8`
- `USER32!GetDlgItem` at `0x180014229`
- `USER32!GetDlgItem` at `0x180014242`
- `USER32!GetDlgItem` at `0x18001425b`
- `USER32!GetDlgItem` at `0x180014274`
- `USER32!GetDlgItem` at `0x18001428d`
- `USER32!GetDlgItem` at `0x1800142a6`
- `USER32!GetDlgItem` at `0x1800142bf`
- `USER32!GetDlgItem` at `0x1800142d8`

## pseudocode

```c
__int64 __fastcall CWcnPageProfileCreateNew::GetControlHandles(HWND *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  HWND DlgItem; // rax
  HWND v5; // rcx
  HWND v6; // rax
  HWND v7; // rcx
  HWND v8; // rax
  HWND v9; // rcx
  HWND v10; // rax
  HWND v11; // rcx
  HWND v12; // rax
  HWND v13; // rcx
  HWND v14; // rax
  HWND v15; // rcx
  HWND v16; // rax
  HWND v17; // rcx
  HWND v18; // rax
  unsigned int v19; // ebx
  _BYTE *v20; // r10
  unsigned int v21; // eax
  __int64 v22; // r10
  const char *v23; // rax
  __int64 v24; // r10

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 46, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  DlgItem = GetDlgItem(this[21], 1411);
  v5 = this[21];
  this[37] = DlgItem;
  v6 = GetDlgItem(v5, 1083);
  v7 = this[21];
  this[38] = v6;
  v8 = GetDlgItem(v7, 1412);
  v9 = this[21];
  this[39] = v8;
  v10 = GetDlgItem(v9, 1082);
  v11 = this[21];
  this[40] = v10;
  v12 = GetDlgItem(v11, 1602);
  v13 = this[21];
  this[41] = v12;
  v14 = GetDlgItem(v13, 1084);
  v15 = this[21];
  this[42] = v14;
  v16 = GetDlgItem(v15, 1603);
  v17 = this[21];
  this[43] = v16;
  v18 = GetDlgItem(v17, 2304);
  this[44] = v18;
  if ( this[37] )
  {
    if ( this[38] )
    {
      if ( this[39] )
      {
        if ( this[40] )
        {
          if ( this[41] )
          {
            if ( this[42] )
            {
              if ( this[43] )
              {
                v19 = 0;
                if ( v18 )
                  goto LABEL_15;
              }
            }
          }
        }
      }
    }
  }
  v19 = -2147024882;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v19;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v22 + 16), 47, (unsigned int)WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v21, 14);
LABEL_15:
    v20 = WPP_GLOBAL_Control;
  }
  if ( v20 != (_BYTE *)&WPP_GLOBAL_Control && v20[25] >= 6u )
  {
    v23 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v24 + 16), 48, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v23);
  }
  return v19;
}

```

## disassembly

```asm
0x1800141d4  mov     [rsp+arg_0], rbx
0x1800141d9  push    rdi
0x1800141da  sub     rsp, 30h
0x1800141de  mov     rbx, rcx
0x1800141e1  mov     r10, cs:WPP_GLOBAL_Control
0x1800141e8  lea     rdi, WPP_GLOBAL_Control
0x1800141ef  cmp     r10, rdi
0x1800141f2  jz      short loc_18001421D
0x1800141f4  cmp     byte ptr [r10+19h], 6
0x1800141f9  jb      short loc_18001421D
0x1800141fb  mov     ecx, 1; int
0x180014200  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014205  mov     rcx, [r10+10h]
0x180014209  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180014210  mov     edx, 2Eh ; '.'
0x180014215  mov     r9, rax
0x180014218  call    WPP_SF_s
0x18001421d  mov     rcx, [rbx+0A8h]; hDlg
0x180014224  mov     edx, 583h; nIDDlgItem
0x180014229  call    cs:__imp_GetDlgItem
0x18001422f  mov     rcx, [rbx+0A8h]; hDlg
0x180014236  mov     edx, 43Bh; nIDDlgItem
0x18001423b  mov     [rbx+128h], rax
0x180014242  call    cs:__imp_GetDlgItem
0x180014248  mov     rcx, [rbx+0A8h]; hDlg
0x18001424f  mov     edx, 584h; nIDDlgItem
0x180014254  mov     [rbx+130h], rax
0x18001425b  call    cs:__imp_GetDlgItem
0x180014261  mov     rcx, [rbx+0A8h]; hDlg
0x180014268  mov     edx, 43Ah; nIDDlgItem
0x18001426d  mov     [rbx+138h], rax
0x180014274  call    cs:__imp_GetDlgItem
0x18001427a  mov     rcx, [rbx+0A8h]; hDlg
0x180014281  mov     edx, 642h; nIDDlgItem
0x180014286  mov     [rbx+140h], rax
0x18001428d  call    cs:__imp_GetDlgItem
0x180014293  mov     rcx, [rbx+0A8h]; hDlg
0x18001429a  mov     edx, 43Ch; nIDDlgItem
0x18001429f  mov     [rbx+148h], rax
0x1800142a6  call    cs:__imp_GetDlgItem
0x1800142ac  mov     rcx, [rbx+0A8h]; hDlg
0x1800142b3  mov     edx, 643h; nIDDlgItem
0x1800142b8  mov     [rbx+150h], rax
0x1800142bf  call    cs:__imp_GetDlgItem
0x1800142c5  mov     rcx, [rbx+0A8h]; hDlg
0x1800142cc  mov     edx, 900h; nIDDlgItem
0x1800142d1  mov     [rbx+158h], rax
0x1800142d8  call    cs:__imp_GetDlgItem
0x1800142de  xor     ecx, ecx; int
0x1800142e0  mov     [rbx+160h], rax
0x1800142e7  cmp     [rbx+128h], rcx
0x1800142ee  jz      short loc_18001432D
0x1800142f0  cmp     [rbx+130h], rcx
0x1800142f7  jz      short loc_18001432D
0x1800142f9  cmp     [rbx+138h], rcx
0x180014300  jz      short loc_18001432D
0x180014302  cmp     [rbx+140h], rcx
0x180014309  jz      short loc_18001432D
0x18001430b  cmp     [rbx+148h], rcx
0x180014312  jz      short loc_18001432D
0x180014314  cmp     [rbx+150h], rcx
0x18001431b  jz      short loc_18001432D
0x18001431d  cmp     [rbx+158h], rcx
0x180014324  jz      short loc_18001432D
0x180014326  mov     ebx, ecx
0x180014328  test    rax, rax
0x18001432b  jnz     short loc_180014366
0x18001432d  mov     ebx, 8007000Eh
0x180014332  mov     r10, cs:WPP_GLOBAL_Control
0x180014339  cmp     r10, rdi
0x18001433c  jz      short loc_180014399
0x18001433e  cmp     byte ptr [r10+19h], 2
0x180014343  jb      short loc_18001436D
0x180014345  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001434a  mov     rcx, [r10+10h]
0x18001434e  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180014355  mov     edx, 2Fh ; '/'
0x18001435a  mov     [rsp+38h+var_18], ebx
0x18001435e  mov     r9, rax
0x180014361  call    WPP_SF_sd
0x180014366  mov     r10, cs:WPP_GLOBAL_Control
0x18001436d  cmp     r10, rdi
0x180014370  jz      short loc_180014399
0x180014372  cmp     byte ptr [r10+19h], 6
0x180014377  jb      short loc_180014399
0x180014379  or      ecx, 0FFFFFFFFh; int
0x18001437c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014381  mov     rcx, [r10+10h]
0x180014385  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x18001438c  mov     edx, 30h ; '0'
0x180014391  mov     r9, rax
0x180014394  call    WPP_SF_s
0x180014399  mov     eax, ebx
0x18001439b  mov     rbx, [rsp+38h+arg_0]
0x1800143a0  add     rsp, 30h
0x1800143a4  pop     rdi
0x1800143a5  retn
```
