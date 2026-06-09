# CDefaultConnectionHandler::LoadSDArbHandler(ISessionArbitrationHelperEx * *)

- ea: `0x180079fcc`
- end: `0x18007a27c`
- name: `?LoadSDArbHandler@CDefaultConnectionHandler@@QEAAJPEAPEAVISessionArbitrationHelperEx@@@Z`
- size: `688`
- prototype: `int(CDefaultConnectionHandler *__hidden this, struct ISessionArbitrationHelperEx **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077a74`

## callees

- `0x1800016a8`
- `0x180015310`
- `0x180028dd8`
- `0x180028e88`
- `0x180028f88`
- `0x180033f60`
- `0x180079fcc`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18007a174`
- `RPCRT4!UuidFromStringW` at `0x18007a174`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007a1d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007a1d3`

## string_xrefs

- `0x18007a0ee`: `CLSID`
- `0x18007a0af`: `SessionDirectory`
- `0x18007a12b`: `ReadRegString`
- `0x18007a1fb`: `CComUtils::CoCreateInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDefaultConnectionHandler::LoadSDArbHandler(CDefaultConnectionHandler *this, LPVOID *a2)
{
  int v3; // ebx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  char *v7; // rax
  int *v8; // rdx
  int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  RPC_WSTR *p_StringUuid; // rax
  char *v14; // rdx
  RPC_STATUS v15; // eax
  const char *v16; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-59h]
  LPVOID *ppva; // [rsp+20h] [rbp-59h]
  RPC_WSTR *v20; // [rsp+38h] [rbp-41h]
  unsigned int v21; // [rsp+40h] [rbp-39h] BYREF
  RPC_WSTR StringUuid; // [rsp+48h] [rbp-31h] BYREF
  const char *v23; // [rsp+50h] [rbp-29h] BYREF
  const char *v24; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-19h] BYREF
  int v26; // [rsp+70h] [rbp-9h]
  __int64 v27; // [rsp+78h] [rbp-1h]
  int v28; // [rsp+80h] [rbp+7h]
  int v29; // [rsp+84h] [rbp+Bh]
  _QWORD v30[2]; // [rsp+88h] [rbp+Fh] BYREF
  int v31; // [rsp+98h] [rbp+1Fh]
  HKEY v32; // [rsp+A0h] [rbp+27h]
  int v33; // [rsp+A8h] [rbp+2Fh]
  int v34; // [rsp+ACh] [rbp+33h]
  UUID Uuid; // [rsp+B0h] [rbp+37h] BYREF

  v3 = -2147467263;
  v30[0] = &CRegistry::`vftable';
  v30[1] = 0;
  v31 = 0;
  v32 = 0;
  v33 = -1;
  v34 = -1;
  v25[0] = &CRegistry::`vftable';
  v25[1] = 0;
  v26 = 0;
  v27 = 0;
  v28 = -1;
  v29 = -1;
  StringUuid = 0;
  Uuid = 0;
  if ( !CRegistry::OpenKey(
          (CRegistry *)v30,
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\SessionArbitrationHelper",
          0x20019u,
          (const unsigned __int16 *)ppv) )
  {
    if ( CRegistry::OpenKey((CRegistry *)v25, v32, L"SessionDirectory", 0x20019u, (const unsigned __int16 *)ppva) )
    {
      if ( (unsigned int)dword_18012E170 <= 4 )
        goto LABEL_23;
      v7 = "No SD arbitrator helper";
      v8 = &dword_18011236C;
      goto LABEL_4;
    }
    v9 = CRegistry::ReadRegString((CRegistry *)v25, L"CLSID", &StringUuid, &v21);
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    if ( v3 >= 0 )
    {
      v15 = UuidFromStringW(StringUuid, &Uuid);
      v3 = v15;
      if ( v15 > 0 )
        v3 = (unsigned __int16)v15 | 0x80070000;
      if ( v3 >= 0 )
      {
        v3 = CoCreateInstance(&Uuid, 0, 5u, &riid, a2);
        if ( v3 >= 0 )
          goto LABEL_23;
        v10 = dword_18012E170;
        if ( (unsigned int)dword_18012E170 <= 3 )
          goto LABEL_23;
        v24 = "LoadSDArbHandler";
        v16 = "CComUtils::CoCreateInstance";
        v14 = byte_18011228B;
      }
      else
      {
        if ( (unsigned int)dword_18012E170 <= 3 )
          goto LABEL_23;
        v24 = "LoadSDArbHandler";
        v16 = "UuidFromString";
        v14 = (char *)&word_1801122D6;
      }
      v23 = v16;
      StringUuid = (RPC_WSTR)"Warning HResult failed";
      v20 = (RPC_WSTR *)&v24;
      p_StringUuid = &StringUuid;
    }
    else
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_23;
      StringUuid = (RPC_WSTR)"LoadSDArbHandler";
      v23 = "ReadRegString";
      v24 = "Warning HResult failed";
      v20 = &StringUuid;
      p_StringUuid = (RPC_WSTR *)&v24;
      v14 = byte_180112321;
    }
    v21 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v10,
      (_DWORD)v14,
      v11,
      v12,
      (__int64)p_StringUuid,
      (__int64)&v23,
      (__int64)&v21,
      (__int64)v20);
    goto LABEL_23;
  }
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v7 = "No arbitrator defined";
    v8 = (int *)byte_18011239D;
LABEL_4:
    StringUuid = (RPC_WSTR)v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (_DWORD)v8,
      v5,
      v6,
      (__int64)&StringUuid);
  }
LABEL_23:
  CRegistry::~CRegistry((CRegistry *)v25);
  CRegistry::~CRegistry((CRegistry *)v30);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180079fcc  mov     [rsp-8+arg_0], rbx
0x180079fd1  mov     [rsp-8+arg_10], rdi
0x180079fd6  push    rbp
0x180079fd7  lea     rbp, [rsp-57h]
0x180079fdc  sub     rsp, 0D0h
0x180079fe3  mov     rax, cs:__security_cookie
0x180079fea  xor     rax, rsp
0x180079fed  mov     [rbp+57h+var_10], rax
0x180079ff1  mov     rdi, rdx
0x180079ff4  mov     ebx, 80004001h
0x180079ff9  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18007a000  mov     [rbp+57h+var_48], rcx
0x18007a004  mov     [rbp+57h+var_40], 0
0x18007a00c  mov     [rbp+57h+var_38], 0
0x18007a013  mov     [rbp+57h+var_30], 0
0x18007a01b  or      eax, 0FFFFFFFFh
0x18007a01e  mov     [rbp+57h+var_28], eax
0x18007a021  mov     [rbp+57h+var_24], eax
0x18007a024  mov     [rbp+57h+var_70], rcx
0x18007a028  mov     [rbp+57h+var_68], 0
0x18007a030  mov     [rbp+57h+var_60], 0
0x18007a037  mov     [rbp+57h+var_58], 0
0x18007a03f  mov     [rbp+57h+var_50], eax
0x18007a042  mov     [rbp+57h+var_4C], eax
0x18007a045  mov     [rbp+57h+StringUuid], 0
0x18007a04d  xorps   xmm0, xmm0
0x18007a050  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18007a054  mov     r9d, 20019h; unsigned int
0x18007a05a  lea     r8, aSystemCurrentc_15; "System\\CurrentControlSet\\Control\\Ter"...
0x18007a061  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18007a068  lea     rcx, [rbp+57h+var_48]; this
0x18007a06c  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18007a071  test    eax, eax
0x18007a073  jz      short loc_18007A0A9
0x18007a075  mov     eax, cs:dword_18012E170
0x18007a07b  cmp     eax, 4
0x18007a07e  jbe     loc_18007A245
0x18007a084  lea     rax, aNoArbitratorDe; "No arbitrator defined"
0x18007a08b  lea     rdx, byte_18011239D
0x18007a092  mov     [rbp+57h+StringUuid], rax
0x18007a096  lea     rax, [rbp+57h+StringUuid]
0x18007a09a  mov     [rsp+0D0h+ppv], rax
0x18007a09f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007a0a4  jmp     loc_18007A245
0x18007a0a9  mov     r9d, 20019h; unsigned int
0x18007a0af  lea     r8, aSessiondirecto; "SessionDirectory"
0x18007a0b6  mov     rdx, [rbp+57h+var_30]; HKEY
0x18007a0ba  lea     rcx, [rbp+57h+var_70]; this
0x18007a0be  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18007a0c3  test    eax, eax
0x18007a0c5  jz      short loc_18007A0E6
0x18007a0c7  mov     eax, cs:dword_18012E170
0x18007a0cd  cmp     eax, 4
0x18007a0d0  jbe     loc_18007A245
0x18007a0d6  lea     rax, aNoSdArbitrator; "No SD arbitrator helper"
0x18007a0dd  lea     rdx, dword_18011236C
0x18007a0e4  jmp     short loc_18007A092
0x18007a0e6  lea     r9, [rbp+57h+var_90]; unsigned int *
0x18007a0ea  lea     r8, [rbp+57h+StringUuid]; unsigned __int16 **
0x18007a0ee  lea     rdx, aClsid; "CLSID"
0x18007a0f5  lea     rcx, [rbp+57h+var_70]; this
0x18007a0f9  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x18007a0fe  mov     ebx, eax
0x18007a100  test    eax, eax
0x18007a102  jle     short loc_18007A10D
0x18007a104  movzx   ebx, ax
0x18007a107  or      ebx, 80070000h
0x18007a10d  test    ebx, ebx
0x18007a10f  jns     short loc_18007A16C
0x18007a111  mov     eax, cs:dword_18012E170
0x18007a117  cmp     eax, 3
0x18007a11a  jbe     loc_18007A245
0x18007a120  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x18007a127  mov     [rbp+57h+StringUuid], rax
0x18007a12b  lea     rax, aReadregstring; "ReadRegString"
0x18007a132  mov     [rbp+57h+var_80], rax
0x18007a136  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007a13d  mov     [rbp+57h+var_78], rax
0x18007a141  lea     rax, [rbp+57h+StringUuid]
0x18007a145  mov     [rsp+0D0h+var_98], rax
0x18007a14a  lea     rax, [rbp+57h+var_90]
0x18007a14e  mov     [rsp+0D0h+var_A0], rax
0x18007a153  lea     rax, [rbp+57h+var_80]
0x18007a157  mov     [rsp+0D0h+var_A8], rax
0x18007a15c  lea     rax, [rbp+57h+var_78]
0x18007a160  lea     rdx, byte_180112321
0x18007a167  jmp     loc_18007A237
0x18007a16c  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18007a170  mov     rcx, [rbp+57h+StringUuid]; StringUuid
0x18007a174  call    cs:__imp_UuidFromStringW
0x18007a17b  nop     dword ptr [rax+rax+00h]
0x18007a180  mov     ebx, eax
0x18007a182  test    eax, eax
0x18007a184  jle     short loc_18007A18F
0x18007a186  movzx   ebx, ax
0x18007a189  or      ebx, 80070000h
0x18007a18f  test    ebx, ebx
0x18007a191  jns     short loc_18007A1BD
0x18007a193  mov     eax, cs:dword_18012E170
0x18007a199  cmp     eax, 3
0x18007a19c  jbe     loc_18007A245
0x18007a1a2  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x18007a1a9  mov     [rbp+57h+var_78], rax
0x18007a1ad  lea     rax, aUuidfromstring; "UuidFromString"
0x18007a1b4  lea     rdx, word_1801122D6
0x18007a1bb  jmp     short loc_18007A209
0x18007a1bd  mov     [rsp+0D0h+ppv], rdi; ppv
0x18007a1c2  lea     r9, riid; riid
0x18007a1c9  xor     edx, edx; pUnkOuter
0x18007a1cb  lea     r8d, [rdx+5]; dwClsContext
0x18007a1cf  lea     rcx, [rbp+57h+Uuid]; rclsid
0x18007a1d3  call    cs:__imp_CoCreateInstance
0x18007a1da  nop     dword ptr [rax+rax+00h]
0x18007a1df  mov     ebx, eax
0x18007a1e1  test    eax, eax
0x18007a1e3  jns     short loc_18007A245
0x18007a1e5  mov     ecx, cs:dword_18012E170
0x18007a1eb  cmp     ecx, 3
0x18007a1ee  jbe     short loc_18007A245
0x18007a1f0  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x18007a1f7  mov     [rbp+57h+var_78], rax
0x18007a1fb  lea     rax, aCcomutilsCocre; "CComUtils::CoCreateInstance"
0x18007a202  lea     rdx, byte_18011228B
0x18007a209  mov     [rbp+57h+var_80], rax
0x18007a20d  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007a214  mov     [rbp+57h+StringUuid], rax
0x18007a218  lea     rax, [rbp+57h+var_78]
0x18007a21c  mov     [rsp+0D0h+var_98], rax
0x18007a221  lea     rax, [rbp+57h+var_90]
0x18007a225  mov     [rsp+0D0h+var_A0], rax
0x18007a22a  lea     rax, [rbp+57h+var_80]
0x18007a22e  mov     [rsp+0D0h+var_A8], rax
0x18007a233  lea     rax, [rbp+57h+StringUuid]
0x18007a237  mov     [rsp+0D0h+ppv], rax
0x18007a23c  mov     [rbp+57h+var_90], ebx
0x18007a23f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007a244  nop
0x18007a245  lea     rcx, [rbp+57h+var_70]; this
0x18007a249  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18007a24e  nop
0x18007a24f  lea     rcx, [rbp+57h+var_48]; this
0x18007a253  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18007a258  mov     eax, ebx
0x18007a25a  mov     rcx, [rbp+57h+var_10]
0x18007a25e  xor     rcx, rsp; StackCookie
0x18007a261  call    __security_check_cookie
0x18007a266  lea     r11, [rsp+0D0h+var_s0]
0x18007a26e  mov     rbx, [r11+10h]
0x18007a272  mov     rdi, [r11+20h]
0x18007a276  mov     rsp, r11
0x18007a279  pop     rbp
0x18007a27a  retn
```
