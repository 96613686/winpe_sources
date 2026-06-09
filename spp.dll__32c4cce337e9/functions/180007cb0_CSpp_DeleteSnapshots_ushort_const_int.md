# CSpp::DeleteSnapshots(ushort const *,int)

- ea: `0x180007cb0`
- end: `0x180008053`
- name: `?DeleteSnapshots@CSpp@@UEAAJPEBGH@Z`
- size: `931`
- prototype: `int(CSpp *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180007cb0`
- `0x18001b70c`
- `0x180020710`
- `0x1800251cc`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800299c4`
- `0x180035b9a`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007f09`
- `msvcrt!_wcsicmp` at `0x180007f09`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180007e9e`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180007ff4`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180007e9e`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180007ff4`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180007ddb`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180007ddb`

## string_xrefs

- `0x180007d1c`: `CSpp::DeleteSnapshots`

## pseudocode

```c
__int64 __fastcall CSpp::DeleteSnapshots(CSpp *this, const unsigned __int16 *a2, int a3)
{
  __int64 v5; // rdx
  __int16 v6; // ax
  CSpp *v7; // rcx
  bool v8; // sf
  __int64 v9; // rax
  int v10; // ebx
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int IsServerSku; // edx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v19; // [rsp+40h] [rbp-C0h] BYREF
  int UniqueVolumeForPath; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v21; // [rsp+4Ch] [rbp-B4h]
  __int16 v22; // [rsp+4Eh] [rbp-B2h]
  int v23; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  GUID v26; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[8]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v28[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v29; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v30; // [rsp+D8h] [rbp-28h]
  __int128 v31; // [rsp+130h] [rbp+30h] BYREF
  wchar_t String2; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v33[526]; // [rsp+142h] [rbp+42h] BYREF
  wchar_t String1; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v35[526]; // [rsp+352h] [rbp+252h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&UniqueVolumeForPath, "CSpp::DeleteSnapshots", 11787, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v19);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v25);
  v23 = 0;
  String1 = 0;
  v24 = 0;
  v31 = 0;
  memset_0(v35, 0, 0x208u);
  String2 = 0;
  memset_0(v33, 0, 0x208u);
  memset_0(v27, 0, 0x88u);
  UniqueVolumeForPath = SxGetUniqueVolumeForPath(a2, &String1, 0x105u);
  v6 = 11807;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_5;
  v21 = 11807;
  UniqueVolumeForPath = CreateVssBackupComponentsInternal(&v19, v5);
  v6 = 11812;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_5;
  v21 = 11812;
  UniqueVolumeForPath = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v19 + 40))(v19, 0);
  v6 = 11813;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_5;
  v21 = 11813;
  if ( a3 )
  {
    UniqueVolumeForPath = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v19 + 280))(v19, 0xFFFFFFFFLL);
    v8 = UniqueVolumeForPath < 0;
    v6 = 11820;
  }
  else
  {
    IsServerSku = CSpp::_IsServerSku(v7);
    UniqueVolumeForPath = IsServerSku;
    v6 = 11825;
    if ( IsServerSku < 0 )
      goto LABEL_5;
    v21 = 11825;
    UniqueVolumeForPath = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v19 + 280))(v19, IsServerSku != 0 ? 13 : 9);
    v8 = UniqueVolumeForPath < 0;
    v6 = 11834;
  }
  if ( !v8 )
  {
    v21 = v6;
    v9 = *v19;
    v26 = GUID_NULL;
    UniqueVolumeForPath = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64, __int64, __int64 *))(v9 + 344))(
                            v19,
                            &v26,
                            1,
                            3,
                            &v25);
    v6 = 11840;
    if ( UniqueVolumeForPath >= 0 )
    {
      v10 = 0;
      v21 = 11840;
      while ( 1 )
      {
        VssFreeSnapshotPropertiesInternal(v28);
        memset_0(v27, 0, 0x88u);
        v11 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, int *))(*(_QWORD *)v25 + 24LL))(v25, 1, v27, &v23);
        UniqueVolumeForPath = v11;
        if ( v11 < 0 )
        {
          v22 = 11850;
          goto LABEL_25;
        }
        v21 = 11850;
        if ( v11 == 1 )
          break;
        if ( (int)SxGetUniqueVolumeForPath(v30, &String2, 0x105u) >= 0 && !_wcsicmp(&String1, &String2) )
        {
          v12 = *v19;
          v26 = (GUID)v28[0];
          v13 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64, __int64, int *, __int128 *))(v12 + 312))(
                  v19,
                  &v26,
                  3,
                  1,
                  &v24,
                  &v31);
          if ( v13 < 0 )
          {
            Log_SPP_ERROR_SNAPSHOT_DELETION((struct CSxFunctionTracer *)&UniqueVolumeForPath, 0x2E6Cu, v30, v29, v13);
            v10 = 1;
          }
        }
      }
      if ( !v10 )
      {
        UniqueVolumeForPath = 0;
        v21 = 11896;
        goto LABEL_25;
      }
      UniqueVolumeForPath = -2130706165;
      v6 = 11894;
    }
  }
LABEL_5:
  v22 = v6;
LABEL_25:
  VssFreeSnapshotPropertiesInternal(v28);
  memset_0(v27, 0, 0x88u);
  v15 = UniqueVolumeForPath;
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&UniqueVolumeForPath, v16, v17);
  return v15;
}

```

## disassembly

```asm
0x180007cb0  mov     [rsp-8+arg_0], rbx
0x180007cb5  mov     [rsp-8+arg_10], rdi
0x180007cba  push    rbp
0x180007cbb  push    r12
0x180007cbd  push    r15
0x180007cbf  lea     rbp, [rsp-470h]
0x180007cc7  sub     rsp, 570h
0x180007cce  mov     rax, cs:__security_cookie
0x180007cd5  xor     rax, rsp
0x180007cd8  mov     [rbp+480h+var_20], rax
0x180007cdf  mov     ebx, r8d
0x180007ce2  mov     rdi, rdx
0x180007ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cec  lea     rax, WPP_GLOBAL_Control
0x180007cf3  cmp     rcx, rax
0x180007cf6  jz      short loc_180007D16
0x180007cf8  test    dword ptr [rcx+1Ch], 20000000h
0x180007cff  jz      short loc_180007D16
0x180007d01  mov     rcx, [rcx+10h]
0x180007d05  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180007d0c  mov     edx, 0CAh
0x180007d11  call    WPP_SF_
0x180007d16  mov     r15d, 1
0x180007d1c  lea     rdx, aCsppDeletesnap; "CSpp::DeleteSnapshots"
0x180007d23  mov     r9d, r15d; unsigned __int16
0x180007d26  lea     rcx, [rsp+580h+var_538]; this
0x180007d2b  mov     r8d, 2E0Bh; unsigned __int16
0x180007d31  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180007d36  lea     rcx, [rsp+580h+var_540]
0x180007d3b  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180007d40  lea     rcx, [rbp+480h+var_4F8]
0x180007d44  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180007d49  xor     eax, eax
0x180007d4b  mov     [rbp+480h+var_500], 0
0x180007d52  xorps   xmm0, xmm0
0x180007d55  mov     [rbp+480h+String1], ax
0x180007d5c  xor     edx, edx; Val
0x180007d5e  mov     [rbp+480h+var_4FC], 0
0x180007d65  mov     r8d, 208h; Size
0x180007d6b  lea     rcx, [rbp+480h+var_22E]; void *
0x180007d72  movups  [rbp+480h+var_450], xmm0
0x180007d76  call    memset_0
0x180007d7b  xor     eax, eax
0x180007d7d  lea     rcx, [rbp+480h+var_43E]; void *
0x180007d81  xor     edx, edx; Val
0x180007d83  mov     [rbp+480h+String2], ax
0x180007d87  mov     r8d, 208h; Size
0x180007d8d  call    memset_0
0x180007d92  mov     r12d, 88h
0x180007d98  lea     rcx, [rbp+480h+var_4E0]; void *
0x180007d9c  mov     r8d, r12d; Size
0x180007d9f  xor     edx, edx; Val
0x180007da1  call    memset_0
0x180007da6  lea     r8d, [r12+7Dh]; cchBufferLength
0x180007dab  mov     rcx, rdi; unsigned __int16 *
0x180007dae  lea     rdx, [rbp+480h+String1]; lpszVolumeName
0x180007db5  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x180007dba  mov     [rsp+580h+var_538], eax
0x180007dbe  test    eax, eax
0x180007dc0  mov     eax, 2E1Fh
0x180007dc5  jns     short loc_180007DD1
0x180007dc7  mov     [rsp+580h+var_532], ax
0x180007dcc  jmp     loc_180007FF0
0x180007dd1  lea     rcx, [rsp+580h+var_540]
0x180007dd6  mov     [rsp+580h+var_534], ax
0x180007ddb  call    cs:__imp_CreateVssBackupComponentsInternal
0x180007de1  mov     [rsp+580h+var_538], eax
0x180007de5  test    eax, eax
0x180007de7  mov     eax, 2E24h
0x180007dec  js      short loc_180007DC7
0x180007dee  mov     rcx, [rsp+580h+var_540]
0x180007df3  xor     edx, edx
0x180007df5  mov     [rsp+580h+var_534], ax
0x180007dfa  mov     rax, [rcx]
0x180007dfd  mov     rax, [rax+28h]
0x180007e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e06  mov     [rsp+580h+var_538], eax
0x180007e0a  test    eax, eax
0x180007e0c  mov     eax, 2E25h
0x180007e11  js      short loc_180007DC7
0x180007e13  mov     [rsp+580h+var_534], ax
0x180007e18  test    ebx, ebx
0x180007e1a  jz      loc_180007F7A
0x180007e20  mov     rcx, [rsp+580h+var_540]
0x180007e25  or      edx, 0FFFFFFFFh
0x180007e28  mov     rax, [rcx]
0x180007e2b  mov     rax, [rax+118h]
0x180007e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e37  mov     [rsp+580h+var_538], eax
0x180007e3b  test    eax, eax
0x180007e3d  mov     eax, 2E2Ch
0x180007e42  js      short loc_180007DC7
0x180007e44  mov     rcx, [rsp+580h+var_540]
0x180007e49  lea     rdx, [rbp+480h+var_4F8]
0x180007e4d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007e54  mov     [rsp+580h+var_534], ax
0x180007e59  mov     r9d, 3
0x180007e5f  mov     qword ptr [rsp+580h+var_560], rdx
0x180007e64  mov     r8d, r15d
0x180007e67  mov     rax, [rcx]
0x180007e6a  lea     rdx, [rbp+480h+var_4F0]
0x180007e6e  movdqu  [rbp+480h+var_4F0], xmm0
0x180007e73  mov     rax, [rax+158h]
0x180007e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e7f  mov     [rsp+580h+var_538], eax
0x180007e83  test    eax, eax
0x180007e85  mov     eax, 2E40h
0x180007e8a  js      loc_180007DC7
0x180007e90  xor     ebx, ebx
0x180007e92  mov     [rsp+580h+var_534], ax
0x180007e97  lea     edi, [rax+0Ah]
0x180007e9a  lea     rcx, [rbp+480h+var_4D8]
0x180007e9e  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x180007ea4  mov     r8, r12; Size
0x180007ea7  lea     rcx, [rbp+480h+var_4E0]; void *
0x180007eab  xor     edx, edx; Val
0x180007ead  call    memset_0
0x180007eb2  mov     rcx, [rbp+480h+var_4F8]
0x180007eb6  lea     r9, [rbp+480h+var_500]
0x180007eba  lea     r8, [rbp+480h+var_4E0]
0x180007ebe  mov     edx, r15d
0x180007ec1  mov     rax, [rcx]
0x180007ec4  mov     rax, [rax+18h]
0x180007ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ecd  mov     [rsp+580h+var_538], eax
0x180007ed1  test    eax, eax
0x180007ed3  js      loc_180007FEB
0x180007ed9  mov     [rsp+580h+var_534], di
0x180007ede  cmp     eax, r15d
0x180007ee1  jz      loc_180007FC5
0x180007ee7  mov     rcx, [rbp+480h+var_4A8]; unsigned __int16 *
0x180007eeb  lea     rdx, [rbp+480h+String2]; lpszVolumeName
0x180007eef  mov     r8d, 105h; cchBufferLength
0x180007ef5  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x180007efa  test    eax, eax
0x180007efc  js      short loc_180007E9A
0x180007efe  lea     rdx, [rbp+480h+String2]; String2
0x180007f02  lea     rcx, [rbp+480h+String1]; String1
0x180007f09  call    cs:__imp__wcsicmp
0x180007f0f  test    eax, eax
0x180007f11  jnz     short loc_180007E9A
0x180007f13  mov     rcx, [rsp+580h+var_540]
0x180007f18  lea     rdx, [rbp+480h+var_450]
0x180007f1c  movups  xmm0, [rbp+480h+var_4D8]
0x180007f20  mov     [rsp+580h+var_558], rdx
0x180007f25  mov     r9d, r15d
0x180007f28  lea     rdx, [rbp+480h+var_4FC]
0x180007f2c  mov     r8d, 3
0x180007f32  mov     rax, [rcx]
0x180007f35  mov     qword ptr [rsp+580h+var_560], rdx
0x180007f3a  lea     rdx, [rbp+480h+var_4F0]
0x180007f3e  movdqu  [rbp+480h+var_4F0], xmm0
0x180007f43  mov     rax, [rax+138h]
0x180007f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f4f  test    eax, eax
0x180007f51  jns     loc_180007E9A
0x180007f57  mov     r9, [rbp+480h+var_4B0]; unsigned __int16 *
0x180007f5b  lea     rcx, [rsp+580h+var_538]; this
0x180007f60  mov     r8, [rbp+480h+var_4A8]; unsigned __int16 *
0x180007f64  mov     edx, 2E6Ch; unsigned int
0x180007f69  mov     [rsp+580h+var_560], eax; int
0x180007f6d  call    ?Log_SPP_ERROR_SNAPSHOT_DELETION@@YAJPEAVCSxFunctionTracer@@KPEBG1J@Z; Log_SPP_ERROR_SNAPSHOT_DELETION(CSxFunctionTracer *,ulong,ushort const *,ushort const *,long)
0x180007f72  mov     ebx, r15d
0x180007f75  jmp     loc_180007E9A
0x180007f7a  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x180007f7f  mov     edx, eax
0x180007f81  mov     [rsp+580h+var_538], eax
0x180007f85  test    eax, eax
0x180007f87  mov     eax, 2E31h
0x180007f8c  js      loc_180007DC7
0x180007f92  mov     rcx, [rsp+580h+var_540]
0x180007f97  neg     edx
0x180007f99  mov     [rsp+580h+var_534], ax
0x180007f9e  sbb     edx, edx
0x180007fa0  and     edx, 4
0x180007fa3  mov     rax, [rcx]
0x180007fa6  add     edx, 9
0x180007fa9  mov     rax, [rax+118h]
0x180007fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb5  mov     [rsp+580h+var_538], eax
0x180007fb9  test    eax, eax
0x180007fbb  mov     eax, 2E3Ah
0x180007fc0  jmp     loc_180007E42
0x180007fc5  test    ebx, ebx
0x180007fc7  jnz     short loc_180007FD9
0x180007fc9  mov     eax, 2E78h
0x180007fce  mov     [rsp+580h+var_538], ebx
0x180007fd2  mov     [rsp+580h+var_534], ax
0x180007fd7  jmp     short loc_180007FF0
0x180007fd9  mov     [rsp+580h+var_538], 8100010Bh
0x180007fe1  mov     eax, 2E76h
0x180007fe6  jmp     loc_180007DC7
0x180007feb  mov     [rsp+580h+var_532], di
0x180007ff0  lea     rcx, [rbp+480h+var_4D8]
0x180007ff4  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x180007ffa  mov     r8, r12; Size
0x180007ffd  lea     rcx, [rbp+480h+var_4E0]; void *
0x180008001  xor     edx, edx; Val
0x180008003  call    memset_0
0x180008008  mov     ebx, [rsp+580h+var_538]
0x18000800c  lea     rcx, [rbp+480h+var_4F8]
0x180008010  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180008015  lea     rcx, [rsp+580h+var_540]
0x18000801a  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x18000801f  lea     rcx, [rsp+580h+var_538]; this
0x180008024  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180008029  mov     eax, ebx
0x18000802b  mov     rcx, [rbp+480h+var_20]
0x180008032  xor     rcx, rsp; StackCookie
0x180008035  call    __security_check_cookie
0x18000803a  lea     r11, [rsp+580h+var_10]
0x180008042  mov     rbx, [r11+20h]
0x180008046  mov     rdi, [r11+30h]
0x18000804a  mov     rsp, r11
0x18000804d  pop     r15
0x18000804f  pop     r12
0x180008051  pop     rbp
0x180008052  retn
```
