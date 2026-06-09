# CUserAccountWizardBase::_GetPage(WIZPAGE,CWizardPageBase * *)

- ea: `0x180012c70`
- end: `0x180012ed2`
- name: `?_GetPage@CUserAccountWizardBase@@AEAAJUWIZPAGE@@PEAPEAVCWizardPageBase@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(__int64, __int128 *, DirectUI::TaskPage **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012388`
- `0x18001279c`

## callees

- `0x180002ae4`
- `0x180012c70`
- `0x18007728a`
- `0x180078010`

## import_xrefs

- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012cf2`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012d3d`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012d9e`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012de2`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012e4a`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012cf2`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012d3d`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012d9e`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012de2`
- `DUI70!??0TaskPage@DirectUI@@QEAA@XZ` at `0x180012e4a`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x180012e9c`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x180012e9c`

## pseudocode

```c
__int64 __fastcall CUserAccountWizardBase::_GetPage(__int64 a1, __int128 *a2, DirectUI::TaskPage **a3)
{
  int v3; // r9d
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  int v10; // r9d
  signed int v11; // edi
  DirectUI::TaskPage *v12; // rax
  DirectUI::TaskPage *v13; // rbx
  DirectUI::TaskPage *v14; // rax
  DirectUI::TaskPage *v15; // rax
  DirectUI::TaskPage *v16; // rax
  DirectUI::TaskPage *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int128 v21[3]; // [rsp+30h] [rbp-38h] BYREF

  v3 = *((_DWORD *)a2 + 1);
  *a3 = 0;
  v7 = v3 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
            return (unsigned int)-2147467259;
          v12 = (DirectUI::TaskPage *)operator new(0x690u, (const struct std::nothrow_t *)&std::nothrow);
          v13 = v12;
          if ( v12 )
          {
            memset_0(v12, 0, 0x690u);
            DirectUI::TaskPage::TaskPage(v13);
            *(_QWORD *)v13 = &CCurrentPasswordEntryPage::`vftable'{for `DirectUI::IElementListener'};
LABEL_15:
            *((_QWORD *)v13 + 1) = &CInfoPage::`vftable'{for `DirectUI::IXProviderCP'};
            goto LABEL_17;
          }
        }
        else
        {
          v14 = (DirectUI::TaskPage *)operator new(0xAA0u, (const struct std::nothrow_t *)&std::nothrow);
          v13 = v14;
          if ( v14 )
          {
            memset_0(v14, 0, 0xAA0u);
            DirectUI::TaskPage::TaskPage(v13);
            *((_QWORD *)v13 + 209) = 0;
            *(_QWORD *)v13 = &CAccountGroupPage::`vftable'{for `DirectUI::IElementListener'};
            *((_QWORD *)v13 + 1) = &CInfoPage::`vftable'{for `DirectUI::IXProviderCP'};
            *((_QWORD *)v13 + 210) = 0;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v15 = (DirectUI::TaskPage *)operator new(0x6B8u, (const struct std::nothrow_t *)&std::nothrow);
        v13 = v15;
        if ( v15 )
        {
          memset_0(v15, 0, 0x6B8u);
          DirectUI::TaskPage::TaskPage(v13);
          *(_QWORD *)v13 = &CAccountInfoEntryPage::`vftable'{for `DirectUI::IElementListener'};
          goto LABEL_15;
        }
      }
    }
    else
    {
      v16 = (DirectUI::TaskPage *)operator new(0x688u, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v16;
      if ( v16 )
      {
        memset_0(v16, 0, 0x688u);
        DirectUI::TaskPage::TaskPage(v13);
        *(_QWORD *)v13 = &CInfoPage::`vftable'{for `DirectUI::IElementListener'};
        goto LABEL_15;
      }
    }
    v13 = 0;
LABEL_17:
    v11 = v13 == 0 ? 0x8007000E : 0;
    if ( !v13 )
      return (unsigned int)v11;
    goto LABEL_21;
  }
  v17 = (DirectUI::TaskPage *)operator new(0x688u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v17;
  if ( !v17 )
    return (unsigned int)-2147024882;
  memset_0(v17, 0, 0x688u);
  DirectUI::TaskPage::TaskPage(v13);
  *(_QWORD *)v13 = &CFinishPageAero::`vftable'{for `DirectUI::IElementListener'};
  *((_QWORD *)v13 + 1) = &CInfoPage::`vftable'{for `DirectUI::IXProviderCP'};
LABEL_21:
  v18 = *(_QWORD *)v13;
  v19 = *(_QWORD *)(a1 + 104);
  v21[0] = *a2;
  v11 = (*(__int64 (__fastcall **)(DirectUI::TaskPage *, __int64, __int128 *, __int64))(v18 + 168))(v13, v19, v21, a1);
  if ( v11 < 0 )
  {
    (*(void (__fastcall **)(DirectUI::TaskPage *, __int64))(*(_QWORD *)v13 + 48LL))(v13, 1);
  }
  else
  {
    v11 = DirectUI::TaskPage::DUICreatePropertySheetPage(v13, g_hinst);
    if ( v11 >= 0 )
      *a3 = v13;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180012c70  push    rbx
0x180012c72  push    rbp
0x180012c73  push    rsi
0x180012c74  push    rdi
0x180012c75  push    r14
0x180012c77  sub     rsp, 40h
0x180012c7b  mov     r9d, [rdx+4]
0x180012c7f  mov     r14, r8
0x180012c82  mov     qword ptr [r8], 0
0x180012c89  mov     rsi, rdx
0x180012c8c  mov     rbp, rcx
0x180012c8f  sub     r9d, 1
0x180012c93  jz      loc_180012E1B
0x180012c99  sub     r9d, 1
0x180012c9d  jz      loc_180012DB7
0x180012ca3  sub     r9d, 1
0x180012ca7  jz      loc_180012D73
0x180012cad  sub     r9d, 1
0x180012cb1  jz      short loc_180012D0E
0x180012cb3  cmp     r9d, 1
0x180012cb7  jz      short loc_180012CC3
0x180012cb9  mov     edi, 80004005h
0x180012cbe  jmp     loc_180012EC5
0x180012cc3  mov     edi, 690h
0x180012cc8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012ccf  mov     ecx, edi; unsigned __int64
0x180012cd1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012cd6  mov     rbx, rax
0x180012cd9  test    rax, rax
0x180012cdc  jz      loc_180012DFF
0x180012ce2  mov     r8d, edi; Size
0x180012ce5  xor     edx, edx; Val
0x180012ce7  mov     rcx, rax; void *
0x180012cea  call    memset_0
0x180012cef  mov     rcx, rbx
0x180012cf2  call    cs:__imp_??0TaskPage@DirectUI@@QEAA@XZ; DirectUI::TaskPage::TaskPage(void)
0x180012cf8  lea     rax, ??_7CCurrentPasswordEntryPage@@6BIElementListener@DirectUI@@@; const CCurrentPasswordEntryPage::`vftable'{for `DirectUI::IElementListener'}
0x180012cff  mov     [rbx], rax
0x180012d02  lea     rax, ??_7CInfoPage@@6BIXProviderCP@DirectUI@@@; const CInfoPage::`vftable'{for `DirectUI::IXProviderCP'}
0x180012d09  jmp     loc_180012DF9
0x180012d0e  mov     edi, 0AA0h
0x180012d13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012d1a  mov     ecx, edi; unsigned __int64
0x180012d1c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012d21  mov     rbx, rax
0x180012d24  test    rax, rax
0x180012d27  jz      loc_180012DFF
0x180012d2d  mov     r8d, edi; Size
0x180012d30  xor     edx, edx; Val
0x180012d32  mov     rcx, rax; void *
0x180012d35  call    memset_0
0x180012d3a  mov     rcx, rbx
0x180012d3d  call    cs:__imp_??0TaskPage@DirectUI@@QEAA@XZ; DirectUI::TaskPage::TaskPage(void)
0x180012d43  lea     rax, ??_7CAccountGroupPage@@6BIElementListener@DirectUI@@@; const CAccountGroupPage::`vftable'{for `DirectUI::IElementListener'}
0x180012d4a  mov     qword ptr [rbx+688h], 0
0x180012d55  mov     [rbx], rax
0x180012d58  lea     rax, ??_7CInfoPage@@6BIXProviderCP@DirectUI@@@; const CInfoPage::`vftable'{for `DirectUI::IXProviderCP'}
0x180012d5f  mov     [rbx+8], rax
0x180012d63  mov     qword ptr [rbx+690h], 0
0x180012d6e  jmp     loc_180012E01
0x180012d73  mov     edi, 6B8h
0x180012d78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012d7f  mov     ecx, edi; unsigned __int64
0x180012d81  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012d86  mov     rbx, rax
0x180012d89  test    rax, rax
0x180012d8c  jz      short loc_180012DFF
0x180012d8e  mov     r8d, edi; Size
0x180012d91  xor     edx, edx; Val
0x180012d93  mov     rcx, rax; void *
0x180012d96  call    memset_0
0x180012d9b  mov     rcx, rbx
0x180012d9e  call    cs:__imp_??0TaskPage@DirectUI@@QEAA@XZ; DirectUI::TaskPage::TaskPage(void)
0x180012da4  lea     rax, ??_7CAccountInfoEntryPage@@6BIElementListener@DirectUI@@@; const CAccountInfoEntryPage::`vftable'{for `DirectUI::IElementListener'}
0x180012dab  mov     [rbx], rax
0x180012dae  lea     rax, ??_7CInfoPage@@6BIXProviderCP@DirectUI@@@; const CInfoPage::`vftable'{for `DirectUI::IXProviderCP'}
0x180012db5  jmp     short loc_180012DF9
0x180012db7  mov     edi, 688h
0x180012dbc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012dc3  mov     ecx, edi; unsigned __int64
0x180012dc5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012dca  mov     rbx, rax
0x180012dcd  test    rax, rax
0x180012dd0  jz      short loc_180012DFF
0x180012dd2  mov     r8d, edi; Size
0x180012dd5  xor     edx, edx; Val
0x180012dd7  mov     rcx, rax; void *
0x180012dda  call    memset_0
0x180012ddf  mov     rcx, rbx
0x180012de2  call    cs:__imp_??0TaskPage@DirectUI@@QEAA@XZ; DirectUI::TaskPage::TaskPage(void)
0x180012de8  lea     rax, ??_7CInfoPage@@6BIElementListener@DirectUI@@@; const CInfoPage::`vftable'{for `DirectUI::IElementListener'}
0x180012def  mov     [rbx], rax
0x180012df2  lea     rax, ??_7CInfoPage@@6BIXProviderCP@DirectUI@@@; const CInfoPage::`vftable'{for `DirectUI::IXProviderCP'}
0x180012df9  mov     [rbx+8], rax
0x180012dfd  jmp     short loc_180012E01
0x180012dff  xor     ebx, ebx
0x180012e01  mov     rax, rbx
0x180012e04  neg     rax
0x180012e07  sbb     edi, edi
0x180012e09  not     edi
0x180012e0b  and     edi, 8007000Eh
0x180012e11  test    edi, edi
0x180012e13  js      loc_180012EC5
0x180012e19  jmp     short loc_180012E65
0x180012e1b  mov     edi, 688h
0x180012e20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012e27  mov     ecx, edi; unsigned __int64
0x180012e29  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012e2e  mov     rbx, rax
0x180012e31  test    rax, rax
0x180012e34  jz      loc_180012EC0
0x180012e3a  mov     r8d, edi; Size
0x180012e3d  xor     edx, edx; Val
0x180012e3f  mov     rcx, rax; void *
0x180012e42  call    memset_0
0x180012e47  mov     rcx, rbx
0x180012e4a  call    cs:__imp_??0TaskPage@DirectUI@@QEAA@XZ; DirectUI::TaskPage::TaskPage(void)
0x180012e50  lea     rax, ??_7CFinishPageAero@@6BIElementListener@DirectUI@@@; const CFinishPageAero::`vftable'{for `DirectUI::IElementListener'}
0x180012e57  mov     [rbx], rax
0x180012e5a  lea     rax, ??_7CInfoPage@@6BIXProviderCP@DirectUI@@@; const CInfoPage::`vftable'{for `DirectUI::IXProviderCP'}
0x180012e61  mov     [rbx+8], rax
0x180012e65  mov     rax, [rbx]
0x180012e68  lea     r8, [rsp+68h+var_38]
0x180012e6d  movaps  xmm0, xmmword ptr [rsi]
0x180012e70  mov     r9, rbp
0x180012e73  mov     rdx, [rbp+68h]
0x180012e77  mov     rcx, rbx
0x180012e7a  movdqa  [rsp+68h+var_38], xmm0
0x180012e80  mov     rax, [rax+0A8h]
0x180012e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e8c  mov     edi, eax
0x180012e8e  mov     rcx, rbx
0x180012e91  test    eax, eax
0x180012e93  js      short loc_180012EAD
0x180012e95  mov     rdx, cs:g_hinst
0x180012e9c  call    cs:__imp_?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z; DirectUI::TaskPage::DUICreatePropertySheetPage(HINSTANCE__ *)
0x180012ea2  mov     edi, eax
0x180012ea4  test    eax, eax
0x180012ea6  js      short loc_180012EC5
0x180012ea8  mov     [r14], rbx
0x180012eab  jmp     short loc_180012EC5
0x180012ead  mov     rax, [rbx]
0x180012eb0  mov     edx, 1
0x180012eb5  mov     rax, [rax+30h]
0x180012eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ebe  jmp     short loc_180012EC5
0x180012ec0  mov     edi, 8007000Eh
0x180012ec5  mov     eax, edi
0x180012ec7  add     rsp, 40h
0x180012ecb  pop     r14
0x180012ecd  pop     rdi
0x180012ece  pop     rsi
0x180012ecf  pop     rbp
0x180012ed0  pop     rbx
0x180012ed1  retn
```
