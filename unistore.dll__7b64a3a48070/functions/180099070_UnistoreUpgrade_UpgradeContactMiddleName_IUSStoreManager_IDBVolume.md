# UnistoreUpgrade::UpgradeContactMiddleName(IUSStoreManager *,IDBVolume *)

- ea: `0x180099070`
- end: `0x1800995b8`
- name: `?UpgradeContactMiddleName@UnistoreUpgrade@@YAJPEAUIUSStoreManager@@PEAVIDBVolume@@@Z`
- size: `1352`
- prototype: `__int64 __fastcall(UnistoreUpgrade *__hidden this, struct IUSStoreManager *, struct IDBVolume *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18001bd48`
- `0x18001c2e0`
- `0x18001e2f4`
- `0x180034664`
- `0x180035d40`
- `0x1800576c0`
- `0x180059828`
- `0x180099070`
- `0x1800c4978`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009947e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009947e`

## string_xrefs

- `0x180099435`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800994ac`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800994c5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800994e1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x1800994fd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x180099519`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009953d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`
- `0x18009957a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\unistoreupgrade.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreUpgrade::UpgradeContactMiddleName(
        UnistoreUpgrade *this,
        struct IUSStoreManager *a2,
        struct IDBVolume *a3)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, _DWORD *); // rbx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int started; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+68h] [rbp-98h]
  _DWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[4]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v32[4]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v33[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v34[5]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v35[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v36; // [rsp+108h] [rbp+8h]
  __int64 v37; // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+118h] [rbp+18h]
  __int64 v39; // [rsp+120h] [rbp+20h]
  __int64 v40; // [rsp+128h] [rbp+28h]
  __int64 v41; // [rsp+150h] [rbp+50h] BYREF
  int v42; // [rsp+158h] [rbp+58h]
  _DWORD v43[8]; // [rsp+160h] [rbp+60h] BYREF
  int v44; // [rsp+180h] [rbp+80h] BYREF
  __int64 v45; // [rsp+188h] [rbp+88h]
  int v46; // [rsp+198h] [rbp+98h]
  __int64 v47; // [rsp+1A0h] [rbp+A0h]
  int v48; // [rsp+1B0h] [rbp+B0h]
  __int64 v49; // [rsp+1B8h] [rbp+B8h]
  int v50; // [rsp+1C8h] [rbp+C8h]
  __int64 v51; // [rsp+1D0h] [rbp+D0h]

  v3 = *(_QWORD *)this;
  v26 = 0;
  v5 = (*(__int64 (__fastcall **)(UnistoreUpgrade *, __int64, _QWORD))(v3 + 136))(this, 1, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 120LL))(v26);
    while ( !v6 )
    {
      v24 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 40LL))(v26, &v24);
      v6 = v10;
      if ( v10 < 0 )
      {
        v22 = 1241;
        goto LABEL_49;
      }
      v41 = 0;
      v42 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL))(v24, &v41);
      v6 = v10;
      if ( v10 < 0 )
      {
        v22 = 1244;
LABEL_49:
        Log_UnistoreHREvent_0(
          (unsigned int)v10,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v22);
        goto LABEL_50;
      }
      v11 = v24;
      v43[0] = 8454175;
      v43[1] = 8519711;
      v43[2] = 8585247;
      v43[3] = 8650783;
      v43[4] = 8716319;
      hMem = 0;
      v12 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v24 + 48LL);
      tlx::replace<_USPROPVAL,&void _LocalFreer<_USPROPVAL>(_USPROPVAL *)>(&hMem);
      v13 = v12(v11, 5, v43);
      v6 = v13;
      if ( v13 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v13,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          1248);
        goto LABEL_35;
      }
      memset_0(v35, 0, 0x48u);
      if ( (*((_WORD *)hMem + 3) & 0x300) == 0 )
        v36 = *((_QWORD *)hMem + 1);
      if ( (*((_WORD *)hMem + 15) & 0x300) == 0 )
        v37 = *((_QWORD *)hMem + 4);
      if ( (*((_WORD *)hMem + 27) & 0x300) == 0 )
        v38 = *((_QWORD *)hMem + 7);
      if ( (*((_WORD *)hMem + 39) & 0x300) == 0 )
        v39 = *((_QWORD *)hMem + 10);
      if ( (*((_WORD *)hMem + 51) & 0x300) == 0 )
        v40 = *((_QWORD *)hMem + 13);
      memset_0(&v44, 0, 0x60u);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v31);
      v14 = ConstructNameFromTemplate(v35, 2, v31);
      v6 = v14;
      if ( v14 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v14,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          1275);
LABEL_34:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v31);
LABEL_35:
        if ( hMem )
          LocalFree(hMem);
LABEL_50:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
        goto LABEL_55;
      }
      v45 = v31[0];
      v44 = 1224736799;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v32);
      v15 = ConstructNameFromTemplate(v35, 4, v32);
      v6 = v15;
      if ( v15 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v15,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          1280);
        goto LABEL_33;
      }
      v47 = v32[0];
      v46 = 1224802335;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v33);
      v16 = ConstructNameFromTemplate(v35, 6, v33);
      v6 = v16;
      if ( v16 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v16,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          1285);
        goto LABEL_32;
      }
      v49 = v33[0];
      v48 = 1224867871;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v34);
      v17 = ConstructNameFromTemplate(v35, 8, v34);
      v6 = v17;
      if ( v17 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v17,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          1290);
        goto LABEL_31;
      }
      v51 = v34[0];
      v30[0] = v41;
      v50 = 1224933407;
      v30[1] = 2147483643;
      ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v28, a2);
      v29 = 0;
      started = DBAutoTopLevelTransact::StartTransaction(
                  (DBAutoTopLevelTransact *)v28,
                  3u,
                  2u,
                  (const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *)v30);
      v6 = started;
      if ( started < 0 )
      {
        v20 = 1302;
LABEL_38:
        v19 = 1;
        goto LABEL_39;
      }
      started = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v24 + 80LL))(v24, 4, &v44);
      v6 = started;
      v19 = 1;
      if ( started < 0 )
      {
        v20 = 1304;
LABEL_39:
        v21 = (unsigned int)started;
        goto LABEL_30;
      }
      v27 = 0;
      started = DBAutoTopLevelTransact::EndTransaction((DBAutoTopLevelTransact *)v28, 1, &v27);
      v6 = started;
      if ( started < 0 )
      {
        v20 = 1307;
        goto LABEL_38;
      }
      if ( !v27 )
      {
        v6 = -2147418113;
        v20 = 1308;
        v21 = 2147549183LL;
        v19 = 0;
LABEL_30:
        Log_UnistoreHREvent_0(
          v21,
          v19,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
          v20);
        DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v28);
LABEL_31:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
LABEL_32:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v33);
LABEL_33:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
        goto LABEL_34;
      }
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 96LL))(v26);
      DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)v28);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v33);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v31);
      if ( hMem )
        LocalFree(hMem);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
    }
    if ( v6 == -2147024871 )
    {
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
      return 0;
    }
    v7 = 1312;
    v8 = 0;
    v9 = v6;
  }
  else
  {
    v7 = 1235;
    v8 = 1;
    v9 = (unsigned int)v5;
  }
  Log_UnistoreHREvent_0(
    v9,
    v8,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\unistoreupgrade.cpp",
    v7);
LABEL_55:
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
  return v6;
}

```

## disassembly

```asm
0x180099070  mov     [rsp-8+arg_10], rbx
0x180099075  push    rbp
0x180099076  push    rsi
0x180099077  push    rdi
0x180099078  push    r12
0x18009907a  push    r15
0x18009907c  lea     rbp, [rsp-0F0h]
0x180099084  sub     rsp, 1F0h
0x18009908b  mov     rax, cs:__security_cookie
0x180099092  xor     rax, rsp
0x180099095  mov     [rbp+110h+var_30], rax
0x18009909c  mov     rax, [rcx]
0x18009909f  mov     rsi, rdx
0x1800990a2  lea     rdx, [rsp+210h+var_1C0]
0x1800990a7  mov     [rsp+210h+var_1C0], 0
0x1800990b0  mov     [rsp+210h+var_1E0], rdx
0x1800990b5  xor     r9d, r9d
0x1800990b8  mov     [rsp+210h+var_1E8], 0
0x1800990c1  xor     r8d, r8d
0x1800990c4  mov     rax, [rax+88h]
0x1800990cb  mov     [rsp+210h+var_1F0], 0
0x1800990d4  lea     r15d, [r9+1]
0x1800990d8  mov     edx, r15d
0x1800990db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800990e0  mov     ebx, eax
0x1800990e2  test    eax, eax
0x1800990e4  jns     short loc_1800990F6
0x1800990e6  mov     r9d, 4D3h
0x1800990ec  mov     edx, r15d
0x1800990ef  mov     ecx, eax
0x1800990f1  jmp     loc_18009957A
0x1800990f6  mov     rcx, [rsp+210h+var_1C0]
0x1800990fb  mov     rax, [rcx]
0x1800990fe  mov     rax, [rax+78h]
0x180099102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099107  mov     ebx, eax
0x180099109  mov     r12d, 300h
0x18009910f  test    ebx, ebx
0x180099111  jnz     loc_18009955A
0x180099117  mov     rcx, [rsp+210h+var_1C0]
0x18009911c  lea     rdx, [rsp+210h+var_1D0]
0x180099121  mov     [rsp+210h+var_1D0], 0
0x18009912a  mov     rax, [rcx]
0x18009912d  mov     rax, [rax+28h]
0x180099131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099136  mov     ebx, eax
0x180099138  test    eax, eax
0x18009913a  js      loc_180099537
0x180099140  mov     rcx, [rsp+210h+var_1D0]
0x180099145  lea     rdx, [rbp+110h+var_C0]
0x180099149  xor     eax, eax
0x18009914b  mov     [rbp+110h+var_C0], rax
0x18009914f  mov     [rbp+110h+var_B8], eax
0x180099152  mov     rax, [rcx]
0x180099155  mov     rax, [rax+18h]
0x180099159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009915e  mov     ebx, eax
0x180099160  test    eax, eax
0x180099162  js      loc_18009952F
0x180099168  mov     rdi, [rsp+210h+var_1D0]
0x18009916d  lea     rcx, [rsp+210h+hMem]
0x180099172  mov     [rbp+110h+var_B0], 81001Fh
0x180099179  mov     [rbp+110h+var_AC], 82001Fh
0x180099180  mov     [rbp+110h+var_A8], 83001Fh
0x180099187  mov     [rbp+110h+var_A4], 84001Fh
0x18009918e  mov     [rbp+110h+var_A0], 85001Fh
0x180099195  mov     [rsp+210h+hMem], 0
0x18009919e  mov     rax, [rdi]
0x1800991a1  mov     rbx, [rax+30h]
0x1800991a5  call    ??$replace@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USPROPVAL@@AEAV?$auto_ptr@U_USPROPVAL@@$1??$_LocalFreer@U_USPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)>(tlx::auto_ptr<_USPROPVAL,&_LocalFreer<_USPROPVAL>(_USPROPVAL *)> &)
0x1800991aa  xor     r9d, r9d
0x1800991ad  mov     [rsp+210h+var_1F0], rax
0x1800991b2  lea     r8, [rbp+110h+var_B0]
0x1800991b6  mov     rcx, rdi
0x1800991b9  mov     rax, rbx
0x1800991bc  lea     edx, [r9+5]
0x1800991c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800991c5  mov     ebx, eax
0x1800991c7  test    eax, eax
0x1800991c9  js      loc_180099513
0x1800991cf  xor     edx, edx; Val
0x1800991d1  lea     rcx, [rbp+110h+var_110]; void *
0x1800991d5  lea     r8d, [rdx+48h]; Size
0x1800991d9  call    memset_0
0x1800991de  mov     rax, [rsp+210h+hMem]
0x1800991e3  test    [rax+6], r12w
0x1800991e8  jnz     short loc_1800991F2
0x1800991ea  mov     rcx, [rax+8]
0x1800991ee  mov     [rbp+110h+var_108], rcx
0x1800991f2  test    [rax+1Eh], r12w
0x1800991f7  jnz     short loc_180099201
0x1800991f9  mov     rcx, [rax+20h]
0x1800991fd  mov     [rbp+110h+var_100], rcx
0x180099201  test    [rax+36h], r12w
0x180099206  jnz     short loc_180099210
0x180099208  mov     rcx, [rax+38h]
0x18009920c  mov     [rbp+110h+var_F8], rcx
0x180099210  test    [rax+4Eh], r12w
0x180099215  jnz     short loc_18009921F
0x180099217  mov     rcx, [rax+50h]
0x18009921b  mov     [rbp+110h+var_F0], rcx
0x18009921f  test    [rax+66h], r12w
0x180099224  jnz     short loc_18009922E
0x180099226  mov     rcx, [rax+68h]
0x18009922a  mov     [rbp+110h+var_E8], rcx
0x18009922e  xor     edx, edx; Val
0x180099230  lea     rcx, [rbp+110h+var_90]; void *
0x180099237  lea     r8d, [rdx+60h]; Size
0x18009923b  call    memset_0
0x180099240  lea     rcx, [rsp+210h+var_198]
0x180099245  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18009924a  mov     edx, 2
0x18009924f  lea     r8, [rsp+210h+var_198]
0x180099254  lea     rcx, [rbp+110h+var_110]
0x180099258  call    ?ConstructNameFromTemplate@@YAJAEBUNameProperties@@W4TEMPLATE_PROP@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z; ConstructNameFromTemplate(NameProperties const &,TEMPLATE_PROP,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)
0x18009925d  mov     ebx, eax
0x18009925f  test    eax, eax
0x180099261  js      loc_1800994F7
0x180099267  mov     rax, [rsp+210h+var_198]
0x18009926c  lea     rcx, [rbp+110h+var_178]
0x180099270  mov     [rbp+110h+var_88], rax
0x180099277  mov     [rbp+110h+var_90], 4900001Fh
0x180099281  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180099286  mov     edx, 4
0x18009928b  lea     r8, [rbp+110h+var_178]
0x18009928f  lea     rcx, [rbp+110h+var_110]
0x180099293  call    ?ConstructNameFromTemplate@@YAJAEBUNameProperties@@W4TEMPLATE_PROP@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z; ConstructNameFromTemplate(NameProperties const &,TEMPLATE_PROP,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)
0x180099298  mov     ebx, eax
0x18009929a  test    eax, eax
0x18009929c  js      loc_1800994DB
0x1800992a2  mov     rax, [rbp+110h+var_178]
0x1800992a6  lea     rcx, [rbp+110h+var_158]
0x1800992aa  mov     [rbp+110h+var_70], rax
0x1800992b1  mov     [rbp+110h+var_78], 4901001Fh
0x1800992bb  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800992c0  mov     edx, 6
0x1800992c5  lea     r8, [rbp+110h+var_158]
0x1800992c9  lea     rcx, [rbp+110h+var_110]
0x1800992cd  call    ?ConstructNameFromTemplate@@YAJAEBUNameProperties@@W4TEMPLATE_PROP@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z; ConstructNameFromTemplate(NameProperties const &,TEMPLATE_PROP,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)
0x1800992d2  mov     ebx, eax
0x1800992d4  test    eax, eax
0x1800992d6  js      loc_1800994BF
0x1800992dc  mov     rax, [rbp+110h+var_158]
0x1800992e0  lea     rcx, [rbp+110h+var_138]
0x1800992e4  mov     [rbp+110h+var_58], rax
0x1800992eb  mov     [rbp+110h+var_60], 4902001Fh
0x1800992f5  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800992fa  mov     edx, 8
0x1800992ff  lea     r8, [rbp+110h+var_138]
0x180099303  lea     rcx, [rbp+110h+var_110]
0x180099307  call    ?ConstructNameFromTemplate@@YAJAEBUNameProperties@@W4TEMPLATE_PROP@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z; ConstructNameFromTemplate(NameProperties const &,TEMPLATE_PROP,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)
0x18009930c  mov     ebx, eax
0x18009930e  test    eax, eax
0x180099310  js      loc_1800994A6
0x180099316  mov     rax, [rbp+110h+var_138]
0x18009931a  lea     rcx, [rsp+210h+var_1B0]
0x18009931f  mov     [rbp+110h+var_40], rax
0x180099326  mov     rdx, rsi
0x180099329  mov     eax, dword ptr [rbp+110h+var_C0]
0x18009932c  mov     [rsp+210h+var_1A0], eax
0x180099330  mov     [rbp+110h+var_48], 4903001Fh
0x18009933a  mov     [rsp+210h+var_19C], 7FFFFFFBh
0x180099342  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x180099347  mov     edx, 3; unsigned int
0x18009934c  mov     [rsp+210h+var_1A8], 0
0x180099354  lea     r9, [rsp+210h+var_1A0]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x180099359  lea     rcx, [rsp+210h+var_1B0]; this
0x18009935e  lea     r8d, [rdx-1]; unsigned int
0x180099362  call    ?StartTransaction@DBAutoTopLevelTransact@@QEAAJKKPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z; DBAutoTopLevelTransact::StartTransaction(ulong,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *)
0x180099367  mov     ebx, eax
0x180099369  test    eax, eax
0x18009936b  js      loc_18009949E
0x180099371  mov     rcx, [rsp+210h+var_1D0]
0x180099376  lea     r8, [rbp+110h+var_90]
0x18009937d  xor     r9d, r9d
0x180099380  mov     rax, [rcx]
0x180099383  lea     edx, [r9+4]
0x180099387  mov     rax, [rax+50h]
0x18009938b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099390  mov     ebx, eax
0x180099392  mov     edx, r15d; int
0x180099395  test    eax, eax
0x180099397  js      loc_180099496
0x18009939d  lea     r8, [rsp+210h+var_1B8]; int *
0x1800993a2  mov     [rsp+210h+var_1B8], 0
0x1800993aa  lea     rcx, [rsp+210h+var_1B0]; this
0x1800993af  call    ?EndTransaction@DBAutoTopLevelTransact@@QEAAJHPEAH@Z; DBAutoTopLevelTransact::EndTransaction(int,int *)
0x1800993b4  mov     ebx, eax
0x1800993b6  test    eax, eax
0x1800993b8  js      loc_180099489
0x1800993be  cmp     [rsp+210h+var_1B8], 0
0x1800993c3  jz      short loc_180099426
0x1800993c5  mov     rcx, [rsp+210h+var_1C0]
0x1800993ca  mov     rax, [rcx]
0x1800993cd  mov     rax, [rax+60h]
0x1800993d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800993d6  lea     rcx, [rsp+210h+var_1B0]; this
0x1800993db  mov     ebx, eax
0x1800993dd  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x1800993e2  lea     rcx, [rbp+110h+var_138]
0x1800993e6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800993eb  lea     rcx, [rbp+110h+var_158]
0x1800993ef  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800993f4  lea     rcx, [rbp+110h+var_178]
0x1800993f8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800993fd  lea     rcx, [rsp+210h+var_198]
0x180099402  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180099407  mov     rcx, [rsp+210h+hMem]; hMem
0x18009940c  test    rcx, rcx
0x18009940f  jz      short loc_180099417
0x180099411  call    cs:__imp_LocalFree
0x180099417  lea     rcx, [rsp+210h+var_1D0]; void *
0x18009941c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180099421  jmp     loc_18009910F
0x180099426  mov     ebx, 8000FFFFh
0x18009942b  mov     r9d, 51Ch
0x180099431  mov     ecx, ebx
0x180099433  xor     edx, edx
0x180099435  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18009943c  call    Log_UnistoreHREvent_0
0x180099441  lea     rcx, [rsp+210h+var_1B0]; this
0x180099446  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18009944b  lea     rcx, [rbp+110h+var_138]
0x18009944f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180099454  lea     rcx, [rbp+110h+var_158]
0x180099458  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009945d  lea     rcx, [rbp+110h+var_178]
0x180099461  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180099466  lea     rcx, [rsp+210h+var_198]
0x18009946b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180099470  mov     rcx, [rsp+210h+hMem]; hMem
0x180099475  test    rcx, rcx
0x180099478  jz      loc_18009954E
0x18009947e  call    cs:__imp_LocalFree
0x180099484  jmp     loc_18009954E
0x180099489  mov     r9d, 51Bh
0x18009948f  mov     edx, r15d
0x180099492  mov     ecx, eax
0x180099494  jmp     short loc_180099435
0x180099496  mov     r9d, 518h
0x18009949c  jmp     short loc_180099492
0x18009949e  mov     r9d, 516h
0x1800994a4  jmp     short loc_18009948F
0x1800994a6  mov     r9d, 50Ah
0x1800994ac  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800994b3  mov     edx, r15d
0x1800994b6  mov     ecx, eax
0x1800994b8  call    Log_UnistoreHREvent_0
0x1800994bd  jmp     short loc_18009944B
0x1800994bf  mov     r9d, 505h
0x1800994c5  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800994cc  mov     edx, r15d
0x1800994cf  mov     ecx, eax
0x1800994d1  call    Log_UnistoreHREvent_0
0x1800994d6  jmp     loc_180099454
0x1800994db  mov     r9d, 500h
0x1800994e1  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800994e8  mov     edx, r15d
0x1800994eb  mov     ecx, eax
0x1800994ed  call    Log_UnistoreHREvent_0
0x1800994f2  jmp     loc_18009945D
0x1800994f7  mov     r9d, 4FBh
0x1800994fd  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180099504  mov     edx, r15d
0x180099507  mov     ecx, eax
0x180099509  call    Log_UnistoreHREvent_0
0x18009950e  jmp     loc_180099466
0x180099513  mov     r9d, 4E0h
0x180099519  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180099520  mov     edx, r15d
0x180099523  mov     ecx, eax
0x180099525  call    Log_UnistoreHREvent_0
0x18009952a  jmp     loc_180099470
0x18009952f  mov     r9d, 4DCh
0x180099535  jmp     short loc_18009953D
0x180099537  mov     r9d, 4D9h
0x18009953d  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180099544  mov     edx, r15d
0x180099547  mov     ecx, eax
0x180099549  call    Log_UnistoreHREvent_0
0x18009954e  lea     rcx, [rsp+210h+var_1D0]; void *
0x180099553  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180099558  jmp     short loc_180099586
0x18009955a  cmp     ebx, 80070019h
0x180099560  jnz     short loc_180099570
0x180099562  lea     rcx, [rsp+210h+var_1C0]; void *
0x180099567  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18009956c  xor     eax, eax
0x18009956e  jmp     short loc_180099592
0x180099570  mov     r9d, 520h
0x180099576  xor     edx, edx
0x180099578  mov     ecx, ebx
0x18009957a  lea     r8, aOnecoreuapBase_41; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180099581  call    Log_UnistoreHREvent_0
0x180099586  lea     rcx, [rsp+210h+var_1C0]; void *
0x18009958b  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180099590  mov     eax, ebx
0x180099592  mov     rcx, [rbp+110h+var_30]
0x180099599  xor     rcx, rsp; StackCookie
0x18009959c  call    __security_check_cookie
  ... truncated ...
```
