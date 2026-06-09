# SM_CLUSTER::OpenResourceById(_GUID *)

- ea: `0x140003c80`
- end: `0x140003dd7`
- name: `?OpenResourceById@SM_CLUSTER@@QEAAPEAU_HRESOURCE@@PEAU_GUID@@@Z`
- size: `343`
- prototype: `struct _HRESOURCE *__fastcall(HCLUSTER *this, struct _GUID *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003494`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x140003c80`
- `0x1400041a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003cee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d43`
- `RPCRT4!RpcStringFreeW` at `0x140003d30`
- `RPCRT4!RpcStringFreeW` at `0x140003d30`
- `RPCRT4!UuidToStringW` at `0x140003ce2`
- `RPCRT4!UuidToStringW` at `0x140003ce2`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x140003d1f`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x140003d1f`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x140003cfd`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterResource` at `0x140003cfd`

## string_xrefs

- `0x140003c9c`: `SM_CLUSTER::OpenResourceById`

## pseudocode

```c
struct _HRESOURCE *__fastcall SM_CLUSTER::OpenResourceById(HCLUSTER *this, struct _GUID *a2, int a3, int a4)
{
  struct _HRESOURCE *v6; // rbx
  RPC_STATUS v7; // eax
  SM_CLUSTER *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  struct _HRESOURCE *v11; // rax
  struct _HRESOURCE *v12; // rdi
  DWORD LastError; // ecx
  int v14; // r8d
  int v15; // r9d
  RPC_WSTR StringUuid; // [rsp+40h] [rbp-10h] BYREF
  const char *v18; // [rsp+48h] [rbp-8h] BYREF
  int v19; // [rsp+80h] [rbp+30h] BYREF
  const char *v20; // [rsp+88h] [rbp+38h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v19 = 236;
    v20 = "SM_CLUSTER::OpenResourceById";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)word_140010C7A,
      a3,
      a4,
      (__int64)&v20,
      (__int64)&v19);
  }
  v6 = 0;
  StringUuid = 0;
  v7 = UuidToStringW(a2, &StringUuid);
  if ( v7 )
  {
    SetLastError(v7);
  }
  else
  {
    v11 = OpenClusterResource(*this, StringUuid);
    v12 = v11;
    if ( v11 )
    {
      if ( SM_CLUSTER::WaitForResourceOnline(v8, v11) )
        v6 = v12;
      else
        CloseClusterResource(v12);
    }
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( v6 )
  {
    if ( (unsigned int)dword_140014048 > 5 )
    {
      v19 = 271;
      v20 = "SM_CLUSTER::OpenResourceById";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)byte_140010D91,
        v9,
        v10,
        (__int64)&v20,
        (__int64)&v19);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_140014048 > 2 )
    {
      v19 = LastError;
      LODWORD(v20) = 271;
      v18 = "SM_CLUSTER::OpenResourceById";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        LastError,
        (unsigned int)word_140010DF2,
        v14,
        v15,
        (__int64)&v18,
        (__int64)&v20,
        (__int64)&v19);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140003c80  mov     r11, rsp
0x140003c83  mov     [r11+8], rbx
0x140003c87  mov     [r11+10h], rsi
0x140003c8b  push    rbp
0x140003c8c  push    rdi
0x140003c8d  push    r15
0x140003c8f  mov     rbp, rsp
0x140003c92  sub     rsp, 50h
0x140003c96  mov     eax, cs:dword_140014048
0x140003c9c  lea     r15, aSmClusterOpenr; "SM_CLUSTER::OpenResourceById"
0x140003ca3  mov     rdi, rdx
0x140003ca6  mov     rsi, rcx
0x140003ca9  cmp     eax, 5
0x140003cac  jbe     short loc_140003CD5
0x140003cae  lea     rax, [rbp+arg_10]
0x140003cb2  mov     [rbp+arg_10], 0ECh
0x140003cb9  mov     [r11-40h], rax
0x140003cbd  lea     rdx, word_140010C7A
0x140003cc4  lea     rax, [rbp+arg_18]
0x140003cc8  mov     [rbp+arg_18], r15
0x140003ccc  mov     [r11-48h], rax
0x140003cd0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003cd5  xor     ebx, ebx
0x140003cd7  lea     rdx, [rbp+StringUuid]; StringUuid
0x140003cdb  mov     rcx, rdi; Uuid
0x140003cde  mov     [rbp+StringUuid], rbx
0x140003ce2  call    cs:__imp_UuidToStringW
0x140003ce8  test    eax, eax
0x140003cea  jz      short loc_140003CF6
0x140003cec  mov     ecx, eax; dwErrCode
0x140003cee  call    cs:__imp_SetLastError
0x140003cf4  jmp     short loc_140003D25
0x140003cf6  mov     rdx, [rbp+StringUuid]; lpszResourceName
0x140003cfa  mov     rcx, [rsi]; hCluster
0x140003cfd  call    cs:__imp_OpenClusterResource
0x140003d03  mov     rdi, rax
0x140003d06  test    rax, rax
0x140003d09  jz      short loc_140003D25
0x140003d0b  mov     rdx, rax; struct _HRESOURCE *
0x140003d0e  call    ?WaitForResourceOnline@SM_CLUSTER@@AEAAHPEAU_HRESOURCE@@@Z; SM_CLUSTER::WaitForResourceOnline(_HRESOURCE *)
0x140003d13  test    eax, eax
0x140003d15  jz      short loc_140003D1C
0x140003d17  mov     rbx, rdi
0x140003d1a  jmp     short loc_140003D25
0x140003d1c  mov     rcx, rdi; hResource
0x140003d1f  call    cs:__imp_CloseClusterResource
0x140003d25  cmp     [rbp+StringUuid], 0
0x140003d2a  jz      short loc_140003D3E
0x140003d2c  lea     rcx, [rbp+StringUuid]; String
0x140003d30  call    cs:__imp_RpcStringFreeW
0x140003d36  mov     [rbp+StringUuid], 0
0x140003d3e  test    rbx, rbx
0x140003d41  jnz     short loc_140003D8D
0x140003d43  call    cs:__imp_GetLastError
0x140003d49  mov     ecx, eax
0x140003d4b  mov     eax, cs:dword_140014048
0x140003d51  cmp     eax, 2
0x140003d54  jbe     short loc_140003DC1
0x140003d56  lea     rax, [rbp+arg_10]
0x140003d5a  mov     [rbp+arg_10], ecx
0x140003d5d  mov     [rsp+50h+var_20], rax
0x140003d62  lea     rdx, word_140010DF2
0x140003d69  lea     rax, [rbp+arg_18]
0x140003d6d  mov     dword ptr [rbp+arg_18], 10Fh
0x140003d74  mov     [rsp+50h+var_28], rax
0x140003d79  lea     rax, [rbp+var_8]
0x140003d7d  mov     [rsp+50h+var_30], rax
0x140003d82  mov     [rbp+var_8], r15
0x140003d86  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003d8b  jmp     short loc_140003DC1
0x140003d8d  mov     eax, cs:dword_140014048
0x140003d93  cmp     eax, 5
0x140003d96  jbe     short loc_140003DC1
0x140003d98  lea     rax, [rbp+arg_10]
0x140003d9c  mov     [rbp+arg_10], 10Fh
0x140003da3  mov     [rsp+50h+var_28], rax
0x140003da8  lea     rdx, byte_140010D91
0x140003daf  lea     rax, [rbp+arg_18]
0x140003db3  mov     [rbp+arg_18], r15
0x140003db7  mov     [rsp+50h+var_30], rax
0x140003dbc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003dc1  mov     rsi, [rsp+50h+arg_8]
0x140003dc6  mov     rax, rbx
0x140003dc9  mov     rbx, [rsp+50h+arg_0]
0x140003dce  add     rsp, 50h
0x140003dd2  pop     r15
0x140003dd4  pop     rdi
0x140003dd5  pop     rbp
0x140003dd6  retn
```
