# CUpnpClassMapper::GetUpnpClassForItem(IPropertyStore *,bool,CUpnpClassMapper::CdsItemClass *)

- ea: `0x140008550`
- end: `0x140008e04`
- name: `?GetUpnpClassForItem@CUpnpClassMapper@@SAJPEAUIPropertyStore@@_NPEAW4CdsItemClass@1@@Z`
- size: `2228`
- prototype: `__int64 __fastcall(struct IPropertyStore *, bool, enum CUpnpClassMapper::CdsItemClass *)`
- caller_count: `11`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000660c`
- `0x140008ee0`
- `0x1400091b0`
- `0x14000aa9c`
- `0x140010240`
- `0x140027860`
- `0x14002e440`
- `0x140032180`
- `0x14003247c`
- `0x14007dd54`
- `0x140080e20`

## callees

- `0x1400065e0`
- `0x140008550`
- `0x140015230`
- `0x140023eb0`
- `0x1400396dc`
- `0x140046c32`
- `0x14009ace0`
- `0x14009ad10`
- `0x14009ad1c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1400087b4`
- `KERNEL32!CompareStringOrdinal` at `0x1400087e0`
- `KERNEL32!CompareStringOrdinal` at `0x14000880c`
- `KERNEL32!CompareStringOrdinal` at `0x140008838`
- `KERNEL32!CompareStringOrdinal` at `0x1400089a0`
- `KERNEL32!CompareStringOrdinal` at `0x1400089c7`
- `KERNEL32!CompareStringOrdinal` at `0x140008a93`
- `KERNEL32!CompareStringOrdinal` at `0x140008abf`
- `KERNEL32!CompareStringOrdinal` at `0x140008b13`
- `KERNEL32!CompareStringOrdinal` at `0x140008b3f`
- `KERNEL32!CompareStringOrdinal` at `0x140008b6b`
- `KERNEL32!CompareStringOrdinal` at `0x140008bda`
- `KERNEL32!CompareStringOrdinal` at `0x140008cb6`
- `KERNEL32!CompareStringOrdinal` at `0x140008ceb`
- `KERNEL32!CompareStringOrdinal` at `0x140008d20`
- `KERNEL32!CompareStringOrdinal` at `0x140008d55`
- `KERNEL32!CompareStringOrdinal` at `0x1400087b4`
- `KERNEL32!CompareStringOrdinal` at `0x1400087e0`
- `KERNEL32!CompareStringOrdinal` at `0x14000880c`
- `KERNEL32!CompareStringOrdinal` at `0x140008838`
- `KERNEL32!CompareStringOrdinal` at `0x1400089a0`
- `KERNEL32!CompareStringOrdinal` at `0x1400089c7`
- `KERNEL32!CompareStringOrdinal` at `0x140008a93`
- `KERNEL32!CompareStringOrdinal` at `0x140008abf`
- `KERNEL32!CompareStringOrdinal` at `0x140008b13`
- `KERNEL32!CompareStringOrdinal` at `0x140008b3f`
- `KERNEL32!CompareStringOrdinal` at `0x140008b6b`
- `KERNEL32!CompareStringOrdinal` at `0x140008bda`
- `KERNEL32!CompareStringOrdinal` at `0x140008cb6`
- `KERNEL32!CompareStringOrdinal` at `0x140008ceb`
- `KERNEL32!CompareStringOrdinal` at `0x140008d20`
- `KERNEL32!CompareStringOrdinal` at `0x140008d55`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000893a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000893a`
- `ole32!PropVariantClear` at `0x140008601`
- `ole32!PropVariantClear` at `0x14000860b`
- `ole32!PropVariantClear` at `0x140008695`
- `ole32!PropVariantClear` at `0x14000875d`
- `ole32!PropVariantClear` at `0x1400088b8`
- `ole32!PropVariantClear` at `0x1400088c2`
- `ole32!PropVariantClear` at `0x140008972`
- `ole32!PropVariantClear` at `0x14000897c`
- `ole32!PropVariantClear` at `0x140008b89`
- `ole32!PropVariantClear` at `0x140008d93`
- `ole32!PropVariantClear` at `0x140008d9d`
- `ole32!PropVariantClear` at `0x140008dc9`
- `ole32!PropVariantClear` at `0x140008601`
- `ole32!PropVariantClear` at `0x14000860b`
- `ole32!PropVariantClear` at `0x140008695`
- `ole32!PropVariantClear` at `0x14000875d`
- `ole32!PropVariantClear` at `0x1400088b8`
- `ole32!PropVariantClear` at `0x1400088c2`
- `ole32!PropVariantClear` at `0x140008972`
- `ole32!PropVariantClear` at `0x14000897c`
- `ole32!PropVariantClear` at `0x140008b89`
- `ole32!PropVariantClear` at `0x140008d93`
- `ole32!PropVariantClear` at `0x140008d9d`
- `ole32!PropVariantClear` at `0x140008dc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUpnpClassMapper::GetUpnpClassForItem(
        struct IPropertyStore *a1,
        __int64 a2,
        enum CUpnpClassMapper::CdsItemClass *a3)
{
  struct IPropertyStore *v4; // r15
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rdi
  _DWORD *v7; // rax
  _WORD *v8; // rsi
  _WORD *v9; // rdx
  __int64 v10; // r8
  int v11; // r14d
  PROPVARIANT v12; // rdi
  __int64 v13; // rbx
  unsigned __int64 v14; // r12
  __int64 v15; // r15
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r14
  unsigned __int64 v19; // r15
  __int64 v21; // rbx
  int *v22; // rcx
  int v23; // r14d
  int v24; // ebx
  int v25; // esi
  __int64 v26; // rdi
  __int64 v27; // rsi
  const WCHAR *v28; // rcx
  __int64 v29; // rbx
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v31; // [rsp+40h] [rbp-40h]
  int v32; // [rsp+48h] [rbp-38h]
  PROPVARIANT v33[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v34; // [rsp+60h] [rbp-20h]
  _WORD *v35; // [rsp+68h] [rbp-18h] BYREF
  struct IPropertyStore *v36; // [rsp+70h] [rbp-10h]

  v4 = a1;
  v36 = a1;
  *(_OWORD *)pvar = 0;
  v31 = 0;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v5 = 0;
  v6 = 0;
  *(_DWORD *)a3 = 0;
  if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
         a1,
         &PKEY_Media_ClassPrimaryID,
         pvar) >= 0
    && LOWORD(pvar[0]) == 31 )
  {
    v5 = (const WCHAR *)pvar[1];
  }
  if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v4->lpVtbl->GetValue)(
         v4,
         &PKEY_Media_ClassSecondaryID,
         v33) >= 0
    && LOWORD(v33[0]) == 31 )
  {
    v6 = (const WCHAR *)v33[1];
  }
  if ( v5 )
  {
    if ( CompareStringOrdinal(v5, -1, L"{D1607DBC-E323-4be2-86A1-48A42A28441E}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 6;
    }
    else if ( CompareStringOrdinal(v5, -1, L"{01CD0F29-DA4E-4157-897B-6275D50C4F11}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 5;
    }
    else if ( CompareStringOrdinal(v5, -1, L"{DB9830BD-3AB3-4fab-8A37-1A995F7FF74B}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 1;
    }
    else if ( CompareStringOrdinal(v5, -1, L"{6FB2E74A-B8CB-40BB-93F3-FAC5F00FA203}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 9;
    }
  }
  if ( v6 )
  {
    if ( CompareStringOrdinal(v6, -1, L"{E0236BEB-C281-4ede-A36D-7AF76A3D45B5}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 7;
    }
    else if ( CompareStringOrdinal(v6, -1, L"{E3E689E2-BA8C-4330-96DF-A0EEEFFA6876}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 3;
    }
    else if ( CompareStringOrdinal(v6, -1, L"{A9B87FC9-BD47-4bf0-AC4F-655B89F7D868}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 4;
    }
    else if ( CompareStringOrdinal(v6, -1, L"{BA7F258A-62F7-47a9-B21F-4651C42A000E}", 38, 1) == 2 )
    {
      *(_DWORD *)a3 = 2;
    }
  }
  PropVariantClear(pvar);
  PropVariantClear(v33);
  if ( *(_DWORD *)a3 )
    goto LABEL_29;
  v7 = (_DWORD *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v8 = v7 + 6;
  v35 = v7 + 6;
  *(_DWORD *)a3 = 0;
  *(_OWORD *)pvar = 0;
  v31 = 0;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  if ( v7[2] )
  {
    if ( (int)v7[4] < 0 )
    {
      if ( (int)v7[3] < 0 )
        goto LABEL_104;
      v7[2] = 0;
      *v8 = 0;
    }
    else
    {
      v21 = *(_QWORD *)v7;
      ATL::CStringData::Release((ATL::CStringData *)v7);
      v8 = (_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21) + 24);
      v35 = v8;
    }
  }
  v11 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v4->lpVtbl->GetValue)(
          v4,
          &PKEY_ContentType,
          pvar);
  v32 = v11;
  if ( v11 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 31 )
      goto LABEL_16;
    PropVariantClear(pvar);
  }
  v11 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v4->lpVtbl->GetValue)(
          v4,
          &PKEY_MIMEType,
          pvar);
  v32 = v11;
  if ( v11 >= 0 && LOWORD(pvar[0]) == 31 )
  {
LABEL_16:
    v12 = pvar[1];
    if ( !pvar[1] )
      goto LABEL_44;
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)pvar[1] + v13) );
    if ( !(_DWORD)v13 )
    {
LABEL_44:
      v22 = (int *)(v8 - 12);
      if ( *((_DWORD *)v8 - 4) )
      {
        if ( v22[4] >= 0 )
        {
          v29 = *(_QWORD *)v22;
          ATL::CStringData::Release((ATL::CStringData *)v22);
          v8 = (_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29) + 24);
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetLength(&v35, 0);
        }
      }
      goto LABEL_51;
    }
    v14 = *((unsigned int *)v8 - 4);
    v15 = (char *)pvar[1] - (char *)v8;
    v16 = *((_DWORD *)v8 - 3) - v13;
    v17 = v16 | (unsigned int)(1 - *((_DWORD *)v8 - 2));
    if ( (v16 | (1 - *((_DWORD *)v8 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v35, (unsigned int)v13);
      v8 = v35;
    }
    v18 = (int)v13;
    if ( !(v18 * 2) )
      goto LABEL_48;
    v19 = v15 >> 1;
    if ( v19 <= v14 )
    {
      if ( v8 )
      {
        v9 = &v8[v19];
        if ( v9 )
        {
          memmove_0(v8, v9, 2LL * (int)v13);
          goto LABEL_48;
        }
      }
    }
    else if ( v8 )
    {
      memcpy_0(v8, v12, 2LL * (int)v13);
LABEL_48:
      if ( (int)v13 >= 0 && (int)v13 <= *((_DWORD *)v8 - 3) )
      {
        *((_DWORD *)v8 - 4) = v13;
        v8[v18] = 0;
        v11 = v32;
        v4 = v36;
LABEL_51:
        PropVariantClear(pvar);
        PropVariantClear(v33);
        if ( CompareStringOrdinal(v8, 6, L"audio/", 6, 1) == 2 )
        {
          *(_DWORD *)a3 = 5;
        }
        else if ( CompareStringOrdinal(v8, 6, L"image/", 6, 1) == 2 )
        {
          *(_DWORD *)a3 = 8;
        }
        else
        {
          *(_DWORD *)a3 = CompareStringOrdinal(v8, 6, L"video/", 6, 1) == 2;
        }
        goto LABEL_54;
      }
LABEL_104:
      ATL::AtlThrowImpl(-2147024809);
    }
    *(_DWORD *)_o__errno(v17, v9, v10) = 22;
    invalid_parameter_noinfo();
    goto LABEL_48;
  }
  v11 = -2147023728;
  PropVariantClear(pvar);
  PropVariantClear(v33);
LABEL_54:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  if ( v11 < 0 )
    *(_DWORD *)a3 = 0;
  v23 = *(_DWORD *)a3;
  *(_OWORD *)pvar = 0;
  v31 = 0;
  v24 = 0;
  v25 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v4->lpVtbl->GetValue)(
          v4,
          &PKEY_Kind,
          pvar);
  if ( v25 >= 0 )
  {
    if ( LOWORD(pvar[0]) != 4127 || !v31 )
    {
      PropVariantClear(pvar);
      goto LABEL_29;
    }
    v26 = 0;
    if ( LODWORD(pvar[1]) )
    {
      while ( 1 )
      {
        v27 = 8 * v26;
        v28 = *(const WCHAR **)(8 * v26 + v31);
        if ( v28 )
        {
          if ( CompareStringOrdinal(v28, -1, L"music", -1, 1) == 2 )
          {
            if ( (unsigned int)(v23 - 8) > 1 && (unsigned int)(v23 - 1) > 3 && (unsigned int)(v24 - 1) > 3 )
              v24 = 6;
            goto LABEL_72;
          }
          if ( CompareStringOrdinal(*(LPCWCH *)(v27 + v31), -1, L"picture", -1, 1) != 2 )
          {
            if ( CompareStringOrdinal(*(LPCWCH *)(v27 + v31), -1, L"movie", -1, 1) == 2 )
            {
              if ( (unsigned int)(v23 - 5) > 4 && v24 != 2 )
                v24 = 4;
            }
            else if ( CompareStringOrdinal(*(LPCWCH *)(v27 + v31), -1, L"recordedtv", -1, 1) == 2 )
            {
              v24 = 2;
            }
            else if ( CompareStringOrdinal(*(LPCWCH *)(v27 + v31), -1, L"video", -1, 1) == 2
                   && (unsigned int)(v23 - 5) > 4
                   && ((v24 - 2) & 0xFFFFFFFD) != 0 )
            {
              v24 = 1;
            }
            goto LABEL_72;
          }
          if ( (unsigned int)(v23 - 1) > 6 )
          {
            if ( (unsigned int)(v24 - 5) > 1 )
            {
LABEL_68:
              v24 = 9;
              goto LABEL_72;
            }
          }
          else if ( (unsigned int)(v24 - 1) <= 2 )
          {
            goto LABEL_72;
          }
          if ( v24 != 4 )
            goto LABEL_68;
        }
LABEL_72:
        v26 = (unsigned int)(v26 + 1);
        if ( (unsigned int)v26 >= LODWORD(pvar[1]) )
        {
          PropVariantClear(pvar);
          goto LABEL_27;
        }
      }
    }
  }
  PropVariantClear(pvar);
  if ( v25 >= 0 )
  {
LABEL_27:
    if ( v24 )
      *(_DWORD *)a3 = v24;
  }
LABEL_29:
  if ( *(_DWORD *)a3 == 1 )
  {
    *(_OWORD *)pvar = 0;
    v31 = 0;
    *(_OWORD *)v33 = 0;
    v34 = 0;
    ((void (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v4->lpVtbl->GetValue)(
      v4,
      &PKEY_Video_Compression,
      pvar);
    ((void (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v4->lpVtbl->GetValue)(
      v4,
      &PKEY_ItemType,
      v33);
    if ( LOWORD(pvar[0]) <= 1u && LOWORD(v33[0]) == 31 && !wcscmp_0((const wchar_t *)v33[1], L".3gp") )
      *(_DWORD *)a3 = 5;
    PropVariantClear(pvar);
    PropVariantClear(v33);
  }
  return 0;
}

```

## disassembly

```asm
0x140008550  mov     [rsp-38h+arg_8], rbx
0x140008555  push    rbp
0x140008556  push    rsi
0x140008557  push    rdi
0x140008558  push    r12
0x14000855a  push    r13
0x14000855c  push    r14
0x14000855e  push    r15
0x140008560  mov     rbp, rsp
0x140008563  sub     rsp, 80h
0x14000856a  mov     r13, r8
0x14000856d  mov     r15, rcx
0x140008570  mov     [rbp+var_10], rcx
0x140008574  xorps   xmm0, xmm0
0x140008577  xor     eax, eax
0x140008579  movups  xmmword ptr [rbp+pvar], xmm0
0x14000857d  mov     [rbp+var_40], rax
0x140008581  xorps   xmm1, xmm1
0x140008584  movups  xmmword ptr [rbp+var_30], xmm1
0x140008588  mov     [rbp+var_20], rax
0x14000858c  xor     r14d, r14d
0x14000858f  mov     ebx, r14d
0x140008592  mov     edi, r14d
0x140008595  mov     [r8], r14d
0x140008598  mov     rax, [rcx]
0x14000859b  lea     r8, [rbp+pvar]
0x14000859f  lea     rdx, PKEY_Media_ClassPrimaryID
0x1400085a6  mov     rax, [rax+28h]
0x1400085aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085af  mov     r12d, 1Fh
0x1400085b5  test    eax, eax
0x1400085b7  js      short loc_1400085C3
0x1400085b9  cmp     r12w, word ptr [rbp+pvar]
0x1400085be  cmovz   rbx, [rbp+pvar+8]
0x1400085c3  mov     rax, [r15]
0x1400085c6  lea     r8, [rbp+var_30]
0x1400085ca  lea     rdx, PKEY_Media_ClassSecondaryID
0x1400085d1  mov     rcx, r15
0x1400085d4  mov     rax, [rax+28h]
0x1400085d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085dd  test    eax, eax
0x1400085df  js      short loc_1400085EB
0x1400085e1  cmp     r12w, word ptr [rbp+var_30]
0x1400085e6  cmovz   rdi, [rbp+var_30+8]
0x1400085eb  test    rbx, rbx
0x1400085ee  jnz     loc_140008C99
0x1400085f4  test    rdi, rdi
0x1400085f7  jnz     loc_140008797
0x1400085fd  lea     rcx, [rbp+pvar]; pvar
0x140008601  call    cs:__imp_PropVariantClear
0x140008607  lea     rcx, [rbp+var_30]; pvar
0x14000860b  call    cs:__imp_PropVariantClear
0x140008611  cmp     [r13+0], r14d
0x140008615  jnz     loc_14000876F
0x14000861b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140008622  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140008629  mov     rax, [rax+18h]
0x14000862d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008632  lea     rsi, [rax+18h]
0x140008636  mov     [rbp+var_18], rsi
0x14000863a  mov     [r13+0], r14d
0x14000863e  xorps   xmm0, xmm0
0x140008641  xor     eax, eax
0x140008643  movups  xmmword ptr [rbp+pvar], xmm0
0x140008647  mov     [rbp+var_40], rax
0x14000864b  xorps   xmm1, xmm1
0x14000864e  movups  xmmword ptr [rbp+var_30], xmm1
0x140008652  mov     [rbp+var_20], rax
0x140008656  lea     rcx, [rsi-18h]; this
0x14000865a  cmp     [rcx+8], eax
0x14000865d  jnz     loc_1400088DA
0x140008663  mov     rax, [r15]
0x140008666  lea     r8, [rbp+pvar]
0x14000866a  lea     rdx, PKEY_ContentType
0x140008671  mov     rcx, r15
0x140008674  mov     rax, [rax+28h]
0x140008678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000867d  mov     r14d, eax
0x140008680  mov     [rbp+var_38], eax
0x140008683  test    eax, eax
0x140008685  js      short loc_14000869B
0x140008687  movzx   ecx, word ptr [rbp+pvar]
0x14000868b  cmp     r12w, cx
0x14000868f  jz      short loc_1400086D1
0x140008691  lea     rcx, [rbp+pvar]; pvar
0x140008695  call    cs:__imp_PropVariantClear
0x14000869b  mov     rax, [r15]
0x14000869e  lea     r8, [rbp+pvar]
0x1400086a2  lea     rdx, PKEY_MIMEType
0x1400086a9  mov     rcx, r15
0x1400086ac  mov     rax, [rax+28h]
0x1400086b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086b5  mov     r14d, eax
0x1400086b8  mov     [rbp+var_38], eax
0x1400086bb  test    eax, eax
0x1400086bd  js      loc_140008D89
0x1400086c3  movzx   ecx, word ptr [rbp+pvar]
0x1400086c7  cmp     r12w, cx
0x1400086cb  jnz     loc_140008D89
0x1400086d1  mov     rdi, [rbp+pvar+8]
0x1400086d5  test    rdi, rdi
0x1400086d8  jz      loc_140008919
0x1400086de  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400086e5  inc     rbx
0x1400086e8  cmp     word ptr [rdi+rbx*2], 0
0x1400086ed  jnz     short loc_1400086E5
0x1400086ef  test    ebx, ebx
0x1400086f1  jz      loc_140008919
0x1400086f7  mov     r12d, [rsi-10h]
0x1400086fb  mov     r15, rdi
0x1400086fe  sub     r15, rsi
0x140008701  mov     ecx, 1
0x140008706  sub     ecx, [rsi-8]
0x140008709  mov     eax, [rsi-0Ch]
0x14000870c  sub     eax, ebx
0x14000870e  or      ecx, eax
0x140008710  jge     short loc_140008721
0x140008712  mov     edx, ebx
0x140008714  lea     rcx, [rbp+var_18]
0x140008718  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000871d  mov     rsi, [rbp+var_18]
0x140008721  movsxd  rax, ebx
0x140008724  lea     r14, [rax+rax]
0x140008728  test    r14, r14
0x14000872b  jz      loc_14000894B
0x140008731  sar     r15, 1
0x140008734  cmp     r15, r12
0x140008737  jbe     loc_140008BFB
0x14000873d  test    rsi, rsi
0x140008740  jz      loc_14000893A
0x140008746  mov     r8, r14; Size
0x140008749  mov     rdx, rdi; Src
0x14000874c  mov     rcx, rsi; void *
0x14000874f  call    memcpy_0
0x140008754  jmp     loc_14000894B
0x140008759  lea     rcx, [rbp+pvar]; pvar
0x14000875d  call    cs:__imp_PropVariantClear
0x140008763  test    esi, esi
0x140008765  js      short loc_14000876F
0x140008767  test    ebx, ebx
0x140008769  jz      short loc_14000876F
0x14000876b  mov     [r13+0], ebx
0x14000876f  cmp     dword ptr [r13+0], 1
0x140008774  jz      loc_14000885D
0x14000877a  xor     eax, eax
0x14000877c  mov     rbx, [rsp+80h+arg_8]
0x140008784  add     rsp, 80h
0x14000878b  pop     r15
0x14000878d  pop     r14
0x14000878f  pop     r13
0x140008791  pop     r12
0x140008793  pop     rdi
0x140008794  pop     rsi
0x140008795  pop     rbp
0x140008796  retn
0x140008797  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x14000879f  mov     r9d, 26h ; '&'; cchCount2
0x1400087a5  lea     r8, g_pszClassSecondaryID_AudioBook; "{E0236BEB-C281-4ede-A36D-7AF76A3D45B5}"
0x1400087ac  mov     edx, 0FFFFFFFFh; cchCount1
0x1400087b1  mov     rcx, rdi; lpString1
0x1400087b4  call    cs:__imp_CompareStringOrdinal
0x1400087ba  cmp     eax, 2
0x1400087bd  jz      loc_140008850
0x1400087c3  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x1400087cb  mov     r9d, 26h ; '&'; cchCount2
0x1400087d1  lea     r8, g_pszClassSecondaryID_MusicVideo; "{E3E689E2-BA8C-4330-96DF-A0EEEFFA6876}"
0x1400087d8  mov     edx, 0FFFFFFFFh; cchCount1
0x1400087dd  mov     rcx, rdi; lpString1
0x1400087e0  call    cs:__imp_CompareStringOrdinal
0x1400087e6  cmp     eax, 2
0x1400087e9  jz      loc_1400088CD
0x1400087ef  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x1400087f7  mov     r9d, 26h ; '&'; cchCount2
0x1400087fd  lea     r8, g_pszClassSecondaryID_Movie; "{A9B87FC9-BD47-4bf0-AC4F-655B89F7D868}"
0x140008804  mov     edx, 0FFFFFFFFh; cchCount1
0x140008809  mov     rcx, rdi; lpString1
0x14000880c  call    cs:__imp_CompareStringOrdinal
0x140008812  cmp     eax, 2
0x140008815  jz      loc_140008D71
0x14000881b  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x140008823  mov     r9d, 26h ; '&'; cchCount2
0x140008829  lea     r8, g_pszClassSecondaryID_RecordedTV; "{BA7F258A-62F7-47a9-B21F-4651C42A000E}"
0x140008830  mov     edx, 0FFFFFFFFh; cchCount1
0x140008835  mov     rcx, rdi; lpString1
0x140008838  call    cs:__imp_CompareStringOrdinal
0x14000883e  cmp     eax, 2
0x140008841  jnz     loc_1400085FD
0x140008847  mov     [r13+0], eax
0x14000884b  jmp     loc_1400085FD
0x140008850  mov     dword ptr [r13+0], 7
0x140008858  jmp     loc_1400085FD
0x14000885d  xorps   xmm0, xmm0
0x140008860  xor     eax, eax
0x140008862  movups  xmmword ptr [rbp+pvar], xmm0
0x140008866  mov     [rbp+var_40], rax
0x14000886a  xorps   xmm1, xmm1
0x14000886d  movups  xmmword ptr [rbp+var_30], xmm1
0x140008871  mov     [rbp+var_20], rax
0x140008875  mov     rax, [r15]
0x140008878  lea     r8, [rbp+pvar]
0x14000887c  lea     rdx, PKEY_Video_Compression
0x140008883  mov     rcx, r15
0x140008886  mov     rax, [rax+28h]
0x14000888a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000888f  mov     rax, [r15]
0x140008892  lea     r8, [rbp+var_30]
0x140008896  lea     rdx, PKEY_ItemType
0x14000889d  mov     rcx, r15
0x1400088a0  mov     rax, [rax+28h]
0x1400088a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088a9  cmp     word ptr [rbp+pvar], 1
0x1400088ae  jbe     loc_140008DD4
0x1400088b4  lea     rcx, [rbp+pvar]; pvar
0x1400088b8  call    cs:__imp_PropVariantClear
0x1400088be  lea     rcx, [rbp+var_30]; pvar
0x1400088c2  call    cs:__imp_PropVariantClear
0x1400088c8  jmp     loc_14000877A
0x1400088cd  mov     dword ptr [r13+0], 3
0x1400088d5  jmp     loc_1400085FD
0x1400088da  cmp     [rcx+10h], eax
0x1400088dd  jl      short loc_140008903
0x1400088df  mov     rbx, [rcx]
0x1400088e2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400088e7  mov     rax, [rbx]
0x1400088ea  mov     rcx, rbx
0x1400088ed  mov     rax, [rax+18h]
0x1400088f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088f6  lea     rsi, [rax+18h]
0x1400088fa  mov     [rbp+var_18], rsi
0x1400088fe  jmp     loc_140008663
0x140008903  cmp     [rsi-0Ch], eax
0x140008906  jl      loc_140008D7E
0x14000890c  mov     [rsi-10h], r14d
0x140008910  mov     [rsi], r14w
0x140008914  jmp     loc_140008663
0x140008919  lea     rcx, [rsi-18h]; this
0x14000891d  cmp     dword ptr [rcx+8], 0
0x140008921  jz      short loc_14000896E
0x140008923  cmp     dword ptr [rcx+10h], 0
0x140008927  jge     loc_140008C21
0x14000892d  xor     edx, edx
0x14000892f  lea     rcx, [rbp+var_18]
0x140008933  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x140008938  jmp     short loc_14000896E
0x14000893a  call    cs:__imp__o__errno
0x140008940  mov     dword ptr [rax], 16h
0x140008946  call    _invalid_parameter_noinfo
0x14000894b  test    ebx, ebx
0x14000894d  js      loc_140008D7E
0x140008953  cmp     ebx, [rsi-0Ch]
0x140008956  jg      loc_140008D7E
0x14000895c  mov     [rsi-10h], ebx
0x14000895f  xor     eax, eax
0x140008961  mov     [r14+rsi], ax
0x140008966  mov     r14d, [rbp+var_38]
0x14000896a  mov     r15, [rbp+var_10]
0x14000896e  lea     rcx, [rbp+pvar]; pvar
0x140008972  call    cs:__imp_PropVariantClear
0x140008978  lea     rcx, [rbp+var_30]; pvar
0x14000897c  call    cs:__imp_PropVariantClear
0x140008982  mov     r12d, 1
0x140008988  mov     [rsp+80h+bIgnoreCase], r12d; bIgnoreCase
0x14000898d  mov     r9d, 6; cchCount2
0x140008993  lea     r8, aAudio_0; "audio/"
0x14000899a  mov     edx, r9d; cchCount1
0x14000899d  mov     rcx, rsi; lpString1
0x1400089a0  call    cs:__imp_CompareStringOrdinal
0x1400089a6  cmp     eax, 2
0x1400089a9  jz      loc_140008BB5
0x1400089af  mov     [rsp+80h+bIgnoreCase], r12d; bIgnoreCase
0x1400089b4  mov     r9d, 6; cchCount2
0x1400089ba  lea     r8, aImage; "image/"
0x1400089c1  mov     edx, r9d; cchCount1
0x1400089c4  mov     rcx, rsi; lpString1
0x1400089c7  call    cs:__imp_CompareStringOrdinal
0x1400089cd  cmp     eax, 2
0x1400089d0  jnz     loc_140008BC2
0x1400089d6  mov     dword ptr [r13+0], 8
0x1400089de  lea     rdx, [rsi-18h]
0x1400089e2  mov     eax, 0FFFFFFFFh
0x1400089e7  lock xadd [rdx+10h], eax
0x1400089ec  sub     eax, 1
0x1400089ef  jg      short loc_140008A01
0x1400089f1  mov     rcx, [rdx]
0x1400089f4  mov     rax, [rcx]
0x1400089f7  mov     rax, [rax+8]
0x1400089fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a00  nop
0x140008a01  test    r14d, r14d
0x140008a04  js      loc_140008DAE
0x140008a0a  mov     r14d, [r13+0]
0x140008a0e  xorps   xmm0, xmm0
0x140008a11  xor     eax, eax
0x140008a13  movups  xmmword ptr [rbp+pvar], xmm0
0x140008a17  mov     [rbp+var_40], rax
0x140008a1b  xor     ebx, ebx
0x140008a1d  mov     rax, [r15]
0x140008a20  lea     r8, [rbp+pvar]
0x140008a24  lea     rdx, PKEY_Kind
0x140008a2b  mov     rcx, r15
  ... truncated ...
```
