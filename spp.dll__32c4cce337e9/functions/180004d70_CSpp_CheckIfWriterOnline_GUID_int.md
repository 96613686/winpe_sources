# CSpp::CheckIfWriterOnline(_GUID,int *)

- ea: `0x180004d70`
- end: `0x180004fdb`
- name: `?CheckIfWriterOnline@CSpp@@UEAAJU_GUID@@PEAH@Z`
- size: `619`
- prototype: `__int64 __fastcall(CSpp *__hidden this, struct _GUID *Buf1, int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180004d70`
- `0x180007344`
- `0x18000907c`
- `0x18000e54c`
- `0x18000e58c`
- `0x180017960`
- `0x18001b1e0`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x180035b76`
- `0x180037010`

## import_xrefs

- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180004e3f`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180004e3f`

## string_xrefs

- `0x180004dca`: `CSpp::CheckIfWriterOnline`

## pseudocode

```c
__int64 __fastcall CSpp::CheckIfWriterOnline(CSpp *this, struct _GUID *Buf1, int *a3)
{
  struct CSxVolumeInfoArray *v6; // rsi
  CWriterEntry *v7; // rdi
  bool v8; // zf
  __int64 v9; // rdx
  __int16 v10; // ax
  int inited; // ebx
  CSpp *v12; // rcx
  int v13; // eax
  bool v14; // sf
  unsigned int v15; // r13d
  unsigned int v16; // r15d
  int v17; // eax
  __int16 v18; // r10
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  struct IVssBackupComponents *v23; // [rsp+20h] [rbp-60h] BYREF
  CWriterEntry *v24; // [rsp+28h] [rbp-58h] BYREF
  struct CSxVolumeInfoArray *v25; // [rsp+30h] [rbp-50h] BYREF
  int v26; // [rsp+38h] [rbp-48h] BYREF
  __int16 v27; // [rsp+3Ch] [rbp-44h]
  __int16 v28; // [rsp+3Eh] [rbp-42h]
  unsigned __int64 v29; // [rsp+70h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CSpp::CheckIfWriterOnline", 11257, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v23);
  v6 = 0;
  v7 = 0;
  v25 = 0;
  v29 = 0;
  v24 = 0;
  v8 = memcmp_0(Buf1, &GUID_NULL, 0x10u) == 0;
  v10 = 11267;
  if ( v8 )
  {
    inited = -2147024809;
    v26 = -2147024809;
LABEL_6:
    v28 = v10;
    goto LABEL_27;
  }
  v26 = 0;
  v27 = 11267;
  if ( a3 )
    *a3 = 0;
  *a3 = 0;
  inited = CreateVssBackupComponentsInternal(&v23, v9);
  v26 = inited;
  v10 = 11276;
  if ( inited < 0 )
    goto LABEL_6;
  v27 = 11276;
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v23 + 40LL))(v23, 0);
  v26 = inited;
  v10 = 11278;
  if ( inited < 0 )
    goto LABEL_6;
  v27 = 11278;
  inited = CSpp::_InitTimer(v12, 0xFFFFFFFFLL, &v29);
  v26 = inited;
  v10 = 11280;
  if ( inited < 0 )
    goto LABEL_6;
  v27 = 11280;
  inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, struct _GUID *, __int64))(*(_QWORD *)v23 + 368LL))(
             v23,
             Buf1,
             1);
  v26 = inited;
  v10 = 11282;
  if ( inited < 0 )
    goto LABEL_6;
  v27 = 11282;
  v13 = CSxVolumeInfoArray::CreateInstance(&v25);
  v6 = v25;
  inited = v13;
  v26 = v13;
  v14 = v13 < 0;
  v10 = 11285;
  if ( v14 )
    goto LABEL_6;
  v27 = 11285;
  if ( (unsigned int)CSpp::_GatherWriterMetadata(this, v23, v25, v29) == -2130706167 )
  {
    inited = 0;
    *a3 = 0;
    v26 = 0;
    v27 = 11294;
  }
  else
  {
    v15 = *((_DWORD *)v6 + 2);
    v16 = 0;
    inited = v26;
    while ( v16 < v15 )
    {
      if ( v7 )
      {
        v24 = 0;
        CWriterEntry::Release(v7);
      }
      v17 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(v6, v16, &v24);
      v7 = v24;
      inited = v17;
      v26 = v17;
      if ( v17 < 0 )
      {
        v28 = v18;
        break;
      }
      v27 = v18;
      v19 = *((_QWORD *)v24 + 4) - *(_QWORD *)&Buf1->Data1;
      if ( !v19 )
        v19 = *((_QWORD *)v24 + 5) - *(_QWORD *)Buf1->Data4;
      if ( !v19 )
        *a3 = 1;
      ++v16;
    }
  }
LABEL_27:
  if ( v7 )
    CWriterEntry::Release(v7);
  if ( v6 )
    CWriterEntryArray::Release(v6);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26, v20, v21);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180004d70  mov     [rsp-38h+arg_18], rbx
0x180004d75  push    rbp
0x180004d76  push    rsi
0x180004d77  push    rdi
0x180004d78  push    r12
0x180004d7a  push    r13
0x180004d7c  push    r14
0x180004d7e  push    r15
0x180004d80  mov     rbp, rsp
0x180004d83  sub     rsp, 80h
0x180004d8a  mov     r14, r8
0x180004d8d  mov     r12, rdx
0x180004d90  mov     r15, rcx
0x180004d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d9a  lea     rax, WPP_GLOBAL_Control
0x180004da1  cmp     rcx, rax
0x180004da4  jz      short loc_180004DC4
0x180004da6  test    dword ptr [rcx+1Ch], 20000000h
0x180004dad  jz      short loc_180004DC4
0x180004daf  mov     rcx, [rcx+10h]
0x180004db3  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180004dba  mov     edx, 0C0h
0x180004dbf  call    WPP_SF_
0x180004dc4  mov     r13d, 1
0x180004dca  lea     rdx, aCsppCheckifwri; "CSpp::CheckIfWriterOnline"
0x180004dd1  mov     r9d, r13d; unsigned __int16
0x180004dd4  lea     rcx, [rbp+var_48]; this
0x180004dd8  mov     r8d, 2BF9h; unsigned __int16
0x180004dde  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180004de3  lea     rcx, [rbp+var_60]
0x180004de7  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180004dec  xor     esi, esi
0x180004dee  lea     r8d, [r13+0Fh]; Size
0x180004df2  xor     edi, edi
0x180004df4  mov     [rbp+var_50], rsi
0x180004df8  lea     rdx, GUID_NULL; Buf2
0x180004dff  mov     [rbp+var_10], rsi
0x180004e03  mov     rcx, r12; Buf1
0x180004e06  mov     [rbp+var_58], rdi
0x180004e0a  call    memcmp_0
0x180004e0f  test    eax, eax
0x180004e11  mov     eax, 2C03h
0x180004e16  jnz     short loc_180004E29
0x180004e18  mov     ebx, 80070057h
0x180004e1d  mov     [rbp+var_48], ebx
0x180004e20  mov     [rbp+var_42], ax
0x180004e24  jmp     loc_180004F92
0x180004e29  mov     [rbp+var_48], esi
0x180004e2c  mov     [rbp+var_44], ax
0x180004e30  test    r14, r14
0x180004e33  jz      short loc_180004E38
0x180004e35  mov     [r14], esi
0x180004e38  lea     rcx, [rbp+var_60]
0x180004e3c  mov     [r14], esi
0x180004e3f  call    cs:__imp_CreateVssBackupComponentsInternal
0x180004e45  mov     ebx, eax
0x180004e47  mov     [rbp+var_48], eax
0x180004e4a  test    eax, eax
0x180004e4c  mov     eax, 2C0Ch
0x180004e51  js      short loc_180004E20
0x180004e53  mov     rcx, [rbp+var_60]
0x180004e57  xor     edx, edx
0x180004e59  mov     [rbp+var_44], ax
0x180004e5d  mov     rax, [rcx]
0x180004e60  mov     rax, [rax+28h]
0x180004e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e69  mov     ebx, eax
0x180004e6b  mov     [rbp+var_48], eax
0x180004e6e  test    eax, eax
0x180004e70  mov     eax, 2C0Eh
0x180004e75  js      short loc_180004E20
0x180004e77  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180004e7b  mov     [rbp+var_44], ax
0x180004e7f  or      edx, 0FFFFFFFFh; unsigned int
0x180004e82  call    ?_InitTimer@CSpp@@AEAAJKPEA_K@Z; CSpp::_InitTimer(ulong,unsigned __int64 *)
0x180004e87  mov     ebx, eax
0x180004e89  mov     [rbp+var_48], eax
0x180004e8c  test    eax, eax
0x180004e8e  mov     eax, 2C10h
0x180004e93  js      short loc_180004E20
0x180004e95  mov     rcx, [rbp+var_60]
0x180004e99  mov     r8d, r13d
0x180004e9c  mov     [rbp+var_44], ax
0x180004ea0  mov     rdx, r12
0x180004ea3  mov     rax, [rcx]
0x180004ea6  mov     rax, [rax+170h]
0x180004ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb2  mov     ebx, eax
0x180004eb4  mov     [rbp+var_48], eax
0x180004eb7  test    eax, eax
0x180004eb9  mov     eax, 2C12h
0x180004ebe  js      loc_180004E20
0x180004ec4  lea     rcx, [rbp+var_50]; struct CSxVolumeInfoArray **
0x180004ec8  mov     [rbp+var_44], ax
0x180004ecc  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x180004ed1  mov     rsi, [rbp+var_50]
0x180004ed5  mov     ebx, eax
0x180004ed7  mov     [rbp+var_48], eax
0x180004eda  test    eax, eax
0x180004edc  mov     eax, 2C15h
0x180004ee1  js      loc_180004E20
0x180004ee7  mov     r9, [rbp+var_10]; unsigned __int64
0x180004eeb  mov     r8, rsi; struct CWriterEntryArray *
0x180004eee  mov     rdx, [rbp+var_60]; struct IVssBackupComponents *
0x180004ef2  mov     rcx, r15; this
0x180004ef5  mov     [rbp+var_44], ax
0x180004ef9  call    ?_GatherWriterMetadata@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@_K@Z; CSpp::_GatherWriterMetadata(IVssBackupComponents *,CWriterEntryArray *,unsigned __int64)
0x180004efe  cmp     eax, 81000109h
0x180004f03  jnz     short loc_180004F18
0x180004f05  xor     ebx, ebx
0x180004f07  mov     [r14], edi
0x180004f0a  mov     eax, 2C1Eh
0x180004f0f  mov     [rbp+var_48], ebx
0x180004f12  mov     [rbp+var_44], ax
0x180004f16  jmp     short loc_180004F92
0x180004f18  mov     r13d, [rsi+8]
0x180004f1c  xor     r15d, r15d
0x180004f1f  mov     ebx, [rbp+var_48]
0x180004f22  mov     r10d, 2C26h
0x180004f28  cmp     r15d, r13d
0x180004f2b  jnb     short loc_180004F92
0x180004f2d  test    rdi, rdi
0x180004f30  jz      short loc_180004F48
0x180004f32  mov     rcx, rdi; this
0x180004f35  mov     [rbp+var_58], 0
0x180004f3d  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x180004f42  mov     r10d, 2C26h
0x180004f48  lea     r8, [rbp+var_58]
0x180004f4c  mov     edx, r15d
0x180004f4f  mov     rcx, rsi
0x180004f52  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x180004f57  mov     rdi, [rbp+var_58]
0x180004f5b  mov     ebx, eax
0x180004f5d  mov     [rbp+var_48], eax
0x180004f60  test    eax, eax
0x180004f62  js      short loc_180004F8D
0x180004f64  mov     [rbp+var_44], r10w
0x180004f69  mov     rax, [rdi+20h]
0x180004f6d  sub     rax, [r12]
0x180004f71  jnz     short loc_180004F7C
0x180004f73  mov     rax, [rdi+28h]
0x180004f77  sub     rax, [r12+8]
0x180004f7c  test    rax, rax
0x180004f7f  jnz     short loc_180004F88
0x180004f81  mov     dword ptr [r14], 1
0x180004f88  inc     r15d
0x180004f8b  jmp     short loc_180004F28
0x180004f8d  mov     [rbp+var_42], r10w
0x180004f92  test    rdi, rdi
0x180004f95  jz      short loc_180004F9F
0x180004f97  mov     rcx, rdi; this
0x180004f9a  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x180004f9f  test    rsi, rsi
0x180004fa2  jz      short loc_180004FAC
0x180004fa4  mov     rcx, rsi; this
0x180004fa7  call    ?Release@CWriterEntryArray@@QEAAKXZ; CWriterEntryArray::Release(void)
0x180004fac  lea     rcx, [rbp+var_60]
0x180004fb0  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180004fb5  lea     rcx, [rbp+var_48]; this
0x180004fb9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180004fbe  mov     eax, ebx
0x180004fc0  mov     rbx, [rsp+80h+arg_18]
0x180004fc8  add     rsp, 80h
0x180004fcf  pop     r15
0x180004fd1  pop     r14
0x180004fd3  pop     r13
0x180004fd5  pop     r12
0x180004fd7  pop     rdi
0x180004fd8  pop     rsi
0x180004fd9  pop     rbp
0x180004fda  retn
```
