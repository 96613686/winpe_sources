# CDeviceCache::s_AddToCache(ushort const *,_ITEMIDLIST *,_ITEMIDLIST *)

- ea: `0x18000ce68`
- end: `0x18000d332`
- name: `?s_AddToCache@CDeviceCache@@CAJPEBGPEFAU_ITEMIDLIST@@1@Z`
- size: `1226`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _ITEMIDLIST *, struct _ITEMIDLIST *)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ba84`
- `0x18000c180`
- `0x180057c90`

## callees

- `0x18000cc48`
- `0x18000ce68`
- `0x18000d338`
- `0x18000d610`
- `0x18000e760`
- `0x18001d3f0`
- `0x1800285c8`
- `0x180028758`
- `0x1800287d0`
- `0x18002ff5c`
- `0x180035590`
- `0x180039ef8`
- `0x1800554bc`
- `0x180055b2c`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000d2ba`
- `KERNEL32!LocalFree` at `0x18000d2ba`
- `KERNEL32!EnterCriticalSection` at `0x18000ceaf`
- `KERNEL32!EnterCriticalSection` at `0x18000ceaf`
- `KERNEL32!LeaveCriticalSection` at `0x18000d2d5`
- `KERNEL32!LeaveCriticalSection` at `0x18000d2d5`
- `KERNEL32!LocalAlloc` at `0x18000cf69`
- `KERNEL32!LocalAlloc` at `0x18000cf69`
- `KERNEL32!GetSystemTime` at `0x18000d0be`
- `KERNEL32!GetSystemTime` at `0x18000d0be`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d0cc`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d0cc`
- `ole32!CoCreateInstance` at `0x18000d129`
- `ole32!CoCreateInstance` at `0x18000d129`
- `SHELL32!__imp_ILFree` at `0x18000d2c8`
- `SHELL32!__imp_ILFree` at `0x18000d2c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDeviceCache::s_AddToCache(
        const unsigned __int16 *a1,
        struct _ITEMIDLIST *a2,
        struct _ITEMIDLIST *a3)
{
  unsigned __int16 *v6; // rsi
  struct _ITEMIDLIST *v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  __int64 v15; // r9
  unsigned int v16; // r14d
  __int64 v17; // rdx
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r8
  unsigned __int16 *v20; // rax
  unsigned __int16 v21; // r9
  unsigned __int16 *v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  struct _FILETIME *Item; // r14
  unsigned int v26; // r14d
  const struct std::nothrow_t *v27; // rdx
  DEVITEM_CACHE *v28; // rax
  __int64 v29; // rdx
  DEVITEM_CACHE *v30; // r14
  unsigned int v31; // edx
  struct _ITEMIDLIST *ppv; // [rsp+40h] [rbp-40h] BYREF
  int v34; // [rsp+48h] [rbp-38h] BYREF
  int v35; // [rsp+4Ch] [rbp-34h] BYREF
  unsigned int v36; // [rsp+50h] [rbp-30h] BYREF
  DEVITEM_CACHE *v37; // [rsp+58h] [rbp-28h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  SystemTime = 0;
  v6 = 0;
  v7 = 0;
  ppv = 0;
  EnterCriticalSection(&g_csDeviceCache);
  v8 = CDeviceCache::s_EnsureDeviceCache();
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 17;
      v12 = (unsigned int)v8;
LABEL_72:
      WPP_SF_d(v10[2], v11, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, v12);
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  if ( !a1 )
  {
    v9 = -2147024809;
LABEL_68:
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_73;
    v11 = 18;
    goto LABEL_71;
  }
  v13 = 0x7FFFFFFF;
  v14 = a1;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v9 = -2147024809;
  v15 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
  {
    v9 = -2147024809;
    goto LABEL_68;
  }
  v16 = v15 + 1;
  if ( (int)v15 + 1 < (unsigned int)v15 )
  {
    v9 = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids);
    goto LABEL_73;
  }
  if ( 2 * (unsigned __int64)(2 * v16) > 0xFFFFFFFF )
  {
    v9 = -2147024362;
LABEL_61:
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_73;
    v11 = 20;
LABEL_71:
    v12 = v9;
    goto LABEL_72;
  }
  v6 = (unsigned __int16 *)LocalAlloc(0x40u, 4 * v16);
  if ( !v6 )
  {
    v9 = -2147024882;
    goto LABEL_61;
  }
  v17 = v16;
  v18 = 2147483646;
  if ( v16 - 1 > 0x7FFFFFFE )
  {
    v23 = 2147942487LL;
    if ( v16 )
    {
      *v6 = 0;
      goto LABEL_24;
    }
  }
  else
  {
    v19 = a1;
    v20 = v6;
    do
    {
      if ( !v18 )
        break;
      v21 = *v19;
      if ( !*v19 )
        break;
      ++v19;
      *v20++ = v21;
      --v18;
      --v17;
    }
    while ( v17 );
    v22 = v20 - 1;
    if ( v17 )
      v22 = v20;
    *v22 = 0;
    v23 = v17 == 0 ? 0x8007007A : 0;
  }
  v9 = v23;
  if ( (int)v23 < 0 )
  {
LABEL_24:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
        (_DWORD)a1,
        v16,
        v23);
    goto LABEL_73;
  }
  if ( a2 && a3 )
  {
    v24 = SHILCombine(a2, a3, &ppv);
    v9 = v24;
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
          (unsigned int)v24);
      v7 = ppv;
      goto LABEL_73;
    }
    v7 = ppv;
  }
  Item = (struct _FILETIME *)CDeviceCache::_FindItem((CDeviceCache *)v23, a1);
  if ( Item )
  {
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, Item + 1);
    if ( v7 && !CDeviceCache::s_AddToPidlCache((struct DEVITEM_CACHE *)Item, v7) )
      v7 = 0;
  }
  else
  {
    v26 = 60000;
    v35 = 0;
    v36 = 0;
    v34 = 0;
    ppv = 0;
    if ( CoCreateInstance(
           &CLSID_PortableDeviceManager,
           0,
           1u,
           &GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40,
           (LPVOID *)&ppv) >= 0 )
    {
      v35 = 4;
      v34 = 0;
      if ( (*(int (__fastcall **)(struct _ITEMIDLIST *, unsigned __int16 *, const wchar_t *, unsigned int *, int *, int *))(*(_QWORD *)&ppv->mkid.cb + 64LL))(
             ppv,
             v6,
             L"PortableDeviceNameSpaceTimeout",
             &v36,
             &v35,
             &v34) >= 0
        && v34 == 4 )
      {
        v26 = v36;
      }
    }
    v28 = (DEVITEM_CACHE *)operator new(0xA8u, v27);
    v37 = v28;
    if ( v28 )
      v30 = DEVITEM_CACHE::DEVITEM_CACHE(v28, v26);
    else
      v30 = 0;
    if ( v30 )
    {
      *(_QWORD *)v30 = v6;
      if ( v7 && !CDeviceCache::s_AddToPidlCache(v30, v7) )
        v7 = 0;
      if ( (unsigned int)IsolationAwareDPA_InsertPtr(*((_QWORD *)g_pDeviceCache + 1), v29, v30) == -1 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        DEVITEM_CACHE::`scalar deleting destructor'(v30, v31);
        v9 = -2147467259;
        v6 = 0;
      }
      else
      {
        v6 = 0;
        if ( ppv )
          (*(void (__fastcall **)(struct _ITEMIDLIST *))(*(_QWORD *)&ppv->mkid.cb + 16LL))(ppv);
      }
    }
    else
    {
      v9 = -2147024882;
      if ( ppv )
        (*(void (__fastcall **)(struct _ITEMIDLIST *))(*(_QWORD *)&ppv->mkid.cb + 16LL))(ppv);
    }
  }
LABEL_73:
  LocalFree(v6);
  if ( v7 )
    ILFree(v7);
  LeaveCriticalSection(&g_csDeviceCache);
  if ( (v9 & 0x80000000) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18000ce68  mov     [rsp-38h+arg_18], rbx
0x18000ce6d  push    rbp
0x18000ce6e  push    rsi
0x18000ce6f  push    rdi
0x18000ce70  push    r12
0x18000ce72  push    r13
0x18000ce74  push    r14
0x18000ce76  push    r15
0x18000ce78  mov     rbp, rsp
0x18000ce7b  sub     rsp, 80h
0x18000ce82  mov     rax, cs:__security_cookie
0x18000ce89  xor     rax, rsp
0x18000ce8c  mov     [rbp+var_10], rax
0x18000ce90  mov     r13, r8
0x18000ce93  mov     r12, rdx
0x18000ce96  mov     r15, rcx
0x18000ce99  xorps   xmm0, xmm0
0x18000ce9c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000cea0  xor     esi, esi
0x18000cea2  xor     edi, edi
0x18000cea4  mov     [rbp+var_40], rdi
0x18000cea8  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ceaf  call    cs:__imp_EnterCriticalSection
0x18000ceb5  call    ?s_EnsureDeviceCache@CDeviceCache@@CAJXZ; CDeviceCache::s_EnsureDeviceCache(void)
0x18000ceba  mov     ebx, eax
0x18000cebc  lea     r11, WPP_GLOBAL_Control
0x18000cec3  xor     r10d, r10d
0x18000cec6  test    eax, eax
0x18000cec8  jns     short loc_18000CEEF
0x18000ceca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ced1  cmp     rcx, r11
0x18000ced4  jz      loc_18000D2B0
0x18000ceda  test    byte ptr [rcx+1Ch], 2
0x18000cede  jz      loc_18000D2B0
0x18000cee4  lea     edx, [rsi+11h]
0x18000cee7  mov     r9d, eax
0x18000ceea  jmp     loc_18000D2A0
0x18000ceef  test    r15, r15
0x18000cef2  jz      loc_18000D281
0x18000cef8  mov     r8d, 7FFFFFFFh
0x18000cefe  mov     ecx, r8d
0x18000cf01  mov     rax, r15
0x18000cf04  cmp     [rax], r10w
0x18000cf08  jz      short loc_18000CF14
0x18000cf0a  add     rax, 2
0x18000cf0e  sub     rcx, 1
0x18000cf12  jnz     short loc_18000CF04
0x18000cf14  mov     rax, rcx
0x18000cf17  neg     rax
0x18000cf1a  sbb     edx, edx
0x18000cf1c  not     edx
0x18000cf1e  mov     ebx, 80070057h
0x18000cf23  and     edx, ebx
0x18000cf25  mov     rax, rcx
0x18000cf28  sub     r8, rcx
0x18000cf2b  neg     rax
0x18000cf2e  sbb     r9, r9
0x18000cf31  and     r9, r8
0x18000cf34  test    rcx, rcx
0x18000cf37  jnz     short loc_18000CF40
0x18000cf39  mov     ebx, edx
0x18000cf3b  jmp     loc_18000D286
0x18000cf40  lea     r14d, [r9+1]
0x18000cf44  cmp     r14d, r9d
0x18000cf47  jb      loc_18000D24F
0x18000cf4d  lea     ecx, [r14+r14]
0x18000cf51  add     rcx, rcx
0x18000cf54  mov     eax, 0FFFFFFFFh
0x18000cf59  cmp     rcx, rax
0x18000cf5c  ja      loc_18000D231
0x18000cf62  mov     edx, ecx; uBytes
0x18000cf64  mov     ecx, 40h ; '@'; uFlags
0x18000cf69  call    cs:__imp_LocalAlloc
0x18000cf6f  mov     rsi, rax
0x18000cf72  mov     ecx, 8007000Eh
0x18000cf77  xor     r10d, r10d
0x18000cf7a  test    rax, rax
0x18000cf7d  cmovnz  ecx, r10d
0x18000cf81  jnz     short loc_18000CF91
0x18000cf83  mov     ebx, ecx
0x18000cf85  lea     r11, WPP_GLOBAL_Control
0x18000cf8c  jmp     loc_18000D236
0x18000cf91  mov     edx, r14d
0x18000cf94  lea     eax, [r14-1]
0x18000cf98  mov     ecx, 7FFFFFFEh
0x18000cf9d  cmp     eax, ecx
0x18000cf9f  ja      loc_18000D038
0x18000cfa5  mov     r8, r15
0x18000cfa8  mov     rax, rsi
0x18000cfab  test    rcx, rcx
0x18000cfae  jz      short loc_18000CFCF
0x18000cfb0  movzx   r9d, word ptr [r8]
0x18000cfb4  test    r9w, r9w
0x18000cfb8  jz      short loc_18000CFCF
0x18000cfba  add     r8, 2
0x18000cfbe  mov     [rax], r9w
0x18000cfc2  add     rax, 2
0x18000cfc6  dec     rcx
0x18000cfc9  sub     rdx, 1
0x18000cfcd  jnz     short loc_18000CFAB
0x18000cfcf  lea     rcx, [rax-2]
0x18000cfd3  test    rdx, rdx
0x18000cfd6  cmovnz  rcx, rax
0x18000cfda  mov     [rcx], r10w
0x18000cfde  neg     rdx
0x18000cfe1  sbb     ecx, ecx
0x18000cfe3  not     ecx
0x18000cfe5  and     ecx, 8007007Ah; this
0x18000cfeb  mov     ebx, ecx
0x18000cfed  test    ecx, ecx
0x18000cfef  jns     short loc_18000D045
0x18000cff1  mov     rax, cs:WPP_GLOBAL_Control
0x18000cff8  lea     r13, WPP_GLOBAL_Control
0x18000cfff  cmp     rax, r13
0x18000d002  jz      loc_18000D2B7
0x18000d008  test    byte ptr [rax+1Ch], 2
0x18000d00c  jz      loc_18000D2B7
0x18000d012  mov     edx, 15h
0x18000d017  mov     dword ptr [rsp+80h+var_58], ecx
0x18000d01b  mov     dword ptr [rsp+80h+ppv], r14d
0x18000d020  mov     r9, r15
0x18000d023  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000d02a  mov     rcx, [rax+10h]
0x18000d02e  call    WPP_SF_Sdd
0x18000d033  jmp     loc_18000D2B7
0x18000d038  mov     ecx, ebx
0x18000d03a  test    r14d, r14d
0x18000d03d  jz      short loc_18000CFEB
0x18000d03f  mov     [rsi], r10w
0x18000d043  jmp     short loc_18000CFF1
0x18000d045  test    r12, r12
0x18000d048  jz      short loc_18000D0A7
0x18000d04a  test    r13, r13
0x18000d04d  jz      short loc_18000D0A7
0x18000d04f  lea     r8, [rbp+var_40]
0x18000d053  mov     rdx, r13
0x18000d056  mov     rcx, r12
0x18000d059  call    SHILCombine
0x18000d05e  mov     ebx, eax
0x18000d060  xor     r12d, r12d
0x18000d063  test    eax, eax
0x18000d065  jns     short loc_18000D0A1
0x18000d067  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d06e  lea     r13, WPP_GLOBAL_Control
0x18000d075  cmp     rcx, r13
0x18000d078  jz      short loc_18000D098
0x18000d07a  test    byte ptr [rcx+1Ch], 2
0x18000d07e  jz      short loc_18000D098
0x18000d080  lea     edx, [r12+16h]
0x18000d085  mov     r9d, eax
0x18000d088  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000d08f  mov     rcx, [rcx+10h]
0x18000d093  call    WPP_SF_d
0x18000d098  mov     rdi, [rbp+var_40]
0x18000d09c  jmp     loc_18000D2B7
0x18000d0a1  mov     rdi, [rbp+var_40]
0x18000d0a5  jmp     short loc_18000D0AA
0x18000d0a7  xor     r12d, r12d
0x18000d0aa  mov     rdx, r15; unsigned __int16 *
0x18000d0ad  call    ?_FindItem@CDeviceCache@@AEAAPEAUDEVITEM_CACHE@@PEBG@Z; CDeviceCache::_FindItem(ushort const *)
0x18000d0b2  mov     r14, rax
0x18000d0b5  test    rax, rax
0x18000d0b8  jz      short loc_18000D0F6
0x18000d0ba  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000d0be  call    cs:__imp_GetSystemTime
0x18000d0c4  lea     rdx, [r14+8]; lpFileTime
0x18000d0c8  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000d0cc  call    cs:__imp_SystemTimeToFileTime
0x18000d0d2  test    rdi, rdi
0x18000d0d5  jz      loc_18000D2B0
0x18000d0db  mov     rdx, rdi; struct _ITEMIDLIST *
0x18000d0de  mov     rcx, r14; struct DEVITEM_CACHE *
0x18000d0e1  call    ?s_AddToPidlCache@CDeviceCache@@CAJPEAUDEVITEM_CACHE@@PEFAU_ITEMIDLIST@@@Z; CDeviceCache::s_AddToPidlCache(DEVITEM_CACHE *,_ITEMIDLIST *)
0x18000d0e6  test    eax, eax
0x18000d0e8  jnz     loc_18000D2B0
0x18000d0ee  mov     rdi, r12
0x18000d0f1  jmp     loc_18000D2B0
0x18000d0f6  mov     r14d, 0EA60h
0x18000d0fc  mov     [rbp+var_34], r12d
0x18000d100  mov     [rbp+var_30], r12d
0x18000d104  mov     [rbp+var_38], r12d
0x18000d108  mov     [rbp+var_40], r12
0x18000d10c  lea     rax, [rbp+var_40]
0x18000d110  mov     [rsp+80h+ppv], rax; ppv
0x18000d115  lea     r9, _GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40; riid
0x18000d11c  xor     edx, edx; pUnkOuter
0x18000d11e  lea     r8d, [rdx+1]; dwClsContext
0x18000d122  lea     rcx, CLSID_PortableDeviceManager; rclsid
0x18000d129  call    cs:__imp_CoCreateInstance
0x18000d12f  test    eax, eax
0x18000d131  js      short loc_18000D17B
0x18000d133  mov     [rbp+var_34], 4
0x18000d13a  mov     [rbp+var_38], r12d
0x18000d13e  mov     rcx, [rbp+var_40]
0x18000d142  mov     rax, [rcx]
0x18000d145  lea     rdx, [rbp+var_38]
0x18000d149  mov     [rsp+80h+var_58], rdx
0x18000d14e  lea     rdx, [rbp+var_34]
0x18000d152  mov     [rsp+80h+ppv], rdx
0x18000d157  lea     r9, [rbp+var_30]
0x18000d15b  lea     r8, aPortabledevice_0; "PortableDeviceNameSpaceTimeout"
0x18000d162  mov     rdx, rsi
0x18000d165  mov     rax, [rax+40h]
0x18000d169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d16e  test    eax, eax
0x18000d170  js      short loc_18000D17B
0x18000d172  cmp     [rbp+var_38], 4
0x18000d176  cmovz   r14d, [rbp+var_30]
0x18000d17b  mov     ecx, 0A8h; unsigned __int64
0x18000d180  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d185  mov     [rbp+var_28], rax
0x18000d189  test    rax, rax
0x18000d18c  jz      short loc_18000D19E
0x18000d18e  mov     edx, r14d; unsigned int
0x18000d191  mov     rcx, rax; this
0x18000d194  call    ??0DEVITEM_CACHE@@QEAA@K@Z; DEVITEM_CACHE::DEVITEM_CACHE(ulong)
0x18000d199  mov     r14, rax
0x18000d19c  jmp     short loc_18000D1A1
0x18000d19e  mov     r14, r12
0x18000d1a1  test    r14, r14
0x18000d1a4  jnz     short loc_18000D1C6
0x18000d1a6  mov     ebx, 8007000Eh
0x18000d1ab  mov     rcx, [rbp+var_40]
0x18000d1af  test    rcx, rcx
0x18000d1b2  jz      short loc_18000D1C1
0x18000d1b4  mov     rax, [rcx]
0x18000d1b7  mov     rax, [rax+10h]
0x18000d1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1c0  nop
0x18000d1c1  jmp     loc_18000D2B0
0x18000d1c6  mov     [r14], rsi
0x18000d1c9  test    rdi, rdi
0x18000d1cc  jz      short loc_18000D1DF
0x18000d1ce  mov     rdx, rdi; struct _ITEMIDLIST *
0x18000d1d1  mov     rcx, r14; struct DEVITEM_CACHE *
0x18000d1d4  call    ?s_AddToPidlCache@CDeviceCache@@CAJPEAUDEVITEM_CACHE@@PEFAU_ITEMIDLIST@@@Z; CDeviceCache::s_AddToPidlCache(DEVITEM_CACHE *,_ITEMIDLIST *)
0x18000d1d9  test    eax, eax
0x18000d1db  cmovz   rdi, r12
0x18000d1df  mov     r8, r14
0x18000d1e2  mov     rcx, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x18000d1e9  mov     rcx, [rcx+8]
0x18000d1ed  call    IsolationAwareDPA_InsertPtr
0x18000d1f2  nop
0x18000d1f3  cmp     eax, 0FFFFFFFFh
0x18000d1f6  jnz     short loc_18000D216
0x18000d1f8  lea     rcx, [rbp+var_40]
0x18000d1fc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d201  mov     rcx, r14; this
0x18000d204  call    ??_GDEVITEM_CACHE@@QEAAPEAXI@Z; DEVITEM_CACHE::`scalar deleting destructor'(uint)
0x18000d209  mov     ebx, 80004005h
0x18000d20e  mov     rsi, r12
0x18000d211  jmp     loc_18000D2B0
0x18000d216  mov     rsi, r12
0x18000d219  mov     rcx, [rbp+var_40]
0x18000d21d  test    rcx, rcx
0x18000d220  jz      short loc_18000D22F
0x18000d222  mov     rax, [rcx]
0x18000d225  mov     rax, [rax+10h]
0x18000d229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d22e  nop
0x18000d22f  jmp     short loc_18000D2B0
0x18000d231  mov     ebx, 80070216h
0x18000d236  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d23d  cmp     rcx, r11
0x18000d240  jz      short loc_18000D2B0
0x18000d242  test    byte ptr [rcx+1Ch], 2
0x18000d246  jz      short loc_18000D2B0
0x18000d248  mov     edx, 14h
0x18000d24d  jmp     short loc_18000D29D
0x18000d24f  mov     ebx, 80070216h
0x18000d254  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d25b  cmp     rcx, r11
0x18000d25e  jz      short loc_18000D2B0
0x18000d260  test    byte ptr [rcx+1Ch], 2
0x18000d264  jz      short loc_18000D2B0
0x18000d266  mov     edx, 13h
0x18000d26b  mov     dword ptr [rsp+80h+var_58], ebx
0x18000d26f  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000d276  mov     rcx, [rcx+10h]
0x18000d27a  call    WPP_SF_Ddd
0x18000d27f  jmp     short loc_18000D2B0
0x18000d281  mov     ebx, 80070057h
0x18000d286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d28d  cmp     rcx, r11
0x18000d290  jz      short loc_18000D2B0
0x18000d292  test    byte ptr [rcx+1Ch], 2
0x18000d296  jz      short loc_18000D2B0
0x18000d298  mov     edx, 12h
0x18000d29d  mov     r9d, ebx
0x18000d2a0  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000d2a7  mov     rcx, [rcx+10h]
0x18000d2ab  call    WPP_SF_d
0x18000d2b0  lea     r13, WPP_GLOBAL_Control
0x18000d2b7  mov     rcx, rsi; hMem
0x18000d2ba  call    cs:__imp_LocalFree
0x18000d2c0  test    rdi, rdi
0x18000d2c3  jz      short loc_18000D2CE
0x18000d2c5  mov     rcx, rdi; pidl
0x18000d2c8  call    cs:__imp_ILFree
0x18000d2ce  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
  ... truncated ...
```
