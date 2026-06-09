# CACSecurityPage::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x18000c290`
- end: `0x18000c7c9`
- name: `?ProcessWindowMessage@CACSecurityPage@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `1337`
- prototype: `__int64 __usercall@<rax>(CACSecurityPage *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006134`
- `0x180007604`
- `0x180008670`
- `0x180009380`
- `0x180009dd0`
- `0x180009f38`
- `0x18000a194`
- `0x18000a29c`
- `0x18000a4b4`
- `0x18000a690`
- `0x18000a7f8`
- `0x18000ad4c`
- `0x18000b078`
- `0x18000b2e8`
- `0x18000b3a8`
- `0x18000b514`
- `0x18000c290`
- `0x18000c824`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x18000c57c`
- `ntdll!WinSqmIncrementDWORD` at `0x18000c57c`
- `USER32!KillTimer` at `0x18000c6db`
- `USER32!KillTimer` at `0x18000c6db`
- `USER32!IsWindowEnabled` at `0x18000c5bf`
- `USER32!IsWindowEnabled` at `0x18000c5bf`
- `USER32!IsWindowVisible` at `0x18000c5b1`
- `USER32!IsWindowVisible` at `0x18000c5b1`
- `USER32!SetWindowLongPtrW` at `0x18000c769`
- `USER32!SetWindowLongPtrW` at `0x18000c769`
- `USER32!SendMessageW` at `0x18000c5d8`
- `USER32!SendMessageW` at `0x18000c603`
- `USER32!SendMessageW` at `0x18000c5d8`
- `USER32!SendMessageW` at `0x18000c603`

## pseudocode

```c
_BOOL8 __fastcall CACSecurityPage::ProcessWindowMessage(
        CACSecurityPage *this,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        struct tagNMHDR *a5,
        __int64 *a6,
        unsigned int a7)
{
  CTooltip *v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int16 v11; // dx
  __int16 v12; // r15
  __int16 v13; // bx
  CACSecurityPage **v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // r14
  unsigned int v18; // r8d
  HWND *v19; // rcx
  NetworkKeyControls *v20; // rcx
  __int64 v21; // rax
  bool v22; // zf
  int v23; // ebx
  __int64 v25; // rbx
  int v26; // eax
  HWND v27; // rcx
  __int64 inited; // rax
  HWND *v29; // rbx
  LONG_PTR v30; // rbx
  HWND v31; // rcx
  int *v32; // [rsp+20h] [rbp-18h]

  if ( a7 )
    return 0;
  v9 = (CACSecurityPage *)((char *)this + 608);
  if ( (unsigned int)(a3 - 513) <= 9 && (a2 = 585, _bittest((const int *)&a2, a3 - 513))
    || (_DWORD)a3 == 24
    || (_DWORD)a3 == 8
    || (_DWORD)a3 == 256 )
  {
    a7 = 1;
    CTooltip::HideBalloon(v9);
    *a6 = 0;
    return 0;
  }
  if ( (_DWORD)a3 != 273 )
  {
    if ( (_DWORD)a3 == 272 )
    {
      a7 = 1;
      inited = CACSecurityPage::OnInitDialog(this, a2, a3, a4, v32);
    }
    else if ( (_DWORD)a3 == 2 )
    {
      a7 = 1;
      inited = CACSecurityPage::OnDestroy(this, a2, a3, a4, v32);
    }
    else if ( (_DWORD)a3 == 794 )
    {
      a7 = 1;
      inited = CACSecurityPage::OnThemeChange(this, a2, a3, a4, (int *)&a7);
    }
    else
    {
      if ( (_DWORD)a3 != 15 )
      {
        if ( (_DWORD)a3 != 275 )
        {
          if ( (_DWORD)a3 == 78 )
          {
            if ( a5->code == -209 )
            {
              *a6 = 0;
              return 1;
            }
            if ( a5->code == -202 )
            {
              a7 = 1;
              *a6 = CACSecurityPage::OnApply(this, (unsigned int)a4, a5, (int *)&a7);
              if ( a7 )
                return 1;
            }
            if ( a5->code == -201 )
            {
              v30 = *((int *)this + 22);
              v31 = (HWND)*((_QWORD *)this + 1);
              a7 = 1;
              SetWindowLongPtrW(v31, 0, v30);
              *a6 = v30;
              if ( a7 )
                return 1;
            }
            if ( a5->code == -200 )
            {
              a7 = 1;
              CACSecurityPage::RefreshControls(this);
              v22 = a7 == 0;
              *a6 = 0;
              return !v22;
            }
          }
          return 0;
        }
        v29 = (HWND *)*((_QWORD *)this + 166);
        a7 = 1;
        CTooltip::HideBalloon((CTooltip *)(*v29 + 152));
        KillTimer(v29[2], 0x3EBu);
        *a6 = 1;
LABEL_68:
        v22 = a7 == 0;
        return !v22;
      }
      a7 = 1;
      inited = CACSecurityPage::OnPaint(this, a2, a3, a4, (int *)&a7);
    }
    *a6 = inited;
    goto LABEL_68;
  }
  if ( (_WORD)a4 == 1115 )
  {
    v10 = a4 >> 16;
LABEL_11:
    v11 = 768;
    a7 = 1;
    if ( (_WORD)v10 == 768 )
      CTooltip::HideBalloon(v9);
    *a6 = 0;
    v12 = a4;
    goto LABEL_14;
  }
  v10 = a4 >> 16;
  v11 = 1116;
  if ( (_WORD)a4 == 1116 )
    goto LABEL_11;
  v12 = a4;
  if ( (_WORD)a4 == 1120 )
  {
    v19 = (HWND *)*((_QWORD *)this + 167);
    a7 = 1;
    *a6 = EapControls::OnProperties(v19, 1116, 273, (HWND)a4, (int *)&a7);
    if ( a7 )
      return 1;
    v13 = 1120;
    goto LABEL_17;
  }
LABEL_14:
  v13 = v12;
  if ( v12 == 1119 )
  {
    v14 = (CACSecurityPage **)*((_QWORD *)this + 167);
    a7 = 1;
    CACSecurityPage::RefreshControls(*v14);
    v15 = LresFromHr(0);
    goto LABEL_16;
  }
  if ( v12 == 1117 )
  {
    v20 = (NetworkKeyControls *)*((_QWORD *)this + 166);
    a7 = 1;
    v15 = NetworkKeyControls::OnShowCharacters(v20, v11, a3, (HWND)a4, (int *)&a7);
LABEL_16:
    *a6 = v15;
    if ( a7 )
      return 1;
    goto LABEL_17;
  }
  if ( v12 != 1111 )
  {
LABEL_17:
    v16 = a4 >> 16;
    goto LABEL_18;
  }
  a7 = 1;
  v16 = a4 >> 16;
  *a6 = CACSecurityPage::OnAuthSelection(this, WORD1(a4), a3, (HWND)a4, (int *)&a7);
  if ( a7 )
    return 1;
LABEL_18:
  switch ( v13 )
  {
    case 1112:
      a7 = 1;
      *a6 = CACSecurityPage::OnEncrSelection(this, v16, a3, (HWND)a4, (int *)&a7);
      if ( a7 )
        return 1;
      break;
    case 1115:
      a7 = 1;
      *a6 = CACSecurityPage::OnSecurityKey(this, v16, a3, (HWND)a4, (int *)&a7);
      if ( a7 )
        return 1;
      v13 = a4;
      goto LABEL_22;
    case 15079:
      a7 = 1;
      *a6 = CACSecurityPage::OnConfigureButton(this, v11, a3, (HWND)a4, (int *)&a7);
      if ( a7 )
        return 1;
      break;
    case 1124:
      a7 = 1;
      *a6 = CACSecurityPage::OnIHVKeyExtSettingsButton(this, v11, a3, (HWND)a4, (int *)&a7);
      if ( a7 )
        return 1;
      goto LABEL_22;
    case 1129:
      a7 = 1;
      WinSqmIncrementDWORD(0, 6147, 1);
      v23 = CACSecurityPage::DisplayAdditionalSettings(this);
      CACSecurityPage::RefreshControls(this);
      *a6 = LresFromHr(v23);
      return 1;
  }
  if ( v13 == 15078 )
  {
    a7 = 1;
    v21 = CACSecurityPage::OnIHVSecuritySelection(this, WORD1(a4), a3, (HWND)a4, (int *)&a7);
    v22 = a7 == 0;
LABEL_54:
    *a6 = v21;
    return !v22;
  }
LABEL_22:
  v17 = a4 >> 16;
  if ( v13 == 1125 )
  {
    a7 = 1;
    if ( (_WORD)v17 != 1 )
    {
      v18 = 0;
LABEL_52:
      v21 = 0;
      goto LABEL_53;
    }
    v25 = *((_QWORD *)this + 166);
    if ( !IsWindowVisible(*(HWND *)(v25 + 56)) || !IsWindowEnabled(*(HWND *)(v25 + 56)) )
    {
      v18 = a7;
      goto LABEL_52;
    }
    v26 = SendMessageW(*(HWND *)(v25 + 56), 0x147u, 0, 0);
    if ( !*(_DWORD *)(v25 + 72) )
    {
      if ( v26 == *(_DWORD *)(v25 + 76) )
      {
LABEL_50:
        v21 = LresFromHr(0);
LABEL_53:
        v22 = v18 == 0;
        goto LABEL_54;
      }
      *(_DWORD *)(v25 + 72) = 1;
    }
    if ( v26 != *(_DWORD *)(v25 + 76) )
    {
      v27 = *(HWND *)(v25 + 56);
      *(_DWORD *)(v25 + 76) = v26;
      SendMessageW(v27, 0x14Eu, v26, 0);
    }
    goto LABEL_50;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c290  push    rbp
0x18000c292  push    rbx
0x18000c293  push    rsi
0x18000c294  push    rdi
0x18000c295  push    r12
0x18000c297  push    r13
0x18000c299  push    r14
0x18000c29b  push    r15
0x18000c29d  mov     rbp, rsp
0x18000c2a0  sub     rsp, 38h
0x18000c2a4  xor     r13d, r13d
0x18000c2a7  mov     r14, r9
0x18000c2aa  mov     rsi, rcx
0x18000c2ad  cmp     [rbp+arg_30], r13d
0x18000c2b1  jnz     loc_18000C7B6
0x18000c2b7  add     rcx, 260h; this
0x18000c2be  lea     eax, [r8-201h]
0x18000c2c5  cmp     eax, 9
0x18000c2c8  ja      short loc_18000C2D8
0x18000c2ca  mov     edx, 249h; unsigned int
0x18000c2cf  bt      edx, eax
0x18000c2d2  jb      loc_18000C7A2
0x18000c2d8  cmp     r8d, 18h
0x18000c2dc  jz      loc_18000C7A2
0x18000c2e2  cmp     r8d, 8
0x18000c2e6  jz      loc_18000C7A2
0x18000c2ec  cmp     r8d, 100h
0x18000c2f3  jz      loc_18000C7A2
0x18000c2f9  cmp     r8d, 111h
0x18000c300  jnz     loc_18000C62E
0x18000c306  mov     r12, [rbp+arg_28]
0x18000c30a  mov     eax, 45Bh
0x18000c30f  cmp     ax, r14w
0x18000c313  mov     edi, 1
0x18000c318  mov     rax, r14
0x18000c31b  jnz     short loc_18000C323
0x18000c31d  shr     rax, 10h
0x18000c321  jmp     short loc_18000C336
0x18000c323  shr     rax, 10h
0x18000c327  mov     edx, 45Ch; unsigned __int16
0x18000c32c  cmp     dx, r14w
0x18000c330  jnz     loc_18000C41F
0x18000c336  mov     edx, 300h
0x18000c33b  mov     [rbp+arg_30], edi
0x18000c33e  cmp     ax, dx
0x18000c341  jnz     short loc_18000C348
0x18000c343  call    ?HideBalloon@CTooltip@@QEAAXXZ; CTooltip::HideBalloon(void)
0x18000c348  mov     [r12], r13
0x18000c34c  movzx   r15d, r14w
0x18000c350  mov     eax, 45Fh
0x18000c355  movzx   ebx, r15w
0x18000c359  cmp     ax, r15w
0x18000c35d  jnz     loc_18000C461
0x18000c363  mov     rcx, [rsi+538h]
0x18000c36a  mov     [rbp+arg_30], edi
0x18000c36d  mov     rcx, [rcx]; this
0x18000c370  call    ?RefreshControls@CACSecurityPage@@AEAA_JXZ; CACSecurityPage::RefreshControls(void)
0x18000c375  xor     ecx, ecx; int
0x18000c377  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000c37c  mov     [r12], rax
0x18000c380  cmp     [rbp+arg_30], r13d
0x18000c384  jnz     loc_18000C59F
0x18000c38a  mov     r13, r14
0x18000c38d  shr     r13, 10h
0x18000c391  xor     r15d, r15d
0x18000c394  mov     eax, 458h
0x18000c399  cmp     ax, bx
0x18000c39c  jnz     loc_18000C4CD
0x18000c3a2  lea     rax, [rbp+arg_30]
0x18000c3a6  mov     [rbp+arg_30], edi
0x18000c3a9  movzx   edx, r13w; unsigned __int16
0x18000c3ad  mov     [rsp+38h+var_18], rax; int *
0x18000c3b2  mov     rcx, rsi; this
0x18000c3b5  call    ?OnEncrSelection@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z; CACSecurityPage::OnEncrSelection(ushort,ushort,HWND__ *,int &)
0x18000c3ba  mov     [r12], rax
0x18000c3be  cmp     [rbp+arg_30], r15d
0x18000c3c2  jnz     loc_18000C59F
0x18000c3c8  mov     eax, 464h
0x18000c3cd  cmp     ax, bx
0x18000c3d0  jnz     loc_18000C565
0x18000c3d6  lea     rax, [rbp+arg_30]
0x18000c3da  mov     [rbp+arg_30], edi
0x18000c3dd  mov     rcx, rsi; this
0x18000c3e0  mov     [rsp+38h+var_18], rax; int *
0x18000c3e5  call    ?OnIHVKeyExtSettingsButton@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z; CACSecurityPage::OnIHVKeyExtSettingsButton(ushort,ushort,HWND__ *,int &)
0x18000c3ea  mov     [r12], rax
0x18000c3ee  cmp     [rbp+arg_30], r15d
0x18000c3f2  jnz     loc_18000C59F
0x18000c3f8  shr     r14, 10h
0x18000c3fc  mov     eax, 465h
0x18000c401  cmp     ax, bx
0x18000c404  jnz     loc_18000C7B6
0x18000c40a  mov     [rbp+arg_30], edi
0x18000c40d  cmp     r14w, di
0x18000c411  jz      loc_18000C5A6
0x18000c417  mov     r8d, r15d; unsigned __int16
0x18000c41a  jmp     loc_18000C619
0x18000c41f  mov     eax, 460h
0x18000c424  movzx   r15d, r14w
0x18000c428  cmp     ax, r14w
0x18000c42c  jnz     loc_18000C350
0x18000c432  mov     rcx, [rsi+538h]; this
0x18000c439  lea     rax, [rbp+arg_30]
0x18000c43d  mov     [rsp+38h+var_18], rax; int *
0x18000c442  mov     [rbp+arg_30], edi
0x18000c445  call    ?OnProperties@EapControls@@QEAA_JGGPEAUHWND__@@AEAH@Z; EapControls::OnProperties(ushort,ushort,HWND__ *,int &)
0x18000c44a  mov     [r12], rax
0x18000c44e  cmp     [rbp+arg_30], r13d
0x18000c452  jnz     loc_18000C59F
0x18000c458  movzx   ebx, r14w
0x18000c45c  jmp     loc_18000C38A
0x18000c461  mov     eax, 45Dh
0x18000c466  cmp     ax, r15w
0x18000c46a  jnz     short loc_18000C489
0x18000c46c  mov     rcx, [rsi+530h]; this
0x18000c473  lea     rax, [rbp+arg_30]
0x18000c477  mov     [rsp+38h+var_18], rax; int *
0x18000c47c  mov     [rbp+arg_30], edi
0x18000c47f  call    ?OnShowCharacters@NetworkKeyControls@@QEAA_JGGPEAUHWND__@@AEAH@Z; NetworkKeyControls::OnShowCharacters(ushort,ushort,HWND__ *,int &)
0x18000c484  jmp     loc_18000C37C
0x18000c489  mov     eax, 457h
0x18000c48e  cmp     ax, r15w
0x18000c492  jnz     loc_18000C38A
0x18000c498  lea     rax, [rbp+arg_30]
0x18000c49c  mov     [rbp+arg_30], edi
0x18000c49f  mov     r13, r14
0x18000c4a2  mov     [rsp+38h+var_18], rax; int *
0x18000c4a7  shr     r13, 10h
0x18000c4ab  mov     rcx, rsi; this
0x18000c4ae  movzx   edx, r13w; unsigned __int16
0x18000c4b2  call    ?OnAuthSelection@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z; CACSecurityPage::OnAuthSelection(ushort,ushort,HWND__ *,int &)
0x18000c4b7  xor     r15d, r15d
0x18000c4ba  mov     [r12], rax
0x18000c4be  cmp     [rbp+arg_30], r15d
0x18000c4c2  jnz     loc_18000C59F
0x18000c4c8  jmp     loc_18000C394
0x18000c4cd  mov     eax, 45Bh
0x18000c4d2  cmp     ax, bx
0x18000c4d5  jnz     short loc_18000C506
0x18000c4d7  lea     rax, [rbp+arg_30]
0x18000c4db  mov     [rbp+arg_30], edi
0x18000c4de  movzx   edx, r13w; unsigned __int16
0x18000c4e2  mov     [rsp+38h+var_18], rax; int *
0x18000c4e7  mov     rcx, rsi; this
0x18000c4ea  call    ?OnSecurityKey@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z; CACSecurityPage::OnSecurityKey(ushort,ushort,HWND__ *,int &)
0x18000c4ef  mov     [r12], rax
0x18000c4f3  cmp     [rbp+arg_30], r15d
0x18000c4f7  jnz     loc_18000C59F
0x18000c4fd  movzx   ebx, r14w
0x18000c501  jmp     loc_18000C3F8
0x18000c506  mov     eax, 3AE7h
0x18000c50b  cmp     ax, bx
0x18000c50e  jnz     loc_18000C3C8
0x18000c514  lea     rax, [rbp+arg_30]
0x18000c518  mov     [rbp+arg_30], edi
0x18000c51b  mov     rcx, rsi; this
0x18000c51e  mov     [rsp+38h+var_18], rax; int *
0x18000c523  call    ?OnConfigureButton@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z; CACSecurityPage::OnConfigureButton(ushort,ushort,HWND__ *,int &)
0x18000c528  mov     [r12], rax
0x18000c52c  cmp     [rbp+arg_30], r15d
0x18000c530  jnz     short loc_18000C59F
0x18000c532  mov     eax, 3AE6h
0x18000c537  cmp     ax, bx
0x18000c53a  jnz     loc_18000C3F8
0x18000c540  lea     rax, [rbp+arg_30]
0x18000c544  shr     r14, 10h
0x18000c548  movzx   edx, r14w; unsigned __int16
0x18000c54c  mov     [rbp+arg_30], edi
0x18000c54f  mov     rcx, rsi; this
0x18000c552  mov     [rsp+38h+var_18], rax; int *
0x18000c557  call    ?OnIHVSecuritySelection@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z; CACSecurityPage::OnIHVSecuritySelection(ushort,ushort,HWND__ *,int &)
0x18000c55c  cmp     [rbp+arg_30], r15d
0x18000c560  jmp     loc_18000C61F
0x18000c565  mov     eax, 469h
0x18000c56a  cmp     ax, bx
0x18000c56d  jnz     short loc_18000C532
0x18000c56f  mov     r8d, edi
0x18000c572  mov     [rbp+arg_30], edi
0x18000c575  mov     edx, 1803h
0x18000c57a  xor     ecx, ecx
0x18000c57c  call    cs:__imp_WinSqmIncrementDWORD
0x18000c582  mov     rcx, rsi; this
0x18000c585  call    ?DisplayAdditionalSettings@CACSecurityPage@@AEAAJXZ; CACSecurityPage::DisplayAdditionalSettings(void)
0x18000c58a  mov     rcx, rsi; this
0x18000c58d  mov     ebx, eax
0x18000c58f  call    ?RefreshControls@CACSecurityPage@@AEAA_JXZ; CACSecurityPage::RefreshControls(void)
0x18000c594  mov     ecx, ebx; int
0x18000c596  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000c59b  mov     [r12], rax
0x18000c59f  mov     eax, edi
0x18000c5a1  jmp     loc_18000C7B8
0x18000c5a6  mov     rbx, [rsi+530h]
0x18000c5ad  mov     rcx, [rbx+38h]; hWnd
0x18000c5b1  call    cs:__imp_IsWindowVisible
0x18000c5b7  test    eax, eax
0x18000c5b9  jz      short loc_18000C615
0x18000c5bb  mov     rcx, [rbx+38h]; hWnd
0x18000c5bf  call    cs:__imp_IsWindowEnabled
0x18000c5c5  test    eax, eax
0x18000c5c7  jz      short loc_18000C615
0x18000c5c9  mov     rcx, [rbx+38h]; hWnd
0x18000c5cd  xor     r9d, r9d; lParam
0x18000c5d0  xor     r8d, r8d; wParam
0x18000c5d3  mov     edx, 147h; Msg
0x18000c5d8  call    cs:__imp_SendMessageW
0x18000c5de  cmp     [rbx+48h], r15d
0x18000c5e2  jnz     short loc_18000C5EC
0x18000c5e4  cmp     eax, [rbx+4Ch]
0x18000c5e7  jz      short loc_18000C609
0x18000c5e9  mov     [rbx+48h], edi
0x18000c5ec  cmp     eax, [rbx+4Ch]
0x18000c5ef  jz      short loc_18000C609
0x18000c5f1  mov     rcx, [rbx+38h]; hWnd
0x18000c5f5  xor     r9d, r9d; lParam
0x18000c5f8  movsxd  r8, eax; wParam
0x18000c5fb  mov     edx, 14Eh; Msg
0x18000c600  mov     [rbx+4Ch], eax
0x18000c603  call    cs:__imp_SendMessageW
0x18000c609  xor     ecx, ecx; int
0x18000c60b  mov     r8d, edi
0x18000c60e  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000c613  jmp     short loc_18000C61C
0x18000c615  mov     r8d, [rbp+arg_30]; unsigned __int64
0x18000c619  mov     rax, r15
0x18000c61c  test    r8d, r8d
0x18000c61f  mov     [r12], rax
0x18000c623  jnz     loc_18000C59F
0x18000c629  jmp     loc_18000C7B6
0x18000c62e  cmp     r8d, 110h
0x18000c635  jnz     short loc_18000C649
0x18000c637  mov     edi, 1
0x18000c63c  mov     rcx, rsi; this
0x18000c63f  mov     [rbp+arg_30], edi
0x18000c642  call    ?OnInitDialog@CACSecurityPage@@QEAA_JI_K_JAEAH@Z; CACSecurityPage::OnInitDialog(uint,unsigned __int64,__int64,int &)
0x18000c647  jmp     short loc_18000C6A2
0x18000c649  cmp     r8d, 2
0x18000c64d  jnz     short loc_18000C660
0x18000c64f  lea     edi, [r8-1]
0x18000c653  mov     rcx, rsi; this
0x18000c656  mov     [rbp+arg_30], edi
0x18000c659  call    ?OnDestroy@CACSecurityPage@@QEAA_JI_K_JAEAH@Z; CACSecurityPage::OnDestroy(uint,unsigned __int64,__int64,int &)
0x18000c65e  jmp     short loc_18000C6A2
0x18000c660  cmp     r8d, 31Ah
0x18000c667  jnz     short loc_18000C684
0x18000c669  lea     rax, [rbp+arg_30]
0x18000c66d  mov     edi, 1
0x18000c672  mov     rcx, rsi; this
0x18000c675  mov     [rbp+arg_30], edi
0x18000c678  mov     [rsp+38h+var_18], rax; int *
0x18000c67d  call    ?OnThemeChange@CACSecurityPage@@QEAA_JI_K_JAEAH@Z; CACSecurityPage::OnThemeChange(uint,unsigned __int64,__int64,int &)
0x18000c682  jmp     short loc_18000C6A2
0x18000c684  cmp     r8d, 0Fh
0x18000c688  jnz     short loc_18000C6AB
0x18000c68a  lea     edi, [r8-0Eh]
0x18000c68e  mov     rcx, rsi; this
0x18000c691  lea     rax, [rbp+arg_30]
0x18000c695  mov     [rbp+arg_30], edi
0x18000c698  mov     [rsp+38h+var_18], rax; int *
0x18000c69d  call    ?OnPaint@CACSecurityPage@@QEAA_JI_K_JAEAH@Z; CACSecurityPage::OnPaint(uint,unsigned __int64,__int64,int &)
0x18000c6a2  mov     rcx, [rbp+arg_28]
0x18000c6a6  mov     [rcx], rax
0x18000c6a9  jmp     short loc_18000C6E8
0x18000c6ab  cmp     r8d, 113h
0x18000c6b2  jnz     short loc_18000C6F1
0x18000c6b4  mov     rbx, [rsi+530h]
0x18000c6bb  mov     edi, 1
0x18000c6c0  mov     [rbp+arg_30], edi
0x18000c6c3  mov     rcx, [rbx]
0x18000c6c6  add     rcx, 260h; this
0x18000c6cd  call    ?HideBalloon@CTooltip@@QEAAXXZ; CTooltip::HideBalloon(void)
0x18000c6d2  mov     rcx, [rbx+10h]; hWnd
0x18000c6d6  mov     edx, 3EBh; uIDEvent
0x18000c6db  call    cs:__imp_KillTimer
0x18000c6e1  mov     rax, [rbp+arg_28]
0x18000c6e5  mov     [rax], rdi
0x18000c6e8  cmp     [rbp+arg_30], r13d
0x18000c6ec  jmp     loc_18000C623
0x18000c6f1  cmp     r8d, 4Eh ; 'N'
0x18000c6f5  jnz     loc_18000C7B6
0x18000c6fb  mov     r15, [rbp+arg_20]
0x18000c6ff  cmp     dword ptr [r15+10h], 0FFFFFF2Fh
0x18000c707  jnz     short loc_18000C719
0x18000c709  mov     rax, [rbp+arg_28]
0x18000c70d  mov     [rax], r13
0x18000c710  lea     eax, [r8-4Dh]
0x18000c714  jmp     loc_18000C7B8
0x18000c719  cmp     dword ptr [r15+10h], 0FFFFFF36h
0x18000c721  mov     edi, 1
0x18000c726  mov     r12, [rbp+arg_28]
0x18000c72a  jnz     short loc_18000C74F
0x18000c72c  mov     edx, r14d; int
0x18000c72f  mov     [rbp+arg_30], edi
0x18000c732  lea     r9, [rbp+arg_30]; int *
0x18000c736  mov     r8, r15; struct tagNMHDR *
0x18000c739  mov     rcx, rsi; this
0x18000c73c  call    ?OnApply@CACSecurityPage@@QEAA_JHPEAUtagNMHDR@@AEAH@Z; CACSecurityPage::OnApply(int,tagNMHDR *,int &)
0x18000c741  mov     [r12], rax
0x18000c745  cmp     [rbp+arg_30], r13d
0x18000c749  jnz     loc_18000C59F
0x18000c74f  cmp     dword ptr [r15+10h], 0FFFFFF37h
  ... truncated ...
```
