# CZipBackupFile::_AddDummyToEmptyZip(void)

- ea: `0x180005d94`
- end: `0x1800060c9`
- name: `?_AddDummyToEmptyZip@CZipBackupFile@@AEAAJXZ`
- size: `821`
- prototype: `__int64 __fastcall(CZipBackupFile *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004ff0`

## callees

- `0x1800039b4`
- `0x180005d94`
- `0x180007ec8`
- `0x1800083a0`
- `0x180008684`
- `0x180072e08`
- `0x180072f14`
- `0x18007e2dc`
- `0x18009df24`
- `0x18009e8c4`
- `0x18009e904`
- `0x18009f560`
- `0x18009fc00`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!GetACP` at `0x180005e85`
- `KERNEL32!GetACP` at `0x180005eee`
- `KERNEL32!GetACP` at `0x180005e85`
- `KERNEL32!GetACP` at `0x180005eee`
- `ole32!CoTaskMemFree` at `0x180006077`
- `ole32!CoTaskMemFree` at `0x18000608b`
- `ole32!CoTaskMemFree` at `0x180006077`
- `ole32!CoTaskMemFree` at `0x18000608b`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CZipBackupFile::_AddDummyToEmptyZip", 0x5DDu, 1u);
  memset(v21, 0, 36);
  TAGZipCommandStruct::TAGZipCommandStruct((TAGZipCommandStruct *)v22, 1);
  v20[0] = qword_1800EE510;
  v20[1] = 0;
  v19[0] = qword_1800EE510;
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
      v12 = sd_dzip_init((__int64)v22, (_QWORD *)this + 21, (_QWORD *)this + 22);
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
0x180005d94  push    rbp
0x180005d96  push    rbx
0x180005d97  push    rsi
0x180005d98  push    rdi
0x180005d99  push    r14
0x180005d9b  lea     rbp, [rsp-3F0h]
0x180005da3  sub     rsp, 4F0h
0x180005daa  mov     rsi, rcx
0x180005dad  mov     r9d, 1; unsigned __int16
0x180005db3  mov     r8d, 5DDh; unsigned __int16
0x180005db9  lea     rdx, aCzipbackupfile_14; "CZipBackupFile::_AddDummyToEmptyZip"
0x180005dc0  lea     rcx, [rsp+510h+var_4E0]; this
0x180005dc5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180005dca  xorps   xmm0, xmm0
0x180005dcd  xor     eax, eax
0x180005dcf  movups  [rbp+410h+var_480], xmm0
0x180005dd3  movups  [rbp+410h+var_470], xmm0
0x180005dd7  mov     [rbp+410h+var_460], eax
0x180005dda  lea     edx, [rax+1]; int
0x180005ddd  lea     rcx, [rbp+410h+var_450]; this
0x180005de1  call    ??0TAGZipCommandStruct@@QEAA@H@Z; TAGZipCommandStruct::TAGZipCommandStruct(int)
0x180005de6  lea     rcx, qword_1800EE510
0x180005ded  mov     [rbp+410h+var_490], rcx
0x180005df1  mov     [rbp+410h+var_488], 0
0x180005df9  mov     [rsp+510h+var_4A0], rcx
0x180005dfe  mov     [rsp+510h+var_498], 0
0x180005e07  mov     [rsp+510h+pv], 0
0x180005e10  mov     [rbp+410h+arg_10], 0
0x180005e1a  mov     [rbp+410h+arg_18], 0
0x180005e25  mov     [rbp+410h+arg_8], 0
0x180005e2f  lea     rdx, asc_1800E0390; "\"_\""
0x180005e36  lea     rcx, [rbp+410h+var_490]; this
0x180005e3a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180005e3f  mov     [rsp+510h+var_4E0], eax
0x180005e43  test    eax, eax
0x180005e45  mov     eax, 5F2h
0x180005e4a  jns     short loc_180005E56
0x180005e4c  mov     [rsp+510h+var_4DA], ax
0x180005e51  jmp     loc_180006097
0x180005e56  mov     [rsp+510h+var_4DC], ax
0x180005e5b  lea     rdx, asc_1800E0100; "\""
0x180005e62  mov     r9, rdx; unsigned __int16 *
0x180005e65  mov     r8, [rsi+48h]; unsigned __int16 *
0x180005e69  lea     rcx, [rsp+510h+var_4A0]; this
0x180005e6e  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x180005e73  mov     [rsp+510h+var_4E0], eax
0x180005e77  test    eax, eax
0x180005e79  mov     eax, 5F3h
0x180005e7e  js      short loc_180005E4C
0x180005e80  mov     [rsp+510h+var_4DC], ax
0x180005e85  call    cs:__imp_GetACP
0x180005e8c  nop     dword ptr [rax+rax+00h]
0x180005e91  mov     edx, eax; unsigned int
0x180005e93  lea     r9, [rbp+410h+arg_8]; unsigned int *
0x180005e9a  lea     r8, [rbp+410h+arg_18]; char **
0x180005ea1  lea     rcx, [rsp+510h+var_4A0]; this
0x180005ea6  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180005eab  mov     [rsp+510h+var_4E0], eax
0x180005eaf  mov     rbx, [rbp+410h+arg_18]
0x180005eb6  test    eax, eax
0x180005eb8  mov     eax, 5F6h
0x180005ebd  jns     short loc_180005EC9
0x180005ebf  mov     [rsp+510h+var_4DA], ax
0x180005ec4  jmp     loc_180006083
0x180005ec9  mov     [rsp+510h+var_4DC], ax
0x180005ece  mov     edx, [rbp+410h+arg_8]; unsigned int
0x180005ed4  mov     rcx, rbx; char *
0x180005ed7  call    ?RemoveCtrlCharactersInPlace@@YAJPEADK@Z; RemoveCtrlCharactersInPlace(char *,ulong)
0x180005edc  mov     [rsp+510h+var_4E0], eax
0x180005ee0  test    eax, eax
0x180005ee2  mov     eax, 5F7h
0x180005ee7  js      short loc_180005EBF
0x180005ee9  mov     [rsp+510h+var_4DC], ax
0x180005eee  call    cs:__imp_GetACP
0x180005ef5  nop     dword ptr [rax+rax+00h]
0x180005efa  mov     edx, eax; unsigned int
0x180005efc  lea     r9, [rbp+410h+arg_10]; unsigned int *
0x180005f03  lea     r8, [rsp+510h+pv]; char **
0x180005f08  lea     rcx, [rbp+410h+var_490]; this
0x180005f0c  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180005f11  mov     [rsp+510h+var_4E0], eax
0x180005f15  mov     rdi, [rsp+510h+pv]
0x180005f1a  test    eax, eax
0x180005f1c  mov     eax, 5FAh
0x180005f21  jns     short loc_180005F2D
0x180005f23  mov     [rsp+510h+var_4DA], ax
0x180005f28  jmp     loc_18000606F
0x180005f2d  mov     [rsp+510h+var_4DC], ax
0x180005f32  mov     edx, [rbp+410h+arg_10]; unsigned int
0x180005f38  mov     rcx, rdi; char *
0x180005f3b  call    ?RemoveCtrlCharactersInPlace@@YAJPEADK@Z; RemoveCtrlCharactersInPlace(char *,ulong)
0x180005f40  mov     [rsp+510h+var_4E0], eax
0x180005f44  test    eax, eax
0x180005f46  mov     eax, 5FBh
0x180005f4b  js      short loc_180005F23
0x180005f4d  mov     [rsp+510h+var_4DC], ax
0x180005f52  lea     rax, WPP_GLOBAL_Control
0x180005f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f60  cmp     rcx, rax
0x180005f63  jz      short loc_180005F7F
0x180005f65  test    dword ptr [rcx+1Ch], 80000h
0x180005f6c  jz      short loc_180005F7F
0x180005f6e  mov     [rsp+510h+var_4F0], rbx
0x180005f73  mov     r9, rdi
0x180005f76  mov     rcx, [rcx+10h]
0x180005f7a  call    WPP_SF_ss
0x180005f7f  mov     rax, [rsi]
0x180005f82  mov     rcx, rsi
0x180005f85  mov     rax, [rax+48h]
0x180005f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8e  mov     [rbp+410h+var_448], rbx
0x180005f92  mov     [rbp+410h+var_440], rdi
0x180005f96  mov     [rbp+410h+var_44C], 7
0x180005f9d  mov     [rbp+410h+var_3F0], 1
0x180005fa4  or      [rbp+410h+var_37E], 2
0x180005fac  lea     rcx, ?_AddFileStatusCallback@CZipBackupFile@@CAHPEBDJPEAX@Z; CZipBackupFile::_AddFileStatusCallback(char const *,long,void *)
0x180005fb3  mov     [rbp+410h+var_428], rcx
0x180005fb7  mov     [rbp+410h+var_420], rax
0x180005fbb  mov     [rbp+410h+var_370], 0
0x180005fc6  mov     [rbp+410h+var_368], 0
0x180005fd1  mov     dword ptr [rbp+410h+var_480], 24h ; '$'
0x180005fd8  lea     rcx, ?_AddDummyFileStreamCallback@CZipBackupFile@@CAXJPEAXPEAKKKKK0PEAJ@Z; CZipBackupFile::_AddDummyFileStreamCallback(long,void *,ulong *,ulong,ulong,ulong,ulong,void *,long *)
0x180005fdf  mov     qword ptr [rbp+410h+var_480+4], rcx
0x180005fe3  mov     qword ptr [rbp+410h+var_480+0Ch], rax
0x180005fe7  xorps   xmm0, xmm0
0x180005fea  movups  [rbp+410h+var_470+4], xmm0
0x180005fee  lea     rax, [rbp+410h+var_480]
0x180005ff2  mov     [rbp+410h+var_37C], rax
0x180005ff9  lea     r8, [rsi+0B0h]
0x180006000  lea     rdx, [rsi+0A8h]
0x180006007  lea     rcx, [rbp+410h+var_450]
0x18000600b  call    sd_dzip_init
0x180006010  mov     r14d, eax
0x180006013  mov     rcx, cs:WPP_GLOBAL_Control
0x18000601a  lea     rax, WPP_GLOBAL_Control
0x180006021  cmp     rcx, rax
0x180006024  jz      short loc_180006047
0x180006026  test    dword ptr [rcx+1Ch], 80000h
0x18000602d  jz      short loc_180006047
0x18000602f  mov     edx, 20h ; ' '
0x180006034  mov     r9d, r14d
0x180006037  lea     r8, WPP_ef1b23c1e6b9313f5069d7982d494eb0_Traceguids
0x18000603e  mov     rcx, [rcx+10h]
0x180006042  call    WPP_SF_d
0x180006047  mov     ecx, r14d; int
0x18000604a  call    ?_TranslateDzipError@CZipBackupFile@@CAJH@Z; CZipBackupFile::_TranslateDzipError(int)
0x18000604f  mov     [rsp+510h+var_4E0], eax
0x180006053  test    eax, eax
0x180006055  mov     eax, 619h
0x18000605a  js      loc_180005F23
0x180006060  mov     [rsp+510h+var_4DC], ax
0x180006065  mov     dword ptr [rsi+0A0h], 1
0x18000606f  test    rdi, rdi
0x180006072  jz      short loc_180006083
0x180006074  mov     rcx, rdi; pv
0x180006077  call    cs:__imp_CoTaskMemFree
0x18000607e  nop     dword ptr [rax+rax+00h]
0x180006083  test    rbx, rbx
0x180006086  jz      short loc_180006097
0x180006088  mov     rcx, rbx; pv
0x18000608b  call    cs:__imp_CoTaskMemFree
0x180006092  nop     dword ptr [rax+rax+00h]
0x180006097  mov     ebx, [rsp+510h+var_4E0]
0x18000609b  lea     rcx, [rsp+510h+var_4A0]; this
0x1800060a0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800060a5  lea     rcx, [rbp+410h+var_490]; this
0x1800060a9  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800060ae  lea     rcx, [rsp+510h+var_4E0]; this
0x1800060b3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800060b8  mov     eax, ebx
0x1800060ba  add     rsp, 4F0h
0x1800060c1  pop     r14
0x1800060c3  pop     rdi
0x1800060c4  pop     rsi
0x1800060c5  pop     rbx
0x1800060c6  pop     rbp
0x1800060c7  retn
```
