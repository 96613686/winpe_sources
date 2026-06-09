# CMMAudioEnum::CreateEnum(void)

- ea: `0x1800bd214`
- end: `0x1800bd819`
- name: `?CreateEnum@CMMAudioEnum@@AEAAJXZ`
- size: `1541`
- prototype: `__int64 __fastcall(CMMAudioEnum *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800be040`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000cdb0`
- `0x180011cb0`
- `0x1800123c0`
- `0x180013ec0`
- `0x1800207f8`
- `0x18003c7e0`
- `0x180079e30`
- `0x18007a2dc`
- `0x18007a350`
- `0x18007aae4`
- `0x1800bd214`
- `0x1800bdea4`
- `0x1800be12c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800bd5ef`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800bd5ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd261`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd567`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd261`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bd567`
- `api-ms-win-mm-mme-l1-1-0!waveOutGetNumDevs` at `0x1800bd2a2`
- `api-ms-win-mm-mme-l1-1-0!waveOutGetNumDevs` at `0x1800bd2a2`
- `api-ms-win-mm-mme-l1-1-0!waveInGetNumDevs` at `0x1800bd29a`
- `api-ms-win-mm-mme-l1-1-0!waveInGetNumDevs` at `0x1800bd29a`
- `api-ms-win-mm-mme-l1-1-0!waveInGetDevCapsW` at `0x1800bd406`
- `api-ms-win-mm-mme-l1-1-0!waveInGetDevCapsW` at `0x1800bd406`

## string_xrefs

- `0x1800bd608`: `CLSID`
- `0x1800bd322`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioOutput\TokenEnums\MMAudioOut\`
- `0x1800bd4f6`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioOutput\TokenEnums\MMAudioOut\`
- `0x1800bd338`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioInput\TokenEnums\MMAudioIn\`
- `0x1800bd4ec`: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioInput\TokenEnums\MMAudioIn\`
- `0x1800bd47e`: `Cannot open audio %s device %u. Error = %X. Ignored`
- `0x1800bd751`: `Failed to create audio device (Name=%S, Id=%S), hr=0x%X. Ignored the device.`
- `0x1800bd7ad`: `Default MMSYS audio device token id is %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CMMAudioEnum::CreateEnum(LPVOID *this)
{
  _QWORD *v2; // r13
  HRESULT Instance; // ebx
  unsigned int v4; // r15d
  UINT NumDevs; // eax
  const char *v6; // r9
  unsigned int v7; // r8d
  const wchar_t *v8; // rdx
  unsigned int v9; // eax
  const wchar_t *v10; // r8
  unsigned int v11; // r12d
  unsigned int v12; // r8d
  struct tagWAVEINCAPSW *v13; // rax
  struct tagWAVEINCAPSW *v14; // rdi
  MMRESULT DevCapsW; // esi
  int v16; // r9d
  const char *v17; // r8
  WCHAR *szPname; // rdi
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  int v22; // esi
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // rdx
  GUID *v25; // rcx
  char v27; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *ppv; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  struct ISpDataKey *v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v36; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 Src[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+A0h] [rbp-60h]
  __int128 v40; // [rsp+B0h] [rbp-50h]
  __int128 v41; // [rsp+C0h] [rbp-40h]
  tagWAVEOUTCAPSW v42; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v43[264]; // [rsp+130h] [rbp+30h] BYREF

  v2 = this + 11;
  Instance = CoCreateInstance(&CLSID_SpObjectTokenEnum, 0, 0x17u, &GUID_06b64f9f_7fda_11d2_b4f2_00c04f797396, this + 11);
  if ( Instance >= 0 )
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v2 + 72LL))(*v2, 0, 0);
  v4 = 0;
  if ( Instance >= 0 )
  {
    if ( *((_DWORD *)this + 20) )
      NumDevs = waveInGetNumDevs();
    else
      NumDevs = waveOutGetNumDevs();
    v4 = NumDevs;
    v6 = "input";
    if ( !*((_DWORD *)this + 20) )
      v6 = "output";
    DoTraceMessage(16, "Enumerate %u %s MMSYS audio devices available", NumDevs, v6);
  }
  memset_0(v43, 0, 0x20Au);
  v27 = 0;
  if ( Instance >= 0 && v4 > 1 )
  {
    v27 = 1;
    Instance = CMMAudioEnum::GetDefaultDeviceLegacy((CMMAudioEnum *)this, v43, v7);
    if ( Instance < 0 )
    {
      DoTraceMessage(4, "Cannot determine the current default audio device");
      Instance = 0;
      v27 = 0;
    }
  }
  v34 = 0;
  if ( Instance >= 0 && v4 )
  {
    ppv = 0;
    v8 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\TokenEnums\\MMAudioIn\\";
    if ( !*((_DWORD *)this + 20) )
      v8 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioOutput\\TokenEnums\\MMAudioOut\\";
    if ( CSpDynamicString::operator=(&ppv, v8) )
    {
      v9 = CSpDynamicString::Length((CSpDynamicString *)&ppv);
      CSpDynamicString::TrimToSize((CSpDynamicString *)&ppv, v9 - 1);
      Instance = SpSzRegPathToDataKey(HKEY_CURRENT_USER, ppv, 1, &v34);
    }
    else
    {
      Instance = -2147024882;
    }
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&ppv);
  }
  v10 = 0;
  v29 = 0;
  v35 = 0;
  v11 = 0;
  if ( Instance < 0 )
  {
LABEL_72:
    DoTraceMessage(
      4,
      "Could not find the audio device that matches the default device. Use the first available device",
      v10);
    v35 = 0;
    v10 = 0;
    v29 = 0;
    goto LABEL_73;
  }
  while ( v11 < v4 )
  {
    memset_0(Src, 0, 0x50u);
    memset_0(&v42, 0, sizeof(v42));
    if ( *((_DWORD *)this + 20) )
    {
      v13 = (struct tagWAVEINCAPSW *)operator new[](0x54u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( v13 )
      {
        DevCapsW = waveInGetDevCapsW(v11, v13, 0x50u);
        if ( !DevCapsW )
        {
          *(_OWORD *)Src = *(_OWORD *)&v14->wMid;
          v38 = *(_OWORD *)&v14->szPname[4];
          v39 = *(_OWORD *)&v14->szPname[12];
          v40 = *(_OWORD *)&v14->szPname[20];
          v41 = *(_OWORD *)&v14->szPname[28];
        }
        operator delete(v14);
      }
      else
      {
        DevCapsW = 1;
      }
    }
    else
    {
      DevCapsW = SpwaveOutGetDevCapsW(v11, &v42, v12);
    }
    v16 = *((_DWORD *)this + 20);
    if ( DevCapsW )
    {
      v17 = "input";
      if ( !v16 )
        v17 = "output";
      DoTraceMessage(4, "Cannot open audio %s device %u. Error = %X. Ignored", v17, v11, DevCapsW);
    }
    else
    {
      szPname = v42.szPname;
      if ( v16 )
        szPname = &Src[4];
      if ( v4 == 1 )
        goto LABEL_44;
      if ( !v27 )
        goto LABEL_43;
      v19 = v43;
      do
      {
        v20 = *(unsigned __int16 *)((char *)v19 + (char *)szPname - (char *)v43);
        v21 = *v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( !v21 )
LABEL_44:
        v22 = 1;
      else
LABEL_43:
        v22 = 0;
      v31 = 0;
      v23 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\TokenEnums\\MMAudioIn\\";
      if ( !v16 )
        v23 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioOutput\\TokenEnums\\MMAudioOut\\";
      CSpDynamicString::AppendHR((CSpDynamicString *)&v31, v23);
      CSpDynamicString::AppendHR((CSpDynamicString *)&v31, szPname);
      v33 = 0;
      Instance = ((__int64 (__fastcall *)(struct ISpDataKey *, WCHAR *, __int64 *))v34->lpVtbl->CreateKey)(
                   v34,
                   szPname,
                   &v33);
      ppv = 0;
      if ( Instance >= 0 )
      {
        Instance = CoCreateInstance(
                     &CLSID_SpObjectToken,
                     0,
                     0x17u,
                     &GUID_b8aab0cf_346f_49d8_9499_c8b03f161d51,
                     (LPVOID *)&ppv);
        if ( Instance >= 0 )
        {
          v24 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput";
          if ( !*((_DWORD *)this + 20) )
            v24 = L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore\\AudioOutput";
          Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const unsigned __int16 *, __int64, __int64))(*(_QWORD *)ppv + 200LL))(
                       ppv,
                       v24,
                       v31,
                       v33);
          if ( Instance >= 0 )
            Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, WCHAR *))(*(_QWORD *)ppv + 40LL))(
                         ppv,
                         0,
                         szPname);
        }
      }
      lpsz = 0;
      if ( Instance >= 0 )
      {
        v25 = &CLSID_SpMMAudioIn;
        if ( !*((_DWORD *)this + 20) )
          v25 = &CLSID_SpMMAudioOut;
        Instance = StringFromCLSID(v25, &lpsz);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const unsigned __int16 *, LPOLESTR))(*(_QWORD *)ppv + 40LL))(
                       ppv,
                       L"CLSID",
                       lpsz);
          if ( Instance >= 0 )
            Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const wchar_t *, WCHAR *))(*(_QWORD *)ppv + 40LL))(
                         ppv,
                         L"DeviceName",
                         szPname);
        }
      }
      v30 = 0;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(unsigned __int16 *, const WCHAR *, __int64 *))(*(_QWORD *)ppv + 80LL))(
                     ppv,
                     L"Attributes",
                     &v30);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v30 + 40LL))(
                       v30,
                       L"Vendor",
                       L"Microsoft");
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v30 + 40LL))(
                         v30,
                         L"Technology",
                         L"MMSys");
            if ( Instance >= 0 )
            {
              v36 = ppv;
              Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(*(_QWORD *)*v2 + 80LL))(
                           *v2,
                           1,
                           &v36);
              if ( Instance >= 0 && !v29 && v22 )
                (*(void (__fastcall **)(unsigned __int16 *, const wchar_t **))(*(_QWORD *)ppv + 128LL))(ppv, &v29);
            }
          }
        }
      }
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v30);
      SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpsz);
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v33);
      SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v31);
      if ( Instance )
      {
        DoTraceMessage(
          4,
          "Failed to create audio device (Name=%S, Id=%S), hr=0x%X. Ignored the device.",
          szPname,
          szPname,
          Instance);
        Instance = 0;
        ++v11;
        goto LABEL_69;
      }
    }
    ++v11;
LABEL_69:
    v10 = v29;
  }
  if ( !v10 )
    goto LABEL_72;
LABEL_73:
  if ( Instance >= 0 && v10 )
  {
    DoTraceMessage(16, "Default MMSYS audio device token id is %S", v10);
    (*(void (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v2 + 104LL))(*v2, v29);
  }
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v35);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v29);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v34);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800bd214  push    rbp
0x1800bd216  push    rbx
0x1800bd217  push    rsi
0x1800bd218  push    rdi
0x1800bd219  push    r12
0x1800bd21b  push    r13
0x1800bd21d  push    r14
0x1800bd21f  push    r15
0x1800bd221  lea     rbp, [rsp-258h]
0x1800bd229  sub     rsp, 358h
0x1800bd230  mov     rax, cs:__security_cookie
0x1800bd237  xor     rax, rsp
0x1800bd23a  mov     [rbp+290h+var_50], rax
0x1800bd241  mov     r14, rcx
0x1800bd244  lea     r13, [rcx+58h]
0x1800bd248  mov     [rsp+390h+ppv], r13; ppv
0x1800bd24d  lea     r9, _GUID_06b64f9f_7fda_11d2_b4f2_00c04f797396; riid
0x1800bd254  xor     edx, edx; pUnkOuter
0x1800bd256  lea     r8d, [rdx+17h]; dwClsContext
0x1800bd25a  lea     rcx, CLSID_SpObjectTokenEnum; rclsid
0x1800bd261  call    cs:__imp_CoCreateInstance
0x1800bd267  mov     ebx, eax
0x1800bd269  xor     edi, edi
0x1800bd26b  test    eax, eax
0x1800bd26d  js      short loc_1800BD286
0x1800bd26f  mov     rcx, [r13+0]
0x1800bd273  mov     rax, [rcx]
0x1800bd276  xor     r8d, r8d
0x1800bd279  xor     edx, edx
0x1800bd27b  mov     rax, [rax+48h]
0x1800bd27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd284  mov     ebx, eax
0x1800bd286  mov     r15d, edi
0x1800bd289  lea     rsi, aOutput_0; "output"
0x1800bd290  test    ebx, ebx
0x1800bd292  js      short loc_1800BD2CE
0x1800bd294  cmp     [r14+50h], edi
0x1800bd298  jz      short loc_1800BD2A2
0x1800bd29a  call    cs:__imp_waveInGetNumDevs
0x1800bd2a0  jmp     short loc_1800BD2A8
0x1800bd2a2  call    cs:__imp_waveOutGetNumDevs
0x1800bd2a8  mov     r15d, eax
0x1800bd2ab  lea     r9, aInput; "input"
0x1800bd2b2  cmp     [r14+50h], edi
0x1800bd2b6  cmovz   r9, rsi
0x1800bd2ba  mov     r8d, eax
0x1800bd2bd  lea     rdx, aEnumerateUSMms; "Enumerate %u %s MMSYS audio devices ava"...
0x1800bd2c4  mov     ecx, 10h; int
0x1800bd2c9  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800bd2ce  xor     edx, edx; Val
0x1800bd2d0  mov     r8d, 20Ah; Size
0x1800bd2d6  lea     rcx, [rbp+290h+var_260]; void *
0x1800bd2da  call    memset_0
0x1800bd2df  mov     [rsp+390h+var_360], dil
0x1800bd2e4  test    ebx, ebx
0x1800bd2e6  js      short loc_1800BD31D
0x1800bd2e8  cmp     r15d, 1
0x1800bd2ec  jbe     short loc_1800BD31D
0x1800bd2ee  mov     [rsp+390h+var_360], 1
0x1800bd2f3  lea     rdx, [rbp+290h+var_260]; unsigned __int16 *
0x1800bd2f7  mov     rcx, r14; this
0x1800bd2fa  call    ?GetDefaultDeviceLegacy@CMMAudioEnum@@AEAAJPEAGK@Z; CMMAudioEnum::GetDefaultDeviceLegacy(ushort *,ulong)
0x1800bd2ff  mov     ebx, eax
0x1800bd301  test    eax, eax
0x1800bd303  jns     short loc_1800BD31D
0x1800bd305  lea     rdx, aCannotDetermin; "Cannot determine the current default au"...
0x1800bd30c  mov     ecx, 4; int
0x1800bd311  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800bd316  mov     ebx, edi
0x1800bd318  mov     [rsp+390h+var_360], dil
0x1800bd31d  mov     [rsp+390h+var_328], rdi
0x1800bd322  lea     rax, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd329  test    ebx, ebx
0x1800bd32b  js      short loc_1800BD39C
0x1800bd32d  cmp     r15d, 1
0x1800bd331  jb      short loc_1800BD39C
0x1800bd333  mov     [rsp+390h+var_358], rdi
0x1800bd338  lea     rdx, aHkeyLocalMachi_9; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd33f  cmp     [r14+50h], edi
0x1800bd343  cmovz   rdx, rax
0x1800bd347  lea     rcx, [rsp+390h+var_358]
0x1800bd34c  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800bd351  test    rax, rax
0x1800bd354  jnz     short loc_1800BD35D
0x1800bd356  mov     ebx, 8007000Eh
0x1800bd35b  jmp     short loc_1800BD392
0x1800bd35d  lea     rcx, [rsp+390h+var_358]; this
0x1800bd362  call    ?Length@CSpDynamicString@@QEBAIXZ; CSpDynamicString::Length(void)
0x1800bd367  lea     edx, [rax-1]; unsigned int
0x1800bd36a  lea     rcx, [rsp+390h+var_358]; this
0x1800bd36f  call    ?TrimToSize@CSpDynamicString@@QEAAXK@Z; CSpDynamicString::TrimToSize(ulong)
0x1800bd374  lea     r9, [rsp+390h+var_328]; struct ISpDataKey **
0x1800bd379  mov     r8d, 1; int
0x1800bd37f  mov     rdx, [rsp+390h+var_358]; unsigned __int16 *
0x1800bd384  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800bd38b  call    ?SpSzRegPathToDataKey@@YAJPEAUHKEY__@@PEBGHPEAPEAUISpDataKey@@@Z; SpSzRegPathToDataKey(HKEY__ *,ushort const *,int,ISpDataKey * *)
0x1800bd390  mov     ebx, eax
0x1800bd392  lea     rcx, [rsp+390h+var_358]; this
0x1800bd397  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800bd39c  mov     r8, rdi
0x1800bd39f  mov     [rsp+390h+var_350], rdi
0x1800bd3a4  mov     [rsp+390h+var_320], rdi
0x1800bd3a9  mov     r12d, edi
0x1800bd3ac  test    ebx, ebx
0x1800bd3ae  js      loc_1800BD786
0x1800bd3b4  cmp     r12d, r15d
0x1800bd3b7  jnb     loc_1800BD781
0x1800bd3bd  xor     edx, edx; Val
0x1800bd3bf  lea     r8d, [rdx+50h]; Size
0x1800bd3c3  lea     rcx, [rbp+290h+Src]; void *
0x1800bd3c7  call    memset_0
0x1800bd3cc  xor     edx, edx; Val
0x1800bd3ce  lea     r8d, [rdx+54h]; Size
0x1800bd3d2  lea     rcx, [rbp+290h+var_2C0]; void *
0x1800bd3d6  call    memset_0
0x1800bd3db  cmp     [r14+50h], edi
0x1800bd3df  jz      short loc_1800BD44C
0x1800bd3e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bd3e8  mov     ecx, 54h ; 'T'; unsigned __int64
0x1800bd3ed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bd3f2  mov     rdi, rax
0x1800bd3f5  test    rax, rax
0x1800bd3f8  jz      short loc_1800BD443
0x1800bd3fa  mov     ecx, r12d; uDeviceID
0x1800bd3fd  mov     r8d, 50h ; 'P'; cbwic
0x1800bd403  mov     rdx, rax; pwic
0x1800bd406  call    cs:__imp_waveInGetDevCapsW
0x1800bd40c  mov     esi, eax
0x1800bd40e  test    eax, eax
0x1800bd410  jnz     short loc_1800BD439
0x1800bd412  movups  xmm0, xmmword ptr [rdi]
0x1800bd415  movaps  xmmword ptr [rbp+290h+Src], xmm0
0x1800bd419  movups  xmm1, xmmword ptr [rdi+10h]
0x1800bd41d  movaps  [rbp+290h+var_300], xmm1
0x1800bd421  movups  xmm0, xmmword ptr [rdi+20h]
0x1800bd425  movaps  [rbp+290h+var_2F0], xmm0
0x1800bd429  movups  xmm1, xmmword ptr [rdi+30h]
0x1800bd42d  movaps  [rbp+290h+var_2E0], xmm1
0x1800bd431  movups  xmm0, xmmword ptr [rdi+40h]
0x1800bd435  movaps  [rbp+290h+var_2D0], xmm0
0x1800bd439  mov     rcx, rdi; Block
0x1800bd43c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bd441  jmp     short loc_1800BD448
0x1800bd443  mov     esi, 1
0x1800bd448  xor     edi, edi
0x1800bd44a  jmp     short loc_1800BD45A
0x1800bd44c  lea     rdx, [rbp+290h+var_2C0]; struct tagWAVEOUTCAPSW *
0x1800bd450  mov     ecx, r12d; uDeviceID
0x1800bd453  call    ?SpwaveOutGetDevCapsW@@YAIIPEAUtagWAVEOUTCAPSW@@I@Z; SpwaveOutGetDevCapsW(uint,tagWAVEOUTCAPSW *,uint)
0x1800bd458  mov     esi, eax
0x1800bd45a  mov     r9d, [r14+50h]
0x1800bd45e  test    esi, esi
0x1800bd460  jz      short loc_1800BD494
0x1800bd462  lea     r8, aInput; "input"
0x1800bd469  test    r9d, r9d
0x1800bd46c  lea     rax, aOutput_0; "output"
0x1800bd473  cmovz   r8, rax
0x1800bd477  mov     dword ptr [rsp+390h+ppv], esi
0x1800bd47b  mov     r9d, r12d
0x1800bd47e  lea     rdx, aCannotOpenAudi; "Cannot open audio %s device %u. Error ="...
0x1800bd485  mov     ecx, 4; int
0x1800bd48a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800bd48f  jmp     loc_1800BD775
0x1800bd494  lea     rdi, [rbp+290h+var_2C0.szPname]
0x1800bd498  lea     rax, [rbp+290h+Src+8]
0x1800bd49c  test    r9d, r9d
0x1800bd49f  cmovnz  rdi, rax
0x1800bd4a3  cmp     r15d, 1
0x1800bd4a7  jz      short loc_1800BD4D6
0x1800bd4a9  cmp     [rsp+390h+var_360], 0
0x1800bd4ae  jz      short loc_1800BD4D2
0x1800bd4b0  lea     rax, [rbp+290h+var_260]
0x1800bd4b4  mov     r8, rdi
0x1800bd4b7  sub     r8, rax
0x1800bd4ba  movzx   edx, word ptr [rax]
0x1800bd4bd  movzx   ecx, word ptr [rax+r8]
0x1800bd4c2  sub     edx, ecx
0x1800bd4c4  jnz     short loc_1800BD4CE
0x1800bd4c6  add     rax, 2
0x1800bd4ca  test    ecx, ecx
0x1800bd4cc  jnz     short loc_1800BD4BA
0x1800bd4ce  test    edx, edx
0x1800bd4d0  jz      short loc_1800BD4D6
0x1800bd4d2  xor     esi, esi
0x1800bd4d4  jmp     short loc_1800BD4DB
0x1800bd4d6  mov     esi, 1
0x1800bd4db  test    ebx, ebx
0x1800bd4dd  js      loc_1800BD745
0x1800bd4e3  mov     [rsp+390h+var_340], 0
0x1800bd4ec  lea     rdx, aHkeyLocalMachi_9; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd4f3  test    r9d, r9d
0x1800bd4f6  lea     rax, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd4fd  cmovz   rdx, rax; Src
0x1800bd501  lea     rcx, [rsp+390h+var_340]; this
0x1800bd506  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x1800bd50b  mov     rdx, rdi; Src
0x1800bd50e  lea     rcx, [rsp+390h+var_340]; this
0x1800bd513  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x1800bd518  mov     [rsp+390h+var_330], 0
0x1800bd521  mov     rcx, [rsp+390h+var_328]
0x1800bd526  mov     rax, [rcx]
0x1800bd529  lea     r8, [rsp+390h+var_330]
0x1800bd52e  mov     rdx, rdi
0x1800bd531  mov     rax, [rax+50h]
0x1800bd535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd53a  mov     ebx, eax
0x1800bd53c  mov     [rsp+390h+var_358], 0
0x1800bd545  test    eax, eax
0x1800bd547  js      short loc_1800BD5C6
0x1800bd549  lea     rax, [rsp+390h+var_358]
0x1800bd54e  mov     [rsp+390h+ppv], rax; ppv
0x1800bd553  lea     r9, _GUID_b8aab0cf_346f_49d8_9499_c8b03f161d51; riid
0x1800bd55a  xor     edx, edx; pUnkOuter
0x1800bd55c  lea     r8d, [rdx+17h]; dwClsContext
0x1800bd560  lea     rcx, CLSID_SpObjectToken; rclsid
0x1800bd567  call    cs:__imp_CoCreateInstance
0x1800bd56d  mov     ebx, eax
0x1800bd56f  test    eax, eax
0x1800bd571  js      short loc_1800BD5C6
0x1800bd573  mov     rcx, [rsp+390h+var_358]
0x1800bd578  mov     rax, [rcx]
0x1800bd57b  lea     r8, aHkeyLocalMachi_12; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd582  lea     rdx, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800bd589  cmp     dword ptr [r14+50h], 0
0x1800bd58e  cmovz   rdx, r8
0x1800bd592  mov     r9, [rsp+390h+var_330]
0x1800bd597  mov     r8, [rsp+390h+var_340]
0x1800bd59c  mov     rax, [rax+0C8h]
0x1800bd5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd5a8  mov     ebx, eax
0x1800bd5aa  test    eax, eax
0x1800bd5ac  js      short loc_1800BD5C6
0x1800bd5ae  mov     rcx, [rsp+390h+var_358]
0x1800bd5b3  mov     rax, [rcx]
0x1800bd5b6  mov     r8, rdi
0x1800bd5b9  xor     edx, edx
0x1800bd5bb  mov     rax, [rax+28h]
0x1800bd5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd5c4  mov     ebx, eax
0x1800bd5c6  mov     [rsp+390h+lpsz], 0
0x1800bd5cf  test    ebx, ebx
0x1800bd5d1  js      short loc_1800BD63B
0x1800bd5d3  lea     rax, CLSID_SpMMAudioOut
0x1800bd5da  lea     rcx, CLSID_SpMMAudioIn
0x1800bd5e1  cmp     dword ptr [r14+50h], 0
0x1800bd5e6  cmovz   rcx, rax; rclsid
0x1800bd5ea  lea     rdx, [rsp+390h+lpsz]; lplpsz
0x1800bd5ef  call    cs:__imp_StringFromCLSID
0x1800bd5f5  mov     ebx, eax
0x1800bd5f7  test    eax, eax
0x1800bd5f9  js      short loc_1800BD63B
0x1800bd5fb  mov     rcx, [rsp+390h+var_358]
0x1800bd600  mov     rax, [rcx]
0x1800bd603  mov     r8, [rsp+390h+lpsz]
0x1800bd608  lea     rdx, aClsid_0; "CLSID"
0x1800bd60f  mov     rax, [rax+28h]
0x1800bd613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd618  mov     ebx, eax
0x1800bd61a  test    eax, eax
0x1800bd61c  js      short loc_1800BD63B
0x1800bd61e  mov     rcx, [rsp+390h+var_358]
0x1800bd623  mov     rax, [rcx]
0x1800bd626  mov     r8, rdi
0x1800bd629  lea     rdx, aDevicename; "DeviceName"
0x1800bd630  mov     rax, [rax+28h]
0x1800bd634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd639  mov     ebx, eax
0x1800bd63b  mov     [rsp+390h+var_348], 0
0x1800bd644  test    ebx, ebx
0x1800bd646  js      loc_1800BD70D
0x1800bd64c  mov     rcx, [rsp+390h+var_358]
0x1800bd651  mov     rax, [rcx]
0x1800bd654  lea     r8, [rsp+390h+var_348]
0x1800bd659  lea     rdx, aAttributes_0; "Attributes"
0x1800bd660  mov     rax, [rax+50h]
0x1800bd664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd669  mov     ebx, eax
0x1800bd66b  test    eax, eax
0x1800bd66d  js      loc_1800BD70D
0x1800bd673  mov     rcx, [rsp+390h+var_348]
0x1800bd678  mov     rax, [rcx]
0x1800bd67b  lea     r8, aMicrosoft; "Microsoft"
0x1800bd682  lea     rdx, aVendor; "Vendor"
0x1800bd689  mov     rax, [rax+28h]
0x1800bd68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd692  mov     ebx, eax
0x1800bd694  test    eax, eax
0x1800bd696  js      short loc_1800BD70D
0x1800bd698  mov     rcx, [rsp+390h+var_348]
0x1800bd69d  mov     rax, [rcx]
0x1800bd6a0  lea     r8, aMmsys; "MMSys"
0x1800bd6a7  lea     rdx, aTechnology; "Technology"
0x1800bd6ae  mov     rax, [rax+28h]
0x1800bd6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd6b7  mov     ebx, eax
0x1800bd6b9  test    eax, eax
0x1800bd6bb  js      short loc_1800BD70D
0x1800bd6bd  mov     rax, [rsp+390h+var_358]
0x1800bd6c2  mov     [rsp+390h+var_318], rax
0x1800bd6c7  mov     rcx, [r13+0]
  ... truncated ...
```
