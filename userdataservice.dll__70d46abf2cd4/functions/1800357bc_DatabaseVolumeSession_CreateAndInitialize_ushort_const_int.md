# DatabaseVolumeSession::CreateAndInitialize(ushort const *,int)

- ea: `0x1800357bc`
- end: `0x180035c2b`
- name: `?CreateAndInitialize@DatabaseVolumeSession@@QEAAJPEBGH@Z`
- size: `1135`
- prototype: `__int64 __fastcall(JET_INSTANCE *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800629c4`

## callees

- `0x180008f0c`
- `0x1800357bc`
- `0x180035c40`
- `0x180035db4`
- `0x180069de8`
- `0x180076664`
- `0x18007ba48`
- `0x18007be90`
- `0x18009a498`
- `0x18009e74c`
- `0x18009eec0`
- `0x180114d28`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetBeginSessionA` at `0x180035b4d`
- `ESENT!JetBeginSessionA` at `0x180035b4d`
- `ESENT!JetCreateInstanceW` at `0x1800358d4`
- `ESENT!JetCreateInstanceW` at `0x1800358d4`
- `ESENT!JetSetSystemParameterW` at `0x18003592e`
- `ESENT!JetSetSystemParameterW` at `0x180035977`
- `ESENT!JetSetSystemParameterW` at `0x1800359a1`
- `ESENT!JetSetSystemParameterW` at `0x1800359e1`
- `ESENT!JetSetSystemParameterW` at `0x180035a0c`
- `ESENT!JetSetSystemParameterW` at `0x180035a39`
- `ESENT!JetSetSystemParameterW` at `0x180035a69`
- `ESENT!JetSetSystemParameterW` at `0x180035a99`
- `ESENT!JetSetSystemParameterW` at `0x180035acc`
- `ESENT!JetSetSystemParameterW` at `0x180035afc`
- `ESENT!JetSetSystemParameterW` at `0x18003592e`
- `ESENT!JetSetSystemParameterW` at `0x180035977`
- `ESENT!JetSetSystemParameterW` at `0x1800359a1`
- `ESENT!JetSetSystemParameterW` at `0x1800359e1`
- `ESENT!JetSetSystemParameterW` at `0x180035a0c`
- `ESENT!JetSetSystemParameterW` at `0x180035a39`
- `ESENT!JetSetSystemParameterW` at `0x180035a69`
- `ESENT!JetSetSystemParameterW` at `0x180035a99`
- `ESENT!JetSetSystemParameterW` at `0x180035acc`
- `ESENT!JetSetSystemParameterW` at `0x180035afc`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800358ae`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800358ae`
- `unistore!GetUnistoreJetInstance` at `0x18003580a`
- `unistore!GetUnistoreJetInstance` at `0x18003580a`
- `UserDataPlatformHelperUtil!SetCommsServiceJetGlobalSystemParameters` at `0x1800358b4`
- `UserDataPlatformHelperUtil!SetCommsServiceJetGlobalSystemParameters` at `0x1800358b4`

## string_xrefs

- `0x180035820`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18003585f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180035945`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800359b8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180035b2c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180035b97`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180035bed`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall DatabaseVolumeSession::CreateAndInitialize(JET_INSTANCE *this, const unsigned __int16 *a2, int a3)
{
  JET_INSTANCE *v5; // rdi
  int UnistoreJetInstance; // eax
  unsigned int v7; // esi
  int v9; // edi
  unsigned __int64 v10; // r11
  __int64 v11; // r9
  __int64 v12; // rdx
  JET_ERR InstanceW; // eax
  __int128 *v14; // rax
  JET_ERR v15; // eax
  __int64 v16; // rbx
  JET_ERR v17; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v19; // r9
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  JET_ERR v26; // eax
  JET_ERR v27; // eax
  unsigned int v28; // edx
  int v29; // eax
  int v30; // esi
  JET_ERR v31; // eax
  __int64 v32; // [rsp+30h] [rbp-D0h] BYREF
  char v33; // [rsp+38h] [rbp-C8h]
  __int128 v34; // [rsp+40h] [rbp-C0h] BYREF
  char v35; // [rsp+50h] [rbp-B0h]
  WCHAR sz[264]; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+2D0h] [rbp+1D0h] BYREF

  v37 = a3;
  if ( a3 )
  {
    v5 = this + 5;
    UnistoreJetInstance = GetUnistoreJetInstance(this + 5);
    v7 = UnistoreJetInstance;
    if ( UnistoreJetInstance < 0 )
    {
      Log_HREvent(
        (unsigned int)UnistoreJetInstance,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        784);
      return v7;
    }
    goto LABEL_14;
  }
  v9 = StringCchCopyW(sz, 0x104u, L"UDM-");
  if ( v9 < 0 )
  {
    v11 = 792;
LABEL_6:
    Log_HREvent(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v11);
    return (unsigned int)v9;
  }
  v9 = StringCchCatW(sz, v10, a2);
  if ( v9 < 0 )
  {
    v11 = 793;
    goto LABEL_6;
  }
  v12 = -1;
  do
    ++v12;
  while ( sz[v12] );
  CharLowerBuffW(sz, v12);
  v9 = SetCommsServiceJetGlobalSystemParameters();
  if ( v9 < 0 )
  {
    v11 = 796;
    goto LABEL_6;
  }
  v5 = this + 5;
  InstanceW = JetCreateInstanceW(this + 5, sz);
  if ( InstanceW < 0 )
  {
    LODWORD(v16) = MakeHresultFromJetError(InstanceW);
    Log_HREvent(
      (unsigned int)v16,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      798);
    return (unsigned int)v16;
  }
LABEL_14:
  v14 = (__int128 *)lambda_4c6e8a46d956cabcc403efff6469091f_::_lambda_4c6e8a46d956cabcc403efff6469091f_(
                      &v32,
                      this,
                      &v37);
  v35 = 1;
  v34 = *v14;
  if ( v37 )
    goto LABEL_38;
  v15 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 3u, 0, L"UDM");
  if ( v15 >= 0 )
  {
    v17 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, a2);
    if ( v17 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v17);
      v19 = 822;
LABEL_21:
      LODWORD(v16) = HresultFromJetError;
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        v19);
LABEL_42:
      tlx::_UndoSolo__lambda_4c6e8a46d956cabcc403efff6469091f___::__UndoSolo__lambda_4c6e8a46d956cabcc403efff6469091f___(&v34);
      return (unsigned int)v16;
    }
    v20 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 1u, 0, a2);
    if ( v20 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v20);
      v19 = 823;
      goto LABEL_21;
    }
    v21 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 2u, 0, a2);
    if ( v21 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v21);
      v19 = 824;
      goto LABEL_21;
    }
    v22 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 0x71u, 0, a2);
    if ( v22 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v22);
      v19 = 825;
      goto LABEL_21;
    }
    v23 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 0x30u, 1u, 0);
    if ( v23 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v23);
      v19 = 826;
      goto LABEL_21;
    }
    v24 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 0x11u, 1u, 0);
    if ( v24 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v24);
      v19 = 827;
      goto LABEL_21;
    }
    v25 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 0x2Du, 1u, 0);
    if ( v25 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v25);
      v19 = 828;
      goto LABEL_21;
    }
    v26 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 0xBu, 0xC00u, 0);
    if ( v26 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v26);
      v19 = 830;
      goto LABEL_21;
    }
    v27 = JetSetSystemParameterW(v5, 0xFFFFFFFFFFFFFFFFuLL, 0x4Du, 1u, 0);
    if ( v27 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v27);
      v19 = 832;
      goto LABEL_21;
    }
    v29 = CommsESE_JetInit2(v5, v28);
    v30 = v29;
    if ( v29 < 0 )
    {
      Log_HREvent(
        (unsigned int)v29,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        834);
      LODWORD(v16) = v30;
      goto LABEL_42;
    }
LABEL_38:
    v31 = JetBeginSessionA(*v5, this + 6, 0, 0);
    if ( v31 >= 0 )
    {
      v32 = *(_QWORD *)_lambda_a98995495b2f0ca89e3fa4f24af127c7_::_lambda_a98995495b2f0ca89e3fa4f24af127c7_(
                         (_lambda_a98995495b2f0ca89e3fa4f24af127c7_ *)&v32,
                         (struct StoreManagerEnumerator *)this);
      v33 = 1;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              this + 1,
                              a2) )
      {
        *((_DWORD *)this + 15) = v37;
        v33 = 0;
        tlx::_UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe___::__UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe___(&v32);
        return 0;
      }
      LODWORD(v16) = -2147024882;
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        847);
      tlx::_UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe___::__UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe___(&v32);
      goto LABEL_42;
    }
    HresultFromJetError = MakeHresultFromJetError(v31);
    v19 = 837;
    goto LABEL_21;
  }
  v16 = (unsigned int)MakeHresultFromJetError(v15);
  Log_HREvent(
    v16,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    821);
  lambda_4c6e8a46d956cabcc403efff6469091f_::operator()(&v34);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800357bc  mov     [rsp-8+arg_18], rbx
0x1800357c1  mov     [rsp-8+arg_10], r8d
0x1800357c6  push    rbp
0x1800357c7  push    rsi
0x1800357c8  push    rdi
0x1800357c9  push    r12
0x1800357cb  push    r13
0x1800357cd  push    r14
0x1800357cf  push    r15
0x1800357d1  lea     rbp, [rsp-180h]
0x1800357d9  sub     rsp, 280h
0x1800357e0  mov     rax, cs:__security_cookie
0x1800357e7  xor     rax, rsp
0x1800357ea  mov     [rbp+1B0h+var_40], rax
0x1800357f1  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800357f5  xor     r12d, r12d
0x1800357f8  mov     r15, rdx
0x1800357fb  mov     r14, rcx
0x1800357fe  test    r8d, r8d
0x180035801  jz      short loc_180035839
0x180035803  lea     rdi, [rcx+28h]
0x180035807  mov     rcx, rdi
0x18003580a  call    cs:__imp_GetUnistoreJetInstance
0x180035810  mov     esi, eax
0x180035812  test    eax, eax
0x180035814  jns     loc_1800358E2
0x18003581a  mov     r9d, 310h
0x180035820  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180035827  lea     edx, [r13+2]
0x18003582b  mov     ecx, eax
0x18003582d  call    Log_HREvent
0x180035832  mov     eax, esi
0x180035834  jmp     loc_180035C01
0x180035839  mov     r11d, 104h
0x18003583f  lea     r8, aUdm; "UDM-"
0x180035846  mov     edx, r11d; unsigned __int64
0x180035849  lea     rcx, [rsp+2B0h+sz]; unsigned __int16 *
0x18003584e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035853  mov     edi, eax
0x180035855  test    eax, eax
0x180035857  jns     short loc_180035879
0x180035859  mov     r9d, 318h
0x18003585f  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180035866  mov     edx, 1
0x18003586b  mov     ecx, edi
0x18003586d  call    Log_HREvent
0x180035872  mov     eax, edi
0x180035874  jmp     loc_180035C01
0x180035879  mov     r8, r15; unsigned __int16 *
0x18003587c  lea     rcx, [rsp+2B0h+sz]; unsigned __int16 *
0x180035881  mov     rdx, r11; unsigned __int64
0x180035884  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035889  mov     edi, eax
0x18003588b  test    eax, eax
0x18003588d  jns     short loc_180035897
0x18003588f  mov     r9d, 319h
0x180035895  jmp     short loc_18003585F
0x180035897  lea     rax, [rsp+2B0h+sz]
0x18003589c  mov     rdx, r13
0x18003589f  inc     rdx; cchLength
0x1800358a2  cmp     [rax+rdx*2], r12w
0x1800358a7  jnz     short loc_18003589F
0x1800358a9  lea     rcx, [rsp+2B0h+sz]; lpsz
0x1800358ae  call    cs:__imp_CharLowerBuffW
0x1800358b4  call    cs:__imp_SetCommsServiceJetGlobalSystemParameters
0x1800358ba  mov     edi, eax
0x1800358bc  test    eax, eax
0x1800358be  jns     short loc_1800358C8
0x1800358c0  mov     r9d, 31Ch
0x1800358c6  jmp     short loc_18003585F
0x1800358c8  lea     rdi, [r14+28h]
0x1800358cc  mov     rcx, rdi; pinstance
0x1800358cf  lea     rdx, [rsp+2B0h+sz]; szInstanceName
0x1800358d4  call    cs:__imp_JetCreateInstanceW
0x1800358da  test    eax, eax
0x1800358dc  js      loc_180035BE0
0x1800358e2  lea     r8, [rbp+1B0h+arg_10]
0x1800358e9  mov     rdx, r14
0x1800358ec  lea     rcx, [rsp+2B0h+var_280]
0x1800358f1  call    _lambda_4c6e8a46d956cabcc403efff6469091f____lambda_4c6e8a46d956cabcc403efff6469091f_
0x1800358f6  mov     ebx, 1
0x1800358fb  mov     [rsp+2B0h+var_260], bl
0x1800358ff  movups  xmm0, xmmword ptr [rax]
0x180035902  movdqu  [rsp+2B0h+var_270], xmm0
0x180035908  cmp     [rbp+1B0h+arg_10], r12d
0x18003590f  jnz     loc_180035B40
0x180035915  lea     rax, ?gc_szUserDataBaseName@@3QBGB; "UDM"
0x18003591c  xor     r9d, r9d; lParam
0x18003591f  lea     r8d, [rbx+2]; paramid
0x180035923  mov     [rsp+2B0h+szParam], rax; szParam
0x180035928  mov     rdx, r13; sesid
0x18003592b  mov     rcx, rdi; pinstance
0x18003592e  call    cs:__imp_JetSetSystemParameterW
0x180035934  test    eax, eax
0x180035936  jns     short loc_180035966
0x180035938  mov     ecx, eax; int
0x18003593a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18003593f  mov     r9d, 335h
0x180035945  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003594c  xor     edx, edx
0x18003594e  mov     ecx, eax
0x180035950  mov     ebx, eax
0x180035952  call    Log_HREvent
0x180035957  lea     rcx, [rsp+2B0h+var_270]
0x18003595c  call    _lambda_4c6e8a46d956cabcc403efff6469091f___operator__
0x180035961  jmp     loc_180035BFF
0x180035966  xor     r9d, r9d; lParam
0x180035969  mov     [rsp+2B0h+szParam], r15; szParam
0x18003596e  xor     r8d, r8d; paramid
0x180035971  mov     rdx, r13; sesid
0x180035974  mov     rcx, rdi; pinstance
0x180035977  call    cs:__imp_JetSetSystemParameterW
0x18003597d  test    eax, eax
0x18003597f  jns     short loc_180035990
0x180035981  mov     ecx, eax; int
0x180035983  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035988  mov     r9d, 336h
0x18003598e  jmp     short loc_1800359B8
0x180035990  xor     r9d, r9d; lParam
0x180035993  mov     [rsp+2B0h+szParam], r15; szParam
0x180035998  mov     r8d, ebx; paramid
0x18003599b  mov     rdx, r13; sesid
0x18003599e  mov     rcx, rdi; pinstance
0x1800359a1  call    cs:__imp_JetSetSystemParameterW
0x1800359a7  test    eax, eax
0x1800359a9  jns     short loc_1800359CF
0x1800359ab  mov     ecx, eax; int
0x1800359ad  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800359b2  mov     r9d, 337h
0x1800359b8  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800359bf  xor     edx, edx
0x1800359c1  mov     ecx, eax
0x1800359c3  mov     ebx, eax
0x1800359c5  call    Log_HREvent
0x1800359ca  jmp     loc_180035BB7
0x1800359cf  xor     r9d, r9d; lParam
0x1800359d2  mov     [rsp+2B0h+szParam], r15; szParam
0x1800359d7  mov     rdx, r13; sesid
0x1800359da  mov     rcx, rdi; pinstance
0x1800359dd  lea     r8d, [r9+2]; paramid
0x1800359e1  call    cs:__imp_JetSetSystemParameterW
0x1800359e7  test    eax, eax
0x1800359e9  jns     short loc_1800359FA
0x1800359eb  mov     ecx, eax; int
0x1800359ed  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800359f2  mov     r9d, 338h
0x1800359f8  jmp     short loc_1800359B8
0x1800359fa  xor     r9d, r9d; lParam
0x1800359fd  mov     [rsp+2B0h+szParam], r15; szParam
0x180035a02  mov     rdx, r13; sesid
0x180035a05  mov     rcx, rdi; pinstance
0x180035a08  lea     r8d, [r9+71h]; paramid
0x180035a0c  call    cs:__imp_JetSetSystemParameterW
0x180035a12  test    eax, eax
0x180035a14  jns     short loc_180035A25
0x180035a16  mov     ecx, eax; int
0x180035a18  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035a1d  mov     r9d, 339h
0x180035a23  jmp     short loc_1800359B8
0x180035a25  mov     r9, rbx; lParam
0x180035a28  mov     [rsp+2B0h+szParam], r12; szParam
0x180035a2d  mov     r8d, 30h ; '0'; paramid
0x180035a33  mov     rdx, r13; sesid
0x180035a36  mov     rcx, rdi; pinstance
0x180035a39  call    cs:__imp_JetSetSystemParameterW
0x180035a3f  test    eax, eax
0x180035a41  jns     short loc_180035A55
0x180035a43  mov     ecx, eax; int
0x180035a45  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035a4a  mov     r9d, 33Ah
0x180035a50  jmp     loc_1800359B8
0x180035a55  mov     r9, rbx; lParam
0x180035a58  mov     [rsp+2B0h+szParam], r12; szParam
0x180035a5d  mov     r8d, 11h; paramid
0x180035a63  mov     rdx, r13; sesid
0x180035a66  mov     rcx, rdi; pinstance
0x180035a69  call    cs:__imp_JetSetSystemParameterW
0x180035a6f  test    eax, eax
0x180035a71  jns     short loc_180035A85
0x180035a73  mov     ecx, eax; int
0x180035a75  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035a7a  mov     r9d, 33Bh
0x180035a80  jmp     loc_1800359B8
0x180035a85  mov     r9, rbx; lParam
0x180035a88  mov     [rsp+2B0h+szParam], r12; szParam
0x180035a8d  mov     r8d, 2Dh ; '-'; paramid
0x180035a93  mov     rdx, r13; sesid
0x180035a96  mov     rcx, rdi; pinstance
0x180035a99  call    cs:__imp_JetSetSystemParameterW
0x180035a9f  test    eax, eax
0x180035aa1  jns     short loc_180035AB5
0x180035aa3  mov     ecx, eax; int
0x180035aa5  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035aaa  mov     r9d, 33Ch
0x180035ab0  jmp     loc_1800359B8
0x180035ab5  mov     r9d, 0C00h; lParam
0x180035abb  mov     [rsp+2B0h+szParam], r12; szParam
0x180035ac0  mov     r8d, 0Bh; paramid
0x180035ac6  mov     rdx, r13; sesid
0x180035ac9  mov     rcx, rdi; pinstance
0x180035acc  call    cs:__imp_JetSetSystemParameterW
0x180035ad2  test    eax, eax
0x180035ad4  jns     short loc_180035AE8
0x180035ad6  mov     ecx, eax; int
0x180035ad8  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035add  mov     r9d, 33Eh
0x180035ae3  jmp     loc_1800359B8
0x180035ae8  mov     r9, rbx; lParam
0x180035aeb  mov     [rsp+2B0h+szParam], r12; szParam
0x180035af0  mov     r8d, 4Dh ; 'M'; paramid
0x180035af6  mov     rdx, r13; sesid
0x180035af9  mov     rcx, rdi; pinstance
0x180035afc  call    cs:__imp_JetSetSystemParameterW
0x180035b02  test    eax, eax
0x180035b04  jns     short loc_180035B18
0x180035b06  mov     ecx, eax; int
0x180035b08  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035b0d  mov     r9d, 340h
0x180035b13  jmp     loc_1800359B8
0x180035b18  mov     rcx, rdi; unsigned __int64 *
0x180035b1b  call    ?CommsESE_JetInit2@@YAJPEA_KK@Z; CommsESE_JetInit2(unsigned __int64 *,ulong)
0x180035b20  mov     esi, eax
0x180035b22  test    eax, eax
0x180035b24  jns     short loc_180035B40
0x180035b26  mov     r9d, 342h
0x180035b2c  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180035b33  mov     edx, ebx
0x180035b35  mov     ecx, eax
0x180035b37  call    Log_HREvent
0x180035b3c  mov     ebx, esi
0x180035b3e  jmp     short loc_180035BB7
0x180035b40  mov     rcx, [rdi]; instance
0x180035b43  lea     rdx, [r14+30h]; psesid
0x180035b47  xor     r9d, r9d; szPassword
0x180035b4a  xor     r8d, r8d; szUserName
0x180035b4d  call    cs:__imp_JetBeginSessionA
0x180035b53  test    eax, eax
0x180035b55  jns     short loc_180035B69
0x180035b57  mov     ecx, eax; int
0x180035b59  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035b5e  mov     r9d, 345h
0x180035b64  jmp     loc_1800359B8
0x180035b69  mov     rdx, r14; struct StoreManagerEnumerator *
0x180035b6c  lea     rcx, [rsp+2B0h+var_280]; this
0x180035b71  call    ??0_lambda_a98995495b2f0ca89e3fa4f24af127c7_@@QEAA@PEAVStoreManagerEnumerator@@@Z; _lambda_a98995495b2f0ca89e3fa4f24af127c7_::_lambda_a98995495b2f0ca89e3fa4f24af127c7_(StoreManagerEnumerator *)
0x180035b76  mov     rdx, r15
0x180035b79  mov     rcx, [rax]
0x180035b7c  mov     [rsp+2B0h+var_280], rcx
0x180035b81  lea     rcx, [r14+8]
0x180035b85  mov     [rsp+2B0h+var_278], bl
0x180035b89  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180035b8e  test    al, al
0x180035b90  jnz     short loc_180035BC3
0x180035b92  mov     ebx, 8007000Eh
0x180035b97  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180035b9e  mov     ecx, ebx
0x180035ba0  mov     r9d, 34Fh
0x180035ba6  xor     edx, edx
0x180035ba8  call    Log_HREvent
0x180035bad  lea     rcx, [rsp+2B0h+var_280]
0x180035bb2  call    tlx___UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe_______UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe___
0x180035bb7  lea     rcx, [rsp+2B0h+var_270]
0x180035bbc  call    tlx___UndoSolo__lambda_4c6e8a46d956cabcc403efff6469091f_______UndoSolo__lambda_4c6e8a46d956cabcc403efff6469091f___
0x180035bc1  jmp     short loc_180035BFF
0x180035bc3  mov     eax, [rbp+1B0h+arg_10]
0x180035bc9  lea     rcx, [rsp+2B0h+var_280]
0x180035bce  mov     [r14+3Ch], eax
0x180035bd2  mov     [rsp+2B0h+var_278], r12b
0x180035bd7  call    tlx___UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe_______UndoSolo__lambda_78b34c185afde8bacd6b73e07dbb4dfe___
0x180035bdc  xor     eax, eax
0x180035bde  jmp     short loc_180035C01
0x180035be0  mov     ecx, eax; int
0x180035be2  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180035be7  mov     r9d, 31Eh
0x180035bed  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180035bf4  xor     edx, edx
0x180035bf6  mov     ecx, eax
0x180035bf8  mov     ebx, eax
0x180035bfa  call    Log_HREvent
0x180035bff  mov     eax, ebx
0x180035c01  mov     rcx, [rbp+1B0h+var_40]
0x180035c08  xor     rcx, rsp; StackCookie
0x180035c0b  call    __security_check_cookie
0x180035c10  mov     rbx, [rsp+2B0h+arg_18]
0x180035c18  add     rsp, 280h
0x180035c1f  pop     r15
0x180035c21  pop     r14
0x180035c23  pop     r13
0x180035c25  pop     r12
0x180035c27  pop     rdi
0x180035c28  pop     rsi
0x180035c29  pop     rbp
0x180035c2a  retn
```
