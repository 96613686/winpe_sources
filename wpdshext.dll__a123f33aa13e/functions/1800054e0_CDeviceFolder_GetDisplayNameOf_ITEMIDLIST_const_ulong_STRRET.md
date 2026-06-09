# CDeviceFolder::GetDisplayNameOf(_ITEMIDLIST const *,ulong,_STRRET *)

- ea: `0x1800054e0`
- end: `0x180005b87`
- name: `?GetDisplayNameOf@CDeviceFolder@@UEAAJPEFBU_ITEMIDLIST@@KPEAU_STRRET@@@Z`
- size: `1703`
- prototype: `int(CDeviceFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x180004110`
- `0x180005460`
- `0x1800054e0`
- `0x180007860`
- `0x180024928`
- `0x18002ff5c`
- `0x1800339cc`
- `0x180035590`
- `0x1800361ba`
- `0x180078010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180005698`
- `SHLWAPI!SHStrDupW` at `0x180005703`
- `SHLWAPI!SHStrDupW` at `0x180005698`
- `SHLWAPI!SHStrDupW` at `0x180005703`
- `SHLWAPI!StrRetToBufW` at `0x180005898`
- `SHLWAPI!StrRetToBufW` at `0x180005898`
- `ole32!CoUninitialize` at `0x1800058e0`
- `ole32!CoUninitialize` at `0x1800058e0`
- `ole32!CoTaskMemFree` at `0x1800056bf`
- `ole32!CoTaskMemFree` at `0x1800056bf`
- `ole32!CoTaskMemAlloc` at `0x1800057df`
- `ole32!CoTaskMemAlloc` at `0x1800057df`
- `SHELL32!SHBindToParent` at `0x18000582e`
- `SHELL32!SHBindToParent` at `0x18000582e`

## pseudocode

```c
HRESULT __fastcall CDeviceFolder::GetDisplayNameOf(
        CDeviceFolder *this,
        const struct _ITEMIDLIST *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  struct _STRRET *v7; // rsi
  CDeviceFolder *v8; // rcx
  CDeviceFolder *v9; // rcx
  const struct DEVICEITEM *v10; // r14
  int v11; // r13d
  __int64 v12; // r12
  int v13; // r8d
  __int64 v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // r9
  WCHAR *v17; // r8
  WCHAR *v18; // rcx
  WCHAR *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r15
  WCHAR *v23; // rcx
  WCHAR *v24; // rdx
  WCHAR *v25; // rcx
  HRESULT v26; // eax
  PVOID *v27; // rcx
  unsigned int v28; // ebx
  HRESULT result; // eax
  PVOID *v30; // rcx
  unsigned int v31; // ebx
  PVOID *v32; // r11
  int v33; // edx
  __int64 v34; // r9
  __int64 v35; // rcx
  bool v36; // zf
  __int64 v37; // rdx
  const wchar_t *v38; // r8
  CDeviceFolder *v39; // r9
  WCHAR *v40; // rax
  const ITEMIDLIST *v41; // rbx
  int v42; // esi
  HRESULT v43; // ebx
  const ITEMIDLIST *v44; // rdi
  void *v45; // rbx
  __int64 v46; // rcx
  WCHAR *v47; // rax
  WCHAR *psz; // [rsp+30h] [rbp-398h]
  void *ppv; // [rsp+38h] [rbp-390h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+40h] [rbp-388h] BYREF
  struct _STRRET *v51; // [rsp+48h] [rbp-380h]
  STRRET pstr; // [rsp+50h] [rbp-378h] BYREF
  WCHAR v53[264]; // [rsp+160h] [rbp-268h] BYREF

  v51 = a4;
  v7 = a4;
  memset_0(v53, 0, 0x208u);
  if ( !v7 )
  {
    v11 = -2147467261;
    goto LABEL_75;
  }
  v10 = CDeviceFolder::_IsValid(v8, a2);
  v11 = -2147024809;
  if ( !v10 )
    goto LABEL_75;
  psz = 0;
  v12 = 2147483646;
  if ( (a3 & 0xC000) != 0 && (a3 & 1) == 0 )
  {
    v40 = (WCHAR *)CoTaskMemAlloc(0x1040u);
    psz = v40;
    if ( !v40 )
    {
      v11 = -2147024882;
      goto LABEL_75;
    }
    memset_0(v40, 0, 0x1040u);
    v41 = (const ITEMIDLIST *)*((_QWORD *)this + 6);
    v42 = SHCoInitialize();
    ppv = 0;
    ppidlLast = 0;
    v43 = SHBindToParent(v41, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
    if ( v43 < 0 )
      goto LABEL_62;
    v44 = ppidlLast;
    v45 = ppv;
    *psz = 0;
    memset_0(&pstr, 0, sizeof(pstr));
    v43 = (*(__int64 (__fastcall **)(void *, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v45 + 88LL))(
            v45,
            v44,
            a3,
            &pstr);
    if ( v43 < 0 || (v43 = StrRetToBufW(&pstr, v44, psz, 0x820u), v43 < 0) )
    {
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_60;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
        (unsigned int)v43);
    }
    v32 = (PVOID *)WPP_GLOBAL_Control;
LABEL_60:
    if ( !ppv )
    {
LABEL_63:
      if ( v42 >= 0 )
      {
        CoUninitialize();
        v32 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v43 < 0 )
      {
        if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 2) != 0 )
        {
          WPP_SF_d(v32[2], 68, &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids, (unsigned int)v43);
          v32 = (PVOID *)WPP_GLOBAL_Control;
        }
        v11 = v43;
        if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 2) != 0 )
          WPP_SF_d(v32[2], 40, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v43);
        goto LABEL_35;
      }
      v46 = 2080;
      v47 = psz;
      do
      {
        if ( !*v47 )
          break;
        ++v47;
        --v46;
      }
      while ( v46 );
      v33 = -2147024809;
      if ( v46 )
        v33 = 0;
      v34 = 2080 - v46;
      if ( !v46 )
      {
        v11 = v33;
        goto LABEL_46;
      }
      v35 = 2147483646;
      v37 = 2080 - v34;
      v36 = v34 == 2080;
      v38 = L"\\";
      v39 = (CDeviceFolder *)&psz[v34];
      if ( !v36 )
      {
        do
        {
          if ( !v35 )
            break;
          if ( !*v38 )
            break;
          *(_WORD *)v39 = *v38++;
          v39 = (CDeviceFolder *)((char *)v39 + 2);
          --v35;
          --v37;
        }
        while ( v37 );
      }
      v9 = (CDeviceFolder *)((char *)v39 - 2);
      v13 = -2147024774;
      if ( v37 )
      {
        v9 = v39;
        v13 = 0;
      }
      *(_WORD *)v9 = 0;
      if ( !v37 )
      {
        v32 = (PVOID *)WPP_GLOBAL_Control;
        v11 = v13;
LABEL_46:
        if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 2) != 0 )
          WPP_SF_SSd(
            (unsigned int)v32[2],
            41,
            (unsigned int)WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
            (_DWORD)psz,
            (__int64)L"\\",
            v11);
        goto LABEL_35;
      }
      v7 = v51;
      goto LABEL_9;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
LABEL_62:
    v32 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_63;
  }
LABEL_9:
  if ( (a3 & 0x4000) != 0 )
  {
    if ( *(_DWORD *)((char *)v10 + 30) > 1u )
      v10 = (const struct DEVICEITEM *)((char *)v10 + 2 * *(unsigned int *)((char *)v10 + 26));
    v14 = 2147483646;
    v15 = (WCHAR *)((char *)v10 + 38);
    v16 = 260;
    v17 = v53;
    do
    {
      if ( !v14 )
        break;
      if ( !*v15 )
        break;
      *v17++ = *v15++;
      --v14;
      --v16;
    }
    while ( v16 );
    v18 = v17 - 1;
    if ( v16 )
      v18 = v17;
    *v18 = 0;
  }
  else if ( (a3 & 0x8000) != 0 )
  {
    StringCchCopyW(
      v53,
      0x104u,
      (const unsigned __int16 *)v10 + *(unsigned int *)((char *)v10 + 26) + *(unsigned int *)((char *)v10 + 30) + 19);
  }
  else
  {
    CDeviceFolder::_Name(v9, v10, v53, 0x104u);
  }
  v19 = psz;
  if ( psz )
  {
    v20 = 2080;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v20;
    }
    while ( v20 );
    if ( v20 )
      v11 = 0;
    v21 = 2080 - v20;
    if ( !v20 )
      goto LABEL_103;
    v22 = v20;
    v23 = v53;
    v24 = &psz[v21];
    do
    {
      if ( !v12 )
        break;
      if ( !*v23 )
        break;
      *v24++ = *v23++;
      --v12;
      --v22;
    }
    while ( v22 );
    v25 = v24 - 1;
    v11 = -2147024774;
    if ( v22 )
    {
      v25 = v24;
      v11 = 0;
    }
    *v25 = 0;
    if ( v22 )
    {
      v7->uType = 0;
      v26 = SHStrDupW(psz, &v7->pOleStr);
      v27 = (PVOID *)WPP_GLOBAL_Control;
      v28 = v26;
      if ( v26 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        v11 = v26;
        if ( v26 >= 0 )
          goto LABEL_35;
      }
      else
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          (unsigned int)v26);
        v27 = (PVOID *)WPP_GLOBAL_Control;
        v11 = v28;
      }
      if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 2) != 0 )
        WPP_SF_d(v27[2], 44, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v28);
    }
    else
    {
LABEL_103:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
          (_DWORD)psz,
          (__int64)v53,
          v11);
    }
LABEL_35:
    CoTaskMemFree(psz);
    if ( v11 >= 0 )
      return v11;
    goto LABEL_75;
  }
  v7->uType = 0;
  result = SHStrDupW(v53, &v7->pOleStr);
  v30 = (PVOID *)WPP_GLOBAL_Control;
  v31 = result;
  if ( result < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
      (unsigned int)result);
    v30 = (PVOID *)WPP_GLOBAL_Control;
    v11 = v31;
LABEL_93:
    if ( v30 == &WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)v30 + 28) & 2) == 0 )
    {
LABEL_76:
      if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 2) != 0 )
        WPP_SF_d(v30[2], 45, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v11);
      return v11;
    }
    WPP_SF_d(v30[2], 42, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v31);
LABEL_75:
    v30 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_76;
  }
  v11 = result;
  if ( result < 0 )
    goto LABEL_93;
  return result;
}

```

## disassembly

```asm
0x1800054e0  push    rbx
0x1800054e2  push    rbp
0x1800054e3  push    rsi
0x1800054e4  push    rdi
0x1800054e5  push    r12
0x1800054e7  push    r13
0x1800054e9  push    r14
0x1800054eb  push    r15
0x1800054ed  sub     rsp, 388h
0x1800054f4  mov     rax, cs:__security_cookie
0x1800054fb  xor     rax, rsp
0x1800054fe  mov     [rsp+3C8h+var_58], rax
0x180005506  mov     ebp, r8d
0x180005509  mov     [rsp+3C8h+var_380], r9
0x18000550e  mov     rbx, rdx
0x180005511  mov     rdi, rcx
0x180005514  xor     edx, edx; Val
0x180005516  lea     rcx, [rsp+3C8h+var_268]; void *
0x18000551e  mov     r8d, 208h; Size
0x180005524  mov     rsi, r9
0x180005527  call    memset_0
0x18000552c  test    rsi, rsi
0x18000552f  jz      loc_18000596D
0x180005535  mov     rdx, rbx; struct _ITEMIDLIST *
0x180005538  call    ?_IsValid@CDeviceFolder@@AEAAPEFBUDEVICEITEM@@PEFBU_ITEMIDLIST@@@Z; CDeviceFolder::_IsValid(_ITEMIDLIST const *)
0x18000553d  mov     r14, rax
0x180005540  mov     r13d, 80070057h
0x180005546  test    rax, rax
0x180005549  jz      loc_1800059B1
0x18000554f  xor     ebx, ebx
0x180005551  mov     r15d, 820h
0x180005557  mov     [rsp+3C8h+psz], rbx
0x18000555c  mov     r12d, 7FFFFFFEh
0x180005562  test    ebp, 0C000h
0x180005568  jnz     loc_1800057D0
0x18000556e  lea     rdi, WPP_GLOBAL_Control
0x180005575  jmp     short loc_18000559E
0x180005577  xor     eax, eax
0x180005579  lea     rcx, [r9-2]
0x18000557d  test    rdx, rdx
0x180005580  mov     r8d, 8007007Ah
0x180005586  cmovnz  rcx, r9; this
0x18000558a  cmovnz  r8d, eax
0x18000558e  mov     [rcx], ax
0x180005591  jz      loc_180005726
0x180005597  mov     rsi, [rsp+3C8h+var_380]
0x18000559c  xor     ebx, ebx
0x18000559e  bt      ebp, 0Eh
0x1800055a2  jnb     loc_180005922
0x1800055a8  cmp     dword ptr [r14+1Eh], 1
0x1800055ad  ja      loc_180005A67
0x1800055b3  mov     rcx, r12
0x1800055b6  lea     rdx, [r14+26h]
0x1800055ba  mov     r9d, 104h
0x1800055c0  lea     r8, [rsp+3C8h+var_268]
0x1800055c8  test    rcx, rcx
0x1800055cb  jz      short loc_1800055EA
0x1800055cd  movzx   eax, word ptr [rdx]
0x1800055d0  test    ax, ax
0x1800055d3  jz      short loc_1800055EA
0x1800055d5  mov     [r8], ax
0x1800055d9  add     rdx, 2
0x1800055dd  add     r8, 2
0x1800055e1  dec     rcx
0x1800055e4  sub     r9, 1
0x1800055e8  jnz     short loc_1800055C8
0x1800055ea  test    r9, r9
0x1800055ed  lea     rcx, [r8-2]
0x1800055f1  cmovnz  rcx, r8
0x1800055f5  mov     [rcx], bx
0x1800055f8  mov     rax, [rsp+3C8h+psz]
0x1800055fd  test    rax, rax
0x180005600  jz      loc_1800056F5
0x180005606  mov     rcx, r15
0x180005609  nop     dword ptr [rax+00000000h]
0x180005610  cmp     word ptr [rax], 0
0x180005614  jz      short loc_180005620
0x180005616  add     rax, 2
0x18000561a  sub     rcx, 1
0x18000561e  jnz     short loc_180005610
0x180005620  mov     r8, [rsp+3C8h+psz]
0x180005625  test    rcx, rcx
0x180005628  mov     rdx, r15
0x18000562b  cmovnz  r13d, ebx
0x18000562f  sub     rdx, rcx
0x180005632  test    rcx, rcx
0x180005635  cmovz   rdx, rbx
0x180005639  jz      loc_180005B3E
0x18000563f  sub     r15, rdx
0x180005642  lea     rcx, [rsp+3C8h+var_268]
0x18000564a  lea     rdx, [r8+rdx*2]
0x18000564e  jz      short loc_180005671
0x180005650  test    r12, r12
0x180005653  jz      short loc_180005671
0x180005655  movzx   eax, word ptr [rcx]
0x180005658  test    ax, ax
0x18000565b  jz      short loc_180005671
0x18000565d  mov     [rdx], ax
0x180005660  add     rcx, 2
0x180005664  add     rdx, 2
0x180005668  dec     r12
0x18000566b  sub     r15, 1
0x18000566f  jnz     short loc_180005650
0x180005671  test    r15, r15
0x180005674  lea     rcx, [rdx-2]
0x180005678  mov     r13d, 8007007Ah
0x18000567e  cmovnz  rcx, rdx
0x180005682  cmovnz  r13d, ebx
0x180005686  mov     [rcx], bx
0x180005689  jz      loc_180005B3E
0x18000568f  lea     rdx, [rsi+8]; ppwsz
0x180005693  mov     [rsi], ebx
0x180005695  mov     rcx, r8; psz
0x180005698  call    cs:__imp_SHStrDupW
0x18000569e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056a5  mov     ebx, eax
0x1800056a7  test    eax, eax
0x1800056a9  js      loc_180005AD9
0x1800056af  mov     r13d, ebx
0x1800056b2  test    ebx, ebx
0x1800056b4  js      loc_180005B0E
0x1800056ba  mov     rcx, [rsp+3C8h+psz]; pv
0x1800056bf  call    cs:__imp_CoTaskMemFree
0x1800056c5  test    r13d, r13d
0x1800056c8  js      loc_18000597A
0x1800056ce  mov     eax, r13d
0x1800056d1  mov     rcx, [rsp+3C8h+var_58]
0x1800056d9  xor     rcx, rsp; StackCookie
0x1800056dc  call    __security_check_cookie
0x1800056e1  add     rsp, 388h
0x1800056e8  pop     r15
0x1800056ea  pop     r14
0x1800056ec  pop     r13
0x1800056ee  pop     r12
0x1800056f0  pop     rdi
0x1800056f1  pop     rsi
0x1800056f2  pop     rbp
0x1800056f3  pop     rbx
0x1800056f4  retn
0x1800056f5  lea     rdx, [rsi+8]; ppwsz
0x1800056f9  mov     [rsi], ebx
0x1800056fb  lea     rcx, [rsp+3C8h+var_268]; psz
0x180005703  call    cs:__imp_SHStrDupW
0x180005709  mov     rcx, cs:WPP_GLOBAL_Control
0x180005710  mov     ebx, eax
0x180005712  test    eax, eax
0x180005714  js      loc_180005A74
0x18000571a  mov     r13d, ebx
0x18000571d  test    ebx, ebx
0x18000571f  jns     short loc_1800056D1
0x180005721  jmp     loc_180005AA9
0x180005726  mov     r11, cs:WPP_GLOBAL_Control
0x18000572d  mov     r13d, r8d
0x180005730  jmp     short loc_180005756
0x180005732  xor     eax, eax
0x180005734  lea     r10, pszSrc; "\\"
0x18000573b  test    rcx, rcx
0x18000573e  mov     edx, r13d
0x180005741  mov     r9, r15
0x180005744  cmovnz  edx, eax
0x180005747  sub     r9, rcx
0x18000574a  test    rcx, rcx
0x18000574d  cmovz   r9, rax
0x180005751  jnz     short loc_180005785
0x180005753  mov     r13d, edx
0x180005756  cmp     r11, rdi
0x180005759  jz      loc_1800056BA
0x18000575f  test    byte ptr [r11+1Ch], 2
0x180005764  jz      loc_1800056BA
0x18000576a  mov     rcx, [r11+10h]
0x18000576e  mov     edx, 29h ; ')'
0x180005773  mov     [rsp+3C8h+var_3A0], r13d
0x180005778  mov     r9, rbx
0x18000577b  mov     [rsp+3C8h+var_3A8], r10
0x180005780  jmp     loc_180005B76
0x180005785  mov     rdx, r15
0x180005788  mov     rcx, r12
0x18000578b  sub     rdx, r9
0x18000578e  mov     r8, r10
0x180005791  lea     r9, [rbx+r9*2]
0x180005795  jz      loc_180005577
0x18000579b  nop     dword ptr [rax+rax+00h]
0x1800057a0  test    rcx, rcx
0x1800057a3  jz      loc_180005577
0x1800057a9  movzx   eax, word ptr [r8]
0x1800057ad  test    ax, ax
0x1800057b0  jz      loc_180005577
0x1800057b6  mov     [r9], ax
0x1800057ba  add     r8, 2
0x1800057be  add     r9, 2
0x1800057c2  dec     rcx
0x1800057c5  sub     rdx, 1
0x1800057c9  jnz     short loc_1800057A0
0x1800057cb  jmp     loc_180005577
0x1800057d0  test    bpl, 1
0x1800057d4  jnz     loc_18000556E
0x1800057da  mov     ecx, 1040h; cb
0x1800057df  call    cs:__imp_CoTaskMemAlloc
0x1800057e5  mov     [rsp+3C8h+psz], rax
0x1800057ea  test    rax, rax
0x1800057ed  jz      loc_1800059BA
0x1800057f3  xor     edx, edx; Val
0x1800057f5  mov     r8d, 1040h; Size
0x1800057fb  mov     rcx, rax; void *
0x1800057fe  call    memset_0
0x180005803  mov     rbx, [rdi+30h]
0x180005807  call    SHCoInitialize
0x18000580c  mov     esi, eax
0x18000580e  lea     r9, [rsp+3C8h+ppidlLast]; ppidlLast
0x180005813  xor     eax, eax
0x180005815  lea     r8, [rsp+3C8h+ppv]; ppv
0x18000581a  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180005821  mov     [rsp+3C8h+ppv], rax
0x180005826  mov     rcx, rbx; pidl
0x180005829  mov     [rsp+3C8h+ppidlLast], rax
0x18000582e  call    cs:__imp_SHBindToParent
0x180005834  mov     ebx, eax
0x180005836  test    eax, eax
0x180005838  js      loc_180005919
0x18000583e  mov     rcx, [rsp+3C8h+psz]
0x180005843  xor     eax, eax
0x180005845  mov     rdi, [rsp+3C8h+ppidlLast]
0x18000584a  xor     edx, edx; Val
0x18000584c  mov     rbx, [rsp+3C8h+ppv]
0x180005851  mov     r8d, 110h; Size
0x180005857  mov     [rcx], ax
0x18000585a  lea     rcx, [rsp+3C8h+pstr]; void *
0x18000585f  call    memset_0
0x180005864  mov     rax, [rbx]
0x180005867  lea     r9, [rsp+3C8h+pstr]
0x18000586c  mov     r8d, ebp
0x18000586f  mov     rdx, rdi
0x180005872  mov     rcx, rbx
0x180005875  mov     rax, [rax+58h]
0x180005879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587e  mov     ebx, eax
0x180005880  test    eax, eax
0x180005882  js      loc_1800059C9
0x180005888  mov     r8, [rsp+3C8h+psz]; pszBuf
0x18000588d  lea     rcx, [rsp+3C8h+pstr]; pstr
0x180005892  mov     r9d, r15d; cchBuf
0x180005895  mov     rdx, rdi; pidl
0x180005898  call    cs:__imp_StrRetToBufW
0x18000589e  mov     ebx, eax
0x1800058a0  test    eax, eax
0x1800058a2  js      loc_1800059C9
0x1800058a8  lea     rdi, WPP_GLOBAL_Control
0x1800058af  mov     r11, cs:WPP_GLOBAL_Control
0x1800058b6  mov     rcx, [rsp+3C8h+ppv]
0x1800058bb  test    rcx, rcx
0x1800058be  jz      short loc_1800058DC
0x1800058c0  mov     rax, [rcx]
0x1800058c3  mov     rax, [rax+10h]
0x1800058c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058cc  mov     [rsp+3C8h+ppv], 0
0x1800058d5  mov     r11, cs:WPP_GLOBAL_Control
0x1800058dc  test    esi, esi
0x1800058de  js      short loc_1800058ED
0x1800058e0  call    cs:__imp_CoUninitialize
0x1800058e6  mov     r11, cs:WPP_GLOBAL_Control
0x1800058ed  test    ebx, ebx
0x1800058ef  js      loc_180005A08
0x1800058f5  mov     rbx, [rsp+3C8h+psz]
0x1800058fa  mov     rcx, r15
0x1800058fd  mov     rax, rbx
0x180005900  cmp     word ptr [rax], 0
0x180005904  jz      loc_180005732
0x18000590a  add     rax, 2
0x18000590e  sub     rcx, 1
0x180005912  jnz     short loc_180005900
0x180005914  jmp     loc_180005732
0x180005919  lea     rdi, WPP_GLOBAL_Control
0x180005920  jmp     short loc_1800058D5
0x180005922  bt      ebp, 0Fh
0x180005926  jnb     short loc_180005952
0x180005928  mov     eax, [r14+1Ah]
0x18000592c  mov     edx, 104h; unsigned __int64
0x180005931  mov     ecx, [r14+1Eh]
0x180005935  add     rax, 13h
0x180005939  add     rcx, rax
0x18000593c  lea     r8, [r14+rcx*2]; unsigned __int16 *
0x180005940  lea     rcx, [rsp+3C8h+var_268]; unsigned __int16 *
0x180005948  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000594d  jmp     loc_1800055F8
0x180005952  mov     r9d, 104h; unsigned int
0x180005958  lea     r8, [rsp+3C8h+var_268]; unsigned __int16 *
0x180005960  mov     rdx, r14; struct DEVICEITEM *
0x180005963  call    ?_Name@CDeviceFolder@@AEAAPEBGPEFBUDEVICEITEM@@PEAGI@Z; CDeviceFolder::_Name(DEVICEITEM const *,ushort *,uint)
0x180005968  jmp     loc_1800055F8
0x18000596d  mov     r13d, 80004003h
0x180005973  lea     rdi, WPP_GLOBAL_Control
0x18000597a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005981  cmp     rcx, rdi
0x180005984  jz      loc_1800056CE
0x18000598a  test    byte ptr [rcx+1Ch], 2
0x18000598e  jz      loc_1800056CE
0x180005994  mov     rcx, [rcx+10h]
0x180005998  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x18000599f  mov     edx, 2Dh ; '-'
0x1800059a4  mov     r9d, r13d
  ... truncated ...
```
