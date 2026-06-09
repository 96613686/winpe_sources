# CToken::TraceCapabilitySids(void)

- ea: `0x1800884b8`
- end: `0x180088667`
- name: `?TraceCapabilitySids@CToken@@QEAAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(CToken *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008b9c4`

## callees

- `0x18000192c`
- `0x18001ec28`
- `0x18002ba28`
- `0x18007c94c`
- `0x1800884b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800884f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800884ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008854c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800884ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008854c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800885b1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800885b1`
- `KERNELBASE!LocalAlloc` at `0x180088524`
- `KERNELBASE!LocalAlloc` at `0x180088524`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180088570`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008861b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008862e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180088570`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008861b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18008862e`

## string_xrefs

- `0x18008855a`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180088646`: `onecore\com\combase\rpcss\objex\token.cxx`

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
  HLOCAL v15; // rcx
  int ReturnLength; // [rsp+20h] [rbp-30h]
  HLOCAL *p_hMem; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-18h] BYREF
  char v19; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+70h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+28h] BYREF
  const wchar_t *v23; // [rsp+80h] [rbp+30h] BYREF

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
      goto LABEL_21;
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
LABEL_19:
      LocalFree(v5);
      return 0;
    }
    while ( 1 )
    {
      hMem = 0;
      p_hMem = &hMem;
      StringSid = 0;
      v19 = 1;
      v10 = ConvertSidToStringSidW(*(PSID *)&v5[4 * v9 + 2], &StringSid);
      wil::details::out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      if ( v10 )
      {
        if ( (unsigned int)dword_18014E4B8 > 5 )
        {
          v13 = (const wchar_t *)hMem;
          v14 = (char *)&unk_18013EF40;
LABEL_15:
          v23 = v13;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_18014E4B8,
            (_DWORD)v14,
            v11,
            v12,
            (__int64)&v23);
        }
      }
      else if ( (unsigned int)dword_18014E4B8 > 5 )
      {
        v13 = L"Error";
        v14 = byte_18013EF0B;
        goto LABEL_15;
      }
      v15 = hMem;
      hMem = 0;
      if ( v15 )
        LocalFree(v15);
      if ( (unsigned int)++v9 >= *v5 )
        goto LABEL_19;
    }
  }
  if ( (v3 & 0x80000000) != 0 )
  {
    v4 = 566;
LABEL_21:
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
0x1800884b8  mov     [rsp-18h+arg_18], rbx
0x1800884bd  push    rbp
0x1800884be  push    rsi
0x1800884bf  push    rdi
0x1800884c0  mov     rbp, rsp
0x1800884c3  sub     rsp, 50h
0x1800884c7  xor     r9d, r9d; TokenInformationLength
0x1800884ca  mov     [rbp+TokenInformationLength], 0
0x1800884d1  mov     rdi, rcx
0x1800884d4  lea     rax, [rbp+TokenInformationLength]
0x1800884d8  mov     rcx, [rcx+48h]; TokenHandle
0x1800884dc  xor     r8d, r8d; TokenInformation
0x1800884df  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x1800884e4  lea     esi, [r9+1Eh]
0x1800884e8  mov     edx, esi; TokenInformationClass
0x1800884ea  call    cs:__imp_GetTokenInformation
0x1800884f0  call    cs:__imp_GetLastError
0x1800884f6  mov     ebx, eax
0x1800884f8  test    eax, eax
0x1800884fa  jle     short loc_180088505
0x1800884fc  movzx   ebx, ax
0x1800884ff  or      ebx, 80070000h
0x180088505  cmp     ebx, 8007007Ah
0x18008850b  jz      short loc_18008851F
0x18008850d  test    ebx, ebx
0x18008850f  jns     loc_180088655
0x180088515  mov     edx, 236h
0x18008851a  jmp     loc_180088642
0x18008851f  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180088522  xor     ecx, ecx; uFlags
0x180088524  call    cs:__imp_LocalAlloc
0x18008852a  mov     rbx, rax
0x18008852d  test    rax, rax
0x180088530  jz      loc_180088638
0x180088536  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18008853a  lea     rax, [rbp+TokenInformationLength]
0x18008853e  mov     rcx, [rdi+48h]; TokenHandle
0x180088542  mov     r8, rbx; TokenInformation
0x180088545  mov     edx, esi; TokenInformationClass
0x180088547  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x18008854c  call    cs:__imp_GetTokenInformation
0x180088552  test    eax, eax
0x180088554  jnz     short loc_18008857D
0x180088556  mov     rcx, [rbp+18h]; this
0x18008855a  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180088561  mov     edx, 23Fh; void *
0x180088566  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008856b  mov     rcx, rbx; hMem
0x18008856e  mov     edi, eax
0x180088570  call    cs:__imp_LocalFree
0x180088576  mov     eax, edi
0x180088578  jmp     loc_180088657
0x18008857d  xor     esi, esi
0x18008857f  cmp     [rbx], esi
0x180088581  jbe     loc_18008862B
0x180088587  lea     rax, [rbp+hMem]
0x18008858b  mov     [rbp+hMem], 0
0x180088593  mov     [rbp+var_20], rax
0x180088597  lea     rdx, [rbp+StringSid]; StringSid
0x18008859b  mov     [rbp+StringSid], 0
0x1800885a3  mov     [rbp+var_10], 1
0x1800885a7  mov     ecx, esi
0x1800885a9  add     rcx, rcx
0x1800885ac  mov     rcx, [rbx+rcx*8+8]; Sid
0x1800885b1  call    cs:__imp_ConvertSidToStringSidW
0x1800885b7  lea     rcx, [rbp+var_20]
0x1800885bb  mov     edi, eax
0x1800885bd  call    ??1?$out_param_t@V?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800885c2  mov     eax, cs:dword_18014E4B8
0x1800885c8  test    edi, edi
0x1800885ca  jz      short loc_1800885DE
0x1800885cc  cmp     eax, 5
0x1800885cf  jbe     short loc_18008860A
0x1800885d1  mov     rax, [rbp+hMem]
0x1800885d5  lea     rdx, unk_18013EF40
0x1800885dc  jmp     short loc_1800885F1
0x1800885de  cmp     eax, 5
0x1800885e1  jbe     short loc_18008860A
0x1800885e3  lea     rax, aError; "Error"
0x1800885ea  lea     rdx, byte_18013EF0B
0x1800885f1  mov     [rbp+arg_10], rax
0x1800885f5  lea     rcx, dword_18014E4B8
0x1800885fc  lea     rax, [rbp+arg_10]
0x180088600  mov     qword ptr [rsp+50h+ReturnLength], rax
0x180088605  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18008860a  mov     rcx, [rbp+hMem]; hMem
0x18008860e  mov     [rbp+hMem], 0
0x180088616  test    rcx, rcx
0x180088619  jz      short loc_180088621
0x18008861b  call    cs:__imp_LocalFree
0x180088621  inc     esi
0x180088623  cmp     esi, [rbx]
0x180088625  jb      loc_180088587
0x18008862b  mov     rcx, rbx; hMem
0x18008862e  call    cs:__imp_LocalFree
0x180088634  xor     eax, eax
0x180088636  jmp     short loc_180088657
0x180088638  mov     ebx, 8007000Eh
0x18008863d  mov     edx, 23Bh; void *
0x180088642  mov     rcx, [rbp+18h]; this
0x180088646  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18008864d  mov     r9d, ebx; char *
0x180088650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088655  mov     eax, ebx
0x180088657  mov     rbx, [rsp+50h+arg_18]
0x18008865f  add     rsp, 50h
0x180088663  pop     rdi
0x180088664  pop     rsi
0x180088665  pop     rbp
0x180088666  retn
```
