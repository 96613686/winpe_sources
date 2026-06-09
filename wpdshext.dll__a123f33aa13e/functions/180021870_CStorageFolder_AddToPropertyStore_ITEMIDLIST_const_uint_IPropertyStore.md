# CStorageFolder::_AddToPropertyStore(_ITEMIDLIST const *,uint,IPropertyStore *)

- ea: `0x180021870`
- end: `0x180021c54`
- name: `?_AddToPropertyStore@CStorageFolder@@EEAAJPEFBU_ITEMIDLIST@@IPEAUIPropertyStore@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(CStorageFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180009890`
- `0x180021870`
- `0x180021c5c`
- `0x180021cec`
- `0x18002ff5c`
- `0x180035590`
- `0x1800671e8`
- `0x1800674a8`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180021a3c`
- `SHLWAPI!PathFindFileNameW` at `0x180021a3c`
- `ole32!CoTaskMemAlloc` at `0x180021a6e`
- `ole32!CoTaskMemAlloc` at `0x180021b16`
- `ole32!CoTaskMemAlloc` at `0x180021a6e`
- `ole32!CoTaskMemAlloc` at `0x180021b16`
- `ole32!PropVariantClear` at `0x18002190c`
- `ole32!PropVariantClear` at `0x18002198e`
- `ole32!PropVariantClear` at `0x180021a47`
- `ole32!PropVariantClear` at `0x180021af6`
- `ole32!PropVariantClear` at `0x180021bfd`
- `ole32!PropVariantClear` at `0x18002190c`
- `ole32!PropVariantClear` at `0x18002198e`
- `ole32!PropVariantClear` at `0x180021a47`
- `ole32!PropVariantClear` at `0x180021af6`
- `ole32!PropVariantClear` at `0x180021bfd`

## pseudocode

```c
__int64 __fastcall CStorageFolder::_AddToPropertyStore(
        CStorageFolder *this,
        const struct _ITEMIDLIST *a2,
        int a3,
        struct IPropertyStore *a4)
{
  int v7; // ebx
  const struct STORAGEITEM *v8; // rax
  const struct STORAGEITEM *v9; // rsi
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  WCHAR *v14; // r8
  __int64 v15; // rcx
  WCHAR *v16; // rax
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rbx
  void *v22; // rax
  CStorageFolder *v23; // rcx
  unsigned int v24; // r9d
  __int64 v25; // rdi
  void *v26; // rax
  PROPVARIANT pvar; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v29[2]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  if ( !a2 )
    goto LABEL_2;
  if ( !a4 )
    goto LABEL_2;
  v8 = CStorageFolder::_IsValid(this, a2);
  v9 = v8;
  if ( !v8 )
    goto LABEL_2;
  if ( !a3 )
  {
    v14 = (WCHAR *)((char *)v8 + 54);
    v15 = 2147483646;
    v16 = pszPath;
    v17 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*v14 )
        break;
      *v16++ = *v14++;
      --v15;
      --v17;
    }
    while ( v17 );
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
    PathFindFileNameW(pszPath);
    PropVariantClear(&pvar);
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( pszPath[v20] );
    v21 = 2 * v20 + 2;
    v22 = CoTaskMemAlloc(v21);
    pvar.hVal.QuadPart = (LONGLONG)v22;
    if ( v22 )
    {
      memcpy_s(v22, v21, pszPath, v21);
      pvar.vt = 31;
      v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
              a4,
              &PKEY_ItemNameDisplay,
              &pvar);
      v7 = v10;
      if ( v10 >= 0 )
      {
        CStorageFolder::_Type(v23, v9, pszPath, v24);
        PropVariantClear(&pvar);
        do
          ++v19;
        while ( pszPath[v19] );
        v25 = 2 * v19 + 2;
        v26 = CoTaskMemAlloc(v25);
        pvar.hVal.QuadPart = (LONGLONG)v26;
        if ( v26 )
        {
          memcpy_s(v26, v25, pszPath, v25);
          pvar.vt = 31;
          v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                  a4,
                  &PKEY_ItemTypeText,
                  &pvar);
          v7 = v10;
          if ( v10 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = 152;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v13 = 2147942414LL;
          memset(&pvar, 0, sizeof(pvar));
          v7 = -2147024882;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 151;
            goto LABEL_44;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v12 = 150;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v13 = 2147942414LL;
      memset(&pvar, 0, sizeof(pvar));
      v7 = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = 149;
        goto LABEL_44;
      }
    }
    goto LABEL_45;
  }
  if ( a3 != 2 )
  {
LABEL_2:
    v7 = -2147024809;
    goto LABEL_45;
  }
  v29[0] = 0;
  v7 = 0;
  if ( (int)CStorageFolder::_GetPercentFull(this, v8, v29) < 0
    || (PropVariantClear(&pvar),
        pvar.vt = 19,
        pvar.lVal = v29[0],
        v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
                a4,
                &PKEY_PercentFull,
                &pvar),
        v7 = v10,
        v10 >= 0) )
  {
    *(_QWORD *)v29 = 0;
    if ( (int)CStorageFolder::_GetFreeSpace(this, v9, (unsigned __int64 *)v29) >= 0 )
    {
      PropVariantClear(&pvar);
      pvar.vt = 21;
      pvar.hVal.QuadPart = *(_QWORD *)v29;
      v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a4->lpVtbl->SetValue)(
              a4,
              &PKEY_FreeSpace,
              &pvar);
      v7 = v10;
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v12 = 154;
          goto LABEL_12;
        }
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 153;
LABEL_12:
      v13 = (unsigned int)v10;
LABEL_44:
      WPP_SF_d(v11[2], v12, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v13);
    }
  }
LABEL_45:
  PropVariantClear(&pvar);
  if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      155,
      WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021870  push    rbp
0x180021872  push    rbx
0x180021873  push    rsi
0x180021874  push    rdi
0x180021875  push    r13
0x180021877  push    r14
0x180021879  push    r15
0x18002187b  lea     rbp, [rsp-160h]
0x180021883  sub     rsp, 260h
0x18002188a  mov     rax, cs:__security_cookie
0x180021891  xor     rax, rsp
0x180021894  mov     [rbp+190h+var_40], rax
0x18002189b  xor     eax, eax
0x18002189d  lea     r13, WPP_GLOBAL_Control
0x1800218a4  xor     r15d, r15d
0x1800218a7  mov     qword ptr [rsp+290h+pvar+10h], rax
0x1800218ac  xorps   xmm0, xmm0
0x1800218af  mov     r14, r9
0x1800218b2  mov     ebx, r8d
0x1800218b5  mov     rdi, rcx
0x1800218b8  movups  xmmword ptr [rsp+290h+pvar], xmm0
0x1800218bd  test    rdx, rdx
0x1800218c0  jnz     short loc_1800218CC
0x1800218c2  mov     ebx, 80070057h
0x1800218c7  jmp     loc_180021BF8
0x1800218cc  test    r14, r14
0x1800218cf  jz      short loc_1800218C2
0x1800218d1  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x1800218d6  mov     rsi, rax
0x1800218d9  test    rax, rax
0x1800218dc  jz      short loc_1800218C2
0x1800218de  test    ebx, ebx
0x1800218e0  jz      loc_1800219F1
0x1800218e6  cmp     ebx, 2
0x1800218e9  jnz     short loc_1800218C2
0x1800218eb  lea     r8, [rsp+290h+var_258]; unsigned int *
0x1800218f0  mov     [rsp+290h+var_258], r15d
0x1800218f5  mov     rdx, rax; struct STORAGEITEM *
0x1800218f8  mov     rcx, rdi; this
0x1800218fb  mov     ebx, r15d
0x1800218fe  call    ?_GetPercentFull@CStorageFolder@@AEAAJPEFBUSTORAGEITEM@@PEAK@Z; CStorageFolder::_GetPercentFull(STORAGEITEM const *,ulong *)
0x180021903  test    eax, eax
0x180021905  js      short loc_18002196C
0x180021907  lea     rcx, [rsp+290h+pvar]; pvar
0x18002190c  call    cs:__imp_PropVariantClear
0x180021912  mov     eax, 13h
0x180021917  lea     r8, [rsp+290h+pvar]
0x18002191c  mov     word ptr [rsp+290h+pvar], ax
0x180021921  lea     rdx, PKEY_PercentFull
0x180021928  mov     eax, [rsp+290h+var_258]
0x18002192c  mov     rcx, r14
0x18002192f  mov     dword ptr [rsp+290h+pvar+8], eax
0x180021933  mov     rax, [r14]
0x180021936  mov     rax, [rax+30h]
0x18002193a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002193f  mov     ebx, eax
0x180021941  test    eax, eax
0x180021943  jns     short loc_18002196C
0x180021945  mov     rcx, cs:WPP_GLOBAL_Control
0x18002194c  cmp     rcx, r13
0x18002194f  jz      loc_180021BF8
0x180021955  test    byte ptr [rcx+1Ch], 2
0x180021959  jz      loc_180021BF8
0x18002195f  mov     edx, 99h
0x180021964  mov     r9d, eax
0x180021967  jmp     loc_180021BE8
0x18002196c  lea     r8, [rsp+290h+var_258]; unsigned __int64 *
0x180021971  mov     qword ptr [rsp+290h+var_258], r15
0x180021976  mov     rdx, rsi; struct STORAGEITEM *
0x180021979  mov     rcx, rdi; this
0x18002197c  call    ?_GetFreeSpace@CStorageFolder@@AEAAJPEFBUSTORAGEITEM@@PEA_K@Z; CStorageFolder::_GetFreeSpace(STORAGEITEM const *,unsigned __int64 *)
0x180021981  test    eax, eax
0x180021983  js      loc_180021BF8
0x180021989  lea     rcx, [rsp+290h+pvar]; pvar
0x18002198e  call    cs:__imp_PropVariantClear
0x180021994  mov     eax, 15h
0x180021999  lea     r8, [rsp+290h+pvar]
0x18002199e  mov     word ptr [rsp+290h+pvar], ax
0x1800219a3  lea     rdx, PKEY_FreeSpace
0x1800219aa  mov     rax, qword ptr [rsp+290h+var_258]
0x1800219af  mov     rcx, r14
0x1800219b2  mov     qword ptr [rsp+290h+pvar+8], rax
0x1800219b7  mov     rax, [r14]
0x1800219ba  mov     rax, [rax+30h]
0x1800219be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219c3  mov     ebx, eax
0x1800219c5  test    eax, eax
0x1800219c7  jns     loc_180021BF8
0x1800219cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219d4  cmp     rcx, r13
0x1800219d7  jz      loc_180021BF8
0x1800219dd  test    byte ptr [rcx+1Ch], 2
0x1800219e1  jz      loc_180021BF8
0x1800219e7  mov     edx, 9Ah
0x1800219ec  jmp     loc_180021964
0x1800219f1  lea     r8, [rax+36h]
0x1800219f5  mov     ecx, 7FFFFFFEh
0x1800219fa  lea     rax, [rsp+290h+pszPath]
0x1800219ff  mov     edx, 104h
0x180021a04  test    rcx, rcx
0x180021a07  jz      short loc_180021A28
0x180021a09  movzx   r9d, word ptr [r8]
0x180021a0d  test    r9w, r9w
0x180021a11  jz      short loc_180021A28
0x180021a13  mov     [rax], r9w
0x180021a17  add     r8, 2
0x180021a1b  add     rax, 2
0x180021a1f  dec     rcx
0x180021a22  sub     rdx, 1
0x180021a26  jnz     short loc_180021A04
0x180021a28  test    rdx, rdx
0x180021a2b  lea     rcx, [rax-2]
0x180021a2f  cmovnz  rcx, rax
0x180021a33  mov     [rcx], r15w
0x180021a37  lea     rcx, [rsp+290h+pszPath]; pszPath
0x180021a3c  call    cs:__imp_PathFindFileNameW
0x180021a42  lea     rcx, [rsp+290h+pvar]; pvar
0x180021a47  call    cs:__imp_PropVariantClear
0x180021a4d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180021a51  lea     rcx, [rsp+290h+pszPath]
0x180021a56  mov     rax, rdi
0x180021a59  inc     rax
0x180021a5c  cmp     [rcx+rax*2], r15w
0x180021a61  jnz     short loc_180021A59
0x180021a63  lea     rbx, ds:2[rax*2]
0x180021a6b  mov     rcx, rbx; cb
0x180021a6e  call    cs:__imp_CoTaskMemAlloc
0x180021a74  mov     qword ptr [rsp+290h+pvar+8], rax
0x180021a79  test    rax, rax
0x180021a7c  jz      loc_180021BB9
0x180021a82  mov     r9, rbx; SourceSize
0x180021a85  lea     r8, [rsp+290h+pszPath]; Source
0x180021a8a  mov     rdx, rbx; DestinationSize
0x180021a8d  mov     rcx, rax; Destination
0x180021a90  call    memcpy_s
0x180021a95  mov     eax, 1Fh
0x180021a9a  lea     r8, [rsp+290h+pvar]
0x180021a9f  mov     word ptr [rsp+290h+pvar], ax
0x180021aa4  lea     rdx, PKEY_ItemNameDisplay
0x180021aab  mov     rax, [r14]
0x180021aae  mov     rcx, r14
0x180021ab1  mov     rax, [rax+30h]
0x180021ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aba  mov     ebx, eax
0x180021abc  test    eax, eax
0x180021abe  jns     short loc_180021AE4
0x180021ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ac7  cmp     rcx, r13
0x180021aca  jz      loc_180021BF8
0x180021ad0  test    byte ptr [rcx+1Ch], 2
0x180021ad4  jz      loc_180021BF8
0x180021ada  mov     edx, 96h
0x180021adf  jmp     loc_180021964
0x180021ae4  lea     r8, [rsp+290h+pszPath]; unsigned __int16 *
0x180021ae9  mov     rdx, rsi; struct STORAGEITEM *
0x180021aec  call    ?_Type@CStorageFolder@@AEAAPEBGPEFBUSTORAGEITEM@@PEAGI@Z; CStorageFolder::_Type(STORAGEITEM const *,ushort *,uint)
0x180021af1  lea     rcx, [rsp+290h+pvar]; pvar
0x180021af6  call    cs:__imp_PropVariantClear
0x180021afc  lea     rax, [rsp+290h+pszPath]
0x180021b01  inc     rdi
0x180021b04  cmp     [rax+rdi*2], r15w
0x180021b09  jnz     short loc_180021B01
0x180021b0b  lea     rdi, ds:2[rdi*2]
0x180021b13  mov     rcx, rdi; cb
0x180021b16  call    cs:__imp_CoTaskMemAlloc
0x180021b1c  mov     qword ptr [rsp+290h+pvar+8], rax
0x180021b21  test    rax, rax
0x180021b24  jz      short loc_180021B88
0x180021b26  mov     r9, rdi; SourceSize
0x180021b29  lea     r8, [rsp+290h+pszPath]; Source
0x180021b2e  mov     rdx, rdi; DestinationSize
0x180021b31  mov     rcx, rax; Destination
0x180021b34  call    memcpy_s
0x180021b39  mov     eax, 1Fh
0x180021b3e  lea     r8, [rsp+290h+pvar]
0x180021b43  mov     word ptr [rsp+290h+pvar], ax
0x180021b48  lea     rdx, PKEY_ItemTypeText
0x180021b4f  mov     rax, [r14]
0x180021b52  mov     rcx, r14
0x180021b55  mov     rax, [rax+30h]
0x180021b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b5e  mov     ebx, eax
0x180021b60  test    eax, eax
0x180021b62  jns     loc_180021BF8
0x180021b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b6f  cmp     rcx, r13
0x180021b72  jz      loc_180021BF8
0x180021b78  test    byte ptr [rcx+1Ch], 2
0x180021b7c  jz      short loc_180021BF8
0x180021b7e  mov     edx, 98h
0x180021b83  jmp     loc_180021964
0x180021b88  xorps   xmm0, xmm0
0x180021b8b  xor     eax, eax
0x180021b8d  mov     r9d, 8007000Eh
0x180021b93  mov     qword ptr [rsp+290h+pvar+10h], rax
0x180021b98  movups  xmmword ptr [rsp+290h+pvar], xmm0
0x180021b9d  mov     ebx, r9d
0x180021ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ba7  cmp     rcx, r13
0x180021baa  jz      short loc_180021BF8
0x180021bac  test    byte ptr [rcx+1Ch], 2
0x180021bb0  jz      short loc_180021BF8
0x180021bb2  mov     edx, 97h
0x180021bb7  jmp     short loc_180021BE8
0x180021bb9  xorps   xmm0, xmm0
0x180021bbc  xor     eax, eax
0x180021bbe  mov     r9d, 8007000Eh
0x180021bc4  mov     qword ptr [rsp+290h+pvar+10h], rax
0x180021bc9  movups  xmmword ptr [rsp+290h+pvar], xmm0
0x180021bce  mov     ebx, r9d
0x180021bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bd8  cmp     rcx, r13
0x180021bdb  jz      short loc_180021BF8
0x180021bdd  test    byte ptr [rcx+1Ch], 2
0x180021be1  jz      short loc_180021BF8
0x180021be3  mov     edx, 95h
0x180021be8  mov     rcx, [rcx+10h]
0x180021bec  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180021bf3  call    WPP_SF_d
0x180021bf8  lea     rcx, [rsp+290h+pvar]; pvar
0x180021bfd  call    cs:__imp_PropVariantClear
0x180021c03  test    ebx, ebx
0x180021c05  jns     short loc_180021C31
0x180021c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c0e  cmp     rcx, r13
0x180021c11  jz      short loc_180021C31
0x180021c13  test    byte ptr [rcx+1Ch], 2
0x180021c17  jz      short loc_180021C31
0x180021c19  mov     rcx, [rcx+10h]
0x180021c1d  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180021c24  mov     edx, 9Bh
0x180021c29  mov     r9d, ebx
0x180021c2c  call    WPP_SF_d
0x180021c31  mov     eax, ebx
0x180021c33  mov     rcx, [rbp+190h+var_40]
0x180021c3a  xor     rcx, rsp; StackCookie
0x180021c3d  call    __security_check_cookie
0x180021c42  add     rsp, 260h
0x180021c49  pop     r15
0x180021c4b  pop     r14
0x180021c4d  pop     r13
0x180021c4f  pop     rdi
0x180021c50  pop     rsi
0x180021c51  pop     rbx
0x180021c52  pop     rbp
0x180021c53  retn
```
