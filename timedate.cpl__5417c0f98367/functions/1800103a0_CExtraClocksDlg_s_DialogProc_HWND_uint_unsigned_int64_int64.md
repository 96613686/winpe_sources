# CExtraClocksDlg::s_DialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800103a0`
- end: `0x180010532`
- name: `?s_DialogProc@CExtraClocksDlg@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `402`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001de4`
- `0x180001dfc`
- `0x18000feec`
- `0x1800100c4`
- `0x1800102a4`
- `0x1800103a0`
- `0x18001768c`
- `0x18001b52c`
- `0x18001b5dc`
- `0x18001bf3c`
- `0x180028f2e`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x18001046e`
- `USER32!SetWindowLongPtrW` at `0x1800104fc`
- `USER32!SetWindowLongPtrW` at `0x18001046e`
- `USER32!SetWindowLongPtrW` at `0x1800104fc`
- `USER32!GetWindowLongPtrW` at `0x1800103bd`
- `USER32!GetWindowLongPtrW` at `0x1800103bd`
- `USER32!GetParent` at `0x180010442`
- `USER32!GetParent` at `0x180010442`
- `USER32!EndDialog` at `0x1800104c0`
- `USER32!EndDialog` at `0x1800104c0`

## pseudocode

```c
__int64 __fastcall CExtraClocksDlg::s_DialogProc(HWND a1, int a2, int a3, __int64 a4)
{
  __int64 v5; // rdi
  HWND *WindowLongPtrW; // rax
  HWND *v10; // rsi
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  char *v15; // rbx
  HWND Parent; // rax
  unsigned int *v17; // rdi
  CDateTimeOm *v18; // rcx
  unsigned int v19; // edx

  v5 = 0;
  WindowLongPtrW = (HWND *)GetWindowLongPtrW(a1, -21);
  v10 = WindowLongPtrW;
  v11 = a2 - 2;
  if ( v11 )
  {
    v12 = v11 - 76;
    if ( v12 )
    {
      v13 = v12 - 194;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          if ( v14 == 752 && a3 == 12 )
            AddInternetTab(a1);
        }
        else if ( WindowLongPtrW )
        {
          return CExtraClocksDlg::_OnWmCommand(WindowLongPtrW, HIWORD(a3), (unsigned __int16)a3);
        }
      }
      else
      {
        v15 = (char *)operator new(0x278u);
        if ( v15 )
        {
          Parent = GetParent(a1);
          *((_QWORD *)v15 + 1) = a1;
          *(_QWORD *)v15 = Parent;
          *((_DWORD *)v15 + 4) = 0;
          memset_0(v15 + 24, 0, 0x260u);
          SetWindowLongPtrW(a1, -21, (LONG_PTR)v15);
          v17 = (unsigned int *)(v15 + 16);
          if ( (int)CDateTimeOm::Advise(g_pom, a1, 0x401u, (unsigned int *)v15 + 4) >= 0
            && (int)CDateTimeOm::AddInternetPageAsync(v18) < 0 )
          {
            CDateTimeOm::UnAdvise(g_pom, *v17);
            *v17 = 0;
          }
          CExtraClocksDlg::_Init((CExtraClocksDlg *)v15, a1);
        }
        else
        {
          EndDialog(a1, 0);
        }
        return 1;
      }
    }
    else if ( WindowLongPtrW && !*(_QWORD *)(a4 + 8) && *(_DWORD *)(a4 + 16) == -202 )
    {
      LOBYTE(v5) = (unsigned int)CExtraClocksDlg::_OnApply((CExtraClocksDlg *)WindowLongPtrW) == 0;
    }
  }
  else
  {
    SetWindowLongPtrW(a1, -21, 0);
    if ( v10 )
    {
      v19 = *((_DWORD *)v10 + 4);
      if ( v19 )
        CDateTimeOm::UnAdvise(g_pom, v19);
      operator delete(v10);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800103a0  push    rbx
0x1800103a2  push    rbp
0x1800103a3  push    rsi
0x1800103a4  push    rdi
0x1800103a5  push    r14
0x1800103a7  push    r15
0x1800103a9  sub     rsp, 28h
0x1800103ad  mov     ebx, edx
0x1800103af  xor     edi, edi
0x1800103b1  mov     r15, r9
0x1800103b4  mov     r14, r8
0x1800103b7  mov     rbp, rcx
0x1800103ba  lea     edx, [rdi-15h]; nIndex
0x1800103bd  call    cs:__imp_GetWindowLongPtrW
0x1800103c3  mov     rsi, rax
0x1800103c6  sub     ebx, 2
0x1800103c9  jz      loc_1800104F2
0x1800103cf  sub     ebx, 4Ch ; 'L'
0x1800103d2  jz      loc_1800104CD
0x1800103d8  sub     ebx, 0C2h
0x1800103de  jz      short loc_18001042D
0x1800103e0  sub     ebx, 1
0x1800103e3  jz      short loc_180010408
0x1800103e5  cmp     ebx, 2F0h
0x1800103eb  jnz     loc_180010522
0x1800103f1  cmp     r14d, 0Ch
0x1800103f5  jnz     loc_180010522
0x1800103fb  mov     rcx, rbp; hWnd
0x1800103fe  call    ?AddInternetTab@@YAJPEAUHWND__@@@Z; AddInternetTab(HWND__ *)
0x180010403  jmp     loc_180010522
0x180010408  test    rsi, rsi
0x18001040b  jz      loc_180010522
0x180010411  movzx   r8d, r14w; unsigned int
0x180010415  mov     rcx, rsi; this
0x180010418  shr     r14, 10h
0x18001041c  movzx   edx, r14w; unsigned int
0x180010420  call    ?_OnWmCommand@CExtraClocksDlg@@AEAA_JII@Z; CExtraClocksDlg::_OnWmCommand(uint,uint)
0x180010425  mov     rdi, rax
0x180010428  jmp     loc_180010522
0x18001042d  mov     ecx, 278h; Size
0x180010432  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010437  mov     rbx, rax
0x18001043a  mov     rcx, rbp; hDlg
0x18001043d  test    rax, rax
0x180010440  jz      short loc_1800104BE
0x180010442  call    cs:__imp_GetParent
0x180010448  lea     rcx, [rbx+18h]; void *
0x18001044c  mov     [rbx+8], rbp
0x180010450  xor     edx, edx; Val
0x180010452  mov     [rbx], rax
0x180010455  mov     r8d, 260h; Size
0x18001045b  mov     [rbx+10h], edi
0x18001045e  call    memset_0
0x180010463  mov     r8, rbx; dwNewLong
0x180010466  mov     edx, 0FFFFFFEBh; nIndex
0x18001046b  mov     rcx, rbp; hWnd
0x18001046e  call    cs:__imp_SetWindowLongPtrW
0x180010474  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x18001047b  lea     rdi, [rbx+10h]
0x18001047f  mov     r9, rdi; unsigned int *
0x180010482  mov     r8d, 401h; unsigned int
0x180010488  mov     rdx, rbp; HWND
0x18001048b  call    ?Advise@CDateTimeOm@@QEAAJPEAUHWND__@@IPEAK@Z; CDateTimeOm::Advise(HWND__ *,uint,ulong *)
0x180010490  test    eax, eax
0x180010492  js      short loc_1800104B1
0x180010494  call    ?AddInternetPageAsync@CDateTimeOm@@QEAAJXZ; CDateTimeOm::AddInternetPageAsync(void)
0x180010499  test    eax, eax
0x18001049b  jns     short loc_1800104B1
0x18001049d  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x1800104a4  mov     edx, [rdi]; unsigned int
0x1800104a6  call    ?UnAdvise@CDateTimeOm@@QEAAJK@Z; CDateTimeOm::UnAdvise(ulong)
0x1800104ab  mov     dword ptr [rdi], 0
0x1800104b1  mov     rdx, rbp; HWND
0x1800104b4  mov     rcx, rbx; this
0x1800104b7  call    ?_Init@CExtraClocksDlg@@AEAA_JQEAUHWND__@@@Z; CExtraClocksDlg::_Init(HWND__ * const)
0x1800104bc  jmp     short loc_1800104C6
0x1800104be  xor     edx, edx; nResult
0x1800104c0  call    cs:__imp_EndDialog
0x1800104c6  mov     edi, 1
0x1800104cb  jmp     short loc_180010522
0x1800104cd  test    rsi, rsi
0x1800104d0  jz      short loc_180010522
0x1800104d2  cmp     [r15+8], rdi
0x1800104d6  jnz     short loc_180010522
0x1800104d8  cmp     dword ptr [r15+10h], 0FFFFFF36h
0x1800104e0  jnz     short loc_180010522
0x1800104e2  mov     rcx, rsi; this
0x1800104e5  call    ?_OnApply@CExtraClocksDlg@@AEAAHXZ; CExtraClocksDlg::_OnApply(void)
0x1800104ea  test    eax, eax
0x1800104ec  setz    dil
0x1800104f0  jmp     short loc_180010522
0x1800104f2  xor     r8d, r8d; dwNewLong
0x1800104f5  mov     rcx, rbp; hWnd
0x1800104f8  lea     edx, [r8-15h]; nIndex
0x1800104fc  call    cs:__imp_SetWindowLongPtrW
0x180010502  test    rsi, rsi
0x180010505  jz      short loc_180010522
0x180010507  mov     edx, [rsi+10h]; unsigned int
0x18001050a  test    edx, edx
0x18001050c  jz      short loc_18001051A
0x18001050e  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x180010515  call    ?UnAdvise@CDateTimeOm@@QEAAJK@Z; CDateTimeOm::UnAdvise(ulong)
0x18001051a  mov     rcx, rsi; Block
0x18001051d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010522  mov     rax, rdi
0x180010525  add     rsp, 28h
0x180010529  pop     r15
0x18001052b  pop     r14
0x18001052d  pop     rdi
0x18001052e  pop     rsi
0x18001052f  pop     rbp
0x180010530  pop     rbx
0x180010531  retn
```
