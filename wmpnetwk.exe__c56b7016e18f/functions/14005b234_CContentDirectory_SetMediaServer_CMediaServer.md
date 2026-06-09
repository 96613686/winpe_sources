# CContentDirectory::SetMediaServer(CMediaServer *)

- ea: `0x14005b234`
- end: `0x14005b668`
- name: `?SetMediaServer@CContentDirectory@@QEAAXPEAVCMediaServer@@@Z`
- size: `1076`
- prototype: `void(CContentDirectory *__hidden this, struct CMediaServer *)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x140054dc8`
- `0x140056200`

## callees

- `0x140007020`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c920`
- `0x1400105a0`
- `0x140015100`
- `0x140024688`
- `0x140025ab0`
- `0x14003d4b0`
- `0x14003d8f8`
- `0x14003f1bc`
- `0x140047798`
- `0x140054490`
- `0x14005b234`
- `0x14005ea04`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14005b28d`
- `KERNEL32!EnterCriticalSection` at `0x14005b28d`
- `KERNEL32!LeaveCriticalSection` at `0x14005b62c`
- `KERNEL32!LeaveCriticalSection` at `0x14005b62c`
- `ole32!CoTaskMemFree` at `0x14005b4ae`
- `ole32!CoTaskMemFree` at `0x14005b5ff`
- `ole32!CoTaskMemFree` at `0x14005b4ae`
- `ole32!CoTaskMemFree` at `0x14005b5ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CContentDirectory::SetMediaServer(CContentDirectory *this, struct CMediaServer *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r12
  CMediaServer *v5; // rcx
  struct IWMCContentProvider *v6; // rdi
  __int64 v7; // r14
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int AtomForElementAttribute; // eax
  _QWORD *NameForAtom; // rax
  __int64 v12; // rbx
  __int64 *v13; // rsi
  __int64 i; // rdi
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // eax
  _QWORD *v18; // rax
  __int64 v19; // rbx
  _QWORD v20[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IWMCContentProvider *v21; // [rsp+80h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF
  __int64 v23; // [rsp+90h] [rbp+50h] BYREF
  struct IWMCContentProvider *v24; // [rsp+98h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids, a2);
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 392);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  v5 = (CMediaServer *)*((_QWORD *)this + 54);
  if ( v5 )
  {
    v21 = 0;
    if ( (int)CMediaServer::GetWMCContentProvider(v5, &v21) >= 0 )
      (*(void (__fastcall **)(struct IWMCContentProvider *, _QWORD))(*(_QWORD *)v21 + 144LL))(
        v21,
        ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
  }
  if ( a2 )
  {
    v21 = 0;
    if ( (int)CMediaServer::GetWMCContentProvider(a2, &v21) >= 0 )
      (*(void (__fastcall **)(struct IWMCContentProvider *, _QWORD))(*(_QWORD *)v21 + 136LL))(
        v21,
        ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
  }
  *((_QWORD *)this + 54) = a2;
  if ( a2 )
  {
    v24 = 0;
    if ( (int)CMediaServer::GetWMCContentProvider(a2, &v24) >= 0 )
    {
      LODWORD(v21) = 0;
      pv = 0;
      v6 = v24;
      if ( (*(int (__fastcall **)(struct IWMCContentProvider *, struct IWMCContentProvider **, LPVOID *))(*(_QWORD *)v24 + 56LL))(
             v24,
             &v21,
             &pv) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 304);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            139,
            &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
            v6,
            (_DWORD)v21);
        }
        ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 304);
        v7 = 0;
        if ( (_DWORD)v21 )
        {
          do
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v23);
            AtomForElementAttribute = CdsValues::GetAtomForElementAttribute(
                                        *((unsigned int *)pv + 2 * v7),
                                        *((unsigned int *)pv + 2 * v7 + 1),
                                        v8,
                                        v9);
            if ( AtomForElementAttribute - 1 <= 0x52 )
            {
              NameForAtom = (_QWORD *)CdsValues::GetNameForAtom(v20, AtomForElementAttribute);
              ATL::CSimpleStringT<unsigned short,0>::operator=(&v23, NameForAtom);
              ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v20);
            }
            v12 = v23;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                140,
                (unsigned int)&WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
                v7,
                v23);
            }
            if ( *(_DWORD *)(v12 - 16) )
            {
              if ( *(_DWORD *)(*((_QWORD *)this + 38) - 16LL) )
                ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)this + 38, L",");
              ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)this + 38, (const void **)&v23);
            }
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v23);
            v7 = (unsigned int)(v7 + 1);
          }
          while ( (unsigned int)v7 < (unsigned int)v21 );
          v6 = v24;
        }
      }
      CoTaskMemFree(pv);
      if ( (*(int (__fastcall **)(struct IWMCContentProvider *, struct IWMCContentProvider **, LPVOID *))(*(_QWORD *)v6 + 64LL))(
             v6,
             &v21,
             &pv) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 312);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            141,
            &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
            v6,
            (_DWORD)v21);
        }
        v13 = (__int64 *)((char *)this + 312);
        ATL::CSimpleStringT<unsigned short,0>::Empty(v13);
        for ( i = 0; (unsigned int)i < (unsigned int)v21; i = (unsigned int)(i + 1) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v23);
          v17 = CdsValues::GetAtomForElementAttribute(
                  *((unsigned int *)pv + 2 * i),
                  *((unsigned int *)pv + 2 * i + 1),
                  v15,
                  v16);
          if ( v17 - 1 <= 0x52 )
          {
            v18 = (_QWORD *)CdsValues::GetNameForAtom(v20, v17);
            ATL::CSimpleStringT<unsigned short,0>::operator=(&v23, v18);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v20);
          }
          v19 = v23;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              142,
              (unsigned int)&WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
              i,
              v23);
          }
          if ( *(_DWORD *)(v19 - 16) )
          {
            if ( *(_DWORD *)(*v13 - 16) )
              ATL::CSimpleStringT<unsigned short,0>::Append(v13, L",");
            ATL::CSimpleStringT<unsigned short,0>::Append(v13, (const void **)&v23);
          }
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v23);
        }
      }
      CoTaskMemFree(pv);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v24);
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 304);
    ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 312);
  }
  LeaveCriticalSection(v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids);
}

```

## disassembly

```asm
0x14005b234  push    rbp
0x14005b236  push    rbx
0x14005b237  push    rsi
0x14005b238  push    rdi
0x14005b239  push    r12
0x14005b23b  push    r14
0x14005b23d  push    r15
0x14005b23f  mov     rbp, rsp
0x14005b242  sub     rsp, 40h
0x14005b246  mov     rbx, rdx
0x14005b249  mov     rsi, rcx
0x14005b24c  lea     r14, WPP_GLOBAL_Control
0x14005b253  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b25a  cmp     rcx, r14
0x14005b25d  jz      short loc_14005B283
0x14005b25f  test    byte ptr [rcx+1Ch], 1
0x14005b263  jz      short loc_14005B283
0x14005b265  cmp     byte ptr [rcx+19h], 5
0x14005b269  jb      short loc_14005B283
0x14005b26b  mov     edx, 8Ah
0x14005b270  mov     r9, rbx
0x14005b273  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005b27a  mov     rcx, [rcx+10h]
0x14005b27e  call    WPP_SF_q
0x14005b283  lea     r12, [rsi+188h]
0x14005b28a  mov     rcx, r12; lpCriticalSection
0x14005b28d  call    cs:__imp_EnterCriticalSection
0x14005b293  mov     rcx, [rsi+1B0h]; this
0x14005b29a  test    rcx, rcx
0x14005b29d  jz      short loc_14005B2E1
0x14005b29f  mov     [rbp+arg_0], 0
0x14005b2a7  lea     rdx, [rbp+arg_0]; struct IWMCContentProvider **
0x14005b2ab  call    ?GetWMCContentProvider@CMediaServer@@QEAAJPEAPEAUIWMCContentProvider@@@Z; CMediaServer::GetWMCContentProvider(IWMCContentProvider * *)
0x14005b2b0  test    eax, eax
0x14005b2b2  js      short loc_14005B2D8
0x14005b2b4  mov     rcx, [rbp+arg_0]
0x14005b2b8  mov     r9, [rcx]
0x14005b2bb  mov     rax, rsi
0x14005b2be  lea     r8, [rsi+8]
0x14005b2c2  neg     rax
0x14005b2c5  sbb     rdx, rdx
0x14005b2c8  and     rdx, r8
0x14005b2cb  mov     rax, [r9+90h]
0x14005b2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b2d7  nop
0x14005b2d8  lea     rcx, [rbp+arg_0]
0x14005b2dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14005b2e1  test    rbx, rbx
0x14005b2e4  jz      short loc_14005B32B
0x14005b2e6  mov     [rbp+arg_0], 0
0x14005b2ee  lea     rdx, [rbp+arg_0]; struct IWMCContentProvider **
0x14005b2f2  mov     rcx, rbx; this
0x14005b2f5  call    ?GetWMCContentProvider@CMediaServer@@QEAAJPEAPEAUIWMCContentProvider@@@Z; CMediaServer::GetWMCContentProvider(IWMCContentProvider * *)
0x14005b2fa  test    eax, eax
0x14005b2fc  js      short loc_14005B322
0x14005b2fe  mov     rcx, [rbp+arg_0]
0x14005b302  mov     r9, [rcx]
0x14005b305  mov     rax, rsi
0x14005b308  lea     r8, [rsi+8]
0x14005b30c  neg     rax
0x14005b30f  sbb     rdx, rdx
0x14005b312  and     rdx, r8
0x14005b315  mov     rax, [r9+88h]
0x14005b31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b321  nop
0x14005b322  lea     rcx, [rbp+arg_0]
0x14005b326  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14005b32b  mov     [rsi+1B0h], rbx
0x14005b332  test    rbx, rbx
0x14005b335  jz      loc_14005B611
0x14005b33b  mov     [rbp+arg_18], 0
0x14005b343  lea     rdx, [rbp+arg_18]; struct IWMCContentProvider **
0x14005b347  mov     rcx, rbx; this
0x14005b34a  call    ?GetWMCContentProvider@CMediaServer@@QEAAJPEAPEAUIWMCContentProvider@@@Z; CMediaServer::GetWMCContentProvider(IWMCContentProvider * *)
0x14005b34f  test    eax, eax
0x14005b351  js      loc_14005B606
0x14005b357  mov     dword ptr [rbp+arg_0], 0
0x14005b35e  mov     [rbp+pv], 0
0x14005b366  mov     rdi, [rbp+arg_18]
0x14005b36a  mov     rax, [rdi]
0x14005b36d  lea     r8, [rbp+pv]
0x14005b371  lea     rdx, [rbp+arg_0]
0x14005b375  mov     rcx, rdi
0x14005b378  mov     rax, [rax+38h]
0x14005b37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b381  test    eax, eax
0x14005b383  js      loc_14005B5DE
0x14005b389  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b390  cmp     rcx, r14
0x14005b393  jz      short loc_14005B3C0
0x14005b395  test    byte ptr [rcx+1Ch], 2
0x14005b399  jz      short loc_14005B3C0
0x14005b39b  cmp     byte ptr [rcx+19h], 5
0x14005b39f  jb      short loc_14005B3C0
0x14005b3a1  mov     edx, 8Bh
0x14005b3a6  mov     eax, dword ptr [rbp+arg_0]
0x14005b3a9  mov     dword ptr [rsp+40h+var_20], eax
0x14005b3ad  mov     r9, rdi
0x14005b3b0  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005b3b7  mov     rcx, [rcx+10h]
0x14005b3bb  call    WPP_SF_qD
0x14005b3c0  lea     r15, [rsi+130h]
0x14005b3c7  mov     rcx, r15
0x14005b3ca  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14005b3cf  xor     r14d, r14d
0x14005b3d2  cmp     dword ptr [rbp+arg_0], r14d
0x14005b3d6  jbe     loc_14005B4A3
0x14005b3dc  lea     rdi, WPP_GLOBAL_Control
0x14005b3e3  lea     rcx, [rbp+arg_10]
0x14005b3e7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14005b3ec  mov     rcx, [rbp+pv]
0x14005b3f0  mov     edx, [rcx+r14*8+4]
0x14005b3f5  mov     ecx, [rcx+r14*8]
0x14005b3f9  call    ?GetAtomForElementAttribute@CdsValues@@SA?AW4Value@CdsValue@@W4CDS_ELEMENT_VALUE@@W4CDS_ATTRIBUTE_VALUE@@@Z; CdsValues::GetAtomForElementAttribute(CDS_ELEMENT_VALUE,CDS_ATTRIBUTE_VALUE)
0x14005b3fe  lea     ecx, [rax-1]
0x14005b401  cmp     ecx, 52h ; 'R'
0x14005b404  ja      short loc_14005B426
0x14005b406  mov     edx, eax
0x14005b408  lea     rcx, [rbp+var_10]
0x14005b40c  call    ?GetNameForAtom@CdsValues@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@W4Value@CdsValue@@@Z; CdsValues::GetNameForAtom(CdsValue::Value)
0x14005b411  mov     rdx, rax
0x14005b414  lea     rcx, [rbp+arg_10]
0x14005b418  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14005b41d  lea     rcx, [rbp+var_10]
0x14005b421  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005b426  mov     rbx, [rbp+arg_10]
0x14005b42a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b431  cmp     rcx, rdi
0x14005b434  jz      short loc_14005B45F
0x14005b436  test    byte ptr [rcx+1Ch], 2
0x14005b43a  jz      short loc_14005B45F
0x14005b43c  cmp     byte ptr [rcx+19h], 5
0x14005b440  jb      short loc_14005B45F
0x14005b442  mov     edx, 8Ch
0x14005b447  mov     [rsp+40h+var_20], rbx
0x14005b44c  mov     r9d, r14d
0x14005b44f  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005b456  mov     rcx, [rcx+10h]
0x14005b45a  call    WPP_SF_dS
0x14005b45f  cmp     dword ptr [rbx-10h], 0
0x14005b463  jz      short loc_14005B489
0x14005b465  mov     rax, [r15]
0x14005b468  cmp     dword ptr [rax-10h], 0
0x14005b46c  jz      short loc_14005B47D
0x14005b46e  lea     rdx, asc_1400A3E98; ","
0x14005b475  mov     rcx, r15
0x14005b478  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14005b47d  lea     rdx, [rbp+arg_10]
0x14005b481  mov     rcx, r15
0x14005b484  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x14005b489  lea     rcx, [rbp+arg_10]
0x14005b48d  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005b492  inc     r14d
0x14005b495  cmp     r14d, dword ptr [rbp+arg_0]
0x14005b499  jb      loc_14005B3E3
0x14005b49f  mov     rdi, [rbp+arg_18]
0x14005b4a3  lea     r14, WPP_GLOBAL_Control
0x14005b4aa  mov     rcx, [rbp+pv]; pv
0x14005b4ae  call    cs:__imp_CoTaskMemFree
0x14005b4b4  mov     rax, [rdi]
0x14005b4b7  lea     r8, [rbp+pv]
0x14005b4bb  lea     rdx, [rbp+arg_0]
0x14005b4bf  mov     rcx, rdi
0x14005b4c2  mov     rax, [rax+40h]
0x14005b4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b4cb  test    eax, eax
0x14005b4cd  js      loc_14005B5EF
0x14005b4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b4da  cmp     rcx, r14
0x14005b4dd  jz      short loc_14005B50A
0x14005b4df  test    byte ptr [rcx+1Ch], 2
0x14005b4e3  jz      short loc_14005B50A
0x14005b4e5  cmp     byte ptr [rcx+19h], 5
0x14005b4e9  jb      short loc_14005B50A
0x14005b4eb  mov     edx, 8Dh
0x14005b4f0  mov     eax, dword ptr [rbp+arg_0]
0x14005b4f3  mov     dword ptr [rsp+40h+var_20], eax
0x14005b4f7  mov     r9, rdi
0x14005b4fa  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005b501  mov     rcx, [rcx+10h]
0x14005b505  call    WPP_SF_qD
0x14005b50a  add     rsi, 138h
0x14005b511  mov     rcx, rsi
0x14005b514  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14005b519  xor     edi, edi
0x14005b51b  cmp     dword ptr [rbp+arg_0], edi
0x14005b51e  jbe     loc_14005B5FB
0x14005b524  lea     rcx, [rbp+arg_10]
0x14005b528  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14005b52d  mov     rcx, [rbp+pv]
0x14005b531  mov     edx, [rcx+rdi*8+4]
0x14005b535  mov     ecx, [rcx+rdi*8]
0x14005b538  call    ?GetAtomForElementAttribute@CdsValues@@SA?AW4Value@CdsValue@@W4CDS_ELEMENT_VALUE@@W4CDS_ATTRIBUTE_VALUE@@@Z; CdsValues::GetAtomForElementAttribute(CDS_ELEMENT_VALUE,CDS_ATTRIBUTE_VALUE)
0x14005b53d  lea     ecx, [rax-1]
0x14005b540  cmp     ecx, 52h ; 'R'
0x14005b543  ja      short loc_14005B565
0x14005b545  mov     edx, eax
0x14005b547  lea     rcx, [rbp+var_10]
0x14005b54b  call    ?GetNameForAtom@CdsValues@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@W4Value@CdsValue@@@Z; CdsValues::GetNameForAtom(CdsValue::Value)
0x14005b550  mov     rdx, rax
0x14005b553  lea     rcx, [rbp+arg_10]
0x14005b557  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14005b55c  lea     rcx, [rbp+var_10]
0x14005b560  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005b565  mov     rbx, [rbp+arg_10]
0x14005b569  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b570  cmp     rcx, r14
0x14005b573  jz      short loc_14005B59E
0x14005b575  test    byte ptr [rcx+1Ch], 2
0x14005b579  jz      short loc_14005B59E
0x14005b57b  cmp     byte ptr [rcx+19h], 5
0x14005b57f  jb      short loc_14005B59E
0x14005b581  mov     edx, 8Eh
0x14005b586  mov     [rsp+40h+var_20], rbx
0x14005b58b  mov     r9d, edi
0x14005b58e  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005b595  mov     rcx, [rcx+10h]
0x14005b599  call    WPP_SF_dS
0x14005b59e  cmp     dword ptr [rbx-10h], 0
0x14005b5a2  jz      short loc_14005B5C8
0x14005b5a4  mov     rax, [rsi]
0x14005b5a7  cmp     dword ptr [rax-10h], 0
0x14005b5ab  jz      short loc_14005B5BC
0x14005b5ad  lea     rdx, asc_1400A3E98; ","
0x14005b5b4  mov     rcx, rsi
0x14005b5b7  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14005b5bc  lea     rdx, [rbp+arg_10]
0x14005b5c0  mov     rcx, rsi
0x14005b5c3  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x14005b5c8  lea     rcx, [rbp+arg_10]
0x14005b5cc  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005b5d1  inc     edi
0x14005b5d3  cmp     edi, dword ptr [rbp+arg_0]
0x14005b5d6  jb      loc_14005B524
0x14005b5dc  jmp     short loc_14005B5FB
0x14005b5de  lea     rcx, [rsi+130h]
0x14005b5e5  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14005b5ea  jmp     loc_14005B4AA
0x14005b5ef  lea     rcx, [rsi+138h]
0x14005b5f6  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14005b5fb  mov     rcx, [rbp+pv]; pv
0x14005b5ff  call    cs:__imp_CoTaskMemFree
0x14005b605  nop
0x14005b606  lea     rcx, [rbp+arg_18]
0x14005b60a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14005b60f  jmp     short loc_14005B629
0x14005b611  lea     rcx, [rsi+130h]
0x14005b618  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14005b61d  lea     rcx, [rsi+138h]
0x14005b624  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14005b629  mov     rcx, r12; lpCriticalSection
0x14005b62c  call    cs:__imp_LeaveCriticalSection
0x14005b632  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b639  cmp     rcx, r14
0x14005b63c  jz      short loc_14005B659
0x14005b63e  test    byte ptr [rcx+1Ch], 1
0x14005b642  jz      short loc_14005B659
0x14005b644  mov     edx, 90h
0x14005b649  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005b650  mov     rcx, [rcx+10h]
0x14005b654  call    WPP_SF_
0x14005b659  add     rsp, 40h
0x14005b65d  pop     r15
0x14005b65f  pop     r14
0x14005b661  pop     r12
0x14005b663  pop     rdi
0x14005b664  pop     rsi
0x14005b665  pop     rbx
0x14005b666  pop     rbp
0x14005b667  retn
```
