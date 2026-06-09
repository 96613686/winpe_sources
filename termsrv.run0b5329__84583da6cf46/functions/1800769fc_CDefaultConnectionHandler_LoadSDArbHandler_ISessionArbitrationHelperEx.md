# CDefaultConnectionHandler::LoadSDArbHandler(ISessionArbitrationHelperEx * *)

- ea: `0x1800769fc`
- end: `0x180076c9f`
- name: `?LoadSDArbHandler@CDefaultConnectionHandler@@QEAAJPEAPEAVISessionArbitrationHelperEx@@@Z`
- size: `675`
- prototype: `int(CDefaultConnectionHandler *__hidden this, struct ISessionArbitrationHelperEx **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800744ec`

## callees

- `0x180001688`
- `0x1800148f0`
- `0x1800279a8`
- `0x180027a44`
- `0x180027b44`
- `0x1800321f0`
- `0x1800769fc`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180076ba4`
- `RPCRT4!UuidFromStringW` at `0x180076ba4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180076bfd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180076bfd`

## string_xrefs

- `0x180076b1e`: `CLSID`
- `0x180076adf`: `SessionDirectory`
- `0x180076b5b`: `ReadRegString`
- `0x180076c1f`: `CComUtils::CoCreateInstance`

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
      if ( (unsigned int)dword_180128170 <= 4 )
        goto LABEL_23;
      v7 = "No SD arbitrator helper";
      v8 = &dword_18010C2EC;
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
        v10 = dword_180128170;
        if ( (unsigned int)dword_180128170 <= 3 )
          goto LABEL_23;
        v24 = "LoadSDArbHandler";
        v16 = "CComUtils::CoCreateInstance";
        v14 = byte_18010C20B;
      }
      else
      {
        if ( (unsigned int)dword_180128170 <= 3 )
          goto LABEL_23;
        v24 = "LoadSDArbHandler";
        v16 = "UuidFromString";
        v14 = (char *)&word_18010C256;
      }
      v23 = v16;
      StringUuid = (RPC_WSTR)"Warning HResult failed";
      v20 = (RPC_WSTR *)&v24;
      p_StringUuid = &StringUuid;
    }
    else
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_23;
      StringUuid = (RPC_WSTR)"LoadSDArbHandler";
      v23 = "ReadRegString";
      v24 = "Warning HResult failed";
      v20 = &StringUuid;
      p_StringUuid = (RPC_WSTR *)&v24;
      v14 = byte_18010C2A1;
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
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v7 = "No arbitrator defined";
    v8 = (int *)byte_18010C31D;
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
0x1800769fc  mov     [rsp-8+arg_0], rbx
0x180076a01  mov     [rsp-8+arg_10], rdi
0x180076a06  push    rbp
0x180076a07  lea     rbp, [rsp-57h]
0x180076a0c  sub     rsp, 0D0h
0x180076a13  mov     rax, cs:__security_cookie
0x180076a1a  xor     rax, rsp
0x180076a1d  mov     [rbp+57h+var_10], rax
0x180076a21  mov     rdi, rdx
0x180076a24  mov     ebx, 80004001h
0x180076a29  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180076a30  mov     [rbp+57h+var_48], rcx
0x180076a34  mov     [rbp+57h+var_40], 0
0x180076a3c  mov     [rbp+57h+var_38], 0
0x180076a43  mov     [rbp+57h+var_30], 0
0x180076a4b  or      eax, 0FFFFFFFFh
0x180076a4e  mov     [rbp+57h+var_28], eax
0x180076a51  mov     [rbp+57h+var_24], eax
0x180076a54  mov     [rbp+57h+var_70], rcx
0x180076a58  mov     [rbp+57h+var_68], 0
0x180076a60  mov     [rbp+57h+var_60], 0
0x180076a67  mov     [rbp+57h+var_58], 0
0x180076a6f  mov     [rbp+57h+var_50], eax
0x180076a72  mov     [rbp+57h+var_4C], eax
0x180076a75  mov     [rbp+57h+StringUuid], 0
0x180076a7d  xorps   xmm0, xmm0
0x180076a80  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180076a84  mov     r9d, 20019h; unsigned int
0x180076a8a  lea     r8, aSystemCurrentc_15; "System\\CurrentControlSet\\Control\\Ter"...
0x180076a91  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180076a98  lea     rcx, [rbp+57h+var_48]; this
0x180076a9c  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180076aa1  test    eax, eax
0x180076aa3  jz      short loc_180076AD9
0x180076aa5  mov     eax, cs:dword_180128170
0x180076aab  cmp     eax, 4
0x180076aae  jbe     loc_180076C69
0x180076ab4  lea     rax, aNoArbitratorDe; "No arbitrator defined"
0x180076abb  lea     rdx, byte_18010C31D
0x180076ac2  mov     [rbp+57h+StringUuid], rax
0x180076ac6  lea     rax, [rbp+57h+StringUuid]
0x180076aca  mov     [rsp+0D0h+ppv], rax
0x180076acf  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180076ad4  jmp     loc_180076C69
0x180076ad9  mov     r9d, 20019h; unsigned int
0x180076adf  lea     r8, aSessiondirecto; "SessionDirectory"
0x180076ae6  mov     rdx, [rbp+57h+var_30]; HKEY
0x180076aea  lea     rcx, [rbp+57h+var_70]; this
0x180076aee  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180076af3  test    eax, eax
0x180076af5  jz      short loc_180076B16
0x180076af7  mov     eax, cs:dword_180128170
0x180076afd  cmp     eax, 4
0x180076b00  jbe     loc_180076C69
0x180076b06  lea     rax, aNoSdArbitrator; "No SD arbitrator helper"
0x180076b0d  lea     rdx, dword_18010C2EC
0x180076b14  jmp     short loc_180076AC2
0x180076b16  lea     r9, [rbp+57h+var_90]; unsigned int *
0x180076b1a  lea     r8, [rbp+57h+StringUuid]; unsigned __int16 **
0x180076b1e  lea     rdx, aClsid; "CLSID"
0x180076b25  lea     rcx, [rbp+57h+var_70]; this
0x180076b29  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180076b2e  mov     ebx, eax
0x180076b30  test    eax, eax
0x180076b32  jle     short loc_180076B3D
0x180076b34  movzx   ebx, ax
0x180076b37  or      ebx, 80070000h
0x180076b3d  test    ebx, ebx
0x180076b3f  jns     short loc_180076B9C
0x180076b41  mov     eax, cs:dword_180128170
0x180076b47  cmp     eax, 3
0x180076b4a  jbe     loc_180076C69
0x180076b50  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x180076b57  mov     [rbp+57h+StringUuid], rax
0x180076b5b  lea     rax, aReadregstring; "ReadRegString"
0x180076b62  mov     [rbp+57h+var_80], rax
0x180076b66  lea     rax, aWarningHresult; "Warning HResult failed"
0x180076b6d  mov     [rbp+57h+var_78], rax
0x180076b71  lea     rax, [rbp+57h+StringUuid]
0x180076b75  mov     [rsp+0D0h+var_98], rax
0x180076b7a  lea     rax, [rbp+57h+var_90]
0x180076b7e  mov     [rsp+0D0h+var_A0], rax
0x180076b83  lea     rax, [rbp+57h+var_80]
0x180076b87  mov     [rsp+0D0h+var_A8], rax
0x180076b8c  lea     rax, [rbp+57h+var_78]
0x180076b90  lea     rdx, byte_18010C2A1
0x180076b97  jmp     loc_180076C5B
0x180076b9c  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180076ba0  mov     rcx, [rbp+57h+StringUuid]; StringUuid
0x180076ba4  call    cs:__imp_UuidFromStringW
0x180076baa  mov     ebx, eax
0x180076bac  test    eax, eax
0x180076bae  jle     short loc_180076BB9
0x180076bb0  movzx   ebx, ax
0x180076bb3  or      ebx, 80070000h
0x180076bb9  test    ebx, ebx
0x180076bbb  jns     short loc_180076BE7
0x180076bbd  mov     eax, cs:dword_180128170
0x180076bc3  cmp     eax, 3
0x180076bc6  jbe     loc_180076C69
0x180076bcc  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x180076bd3  mov     [rbp+57h+var_78], rax
0x180076bd7  lea     rax, aUuidfromstring; "UuidFromString"
0x180076bde  lea     rdx, word_18010C256
0x180076be5  jmp     short loc_180076C2D
0x180076be7  mov     [rsp+0D0h+ppv], rdi; ppv
0x180076bec  lea     r9, riid; riid
0x180076bf3  xor     edx, edx; pUnkOuter
0x180076bf5  lea     r8d, [rdx+5]; dwClsContext
0x180076bf9  lea     rcx, [rbp+57h+Uuid]; rclsid
0x180076bfd  call    cs:__imp_CoCreateInstance
0x180076c03  mov     ebx, eax
0x180076c05  test    eax, eax
0x180076c07  jns     short loc_180076C69
0x180076c09  mov     ecx, cs:dword_180128170
0x180076c0f  cmp     ecx, 3
0x180076c12  jbe     short loc_180076C69
0x180076c14  lea     rax, aLoadsdarbhandl; "LoadSDArbHandler"
0x180076c1b  mov     [rbp+57h+var_78], rax
0x180076c1f  lea     rax, aCcomutilsCocre; "CComUtils::CoCreateInstance"
0x180076c26  lea     rdx, byte_18010C20B
0x180076c2d  mov     [rbp+57h+var_80], rax
0x180076c31  lea     rax, aWarningHresult; "Warning HResult failed"
0x180076c38  mov     [rbp+57h+StringUuid], rax
0x180076c3c  lea     rax, [rbp+57h+var_78]
0x180076c40  mov     [rsp+0D0h+var_98], rax
0x180076c45  lea     rax, [rbp+57h+var_90]
0x180076c49  mov     [rsp+0D0h+var_A0], rax
0x180076c4e  lea     rax, [rbp+57h+var_80]
0x180076c52  mov     [rsp+0D0h+var_A8], rax
0x180076c57  lea     rax, [rbp+57h+StringUuid]
0x180076c5b  mov     [rsp+0D0h+ppv], rax
0x180076c60  mov     [rbp+57h+var_90], ebx
0x180076c63  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180076c68  nop
0x180076c69  lea     rcx, [rbp+57h+var_70]; this
0x180076c6d  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180076c72  nop
0x180076c73  lea     rcx, [rbp+57h+var_48]; this
0x180076c77  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180076c7c  mov     eax, ebx
0x180076c7e  mov     rcx, [rbp+57h+var_10]
0x180076c82  xor     rcx, rsp; StackCookie
0x180076c85  call    __security_check_cookie
0x180076c8a  lea     r11, [rsp+0D0h+var_s0]
0x180076c92  mov     rbx, [r11+10h]
0x180076c96  mov     rdi, [r11+20h]
0x180076c9a  mov     rsp, r11
0x180076c9d  pop     rbp
0x180076c9e  retn
```
