# CThemeManager2::ImportRoamingThemeFromStream(IStream *,int)

- ea: `0x180054390`
- end: `0x1800547b9`
- name: `?ImportRoamingThemeFromStream@CThemeManager2@@UEAAJPEAUIStream@@H@Z`
- size: `1065`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b328`
- `0x1800358c0`
- `0x18003c1f4`
- `0x18003cf08`
- `0x1800427dc`
- `0x180042f84`
- `0x180054390`
- `0x180055d7c`
- `0x1800560f4`
- `0x180056450`
- `0x180061d68`
- `0x180061e30`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800545d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005475a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800545d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005475a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054516`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054627`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054682`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800546e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054516`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054627`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054682`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800546e5`
- `PROPSYS!PropVariantToGUID` at `0x18005461b`
- `PROPSYS!PropVariantToGUID` at `0x18005461b`
- `PROPSYS!PropVariantToUInt32` at `0x1800546d5`
- `PROPSYS!PropVariantToUInt32` at `0x1800546d5`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180054405`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180054405`
- `PROPSYS!PropVariantToInt32` at `0x180054506`
- `PROPSYS!PropVariantToInt32` at `0x180054506`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThemeManager2::ImportRoamingThemeFromStream(
        CThemeManager2 *this,
        struct IStream *a2,
        unsigned int a3)
{
  HRESULT String; // ebx
  __int64 v7; // rdx
  void *v8; // rcx
  int v9; // edx
  const struct _GUID *v10; // rdx
  void *ppv; // [rsp+30h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-21h] BYREF
  LONG plRet; // [rsp+40h] [rbp-19h] BYREF
  ULONG pulRet; // [rsp+44h] [rbp-15h] BYREF
  LPVOID v16; // [rsp+48h] [rbp-11h] BYREF
  struct tagPROPVARIANT propvar; // [rsp+50h] [rbp-9h] BYREF
  void *v18; // [rsp+68h] [rbp+Fh] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v20; // [rsp+80h] [rbp+27h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids, a3);
  ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&ppv);
  String = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( String >= 0 )
  {
    pv = 0;
    String = (**(__int64 (__fastcall ***)(void *, GUID *, LPVOID *))ppv)(
               ppv,
               &GUID_00000109_0000_0000_c000_000000000046,
               &pv);
    if ( String >= 0 )
    {
      String = (*(__int64 (__fastcall **)(LPVOID, struct IStream *))(*(_QWORD *)pv + 40LL))(pv, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      if ( String >= 0 )
      {
        v16 = 0;
        String = IPropertyStore_GetString(ppv, v7, &v16);
        if ( String >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids, v16);
          plRet = 0;
          *(_OWORD *)propvarIn = 0;
          v20 = 0;
          String = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 40LL))(
                     ppv,
                     qword_18007A7D0,
                     propvarIn);
          if ( String < 0 )
            goto LABEL_45;
          String = LOWORD(propvarIn[0]) ? PropVariantToInt32(propvarIn, &plRet) : -2147023728;
          PropVariantClear(propvarIn);
          if ( String < 0 )
            goto LABEL_45;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids,
              (unsigned int)plRet);
          if ( plRet == -1 )
          {
LABEL_44:
            String = -2147467259;
            goto LABEL_45;
          }
          if ( plRet )
          {
            if ( plRet == 1 || plRet == 3 )
            {
              pv = 0;
              String = CThemeManager2::_GetInboxThemePath(v8, (unsigned int)plRet, v16, &pv);
              if ( String >= 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids, pv);
                }
                String = CThemeManager2::_OpenInboxTheme(this, v9, (const unsigned __int16 *)pv);
                CoTaskMemFree(pv);
              }
              goto LABEL_45;
            }
            goto LABEL_44;
          }
          *(_OWORD *)propvarIn = 0;
          memset(&propvar, 0, sizeof(propvar));
          String = (*(__int64 (__fastcall **)(void *, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 40LL))(
                     ppv,
                     qword_18007A818,
                     &propvar);
          if ( String < 0 )
            goto LABEL_45;
          String = PropVariantToGUID((const PROPVARIANT *const)&propvar, (GUID *)propvarIn);
          PropVariantClear((PROPVARIANT *)&propvar);
          if ( String < 0 )
            goto LABEL_45;
          v18 = 0;
          memset(&propvar, 0, sizeof(propvar));
          String = (*(__int64 (__fastcall **)(void *, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 40LL))(
                     ppv,
                     qword_18007A7E8,
                     &propvar);
          if ( String >= 0 )
          {
            String = QueryInterfacePropVariant(&propvar, v10, &v18);
            PropVariantClear((PROPVARIANT *)&propvar);
            if ( String >= 0 )
            {
              pulRet = 0;
              memset(&propvar, 0, sizeof(propvar));
              String = (*(__int64 (__fastcall **)(void *, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 40LL))(
                         ppv,
                         qword_18007A7B8,
                         &propvar);
              if ( String >= 0 )
              {
                if ( propvar.vt )
                  String = PropVariantToUInt32((const PROPVARIANT *const)&propvar, &pulRet);
                else
                  String = -2147023728;
                PropVariantClear((PROPVARIANT *)&propvar);
              }
              if ( String == -2147023728 )
              {
                pulRet = 0;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids);
                }
                goto LABEL_42;
              }
              if ( String >= 0 )
LABEL_42:
                String = CThemeManager2::_InstallRoamingThemePack(
                           this,
                           (const unsigned __int16 *)v16,
                           (__int64)propvarIn,
                           pulRet,
                           a3,
                           (__int64)v18);
            }
          }
          ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v18);
LABEL_45:
          CoTaskMemFree(v16);
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids,
      (unsigned int)String);
  ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&ppv);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180054390  mov     [rsp-8+arg_18], rbx
0x180054395  push    rbp
0x180054396  push    rsi
0x180054397  push    rdi
0x180054398  push    r13
0x18005439a  push    r14
0x18005439c  lea     rbp, [rsp-37h]
0x1800543a1  sub     rsp, 90h
0x1800543a8  mov     rax, cs:__security_cookie
0x1800543af  xor     rax, rsp
0x1800543b2  mov     [rbp+57h+var_28], rax
0x1800543b6  mov     esi, r8d
0x1800543b9  mov     rdi, rdx
0x1800543bc  mov     r14, rcx
0x1800543bf  lea     r13, WPP_GLOBAL_Control
0x1800543c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543cd  cmp     rcx, r13
0x1800543d0  jz      short loc_1800543F0
0x1800543d2  test    byte ptr [rcx+1Ch], 8
0x1800543d6  jz      short loc_1800543F0
0x1800543d8  mov     edx, 14h
0x1800543dd  mov     r9d, r8d
0x1800543e0  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x1800543e7  mov     rcx, [rcx+10h]
0x1800543eb  call    WPP_SF_d
0x1800543f0  lea     rcx, [rbp+57h+ppv]
0x1800543f4  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x1800543f9  nop
0x1800543fa  lea     rdx, [rbp+57h+ppv]; ppv
0x1800543fe  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180054405  call    cs:__imp_PSCreateMemoryPropertyStore
0x18005440b  mov     ebx, eax
0x18005440d  test    eax, eax
0x18005440f  js      loc_180054760
0x180054415  mov     rcx, [rbp+57h+ppv]
0x180054419  mov     [rbp+57h+pv], 0
0x180054421  mov     rax, [rcx]
0x180054424  lea     r8, [rbp+57h+pv]
0x180054428  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18005442f  mov     rax, [rax]
0x180054432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054437  mov     ebx, eax
0x180054439  test    eax, eax
0x18005443b  js      loc_180054760
0x180054441  mov     rcx, [rbp+57h+pv]
0x180054445  mov     rax, [rcx]
0x180054448  mov     rdx, rdi
0x18005444b  mov     rax, [rax+28h]
0x18005444f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054454  mov     ebx, eax
0x180054456  mov     rcx, [rbp+57h+pv]
0x18005445a  mov     rax, [rcx]
0x18005445d  mov     rax, [rax+10h]
0x180054461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054466  test    ebx, ebx
0x180054468  js      loc_180054760
0x18005446e  mov     [rbp+57h+var_68], 0
0x180054476  lea     r8, [rbp+57h+var_68]
0x18005447a  mov     rcx, [rbp+57h+ppv]
0x18005447e  call    IPropertyStore_GetString
0x180054483  mov     ebx, eax
0x180054485  test    eax, eax
0x180054487  js      loc_180054760
0x18005448d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054494  cmp     rcx, r13
0x180054497  jz      short loc_1800544B8
0x180054499  test    byte ptr [rcx+1Ch], 8
0x18005449d  jz      short loc_1800544B8
0x18005449f  mov     edx, 15h
0x1800544a4  mov     r9, [rbp+57h+var_68]
0x1800544a8  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x1800544af  mov     rcx, [rcx+10h]
0x1800544b3  call    WPP_SF_S
0x1800544b8  mov     rcx, [rbp+57h+ppv]
0x1800544bc  mov     [rbp+57h+plRet], 0
0x1800544c3  xorps   xmm0, xmm0
0x1800544c6  xor     eax, eax
0x1800544c8  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x1800544cc  mov     [rbp+57h+var_30], rax
0x1800544d0  mov     rax, [rcx]
0x1800544d3  lea     r8, [rbp+57h+propvarIn]
0x1800544d7  lea     rdx, qword_18007A7D0
0x1800544de  mov     rax, [rax+28h]
0x1800544e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544e7  mov     ebx, eax
0x1800544e9  test    eax, eax
0x1800544eb  js      loc_180054756
0x1800544f1  xor     eax, eax
0x1800544f3  mov     edi, 80070490h
0x1800544f8  cmp     ax, word ptr [rbp+57h+propvarIn]
0x1800544fc  jz      short loc_180054510
0x1800544fe  lea     rdx, [rbp+57h+plRet]; plRet
0x180054502  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x180054506  call    cs:__imp_PropVariantToInt32
0x18005450c  mov     ebx, eax
0x18005450e  jmp     short loc_180054512
0x180054510  mov     ebx, edi
0x180054512  lea     rcx, [rbp+57h+propvarIn]; pvar
0x180054516  call    cs:__imp_PropVariantClear
0x18005451c  test    ebx, ebx
0x18005451e  js      loc_180054756
0x180054524  mov     rcx, cs:WPP_GLOBAL_Control
0x18005452b  cmp     rcx, r13
0x18005452e  jz      short loc_18005454F
0x180054530  test    byte ptr [rcx+1Ch], 8
0x180054534  jz      short loc_18005454F
0x180054536  mov     edx, 16h
0x18005453b  mov     r9d, [rbp+57h+plRet]
0x18005453f  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x180054546  mov     rcx, [rcx+10h]
0x18005454a  call    WPP_SF_d
0x18005454f  mov     edx, [rbp+57h+plRet]
0x180054552  cmp     edx, 0FFFFFFFFh
0x180054555  jz      loc_180054751
0x18005455b  test    edx, edx
0x18005455d  jz      short loc_1800545DD
0x18005455f  cmp     edx, 1
0x180054562  jz      short loc_180054576
0x180054564  cmp     edx, 2
0x180054567  jz      loc_180054751
0x18005456d  cmp     edx, 3
0x180054570  jnz     loc_180054751
0x180054576  mov     [rbp+57h+pv], 0
0x18005457e  lea     r9, [rbp+57h+pv]
0x180054582  mov     r8, [rbp+57h+var_68]
0x180054586  call    ?_GetInboxThemePath@CThemeManager2@@AEAAJW4tagTHEMECAT@@PEBGPEAPEAG@Z; CThemeManager2::_GetInboxThemePath(tagTHEMECAT,ushort const *,ushort * *)
0x18005458b  mov     ebx, eax
0x18005458d  test    eax, eax
0x18005458f  js      loc_180054756
0x180054595  mov     rcx, cs:WPP_GLOBAL_Control
0x18005459c  cmp     rcx, r13
0x18005459f  jz      short loc_1800545C0
0x1800545a1  test    byte ptr [rcx+1Ch], 8
0x1800545a5  jz      short loc_1800545C0
0x1800545a7  mov     edx, 17h
0x1800545ac  mov     r9, [rbp+57h+pv]
0x1800545b0  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x1800545b7  mov     rcx, [rcx+10h]
0x1800545bb  call    WPP_SF_S
0x1800545c0  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x1800545c4  mov     rcx, r14; this
0x1800545c7  call    ?_OpenInboxTheme@CThemeManager2@@AEAAJHPEBG@Z; CThemeManager2::_OpenInboxTheme(int,ushort const *)
0x1800545cc  mov     ebx, eax
0x1800545ce  mov     rcx, [rbp+57h+pv]; pv
0x1800545d2  call    cs:__imp_CoTaskMemFree
0x1800545d8  jmp     loc_180054756
0x1800545dd  xorps   xmm0, xmm0
0x1800545e0  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x1800545e4  mov     rcx, [rbp+57h+ppv]
0x1800545e8  xor     eax, eax
0x1800545ea  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x1800545ee  mov     [rbp+57h+var_50], rax
0x1800545f2  mov     rax, [rcx]
0x1800545f5  lea     r8, [rbp+57h+propvar]
0x1800545f9  lea     rdx, qword_18007A818
0x180054600  mov     rax, [rax+28h]
0x180054604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054609  mov     ebx, eax
0x18005460b  test    eax, eax
0x18005460d  js      loc_180054756
0x180054613  lea     rdx, [rbp+57h+propvarIn]; pguid
0x180054617  lea     rcx, [rbp+57h+propvar]; propvar
0x18005461b  call    cs:__imp_PropVariantToGUID
0x180054621  mov     ebx, eax
0x180054623  lea     rcx, [rbp+57h+propvar]; pvar
0x180054627  call    cs:__imp_PropVariantClear
0x18005462d  test    ebx, ebx
0x18005462f  js      loc_180054756
0x180054635  mov     rcx, [rbp+57h+ppv]
0x180054639  mov     [rbp+57h+var_48], 0
0x180054641  xorps   xmm0, xmm0
0x180054644  xor     eax, eax
0x180054646  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x18005464a  mov     [rbp+57h+var_50], rax
0x18005464e  mov     rax, [rcx]
0x180054651  lea     r8, [rbp+57h+propvar]
0x180054655  lea     rdx, qword_18007A7E8
0x18005465c  mov     rax, [rax+28h]
0x180054660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054665  mov     ebx, eax
0x180054667  test    eax, eax
0x180054669  js      loc_180054746
0x18005466f  lea     r8, [rbp+57h+var_48]; void **
0x180054673  lea     rcx, [rbp+57h+propvar]; struct tagPROPVARIANT *
0x180054677  call    ?QueryInterfacePropVariant@@YAJAEBUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; QueryInterfacePropVariant(tagPROPVARIANT const &,_GUID const &,void * *)
0x18005467c  mov     ebx, eax
0x18005467e  lea     rcx, [rbp+57h+propvar]; pvar
0x180054682  call    cs:__imp_PropVariantClear
0x180054688  test    ebx, ebx
0x18005468a  js      loc_180054746
0x180054690  mov     rcx, [rbp+57h+ppv]
0x180054694  mov     [rbp+57h+pulRet], 0
0x18005469b  xorps   xmm0, xmm0
0x18005469e  xor     eax, eax
0x1800546a0  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x1800546a4  mov     [rbp+57h+var_50], rax
0x1800546a8  mov     rax, [rcx]
0x1800546ab  lea     r8, [rbp+57h+propvar]
0x1800546af  lea     rdx, qword_18007A7B8
0x1800546b6  mov     rax, [rax+28h]
0x1800546ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546bf  mov     ebx, eax
0x1800546c1  test    eax, eax
0x1800546c3  js      short loc_1800546EB
0x1800546c5  xor     eax, eax
0x1800546c7  cmp     ax, word ptr [rbp+57h+propvar]
0x1800546cb  jz      short loc_1800546DF
0x1800546cd  lea     rdx, [rbp+57h+pulRet]; pulRet
0x1800546d1  lea     rcx, [rbp+57h+propvar]; propvarIn
0x1800546d5  call    cs:__imp_PropVariantToUInt32
0x1800546db  mov     ebx, eax
0x1800546dd  jmp     short loc_1800546E1
0x1800546df  mov     ebx, edi
0x1800546e1  lea     rcx, [rbp+57h+propvar]; pvar
0x1800546e5  call    cs:__imp_PropVariantClear
0x1800546eb  cmp     ebx, edi
0x1800546ed  jnz     short loc_18005471F
0x1800546ef  mov     [rbp+57h+pulRet], 0
0x1800546f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800546fd  cmp     rcx, r13
0x180054700  jz      short loc_180054723
0x180054702  test    byte ptr [rcx+1Ch], 8
0x180054706  jz      short loc_180054723
0x180054708  mov     edx, 18h
0x18005470d  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x180054714  mov     rcx, [rcx+10h]
0x180054718  call    WPP_SF_
0x18005471d  jmp     short loc_180054723
0x18005471f  test    ebx, ebx
0x180054721  js      short loc_180054746
0x180054723  mov     rax, [rbp+57h+var_48]
0x180054727  mov     [rsp+0B0h+var_88], rax
0x18005472c  mov     [rsp+0B0h+var_90], esi
0x180054730  mov     r9d, [rbp+57h+pulRet]
0x180054734  lea     r8, [rbp+57h+propvarIn]
0x180054738  mov     rdx, [rbp+57h+var_68]
0x18005473c  mov     rcx, r14
0x18005473f  call    ?_InstallRoamingThemePack@CThemeManager2@@AEAAJPEBGAEBU_GUID@@W4THEMETYPE@@HPEAUIStream@@@Z; CThemeManager2::_InstallRoamingThemePack(ushort const *,_GUID const &,THEMETYPE,int,IStream *)
0x180054744  mov     ebx, eax
0x180054746  lea     rcx, [rbp+57h+var_48]
0x18005474a  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x18005474f  jmp     short loc_180054756
0x180054751  mov     ebx, 80004005h
0x180054756  mov     rcx, [rbp+57h+var_68]; pv
0x18005475a  call    cs:__imp_CoTaskMemFree
0x180054760  mov     rcx, cs:WPP_GLOBAL_Control
0x180054767  cmp     rcx, r13
0x18005476a  jz      short loc_18005478B
0x18005476c  test    byte ptr [rcx+1Ch], 8
0x180054770  jz      short loc_18005478B
0x180054772  mov     edx, 19h
0x180054777  mov     r9d, ebx
0x18005477a  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x180054781  mov     rcx, [rcx+10h]
0x180054785  call    WPP_SF_d
0x18005478a  nop
0x18005478b  lea     rcx, [rbp+57h+ppv]
0x18005478f  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180054794  mov     eax, ebx
0x180054796  mov     rcx, [rbp+57h+var_28]
0x18005479a  xor     rcx, rsp; StackCookie
0x18005479d  call    __security_check_cookie
0x1800547a2  mov     rbx, [rsp+0B0h+arg_18]
0x1800547aa  add     rsp, 90h
0x1800547b1  pop     r14
0x1800547b3  pop     r13
0x1800547b5  pop     rdi
0x1800547b6  pop     rsi
0x1800547b7  pop     rbp
0x1800547b8  retn
```
