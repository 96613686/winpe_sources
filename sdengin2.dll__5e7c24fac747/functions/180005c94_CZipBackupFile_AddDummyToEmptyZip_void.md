# CZipBackupFile::_AddDummyToEmptyZip(void)

- ea: `0x180005c94`
- end: `0x180005fb0`
- name: `?_AddDummyToEmptyZip@CZipBackupFile@@AEAAJXZ`
- size: `796`
- prototype: `__int64 __fastcall(CZipBackupFile *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004e70`

## callees

- `0x1800038a4`
- `0x180005c94`
- `0x180007d50`
- `0x180008200`
- `0x1800084b4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18007b094`
- `0x180099904`
- `0x18009a20c`
- `0x18009a24c`
- `0x18009ae34`
- `0x18009b494`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!GetACP` at `0x180005d85`
- `KERNEL32!GetACP` at `0x180005de8`
- `KERNEL32!GetACP` at `0x180005d85`
- `KERNEL32!GetACP` at `0x180005de8`
- `ole32!CoTaskMemFree` at `0x180005f6b`
- `ole32!CoTaskMemFree` at `0x180005f79`
- `ole32!CoTaskMemFree` at `0x180005f6b`
- `ole32!CoTaskMemFree` at `0x180005f79`

## pseudocode

```c
__int64 __fastcall CZipBackupFile::_AddDummyToEmptyZip(CZipBackupFile *this)
{
  __int16 v2; // ax
  UINT ACP; // eax
  char *v4; // rbx
  __int16 v5; // ax
  UINT v6; // eax
  void *v7; // rdi
  __int16 v8; // ax
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned int v13; // ebx
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v16; // [rsp+34h] [rbp-CCh]
  __int16 v17; // [rsp+36h] [rbp-CAh]
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v19[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v20[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v21[3]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v23; // [rsp+C4h] [rbp-3Ch]
  char *v24; // [rsp+C8h] [rbp-38h]
  void *v25; // [rsp+D0h] [rbp-30h]
  __int64 (__fastcall *v26)(const char *, int, void *); // [rsp+E8h] [rbp-18h]
  __int64 v27; // [rsp+F0h] [rbp-10h]
  int v28; // [rsp+120h] [rbp+20h]
  __int16 v29; // [rsp+192h] [rbp+92h]
  _OWORD *v30; // [rsp+194h] [rbp+94h]
  __int64 v31; // [rsp+1A0h] [rbp+A0h]
  __int64 v32; // [rsp+1A8h] [rbp+A8h]
  unsigned int v33; // [rsp+528h] [rbp+428h] BYREF
  unsigned int v34; // [rsp+530h] [rbp+430h] BYREF
  char *v35; // [rsp+538h] [rbp+438h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CZipBackupFile::_AddDummyToEmptyZip", 1501, 1);
  memset(v21, 0, 36);
  TAGZipCommandStruct::TAGZipCommandStruct((TAGZipCommandStruct *)v22, 1);
  v20[0] = qword_1800E8530;
  v20[1] = 0;
  v19[0] = qword_1800E8530;
  v19[1] = 0;
  pv = 0;
  v34 = 0;
  v35 = 0;
  v33 = 0;
  v15 = CBsString::Set((CBsString *)v20, L"\"_\"");
  v2 = 1522;
  if ( v15 < 0
    || (v16 = 1522,
        v15 = CBsString::Set((CBsString *)v19, L"\"", *((const unsigned __int16 **)this + 9), L"\""),
        v2 = 1523,
        v15 < 0) )
  {
    v17 = v2;
  }
  else
  {
    v16 = 1523;
    ACP = GetACP();
    v15 = CBsString::ConvertMBS((CBsString *)v19, ACP, &v35, &v33);
    v4 = v35;
    v5 = 1526;
    if ( v15 < 0 || (v16 = 1526, v15 = RemoveCtrlCharactersInPlace(v35, v33), v5 = 1527, v15 < 0) )
    {
      v17 = v5;
    }
    else
    {
      v16 = 1527;
      v6 = GetACP();
      v15 = CBsString::ConvertMBS((CBsString *)v20, v6, (char **)&pv, &v34);
      v7 = pv;
      v8 = 1530;
      if ( v15 < 0 )
        goto LABEL_8;
      v16 = 1530;
      v15 = RemoveCtrlCharactersInPlace((char *)pv, v34);
      v8 = 1531;
      if ( v15 < 0 )
        goto LABEL_8;
      v16 = 1531;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
        WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, (_DWORD)v7, (__int64)v4);
      v11 = (*(__int64 (__fastcall **)(CZipBackupFile *))(*(_QWORD *)this + 72LL))(this);
      v24 = v4;
      v25 = v7;
      v23 = 7;
      v28 = 1;
      v29 |= 2u;
      v26 = CZipBackupFile::_AddFileStatusCallback;
      v27 = v11;
      v31 = 0;
      v32 = 0;
      LODWORD(v21[0]) = 36;
      *(_QWORD *)((char *)v21 + 4) = CZipBackupFile::_AddDummyFileStreamCallback;
      *(_QWORD *)((char *)v21 + 12) = v11;
      *(_OWORD *)((char *)&v21[1] + 4) = 0;
      v30 = v21;
      v12 = sd_dzip_init(v22, (char *)this + 168, (char *)this + 176);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_ef1b23c1e6b9313f5069d7982d494eb0_Traceguids, v12);
      v15 = CZipBackupFile::_TranslateDzipError(v12);
      v8 = 1561;
      if ( v15 < 0 )
      {
LABEL_8:
        v17 = v8;
      }
      else
      {
        v16 = 1561;
        *((_DWORD *)this + 40) = 1;
      }
      if ( v7 )
        CoTaskMemFree(v7);
    }
    if ( v4 )
      CoTaskMemFree(v4);
  }
  v13 = v15;
  CBsString::_Release((CBsString *)v19);
  CBsString::_Release((CBsString *)v20);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15);
  return v13;
}

```

## disassembly

```asm
0x180005c94  push    rbp
0x180005c96  push    rbx
0x180005c97  push    rsi
0x180005c98  push    rdi
0x180005c99  push    r14
0x180005c9b  lea     rbp, [rsp-3F0h]
0x180005ca3  sub     rsp, 4F0h
0x180005caa  mov     rsi, rcx
0x180005cad  mov     r9d, 1; unsigned __int16
0x180005cb3  mov     r8d, 5DDh; unsigned __int16
0x180005cb9  lea     rdx, aCzipbackupfile_14; "CZipBackupFile::_AddDummyToEmptyZip"
0x180005cc0  lea     rcx, [rsp+510h+var_4E0]; this
0x180005cc5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180005cca  xorps   xmm0, xmm0
0x180005ccd  xor     eax, eax
0x180005ccf  movups  [rbp+410h+var_480], xmm0
0x180005cd3  movups  [rbp+410h+var_470], xmm0
0x180005cd7  mov     [rbp+410h+var_460], eax
0x180005cda  lea     edx, [rax+1]; int
0x180005cdd  lea     rcx, [rbp+410h+var_450]; this
0x180005ce1  call    ??0TAGZipCommandStruct@@QEAA@H@Z; TAGZipCommandStruct::TAGZipCommandStruct(int)
0x180005ce6  lea     rcx, qword_1800E8530
0x180005ced  mov     [rbp+410h+var_490], rcx
0x180005cf1  mov     [rbp+410h+var_488], 0
0x180005cf9  mov     [rsp+510h+var_4A0], rcx
0x180005cfe  mov     [rsp+510h+var_498], 0
0x180005d07  mov     [rsp+510h+pv], 0
0x180005d10  mov     [rbp+410h+arg_10], 0
0x180005d1a  mov     [rbp+410h+arg_18], 0
0x180005d25  mov     [rbp+410h+arg_8], 0
0x180005d2f  lea     rdx, asc_1800DA3B0; "\"_\""
0x180005d36  lea     rcx, [rbp+410h+var_490]; this
0x180005d3a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180005d3f  mov     [rsp+510h+var_4E0], eax
0x180005d43  test    eax, eax
0x180005d45  mov     eax, 5F2h
0x180005d4a  jns     short loc_180005D56
0x180005d4c  mov     [rsp+510h+var_4DA], ax
0x180005d51  jmp     loc_180005F7F
0x180005d56  mov     [rsp+510h+var_4DC], ax
0x180005d5b  lea     rdx, asc_1800DA120; "\""
0x180005d62  mov     r9, rdx; unsigned __int16 *
0x180005d65  mov     r8, [rsi+48h]; unsigned __int16 *
0x180005d69  lea     rcx, [rsp+510h+var_4A0]; this
0x180005d6e  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x180005d73  mov     [rsp+510h+var_4E0], eax
0x180005d77  test    eax, eax
0x180005d79  mov     eax, 5F3h
0x180005d7e  js      short loc_180005D4C
0x180005d80  mov     [rsp+510h+var_4DC], ax
0x180005d85  call    cs:__imp_GetACP
0x180005d8b  mov     edx, eax; unsigned int
0x180005d8d  lea     r9, [rbp+410h+arg_8]; unsigned int *
0x180005d94  lea     r8, [rbp+410h+arg_18]; char **
0x180005d9b  lea     rcx, [rsp+510h+var_4A0]; this
0x180005da0  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180005da5  mov     [rsp+510h+var_4E0], eax
0x180005da9  mov     rbx, [rbp+410h+arg_18]
0x180005db0  test    eax, eax
0x180005db2  mov     eax, 5F6h
0x180005db7  jns     short loc_180005DC3
0x180005db9  mov     [rsp+510h+var_4DA], ax
0x180005dbe  jmp     loc_180005F71
0x180005dc3  mov     [rsp+510h+var_4DC], ax
0x180005dc8  mov     edx, [rbp+410h+arg_8]; unsigned int
0x180005dce  mov     rcx, rbx; char *
0x180005dd1  call    ?RemoveCtrlCharactersInPlace@@YAJPEADK@Z; RemoveCtrlCharactersInPlace(char *,ulong)
0x180005dd6  mov     [rsp+510h+var_4E0], eax
0x180005dda  test    eax, eax
0x180005ddc  mov     eax, 5F7h
0x180005de1  js      short loc_180005DB9
0x180005de3  mov     [rsp+510h+var_4DC], ax
0x180005de8  call    cs:__imp_GetACP
0x180005dee  mov     edx, eax; unsigned int
0x180005df0  lea     r9, [rbp+410h+arg_10]; unsigned int *
0x180005df7  lea     r8, [rsp+510h+pv]; char **
0x180005dfc  lea     rcx, [rbp+410h+var_490]; this
0x180005e00  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180005e05  mov     [rsp+510h+var_4E0], eax
0x180005e09  mov     rdi, [rsp+510h+pv]
0x180005e0e  test    eax, eax
0x180005e10  mov     eax, 5FAh
0x180005e15  jns     short loc_180005E21
0x180005e17  mov     [rsp+510h+var_4DA], ax
0x180005e1c  jmp     loc_180005F63
0x180005e21  mov     [rsp+510h+var_4DC], ax
0x180005e26  mov     edx, [rbp+410h+arg_10]; unsigned int
0x180005e2c  mov     rcx, rdi; char *
0x180005e2f  call    ?RemoveCtrlCharactersInPlace@@YAJPEADK@Z; RemoveCtrlCharactersInPlace(char *,ulong)
0x180005e34  mov     [rsp+510h+var_4E0], eax
0x180005e38  test    eax, eax
0x180005e3a  mov     eax, 5FBh
0x180005e3f  js      short loc_180005E17
0x180005e41  mov     [rsp+510h+var_4DC], ax
0x180005e46  lea     rax, WPP_GLOBAL_Control
0x180005e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e54  cmp     rcx, rax
0x180005e57  jz      short loc_180005E73
0x180005e59  test    dword ptr [rcx+1Ch], 80000h
0x180005e60  jz      short loc_180005E73
0x180005e62  mov     [rsp+510h+var_4F0], rbx
0x180005e67  mov     r9, rdi
0x180005e6a  mov     rcx, [rcx+10h]
0x180005e6e  call    WPP_SF_ss
0x180005e73  mov     rax, [rsi]
0x180005e76  mov     rcx, rsi
0x180005e79  mov     rax, [rax+48h]
0x180005e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e82  mov     [rbp+410h+var_448], rbx
0x180005e86  mov     [rbp+410h+var_440], rdi
0x180005e8a  mov     [rbp+410h+var_44C], 7
0x180005e91  mov     [rbp+410h+var_3F0], 1
0x180005e98  or      [rbp+410h+var_37E], 2
0x180005ea0  lea     rcx, ?_AddFileStatusCallback@CZipBackupFile@@CAHPEBDJPEAX@Z; CZipBackupFile::_AddFileStatusCallback(char const *,long,void *)
0x180005ea7  mov     [rbp+410h+var_428], rcx
0x180005eab  mov     [rbp+410h+var_420], rax
0x180005eaf  mov     [rbp+410h+var_370], 0
0x180005eba  mov     [rbp+410h+var_368], 0
0x180005ec5  mov     dword ptr [rbp+410h+var_480], 24h ; '$'
0x180005ecc  lea     rcx, ?_AddDummyFileStreamCallback@CZipBackupFile@@CAXJPEAXPEAKKKKK0PEAJ@Z; CZipBackupFile::_AddDummyFileStreamCallback(long,void *,ulong *,ulong,ulong,ulong,ulong,void *,long *)
0x180005ed3  mov     qword ptr [rbp+410h+var_480+4], rcx
0x180005ed7  mov     qword ptr [rbp+410h+var_480+0Ch], rax
0x180005edb  xorps   xmm0, xmm0
0x180005ede  movups  [rbp+410h+var_470+4], xmm0
0x180005ee2  lea     rax, [rbp+410h+var_480]
0x180005ee6  mov     [rbp+410h+var_37C], rax
0x180005eed  lea     r8, [rsi+0B0h]
0x180005ef4  lea     rdx, [rsi+0A8h]
0x180005efb  lea     rcx, [rbp+410h+var_450]
0x180005eff  call    sd_dzip_init
0x180005f04  mov     r14d, eax
0x180005f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f0e  lea     rax, WPP_GLOBAL_Control
0x180005f15  cmp     rcx, rax
0x180005f18  jz      short loc_180005F3B
0x180005f1a  test    dword ptr [rcx+1Ch], 80000h
0x180005f21  jz      short loc_180005F3B
0x180005f23  mov     edx, 20h ; ' '
0x180005f28  mov     r9d, r14d
0x180005f2b  lea     r8, WPP_ef1b23c1e6b9313f5069d7982d494eb0_Traceguids
0x180005f32  mov     rcx, [rcx+10h]
0x180005f36  call    WPP_SF_d
0x180005f3b  mov     ecx, r14d; int
0x180005f3e  call    ?_TranslateDzipError@CZipBackupFile@@CAJH@Z; CZipBackupFile::_TranslateDzipError(int)
0x180005f43  mov     [rsp+510h+var_4E0], eax
0x180005f47  test    eax, eax
0x180005f49  mov     eax, 619h
0x180005f4e  js      loc_180005E17
0x180005f54  mov     [rsp+510h+var_4DC], ax
0x180005f59  mov     dword ptr [rsi+0A0h], 1
0x180005f63  test    rdi, rdi
0x180005f66  jz      short loc_180005F71
0x180005f68  mov     rcx, rdi; pv
0x180005f6b  call    cs:__imp_CoTaskMemFree
0x180005f71  test    rbx, rbx
0x180005f74  jz      short loc_180005F7F
0x180005f76  mov     rcx, rbx; pv
0x180005f79  call    cs:__imp_CoTaskMemFree
0x180005f7f  mov     ebx, [rsp+510h+var_4E0]
0x180005f83  lea     rcx, [rsp+510h+var_4A0]; this
0x180005f88  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005f8d  lea     rcx, [rbp+410h+var_490]; this
0x180005f91  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005f96  lea     rcx, [rsp+510h+var_4E0]; this
0x180005f9b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180005fa0  mov     eax, ebx
0x180005fa2  add     rsp, 4F0h
0x180005fa9  pop     r14
0x180005fab  pop     rdi
0x180005fac  pop     rsi
0x180005fad  pop     rbx
0x180005fae  pop     rbp
0x180005faf  retn
```
