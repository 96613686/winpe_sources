# CreateCacheDatabaseJetInstance(ushort const *,ushort const *,int,unsigned __int64 *)

- ea: `0x1800afe20`
- end: `0x1800b01cb`
- name: `?CreateCacheDatabaseJetInstance@@YAJPEBG0HPEA_K@Z`
- size: `939`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b0660`
- `0x1801a7c0c`

## callees

- `0x1800204f8`
- `0x180025910`
- `0x18007ec9c`
- `0x1800afe20`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e8878`

## import_xrefs

- `ESENT!JetTerm2` at `0x1800afec9`
- `ESENT!JetTerm2` at `0x1800afec9`
- `ESENT!JetInit` at `0x1800b019f`
- `ESENT!JetInit` at `0x1800b019f`
- `ESENT!JetCreateInstance2W` at `0x1800aff38`
- `ESENT!JetCreateInstance2W` at `0x1800aff38`
- `ESENT!JetSetSystemParameterW` at `0x1800aff65`
- `ESENT!JetSetSystemParameterW` at `0x1800aff92`
- `ESENT!JetSetSystemParameterW` at `0x1800affc4`
- `ESENT!JetSetSystemParameterW` at `0x1800affef`
- `ESENT!JetSetSystemParameterW` at `0x1800b0019`
- `ESENT!JetSetSystemParameterW` at `0x1800b0047`
- `ESENT!JetSetSystemParameterW` at `0x1800b0072`
- `ESENT!JetSetSystemParameterW` at `0x1800b009d`
- `ESENT!JetSetSystemParameterW` at `0x1800b00cb`
- `ESENT!JetSetSystemParameterW` at `0x1800b00f9`
- `ESENT!JetSetSystemParameterW` at `0x1800b0127`
- `ESENT!JetSetSystemParameterW` at `0x1800b0157`
- `ESENT!JetSetSystemParameterW` at `0x1800b0182`
- `ESENT!JetSetSystemParameterW` at `0x1800aff65`
- `ESENT!JetSetSystemParameterW` at `0x1800aff92`
- `ESENT!JetSetSystemParameterW` at `0x1800affc4`
- `ESENT!JetSetSystemParameterW` at `0x1800affef`
- `ESENT!JetSetSystemParameterW` at `0x1800b0019`
- `ESENT!JetSetSystemParameterW` at `0x1800b0047`
- `ESENT!JetSetSystemParameterW` at `0x1800b0072`
- `ESENT!JetSetSystemParameterW` at `0x1800b009d`
- `ESENT!JetSetSystemParameterW` at `0x1800b00cb`
- `ESENT!JetSetSystemParameterW` at `0x1800b00f9`
- `ESENT!JetSetSystemParameterW` at `0x1800b0127`
- `ESENT!JetSetSystemParameterW` at `0x1800b0157`
- `ESENT!JetSetSystemParameterW` at `0x1800b0182`

## string_xrefs

- `0x1800afe97`: `WebCacheV01.tmp`
- `0x1800aff2a`: `WebCacheLocal`

## pseudocode

```c
__int64 __fastcall CreateCacheDatabaseJetInstance(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4)
{
  int v7; // ebx
  JET_INSTANCE v8; // rcx
  JET_ERR v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  const unsigned __int16 *szParam; // [rsp+20h] [rbp-49h]
  unsigned __int16 *v26; // [rsp+28h] [rbp-41h]
  unsigned __int16 *v27; // [rsp+30h] [rbp-39h]
  const unsigned __int16 *v28; // [rsp+38h] [rbp-31h]
  const unsigned __int16 *v29; // [rsp+40h] [rbp-29h]
  const unsigned __int16 *v30; // [rsp+48h] [rbp-21h]
  const unsigned __int16 *v31; // [rsp+50h] [rbp-19h]
  JET_PCWSTR v32[2]; // [rsp+60h] [rbp-9h] BYREF
  int v33; // [rsp+74h] [rbp+Bh]
  JET_INSTANCE instance; // [rsp+78h] [rbp+Fh] BYREF

  v33 = 0;
  instance = -1;
  v32[0] = &Data;
  v32[1] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    v27 = a4;
    LODWORD(v26) = a3;
    WPP_SF_SSlq((_DWORD)a1, (_DWORD)a2, a3, (_DWORD)a1);
  }
  if ( a4 )
    *(_QWORD *)a4 = 0;
  v7 = CWxString::SetPath((CWxString *)v32, a1, L"WebCacheV01.tmp", 0, szParam, v26, v27, v28, v29, v30, v31);
  if ( v7 < 0 )
  {
    v33 = 754;
LABEL_7:
    v8 = instance;
    goto LABEL_8;
  }
  v10 = JetCreateInstance2W(&instance, L"WebCacheLocal", 0, 0);
  v7 = HRESULTFromJET_ERR(v10, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v11 = JetSetSystemParameterW(&instance, 0, 0x81u, 0, 0);
  v7 = HRESULTFromJET_ERR(v11, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v12 = JetSetSystemParameterW(&instance, 0, 0x82u, 1u, 0);
  v7 = HRESULTFromJET_ERR(v12, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v13 = JetSetSystemParameterW(&instance, 0, 3u, 0, L"V01");
  v7 = HRESULTFromJET_ERR(v13, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v14 = JetSetSystemParameterW(&instance, 0, 2u, 0, a1);
  v7 = HRESULTFromJET_ERR(v14, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v15 = JetSetSystemParameterW(&instance, 0, 0, 0, a1);
  v7 = HRESULTFromJET_ERR(v15, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v16 = JetSetSystemParameterW(&instance, 0, 1u, 0, v32[0]);
  v7 = HRESULTFromJET_ERR(v16, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v17 = JetSetSystemParameterW(&instance, 0, 0x11u, 1u, 0);
  v7 = HRESULTFromJET_ERR(v17, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v18 = JetSetSystemParameterW(&instance, 0, 0x4Du, 1u, 0);
  v7 = HRESULTFromJET_ERR(v18, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v19 = JetSetSystemParameterW(&instance, 0, 0xBu, 0x200u, 0);
  v7 = HRESULTFromJET_ERR(v19, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v20 = JetSetSystemParameterW(&instance, 0, 0xCu, 0x400u, 0);
  v7 = HRESULTFromJET_ERR(v20, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v21 = JetSetSystemParameterW(&instance, 0, 0x18u, 0x500000u, 0);
  v7 = HRESULTFromJET_ERR(v21, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  if ( a3 )
  {
    v22 = JetSetSystemParameterW(&instance, 0, 0x2Du, 0, 0);
    v7 = HRESULTFromJET_ERR(v22, 0);
    if ( v7 < 0 )
      goto LABEL_7;
    v23 = JetSetSystemParameterW(&instance, 0, 0x36u, 0, 0);
    v7 = HRESULTFromJET_ERR(v23, 0);
    if ( v7 < 0 )
      goto LABEL_7;
  }
  v24 = JetInit(&instance);
  v7 = HRESULTFromJET_ERR(v24, 0);
  if ( v7 < 0 )
    goto LABEL_7;
  v8 = -1;
  *(_QWORD *)a4 = instance;
  instance = -1;
LABEL_8:
  if ( v8 != -1 )
  {
    JetTerm2(v8, 1u);
    instance = -1;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 38, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, (unsigned int)v7);
  CWxString::_Release((CWxString *)v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800afe20  mov     [rsp-8+arg_8], rbx
0x1800afe25  push    rbp
0x1800afe26  push    rsi
0x1800afe27  push    rdi
0x1800afe28  push    r12
0x1800afe2a  push    r13
0x1800afe2c  push    r14
0x1800afe2e  push    r15
0x1800afe30  lea     rbp, [rsp-27h]
0x1800afe35  sub     rsp, 90h
0x1800afe3c  mov     rax, cs:__security_cookie
0x1800afe43  xor     rax, rsp
0x1800afe46  mov     [rbp+57h+var_40], rax
0x1800afe4a  xor     r15d, r15d
0x1800afe4d  lea     rax, Data
0x1800afe54  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800afe58  mov     [rbp+57h+var_4C], r15d
0x1800afe5c  mov     [rbp+57h+instance], r12
0x1800afe60  mov     rdi, r9
0x1800afe63  mov     r14d, r8d
0x1800afe66  mov     [rbp+57h+var_60], rax
0x1800afe6a  mov     rsi, rcx
0x1800afe6d  mov     [rbp+57h+var_58], r15
0x1800afe71  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800afe78  jz      short loc_1800AFE8C
0x1800afe7a  mov     [rsp+0C0h+var_90], r9; unsigned __int16 *
0x1800afe7f  mov     r9, rcx
0x1800afe82  mov     dword ptr [rsp+0C0h+var_98], r8d; unsigned __int16 *
0x1800afe87  call    WPP_SF_SSlq
0x1800afe8c  test    rdi, rdi
0x1800afe8f  jz      short loc_1800AFE94
0x1800afe91  mov     [rdi], r15
0x1800afe94  xor     r9d, r9d; unsigned __int16 *
0x1800afe97  lea     r8, ?c_wszDatabaseTempFilename@@3QBGB; "WebCacheV01.tmp"
0x1800afe9e  mov     rdx, rsi; unsigned __int16 *
0x1800afea1  lea     rcx, [rbp+57h+var_60]; this
0x1800afea5  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800afeaa  mov     ebx, eax
0x1800afeac  mov     r13d, 1
0x1800afeb2  test    eax, eax
0x1800afeb4  jns     short loc_1800AFF27
0x1800afeb6  mov     [rbp+57h+var_4C], 2F2h
0x1800afebd  mov     rcx, [rbp+57h+instance]; instance
0x1800afec1  cmp     rcx, r12
0x1800afec4  jz      short loc_1800AFED3
0x1800afec6  mov     edx, r13d; grbit
0x1800afec9  call    cs:__imp_JetTerm2
0x1800afecf  mov     [rbp+57h+instance], r12
0x1800afed3  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800afeda  jz      short loc_1800AFEF5
0x1800afedc  mov     edx, 26h ; '&'
0x1800afee1  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800afee8  mov     ecx, 40Ch
0x1800afeed  mov     r9d, ebx
0x1800afef0  call    WPP_SF_d
0x1800afef5  lea     rcx, [rbp+57h+var_60]; this
0x1800afef9  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800afefe  mov     eax, ebx
0x1800aff00  mov     rcx, [rbp+57h+var_40]
0x1800aff04  xor     rcx, rsp; StackCookie
0x1800aff07  call    __security_check_cookie
0x1800aff0c  mov     rbx, [rsp+0C0h+arg_8]
0x1800aff14  add     rsp, 90h
0x1800aff1b  pop     r15
0x1800aff1d  pop     r14
0x1800aff1f  pop     r13
0x1800aff21  pop     r12
0x1800aff23  pop     rdi
0x1800aff24  pop     rsi
0x1800aff25  pop     rbp
0x1800aff26  retn
0x1800aff27  xor     r9d, r9d; grbit
0x1800aff2a  lea     rdx, ?c_wszLocalInstance@@3QBGB; "WebCacheLocal"
0x1800aff31  xor     r8d, r8d; szDisplayName
0x1800aff34  lea     rcx, [rbp+57h+instance]; pinstance
0x1800aff38  call    cs:__imp_JetCreateInstance2W
0x1800aff3e  mov     ecx, eax; int
0x1800aff40  xor     edx, edx; int
0x1800aff42  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aff47  mov     ebx, eax
0x1800aff49  test    eax, eax
0x1800aff4b  js      loc_1800AFEBD
0x1800aff51  xor     r9d, r9d; lParam
0x1800aff54  mov     [rsp+0C0h+szParam], r15; szParam
0x1800aff59  xor     edx, edx; sesid
0x1800aff5b  lea     rcx, [rbp+57h+instance]; pinstance
0x1800aff5f  mov     r8d, 81h; paramid
0x1800aff65  call    cs:__imp_JetSetSystemParameterW
0x1800aff6b  mov     ecx, eax; int
0x1800aff6d  xor     edx, edx; int
0x1800aff6f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aff74  mov     ebx, eax
0x1800aff76  test    eax, eax
0x1800aff78  js      loc_1800AFEBD
0x1800aff7e  mov     r9, r13; lParam
0x1800aff81  mov     [rsp+0C0h+szParam], r15; szParam
0x1800aff86  xor     edx, edx; sesid
0x1800aff88  lea     rcx, [rbp+57h+instance]; pinstance
0x1800aff8c  mov     r8d, 82h; paramid
0x1800aff92  call    cs:__imp_JetSetSystemParameterW
0x1800aff98  mov     ecx, eax; int
0x1800aff9a  xor     edx, edx; int
0x1800aff9c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800affa1  mov     ebx, eax
0x1800affa3  test    eax, eax
0x1800affa5  js      loc_1800AFEBD
0x1800affab  xor     r9d, r9d; lParam
0x1800affae  lea     rax, ?c_wszDatabaseVersion@@3QBGB; "V01"
0x1800affb5  xor     edx, edx; sesid
0x1800affb7  mov     [rsp+0C0h+szParam], rax; szParam
0x1800affbc  lea     rcx, [rbp+57h+instance]; pinstance
0x1800affc0  lea     r8d, [r9+3]; paramid
0x1800affc4  call    cs:__imp_JetSetSystemParameterW
0x1800affca  mov     ecx, eax; int
0x1800affcc  xor     edx, edx; int
0x1800affce  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800affd3  mov     ebx, eax
0x1800affd5  test    eax, eax
0x1800affd7  js      loc_1800AFEBD
0x1800affdd  xor     r9d, r9d; lParam
0x1800affe0  mov     [rsp+0C0h+szParam], rsi; szParam
0x1800affe5  xor     edx, edx; sesid
0x1800affe7  lea     rcx, [rbp+57h+instance]; pinstance
0x1800affeb  lea     r8d, [r9+2]; paramid
0x1800affef  call    cs:__imp_JetSetSystemParameterW
0x1800afff5  mov     ecx, eax; int
0x1800afff7  xor     edx, edx; int
0x1800afff9  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800afffe  mov     ebx, eax
0x1800b0000  test    eax, eax
0x1800b0002  js      loc_1800AFEBD
0x1800b0008  xor     r9d, r9d; lParam
0x1800b000b  mov     [rsp+0C0h+szParam], rsi; szParam
0x1800b0010  xor     r8d, r8d; paramid
0x1800b0013  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b0017  xor     edx, edx; sesid
0x1800b0019  call    cs:__imp_JetSetSystemParameterW
0x1800b001f  mov     ecx, eax; int
0x1800b0021  xor     edx, edx; int
0x1800b0023  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b0028  mov     ebx, eax
0x1800b002a  test    eax, eax
0x1800b002c  js      loc_1800AFEBD
0x1800b0032  mov     rax, [rbp+57h+var_60]
0x1800b0036  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b003a  xor     r9d, r9d; lParam
0x1800b003d  mov     [rsp+0C0h+szParam], rax; szParam
0x1800b0042  mov     r8d, r13d; paramid
0x1800b0045  xor     edx, edx; sesid
0x1800b0047  call    cs:__imp_JetSetSystemParameterW
0x1800b004d  mov     ecx, eax; int
0x1800b004f  xor     edx, edx; int
0x1800b0051  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b0056  mov     ebx, eax
0x1800b0058  test    eax, eax
0x1800b005a  js      loc_1800AFEBD
0x1800b0060  xor     edx, edx; sesid
0x1800b0062  mov     [rsp+0C0h+szParam], r15; szParam
0x1800b0067  mov     r9, r13; lParam
0x1800b006a  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b006e  lea     r8d, [rdx+11h]; paramid
0x1800b0072  call    cs:__imp_JetSetSystemParameterW
0x1800b0078  mov     ecx, eax; int
0x1800b007a  xor     edx, edx; int
0x1800b007c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b0081  mov     ebx, eax
0x1800b0083  test    eax, eax
0x1800b0085  js      loc_1800AFEBD
0x1800b008b  xor     edx, edx; sesid
0x1800b008d  mov     [rsp+0C0h+szParam], r15; szParam
0x1800b0092  mov     r9, r13; lParam
0x1800b0095  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b0099  lea     r8d, [rdx+4Dh]; paramid
0x1800b009d  call    cs:__imp_JetSetSystemParameterW
0x1800b00a3  mov     ecx, eax; int
0x1800b00a5  xor     edx, edx; int
0x1800b00a7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b00ac  mov     ebx, eax
0x1800b00ae  test    eax, eax
0x1800b00b0  js      loc_1800AFEBD
0x1800b00b6  xor     edx, edx; sesid
0x1800b00b8  mov     [rsp+0C0h+szParam], r15; szParam
0x1800b00bd  mov     r9d, 200h; lParam
0x1800b00c3  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b00c7  lea     r8d, [rdx+0Bh]; paramid
0x1800b00cb  call    cs:__imp_JetSetSystemParameterW
0x1800b00d1  mov     ecx, eax; int
0x1800b00d3  xor     edx, edx; int
0x1800b00d5  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b00da  mov     ebx, eax
0x1800b00dc  test    eax, eax
0x1800b00de  js      loc_1800AFEBD
0x1800b00e4  xor     edx, edx; sesid
0x1800b00e6  mov     [rsp+0C0h+szParam], r15; szParam
0x1800b00eb  mov     r9d, 400h; lParam
0x1800b00f1  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b00f5  lea     r8d, [rdx+0Ch]; paramid
0x1800b00f9  call    cs:__imp_JetSetSystemParameterW
0x1800b00ff  mov     ecx, eax; int
0x1800b0101  xor     edx, edx; int
0x1800b0103  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b0108  mov     ebx, eax
0x1800b010a  test    eax, eax
0x1800b010c  js      loc_1800AFEBD
0x1800b0112  xor     edx, edx; sesid
0x1800b0114  mov     [rsp+0C0h+szParam], r15; szParam
0x1800b0119  mov     r9d, 500000h; lParam
0x1800b011f  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b0123  lea     r8d, [rdx+18h]; paramid
0x1800b0127  call    cs:__imp_JetSetSystemParameterW
0x1800b012d  mov     ecx, eax; int
0x1800b012f  xor     edx, edx; int
0x1800b0131  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b0136  mov     ebx, eax
0x1800b0138  test    eax, eax
0x1800b013a  js      loc_1800AFEBD
0x1800b0140  test    r14d, r14d
0x1800b0143  jz      short loc_1800B019B
0x1800b0145  xor     r9d, r9d; lParam
0x1800b0148  mov     [rsp+0C0h+szParam], r15; szParam
0x1800b014d  xor     edx, edx; sesid
0x1800b014f  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b0153  lea     r8d, [r9+2Dh]; paramid
0x1800b0157  call    cs:__imp_JetSetSystemParameterW
0x1800b015d  mov     ecx, eax; int
0x1800b015f  xor     edx, edx; int
0x1800b0161  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b0166  mov     ebx, eax
0x1800b0168  test    eax, eax
0x1800b016a  js      loc_1800AFEBD
0x1800b0170  xor     r9d, r9d; lParam
0x1800b0173  mov     [rsp+0C0h+szParam], r15; szParam
0x1800b0178  xor     edx, edx; sesid
0x1800b017a  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b017e  lea     r8d, [r9+36h]; paramid
0x1800b0182  call    cs:__imp_JetSetSystemParameterW
0x1800b0188  mov     ecx, eax; int
0x1800b018a  xor     edx, edx; int
0x1800b018c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b0191  mov     ebx, eax
0x1800b0193  test    eax, eax
0x1800b0195  js      loc_1800AFEBD
0x1800b019b  lea     rcx, [rbp+57h+instance]; pinstance
0x1800b019f  call    cs:__imp_JetInit
0x1800b01a5  mov     ecx, eax; int
0x1800b01a7  xor     edx, edx; int
0x1800b01a9  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b01ae  mov     ebx, eax
0x1800b01b0  test    eax, eax
0x1800b01b2  js      loc_1800AFEBD
0x1800b01b8  mov     rax, [rbp+57h+instance]
0x1800b01bc  mov     rcx, r12
0x1800b01bf  mov     [rdi], rax
0x1800b01c2  mov     [rbp+57h+instance], rcx
0x1800b01c6  jmp     loc_1800AFEC1
```
