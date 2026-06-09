# CClientConfigDataCacheManager::WriteResponseStream(ushort const *,IStream *)

- ea: `0x1800c8f7c`
- end: `0x1800c9163`
- name: `?WriteResponseStream@CClientConfigDataCacheManager@@AEAAJPEBGPEAUIStream@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(CClientConfigDataCacheManager *__hidden this, const unsigned __int16 *, struct IStream *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7b8c`

## callees

- `0x18000c050`
- `0x1800a3b60`
- `0x1800c49c4`
- `0x1800c8f7c`
- `0x180116bb0`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9096`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c908c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c908c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c9010`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c9010`

## string_xrefs

- `0x1800c9123`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c911c`: `CClientConfigDataCacheManager::WriteResponseStream`
- `0x1800c90e4`: `cbRead <= cb`

## pseudocode

```c
__int64 __fastcall CClientConfigDataCacheManager::WriteResponseStream(
        CClientConfigDataCacheManager *this,
        const unsigned __int16 *a2,
        struct IStream *a3)
{
  HANDLE FileW; // rbx
  signed int v5; // eax
  signed int v6; // edi
  DWORD v7; // eax
  signed int LastError; // eax
  const char *v9; // rax
  unsigned int v10; // r8d
  DWORD nNumberOfBytesToWrite; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Buffer[8192]; // [rsp+60h] [rbp-A0h] BYREF

  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v15 = -1;
  v14 = 0;
  if ( !a2 || !*a2 || !a3 )
  {
    v6 = -2147024809;
    v9 = "szFileName != nullptr && *szFileName != L'\\0' && pStream != nullptr";
    v10 = 1900;
    goto LABEL_21;
  }
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v15 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v6 = (*(__int64 (__fastcall **)(struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a3 + 40LL))(a3, v14, 0, 0);
    if ( v6 )
      goto LABEL_22;
    while ( 1 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64, DWORD *))(*(_QWORD *)a3 + 24LL))(
             a3,
             Buffer,
             0x2000,
             &nNumberOfBytesToWrite);
      if ( v6 < 0 )
      {
        v7 = nNumberOfBytesToWrite;
LABEL_17:
        if ( v7 <= 0x2000 )
          goto LABEL_22;
LABEL_18:
        v6 = -2147418113;
        v9 = "cbRead <= cb";
        v10 = 1929;
        goto LABEL_21;
      }
      v7 = nNumberOfBytesToWrite;
      if ( !nNumberOfBytesToWrite )
        goto LABEL_17;
      if ( nNumberOfBytesToWrite > 0x2000 )
        goto LABEL_18;
      if ( !WriteFile(FileW, Buffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( v6 < 0 )
          break;
      }
    }
    v9 = "hr = HRESULT_FROM_WIN32(GetLastError())";
    v10 = 1925;
LABEL_21:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "CClientConfigDataCacheManager::WriteResponseStream",
      v10,
      v6,
      v9);
    goto LABEL_22;
  }
  v5 = GetLastError();
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
LABEL_22:
  CHandle_INVALID_HANDLE_VALUE::~CHandle_INVALID_HANDLE_VALUE((CHandle_INVALID_HANDLE_VALUE *)&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c8f7c  mov     [rsp-8+arg_0], rbx
0x1800c8f81  mov     [rsp-8+arg_18], rsi
0x1800c8f86  push    rbp
0x1800c8f87  push    rdi
0x1800c8f88  push    r14
0x1800c8f8a  lea     rbp, [rsp-1F70h]
0x1800c8f92  mov     eax, 2070h
0x1800c8f97  call    _alloca_probe
0x1800c8f9c  sub     rsp, rax
0x1800c8f9f  mov     rax, cs:__security_cookie
0x1800c8fa6  xor     rax, rsp
0x1800c8fa9  mov     [rbp+1F80h+var_20], rax
0x1800c8fb0  mov     rsi, r8
0x1800c8fb3  mov     rax, rdx
0x1800c8fb6  xor     r14d, r14d
0x1800c8fb9  mov     [rsp+2080h+nNumberOfBytesToWrite], r14d
0x1800c8fbe  mov     [rsp+2080h+NumberOfBytesWritten], r14d
0x1800c8fc3  mov     [rsp+2080h+var_2030], 0FFFFFFFFFFFFFFFFh
0x1800c8fcc  mov     [rsp+2080h+var_2038], r14
0x1800c8fd1  test    rdx, rdx
0x1800c8fd4  jz      loc_1800C9102
0x1800c8fda  cmp     [rdx], r14w
0x1800c8fde  jz      loc_1800C9102
0x1800c8fe4  test    r8, r8
0x1800c8fe7  jz      loc_1800C9102
0x1800c8fed  mov     [rsp+2080h+hTemplateFile], r14; hTemplateFile
0x1800c8ff2  mov     [rsp+2080h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c8ffa  mov     [rsp+2080h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c9002  xor     r9d, r9d; lpSecurityAttributes
0x1800c9005  xor     r8d, r8d; dwShareMode
0x1800c9008  mov     edx, 40000000h; dwDesiredAccess
0x1800c900d  mov     rcx, rax; lpFileName
0x1800c9010  call    cs:__imp_CreateFileW
0x1800c9016  mov     rbx, rax
0x1800c9019  mov     [rsp+2080h+var_2030], rax
0x1800c901e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c9022  jnz     short loc_1800C9042
0x1800c9024  call    cs:__imp_GetLastError
0x1800c902a  mov     edi, eax
0x1800c902c  test    eax, eax
0x1800c902e  jle     loc_1800C9130
0x1800c9034  movzx   edi, ax
0x1800c9037  or      edi, 80070000h
0x1800c903d  jmp     loc_1800C9130
0x1800c9042  mov     rax, [rsi]
0x1800c9045  xor     r9d, r9d
0x1800c9048  xor     r8d, r8d
0x1800c904b  mov     rdx, [rsp+2080h+var_2038]
0x1800c9050  mov     rcx, rsi
0x1800c9053  mov     rax, [rax+28h]
0x1800c9057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c905c  mov     edi, eax
0x1800c905e  test    eax, eax
0x1800c9060  jnz     loc_1800C9130
0x1800c9066  jmp     short loc_1800C90AF
0x1800c9068  mov     eax, [rsp+2080h+nNumberOfBytesToWrite]
0x1800c906c  test    eax, eax
0x1800c906e  jz      short loc_1800C90D8
0x1800c9070  cmp     eax, 2000h
0x1800c9075  ja      short loc_1800C90DF
0x1800c9077  mov     qword ptr [rsp+2080h+dwCreationDisposition], r14; lpOverlapped
0x1800c907c  lea     r9, [rsp+2080h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c9081  mov     r8d, eax; nNumberOfBytesToWrite
0x1800c9084  lea     rdx, [rsp+2080h+Buffer]; lpBuffer
0x1800c9089  mov     rcx, rbx; hFile
0x1800c908c  call    cs:__imp_WriteFile
0x1800c9092  test    eax, eax
0x1800c9094  jnz     short loc_1800C90AF
0x1800c9096  call    cs:__imp_GetLastError
0x1800c909c  mov     edi, eax
0x1800c909e  test    eax, eax
0x1800c90a0  jle     short loc_1800C90AB
0x1800c90a2  movzx   edi, ax
0x1800c90a5  or      edi, 80070000h
0x1800c90ab  test    edi, edi
0x1800c90ad  js      short loc_1800C90F3
0x1800c90af  mov     rax, [rsi]
0x1800c90b2  lea     r9, [rsp+2080h+nNumberOfBytesToWrite]
0x1800c90b7  mov     r8d, 2000h
0x1800c90bd  lea     rdx, [rsp+2080h+Buffer]
0x1800c90c2  mov     rcx, rsi
0x1800c90c5  mov     rax, [rax+18h]
0x1800c90c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c90ce  test    eax, eax
0x1800c90d0  mov     edi, eax
0x1800c90d2  jns     short loc_1800C9068
0x1800c90d4  mov     eax, [rsp+2080h+nNumberOfBytesToWrite]
0x1800c90d8  cmp     eax, 2000h
0x1800c90dd  jbe     short loc_1800C9130
0x1800c90df  mov     edi, 8000FFFFh
0x1800c90e4  lea     rax, aCbreadCb; "cbRead <= cb"
0x1800c90eb  mov     r8d, 789h
0x1800c90f1  jmp     short loc_1800C9114
0x1800c90f3  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800c90fa  mov     r8d, 785h
0x1800c9100  jmp     short loc_1800C9114
0x1800c9102  mov     edi, 80070057h
0x1800c9107  lea     rax, aSzfilenameNull_0; "szFileName != nullptr && *szFileName !="...
0x1800c910e  mov     r8d, 76Ch; unsigned int
0x1800c9114  mov     qword ptr [rsp+2080h+dwCreationDisposition], rax; char *
0x1800c9119  mov     r9d, edi; int
0x1800c911c  lea     rdx, aCclientconfigd_11; "CClientConfigDataCacheManager::WriteRes"...
0x1800c9123  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c912a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c912f  nop
0x1800c9130  lea     rcx, [rsp+2080h+var_2030]; this
0x1800c9135  call    ??1CHandle_INVALID_HANDLE_VALUE@@QEAA@XZ; CHandle_INVALID_HANDLE_VALUE::~CHandle_INVALID_HANDLE_VALUE(void)
0x1800c913a  mov     eax, edi
0x1800c913c  mov     rcx, [rbp+1F80h+var_20]
0x1800c9143  xor     rcx, rsp; StackCookie
0x1800c9146  call    __security_check_cookie
0x1800c914b  lea     r11, [rsp+2080h+var_10]
0x1800c9153  mov     rbx, [r11+20h]
0x1800c9157  mov     rsi, [r11+38h]
0x1800c915b  mov     rsp, r11
0x1800c915e  pop     r14
0x1800c9160  pop     rdi
0x1800c9161  pop     rbp
0x1800c9162  retn
```
