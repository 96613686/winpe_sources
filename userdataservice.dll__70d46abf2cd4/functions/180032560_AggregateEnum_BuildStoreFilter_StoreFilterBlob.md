# AggregateEnum::BuildStoreFilter(StoreFilterBlob *)

- ea: `0x180032560`
- end: `0x180032a43`
- name: `?BuildStoreFilter@AggregateEnum@@IEAAJPEAUStoreFilterBlob@@@Z`
- size: `1251`
- prototype: `__int64 __fastcall(AggregateEnum *__hidden this, struct StoreFilterBlob *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032250`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180011838`
- `0x18001e940`
- `0x180032560`
- `0x180032a4c`
- `0x180032ad0`
- `0x18005ea14`
- `0x180124e00`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!GetDefaultStoreFilter` at `0x18003261f`
- `PIMSTORE!GetDefaultStoreFilter` at `0x1800327a1`
- `PIMSTORE!GetDefaultStoreFilter` at `0x18003261f`
- `PIMSTORE!GetDefaultStoreFilter` at `0x1800327a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003284c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800328df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800329eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003284c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800328df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800329eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a36`

## string_xrefs

- `0x180032766`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x1800327b7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180032802`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180032832`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x1800328b7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x1800328cb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x1800329bf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x1800329d7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x1800329fb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`

## pseudocode

```c
__int64 __fastcall AggregateEnum::BuildStoreFilter(AggregateEnum *this, struct StoreFilterBlob *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, __int64, _DWORD *, __int16, void **); // rbx
  void **v9; // rax
  int v10; // eax
  _BOOL8 v11; // rdx
  int DefaultStoreFilter; // eax
  int CommonSetBits; // eax
  HLOCAL v14; // rbx
  __int64 *v15; // rax
  int v16; // r10d
  __int64 v17; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rdx
  _QWORD *v25; // rax
  unsigned int i; // r9d
  int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rax
  _QWORD *v30; // r8
  unsigned int v31; // r9d
  __int64 v32; // xmm0_8
  int v33; // r9d
  __int64 v34; // r10
  int v35; // eax
  int v36; // edi
  int v37; // [rsp+40h] [rbp-39h] BYREF
  int v38; // [rsp+44h] [rbp-35h]
  HLOCAL hMem; // [rsp+48h] [rbp-31h]
  int v40; // [rsp+50h] [rbp-29h] BYREF
  int v41; // [rsp+54h] [rbp-25h]
  HLOCAL v42; // [rsp+58h] [rbp-21h]
  _QWORD *v43; // [rsp+60h] [rbp-19h] BYREF
  __int64 v44; // [rsp+68h] [rbp-11h] BYREF
  HLOCAL v45[2]; // [rsp+70h] [rbp-9h] BYREF
  _DWORD v46[2]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v47; // [rsp+88h] [rbp+Fh] BYREF
  int v48; // [rsp+90h] [rbp+17h]

  v4 = *((_QWORD *)this + 22);
  v44 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 88LL))(v4, &v44);
  v6 = v5;
  if ( v5 < 0 )
  {
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1393);
LABEL_18:
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    return v6;
  }
  v7 = v44;
  v46[0] = 327698;
  v46[1] = 29556747;
  v43 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _DWORD *, __int16, void **))(*(_QWORD *)v44 + 120LL);
  v9 = tlx::replace<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>((void **)&v43);
  v10 = v8(v7, 1, 0xFFFFFFFFLL, v46, 2, v9);
  v6 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1403);
LABEL_17:
    tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v43);
    goto LABEL_18;
  }
  v11 = *((_DWORD *)this + 49) == 0;
  v40 = 0;
  v41 = v38;
  v42 = 0;
  DefaultStoreFilter = GetDefaultStoreFilter(&v40, v11);
  v6 = DefaultStoreFilter;
  if ( DefaultStoreFilter < 0 )
  {
    Log_HREvent(
      (unsigned int)DefaultStoreFilter,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1407);
    LocalFree(v42);
    v41 = v38;
    goto LABEL_29;
  }
  if ( *((_DWORD *)this + 49) )
  {
    v25 = v43;
    for ( i = 0; i < *(_DWORD *)v25; ++i )
    {
      v21 = *(_QWORD *)(v25[3] + 8LL * i);
      if ( (*(_WORD *)(v21 + 30) & 0x300) != 0 || *(_DWORD *)(v21 + 32) )
      {
        if ( (*(_WORD *)(v21 + 6) & 0x300) != 0 )
        {
          v6 = -2147418113;
          v22 = 1420;
          v23 = 2147549183LL;
          v24 = 0;
          goto LABEL_33;
        }
        v27 = StoreFilterBlob::SetNthBlobBit((StoreFilterBlob *)&v40, *(unsigned __int16 *)(v21 + 8));
        v6 = v27;
        if ( v27 < 0 )
        {
          v22 = 1421;
          v24 = 1;
          v23 = (unsigned int)v27;
LABEL_33:
          Log_HREvent(
            v23,
            v24,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
            v22);
LABEL_27:
          LocalFree(v42);
          goto LABEL_28;
        }
        v25 = v43;
      }
    }
  }
  v37 = 0;
  hMem = 0;
  if ( !*((_DWORD *)this + 50) )
  {
LABEL_6:
    HIDWORD(v45[0]) = v38;
    LODWORD(v45[0]) = 0;
    v45[1] = 0;
    CommonSetBits = StoreFilterBlob::GetCommonSetBits(
                      (StoreFilterBlob *)&v40,
                      (const struct _SQLCEBLOB *)&v37,
                      (struct _SQLCEBLOB *)v45);
    v6 = CommonSetBits;
    if ( CommonSetBits >= 0 )
    {
      v14 = v45[1];
      v15 = (__int64 *)*((_QWORD *)this + 41);
      v16 = (int)v45[0];
      while ( v15 != (__int64 *)((char *)this + 328) )
      {
        v17 = *(__int64 *)((char *)v15 + 36);
        if ( !(_DWORD)v17 )
        {
          if ( 8 * v16 <= (unsigned int)WORD2(v17) )
          {
            v36 = -2147024809;
            Log_HREvent(
              2147942487LL,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
              1455);
            LocalFree(v14);
            goto LABEL_57;
          }
          *((_BYTE *)v14 + ((unsigned __int64)WORD2(v17) >> 3)) &= ~(1 << (BYTE4(v17) & 7));
        }
        v15 = (__int64 *)*v15;
      }
      *(_OWORD *)a2 = *(_OWORD *)v45;
      LocalFree(0);
      LocalFree(hMem);
      v37 = 0;
      hMem = 0;
      LocalFree(v42);
      v41 = v38;
      v40 = 0;
      v42 = 0;
      tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v43);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      return 0;
    }
    Log_HREvent(
      (unsigned int)CommonSetBits,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1448);
    LocalFree(v45[1]);
LABEL_26:
    LocalFree(hMem);
    v37 = 0;
    hMem = 0;
    goto LABEL_27;
  }
  v19 = GetDefaultStoreFilter(&v37, 0);
  v6 = v19;
  if ( v19 < 0 )
  {
    Log_HREvent(
      (unsigned int)v19,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1430);
    LocalFree(hMem);
    v37 = 0;
    hMem = 0;
    LocalFree(v42);
    v41 = v38;
    v40 = 0;
    v42 = 0;
    goto LABEL_17;
  }
  v28 = 0;
LABEL_45:
  if ( v28 >= *((_DWORD *)this + 50) )
    goto LABEL_6;
  v29 = UdmIdToPoomId(v45, *((_QWORD *)this + 26) + 12LL * v28);
  v30 = v43;
  v31 = 0;
  v32 = *(_QWORD *)v29;
  LODWORD(v29) = *(_DWORD *)(v29 + 8);
  v47 = v32;
  v48 = v29;
  while ( 1 )
  {
    if ( v31 >= *(_DWORD *)v30 )
    {
      ++v28;
      goto LABEL_45;
    }
    if ( (unsigned __int8)operator==(&v47, v30[1] + 12LL * v31) )
      break;
LABEL_52:
    v31 = v33 + 1;
  }
  v20 = *(_QWORD *)(v30[3] + 8 * v34);
  if ( (*(_WORD *)(v20 + 6) & 0x300) != 0 )
  {
    v6 = -2147418113;
    Log_HREvent(
      2147549183LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1439);
    goto LABEL_26;
  }
  v35 = StoreFilterBlob::SetNthBlobBit((StoreFilterBlob *)&v37, *(unsigned __int16 *)(v20 + 8));
  v36 = v35;
  if ( v35 >= 0 )
  {
    v30 = v43;
    goto LABEL_52;
  }
  Log_HREvent(
    (unsigned int)v35,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
    1440);
LABEL_57:
  LocalFree(hMem);
  v37 = 0;
  hMem = 0;
  LocalFree(v42);
  v6 = v36;
LABEL_28:
  v41 = v38;
LABEL_29:
  v40 = 0;
  v42 = 0;
  tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&void FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(&v43);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
  return v6;
}

```

## disassembly

```asm
0x180032560  mov     [rsp-8+arg_10], rbx
0x180032565  push    rbp
0x180032566  push    rsi
0x180032567  push    rdi
0x180032568  push    r12
0x18003256a  push    r13
0x18003256c  push    r14
0x18003256e  push    r15
0x180032570  lea     rbp, [rsp-27h]
0x180032575  sub     rsp, 0A0h
0x18003257c  mov     r14, rcx
0x18003257f  mov     r15, rdx
0x180032582  mov     rcx, [rcx+0B0h]
0x180032589  lea     rdx, [rbp+57h+var_68]
0x18003258d  xor     r12d, r12d
0x180032590  mov     [rbp+57h+var_68], r12
0x180032594  mov     rax, [rcx]
0x180032597  mov     rax, [rax+58h]
0x18003259b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325a0  mov     ebx, eax
0x1800325a2  test    eax, eax
0x1800325a4  js      loc_1800327FC
0x1800325aa  mov     rdi, [rbp+57h+var_68]
0x1800325ae  lea     rcx, [rbp+57h+var_70]
0x1800325b2  mov     [rbp+57h+var_50], 50012h
0x1800325b9  mov     [rbp+57h+var_4C], 1C3000Bh
0x1800325c0  mov     [rbp+57h+var_70], r12
0x1800325c4  mov     rax, [rdi]
0x1800325c7  mov     rbx, [rax+78h]
0x1800325cb  call    ??$replace@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@YAPEAPEAU_USPROPVALBATCH@@AEAV?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@0@@Z; tlx::replace<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0> &)
0x1800325d0  mov     [rsp+0D0h+var_A8], rax
0x1800325d5  lea     esi, [r12+1]
0x1800325da  mov     edx, esi
0x1800325dc  mov     [rsp+0D0h+var_B0], 2
0x1800325e3  mov     rax, rbx
0x1800325e6  lea     r9, [rbp+57h+var_50]
0x1800325ea  or      r8d, 0FFFFFFFFh
0x1800325ee  mov     rcx, rdi
0x1800325f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325f6  mov     ebx, eax
0x1800325f8  test    eax, eax
0x1800325fa  js      loc_180032760
0x180032600  cmp     [r14+0C4h], r12d
0x180032607  lea     rcx, [rbp+57h+var_80]
0x18003260b  mov     eax, [rbp+57h+var_8C]
0x18003260e  mov     edx, r12d
0x180032611  setz    dl
0x180032614  mov     [rbp+57h+var_80], r12d
0x180032618  mov     [rbp+57h+var_7C], eax
0x18003261b  mov     [rbp+57h+var_78], r12
0x18003261f  call    cs:__imp_GetDefaultStoreFilter
0x180032625  mov     ebx, eax
0x180032627  test    eax, eax
0x180032629  js      loc_1800328C5
0x18003262f  mov     r13d, 300h
0x180032635  cmp     [r14+0C4h], r12d
0x18003263c  jnz     loc_1800328ED
0x180032642  mov     eax, [rbp+57h+var_8C]
0x180032645  mov     [rbp+57h+var_8C], eax
0x180032648  mov     [rbp+57h+var_90], r12d
0x18003264c  mov     [rbp+57h+hMem], r12
0x180032650  cmp     [r14+0C8h], r12d
0x180032657  ja      loc_18003279B
0x18003265d  mov     eax, [rbp+57h+var_8C]
0x180032660  lea     r8, [rbp+57h+var_60]; struct _SQLCEBLOB *
0x180032664  lea     rdx, [rbp+57h+var_90]; struct _SQLCEBLOB *
0x180032668  mov     dword ptr [rbp+57h+var_60+4], eax
0x18003266b  lea     rcx, [rbp+57h+var_80]; this
0x18003266f  mov     dword ptr [rbp+57h+var_60], r12d
0x180032673  mov     [rbp+57h+var_60+8], r12
0x180032677  call    ?GetCommonSetBits@StoreFilterBlob@@QEBAJPEBU_SQLCEBLOB@@PEAU2@@Z; StoreFilterBlob::GetCommonSetBits(_SQLCEBLOB const *,_SQLCEBLOB *)
0x18003267c  mov     ebx, eax
0x18003267e  test    eax, eax
0x180032680  js      loc_1800329D1
0x180032686  mov     rbx, [rbp+57h+var_60+8]
0x18003268a  lea     rdx, [r14+148h]
0x180032691  mov     rax, [rdx]
0x180032694  mov     r10d, dword ptr [rbp+57h+var_60]
0x180032698  cmp     rax, rdx
0x18003269b  jz      short loc_1800326AE
0x18003269d  mov     rcx, [rax+24h]
0x1800326a1  test    ecx, ecx
0x1800326a3  jz      loc_18003272A
0x1800326a9  mov     rax, [rax]
0x1800326ac  jmp     short loc_180032698
0x1800326ae  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x1800326b2  xor     ecx, ecx; hMem
0x1800326b4  movdqu  xmmword ptr [r15], xmm0
0x1800326b9  call    cs:__imp_LocalFree
0x1800326bf  mov     rcx, [rbp+57h+hMem]; hMem
0x1800326c3  call    cs:__imp_LocalFree
0x1800326c9  mov     eax, [rbp+57h+var_8C]
0x1800326cc  mov     rcx, [rbp+57h+var_78]; hMem
0x1800326d0  mov     [rbp+57h+var_8C], eax
0x1800326d3  mov     [rbp+57h+var_90], r12d
0x1800326d7  mov     [rbp+57h+hMem], r12
0x1800326db  call    cs:__imp_LocalFree
0x1800326e1  mov     eax, [rbp+57h+var_8C]
0x1800326e4  lea     rcx, [rbp+57h+var_70]
0x1800326e8  mov     [rbp+57h+var_7C], eax
0x1800326eb  mov     [rbp+57h+var_80], r12d
0x1800326ef  mov     [rbp+57h+var_78], r12
0x1800326f3  call    ??1?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(void)
0x1800326f8  mov     rcx, [rbp+57h+var_68]
0x1800326fc  test    rcx, rcx
0x1800326ff  jz      short loc_18003270D
0x180032701  mov     rax, [rcx]
0x180032704  mov     rax, [rax+10h]
0x180032708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003270d  xor     eax, eax
0x18003270f  mov     rbx, [rsp+0D0h+arg_10]
0x180032717  add     rsp, 0A0h
0x18003271e  pop     r15
0x180032720  pop     r14
0x180032722  pop     r13
0x180032724  pop     r12
0x180032726  pop     rdi
0x180032727  pop     rsi
0x180032728  pop     rbp
0x180032729  retn
0x18003272a  shr     rcx, 20h
0x18003272e  movzx   r9d, cx
0x180032732  lea     ecx, ds:0[r10*8]
0x18003273a  cmp     ecx, r9d
0x18003273d  jbe     loc_1800329F6
0x180032743  mov     r8d, r9d
0x180032746  and     r9d, 7
0x18003274a  shr     r8, 3
0x18003274e  movzx   ecx, byte ptr [r8+rbx]
0x180032753  btr     ecx, r9d
0x180032757  mov     [r8+rbx], cl
0x18003275b  jmp     loc_1800326A9
0x180032760  mov     r9d, 57Bh
0x180032766  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003276d  mov     edx, esi
0x18003276f  mov     ecx, ebx
0x180032771  call    Log_HREvent
0x180032776  lea     rcx, [rbp+57h+var_70]
0x18003277a  call    ??1?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(void)
0x18003277f  mov     rcx, [rbp+57h+var_68]
0x180032783  test    rcx, rcx
0x180032786  jz      short loc_180032794
0x180032788  mov     rax, [rcx]
0x18003278b  mov     rax, [rax+10h]
0x18003278f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032794  mov     eax, ebx
0x180032796  jmp     loc_18003270F
0x18003279b  xor     edx, edx
0x18003279d  lea     rcx, [rbp+57h+var_90]
0x1800327a1  call    cs:__imp_GetDefaultStoreFilter
0x1800327a7  mov     ebx, eax
0x1800327a9  test    eax, eax
0x1800327ab  jns     loc_180032930
0x1800327b1  mov     r9d, 596h
0x1800327b7  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800327be  mov     edx, esi
0x1800327c0  mov     ecx, eax
0x1800327c2  call    Log_HREvent
0x1800327c7  mov     rcx, [rbp+57h+hMem]; hMem
0x1800327cb  call    cs:__imp_LocalFree
0x1800327d1  mov     ecx, [rbp+57h+var_8C]
0x1800327d4  mov     [rbp+57h+var_8C], ecx
0x1800327d7  mov     rcx, [rbp+57h+var_78]; hMem
0x1800327db  mov     [rbp+57h+var_90], r12d
0x1800327df  mov     [rbp+57h+hMem], r12
0x1800327e3  call    cs:__imp_LocalFree
0x1800327e9  mov     eax, [rbp+57h+var_8C]
0x1800327ec  mov     [rbp+57h+var_7C], eax
0x1800327ef  mov     [rbp+57h+var_80], r12d
0x1800327f3  mov     [rbp+57h+var_78], r12
0x1800327f7  jmp     loc_180032776
0x1800327fc  mov     r9d, 571h
0x180032802  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180032809  mov     edx, 1
0x18003280e  mov     ecx, ebx
0x180032810  call    Log_HREvent
0x180032815  jmp     loc_18003277F
0x18003281a  mov     rax, [r8+18h]
0x18003281e  mov     rcx, [rax+r10*8]
0x180032822  test    [rcx+6], r13w
0x180032827  jz      loc_180032996
0x18003282d  mov     ebx, 8000FFFFh
0x180032832  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180032839  mov     ecx, ebx
0x18003283b  mov     r9d, 59Fh
0x180032841  xor     edx, edx
0x180032843  call    Log_HREvent
0x180032848  mov     rcx, [rbp+57h+hMem]; hMem
0x18003284c  call    cs:__imp_LocalFree
0x180032852  mov     eax, [rbp+57h+var_8C]
0x180032855  mov     [rbp+57h+var_8C], eax
0x180032858  mov     [rbp+57h+var_90], r12d
0x18003285c  mov     [rbp+57h+hMem], r12
0x180032860  mov     rcx, [rbp+57h+var_78]; hMem
0x180032864  call    cs:__imp_LocalFree
0x18003286a  mov     eax, [rbp+57h+var_8C]
0x18003286d  mov     [rbp+57h+var_7C], eax
0x180032870  lea     rcx, [rbp+57h+var_70]
0x180032874  mov     [rbp+57h+var_80], r12d
0x180032878  mov     [rbp+57h+var_78], r12
0x18003287c  call    ??1?$auto_xxx@PEAU_USPROPVALBATCH@@P6AXPEAU1@@Z$1?FreeUSPROPVALBATCH@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>::~auto_xxx<_USPROPVALBATCH *,void (*)(_USPROPVALBATCH *),&FreeUSPROPVALBATCH(_USPROPVALBATCH *),0>(void)
0x180032881  lea     rcx, [rbp+57h+var_68]
0x180032885  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18003288a  jmp     loc_180032794
0x18003288f  mov     rcx, [rax+18h]
0x180032893  mov     edx, r9d
0x180032896  mov     r8, [rcx+rdx*8]
0x18003289a  test    [r8+1Eh], r13w
0x18003289f  jz      short loc_1800328FF
0x1800328a1  test    [r8+6], r13w
0x1800328a6  jz      short loc_180032907
0x1800328a8  mov     ebx, 8000FFFFh
0x1800328ad  mov     r9d, 58Ch
0x1800328b3  mov     ecx, ebx
0x1800328b5  xor     edx, edx
0x1800328b7  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800328be  call    Log_HREvent
0x1800328c3  jmp     short loc_180032860
0x1800328c5  mov     r9d, 57Fh
0x1800328cb  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800328d2  mov     edx, esi
0x1800328d4  mov     ecx, eax
0x1800328d6  call    Log_HREvent
0x1800328db  mov     rcx, [rbp+57h+var_78]; hMem
0x1800328df  call    cs:__imp_LocalFree
0x1800328e5  mov     ecx, [rbp+57h+var_8C]
0x1800328e8  mov     [rbp+57h+var_7C], ecx
0x1800328eb  jmp     short loc_180032870
0x1800328ed  mov     rax, [rbp+57h+var_70]
0x1800328f1  mov     r9d, r12d
0x1800328f4  cmp     r9d, [rax]
0x1800328f7  jnb     loc_180032642
0x1800328fd  jmp     short loc_18003288F
0x1800328ff  cmp     [r8+20h], r12d
0x180032903  jz      short loc_18003291F
0x180032905  jmp     short loc_1800328A1
0x180032907  movzx   edx, word ptr [r8+8]; unsigned int
0x18003290c  lea     rcx, [rbp+57h+var_80]; this
0x180032910  call    ?SetNthBlobBit@StoreFilterBlob@@QEAAJI@Z; StoreFilterBlob::SetNthBlobBit(uint)
0x180032915  mov     ebx, eax
0x180032917  test    eax, eax
0x180032919  js      short loc_180032924
0x18003291b  mov     rax, [rbp+57h+var_70]
0x18003291f  add     r9d, esi
0x180032922  jmp     short loc_1800328F4
0x180032924  mov     r9d, 58Dh
0x18003292a  mov     edx, esi
0x18003292c  mov     ecx, eax
0x18003292e  jmp     short loc_1800328B7
0x180032930  mov     ebx, r12d
0x180032933  cmp     ebx, [r14+0C8h]
0x18003293a  jnb     loc_18003265D
0x180032940  mov     eax, ebx
0x180032942  lea     rcx, [rax+rax*2]
0x180032946  mov     rax, [r14+0D0h]
0x18003294d  lea     rdx, [rax+rcx*4]
0x180032951  lea     rcx, [rbp+57h+var_60]
0x180032955  call    ?UdmIdToPoomId@@YA?AUOLITEMID@@AEBUUdmObjectId@@@Z; UdmIdToPoomId(UdmObjectId const &)
0x18003295a  mov     r8, [rbp+57h+var_70]
0x18003295e  mov     r9d, r12d
0x180032961  movsd   xmm0, qword ptr [rax]
0x180032965  mov     eax, [rax+8]
0x180032968  movsd   [rbp+57h+var_48], xmm0
0x18003296d  mov     [rbp+57h+var_40], eax
0x180032970  cmp     r9d, [r8]
0x180032973  jnb     short loc_1800329B2
0x180032975  mov     rax, [r8+8]
0x180032979  mov     r10d, r9d
0x18003297c  lea     rcx, [r10+r10*2]
0x180032980  lea     rdx, [rax+rcx*4]
0x180032984  lea     rcx, [rbp+57h+var_48]
0x180032988  call    ??8@YA_NAEBUOLITEMID@@0@Z; operator==(OLITEMID const &,OLITEMID const &)
0x18003298d  test    al, al
0x18003298f  jz      short loc_1800329AD
0x180032991  jmp     loc_18003281A
0x180032996  movzx   edx, word ptr [rcx+8]; unsigned int
0x18003299a  lea     rcx, [rbp+57h+var_90]; this
0x18003299e  call    ?SetNthBlobBit@StoreFilterBlob@@QEAAJI@Z; StoreFilterBlob::SetNthBlobBit(uint)
0x1800329a3  mov     edi, eax
0x1800329a5  test    eax, eax
0x1800329a7  js      short loc_1800329B9
0x1800329a9  mov     r8, [rbp+57h+var_70]
0x1800329ad  add     r9d, esi
0x1800329b0  jmp     short loc_180032970
0x1800329b2  add     ebx, esi
0x1800329b4  jmp     loc_180032933
0x1800329b9  mov     r9d, 5A0h
0x1800329bf  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800329c6  mov     edx, esi
0x1800329c8  mov     ecx, edi
0x1800329ca  call    Log_HREvent
0x1800329cf  jmp     short loc_180032A1A
0x1800329d1  mov     r9d, 5A8h
0x1800329d7  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800329de  mov     edx, esi
0x1800329e0  mov     ecx, eax
0x1800329e2  call    Log_HREvent
0x1800329e7  mov     rcx, [rbp+57h+var_60+8]; hMem
0x1800329eb  call    cs:__imp_LocalFree
0x1800329f1  jmp     loc_180032848
  ... truncated ...
```
