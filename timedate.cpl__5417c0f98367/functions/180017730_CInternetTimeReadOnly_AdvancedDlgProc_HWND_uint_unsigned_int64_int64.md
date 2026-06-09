# CInternetTimeReadOnly::AdvancedDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180017730`
- end: `0x1800178a7`
- name: `?AdvancedDlgProc@CInternetTimeReadOnly@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `375`
- prototype: `__int64(CInternetTimeReadOnly *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180017af0`

## callees

- `0x18000c220`
- `0x180014b24`
- `0x180017730`
- `0x1800178b0`
- `0x1800179fc`
- `0x18001b5dc`
- `0x18001b618`
- `0x18001c300`
- `0x18001ca88`
- `0x18001cae4`
- `0x18002a010`

## import_xrefs

- `USER32!EndDialog` at `0x180017847`
- `USER32!EndDialog` at `0x180017847`
- `USER32!GetDlgItem` at `0x180017855`
- `USER32!GetDlgItem` at `0x180017855`
- `USER32!SendMessageW` at `0x18001786c`
- `USER32!SendMessageW` at `0x18001786c`

## pseudocode

```c
__int64 __fastcall CInternetTimeReadOnly::AdvancedDlgProc(
        CInternetTimeReadOnly *this,
        HWND a2,
        int a3,
        int a4,
        unsigned __int16 *a5)
{
  CInternetTimeReadOnly *v5; // rbx
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  CDateTimeOm *v11; // rdi
  CDateTimeOm *v12; // rcx
  unsigned int *v13; // r9
  HWND DlgItem; // rax

  v5 = g_pInternetTimeReadOnly;
  v7 = a3 - 2;
  if ( v7 )
  {
    v8 = v7 - 270;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 != 753 || a4 != 11 )
          return 0;
        CInternetTimeReadOnly::_OnUpdateStatusString(g_pInternetTimeReadOnly, a5);
      }
      else if ( (_WORD)a4 == 827 )
      {
        if ( (unsigned int)CDateTimeOm::get_IsLUAFeatureOn(this)
          || (unsigned int)CDateTimeOm::get_CanModifyInternetTime(g_pom) )
        {
          if ( OpenInternetCfgDlg(a2) )
          {
            v11 = g_pom;
            if ( *((_QWORD *)g_pom + 61) )
            {
              if ( (int)CDateTimeOm::_InitializeInternetTimeOm(g_pom, 0) >= 0
                && (int)CDateTimeOm::CheckInternetTimeStatus(v11) >= 0 )
              {
                CInternetTimeReadOnly::_InitAdvancedPage(v5);
              }
            }
          }
        }
        else
        {
          ShowErrorMessage(a2, 53);
        }
      }
    }
    else
    {
      v12 = g_pom;
      v13 = (unsigned int *)((char *)g_pInternetTimeReadOnly + 32);
      *((_QWORD *)g_pInternetTimeReadOnly + 2) = a2;
      if ( (int)CDateTimeOm::Advise(v12, a2, 0x402u, v13) >= 0 && (int)CInternetTimeReadOnly::_InitAdvancedPage(v5) < 0 )
        EndDialog(a2, -1);
      DlgItem = GetDlgItem(a2, 827);
      SendMessageW(DlgItem, 0x160Cu, 0, 1);
    }
  }
  else if ( g_pInternetTimeReadOnly )
  {
    (**(void (__fastcall ***)(CInternetTimeReadOnly *, __int64))g_pInternetTimeReadOnly)(g_pInternetTimeReadOnly, 1);
    g_pInternetTimeReadOnly = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180017730  mov     [rsp+arg_0], rbx
0x180017735  push    rdi
0x180017736  sub     rsp, 20h
0x18001773a  mov     rbx, cs:?g_pInternetTimeReadOnly@@3PEAVCInternetTimeReadOnly@@EA; CInternetTimeReadOnly * g_pInternetTimeReadOnly
0x180017741  mov     rdi, rdx
0x180017744  sub     r8d, 2
0x180017748  jz      loc_180017874
0x18001774e  sub     r8d, 10Eh
0x180017755  jz      loc_180017816
0x18001775b  sub     r8d, 1
0x18001775f  jz      short loc_180017789
0x180017761  cmp     r8d, 2F1h
0x180017768  jnz     short loc_180017782
0x18001776a  cmp     r9d, 0Bh
0x18001776e  jnz     short loc_180017782
0x180017770  mov     rdx, [rsp+28h+arg_20]; unsigned __int16 *
0x180017775  mov     rcx, rbx; this
0x180017778  call    ?_OnUpdateStatusString@CInternetTimeReadOnly@@AEAAJPEBG@Z; CInternetTimeReadOnly::_OnUpdateStatusString(ushort const *)
0x18001777d  jmp     loc_180017897
0x180017782  xor     eax, eax
0x180017784  jmp     loc_18001789C
0x180017789  mov     edx, 33Bh
0x18001778e  cmp     r9w, dx
0x180017792  jnz     loc_180017897
0x180017798  call    ?get_IsLUAFeatureOn@CDateTimeOm@@QEAAHXZ; CDateTimeOm::get_IsLUAFeatureOn(void)
0x18001779d  test    eax, eax
0x18001779f  jnz     short loc_1800177C1
0x1800177a1  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x1800177a8  call    ?get_CanModifyInternetTime@CDateTimeOm@@QEAAHXZ; CDateTimeOm::get_CanModifyInternetTime(void)
0x1800177ad  test    eax, eax
0x1800177af  jnz     short loc_1800177C1
0x1800177b1  lea     edx, [rax+35h]; int
0x1800177b4  mov     rcx, rdi; HWND
0x1800177b7  call    ?ShowErrorMessage@@YAXPEAUHWND__@@H@Z; ShowErrorMessage(HWND__ *,int)
0x1800177bc  jmp     loc_180017897
0x1800177c1  mov     rcx, rdi; HWND
0x1800177c4  call    ?OpenInternetCfgDlg@@YA_JPEAUHWND__@@@Z; OpenInternetCfgDlg(HWND__ *)
0x1800177c9  test    rax, rax
0x1800177cc  jz      loc_180017897
0x1800177d2  mov     rdi, cs:?g_pom@@3PEAVCDateTimeOm@@EA; CDateTimeOm * g_pom
0x1800177d9  cmp     qword ptr [rdi+1E8h], 0
0x1800177e1  jz      loc_180017897
0x1800177e7  xor     edx, edx; int
0x1800177e9  mov     rcx, rdi; this
0x1800177ec  call    ?_InitializeInternetTimeOm@CDateTimeOm@@AEAAJH@Z; CDateTimeOm::_InitializeInternetTimeOm(int)
0x1800177f1  test    eax, eax
0x1800177f3  js      loc_180017897
0x1800177f9  mov     rcx, rdi; this
0x1800177fc  call    ?CheckInternetTimeStatus@CDateTimeOm@@QEAAJXZ; CDateTimeOm::CheckInternetTimeStatus(void)
0x180017801  test    eax, eax
0x180017803  js      loc_180017897
0x180017809  mov     rcx, rbx; this
0x18001780c  call    ?_InitAdvancedPage@CInternetTimeReadOnly@@AEAAJXZ; CInternetTimeReadOnly::_InitAdvancedPage(void)
0x180017811  jmp     loc_180017897
0x180017816  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x18001781d  lea     r9, [rbx+20h]; unsigned int *
0x180017821  mov     r8d, 402h; unsigned int
0x180017827  mov     [rbx+10h], rdi
0x18001782b  call    ?Advise@CDateTimeOm@@QEAAJPEAUHWND__@@IPEAK@Z; CDateTimeOm::Advise(HWND__ *,uint,ulong *)
0x180017830  test    eax, eax
0x180017832  js      short loc_18001784D
0x180017834  mov     rcx, rbx; this
0x180017837  call    ?_InitAdvancedPage@CInternetTimeReadOnly@@AEAAJXZ; CInternetTimeReadOnly::_InitAdvancedPage(void)
0x18001783c  test    eax, eax
0x18001783e  jns     short loc_18001784D
0x180017840  or      rdx, 0FFFFFFFFFFFFFFFFh; nResult
0x180017844  mov     rcx, rdi; hDlg
0x180017847  call    cs:__imp_EndDialog
0x18001784d  mov     edx, 33Bh; nIDDlgItem
0x180017852  mov     rcx, rdi; hDlg
0x180017855  call    cs:__imp_GetDlgItem
0x18001785b  mov     r9d, 1; lParam
0x180017861  xor     r8d, r8d; wParam
0x180017864  mov     rcx, rax; hWnd
0x180017867  mov     edx, 160Ch; Msg
0x18001786c  call    cs:__imp_SendMessageW
0x180017872  jmp     short loc_180017897
0x180017874  test    rbx, rbx
0x180017877  jz      short loc_180017897
0x180017879  mov     rcx, [rbx]
0x18001787c  mov     edx, 1
0x180017881  mov     rax, [rcx]
0x180017884  mov     rcx, rbx
0x180017887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001788c  mov     cs:?g_pInternetTimeReadOnly@@3PEAVCInternetTimeReadOnly@@EA, 0; CInternetTimeReadOnly * g_pInternetTimeReadOnly
0x180017897  mov     eax, 1
0x18001789c  mov     rbx, [rsp+28h+arg_0]
0x1800178a1  add     rsp, 20h
0x1800178a5  pop     rdi
0x1800178a6  retn
```
