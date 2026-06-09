# CInstallationWizard::CEulaDialog::HandleMessage(uint,unsigned __int64,__int64,__int64 &)

- ea: `0x1800280f0`
- end: `0x180028395`
- name: `?HandleMessage@CEulaDialog@CInstallationWizard@@EEAAHI_K_JAEA_J@Z`
- size: `677`
- prototype: `__int64 __fastcall(CInstallationWizard::CEulaDialog *this, int, unsigned __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000588c`
- `0x1800280f0`
- `0x18002839c`
- `0x18004b958`
- `0x180081a38`
- `0x180095fa8`
- `0x18009b050`
- `0x18009b0b8`
- `0x1800a1960`

## import_xrefs

- `USER32!SendMessageW` at `0x180028231`
- `USER32!SendMessageW` at `0x180028231`
- `USER32!GetParent` at `0x1800281a0`
- `USER32!GetParent` at `0x180028214`
- `USER32!GetParent` at `0x18002827b`
- `USER32!GetParent` at `0x1800282d4`
- `USER32!GetParent` at `0x1800281a0`
- `USER32!GetParent` at `0x180028214`
- `USER32!GetParent` at `0x18002827b`
- `USER32!GetParent` at `0x1800282d4`
- `GDI32!DeleteObject` at `0x180028350`
- `GDI32!DeleteObject` at `0x180028350`

## string_xrefs

- `0x180028324`: `C:\__w\1\s\src\Client\comapi\installationwizard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CInstallationWizard::CEulaDialog::HandleMessage(
        CInstallationWizard::CEulaDialog *this,
        int a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 *a5)
{
  unsigned __int64 v6; // rsi
  unsigned int v7; // edi
  int v8; // ebp
  __int64 *v9; // r14
  _DWORD *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // r14
  __int64 v14; // r8
  _DWORD *v15; // rcx
  HWND Parent; // rcx
  WPARAM v17; // r8
  __int64 v19; // rdi
  struct SimpleUpdateInfo *v20; // r10
  __int64 v21; // rbp
  HWND v22; // rcx
  struct ISusInternal **v23; // rax
  int v24; // eax
  void *v25; // rcx
  int v26; // [rsp+20h] [rbp-58h]
  int v27; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a5 = 0;
  if ( a2 == 2 )
  {
    SusFree(*((void **)this + 14));
    *((_QWORD *)this + 14) = 0;
    v25 = (void *)*((_QWORD *)this + 16);
    if ( v25 )
      DeleteObject(v25);
    *((_QWORD *)this + 16) = 0;
    operator delete(*((void **)this + 12));
    *((_QWORD *)this + 12) = 0;
    return 1;
  }
  if ( a2 == 78 )
  {
    if ( *(_QWORD *)(a4 + 8) == 64407 && (*(_DWORD *)(a4 + 16) == -2 || *(_DWORD *)(a4 + 16) == -4) )
    {
      v24 = CInstallationWizard::CEulaDialog::OnPrintableVersionInternal(this);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x231,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
          (const char *)(unsigned int)v24,
          v26);
      return 1;
    }
    return 0;
  }
  if ( a2 != 273 )
    return 0;
  v6 = a3 >> 16;
  v7 = (unsigned __int16)a3;
  if ( WORD1(a3) )
    return 0;
  if ( (_WORD)a3 == 0xFB98 )
  {
    v8 = ConfirmDecline(*((_QWORD *)this + 1));
    if ( v8 )
    {
      v9 = (__int64 *)*((_QWORD *)this + 11);
      v10 = (_DWORD *)(*v9 + 88LL * *(int *)(*((_QWORD *)this + 12) + 4LL * *((int *)this + 30)));
      if ( *((_DWORD *)this + 35) )
        GetParent(*((HWND *)this + 1));
      v11 = *((_QWORD *)this + 10);
      v12 = *((int *)v9 + 2);
      v13 = *v9;
      v27 = 0;
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 80LL))(v11, &v27) >= 0 )
      {
        v14 = v12;
        if ( (int)v12 > 0 )
        {
          v15 = (_DWORD *)(v13 + 36);
          do
          {
            if ( *(v15 - 2) == v10[7] && *(v15 - 1) == v10[8] && *v15 == v10[9] && v15[1] == v10[10] )
            {
              v15[2] = 0;
              v15[12] = v8 == 2;
            }
            v15 += 22;
            --v14;
          }
          while ( v14 );
        }
      }
      Parent = GetParent(*((HWND *)this + 1));
      v17 = ((unsigned __int16)v6 << 16) | 1;
      goto LABEL_19;
    }
    return 0;
  }
  if ( (unsigned __int16)a3 == 64409 )
  {
    v19 = *((_QWORD *)this + 11);
    v20 = *(struct SimpleUpdateInfo **)v19;
    v21 = *(_QWORD *)v19 + 88LL * *(int *)(*((_QWORD *)this + 12) + 4LL * *((int *)this + 30));
    if ( *((_DWORD *)this + 35) )
    {
      v22 = GetParent(*((HWND *)this + 1));
      v20 = *(struct SimpleUpdateInfo **)v19;
    }
    else
    {
      v22 = 0;
    }
    if ( *((_DWORD *)this + 35) )
      v23 = (struct ISusInternal **)*((_QWORD *)this + 18);
    else
      v23 = 0;
    SetSimpleUpdateEulaAcceptance(
      v20,
      *(_DWORD *)(v19 + 8),
      *((struct IUpdateCollection **)this + 10),
      (const struct _GUID *)(v21 + 28),
      1,
      0,
      v23,
      v22);
    v7 = 1;
  }
  else if ( (unsigned __int16)a3 != 2 )
  {
    return 0;
  }
  Parent = GetParent(*((HWND *)this + 1));
  v17 = v7 | (unsigned __int64)((unsigned __int16)v6 << 16);
LABEL_19:
  SendMessageW(Parent, 0x111u, v17, 0);
  return 1;
}

```

## disassembly

```asm
0x1800280f0  mov     [rsp+arg_8], rbx
0x1800280f5  mov     [rsp+arg_18], rbp
0x1800280fa  push    rsi
0x1800280fb  push    rdi
0x1800280fc  push    r12
0x1800280fe  push    r14
0x180028100  push    r15
0x180028102  sub     rsp, 50h
0x180028106  mov     rax, cs:__security_cookie
0x18002810d  xor     rax, rsp
0x180028110  mov     [rsp+78h+var_30], rax
0x180028115  mov     rbx, rcx
0x180028118  mov     rax, [rsp+78h+arg_20]
0x180028120  xor     r12d, r12d
0x180028123  mov     [rax], r12
0x180028126  cmp     edx, 2
0x180028129  jz      loc_180028337
0x18002812f  cmp     edx, 4Eh ; 'N'
0x180028132  jz      loc_1800282F3
0x180028138  mov     r14d, 111h
0x18002813e  cmp     edx, r14d
0x180028141  jnz     loc_18002824D
0x180028147  mov     rsi, r8
0x18002814a  shr     rsi, 10h
0x18002814e  movzx   edi, r8w
0x180028152  test    si, si
0x180028155  jnz     loc_18002824D
0x18002815b  mov     eax, 0FB98h
0x180028160  cmp     di, ax
0x180028163  jnz     loc_18002823C
0x180028169  mov     rcx, [rcx+8]
0x18002816d  call    ?ConfirmDecline@@YA?AW4ConfirmDeclineResult@@PEAUHWND__@@W4ConfirmDeclineType@@@Z; ConfirmDecline(HWND__ *,ConfirmDeclineType)
0x180028172  mov     ebp, eax
0x180028174  test    eax, eax
0x180028176  jz      loc_18002824D
0x18002817c  mov     r14, [rbx+58h]
0x180028180  movsxd  rcx, dword ptr [rbx+78h]
0x180028184  mov     rax, [rbx+60h]
0x180028188  movsxd  rcx, dword ptr [rax+rcx*4]
0x18002818c  imul    rdi, rcx, 58h ; 'X'
0x180028190  add     rdi, [r14]
0x180028193  cmp     [rbx+8Ch], r12d
0x18002819a  jz      short loc_1800281A6
0x18002819c  mov     rcx, [rbx+8]; hWnd
0x1800281a0  call    cs:__imp_GetParent
0x1800281a6  mov     rcx, [rbx+50h]
0x1800281aa  movsxd  r15, dword ptr [r14+8]
0x1800281ae  mov     r14, [r14]
0x1800281b1  mov     [rsp+78h+var_38], r12d
0x1800281b6  mov     rax, [rcx]
0x1800281b9  lea     rdx, [rsp+78h+var_38]
0x1800281be  mov     rax, [rax+50h]
0x1800281c2  call    _guard_dispatch_icall
0x1800281c7  test    eax, eax
0x1800281c9  js      short loc_180028210
0x1800281cb  mov     r8, r15
0x1800281ce  test    r15d, r15d
0x1800281d1  jle     short loc_180028210
0x1800281d3  lea     rcx, [r14+24h]
0x1800281d7  mov     eax, [rdi+1Ch]
0x1800281da  cmp     [rcx-8], eax
0x1800281dd  jnz     short loc_180028206
0x1800281df  mov     eax, [rdi+20h]
0x1800281e2  cmp     [rcx-4], eax
0x1800281e5  jnz     short loc_180028206
0x1800281e7  mov     eax, [rdi+24h]
0x1800281ea  cmp     [rcx], eax
0x1800281ec  jnz     short loc_180028206
0x1800281ee  mov     eax, [rdi+28h]
0x1800281f1  cmp     [rcx+4], eax
0x1800281f4  jnz     short loc_180028206
0x1800281f6  mov     [rcx+8], r12d
0x1800281fa  mov     eax, r12d
0x1800281fd  cmp     ebp, 2
0x180028200  setz    al
0x180028203  mov     [rcx+30h], eax
0x180028206  add     rcx, 58h ; 'X'
0x18002820a  sub     r8, 1
0x18002820e  jnz     short loc_1800281D7
0x180028210  mov     rcx, [rbx+8]; hWnd
0x180028214  call    cs:__imp_GetParent
0x18002821a  mov     rcx, rax; hWnd
0x18002821d  movzx   eax, si
0x180028220  shl     eax, 10h
0x180028223  or      eax, 1
0x180028226  movsxd  r8, eax; wParam
0x180028229  mov     edx, 111h; Msg
0x18002822e  xor     r9d, r9d; lParam
0x180028231  call    cs:__imp_SendMessageW
0x180028237  jmp     loc_18002836A
0x18002823c  cmp     edi, 0FB99h
0x180028242  jz      short loc_180028254
0x180028244  cmp     edi, 2
0x180028247  jz      loc_1800282D0
0x18002824d  xor     eax, eax
0x18002824f  jmp     loc_18002836F
0x180028254  mov     rdi, [rcx+58h]
0x180028258  mov     r10, [rdi]
0x18002825b  movsxd  rcx, dword ptr [rcx+78h]
0x18002825f  mov     rax, [rbx+60h]
0x180028263  movsxd  rcx, dword ptr [rax+rcx*4]
0x180028267  imul    rbp, rcx, 58h ; 'X'
0x18002826b  add     rbp, r10
0x18002826e  cmp     [rbx+8Ch], r12d
0x180028275  jz      short loc_180028289
0x180028277  mov     rcx, [rbx+8]; hWnd
0x18002827b  call    cs:__imp_GetParent
0x180028281  mov     rcx, rax
0x180028284  mov     r10, [rdi]
0x180028287  jmp     short loc_18002828C
0x180028289  mov     rcx, r12
0x18002828c  cmp     [rbx+8Ch], r12d
0x180028293  jz      short loc_18002829E
0x180028295  mov     rax, [rbx+90h]
0x18002829c  jmp     short loc_1800282A1
0x18002829e  mov     rax, r12
0x1800282a1  lea     r9, [rbp+1Ch]; struct _GUID *
0x1800282a5  mov     [rsp+78h+var_40], rcx; HWND
0x1800282aa  mov     [rsp+78h+var_48], rax; struct ISusInternal **
0x1800282af  mov     [rsp+78h+var_50], r12d; int
0x1800282b4  mov     [rsp+78h+var_58], 1; int
0x1800282bc  mov     r8, [rbx+50h]; struct IUpdateCollection *
0x1800282c0  mov     edx, [rdi+8]; int
0x1800282c3  mov     rcx, r10; struct SimpleUpdateInfo *
0x1800282c6  call    ?SetSimpleUpdateEulaAcceptance@@YAXPEAUSimpleUpdateInfo@@JPEAUIUpdateCollection@@AEBU_GUID@@HHPEAPEAUISusInternal@@PEAUHWND__@@@Z; SetSimpleUpdateEulaAcceptance(SimpleUpdateInfo *,long,IUpdateCollection *,_GUID const &,int,int,ISusInternal * *,HWND__ *)
0x1800282cb  mov     edi, 1
0x1800282d0  mov     rcx, [rbx+8]; hWnd
0x1800282d4  call    cs:__imp_GetParent
0x1800282da  mov     rcx, rax; this
0x1800282dd  movzx   eax, si
0x1800282e0  shl     eax, 10h
0x1800282e3  movsxd  r8, eax
0x1800282e6  mov     eax, edi
0x1800282e8  or      r8, rax
0x1800282eb  mov     edx, r14d
0x1800282ee  jmp     loc_18002822E
0x1800282f3  cmp     qword ptr [r9+8], 0FB97h
0x1800282fb  jnz     loc_18002824D
0x180028301  cmp     dword ptr [r9+10h], 0FFFFFFFEh
0x180028306  jz      short loc_180028313
0x180028308  cmp     dword ptr [r9+10h], 0FFFFFFFCh
0x18002830d  jnz     loc_18002824D
0x180028313  call    ?OnPrintableVersionInternal@CEulaDialog@CInstallationWizard@@AEAAJXZ; CInstallationWizard::CEulaDialog::OnPrintableVersionInternal(void)
0x180028318  test    eax, eax
0x18002831a  jns     short loc_18002836A
0x18002831c  mov     rcx, [rsp+78h]; this
0x180028321  mov     r9d, eax; char *
0x180028324  lea     r8, aCW1SSrcClientC_48; "C:\\__w\\1\\s\\src\\Client\\comapi\\ins"...
0x18002832b  mov     edx, 231h; void *
0x180028330  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028335  jmp     short loc_18002836A
0x180028337  mov     rcx, [rcx+70h]; lpMem
0x18002833b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180028340  mov     [rbx+70h], r12
0x180028344  mov     rcx, [rbx+80h]; ho
0x18002834b  test    rcx, rcx
0x18002834e  jz      short loc_180028356
0x180028350  call    cs:__imp_DeleteObject
0x180028356  mov     [rbx+80h], r12
0x18002835d  mov     rcx, [rbx+60h]; Block
0x180028361  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028366  mov     [rbx+60h], r12
0x18002836a  mov     eax, 1
0x18002836f  mov     rcx, [rsp+78h+var_30]
0x180028374  xor     rcx, rsp; StackCookie
0x180028377  call    __security_check_cookie
0x18002837c  lea     r11, [rsp+78h+var_28]
0x180028381  mov     rbx, [r11+38h]
0x180028385  mov     rbp, [r11+48h]
0x180028389  mov     rsp, r11
0x18002838c  pop     r15
0x18002838e  pop     r14
0x180028390  pop     r12
0x180028392  pop     rdi
0x180028393  pop     rsi
0x180028394  retn
```
