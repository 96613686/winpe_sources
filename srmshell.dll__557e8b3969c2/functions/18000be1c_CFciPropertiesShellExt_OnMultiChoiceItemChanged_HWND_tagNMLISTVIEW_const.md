# CFciPropertiesShellExt::OnMultiChoiceItemChanged(HWND__ *,tagNMLISTVIEW const *)

- ea: `0x18000be1c`
- end: `0x18000c2c4`
- name: `?OnMultiChoiceItemChanged@CFciPropertiesShellExt@@AEAA_JPEAUHWND__@@PEBUtagNMLISTVIEW@@@Z`
- size: `1192`
- prototype: `__int64 __fastcall(CFciPropertiesShellExt *this, HWND, const struct tagNMLISTVIEW *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180007290`

## callees

- `0x180005e50`
- `0x180009090`
- `0x18000be1c`
- `0x18000fa8c`
- `0x18000ff54`
- `0x180010360`
- `0x1800103a8`
- `0x1800106fc`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c0b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c189`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c1ab`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c267`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c289`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c0b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c189`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c1ab`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c267`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c289`
- `msvcrt!_wcsicmp` at `0x18000c050`
- `msvcrt!_wcsicmp` at `0x18000c050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c29e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c29e`
- `USER32!SendMessageW` at `0x18000be96`
- `USER32!SendMessageW` at `0x18000bef5`
- `USER32!SendMessageW` at `0x18000bfca`
- `USER32!SendMessageW` at `0x18000be96`
- `USER32!SendMessageW` at `0x18000bef5`
- `USER32!SendMessageW` at `0x18000bfca`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::OnMultiChoiceItemChanged(
        CFciPropertiesShellExt *this,
        HWND a2,
        const struct tagNMLISTVIEW *a3)
{
  unsigned int v4; // r15d
  struct CFciPropertiesShellExt::PropertyInfo *SelectedProperty; // rax
  struct CFciPropertiesShellExt::PropertyInfo *v6; // rdi
  unsigned int v7; // r14d
  HWND hwndFrom; // r13
  LRESULT v9; // rax
  int v10; // esi
  char v11; // bl
  char *v12; // r12
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rdx
  void **p_Src; // rax
  void **v17; // rcx
  unsigned __int64 v18; // r8
  char *v19; // rdx
  unsigned __int64 v20; // r8
  __int64 *i; // rbx
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  void **v24; // rcx
  unsigned __int64 v25; // r8
  const void **v26; // r9
  _WORD *v27; // rcx
  _WORD *v28; // rcx
  unsigned __int64 v29; // r11
  unsigned __int64 v30; // r10
  void **v31; // r8
  void **v33; // rdx
  __int64 v34; // rax
  unsigned __int64 v35; // r8
  unsigned __int64 v36; // r8
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  LRESULT v38; // [rsp+28h] [rbp-D8h]
  HWND v39; // [rsp+30h] [rbp-D0h]
  CFciPropertiesShellExt *v40; // [rsp+38h] [rbp-C8h]
  LPARAM lParam[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+60h] [rbp-A0h]
  void **Src; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v45; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v46; // [rsp+B8h] [rbp-48h]
  void *v47[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v49; // [rsp+E0h] [rbp-20h]
  wchar_t *String1[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+100h] [rbp+0h]
  unsigned __int64 v52; // [rsp+108h] [rbp+8h]

  v39 = a2;
  v40 = this;
  v4 = 0;
  if ( *((_BYTE *)this + 217) )
    return 0;
  SelectedProperty = CFciPropertiesShellExt::GetSelectedProperty(a2);
  v6 = SelectedProperty;
  if ( !SelectedProperty )
    return 0;
  v7 = 2;
  if ( *((_DWORD *)SelectedProperty + 20) != 2 )
    return 0;
  hwndFrom = a3->hdr.hwndFrom;
  v9 = SendMessageW(a3->hdr.hwndFrom, 0x1004u, 0, 0);
  v10 = v9;
  v38 = v9;
  pv = 0;
  v46 = 7;
  v45 = 0;
  LOWORD(Src) = 0;
  v49 = 7;
  v48 = 0;
  LOWORD(v47[0]) = 0;
  v11 = 0;
  CSrmAutoPWSZ::Allocate(&pv);
  v12 = (char *)pv;
  if ( v10 > 0 )
  {
    while ( (SendMessageW(hwndFrom, 0x102Cu, v4, 61440) & 0xFFFFF000) == 0x1000 )
    {
LABEL_42:
      if ( (int)++v4 >= (int)v38 )
        goto LABEL_43;
    }
    if ( v11 )
    {
      v13 = v45;
      if ( v45 == -1 || v45 == -2 )
        std::wstring::_Xlen();
      v14 = v45 + 1;
      if ( v45 + 1 > 0x7FFFFFFFFFFFFFFELL )
        std::wstring::_Xlen();
      v15 = v46;
      if ( v46 < v14 )
      {
        std::wstring::_Copy((const void **)&Src, v45 + 1, v45);
        v15 = v46;
        v13 = v45;
        if ( !v14 )
          goto LABEL_16;
        goto LABEL_11;
      }
      if ( v45 != -1 )
      {
LABEL_11:
        p_Src = (void **)&Src;
        if ( v15 >= 8 )
          p_Src = Src;
        *((_WORD *)p_Src + v13) = 124;
        v17 = (void **)&Src;
        if ( v46 >= 8 )
          v17 = Src;
        v45 = v14;
        *((_WORD *)v17 + v14) = 0;
        goto LABEL_16;
      }
      v24 = (void **)&Src;
      if ( v46 >= 8 )
        v24 = Src;
      v45 = 0;
      *(_WORD *)v24 = 0;
    }
LABEL_16:
    *(_WORD *)v12 = 0;
    memset_0(lParam, 0, 0x58u);
    v42 = 1001;
    lParam[3] = (LPARAM)v12;
    SendMessageW(hwndFrom, 0x1073u, v4, (LPARAM)lParam);
    v52 = 7;
    v51 = 0;
    LOWORD(String1[0]) = 0;
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)&v12[2 * v18] );
    std::wstring::assign(String1, v12, v18);
    v19 = (char *)String1;
    if ( v52 >= 8 )
      v19 = (char *)String1[0];
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&v19[2 * v20] );
    std::wstring::assign(v47, v19, v20);
    for ( i = (__int64 *)*((_QWORD *)v6 + 17); i != *((__int64 **)v6 + 18); i += 15 )
    {
      v22 = (const wchar_t *)(i + 5);
      if ( (unsigned __int64)i[8] >= 8 )
        v22 = *(const wchar_t **)v22;
      v23 = (const wchar_t *)String1;
      if ( v52 >= 8 )
        v23 = String1[0];
      if ( !_wcsicmp(v23, v22) )
      {
        if ( (unsigned __int64)i[3] >= 8 )
          i = (__int64 *)*i;
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)i + v25) );
        std::wstring::assign(v47, (char *)i, v25);
        break;
      }
    }
    if ( v52 >= 8 )
      operator delete(String1[0]);
    v52 = 7;
    v51 = 0;
    LOWORD(String1[0]) = 0;
    std::wstring::append(&Src, v47, 0, -1);
    v11 = 1;
    goto LABEL_42;
  }
LABEL_43:
  v26 = (const void **)((char *)v6 + 168);
  if ( v45 )
  {
    if ( *((_QWORD *)v6 + 24) < 8u )
      v28 = (_WORD *)((char *)v6 + 168);
    else
      v28 = *v26;
    v29 = *((_QWORD *)v6 + 23);
    v30 = v45;
    if ( v45 >= v29 )
      v30 = *((_QWORD *)v6 + 23);
    v31 = (void **)&Src;
    if ( v46 >= 8 )
      v31 = Src;
    if ( v30 )
    {
      while ( *(_WORD *)v31 == *v28 )
      {
        v31 = (void **)((char *)v31 + 2);
        ++v28;
        if ( !--v30 )
          goto LABEL_58;
      }
      goto LABEL_65;
    }
LABEL_58:
    if ( v45 != v29 )
    {
LABEL_65:
      if ( v26 != (const void **)&Src )
      {
        v33 = (void **)*v26;
        v34 = *((_QWORD *)v6 + 22);
        *v26 = Src;
        *((_QWORD *)v6 + 22) = v44;
        Src = v33;
        v44 = v34;
        v35 = *((_QWORD *)v6 + 23);
        *((_QWORD *)v6 + 23) = v45;
        v45 = v35;
        v36 = *((_QWORD *)v6 + 24);
        *((_QWORD *)v6 + 24) = v46;
        v46 = v36;
      }
      *((_DWORD *)v6 + 52) = 3;
      goto LABEL_68;
    }
    if ( v49 >= 8 )
      operator delete(v47[0]);
    v49 = 7;
    v48 = 0;
    LOWORD(v47[0]) = 0;
    if ( v46 >= 8 )
      operator delete(Src);
    v46 = 7;
    v45 = 0;
    LOWORD(Src) = 0;
    CoTaskMemFree(v12);
    pv = 0;
    return 0;
  }
  v7 = 1;
  *((_DWORD *)v6 + 52) = 4;
  if ( *((_QWORD *)v6 + 24) < 8u )
    v27 = (_WORD *)((char *)v6 + 168);
  else
    v27 = *v26;
  *((_QWORD *)v6 + 23) = 0;
  *v27 = 0;
LABEL_68:
  CFciPropertiesShellExt::UpdatePage(v40, v39, v6, v7);
  if ( v49 >= 8 )
    operator delete(v47[0]);
  v49 = 7;
  v48 = 0;
  LOWORD(v47[0]) = 0;
  if ( v46 >= 8 )
    operator delete(Src);
  v46 = 7;
  v45 = 0;
  LOWORD(Src) = 0;
  CoTaskMemFree(v12);
  pv = 0;
  return 1;
}

```

## disassembly

```asm
0x18000be1c  mov     [rsp-8+arg_18], rbx
0x18000be21  push    rbp
0x18000be22  push    rsi
0x18000be23  push    rdi
0x18000be24  push    r12
0x18000be26  push    r13
0x18000be28  push    r14
0x18000be2a  push    r15
0x18000be2c  lea     rbp, [rsp-20h]
0x18000be31  sub     rsp, 120h
0x18000be38  mov     rax, cs:__security_cookie
0x18000be3f  xor     rax, rsp
0x18000be42  mov     [rbp+50h+var_38], rax
0x18000be46  mov     rbx, r8
0x18000be49  mov     [rsp+150h+var_120], rdx
0x18000be4e  mov     [rsp+150h+var_118], rcx
0x18000be53  xor     r15d, r15d
0x18000be56  cmp     [rcx+0D9h], r15b
0x18000be5d  jnz     loc_18000C1D0
0x18000be63  mov     rcx, rdx; HWND
0x18000be66  call    ?GetSelectedProperty@CFciPropertiesShellExt@@CAPEAUPropertyInfo@1@PEAUHWND__@@@Z; CFciPropertiesShellExt::GetSelectedProperty(HWND__ *)
0x18000be6b  mov     rdi, rax
0x18000be6e  test    rax, rax
0x18000be71  jz      loc_18000C1D0
0x18000be77  lea     r14d, [r15+2]
0x18000be7b  cmp     [rax+50h], r14d
0x18000be7f  jnz     loc_18000C1D0
0x18000be85  mov     r13, [rbx]
0x18000be88  xor     r9d, r9d; lParam
0x18000be8b  xor     r8d, r8d; wParam
0x18000be8e  mov     edx, 1004h; Msg
0x18000be93  mov     rcx, r13; hWnd
0x18000be96  call    cs:__imp_SendMessageW
0x18000be9c  mov     rsi, rax
0x18000be9f  mov     [rsp+150h+var_128], rax
0x18000bea4  mov     [rsp+150h+pv], r15
0x18000bea9  lea     eax, [r15+7]
0x18000bead  mov     [rbp+50h+var_98], rax
0x18000beb1  mov     [rbp+50h+var_A0], r15
0x18000beb5  mov     word ptr [rbp+50h+Src], r15w
0x18000beba  mov     [rbp+50h+var_70], rax
0x18000bebe  mov     [rbp+50h+var_78], r15
0x18000bec2  mov     word ptr [rbp+50h+var_88], r15w
0x18000bec7  mov     bl, r15b
0x18000beca  lea     rcx, [rsp+150h+pv]; this
0x18000becf  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18000bed4  mov     r12, [rsp+150h+pv]
0x18000bed9  test    esi, esi
0x18000bedb  jle     loc_18000C0ED
0x18000bee1  mov     esi, r15d
0x18000bee4  mov     r9d, 0F000h; lParam
0x18000beea  mov     r8d, r15d; wParam
0x18000beed  mov     edx, 102Ch; Msg
0x18000bef2  mov     rcx, r13; hWnd
0x18000bef5  call    cs:__imp_SendMessageW
0x18000befb  and     eax, 0FFFFF000h
0x18000bf00  cmp     eax, 1000h
0x18000bf05  jz      loc_18000C0DF
0x18000bf0b  xor     r8d, r8d
0x18000bf0e  test    bl, bl
0x18000bf10  jz      loc_18000BF98
0x18000bf16  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bf1a  mov     rcx, [rbp+50h+var_A0]
0x18000bf1e  sub     rax, rcx
0x18000bf21  cmp     rax, 1
0x18000bf25  jbe     loc_18000C2B8
0x18000bf2b  lea     rbx, [rcx+1]
0x18000bf2f  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000bf39  cmp     rbx, rax
0x18000bf3c  ja      loc_18000C2BE
0x18000bf42  mov     rdx, [rbp+50h+var_98]
0x18000bf46  cmp     rdx, rbx
0x18000bf49  jnb     loc_18000C060
0x18000bf4f  mov     r8, rcx
0x18000bf52  mov     rdx, rbx
0x18000bf55  lea     rcx, [rbp+50h+Src]; Src
0x18000bf59  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000bf5e  mov     rdx, [rbp+50h+var_98]
0x18000bf62  mov     rcx, [rbp+50h+var_A0]
0x18000bf66  xor     r8d, r8d
0x18000bf69  test    rbx, rbx
0x18000bf6c  jz      short loc_18000BF98
0x18000bf6e  lea     rax, [rbp+50h+Src]
0x18000bf72  cmp     rdx, 8
0x18000bf76  cmovnb  rax, [rbp+50h+Src]
0x18000bf7b  mov     word ptr [rax+rcx*2], 7Ch ; '|'
0x18000bf81  lea     rcx, [rbp+50h+Src]
0x18000bf85  cmp     [rbp+50h+var_98], 8
0x18000bf8a  cmovnb  rcx, [rbp+50h+Src]
0x18000bf8f  mov     [rbp+50h+var_A0], rbx
0x18000bf93  mov     [rcx+rbx*2], r8w
0x18000bf98  mov     [r12], r8w
0x18000bf9d  xor     edx, edx; Val
0x18000bf9f  lea     r8d, [rdx+58h]; Size
0x18000bfa3  lea     rcx, [rsp+150h+lParam]; void *
0x18000bfa8  call    memset_0
0x18000bfad  mov     [rsp+150h+var_F0], 3E9h
0x18000bfb5  mov     [rsp+150h+var_F8], r12
0x18000bfba  lea     r9, [rsp+150h+lParam]; lParam
0x18000bfbf  mov     r8, rsi; wParam
0x18000bfc2  mov     edx, 1073h; Msg
0x18000bfc7  mov     rcx, r13; hWnd
0x18000bfca  call    cs:__imp_SendMessageW
0x18000bfd0  mov     [rbp+50h+var_48], 7
0x18000bfd8  xor     esi, esi
0x18000bfda  mov     [rbp+50h+var_50], rsi
0x18000bfde  mov     word ptr [rbp+50h+String1], si
0x18000bfe2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bfe6  mov     r8, rbx
0x18000bfe9  inc     r8
0x18000bfec  cmp     [r12+r8*2], si
0x18000bff1  jnz     short loc_18000BFE9
0x18000bff3  mov     rdx, r12; void *
0x18000bff6  lea     rcx, [rbp+50h+String1]; Src
0x18000bffa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000bfff  nop
0x18000c000  lea     rdx, [rbp+50h+String1]
0x18000c004  cmp     [rbp+50h+var_48], 8
0x18000c009  cmovnb  rdx, [rbp+50h+String1]; void *
0x18000c00e  mov     r8, rbx
0x18000c011  inc     r8
0x18000c014  cmp     [rdx+r8*2], si
0x18000c019  jnz     short loc_18000C011
0x18000c01b  lea     rcx, [rbp+50h+var_88]; Src
0x18000c01f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000c024  mov     rbx, [rdi+88h]
0x18000c02b  cmp     rbx, [rdi+90h]
0x18000c032  jz      short loc_18000C0A8
0x18000c034  lea     rdx, [rbx+28h]
0x18000c038  cmp     qword ptr [rdx+18h], 8
0x18000c03d  jb      short loc_18000C042
0x18000c03f  mov     rdx, [rdx]; String2
0x18000c042  lea     rcx, [rbp+50h+String1]
0x18000c046  cmp     [rbp+50h+var_48], 8
0x18000c04b  cmovnb  rcx, [rbp+50h+String1]; String1
0x18000c050  call    cs:__imp__wcsicmp
0x18000c056  test    eax, eax
0x18000c058  jz      short loc_18000C083
0x18000c05a  add     rbx, 78h ; 'x'
0x18000c05e  jmp     short loc_18000C02B
0x18000c060  test    rbx, rbx
0x18000c063  jnz     loc_18000BF6E
0x18000c069  lea     rcx, [rbp+50h+Src]
0x18000c06d  cmp     rdx, 8
0x18000c071  cmovnb  rcx, [rbp+50h+Src]
0x18000c076  mov     [rbp+50h+var_A0], r8
0x18000c07a  mov     [rcx], r8w
0x18000c07e  jmp     loc_18000BF98
0x18000c083  cmp     qword ptr [rbx+18h], 8
0x18000c088  jb      short loc_18000C08D
0x18000c08a  mov     rbx, [rbx]
0x18000c08d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c091  inc     r8
0x18000c094  cmp     [rbx+r8*2], si
0x18000c099  jnz     short loc_18000C091
0x18000c09b  mov     rdx, rbx; void *
0x18000c09e  lea     rcx, [rbp+50h+var_88]; Src
0x18000c0a2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000c0a7  nop
0x18000c0a8  cmp     [rbp+50h+var_48], 8
0x18000c0ad  jb      short loc_18000C0B9
0x18000c0af  mov     rcx, [rbp+50h+String1]
0x18000c0b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c0b9  mov     [rbp+50h+var_48], 7
0x18000c0c1  mov     [rbp+50h+var_50], rsi
0x18000c0c5  mov     word ptr [rbp+50h+String1], si
0x18000c0c9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000c0cd  xor     r8d, r8d
0x18000c0d0  lea     rdx, [rbp+50h+var_88]
0x18000c0d4  lea     rcx, [rbp+50h+Src]
0x18000c0d8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000c0dd  mov     bl, 1
0x18000c0df  inc     r15d
0x18000c0e2  cmp     r15d, dword ptr [rsp+150h+var_128]
0x18000c0e7  jl      loc_18000BEE1
0x18000c0ed  mov     rdx, [rbp+50h+var_A0]
0x18000c0f1  xor     esi, esi
0x18000c0f3  test    rdx, rdx
0x18000c0f6  setz    al
0x18000c0f9  lea     r9, [rdi+0A8h]
0x18000c100  test    al, al
0x18000c102  jz      short loc_18000C12D
0x18000c104  lea     r14d, [rsi+1]
0x18000c108  mov     dword ptr [rdi+0D0h], 4
0x18000c112  cmp     qword ptr [r9+18h], 8
0x18000c117  jb      short loc_18000C11E
0x18000c119  mov     rcx, [r9]
0x18000c11c  jmp     short loc_18000C121
0x18000c11e  mov     rcx, r9
0x18000c121  mov     [r9+10h], rsi
0x18000c125  mov     [rcx], si
0x18000c128  jmp     loc_18000C246
0x18000c12d  cmp     qword ptr [r9+18h], 8
0x18000c132  jb      short loc_18000C139
0x18000c134  mov     rcx, [r9]
0x18000c137  jmp     short loc_18000C13C
0x18000c139  mov     rcx, r9
0x18000c13c  mov     r11, [r9+10h]
0x18000c140  mov     r10, rdx
0x18000c143  cmp     rdx, r11
0x18000c146  cmovnb  r10, r11
0x18000c14a  lea     r8, [rbp+50h+Src]
0x18000c14e  mov     rbx, [rbp+50h+Src]
0x18000c152  cmp     [rbp+50h+var_98], 8
0x18000c157  cmovnb  r8, rbx
0x18000c15b  test    r10, r10
0x18000c15e  jz      short loc_18000C179
0x18000c160  movzx   eax, word ptr [rcx]
0x18000c163  cmp     [r8], ax
0x18000c167  jnz     loc_18000C1F9
0x18000c16d  add     r8, r14
0x18000c170  add     rcx, r14
0x18000c173  sub     r10, 1
0x18000c177  jnz     short loc_18000C160
0x18000c179  cmp     rdx, r11
0x18000c17c  jnz     short loc_18000C1F9
0x18000c17e  cmp     [rbp+50h+var_70], 8
0x18000c183  jb      short loc_18000C18F
0x18000c185  mov     rcx, [rbp+50h+var_88]
0x18000c189  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c18f  mov     ebx, 7
0x18000c194  mov     [rbp+50h+var_70], rbx
0x18000c198  mov     [rbp+50h+var_78], rsi
0x18000c19c  mov     word ptr [rbp+50h+var_88], si
0x18000c1a0  cmp     [rbp+50h+var_98], 8
0x18000c1a5  jb      short loc_18000C1B1
0x18000c1a7  mov     rcx, [rbp+50h+Src]
0x18000c1ab  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c1b1  mov     [rbp+50h+var_98], rbx
0x18000c1b5  mov     [rbp+50h+var_A0], rsi
0x18000c1b9  mov     word ptr [rbp+50h+Src], si
0x18000c1bd  mov     rcx, r12; pv
0x18000c1c0  call    cs:__imp_CoTaskMemFree
0x18000c1c6  mov     [rsp+150h+pv], rsi
0x18000c1cb  mov     [rsp+150h+pv], rsi
0x18000c1d0  xor     eax, eax
0x18000c1d2  mov     rcx, [rbp+50h+var_38]
0x18000c1d6  xor     rcx, rsp; StackCookie
0x18000c1d9  call    __security_check_cookie
0x18000c1de  mov     rbx, [rsp+150h+arg_18]
0x18000c1e6  add     rsp, 120h
0x18000c1ed  pop     r15
0x18000c1ef  pop     r14
0x18000c1f1  pop     r13
0x18000c1f3  pop     r12
0x18000c1f5  pop     rdi
0x18000c1f6  pop     rsi
0x18000c1f7  pop     rbp
0x18000c1f8  retn
0x18000c1f9  lea     rax, [rbp+50h+Src]
0x18000c1fd  cmp     r9, rax
0x18000c200  jz      short loc_18000C23C
0x18000c202  mov     rdx, [r9]
0x18000c205  mov     rax, [r9+8]
0x18000c209  mov     [r9], rbx
0x18000c20c  mov     rcx, [rbp+50h+var_A8]
0x18000c210  mov     [r9+8], rcx
0x18000c214  mov     [rbp+50h+Src], rdx
0x18000c218  mov     [rbp+50h+var_A8], rax
0x18000c21c  mov     r8, [r9+10h]
0x18000c220  mov     rax, [rbp+50h+var_A0]
0x18000c224  mov     [r9+10h], rax
0x18000c228  mov     [rbp+50h+var_A0], r8
0x18000c22c  mov     r8, [r9+18h]
0x18000c230  mov     rax, [rbp+50h+var_98]
0x18000c234  mov     [r9+18h], rax
0x18000c238  mov     [rbp+50h+var_98], r8
0x18000c23c  mov     dword ptr [rdi+0D0h], 3
0x18000c246  mov     r9d, r14d
0x18000c249  mov     r8, rdi
0x18000c24c  mov     rdx, [rsp+150h+var_120]
0x18000c251  mov     rcx, [rsp+150h+var_118]
0x18000c256  call    ?UpdatePage@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@PEBUPropertyInfo@1@W4UpdatePageReason@1@@Z; CFciPropertiesShellExt::UpdatePage(HWND__ *,CFciPropertiesShellExt::PropertyInfo const *,CFciPropertiesShellExt::UpdatePageReason)
0x18000c25b  nop
0x18000c25c  cmp     [rbp+50h+var_70], 8
0x18000c261  jb      short loc_18000C26D
0x18000c263  mov     rcx, [rbp+50h+var_88]
0x18000c267  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c26d  mov     ebx, 7
0x18000c272  mov     [rbp+50h+var_70], rbx
0x18000c276  mov     [rbp+50h+var_78], rsi
0x18000c27a  mov     word ptr [rbp+50h+var_88], si
0x18000c27e  cmp     [rbp+50h+var_98], 8
0x18000c283  jb      short loc_18000C28F
0x18000c285  mov     rcx, [rbp+50h+Src]
0x18000c289  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c28f  mov     [rbp+50h+var_98], rbx
0x18000c293  mov     [rbp+50h+var_A0], rsi
0x18000c297  mov     word ptr [rbp+50h+Src], si
0x18000c29b  mov     rcx, r12; pv
0x18000c29e  call    cs:__imp_CoTaskMemFree
0x18000c2a4  mov     [rsp+150h+pv], rsi
0x18000c2a9  mov     [rsp+150h+pv], rsi
0x18000c2ae  mov     eax, 1
0x18000c2b3  jmp     loc_18000C1D2
0x18000c2b8  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18000c2be  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
