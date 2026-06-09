# CSpp::_SplitWriterList(int,ushort const *,ulong *,_GUID * *)

- ea: `0x18001e898`
- end: `0x18001eae1`
- name: `?_SplitWriterList@CSpp@@AEAAJHPEBGPEAKPEAPEAU_GUID@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(CSpp *this, int, const unsigned __int16 *, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018cb0`

## callees

- `0x1800041d4`
- `0x18000702c`
- `0x18000e040`
- `0x18001b5a4`
- `0x18001e898`
- `0x180020908`
- `0x1800256e4`
- `0x180025844`
- `0x1800268b4`
- `0x1800269ac`
- `0x18003532c`
- `0x180035b00`
- `0x180035bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001e9d1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001e9d1`

## string_xrefs

- `0x18001e909`: `CSpp::_SplitWriterList`
- `0x18001e9e3`: `EnabledWriters`
- `0x18001e9ea`: `DisabledWriters`

## pseudocode

```c
__int64 __fastcall CSpp::_SplitWriterList(
        CSpp *this,
        int a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        struct _GUID **a5)
{
  const unsigned __int16 *v6; // rsi
  struct _GUID **v8; // rdi
  __int16 v9; // ax
  int Instance; // eax
  int IsNonDisableWriter; // ebx
  bool v12; // sf
  const unsigned __int16 *v13; // r12
  unsigned int v14; // edx
  CSpp *v15; // rcx
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // r9
  unsigned int v18; // edx
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // r9
  struct _GUID *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  int v25; // [rsp+30h] [rbp-61h] BYREF
  __int16 v26; // [rsp+34h] [rbp-5Dh]
  __int16 v27; // [rsp+36h] [rbp-5Bh]
  void *Block[2]; // [rsp+70h] [rbp-21h] BYREF
  LPCOLESTR lpsz; // [rsp+80h] [rbp-11h] BYREF
  __int64 v30; // [rsp+88h] [rbp-9h]
  GUID pclsid; // [rsp+90h] [rbp-1h] BYREF

  v6 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v25, "CSpp::_SplitWriterList", 6818, 1);
  lpsz = &FileName;
  Block[0] = 0;
  v8 = 0;
  v30 = 0;
  pclsid = 0;
  if ( a5 )
    *a5 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = 6830;
  if ( !v6 || (v26 = 6830, v9 = 6831, !a5) )
  {
    IsNonDisableWriter = -2147024809;
    v25 = -2147024809;
    goto LABEL_28;
  }
  v25 = 0;
  v26 = 6831;
  Instance = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(Block);
  v8 = (struct _GUID **)Block[0];
  IsNonDisableWriter = Instance;
  v25 = Instance;
  v12 = Instance < 0;
  v9 = 6833;
  if ( v12 )
  {
LABEL_28:
    v27 = v9;
    goto LABEL_29;
  }
  v26 = 6833;
  while ( *v6 )
  {
    IsNonDisableWriter = CBsString::Set((CBsString *)&lpsz, v6);
    v25 = IsNonDisableWriter;
    v9 = 6837;
    if ( IsNonDisableWriter < 0 )
      goto LABEL_28;
    v13 = lpsz;
    v26 = 6837;
    if ( CLSIDFromString(lpsz, &pclsid) >= 0 )
    {
      if ( !a2 )
        goto LABEL_23;
      IsNonDisableWriter = CSpp::_IsNonDisableWriter(v15, &pclsid);
      v25 = IsNonDisableWriter;
      v9 = 6853;
      if ( IsNonDisableWriter < 0 )
        goto LABEL_28;
      v26 = 6853;
      if ( IsNonDisableWriter )
      {
LABEL_23:
        *(GUID *)Block = pclsid;
        v25 = CSxSimpleArray<_GUID>::Append(v8, Block);
        IsNonDisableWriter = v25;
        v9 = 6864;
        if ( v25 < 0 )
          goto LABEL_28;
        v26 = 6864;
      }
      else
      {
        Log_SPP_WARNING_NONDISABLEWRITER((struct CSxFunctionTracer *)&v25, v18, v19, v20, v13);
      }
    }
    else
    {
      v17 = L"DisabledWriters";
      if ( !a2 )
        v17 = L"EnabledWriters";
      Log_SPP_WARNING_MALFORMED_GUID((struct CSxFunctionTracer *)&v25, v14, v16, v17, v13);
    }
    v6 += (unsigned int)(v30 + 1);
  }
  *a4 = *((_DWORD *)v8 + 4);
  v21 = v8[1];
  v8[1] = 0;
  v8[2] = 0;
  IsNonDisableWriter = v25;
  *a5 = v21;
LABEL_29:
  CBsString::_Release((unsigned __int16 **)&lpsz);
  if ( v8 )
    CSxSimpleArray<_GUID>::Release(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v25, v22, v23);
  return (unsigned int)IsNonDisableWriter;
}

```

## disassembly

```asm
0x18001e898  mov     [rsp-8+arg_0], rbx
0x18001e89d  push    rbp
0x18001e89e  push    rsi
0x18001e89f  push    rdi
0x18001e8a0  push    r12
0x18001e8a2  push    r13
0x18001e8a4  push    r14
0x18001e8a6  push    r15
0x18001e8a8  lea     rbp, [rsp-1Fh]
0x18001e8ad  sub     rsp, 0B0h
0x18001e8b4  mov     rax, cs:__security_cookie
0x18001e8bb  xor     rax, rsp
0x18001e8be  mov     [rbp+4Fh+var_40], rax
0x18001e8c2  mov     r14, [rbp+4Fh+arg_20]
0x18001e8c6  mov     r15, r9
0x18001e8c9  mov     rsi, r8
0x18001e8cc  mov     r13d, edx
0x18001e8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8d6  lea     rax, WPP_GLOBAL_Control
0x18001e8dd  cmp     rcx, rax
0x18001e8e0  jz      short loc_18001E903
0x18001e8e2  test    dword ptr [rcx+1Ch], 20000000h
0x18001e8e9  jz      short loc_18001E903
0x18001e8eb  mov     rcx, [rcx+10h]
0x18001e8ef  mov     r9, r8
0x18001e8f2  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001e8f9  mov     edx, 76h ; 'v'
0x18001e8fe  call    WPP_SF_S
0x18001e903  mov     r9d, 1; unsigned __int16
0x18001e909  lea     rdx, aCsppSplitwrite; "CSpp::_SplitWriterList"
0x18001e910  mov     r8d, 1AA2h; unsigned __int16
0x18001e916  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001e91a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e91f  xor     r12d, r12d
0x18001e922  lea     rax, FileName
0x18001e929  mov     [rbp+4Fh+lpsz], rax
0x18001e92d  xorps   xmm0, xmm0
0x18001e930  mov     [rbp+4Fh+Block], r12
0x18001e934  mov     edi, r12d
0x18001e937  mov     [rbp+4Fh+var_58], r12
0x18001e93b  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x18001e93f  test    r14, r14
0x18001e942  jz      short loc_18001E947
0x18001e944  mov     [r14], r12
0x18001e947  test    r15, r15
0x18001e94a  jz      short loc_18001E94F
0x18001e94c  mov     [r15], r12d
0x18001e94f  mov     eax, 1AAEh
0x18001e954  test    rsi, rsi
0x18001e957  jz      loc_18001EA8D
0x18001e95d  mov     [rbp+4Fh+var_AC], ax
0x18001e961  mov     eax, 1AAFh
0x18001e966  test    r14, r14
0x18001e969  jz      loc_18001EA8D
0x18001e96f  lea     rcx, [rbp+4Fh+Block]
0x18001e973  mov     [rbp+4Fh+var_B0], r12d
0x18001e977  mov     [rbp+4Fh+var_AC], ax
0x18001e97b  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18001e980  mov     rdi, [rbp+4Fh+Block]
0x18001e984  mov     ebx, eax
0x18001e986  mov     [rbp+4Fh+var_B0], eax
0x18001e989  test    eax, eax
0x18001e98b  mov     eax, 1AB1h
0x18001e990  js      loc_18001EA95
0x18001e996  mov     [rbp+4Fh+var_AC], ax
0x18001e99a  cmp     [rsi], r12w
0x18001e99e  jz      loc_18001EA6F
0x18001e9a4  mov     rdx, rsi; unsigned __int16 *
0x18001e9a7  lea     rcx, [rbp+4Fh+lpsz]; this
0x18001e9ab  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001e9b0  mov     ebx, eax
0x18001e9b2  mov     [rbp+4Fh+var_B0], eax
0x18001e9b5  test    eax, eax
0x18001e9b7  mov     eax, 1AB5h
0x18001e9bc  js      loc_18001EA95
0x18001e9c2  mov     r12, [rbp+4Fh+lpsz]
0x18001e9c6  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x18001e9ca  mov     rcx, r12; lpsz
0x18001e9cd  mov     [rbp+4Fh+var_AC], ax
0x18001e9d1  call    cs:__imp_CLSIDFromString
0x18001e9d7  test    eax, eax
0x18001e9d9  jns     short loc_18001EA03
0x18001e9db  test    r13d, r13d
0x18001e9de  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x18001e9e3  lea     rax, ValueName; "EnabledWriters"
0x18001e9ea  lea     r9, aDisabledwriter; "DisabledWriters"
0x18001e9f1  cmovz   r9, rax; unsigned __int16 *
0x18001e9f5  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001e9f9  call    ?Log_SPP_WARNING_MALFORMED_GUID@@YAJPEAVCSxFunctionTracer@@KPEBG11@Z; Log_SPP_WARNING_MALFORMED_GUID(CSxFunctionTracer *,ulong,ushort const *,ushort const *,ushort const *)
0x18001e9fe  xor     r12d, r12d
0x18001ea01  jmp     short loc_18001EA61
0x18001ea03  test    r13d, r13d
0x18001ea06  jz      short loc_18001EA37
0x18001ea08  lea     rdx, [rbp+4Fh+pclsid]; struct _GUID *
0x18001ea0c  call    ?_IsNonDisableWriter@CSpp@@AEAAJPEBU_GUID@@@Z; CSpp::_IsNonDisableWriter(_GUID const *)
0x18001ea11  mov     ebx, eax
0x18001ea13  mov     [rbp+4Fh+var_B0], eax
0x18001ea16  test    eax, eax
0x18001ea18  mov     eax, 1AC5h
0x18001ea1d  js      short loc_18001EA95
0x18001ea1f  mov     [rbp+4Fh+var_AC], ax
0x18001ea23  test    ebx, ebx
0x18001ea25  jnz     short loc_18001EA37
0x18001ea27  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001ea2b  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x18001ea30  call    ?Log_SPP_WARNING_NONDISABLEWRITER@@YAJPEAVCSxFunctionTracer@@KPEBG11@Z; Log_SPP_WARNING_NONDISABLEWRITER(CSxFunctionTracer *,ulong,ushort const *,ushort const *,ushort const *)
0x18001ea35  jmp     short loc_18001E9FE
0x18001ea37  movaps  xmm0, xmmword ptr [rbp+4Fh+pclsid.Data1]
0x18001ea3b  lea     rdx, [rbp+4Fh+Block]
0x18001ea3f  mov     rcx, rdi
0x18001ea42  movdqa  xmmword ptr [rbp+4Fh+Block], xmm0
0x18001ea47  call    ?Append@?$CSxSimpleArray@U_GUID@@@@QEAAJU_GUID@@@Z; CSxSimpleArray<_GUID>::Append(_GUID)
0x18001ea4c  xor     r12d, r12d
0x18001ea4f  mov     [rbp+4Fh+var_B0], eax
0x18001ea52  test    eax, eax
0x18001ea54  mov     ebx, eax
0x18001ea56  mov     eax, 1AD0h
0x18001ea5b  js      short loc_18001EA95
0x18001ea5d  mov     [rbp+4Fh+var_AC], ax
0x18001ea61  mov     eax, dword ptr [rbp+4Fh+var_58]
0x18001ea64  inc     eax
0x18001ea66  lea     rsi, [rsi+rax*2]
0x18001ea6a  jmp     loc_18001E99A
0x18001ea6f  mov     eax, [rdi+10h]
0x18001ea72  mov     [r15], eax
0x18001ea75  mov     rax, [rdi+8]
0x18001ea79  mov     [rdi+8], r12
0x18001ea7d  mov     qword ptr [rdi+10h], 0
0x18001ea85  mov     ebx, [rbp+4Fh+var_B0]
0x18001ea88  mov     [r14], rax
0x18001ea8b  jmp     short loc_18001EA99
0x18001ea8d  mov     ebx, 80070057h
0x18001ea92  mov     [rbp+4Fh+var_B0], ebx
0x18001ea95  mov     [rbp+4Fh+var_AA], ax
0x18001ea99  lea     rcx, [rbp+4Fh+lpsz]; this
0x18001ea9d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001eaa2  test    rdi, rdi
0x18001eaa5  jz      short loc_18001EAAF
0x18001eaa7  mov     rcx, rdi; Block
0x18001eaaa  call    ?Release@?$CSxSimpleArray@U_GUID@@@@QEAAKXZ; CSxSimpleArray<_GUID>::Release(void)
0x18001eaaf  lea     rcx, [rbp+4Fh+var_B0]; this
0x18001eab3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001eab8  mov     eax, ebx
0x18001eaba  mov     rcx, [rbp+4Fh+var_40]
0x18001eabe  xor     rcx, rsp; StackCookie
0x18001eac1  call    __security_check_cookie
0x18001eac6  mov     rbx, [rsp+0E0h+arg_0]
0x18001eace  add     rsp, 0B0h
0x18001ead5  pop     r15
0x18001ead7  pop     r14
0x18001ead9  pop     r13
0x18001eadb  pop     r12
0x18001eadd  pop     rdi
0x18001eade  pop     rsi
0x18001eadf  pop     rbp
0x18001eae0  retn
```
