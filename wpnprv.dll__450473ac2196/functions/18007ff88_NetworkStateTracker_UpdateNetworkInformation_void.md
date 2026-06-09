# NetworkStateTracker::UpdateNetworkInformation(void)

- ea: `0x18007ff88`
- end: `0x180080344`
- name: `?UpdateNetworkInformation@NetworkStateTracker@@AEAAJXZ`
- size: `956`
- prototype: `__int64 __fastcall(_Smtx_t *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007fa6c`
- `0x18007fd50`

## callees

- `0x180008a5c`
- `0x18000ba54`
- `0x18000fe0c`
- `0x180013294`
- `0x180039a7c`
- `0x180045140`
- `0x18007f6f4`
- `0x18007fca8`
- `0x18007fe84`
- `0x18007ff88`
- `0x18008036c`
- `0x180096010`

## string_xrefs

- `0x18008001e`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\networkstatetracker.cpp`
- `0x18008006a`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\networkstatetracker.cpp`
- `0x1800800c1`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\networkstatetracker.cpp`
- `0x1800800f7`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\networkstatetracker.cpp`
- `0x18008012f`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\networkstatetracker.cpp`
- `0x180080170`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\networkstatetracker.cpp`
- `0x1800801b1`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\networkstatetracker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NetworkStateTracker::UpdateNetworkInformation(_Smtx_t *this)
{
  unsigned int v2; // r14d
  __int64 v3; // rax
  __int64 v4; // rdx
  _Smtx_t v5; // rdi
  __int64 (__fastcall *v6)(_Smtx_t, int *); // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, char **); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  const char *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  char *v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned __int64 v33; // rdx
  wil *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  int v38[2]; // [rsp+20h] [rbp-98h] BYREF
  int v39; // [rsp+28h] [rbp-90h] BYREF
  __int128 v40; // [rsp+30h] [rbp-88h] BYREF
  __int128 v41; // [rsp+40h] [rbp-78h]
  void *v42; // [rsp+50h] [rbp-68h]
  __int64 v43; // [rsp+60h] [rbp-58h] BYREF
  int v44; // [rsp+68h] [rbp-50h] BYREF
  char *v45; // [rsp+70h] [rbp-48h] BYREF
  char v46; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  unsigned int v49; // [rsp+C8h] [rbp+10h] BYREF
  char v50; // [rsp+D0h] [rbp+18h] BYREF
  int v51; // [rsp+D8h] [rbp+20h] BYREF

  try
  {
    v2 = 0;
    v49 = 0;
    v3 = std::map<unsigned int,std::string>::at(this, &v49);
    *(_QWORD *)&v40 = std::_String_val<std::_Simple_types<char>>::_Myptr(v3);
    *((_QWORD *)&v40 + 1) = *(_QWORD *)(v4 + 16);
    *(_QWORD *)&v41 = "None";
    *((_QWORD *)&v41 + 1) = 4;
    v42 = 0;
    *(_QWORD *)v38 = 0;
    v5 = *this;
    v6 = *(__int64 (__fastcall **)(_Smtx_t, int *))(*(_QWORD *)*this + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v38, v4, v7, v8);
    v9 = v6(v5, v38);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\networkstatetracker.cpp",
        (const char *)(unsigned int)v9,
        v38[0]);
    if ( !*(_QWORD *)v38 )
      goto LABEL_33;
    v51 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v38 + 56LL))(*(_QWORD *)v38, &v51);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\networkstatetracker.cpp",
        (const char *)(unsigned int)v10,
        v38[0]);
    v45 = 0;
    v39 = 0;
    v14 = *(_QWORD *)v38;
    v15 = *(__int64 (__fastcall **)(__int64, char **))(**(_QWORD **)v38 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45, v11, v12, v13);
    v16 = v15(v14, &v45);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\networkstatetracker.cpp",
        (const char *)(unsigned int)v16,
        v38[0]);
    v17 = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v45 + 64LL))(v45, &v39);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\networkstatetracker.cpp",
        (const char *)(unsigned int)v17,
        v38[0]);
    v43 = 0;
    v18 = Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile>::As<Windows::Networking::Connectivity::IConnectionProfile2>(
            v38,
            &v43);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\networkstatetracker.cpp",
        (const char *)(unsigned int)v18,
        v38[0]);
    LOBYTE(v49) = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 56LL))(v43, &v49);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\networkstatetracker.cpp",
        (const char *)(unsigned int)v19,
        v38[0]);
    v50 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 48LL))(v43, &v50);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\networkstatetracker.cpp",
        (const char *)(unsigned int)v20,
        v38[0]);
    v44 = v51;
    v21 = std::map<unsigned int,std::string>::at(retaddr, &v44);
    *(_QWORD *)&v40 = std::_String_val<std::_Simple_types<char>>::_Myptr(v21);
    *((_QWORD *)&v40 + 1) = *(_QWORD *)(v22 + 16);
    LODWORD(v42) = v39;
    if ( (_BYTE)v49 )
    {
      *(_QWORD *)&v41 = "WiFi";
LABEL_31:
      *((_QWORD *)&v41 + 1) = 4;
      goto LABEL_32;
    }
    if ( v50 )
    {
      v25 = "Cellular";
    }
    else
    {
      if ( !v39 )
      {
        *(_QWORD *)&v41 = "None";
        goto LABEL_31;
      }
      if ( v39 != 6 && v39 != 26 && v39 != 233 && v39 != 249 && v39 != 266 )
      {
        *(_QWORD *)&v41 = "Other";
        *((_QWORD *)&v41 + 1) = 5;
LABEL_32:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v22, v23, v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45, v26, v27, v28);
LABEL_33:
        v45 = (char *)(this + 7);
        Smtx_lock_exclusive(this + 7);
        v46 = 1;
        v29 = (char *)(this + 2);
        *((_OWORD *)this + 1) = v40;
        *((_OWORD *)this + 2) = v41;
        this[6] = v42;
        std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(&v45);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v38, v30, v31, v32);
        goto LABEL_40;
      }
      v25 = "Ethernet";
    }
    *(_QWORD *)&v41 = v25;
    *((_QWORD *)&v41 + 1) = 8;
    goto LABEL_32;
  }
  catch ( ... )
  {
    v49 = wil::ResultFromCaughtException(v34);
    v29 = (char *)(this + 2);
    v2 = v49;
  }
LABEL_40:
  if ( WpnconTelemetry::IsEnabled((unsigned __int8)v34, v33) )
  {
    v36 = wil::details::static_lazy<WpnconTelemetry>::get(
            v35,
            _lambda_de4d36b645fed666bcd49a481e929f91_::_lambda_invoker_cdecl_);
    v40 = *(_OWORD *)v29;
    v41 = *((_OWORD *)v29 + 1);
    v42 = (void *)*((_QWORD *)v29 + 4);
    WpnconTelemetry::NetworkStateChanged_(v36, v2, &v40);
  }
  return v2;
}

```

## disassembly

```asm
0x18007ff88  mov     rax, rsp
0x18007ff8b  mov     [rax+8], rcx
0x18007ff8f  push    rbx
0x18007ff90  push    rdi
0x18007ff91  push    r12
0x18007ff93  push    r13
0x18007ff95  push    r14
0x18007ff97  push    r15
0x18007ff99  sub     rsp, 88h
0x18007ffa0  mov     r15, rcx
0x18007ffa3  xor     r14d, r14d
0x18007ffa6  mov     [rax+10h], r14d
0x18007ffaa  lea     rdx, [rax+10h]
0x18007ffae  call    ?at@?$map@IV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@QEBAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBI@Z; std::map<uint,std::string>::at(uint const &)
0x18007ffb3  mov     rdx, rax
0x18007ffb6  mov     rcx, rax
0x18007ffb9  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18007ffbe  mov     qword ptr [rsp+0B8h+var_88], rax
0x18007ffc3  mov     rax, [rdx+10h]
0x18007ffc7  mov     qword ptr [rsp+0B8h+var_88+8], rax
0x18007ffcc  lea     r13, aNone; "None"
0x18007ffd3  mov     qword ptr [rsp+0B8h+var_78], r13
0x18007ffd8  lea     r12d, [r14+4]
0x18007ffdc  mov     qword ptr [rsp+0B8h+var_78+8], r12
0x18007ffe1  mov     [rsp+0B8h+var_68], r14
0x18007ffe6  mov     qword ptr [rsp+0B8h+var_98], r14; int
0x18007ffeb  mov     rdi, [r15]
0x18007ffee  mov     rax, [rdi]
0x18007fff1  mov     rbx, [rax+38h]
0x18007fff5  lea     rcx, [rsp+0B8h+var_98]
0x18007fffa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007ffff  lea     rdx, [rsp+0B8h+var_98]
0x180080004  mov     rcx, rdi
0x180080007  mov     rax, rbx
0x18008000a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008000f  mov     rcx, [rsp+0B8h]; this
0x180080017  test    eax, eax
0x180080019  jns     short loc_18008002E
0x18008001b  mov     r9d, eax; char *
0x18008001e  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080025  lea     edx, [r14+2Ah]; void *
0x180080029  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008002e  mov     rcx, qword ptr [rsp+0B8h+var_98]
0x180080033  test    rcx, rcx
0x180080036  jz      loc_18008028F
0x18008003c  mov     [rsp+0B8h+arg_18], 0
0x180080047  mov     rax, [rcx]
0x18008004a  lea     rdx, [rsp+0B8h+arg_18]
0x180080052  mov     rax, [rax+38h]
0x180080056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008005b  mov     rcx, [rsp+0B8h]; this
0x180080063  test    eax, eax
0x180080065  jns     short loc_18008007B
0x180080067  mov     r9d, eax; char *
0x18008006a  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080071  mov     edx, 30h ; '0'; void *
0x180080076  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008007b  mov     [rsp+0B8h+var_48], 0
0x180080084  mov     [rsp+0B8h+var_90], 0
0x18008008c  mov     rdi, qword ptr [rsp+0B8h+var_98]
0x180080091  mov     rax, [rdi]
0x180080094  mov     rbx, [rax+58h]
0x180080098  lea     rcx, [rsp+0B8h+var_48]
0x18008009d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800800a2  lea     rdx, [rsp+0B8h+var_48]
0x1800800a7  mov     rcx, rdi
0x1800800aa  mov     rax, rbx
0x1800800ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800800b2  mov     rcx, [rsp+0B8h]; this
0x1800800ba  test    eax, eax
0x1800800bc  jns     short loc_1800800D2
0x1800800be  mov     r9d, eax; char *
0x1800800c1  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800800c8  mov     edx, 34h ; '4'; void *
0x1800800cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800800d2  mov     rcx, [rsp+0B8h+var_48]
0x1800800d7  mov     rax, [rcx]
0x1800800da  lea     rdx, [rsp+0B8h+var_90]
0x1800800df  mov     rax, [rax+40h]
0x1800800e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800800e8  mov     rcx, [rsp+0B8h]; this
0x1800800f0  test    eax, eax
0x1800800f2  jns     short loc_180080108
0x1800800f4  mov     r9d, eax; char *
0x1800800f7  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800800fe  mov     edx, 35h ; '5'; void *
0x180080103  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080108  mov     [rsp+0B8h+var_58], 0
0x180080111  lea     rdx, [rsp+0B8h+var_58]
0x180080116  lea     rcx, [rsp+0B8h+var_98]
0x18008011b  call    ??$As@UIConnectionProfile2@Connectivity@Networking@Windows@@@?$ComPtr@UIConnectionProfile@Connectivity@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIConnectionProfile2@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile>::As<Windows::Networking::Connectivity::IConnectionProfile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile2>>)
0x180080120  mov     rcx, [rsp+0B8h]; this
0x180080128  test    eax, eax
0x18008012a  jns     short loc_180080140
0x18008012c  mov     r9d, eax; char *
0x18008012f  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080136  mov     edx, 38h ; '8'; void *
0x18008013b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080140  mov     byte ptr [rsp+0B8h+arg_8], 0
0x180080148  mov     rcx, [rsp+0B8h+var_58]
0x18008014d  mov     rax, [rcx]
0x180080150  lea     rdx, [rsp+0B8h+arg_8]
0x180080158  mov     rax, [rax+38h]
0x18008015c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080161  mov     rcx, [rsp+0B8h]; this
0x180080169  test    eax, eax
0x18008016b  jns     short loc_180080181
0x18008016d  mov     r9d, eax; char *
0x180080170  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180080177  mov     edx, 3Ah ; ':'; void *
0x18008017c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080181  mov     [rsp+0B8h+arg_10], 0
0x180080189  mov     rcx, [rsp+0B8h+var_58]
0x18008018e  mov     rax, [rcx]
0x180080191  lea     rdx, [rsp+0B8h+arg_10]
0x180080199  mov     rax, [rax+30h]
0x18008019d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800801a2  mov     rcx, [rsp+0B8h]; this
0x1800801aa  test    eax, eax
0x1800801ac  jns     short loc_1800801C2
0x1800801ae  mov     r9d, eax; char *
0x1800801b1  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800801b8  mov     edx, 3Ch ; '<'; void *
0x1800801bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800801c2  mov     eax, [rsp+0B8h+arg_18]
0x1800801c9  mov     [rsp+0B8h+var_50], eax
0x1800801cd  lea     rdx, [rsp+0B8h+var_50]
0x1800801d2  call    ?at@?$map@IV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@QEBAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBI@Z; std::map<uint,std::string>::at(uint const &)
0x1800801d7  mov     rdx, rax
0x1800801da  mov     rcx, rax
0x1800801dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800801e2  mov     qword ptr [rsp+0B8h+var_88], rax
0x1800801e7  mov     rax, [rdx+10h]
0x1800801eb  mov     qword ptr [rsp+0B8h+var_88+8], rax
0x1800801f0  mov     eax, [rsp+0B8h+var_90]
0x1800801f4  mov     dword ptr [rsp+0B8h+var_68], eax
0x1800801f8  cmp     byte ptr [rsp+0B8h+arg_8], 0
0x180080200  jz      short loc_180080210
0x180080202  lea     rax, aWifi_0; "WiFi"
0x180080209  mov     qword ptr [rsp+0B8h+var_78], rax
0x18008020e  jmp     short loc_180080275
0x180080210  cmp     [rsp+0B8h+arg_10], 0
0x180080218  jz      short loc_180080223
0x18008021a  lea     rax, aCellular; "Cellular"
0x180080221  jmp     short loc_180080260
0x180080223  test    eax, eax
0x180080225  jz      short loc_180080270
0x180080227  sub     eax, 6
0x18008022a  jz      short loc_180080259
0x18008022c  sub     eax, 14h
0x18008022f  jz      short loc_180080259
0x180080231  sub     eax, 0CFh
0x180080236  jz      short loc_180080259
0x180080238  sub     eax, 10h
0x18008023b  jz      short loc_180080259
0x18008023d  cmp     eax, 11h
0x180080240  jz      short loc_180080259
0x180080242  lea     rax, aOther; "Other"
0x180080249  mov     qword ptr [rsp+0B8h+var_78], rax
0x18008024e  mov     qword ptr [rsp+0B8h+var_78+8], 5
0x180080257  jmp     short loc_18008027A
0x180080259  lea     rax, aEthernet; "Ethernet"
0x180080260  mov     qword ptr [rsp+0B8h+var_78], rax
0x180080265  mov     qword ptr [rsp+0B8h+var_78+8], 8
0x18008026e  jmp     short loc_18008027A
0x180080270  mov     qword ptr [rsp+0B8h+var_78], r13
0x180080275  mov     qword ptr [rsp+0B8h+var_78+8], r12
0x18008027a  lea     rcx, [rsp+0B8h+var_58]
0x18008027f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080284  nop
0x180080285  lea     rcx, [rsp+0B8h+var_48]
0x18008028a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008028f  lea     rcx, [r15+38h]; _Smtx_t *
0x180080293  mov     [rsp+0B8h+var_48], rcx
0x180080298  call    _Smtx_lock_exclusive
0x18008029d  mov     [rsp+0B8h+var_40], 1
0x1800802a2  lea     rbx, [r15+10h]
0x1800802a6  movups  xmm0, [rsp+0B8h+var_88]
0x1800802ab  movups  xmmword ptr [rbx], xmm0
0x1800802ae  movups  xmm1, [rsp+0B8h+var_78]
0x1800802b3  movups  xmmword ptr [rbx+10h], xmm1
0x1800802b7  movsd   xmm0, [rsp+0B8h+var_68]
0x1800802bd  movsd   qword ptr [rbx+20h], xmm0
0x1800802c2  lea     rcx, [rsp+0B8h+var_48]
0x1800802c7  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x1800802cc  nop
0x1800802cd  lea     rcx, [rsp+0B8h+var_98]
0x1800802d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800802d7  nop
0x1800802d8  jmp     short loc_1800802EE
0x1800802da  mov     rbx, [rsp+0B8h+arg_0]
0x1800802e2  add     rbx, 10h
0x1800802e6  mov     r14d, [rsp+0B8h+arg_8]
0x1800802ee  call    ?IsEnabled@WpnconTelemetry@@SA_NE_K@Z; WpnconTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800802f3  test    al, al
0x1800802f5  jz      short loc_18008032F
0x1800802f7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_de4d36b645fed666bcd49a481e929f91_@@CA@XZ; _lambda_de4d36b645fed666bcd49a481e929f91_::_lambda_invoker_cdecl_(void)
0x1800802fe  call    ?get@?$static_lazy@VWpnconTelemetry@@@details@wil@@QEAAPEAVWpnconTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpnconTelemetry>::get(void (*)(void))
0x180080303  movups  xmm0, xmmword ptr [rbx]
0x180080306  movaps  [rsp+0B8h+var_88], xmm0
0x18008030b  movups  xmm1, xmmword ptr [rbx+10h]
0x18008030f  movaps  [rsp+0B8h+var_78], xmm1
0x180080314  movsd   xmm0, qword ptr [rbx+20h]
0x180080319  movsd   [rsp+0B8h+var_68], xmm0
0x18008031f  lea     r8, [rsp+0B8h+var_88]
0x180080324  mov     edx, r14d
0x180080327  mov     rcx, rax
0x18008032a  call    ?NetworkStateChanged_@WpnconTelemetry@@QEAAXJUNetworkStateInformation@NetworkStateTracker@@@Z; WpnconTelemetry::NetworkStateChanged_(long,NetworkStateTracker::NetworkStateInformation)
0x18008032f  mov     eax, r14d
0x180080332  add     rsp, 88h
0x180080339  pop     r15
0x18008033b  pop     r14
0x18008033d  pop     r13
0x18008033f  pop     r12
0x180080341  pop     rdi
0x180080342  pop     rbx
0x180080343  retn
```
