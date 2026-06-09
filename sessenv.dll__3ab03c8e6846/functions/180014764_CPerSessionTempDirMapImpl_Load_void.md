# CPerSessionTempDirMapImpl::Load(void)

- ea: `0x180014764`
- end: `0x180014aae`
- name: `?Load@CPerSessionTempDirMapImpl@@QEAAJXZ`
- size: `842`
- prototype: `__int64 __fastcall(CPerSessionTempDirMapImpl *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026f14`

## callees

- `0x180003f30`
- `0x180004f50`
- `0x180005190`
- `0x180012be0`
- `0x180012d7c`
- `0x180014764`
- `0x180014ab4`
- `0x180017b30`
- `0x18001a280`
- `0x18001acfc`
- `0x1800274ac`
- `0x180027ba4`
- `0x180027f18`
- `0x18005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800148f8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800148f8`

## string_xrefs

- `0x1800149f5`: `PerSessionTempDirs`
- `0x180014a40`: `IPerSessionTempDir::GetInstanceOfPerSessionTempDir failed: 0x%x in %s`
- `0x1800147b9`: `%s\PerSessionTempDirs`
- `0x1800147fb`: `CPerSessionTempDirMapImpl::Load`
- `0x180014a61`: `CPerSessionTempDirMapImpl::Load`
- `0x180014851`: `RegBase.OpenKey failed: 0x%x in %s`
- `0x180014a57`: `RegLuid.OpenKey failed: 0x%x in %s`
- `0x180014a34`: `ptrTempDir->Load failed: 0x%x in %s`
- `0x180014a19`: `RegBase.RecurseDeleteKey failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CPerSessionTempDirMapImpl::Load(CPerSessionTempDirMapImpl *this)
{
  int v2; // eax
  signed int v3; // edi
  int v4; // eax
  int NextSubKey; // eax
  wchar_t *v6; // rbx
  int v7; // eax
  __int64 v8; // rsi
  wchar_t *v9; // rax
  __int64 v10; // r9
  wchar_t *v11; // rdi
  wchar_t *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int InstanceOfPerSessionTempDir; // eax
  struct IPerSessionTempDir *v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  const char *v22; // rdx
  const unsigned __int16 *v24; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v25; // [rsp+20h] [rbp-E0h]
  unsigned int v26; // [rsp+30h] [rbp-D0h] BYREF
  struct IPerSessionTempDir *v27; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-C0h] BYREF
  struct _LUID v29; // [rsp+48h] [rbp-B8h]
  _QWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  _QWORD v34[2]; // [rsp+78h] [rbp-88h] BYREF
  int v35; // [rsp+88h] [rbp-78h]
  HKEY v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  unsigned __int16 v38[72]; // [rsp+A0h] [rbp-60h] BYREF

  v27 = 0;
  v34[1] = 0;
  v34[0] = &CRegistry::`vftable';
  v35 = 0;
  v36 = 0;
  v37 = -1;
  Str = 0;
  v26 = 0;
  v2 = StringCchPrintfW(v38, 0x45u, L"%s\\PerSessionTempDirs", L"System\\CurrentControlSet\\Control\\Terminal Server");
  v3 = v2;
  if ( v2 < 0 )
  {
    _DbgPrintMessage(8, "StringCbPrintf failed: 0x%x in %s", (unsigned int)v2, "CPerSessionTempDirMapImpl::Load");
    goto LABEL_37;
  }
  v4 = CRegistry::OpenKey((CRegistry *)v34, HKEY_LOCAL_MACHINE, v38, 0x20019u, v24);
  v3 = v4;
  if ( v4 == 2 )
  {
    v3 = 0;
  }
  else
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_9;
    LODWORD(v37) = 0;
    NextSubKey = CRegistry::GetNextSubKey((CRegistry *)v34, &Str, &v26);
    v3 = NextSubKey;
    if ( NextSubKey > 0 )
      v3 = (unsigned __int16)NextSubKey | 0x80070000;
    if ( v3 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RegBase.GetFirstSubKey failed: 0x%x in %s",
        (unsigned int)v3,
        "CPerSessionTempDirMapImpl::Load");
      goto LABEL_37;
    }
    do
    {
      v30[0] = &CRegistry::`vftable';
      v6 = Str;
      v30[1] = 0;
      v31 = 0;
      v32 = 0;
      v33 = -1;
      v7 = CRegistry::OpenKey((CRegistry *)v30, v36, Str, 0x20019u, v25);
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 < 0 )
      {
        v22 = "RegLuid.OpenKey failed: 0x%x in %s";
LABEL_35:
        _DbgPrintMessage(8, v22, (unsigned int)v3, "CPerSessionTempDirMapImpl::Load");
LABEL_36:
        CRegistry::~CRegistry((CRegistry *)v30);
        goto LABEL_37;
      }
      v8 = v26;
      v9 = wcschr(v6, 0x2Eu);
      v11 = v9;
      if ( !v9 || (v12 = &v6[v8 - 2], v9 >= v12) )
      {
        v3 = -2147024809;
        v22 = "StringToLUID failed: 0x%x in %s";
        goto LABEL_35;
      }
      *v9 = 0;
      v29.HighPart = o__wtol_0(v6, 0, v12, v10);
      v29.LowPart = o__wtol_0(v11 + 1, v13, v14, v15);
      SmartPtr<CPerSessionTempDirItem>::operator=(&v27, 0);
      InstanceOfPerSessionTempDir = IPerSessionTempDir::GetInstanceOfPerSessionTempDir(&v27);
      v3 = InstanceOfPerSessionTempDir;
      if ( InstanceOfPerSessionTempDir < 0 )
      {
        _DbgPrintMessage(
          8,
          "IPerSessionTempDir::GetInstanceOfPerSessionTempDir failed: 0x%x in %s",
          (unsigned int)InstanceOfPerSessionTempDir,
          "CPerSessionTempDirMapImpl::Load");
        goto LABEL_36;
      }
      v17 = v27;
      v18 = (*(__int64 (__fastcall **)(struct IPerSessionTempDir *, _QWORD *))(*(_QWORD *)v27 + 48LL))(v27, v30);
      v3 = v18;
      if ( v18 < 0 )
      {
        _DbgPrintMessage(8, "ptrTempDir->Load failed: 0x%x in %s", (unsigned int)v18, "CPerSessionTempDirMapImpl::Load");
        goto LABEL_36;
      }
      v19 = CPerSessionTempDirMapImpl::Insert(this, v29, v17);
      v3 = v19;
      if ( v19 < 0 )
      {
        _DbgPrintMessage(8, "Insert failed: 0x%x in %s", (unsigned int)v19, "CPerSessionTempDirMapImpl::Load");
        goto LABEL_36;
      }
      CRegistry::~CRegistry((CRegistry *)v30);
    }
    while ( !CRegistry::GetNextSubKey((CRegistry *)v34, &Str, &v26) );
    v20 = CRegistry::OpenKey(
            (CRegistry *)v34,
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server",
            0x20006u,
            v25);
    v3 = v20;
    if ( v20 > 0 )
      v3 = (unsigned __int16)v20 | 0x80070000;
    if ( v3 < 0 )
    {
LABEL_9:
      _DbgPrintMessage(8, "RegBase.OpenKey failed: 0x%x in %s", (unsigned int)v3, "CPerSessionTempDirMapImpl::Load");
    }
    else
    {
      v21 = CRegistry::RecurseDeleteKey((CRegistry *)v34, L"PerSessionTempDirs");
      v3 = v21;
      if ( v21 > 0 )
        v3 = (unsigned __int16)v21 | 0x80070000;
      if ( v3 < 0 )
        _DbgPrintMessage(
          8,
          "RegBase.RecurseDeleteKey failed: 0x%x in %s",
          (unsigned int)v3,
          "CPerSessionTempDirMapImpl::Load");
    }
  }
LABEL_37:
  CRegistry::~CRegistry((CRegistry *)v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014764  push    rbp
0x180014766  push    rbx
0x180014767  push    rsi
0x180014768  push    rdi
0x180014769  push    r12
0x18001476b  push    r14
0x18001476d  lea     rbp, [rsp-48h]
0x180014772  sub     rsp, 148h
0x180014779  mov     rax, cs:__security_cookie
0x180014780  xor     rax, rsp
0x180014783  mov     [rbp+70h+var_40], rax
0x180014787  mov     r14, rcx
0x18001478a  mov     [rsp+170h+var_138], 0
0x180014793  lea     rbx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18001479a  mov     [rbp+70h+var_F0], 0
0x1800147a2  lea     rcx, [rbp+70h+var_D0]; unsigned __int16 *
0x1800147a6  mov     [rsp+170h+var_F8], rbx
0x1800147ab  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800147b2  mov     [rbp+70h+var_E8], 0
0x1800147b9  lea     r8, aSPersessiontem; "%s\\PerSessionTempDirs"
0x1800147c0  mov     [rbp+70h+var_E0], 0
0x1800147c8  mov     edx, 45h ; 'E'; unsigned __int64
0x1800147cd  mov     [rbp+70h+var_D8], 0FFFFFFFFFFFFFFFFh
0x1800147d5  mov     [rsp+170h+Str], 0
0x1800147de  mov     [rsp+170h+var_140], 0
0x1800147e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800147eb  mov     edi, eax
0x1800147ed  test    eax, eax
0x1800147ef  jns     short loc_180014811
0x1800147f1  mov     r8d, eax
0x1800147f4  lea     rdx, aStringcbprintf; "StringCbPrintf failed: 0x%x in %s"
0x1800147fb  lea     r9, aCpersessiontem_6; "CPerSessionTempDirMapImpl::Load"
0x180014802  mov     ecx, 8; int
0x180014807  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001480c  jmp     loc_180014A7C
0x180014811  mov     r9d, 20019h; unsigned int
0x180014817  lea     r8, [rbp+70h+var_D0]; unsigned __int16 *
0x18001481b  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180014822  lea     rcx, [rsp+170h+var_F8]; this
0x180014827  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18001482c  mov     edi, eax
0x18001482e  cmp     eax, 2
0x180014831  jnz     short loc_18001483A
0x180014833  xor     edi, edi
0x180014835  jmp     loc_180014A7C
0x18001483a  mov     r12d, 80070000h
0x180014840  test    eax, eax
0x180014842  jle     short loc_18001484A
0x180014844  movzx   edi, ax
0x180014847  or      edi, r12d
0x18001484a  test    edi, edi
0x18001484c  jns     short loc_18001485A
0x18001484e  mov     r8d, edi
0x180014851  lea     rdx, aRegbaseOpenkey; "RegBase.OpenKey failed: 0x%x in %s"
0x180014858  jmp     short loc_1800147FB
0x18001485a  lea     r8, [rsp+170h+var_140]; unsigned int *
0x18001485f  mov     dword ptr [rbp+70h+var_D8], 0
0x180014866  lea     rdx, [rsp+170h+Str]; unsigned __int16 **
0x18001486b  lea     rcx, [rsp+170h+var_F8]; this
0x180014870  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x180014875  mov     edi, eax
0x180014877  test    eax, eax
0x180014879  jle     short loc_180014881
0x18001487b  movzx   edi, ax
0x18001487e  or      edi, r12d
0x180014881  test    edi, edi
0x180014883  jns     short loc_180014894
0x180014885  mov     r8d, edi
0x180014888  lea     rdx, aRegbaseGetfirs; "RegBase.GetFirstSubKey failed: 0x%x in "...
0x18001488f  jmp     loc_1800147FB
0x180014894  mov     rdx, [rbp+70h+var_E0]; HKEY
0x180014898  lea     rcx, [rsp+170h+var_120]; this
0x18001489d  mov     [rsp+170h+var_120], rbx
0x1800148a2  mov     r9d, 20019h; unsigned int
0x1800148a8  mov     rbx, [rsp+170h+Str]
0x1800148ad  mov     r8, rbx; unsigned __int16 *
0x1800148b0  mov     [rsp+170h+var_118], 0
0x1800148b9  mov     [rsp+170h+var_110], 0
0x1800148c1  mov     [rsp+170h+var_108], 0
0x1800148ca  mov     [rsp+170h+var_100], 0FFFFFFFFFFFFFFFFh
0x1800148d3  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800148d8  mov     edi, eax
0x1800148da  test    eax, eax
0x1800148dc  jle     short loc_1800148E4
0x1800148de  movzx   edi, ax
0x1800148e1  or      edi, r12d
0x1800148e4  test    edi, edi
0x1800148e6  js      loc_180014A57
0x1800148ec  mov     esi, [rsp+170h+var_140]
0x1800148f0  mov     edx, 2Eh ; '.'; Ch
0x1800148f5  mov     rcx, rbx; Str
0x1800148f8  call    cs:__imp_wcschr
0x1800148fe  mov     rdi, rax
0x180014901  test    rax, rax
0x180014904  jz      loc_180014A49
0x18001490a  lea     r8, [rsi-2]
0x18001490e  lea     r8, [rbx+r8*2]
0x180014912  cmp     rax, r8
0x180014915  jnb     loc_180014A49
0x18001491b  xor     edx, edx
0x18001491d  mov     rcx, rbx
0x180014920  mov     [rax], dx
0x180014923  call    _o__wtol_0
0x180014928  lea     rcx, [rdi+2]
0x18001492c  mov     [rsp+170h+var_128.HighPart], eax
0x180014930  call    _o__wtol_0
0x180014935  xor     edx, edx
0x180014937  mov     [rsp+170h+var_128.LowPart], eax
0x18001493b  lea     rcx, [rsp+170h+var_138]
0x180014940  call    ??4?$SmartPtr@VCPerSessionTempDirItem@@@@QEAAAEAV0@PEAVCPerSessionTempDirItem@@@Z; SmartPtr<CPerSessionTempDirItem>::operator=(CPerSessionTempDirItem *)
0x180014945  lea     rcx, [rsp+170h+var_138]; struct IPerSessionTempDir **
0x18001494a  call    ?GetInstanceOfPerSessionTempDir@IPerSessionTempDir@@SAJPEAPEAV1@@Z; IPerSessionTempDir::GetInstanceOfPerSessionTempDir(IPerSessionTempDir * *)
0x18001494f  mov     edi, eax
0x180014951  test    eax, eax
0x180014953  js      loc_180014A3D
0x180014959  mov     rbx, [rsp+170h+var_138]
0x18001495e  lea     rdx, [rsp+170h+var_120]
0x180014963  mov     rcx, rbx
0x180014966  mov     rax, [rbx]
0x180014969  mov     rax, [rax+30h]
0x18001496d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014972  mov     edi, eax
0x180014974  test    eax, eax
0x180014976  js      loc_180014A31
0x18001497c  mov     rdx, qword ptr [rsp+170h+var_128.LowPart]; struct _LUID
0x180014981  mov     r8, rbx; struct IPerSessionTempDir *
0x180014984  mov     rcx, r14; this
0x180014987  call    ?Insert@CPerSessionTempDirMapImpl@@QEAAJU_LUID@@PEAVIPerSessionTempDir@@@Z; CPerSessionTempDirMapImpl::Insert(_LUID,IPerSessionTempDir *)
0x18001498c  mov     edi, eax
0x18001498e  test    eax, eax
0x180014990  js      loc_180014A25
0x180014996  lea     rcx, [rsp+170h+var_120]; this
0x18001499b  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800149a0  lea     r8, [rsp+170h+var_140]; unsigned int *
0x1800149a5  lea     rdx, [rsp+170h+Str]; unsigned __int16 **
0x1800149aa  lea     rcx, [rsp+170h+var_F8]; this
0x1800149af  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x1800149b4  lea     rbx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800149bb  test    eax, eax
0x1800149bd  jz      loc_180014894
0x1800149c3  mov     r9d, 20006h; unsigned int
0x1800149c9  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800149d0  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800149d7  lea     rcx, [rsp+170h+var_F8]; this
0x1800149dc  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800149e1  mov     edi, eax
0x1800149e3  test    eax, eax
0x1800149e5  jle     short loc_1800149ED
0x1800149e7  movzx   edi, ax
0x1800149ea  or      edi, r12d
0x1800149ed  test    edi, edi
0x1800149ef  js      loc_18001484E
0x1800149f5  lea     rdx, aPersessiontemp_2; "PerSessionTempDirs"
0x1800149fc  lea     rcx, [rsp+170h+var_F8]; this
0x180014a01  call    ?RecurseDeleteKey@CRegistry@@QEAAKPEBG@Z; CRegistry::RecurseDeleteKey(ushort const *)
0x180014a06  mov     edi, eax
0x180014a08  test    eax, eax
0x180014a0a  jle     short loc_180014A12
0x180014a0c  movzx   edi, ax
0x180014a0f  or      edi, r12d
0x180014a12  test    edi, edi
0x180014a14  jns     short loc_180014A7C
0x180014a16  mov     r8d, edi
0x180014a19  lea     rdx, aRegbaseRecurse; "RegBase.RecurseDeleteKey failed: 0x%x i"...
0x180014a20  jmp     loc_1800147FB
0x180014a25  mov     r8d, eax
0x180014a28  lea     rdx, aInsertFailed0x; "Insert failed: 0x%x in %s"
0x180014a2f  jmp     short loc_180014A61
0x180014a31  mov     r8d, eax
0x180014a34  lea     rdx, aPtrtempdirLoad; "ptrTempDir->Load failed: 0x%x in %s"
0x180014a3b  jmp     short loc_180014A61
0x180014a3d  mov     r8d, eax
0x180014a40  lea     rdx, aIpersessiontem; "IPerSessionTempDir::GetInstanceOfPerSes"...
0x180014a47  jmp     short loc_180014A61
0x180014a49  mov     edi, 80070057h
0x180014a4e  lea     rdx, aStringtoluidFa; "StringToLUID failed: 0x%x in %s"
0x180014a55  jmp     short loc_180014A5E
0x180014a57  lea     rdx, aRegluidOpenkey; "RegLuid.OpenKey failed: 0x%x in %s"
0x180014a5e  mov     r8d, edi
0x180014a61  lea     r9, aCpersessiontem_6; "CPerSessionTempDirMapImpl::Load"
0x180014a68  mov     ecx, 8; int
0x180014a6d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014a72  lea     rcx, [rsp+170h+var_120]; this
0x180014a77  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180014a7c  lea     rcx, [rsp+170h+var_F8]; this
0x180014a81  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180014a86  lea     rcx, [rsp+170h+var_138]
0x180014a8b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014a90  mov     eax, edi
0x180014a92  mov     rcx, [rbp+70h+var_40]
0x180014a96  xor     rcx, rsp; StackCookie
0x180014a99  call    __security_check_cookie
0x180014a9e  add     rsp, 148h
0x180014aa5  pop     r14
0x180014aa7  pop     r12
0x180014aa9  pop     rdi
0x180014aaa  pop     rsi
0x180014aab  pop     rbx
0x180014aac  pop     rbp
0x180014aad  retn
```
