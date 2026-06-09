# WwanIsLowBoxMBAEClient(int *)

- ea: `0x1800ae22c`
- end: `0x1800ae362`
- name: `?WwanIsLowBoxMBAEClient@@YAKPEAH@Z`
- size: `310`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ae368`

## callees

- `0x180012300`
- `0x1800adacc`
- `0x1800ae22c`
- `0x1800c5d28`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800ae318`
- `ntdll!RtlNtStatusToDosError` at `0x1800ae318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae2d9`
- `RPCRT4!RpcImpersonateClient` at `0x1800ae250`
- `RPCRT4!RpcImpersonateClient` at `0x1800ae250`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800ae30c`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800ae30c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ae33c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ae33c`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800ae2cf`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800ae2cf`

## string_xrefs

- `0x1800ae2aa`: `ConvertClassGuidToSid: could not convert class to SID, hr %#x`

## pseudocode

```c
__int64 __fastcall WwanIsLowBoxMBAEClient(int *a1)
{
  RPC_STATUS v2; // edi
  signed int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  RPC_STATUS v6; // eax
  signed int v7; // eax
  __int64 result; // rax
  struct _GUID v9; // [rsp+20h] [rbp-18h] BYREF
  int v10; // [rsp+40h] [rbp+8h] BYREF
  PSID pSid; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  pSid = 0;
  v2 = RpcImpersonateClient(0);
  if ( v2 < 1 )
    v3 = v2;
  else
    v3 = (unsigned __int16)v2 | 0x80010000;
  if ( v3 >= 0 )
  {
    v9 = GUID_DEVINTERFACE_MBAE;
    if ( (unsigned int)ConvertClassGuidToSid(&v9, &pSid) )
      goto LABEL_24;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    WwanLog::Error(
      "WwanIsLowBoxMBAEClient",
      0,
      L"ConvertClassGuidToSid: could not convert class to SID, hr %#x",
      (unsigned int)v3);
    if ( v3 >= 0 )
    {
LABEL_24:
      if ( !(unsigned int)CheckTokenCapability(0, pSid, &v10) )
      {
        v5 = GetLastError();
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
        WwanLog::Error("WwanIsLowBoxMBAEClient", 0, L"Cannot determine if caller is MBAE, hr %#x", (unsigned int)v3);
      }
    }
  }
  if ( !v2 )
  {
    v6 = RpcRevertToSelfEx(0);
    if ( v6 )
    {
      v7 = RtlNtStatusToDosError(v6);
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  if ( pSid )
    FreeSid(pSid);
  *a1 = v10;
  result = 0;
  if ( v3 < 0 )
    return (unsigned __int16)v3;
  return result;
}

```

## disassembly

```asm
0x1800ae22c  mov     rax, rsp
0x1800ae22f  mov     [rax+18h], rbx
0x1800ae233  mov     [rax+20h], rsi
0x1800ae237  push    rdi
0x1800ae238  sub     rsp, 30h
0x1800ae23c  mov     rsi, rcx
0x1800ae23f  mov     dword ptr [rax+8], 0
0x1800ae246  xor     ecx, ecx; BindingHandle
0x1800ae248  mov     qword ptr [rax+10h], 0
0x1800ae250  call    cs:__imp_RpcImpersonateClient
0x1800ae256  mov     edi, eax
0x1800ae258  cmp     eax, 1
0x1800ae25b  jl      short loc_1800AE268
0x1800ae25d  movzx   ebx, di
0x1800ae260  or      ebx, 80010000h
0x1800ae266  jmp     short loc_1800AE26A
0x1800ae268  mov     ebx, edi
0x1800ae26a  test    ebx, ebx
0x1800ae26c  js      loc_1800AE306
0x1800ae272  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_MBAE.Data1
0x1800ae279  lea     rdx, [rsp+38h+pSid]; void **
0x1800ae27e  lea     rcx, [rsp+38h+var_18]; struct _GUID
0x1800ae283  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1800ae289  call    ?ConvertClassGuidToSid@@YAHU_GUID@@PEAPEAX@Z; ConvertClassGuidToSid(_GUID,void * *)
0x1800ae28e  test    eax, eax
0x1800ae290  jnz     short loc_1800AE2C3
0x1800ae292  call    cs:__imp_GetLastError
0x1800ae298  mov     ebx, eax
0x1800ae29a  test    eax, eax
0x1800ae29c  jle     short loc_1800AE2A7
0x1800ae29e  movzx   ebx, ax
0x1800ae2a1  or      ebx, 80070000h
0x1800ae2a7  mov     r9d, ebx
0x1800ae2aa  lea     r8, aConvertclassgu; "ConvertClassGuidToSid: could not conver"...
0x1800ae2b1  xor     edx, edx; struct _GUID *
0x1800ae2b3  lea     rcx, aWwanislowboxmb; "WwanIsLowBoxMBAEClient"
0x1800ae2ba  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae2bf  test    ebx, ebx
0x1800ae2c1  js      short loc_1800AE306
0x1800ae2c3  mov     rdx, [rsp+38h+pSid]
0x1800ae2c8  lea     r8, [rsp+38h+arg_0]
0x1800ae2cd  xor     ecx, ecx
0x1800ae2cf  call    cs:__imp_CheckTokenCapability
0x1800ae2d5  test    eax, eax
0x1800ae2d7  jnz     short loc_1800AE306
0x1800ae2d9  call    cs:__imp_GetLastError
0x1800ae2df  mov     ebx, eax
0x1800ae2e1  test    eax, eax
0x1800ae2e3  jle     short loc_1800AE2EE
0x1800ae2e5  movzx   ebx, ax
0x1800ae2e8  or      ebx, 80070000h
0x1800ae2ee  mov     r9d, ebx
0x1800ae2f1  lea     r8, aCannotDetermin; "Cannot determine if caller is MBAE, hr "...
0x1800ae2f8  xor     edx, edx; struct _GUID *
0x1800ae2fa  lea     rcx, aWwanislowboxmb; "WwanIsLowBoxMBAEClient"
0x1800ae301  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae306  test    edi, edi
0x1800ae308  jnz     short loc_1800AE332
0x1800ae30a  xor     ecx, ecx; BindingHandle
0x1800ae30c  call    cs:__imp_RpcRevertToSelfEx
0x1800ae312  test    eax, eax
0x1800ae314  jz      short loc_1800AE332
0x1800ae316  mov     ecx, eax; Status
0x1800ae318  call    cs:__imp_RtlNtStatusToDosError
0x1800ae31e  mov     ebx, eax
0x1800ae320  test    eax, eax
0x1800ae322  jle     short loc_1800AE32D
0x1800ae324  movzx   ebx, ax
0x1800ae327  or      ebx, 80070000h
0x1800ae32d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ae332  mov     rcx, [rsp+38h+pSid]; pSid
0x1800ae337  test    rcx, rcx
0x1800ae33a  jz      short loc_1800AE342
0x1800ae33c  call    cs:__imp_FreeSid
0x1800ae342  mov     eax, [rsp+38h+arg_0]
0x1800ae346  mov     [rsi], eax
0x1800ae348  xor     eax, eax
0x1800ae34a  mov     rsi, [rsp+38h+arg_18]
0x1800ae34f  test    ebx, ebx
0x1800ae351  movzx   ecx, bx
0x1800ae354  mov     rbx, [rsp+38h+arg_10]
0x1800ae359  cmovs   eax, ecx
0x1800ae35c  add     rsp, 30h
0x1800ae360  pop     rdi
0x1800ae361  retn
```
