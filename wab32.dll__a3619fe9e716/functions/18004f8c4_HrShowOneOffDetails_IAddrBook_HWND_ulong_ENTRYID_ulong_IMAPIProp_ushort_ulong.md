# HrShowOneOffDetails(IAddrBook *,HWND__ *,ulong,ENTRYID *,ulong,IMAPIProp *,ushort *,ulong)

- ea: `0x18004f8c4`
- end: `0x18004fe05`
- name: `?HrShowOneOffDetails@@YAJPEAUIAddrBook@@PEAUHWND__@@KPEAUENTRYID@@KPEAUIMAPIProp@@PEAGK@Z`
- size: `1345`
- prototype: `int(struct IAddrBook *, HWND, unsigned int, struct ENTRYID *, unsigned int, struct IMAPIProp *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019cc0`
- `0x180028014`
- `0x18004fe0c`

## callees

- `0x180002818`
- `0x18000683c`
- `0x1800175c0`
- `0x180025998`
- `0x18002fe40`
- `0x18004b860`
- `0x18004f8c4`
- `0x18005b37c`
- `0x18005b418`
- `0x1800653bc`
- `0x180069e24`
- `0x18006bcac`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004f9b9`
- `KERNEL32!LocalFree` at `0x18004f9cb`
- `KERNEL32!LocalFree` at `0x18004f9ea`
- `KERNEL32!LocalFree` at `0x18004f9fd`
- `KERNEL32!LocalFree` at `0x18004f9b9`
- `KERNEL32!LocalFree` at `0x18004f9cb`
- `KERNEL32!LocalFree` at `0x18004f9ea`
- `KERNEL32!LocalFree` at `0x18004f9fd`
- `KERNEL32!CompareStringW` at `0x18004fc71`
- `KERNEL32!CompareStringW` at `0x18004fc71`

## pseudocode

```c
__int64 __fastcall HrShowOneOffDetails(
        struct IAddrBook *a1,
        HWND a2,
        unsigned int a3,
        struct ENTRYID *a4,
        unsigned int a5,
        struct IMAPIProp *a6,
        unsigned __int16 *a7,
        unsigned int a8)
{
  int v12; // ebx
  unsigned int v14; // eax
  int v15; // eax
  int v16; // edx
  struct IMAPIProp *v17; // rcx
  int inited; // eax
  int v19; // edx
  unsigned int i; // r8d
  unsigned int j; // ecx
  const WCHAR *lpString2; // rcx
  unsigned __int64 v23; // rax
  unsigned int v24; // ecx
  unsigned int v25; // r8d
  char *cchCount2; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+38h] [rbp-C8h]
  unsigned int v28; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  struct ENTRYID *k; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v31; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v32; // [rsp+7Ch] [rbp-84h] BYREF
  struct ENTRYID *v33; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+90h] [rbp-70h] BYREF
  __int128 v35; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h]
  __int128 v37; // [rsp+B8h] [rbp-48h]
  __int128 v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+D8h] [rbp-28h]
  _DWORD v40[5]; // [rsp+DCh] [rbp-24h] BYREF
  struct IAddrBook *v41; // [rsp+F0h] [rbp-10h]
  struct CWABDocHost *v42[2]; // [rsp+F8h] [rbp-8h] BYREF
  HLOCAL v43; // [rsp+108h] [rbp+8h]
  int v44; // [rsp+114h] [rbp+14h]
  HLOCAL v45; // [rsp+118h] [rbp+18h]
  int v46; // [rsp+154h] [rbp+54h]
  HLOCAL hMem; // [rsp+170h] [rbp+70h]
  int v48[2]; // [rsp+178h] [rbp+78h] BYREF
  HLOCAL v49; // [rsp+180h] [rbp+80h]
  int v50; // [rsp+18Ch] [rbp+8Ch]
  _QWORD v51[5]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v52; // [rsp+1D0h] [rbp+D0h]
  __int128 v53; // [rsp+1E0h] [rbp+E0h]

  v36 = 0;
  v39 = 0;
  v40[4] = 0;
  v44 = 0;
  v46 = 0;
  v28 = 0;
  pv = 0;
  v48[1] = 0;
  v34 = 0;
  v50 = 0;
  v35 = 0;
  v37 = 0;
  v38 = 0;
  memset_0(v40, 0, 0xCCu);
  v51[0] = &CUserTile::`vftable';
  v52 = 0;
  v53 = 0;
  memset(&v51[1], 0, 32);
  if ( !ghCommCtrlDLLInst )
  {
    v12 = -2147221220;
    goto LABEL_3;
  }
  v14 = a8;
  if ( (a8 & 0x80u) != 0 )
  {
    v14 = a8 & 0xFFFFFF7F;
    v40[0] |= 0x80u;
  }
  if ( !a4 && !a6 || v14 != 256 )
  {
    v12 = -2147024809;
    goto LABEL_3;
  }
  if ( a3 && a4 )
  {
    cchCount2 = (char *)&v35 + 4;
    v15 = ((__int64 (__fastcall *)(struct IAddrBook *, _QWORD, struct ENTRYID *, _QWORD, _DWORD))a1->lpVtbl->OpenEntry)(
            a1,
            a3,
            a4,
            0,
            0);
    v12 = v15;
    if ( v15 < 0 )
    {
      switch ( v15 )
      {
        case -2147221229:
          goto LABEL_3;
        case -2147221233:
          v16 = 4048;
          goto LABEL_40;
        case -2147221227:
          v16 = 4052;
          goto LABEL_40;
      }
      if ( v15 != -2147220480 )
      {
        if ( v15 == -2147220479 )
        {
          v16 = 4051;
LABEL_40:
          ShowMessageBox(a2, v16, 48);
          goto LABEL_3;
        }
        if ( v15 != -2147219712 )
        {
          v16 = 4050;
          if ( v15 != -2147024891 )
            v16 = 4310;
          goto LABEL_40;
        }
      }
      v16 = 4049;
      goto LABEL_40;
    }
    v17 = (struct IMAPIProp *)*((_QWORD *)&v35 + 1);
  }
  else
  {
    v17 = a6;
    DWORD1(v35) = 6;
    *((_QWORD *)&v35 + 1) = a6;
  }
  v12 = ((__int64 (__fastcall *)(struct IMAPIProp *, _QWORD, __int64, unsigned int *, LPVOID *))v17->lpVtbl->GetProps)(
          v17,
          0,
          0x80000000LL,
          &v28,
          &pv);
  if ( v12 >= 0 )
  {
    if ( !v28 )
      goto LABEL_45;
    v40[0] |= 0x2000u;
    v41 = a1;
    v37 = 0;
    v39 = 0;
    v38 = 0;
    LODWORD(v34) = 0;
    *((_QWORD *)&v34 + 1) = 0;
    v36 = 0;
    LODWORD(v35) = 256;
    inited = InitCryptoLib();
    v19 = v40[0];
    if ( inited )
    {
      v19 = v40[0] | 0x100;
      v40[0] |= 0x100u;
    }
    for ( i = 0; i < v28; ++i )
    {
      if ( *((_DWORD *)pv + 6 * i) == 1711931423 || *((_DWORD *)pv + 6 * i) == 1712001055 )
      {
        v40[0] = v19 | 0x800;
        break;
      }
    }
    for ( j = 0; j < v28; ++j )
    {
      if ( *((_DWORD *)pv + 6 * j) == 1711669279 )
      {
        lpString2 = (const WCHAR *)*((_QWORD *)pv + 3 * j + 1);
        if ( lpString2 )
        {
          v23 = -1;
          do
            ++v23;
          while ( lpString2[v23] );
          if ( v23 > 7 )
            LODWORD(v23) = 7;
          if ( CompareStringW(0x7Fu, 1u, L"http://", 7, lpString2, v23) == 2 )
          {
            v12 = CWABDocHost::Create(v42);
            if ( v12 >= 0 )
              v40[0] |= 0x200u;
          }
        }
        break;
      }
    }
    if ( a3 && a4 )
    {
      k = 0;
      CreateLDAPURLFromEntryID(a3, a4, (unsigned __int16 **)&k, v48);
      hMem = k;
    }
    else
    {
      hMem = a7;
    }
    GetExtDisplayInfo(
      (struct AddressBook *)(-(__int64)(a1 != 0) & (unsigned __int64)&a1[-79]),
      (struct _PropArrayInfo *)&v34,
      1,
      1);
    if ( (unsigned int)CreateDetailsPropertySheet(a2, (struct _PropArrayInfo *)&v34, 0x100u) == -1 )
    {
LABEL_45:
      v12 = -2147467259;
    }
    else if ( (_DWORD)v36 == 3 )
    {
      v24 = 0;
      v32 = 0;
      v31 = 0;
      v33 = 0;
      for ( k = 0; v24 < v28; ++v24 )
      {
        if ( *((_DWORD *)pv + 6 * v24) == 268370178 || *((_DWORD *)pv + 6 * v24) == 1711669279 )
          *((_DWORD *)pv + 6 * v24) = 1;
        if ( *((_DWORD *)pv + 6 * v24) == 1711931423 || *((_DWORD *)pv + 6 * v24) == 1712001055 )
          *((_DWORD *)pv + 6 * v24) = 1;
      }
      v12 = ((__int64 (__fastcall *)(struct IAddrBook *, unsigned int *, struct ENTRYID **))a1->lpVtbl->GetPAB)(
              a1,
              &v31,
              &k);
      if ( v12 >= 0 )
        v12 = HrCreateNewEntry(
                a1,
                a2,
                v25,
                v31,
                k,
                (unsigned int)cchCount2,
                1u,
                v27,
                v28,
                (struct _SPropValue *)pv,
                &v32,
                &v33);
      if ( k )
        MAPIFreeBuffer(k);
      if ( v33 )
        MAPIFreeBuffer(v33);
    }
  }
LABEL_3:
  if ( hMem && hMem != a7 )
    LocalFree(hMem);
  if ( v49 )
  {
    LocalFree(v49);
    v49 = 0;
  }
  FreeExtDisplayInfo((struct _PropArrayInfo *)&v34);
  if ( v43 )
  {
    LocalFree(v43);
    v43 = 0;
  }
  if ( v45 )
  {
    LocalFree(v45);
    v45 = 0;
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(v42);
  if ( *((_QWORD *)&v35 + 1) && !a6 )
    (*(void (**)(void))(**((_QWORD **)&v35 + 1) + 16LL))();
  if ( pv )
    MAPIFreeBuffer(pv);
  CUserTile::~CUserTile((CUserTile *)v51);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004f8c4  push    rbp
0x18004f8c6  push    rbx
0x18004f8c7  push    rsi
0x18004f8c8  push    rdi
0x18004f8c9  push    r12
0x18004f8cb  push    r13
0x18004f8cd  push    r14
0x18004f8cf  push    r15
0x18004f8d1  lea     rbp, [rsp-108h]
0x18004f8d9  sub     rsp, 208h
0x18004f8e0  mov     rax, cs:__security_cookie
0x18004f8e7  xor     rax, rsp
0x18004f8ea  mov     [rbp+140h+var_50], rax
0x18004f8f1  mov     r15, [rbp+140h+arg_28]
0x18004f8f8  xor     eax, eax
0x18004f8fa  mov     r13, [rbp+140h+arg_30]
0x18004f901  xorps   xmm0, xmm0
0x18004f904  xorps   xmm1, xmm1
0x18004f907  mov     [rbp+140h+var_190], rax
0x18004f90b  mov     r14d, r8d
0x18004f90e  mov     [rbp+140h+var_168], eax
0x18004f911  mov     r12, rdx
0x18004f914  mov     [rbp+140h+var_154], eax
0x18004f917  mov     rdi, rcx
0x18004f91a  mov     [rbp+140h+var_12C], eax
0x18004f91d  xor     ebx, ebx
0x18004f91f  mov     [rbp+140h+var_EC], eax
0x18004f922  xor     edx, edx; Val
0x18004f924  mov     [rsp+240h+var_1E0], ebx
0x18004f928  mov     r8d, 0CCh; Size
0x18004f92e  mov     [rsp+240h+pv], rbx
0x18004f933  lea     rcx, [rbp+140h+var_164]; void *
0x18004f937  mov     [rbp+140h+var_C4], eax
0x18004f93a  movups  [rbp+140h+var_1B0], xmm0
0x18004f93e  mov     [rbp+140h+var_B4], eax
0x18004f944  mov     rsi, r9
0x18004f947  movups  [rbp+140h+var_1A0], xmm0
0x18004f94b  movups  [rbp+140h+var_188], xmm1
0x18004f94f  movups  [rbp+140h+var_178], xmm1
0x18004f953  call    memset_0
0x18004f958  cmp     cs:?ghCommCtrlDLLInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * ghCommCtrlDLLInst
0x18004f95f  lea     rax, ??_7CUserTile@@6B@; const CUserTile::`vftable'
0x18004f966  xorps   xmm0, xmm0
0x18004f969  mov     [rbp+140h+var_98], rax
0x18004f970  xorps   xmm1, xmm1
0x18004f973  movdqa  [rbp+140h+var_70], xmm0
0x18004f97b  movups  [rbp+140h+var_60], xmm1
0x18004f982  mov     [rbp+140h+var_90], rbx
0x18004f989  mov     [rbp+140h+var_88], rbx
0x18004f990  mov     [rbp+140h+var_80], rbx
0x18004f997  mov     [rbp+140h+var_78], rbx
0x18004f99e  jnz     loc_18004FA6A
0x18004f9a4  mov     ebx, 8004011Ch
0x18004f9a9  xor     esi, esi
0x18004f9ab  mov     rcx, [rbp+140h+hMem]; hMem
0x18004f9af  test    rcx, rcx
0x18004f9b2  jz      short loc_18004F9BF
0x18004f9b4  cmp     rcx, r13
0x18004f9b7  jz      short loc_18004F9BF
0x18004f9b9  call    cs:__imp_LocalFree
0x18004f9bf  mov     rcx, [rbp+140h+var_C0]; hMem
0x18004f9c6  test    rcx, rcx
0x18004f9c9  jz      short loc_18004F9D8
0x18004f9cb  call    cs:__imp_LocalFree
0x18004f9d1  mov     [rbp+140h+var_C0], rsi
0x18004f9d8  lea     rcx, [rbp+140h+var_1B0]; struct _PropArrayInfo *
0x18004f9dc  call    ?FreeExtDisplayInfo@@YAXPEAU_PropArrayInfo@@@Z; FreeExtDisplayInfo(_PropArrayInfo *)
0x18004f9e1  mov     rcx, [rbp+140h+var_138]; hMem
0x18004f9e5  test    rcx, rcx
0x18004f9e8  jz      short loc_18004F9F4
0x18004f9ea  call    cs:__imp_LocalFree
0x18004f9f0  mov     [rbp+140h+var_138], rsi
0x18004f9f4  mov     rcx, [rbp+140h+var_128]; hMem
0x18004f9f8  test    rcx, rcx
0x18004f9fb  jz      short loc_18004FA07
0x18004f9fd  call    cs:__imp_LocalFree
0x18004fa03  mov     [rbp+140h+var_128], rsi
0x18004fa07  lea     rcx, [rbp+140h+var_148]
0x18004fa0b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18004fa10  mov     rcx, qword ptr [rbp+140h+var_1A0+8]
0x18004fa14  test    rcx, rcx
0x18004fa17  jz      short loc_18004FA2A
0x18004fa19  test    r15, r15
0x18004fa1c  jnz     short loc_18004FA2A
0x18004fa1e  mov     rax, [rcx]
0x18004fa21  mov     rax, [rax+10h]
0x18004fa25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa2a  mov     rcx, [rsp+240h+pv]; pv
0x18004fa2f  test    rcx, rcx
0x18004fa32  jz      short loc_18004FA39
0x18004fa34  call    MAPIFreeBuffer
0x18004fa39  lea     rcx, [rbp+140h+var_98]; this
0x18004fa40  call    ??1CUserTile@@UEAA@XZ; CUserTile::~CUserTile(void)
0x18004fa45  mov     eax, ebx
0x18004fa47  mov     rcx, [rbp+140h+var_50]
0x18004fa4e  xor     rcx, rsp; StackCookie
0x18004fa51  call    __security_check_cookie
0x18004fa56  add     rsp, 208h
0x18004fa5d  pop     r15
0x18004fa5f  pop     r14
0x18004fa61  pop     r13
0x18004fa63  pop     r12
0x18004fa65  pop     rdi
0x18004fa66  pop     rsi
0x18004fa67  pop     rbx
0x18004fa68  pop     rbp
0x18004fa69  retn
0x18004fa6a  mov     eax, [rbp+140h+arg_38]
0x18004fa70  test    al, al
0x18004fa72  jns     short loc_18004FA7D
0x18004fa74  btr     eax, 7
0x18004fa78  bts     [rbp+140h+var_164], 7
0x18004fa7d  test    rsi, rsi
0x18004fa80  jnz     short loc_18004FA87
0x18004fa82  test    r15, r15
0x18004fa85  jz      short loc_18004FA8E
0x18004fa87  cmp     eax, 100h
0x18004fa8c  jz      short loc_18004FA98
0x18004fa8e  mov     ebx, 80070057h
0x18004fa93  jmp     loc_18004F9A9
0x18004fa98  test    r14d, r14d
0x18004fa9b  jz      loc_18004FB54
0x18004faa1  test    rsi, rsi
0x18004faa4  jz      loc_18004FB54
0x18004faaa  mov     rax, [rdi]
0x18004faad  lea     rcx, [rbp+140h+var_1A0+8]
0x18004fab1  mov     qword ptr [rsp+240h+var_210], rcx
0x18004fab6  xor     r9d, r9d
0x18004fab9  lea     rcx, [rbp+140h+var_1A0+4]
0x18004fabd  mov     r8, rsi
0x18004fac0  mov     qword ptr [rsp+240h+cchCount2], rcx
0x18004fac5  mov     edx, r14d
0x18004fac8  mov     rax, [rax+70h]
0x18004facc  mov     rcx, rdi
0x18004facf  mov     dword ptr [rsp+240h+lpString2], ebx
0x18004fad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fad8  mov     ebx, eax
0x18004fada  test    eax, eax
0x18004fadc  jns     short loc_18004FB4E
0x18004fade  cmp     eax, 80040113h
0x18004fae3  jz      loc_18004F9A9
0x18004fae9  cmp     eax, 8004010Fh
0x18004faee  jz      short loc_18004FB36
0x18004faf0  cmp     eax, 80040115h
0x18004faf5  jz      short loc_18004FB2F
0x18004faf7  cmp     eax, 80040400h
0x18004fafc  jz      short loc_18004FB28
0x18004fafe  cmp     eax, 80040401h
0x18004fb03  jz      short loc_18004FB21
0x18004fb05  cmp     eax, 80040700h
0x18004fb0a  jz      short loc_18004FB28
0x18004fb0c  cmp     ebx, 80070005h
0x18004fb12  mov     edx, 0FD2h
0x18004fb17  mov     eax, 10D6h
0x18004fb1c  cmovnz  edx, eax
0x18004fb1f  jmp     short loc_18004FB3B
0x18004fb21  mov     edx, 0FD3h
0x18004fb26  jmp     short loc_18004FB3B
0x18004fb28  mov     edx, 0FD1h
0x18004fb2d  jmp     short loc_18004FB3B
0x18004fb2f  mov     edx, 0FD4h
0x18004fb34  jmp     short loc_18004FB3B
0x18004fb36  mov     edx, 0FD0h; int
0x18004fb3b  mov     r8d, 30h ; '0'; int
0x18004fb41  mov     rcx, r12; hWnd
0x18004fb44  call    ?ShowMessageBox@@YAHPEAUHWND__@@HH@Z; ShowMessageBox(HWND__ *,int,int)
0x18004fb49  jmp     loc_18004F9A9
0x18004fb4e  mov     rcx, qword ptr [rbp+140h+var_1A0+8]
0x18004fb52  jmp     short loc_18004FB62
0x18004fb54  mov     rcx, r15
0x18004fb57  mov     dword ptr [rbp+140h+var_1A0+4], 6
0x18004fb5e  mov     qword ptr [rbp+140h+var_1A0+8], rcx
0x18004fb62  mov     rax, [rcx]
0x18004fb65  lea     rdx, [rsp+240h+pv]
0x18004fb6a  mov     [rsp+240h+lpString2], rdx
0x18004fb6f  lea     r9, [rsp+240h+var_1E0]
0x18004fb74  xor     edx, edx
0x18004fb76  mov     r8d, 80000000h
0x18004fb7c  mov     rax, [rax+28h]
0x18004fb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb85  xor     ecx, ecx
0x18004fb87  mov     ebx, eax
0x18004fb89  test    eax, eax
0x18004fb8b  js      loc_18004F9A9
0x18004fb91  cmp     [rsp+240h+var_1E0], ecx
0x18004fb95  jnz     short loc_18004FBA1
0x18004fb97  mov     ebx, 80004005h
0x18004fb9c  jmp     loc_18004F9A9
0x18004fba1  bts     [rbp+140h+var_164], 0Dh
0x18004fba6  xorps   xmm0, xmm0
0x18004fba9  xor     eax, eax
0x18004fbab  mov     [rbp+140h+var_150], rdi
0x18004fbaf  movups  [rbp+140h+var_188], xmm0
0x18004fbb3  mov     [rbp+140h+var_168], eax
0x18004fbb6  movups  [rbp+140h+var_178], xmm0
0x18004fbba  mov     dword ptr [rbp+140h+var_1B0], ecx
0x18004fbbd  mov     qword ptr [rbp+140h+var_1B0+8], rcx
0x18004fbc1  mov     [rbp+140h+var_190], rcx
0x18004fbc5  mov     dword ptr [rbp+140h+var_1A0], 100h
0x18004fbcc  call    ?InitCryptoLib@@YAHXZ; InitCryptoLib(void)
0x18004fbd1  mov     edx, [rbp+140h+var_164]
0x18004fbd4  xor     r10d, r10d
0x18004fbd7  test    eax, eax
0x18004fbd9  jz      short loc_18004FBE2
0x18004fbdb  bts     edx, 8
0x18004fbdf  mov     [rbp+140h+var_164], edx
0x18004fbe2  mov     r9, [rsp+240h+pv]
0x18004fbe7  mov     r8d, r10d
0x18004fbea  cmp     r8d, [rsp+240h+var_1E0]
0x18004fbef  jnb     short loc_18004FC18
0x18004fbf1  mov     eax, r8d
0x18004fbf4  lea     rcx, [rax+rax*2]
0x18004fbf8  cmp     dword ptr [r9+rcx*8], 660A001Fh
0x18004fc00  jz      short loc_18004FC11
0x18004fc02  cmp     dword ptr [r9+rcx*8], 660B101Fh
0x18004fc0a  jz      short loc_18004FC11
0x18004fc0c  inc     r8d
0x18004fc0f  jmp     short loc_18004FBEA
0x18004fc11  bts     edx, 0Bh
0x18004fc15  mov     [rbp+140h+var_164], edx
0x18004fc18  mov     ecx, r10d
0x18004fc1b  cmp     ecx, [rsp+240h+var_1E0]
0x18004fc1f  jnb     short loc_18004FC98
0x18004fc21  mov     eax, ecx
0x18004fc23  lea     rdx, [rax+rax*2]
0x18004fc27  cmp     dword ptr [r9+rdx*8], 6606001Fh
0x18004fc2f  jz      short loc_18004FC35
0x18004fc31  inc     ecx
0x18004fc33  jmp     short loc_18004FC1B
0x18004fc35  mov     rcx, [r9+rdx*8+8]
0x18004fc3a  test    rcx, rcx
0x18004fc3d  jz      short loc_18004FC98
0x18004fc3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fc43  inc     rax
0x18004fc46  cmp     [rcx+rax*2], r10w
0x18004fc4b  jnz     short loc_18004FC43
0x18004fc4d  mov     r9d, 7; cchCount1
0x18004fc53  lea     r8, String1; "http://"
0x18004fc5a  cmp     rax, r9
0x18004fc5d  cmova   rax, r9
0x18004fc61  mov     [rsp+240h+cchCount2], eax; unsigned int
0x18004fc65  lea     edx, [r9-6]; dwCmpFlags
0x18004fc69  mov     [rsp+240h+lpString2], rcx; lpString2
0x18004fc6e  lea     ecx, [rdx+7Eh]; Locale
0x18004fc71  call    cs:__imp_CompareStringW
0x18004fc77  cmp     eax, 2
0x18004fc7a  jnz     short loc_18004FC95
0x18004fc7c  lea     rcx, [rbp+140h+var_148]; struct CWABDocHost **
0x18004fc80  call    ?Create@CWABDocHost@@SAJPEAPEAV1@@Z; CWABDocHost::Create(CWABDocHost * *)
0x18004fc85  xor     r10d, r10d
0x18004fc88  mov     ebx, eax
0x18004fc8a  test    eax, eax
0x18004fc8c  js      short loc_18004FC98
0x18004fc8e  bts     [rbp+140h+var_164], 9
0x18004fc93  jmp     short loc_18004FC98
0x18004fc95  xor     r10d, r10d
0x18004fc98  test    r14d, r14d
0x18004fc9b  jz      short loc_18004FCC6
0x18004fc9d  test    rsi, rsi
0x18004fca0  jz      short loc_18004FCC6
0x18004fca2  lea     r9, [rbp+140h+var_C8]; int *
0x18004fca6  mov     [rsp+240h+var_1D0], r10
0x18004fcab  lea     r8, [rsp+240h+var_1D0]; unsigned __int16 **
0x18004fcb0  mov     rdx, rsi; struct ENTRYID *
0x18004fcb3  mov     ecx, r14d; unsigned int
0x18004fcb6  call    ?CreateLDAPURLFromEntryID@@YAXKPEAUENTRYID@@PEAPEAGPEAH@Z; CreateLDAPURLFromEntryID(ulong,ENTRYID *,ushort * *,int *)
0x18004fcbb  mov     rax, [rsp+240h+var_1D0]
0x18004fcc0  mov     [rbp+140h+hMem], rax
0x18004fcc4  jmp     short loc_18004FCCA
0x18004fcc6  mov     [rbp+140h+hMem], r13
0x18004fcca  mov     r14d, 1
0x18004fcd0  lea     rcx, [rdi-278h]
0x18004fcd7  mov     rax, rdi
0x18004fcda  lea     rdx, [rbp+140h+var_1B0]; struct _PropArrayInfo *
0x18004fcde  neg     rax
0x18004fce1  mov     r9d, r14d; int
0x18004fce4  mov     r8d, r14d; int
0x18004fce7  sbb     r10, r10
0x18004fcea  and     rcx, r10; struct AddressBook *
0x18004fced  call    ?GetExtDisplayInfo@@YAJPEAVAddressBook@@PEAU_PropArrayInfo@@HH@Z; GetExtDisplayInfo(AddressBook *,_PropArrayInfo *,int,int)
0x18004fcf2  mov     r8d, 100h; unsigned int
0x18004fcf8  lea     rdx, [rbp+140h+var_1B0]; struct _PropArrayInfo *
0x18004fcfc  mov     rcx, r12; HWND
0x18004fcff  call    ?CreateDetailsPropertySheet@@YAHPEAUHWND__@@PEAU_PropArrayInfo@@K@Z; CreateDetailsPropertySheet(HWND__ *,_PropArrayInfo *,ulong)
0x18004fd04  cmp     eax, 0FFFFFFFFh
0x18004fd07  jz      loc_18004FB97
0x18004fd0d  cmp     dword ptr [rbp+140h+var_190], 3
0x18004fd11  jnz     loc_18004F9A9
0x18004fd17  xor     esi, esi
0x18004fd19  mov     ecx, esi
0x18004fd1b  mov     [rsp+240h+var_1C4], esi
0x18004fd1f  mov     [rsp+240h+var_1C8], esi
0x18004fd23  mov     [rbp+140h+var_1C0], rsi
0x18004fd27  mov     [rsp+240h+var_1D0], rsi
0x18004fd2c  cmp     [rsp+240h+var_1E0], esi
0x18004fd30  jbe     short loc_18004FD77
0x18004fd32  mov     eax, ecx
0x18004fd34  lea     rdx, [rax+rax*2]
0x18004fd38  mov     rax, [rsp+240h+pv]
0x18004fd3d  cmp     dword ptr [rax+rdx*8], 0FFF0102h
  ... truncated ...
```
