# CToken::TraceCapabilitySids(void)

- ea: `0x18008cfa4`
- end: `0x18008d172`
- name: `?TraceCapabilitySids@CToken@@QEAAJXZ`
- size: `462`
- prototype: `__int64 __fastcall(CToken *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180090af8`

## callees

- `0x180001938`
- `0x18000c6fc`
- `0x18000ce5c`
- `0x1800210f8`
- `0x18008044c`
- `0x18008cfa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cfe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cfe2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008cfd6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008d04a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008cfd6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008d04a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008d0bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008d0bb`
- `KERNELBASE!LocalAlloc` at `0x18008d01c`
- `KERNELBASE!LocalAlloc` at `0x18008d01c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008d074`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008d132`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008d074`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008d132`

## string_xrefs

- `0x18008d05e`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18008d150`: `onecore\com\combase\rpcss\objex\token.cxx`

## pseudocode

```c
__int64 __fastcall CToken::TraceCapabilitySids(HANDLE *this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  _DWORD *v5; // rbx
  const char *v6; // r9
  unsigned int v7; // edi
  int v9; // esi
  BOOL v10; // edi
  int v11; // r8d
  int v12; // r9d
  const wchar_t *v13; // rax
  char *v14; // rdx
  int ReturnLength; // [rsp+20h] [rbp-30h]
  const wchar_t **v16; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-18h] BYREF
  char v18; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+70h] [rbp+20h] BYREF
  const wchar_t *v21; // [rsp+78h] [rbp+28h] BYREF
  const wchar_t *v22; // [rsp+80h] [rbp+30h] BYREF

  TokenInformationLength = 0;
  GetTokenInformation(this[9], TokenCapabilities, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 == -2147024774 )
  {
    v5 = LocalAlloc(0, TokenInformationLength);
    if ( !v5 )
    {
      v3 = -2147024882;
      v4 = 571;
      goto LABEL_19;
    }
    if ( !GetTokenInformation(this[9], TokenCapabilities, v5, TokenInformationLength, &TokenInformationLength) )
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x23F,
             (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
             v6);
      LocalFree(v5);
      return v7;
    }
    v9 = 0;
    if ( !*v5 )
    {
LABEL_17:
      LocalFree(v5);
      return 0;
    }
    while ( 1 )
    {
      v21 = 0;
      v16 = &v21;
      StringSid = 0;
      v18 = 1;
      v10 = ConvertSidToStringSidW(*(PSID *)&v5[4 * v9 + 2], &StringSid);
      wil::details::out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v16);
      if ( v10 )
      {
        if ( (unsigned int)dword_1801574B8 > 5 )
        {
          v13 = v21;
          v14 = (char *)&unk_180147EE0;
LABEL_15:
          v22 = v13;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_1801574B8,
            (_DWORD)v14,
            v11,
            v12,
            (__int64)&v22);
        }
      }
      else if ( (unsigned int)dword_1801574B8 > 5 )
      {
        v13 = L"Error";
        v14 = byte_180147EAB;
        goto LABEL_15;
      }
      wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v21,
        0);
      if ( (unsigned int)++v9 >= *v5 )
        goto LABEL_17;
    }
  }
  if ( (v3 & 0x80000000) != 0 )
  {
    v4 = 566;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (const char *)v3,
      ReturnLength);
  }
  return v3;
}

```

## disassembly

```asm
0x18008cfa4  mov     [rsp-18h+arg_18], rbx
0x18008cfa9  push    rbp
0x18008cfaa  push    rsi
0x18008cfab  push    rdi
0x18008cfac  mov     rbp, rsp
0x18008cfaf  sub     rsp, 50h
0x18008cfb3  xor     r9d, r9d; TokenInformationLength
0x18008cfb6  mov     [rbp+TokenInformationLength], 0
0x18008cfbd  mov     rdi, rcx
0x18008cfc0  lea     rax, [rbp+TokenInformationLength]
0x18008cfc4  mov     rcx, [rcx+48h]; TokenHandle
0x18008cfc8  xor     r8d, r8d; TokenInformation
0x18008cfcb  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x18008cfd0  lea     esi, [r9+1Eh]
0x18008cfd4  mov     edx, esi; TokenInformationClass
0x18008cfd6  call    cs:__imp_GetTokenInformation
0x18008cfdd  nop     dword ptr [rax+rax+00h]
0x18008cfe2  call    cs:__imp_GetLastError
0x18008cfe9  nop     dword ptr [rax+rax+00h]
0x18008cfee  mov     ebx, eax
0x18008cff0  test    eax, eax
0x18008cff2  jle     short loc_18008CFFD
0x18008cff4  movzx   ebx, ax
0x18008cff7  or      ebx, 80070000h
0x18008cffd  cmp     ebx, 8007007Ah
0x18008d003  jz      short loc_18008D017
0x18008d005  test    ebx, ebx
0x18008d007  jns     loc_18008D15F
0x18008d00d  mov     edx, 236h
0x18008d012  jmp     loc_18008D14C
0x18008d017  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18008d01a  xor     ecx, ecx; uFlags
0x18008d01c  call    cs:__imp_LocalAlloc
0x18008d023  nop     dword ptr [rax+rax+00h]
0x18008d028  mov     rbx, rax
0x18008d02b  test    rax, rax
0x18008d02e  jz      loc_18008D142
0x18008d034  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18008d038  lea     rax, [rbp+TokenInformationLength]
0x18008d03c  mov     rcx, [rdi+48h]; TokenHandle
0x18008d040  mov     r8, rbx; TokenInformation
0x18008d043  mov     edx, esi; TokenInformationClass
0x18008d045  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x18008d04a  call    cs:__imp_GetTokenInformation
0x18008d051  nop     dword ptr [rax+rax+00h]
0x18008d056  test    eax, eax
0x18008d058  jnz     short loc_18008D087
0x18008d05a  mov     rcx, [rbp+18h]; this
0x18008d05e  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008d065  mov     edx, 23Fh; void *
0x18008d06a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008d06f  mov     rcx, rbx; hMem
0x18008d072  mov     edi, eax
0x18008d074  call    cs:__imp_LocalFree
0x18008d07b  nop     dword ptr [rax+rax+00h]
0x18008d080  mov     eax, edi
0x18008d082  jmp     loc_18008D161
0x18008d087  xor     esi, esi
0x18008d089  cmp     [rbx], esi
0x18008d08b  jbe     loc_18008D12F
0x18008d091  lea     rax, [rbp+arg_8]
0x18008d095  mov     [rbp+arg_8], 0
0x18008d09d  mov     [rbp+var_20], rax
0x18008d0a1  lea     rdx, [rbp+StringSid]; StringSid
0x18008d0a5  mov     [rbp+StringSid], 0
0x18008d0ad  mov     [rbp+var_10], 1
0x18008d0b1  mov     ecx, esi
0x18008d0b3  add     rcx, rcx
0x18008d0b6  mov     rcx, [rbx+rcx*8+8]; Sid
0x18008d0bb  call    cs:__imp_ConvertSidToStringSidW
0x18008d0c2  nop     dword ptr [rax+rax+00h]
0x18008d0c7  lea     rcx, [rbp+var_20]
0x18008d0cb  mov     edi, eax
0x18008d0cd  call    ??1?$out_param_t@V?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18008d0d2  mov     eax, cs:dword_1801574B8
0x18008d0d8  test    edi, edi
0x18008d0da  jz      short loc_18008D0EE
0x18008d0dc  cmp     eax, 5
0x18008d0df  jbe     short loc_18008D11A
0x18008d0e1  mov     rax, [rbp+arg_8]
0x18008d0e5  lea     rdx, unk_180147EE0
0x18008d0ec  jmp     short loc_18008D101
0x18008d0ee  cmp     eax, 5
0x18008d0f1  jbe     short loc_18008D11A
0x18008d0f3  lea     rax, aError; "Error"
0x18008d0fa  lea     rdx, byte_180147EAB
0x18008d101  mov     [rbp+arg_10], rax
0x18008d105  lea     rcx, dword_1801574B8
0x18008d10c  lea     rax, [rbp+arg_10]
0x18008d110  mov     qword ptr [rsp+50h+ReturnLength], rax
0x18008d115  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18008d11a  xor     edx, edx
0x18008d11c  lea     rcx, [rbp+arg_8]
0x18008d120  call    ?reset@?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_PROC_THREAD_ATTRIBUTE_LIST *)
0x18008d125  inc     esi
0x18008d127  cmp     esi, [rbx]
0x18008d129  jb      loc_18008D091
0x18008d12f  mov     rcx, rbx; hMem
0x18008d132  call    cs:__imp_LocalFree
0x18008d139  nop     dword ptr [rax+rax+00h]
0x18008d13e  xor     eax, eax
0x18008d140  jmp     short loc_18008D161
0x18008d142  mov     ebx, 8007000Eh
0x18008d147  mov     edx, 23Bh; void *
0x18008d14c  mov     rcx, [rbp+18h]; this
0x18008d150  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008d157  mov     r9d, ebx; char *
0x18008d15a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d15f  mov     eax, ebx
0x18008d161  mov     rbx, [rsp+50h+arg_18]
0x18008d169  add     rsp, 50h
0x18008d16d  pop     rdi
0x18008d16e  pop     rsi
0x18008d16f  pop     rbp
0x18008d170  retn
```
