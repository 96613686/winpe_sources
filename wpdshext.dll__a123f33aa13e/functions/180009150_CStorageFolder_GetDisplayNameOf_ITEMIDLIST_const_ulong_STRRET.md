# CStorageFolder::GetDisplayNameOf(_ITEMIDLIST const *,ulong,_STRRET *)

- ea: `0x180009150`
- end: `0x18000987d`
- name: `?GetDisplayNameOf@CStorageFolder@@UEAAJPEFBU_ITEMIDLIST@@KPEAU_STRRET@@@Z`
- size: `1837`
- prototype: `int(CStorageFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x180009150`
- `0x180009890`
- `0x18002ff5c`
- `0x1800339cc`
- `0x180035590`
- `0x1800361ba`
- `0x180078010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x1800092d8`
- `SHLWAPI!SHStrDupW` at `0x18000936a`
- `SHLWAPI!SHStrDupW` at `0x1800092d8`
- `SHLWAPI!SHStrDupW` at `0x18000936a`
- `SHLWAPI!PathFindFileNameW` at `0x18000923b`
- `SHLWAPI!PathFindFileNameW` at `0x18000923b`
- `SHLWAPI!StrRetToBufW` at `0x180009511`
- `SHLWAPI!StrRetToBufW` at `0x180009511`
- `ole32!CoUninitialize` at `0x180009559`
- `ole32!CoUninitialize` at `0x180009559`
- `ole32!CoTaskMemFree` at `0x1800093bc`
- `ole32!CoTaskMemFree` at `0x1800093bc`
- `ole32!CoTaskMemAlloc` at `0x180009442`
- `ole32!CoTaskMemAlloc` at `0x180009442`
- `ole32!CoInitializeEx` at `0x18000946f`
- `ole32!CoInitializeEx` at `0x18000968d`
- `ole32!CoInitializeEx` at `0x18000946f`
- `ole32!CoInitializeEx` at `0x18000968d`
- `SHELL32!SHBindToParent` at `0x1800094a6`
- `SHELL32!SHBindToParent` at `0x1800094a6`

## pseudocode

```c
HRESULT __fastcall CStorageFolder::GetDisplayNameOf(
        CStorageFolder *this,
        const struct _ITEMIDLIST *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  struct _STRRET *v7; // rsi
  CStorageFolder *v8; // rcx
  const struct STORAGEITEM *v9; // r13
  WCHAR *v10; // r12
  HRESULT v11; // edi
  __int64 v12; // rbx
  WCHAR *v13; // r9
  __int64 v14; // rdx
  WCHAR *v15; // r8
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rcx
  WCHAR *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r14
  WCHAR *v22; // rcx
  WCHAR *v23; // rdx
  WCHAR *v24; // rcx
  HRESULT v25; // eax
  PVOID *v26; // rcx
  unsigned int v27; // ebx
  __int64 v28; // rax
  WCHAR *v29; // r8
  WCHAR *v30; // rcx
  HRESULT result; // eax
  PVOID *v32; // rcx
  unsigned int v33; // ebx
  WCHAR *v34; // rcx
  int v35; // edx
  PVOID *v36; // r10
  WCHAR *v37; // r8
  WCHAR *v38; // rax
  const ITEMIDLIST *v39; // rbx
  HRESULT v40; // esi
  const ITEMIDLIST *v41; // rbp
  void *v42; // rbx
  __int64 v43; // rcx
  WCHAR *v44; // rax
  __int64 v45; // r9
  bool v46; // zf
  __int64 v47; // r8
  __int64 v48; // rcx
  WCHAR *v49; // r9
  const wchar_t *v50; // rdx
  HRESULT v51; // eax
  void *ppv; // [rsp+30h] [rbp-398h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+38h] [rbp-390h] BYREF
  struct _STRRET *v54; // [rsp+40h] [rbp-388h]
  STRRET pstr; // [rsp+50h] [rbp-378h] BYREF
  WCHAR pszPath[264]; // [rsp+160h] [rbp-268h] BYREF

  v54 = a4;
  v7 = a4;
  memset_0(pszPath, 0, 0x208u);
  if ( !v7 )
  {
    v11 = -2147467261;
    goto LABEL_82;
  }
  v9 = CStorageFolder::_IsValid(v8, a2);
  if ( !v9 )
  {
    v11 = -2147024809;
    goto LABEL_82;
  }
  v10 = 0;
  if ( (a3 & 0xC000) == 0 || (a3 & 1) != 0 )
  {
    v11 = -2147024809;
    v12 = 2147483646;
    goto LABEL_5;
  }
  v38 = (WCHAR *)CoTaskMemAlloc(0x1040u);
  v10 = v38;
  if ( !v38 )
  {
    v11 = -2147024882;
    goto LABEL_82;
  }
  memset_0(v38, 0, 0x1040u);
  v39 = (const ITEMIDLIST *)*((_QWORD *)this + 6);
  v40 = CoInitializeEx(0, 6u);
  if ( v40 < 0 )
  {
    v51 = CoInitializeEx(0, 4u);
    v40 = v51;
    if ( v51 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
        (unsigned int)v51);
  }
  ppv = 0;
  ppidlLast = 0;
  v11 = SHBindToParent(v39, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
  if ( v11 < 0 )
    goto LABEL_63;
  v41 = ppidlLast;
  v42 = ppv;
  *v10 = 0;
  memset_0(&pstr, 0, sizeof(pstr));
  v11 = (*(__int64 (__fastcall **)(void *, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v42 + 88LL))(
          v42,
          v41,
          a3,
          &pstr);
  if ( v11 >= 0 )
  {
    v11 = StrRetToBufW(&pstr, v41, v10, 0x820u);
    if ( v11 >= 0 )
      goto LABEL_60;
  }
  v36 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
      (unsigned int)v11);
LABEL_60:
    v36 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
LABEL_63:
    v36 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v40 >= 0 )
  {
    CoUninitialize();
    v36 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 < 0 )
  {
    if ( v36 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v36 + 28) & 2) != 0 )
      {
        WPP_SF_d(v36[2], 68, &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids, (unsigned int)v11);
        v36 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 2) != 0 )
        WPP_SF_d(v36[2], 51, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v11);
    }
    goto LABEL_46;
  }
  v43 = 2080;
  v44 = v10;
  do
  {
    if ( !*v44 )
      break;
    ++v44;
    --v43;
  }
  while ( v43 );
  v11 = -2147024809;
  v35 = -2147024809;
  if ( v43 )
    v35 = 0;
  v45 = 2080 - v43;
  if ( !v43 )
    goto LABEL_45;
  v12 = 2147483646;
  v47 = v43;
  v46 = v45 == 2080;
  v48 = 2147483646;
  v49 = &v10[v45];
  v50 = L"\\";
  if ( !v46 )
  {
    do
    {
      if ( !v48 )
        break;
      if ( !*v50 )
        break;
      *v49++ = *v50++;
      --v48;
      --v47;
    }
    while ( v47 );
  }
  v34 = v49 - 1;
  v35 = -2147024774;
  if ( v47 )
  {
    v34 = v49;
    v35 = 0;
  }
  *v34 = 0;
  if ( !v47 )
  {
    v36 = (PVOID *)WPP_GLOBAL_Control;
LABEL_45:
    v11 = v35;
    if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 2) != 0 )
      WPP_SF_SSd(
        (unsigned int)v36[2],
        52,
        (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
        (_DWORD)v10,
        (__int64)L"\\",
        v35,
        ppv);
    goto LABEL_46;
  }
  v7 = v54;
LABEL_5:
  v13 = pszPath;
  v14 = 2147483646;
  if ( (a3 & 0x4000) != 0 )
  {
    v15 = (WCHAR *)((char *)v9 + 54);
    v16 = 260;
    do
    {
      if ( !v14 )
        break;
      if ( !*v15 )
        break;
      *v13++ = *v15++;
      --v14;
      --v16;
    }
    while ( v16 );
LABEL_10:
    v17 = v13 - 1;
    if ( v16 )
      v17 = v13;
    *v17 = 0;
    PathFindFileNameW(pszPath);
    goto LABEL_13;
  }
  if ( (a3 & 0x8000) == 0 )
  {
    v37 = (WCHAR *)((char *)v9 + 54);
    v16 = 260;
    do
    {
      if ( !v14 )
        break;
      if ( !*v37 )
        break;
      *v13++ = *v37++;
      --v14;
      --v16;
    }
    while ( v16 );
    goto LABEL_10;
  }
  v28 = 260;
  v29 = (WCHAR *)((char *)v9 + 2 * *(unsigned int *)((char *)v9 + 38) + 54);
  do
  {
    if ( !v14 )
      break;
    if ( !*v29 )
      break;
    *v13++ = *v29++;
    --v14;
    --v28;
  }
  while ( v28 );
  v30 = v13 - 1;
  if ( v28 )
    v30 = v13;
  *v30 = 0;
LABEL_13:
  if ( v10 )
  {
    v18 = 2080;
    v19 = v10;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( v18 )
      v11 = 0;
    v20 = 2080 - v18;
    if ( !v18 )
      goto LABEL_113;
    v21 = v18;
    v22 = pszPath;
    v23 = &v10[v20];
    do
    {
      if ( !v12 )
        break;
      if ( !*v22 )
        break;
      *v23++ = *v22++;
      --v12;
      --v21;
    }
    while ( v21 );
    v24 = v23 - 1;
    v11 = -2147024774;
    if ( v21 )
    {
      v24 = v23;
      v11 = 0;
    }
    *v24 = 0;
    if ( v21 )
    {
      v7->uType = 0;
      v25 = SHStrDupW(v10, &v7->pOleStr);
      v26 = (PVOID *)WPP_GLOBAL_Control;
      v27 = v25;
      if ( v25 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        v11 = v25;
        if ( v25 >= 0 )
          goto LABEL_46;
      }
      else
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          (unsigned int)v25);
        v26 = (PVOID *)WPP_GLOBAL_Control;
        v11 = v27;
      }
      if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 2) != 0 )
        WPP_SF_d(v26[2], 55, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v27);
    }
    else
    {
LABEL_113:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
          (_DWORD)v10,
          (__int64)pszPath,
          v11,
          ppv);
    }
LABEL_46:
    CoTaskMemFree(v10);
    if ( v11 >= 0 )
      return v11;
    goto LABEL_82;
  }
  v7->uType = 0;
  result = SHStrDupW(pszPath, &v7->pOleStr);
  v32 = (PVOID *)WPP_GLOBAL_Control;
  v33 = result;
  if ( result < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
      (unsigned int)result);
    v32 = (PVOID *)WPP_GLOBAL_Control;
    v11 = v33;
    goto LABEL_103;
  }
  v11 = result;
  if ( result < 0 )
  {
LABEL_103:
    if ( v32 == &WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)v32 + 28) & 2) == 0 )
    {
LABEL_83:
      if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 2) != 0 )
        WPP_SF_d(v32[2], 56, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v11);
      return v11;
    }
    WPP_SF_d(v32[2], 53, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v33);
LABEL_82:
    v32 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_83;
  }
  return result;
}

```

## disassembly

```asm
0x180009150  push    rbx
0x180009152  push    rbp
0x180009153  push    rsi
0x180009154  push    rdi
0x180009155  push    r12
0x180009157  push    r13
0x180009159  push    r14
0x18000915b  push    r15
0x18000915d  sub     rsp, 388h
0x180009164  mov     rax, cs:__security_cookie
0x18000916b  xor     rax, rsp
0x18000916e  mov     [rsp+3C8h+var_58], rax
0x180009176  mov     r15d, r8d
0x180009179  mov     [rsp+3C8h+var_388], r9
0x18000917e  mov     rbx, rdx
0x180009181  mov     rdi, rcx
0x180009184  xor     edx, edx; Val
0x180009186  lea     rcx, [rsp+3C8h+pszPath]; void *
0x18000918e  mov     r8d, 208h; Size
0x180009194  mov     rsi, r9
0x180009197  call    memset_0
0x18000919c  test    rsi, rsi
0x18000919f  jz      loc_180009627
0x1800091a5  mov     rdx, rbx; struct _ITEMIDLIST *
0x1800091a8  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x1800091ad  mov     r13, rax
0x1800091b0  test    rax, rax
0x1800091b3  jz      loc_18000966A
0x1800091b9  xor     r12d, r12d
0x1800091bc  test    r15d, 0C000h
0x1800091c3  jnz     loc_180009433
0x1800091c9  mov     edi, 80070057h
0x1800091ce  lea     rbp, WPP_GLOBAL_Control
0x1800091d5  mov     ebx, 7FFFFFFEh
0x1800091da  mov     r14d, 820h
0x1800091e0  lea     r9, [rsp+3C8h+pszPath]
0x1800091e8  mov     rdx, rbx
0x1800091eb  bt      r15d, 0Eh
0x1800091f0  jnb     loc_1800092FE
0x1800091f6  lea     r8, [r13+36h]
0x1800091fa  mov     eax, 104h
0x1800091ff  nop
0x180009200  test    rdx, rdx
0x180009203  jz      short loc_180009223
0x180009205  movzx   ecx, word ptr [r8]
0x180009209  test    cx, cx
0x18000920c  jz      short loc_180009223
0x18000920e  mov     [r9], cx
0x180009212  add     r8, 2
0x180009216  add     r9, 2
0x18000921a  dec     rdx
0x18000921d  sub     rax, 1
0x180009221  jnz     short loc_180009200
0x180009223  test    rax, rax
0x180009226  lea     rcx, [r9-2]
0x18000922a  cmovnz  rcx, r9
0x18000922e  xor     eax, eax
0x180009230  mov     [rcx], ax
0x180009233  lea     rcx, [rsp+3C8h+pszPath]; pszPath
0x18000923b  call    cs:__imp_PathFindFileNameW
0x180009241  test    r12, r12
0x180009244  jz      loc_180009358
0x18000924a  mov     rcx, r14
0x18000924d  mov     rax, r12
0x180009250  cmp     word ptr [rax], 0
0x180009254  jz      short loc_180009260
0x180009256  add     rax, 2
0x18000925a  sub     rcx, 1
0x18000925e  jnz     short loc_180009250
0x180009260  xor     eax, eax
0x180009262  mov     rdx, r14
0x180009265  test    rcx, rcx
0x180009268  cmovnz  edi, eax
0x18000926b  sub     rdx, rcx
0x18000926e  test    rcx, rcx
0x180009271  cmovz   rdx, rax
0x180009275  jz      loc_180009835
0x18000927b  sub     r14, rdx
0x18000927e  lea     rcx, [rsp+3C8h+pszPath]
0x180009286  lea     rdx, [r12+rdx*2]
0x18000928a  jz      short loc_1800092B1
0x18000928c  nop     dword ptr [rax+00h]
0x180009290  test    rbx, rbx
0x180009293  jz      short loc_1800092B1
0x180009295  movzx   eax, word ptr [rcx]
0x180009298  test    ax, ax
0x18000929b  jz      short loc_1800092B1
0x18000929d  mov     [rdx], ax
0x1800092a0  add     rcx, 2
0x1800092a4  add     rdx, 2
0x1800092a8  dec     rbx
0x1800092ab  sub     r14, 1
0x1800092af  jnz     short loc_180009290
0x1800092b1  xor     eax, eax
0x1800092b3  lea     rcx, [rdx-2]
0x1800092b7  test    r14, r14
0x1800092ba  mov     edi, 8007007Ah
0x1800092bf  cmovnz  rcx, rdx
0x1800092c3  cmovnz  edi, eax
0x1800092c6  mov     [rcx], ax
0x1800092c9  jz      loc_180009835
0x1800092cf  lea     rdx, [rsi+8]; ppwsz
0x1800092d3  mov     [rsi], eax
0x1800092d5  mov     rcx, r12; psz
0x1800092d8  call    cs:__imp_SHStrDupW
0x1800092de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092e5  mov     ebx, eax
0x1800092e7  test    eax, eax
0x1800092e9  js      loc_1800097D1
0x1800092ef  mov     edi, ebx
0x1800092f1  test    ebx, ebx
0x1800092f3  jns     loc_1800093B9
0x1800092f9  jmp     loc_180009805
0x1800092fe  bt      r15d, 0Fh
0x180009303  jnb     loc_1800093FA
0x180009309  mov     eax, [r13+26h]
0x18000930d  lea     r8, ds:36h[rax*2]
0x180009315  mov     eax, 104h
0x18000931a  add     r8, r13
0x18000931d  nop     dword ptr [rax]
0x180009320  test    rdx, rdx
0x180009323  jz      short loc_180009343
0x180009325  movzx   ecx, word ptr [r8]
0x180009329  test    cx, cx
0x18000932c  jz      short loc_180009343
0x18000932e  mov     [r9], cx
0x180009332  add     r8, 2
0x180009336  add     r9, 2
0x18000933a  dec     rdx
0x18000933d  sub     rax, 1
0x180009341  jnz     short loc_180009320
0x180009343  test    rax, rax
0x180009346  lea     rcx, [r9-2]
0x18000934a  cmovnz  rcx, r9
0x18000934e  xor     eax, eax
0x180009350  mov     [rcx], ax
0x180009353  jmp     loc_180009241
0x180009358  lea     rdx, [rsi+8]; ppwsz
0x18000935c  mov     dword ptr [rsi], 0
0x180009362  lea     rcx, [rsp+3C8h+pszPath]; psz
0x18000936a  call    cs:__imp_SHStrDupW
0x180009370  mov     rcx, cs:WPP_GLOBAL_Control
0x180009377  mov     ebx, eax
0x180009379  test    eax, eax
0x18000937b  js      loc_18000976D
0x180009381  mov     edi, ebx
0x180009383  test    ebx, ebx
0x180009385  js      loc_1800097A1
0x18000938b  jmp     short loc_1800093CC
0x18000938d  xor     eax, eax
0x18000938f  lea     rcx, [r9-2]
0x180009393  test    r8, r8
0x180009396  mov     edx, 8007007Ah
0x18000939b  cmovnz  rcx, r9
0x18000939f  cmovnz  edx, eax
0x1800093a2  mov     [rcx], ax
0x1800093a5  jnz     short loc_1800093F0
0x1800093a7  mov     r10, cs:WPP_GLOBAL_Control
0x1800093ae  mov     edi, edx
0x1800093b0  cmp     r10, rbp
0x1800093b3  jnz     loc_18000974B
0x1800093b9  mov     rcx, r12; pv
0x1800093bc  call    cs:__imp_CoTaskMemFree
0x1800093c2  test    edi, edi
0x1800093c4  js      loc_180009633
0x1800093ca  mov     eax, edi
0x1800093cc  mov     rcx, [rsp+3C8h+var_58]
0x1800093d4  xor     rcx, rsp; StackCookie
0x1800093d7  call    __security_check_cookie
0x1800093dc  add     rsp, 388h
0x1800093e3  pop     r15
0x1800093e5  pop     r14
0x1800093e7  pop     r13
0x1800093e9  pop     r12
0x1800093eb  pop     rdi
0x1800093ec  pop     rsi
0x1800093ed  pop     rbp
0x1800093ee  pop     rbx
0x1800093ef  retn
0x1800093f0  mov     rsi, [rsp+3C8h+var_388]
0x1800093f5  jmp     loc_1800091E0
0x1800093fa  lea     r8, [r13+36h]
0x1800093fe  mov     eax, 104h
0x180009403  test    rdx, rdx
0x180009406  jz      loc_180009223
0x18000940c  movzx   ecx, word ptr [r8]
0x180009410  test    cx, cx
0x180009413  jz      loc_180009223
0x180009419  mov     [r9], cx
0x18000941d  add     r8, 2
0x180009421  add     r9, 2
0x180009425  dec     rdx
0x180009428  sub     rax, 1
0x18000942c  jnz     short loc_180009403
0x18000942e  jmp     loc_180009223
0x180009433  test    r15b, 1
0x180009437  jnz     loc_1800091C9
0x18000943d  mov     ecx, 1040h; cb
0x180009442  call    cs:__imp_CoTaskMemAlloc
0x180009448  mov     r12, rax
0x18000944b  test    rax, rax
0x18000944e  jz      loc_180009678
0x180009454  xor     edx, edx; Val
0x180009456  mov     r8d, 1040h; Size
0x18000945c  mov     rcx, rax; void *
0x18000945f  call    memset_0
0x180009464  mov     rbx, [rdi+30h]
0x180009468  mov     edx, 6; dwCoInit
0x18000946d  xor     ecx, ecx; pvReserved
0x18000946f  call    cs:__imp_CoInitializeEx
0x180009475  lea     rbp, WPP_GLOBAL_Control
0x18000947c  mov     esi, eax
0x18000947e  test    eax, eax
0x180009480  js      loc_180009686
0x180009486  xor     eax, eax
0x180009488  lea     r9, [rsp+3C8h+ppidlLast]; ppidlLast
0x18000948d  lea     r8, [rsp+3C8h+ppv]; ppv
0x180009492  mov     [rsp+3C8h+ppv], rax
0x180009497  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000949e  mov     [rsp+3C8h+ppidlLast], rax
0x1800094a3  mov     rcx, rbx; pidl
0x1800094a6  call    cs:__imp_SHBindToParent
0x1800094ac  mov     edi, eax
0x1800094ae  mov     r14d, 820h
0x1800094b4  test    eax, eax
0x1800094b6  js      loc_18000954E
0x1800094bc  mov     rbp, [rsp+3C8h+ppidlLast]
0x1800094c1  lea     rcx, [rsp+3C8h+pstr]; void *
0x1800094c6  mov     rbx, [rsp+3C8h+ppv]
0x1800094cb  xor     eax, eax
0x1800094cd  xor     edx, edx; Val
0x1800094cf  mov     [r12], ax
0x1800094d4  mov     r8d, 110h; Size
0x1800094da  call    memset_0
0x1800094df  mov     rax, [rbx]
0x1800094e2  lea     r9, [rsp+3C8h+pstr]
0x1800094e7  mov     r8d, r15d
0x1800094ea  mov     rdx, rbp
0x1800094ed  mov     rcx, rbx
0x1800094f0  mov     rax, [rax+58h]
0x1800094f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f9  mov     edi, eax
0x1800094fb  test    eax, eax
0x1800094fd  js      loc_1800096D4
0x180009503  mov     r9d, r14d; cchBuf
0x180009506  lea     rcx, [rsp+3C8h+pstr]; pstr
0x18000950b  mov     r8, r12; pszBuf
0x18000950e  mov     rdx, rbp; pidl
0x180009511  call    cs:__imp_StrRetToBufW
0x180009517  mov     edi, eax
0x180009519  test    eax, eax
0x18000951b  js      loc_1800096D4
0x180009521  lea     rbp, WPP_GLOBAL_Control
0x180009528  mov     r10, cs:WPP_GLOBAL_Control
0x18000952f  mov     rcx, [rsp+3C8h+ppv]
0x180009534  test    rcx, rcx
0x180009537  jz      short loc_180009555
0x180009539  mov     rax, [rcx]
0x18000953c  mov     rax, [rax+10h]
0x180009540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009545  mov     [rsp+3C8h+ppv], 0
0x18000954e  mov     r10, cs:WPP_GLOBAL_Control
0x180009555  test    esi, esi
0x180009557  js      short loc_180009566
0x180009559  call    cs:__imp_CoUninitialize
0x18000955f  mov     r10, cs:WPP_GLOBAL_Control
0x180009566  test    edi, edi
0x180009568  js      loc_180009713
0x18000956e  mov     rcx, r14
0x180009571  mov     rax, r12
0x180009574  cmp     word ptr [rax], 0
0x180009578  jz      short loc_180009584
0x18000957a  add     rax, 2
0x18000957e  sub     rcx, 1
0x180009582  jnz     short loc_180009574
0x180009584  xor     eax, eax
0x180009586  lea     r11, pszSrc; "\\"
0x18000958d  test    rcx, rcx
0x180009590  mov     edi, 80070057h
0x180009595  mov     edx, edi
0x180009597  mov     r9, r14
0x18000959a  cmovnz  edx, eax
0x18000959d  sub     r9, rcx
0x1800095a0  test    rcx, rcx
0x1800095a3  cmovz   r9, rax
0x1800095a7  jz      loc_1800093AE
0x1800095ad  mov     r8, r14
0x1800095b0  mov     ebx, 7FFFFFFEh
0x1800095b5  sub     r8, r9
0x1800095b8  mov     ecx, ebx
0x1800095ba  lea     r9, [r12+r9*2]
0x1800095be  mov     rdx, r11
0x1800095c1  jz      loc_18000938D
0x1800095c7  test    rcx, rcx
0x1800095ca  jz      loc_18000938D
0x1800095d0  movzx   eax, word ptr [rdx]
0x1800095d3  test    ax, ax
0x1800095d6  jz      loc_18000938D
0x1800095dc  mov     [r9], ax
0x1800095e0  add     rdx, 2
  ... truncated ...
```
