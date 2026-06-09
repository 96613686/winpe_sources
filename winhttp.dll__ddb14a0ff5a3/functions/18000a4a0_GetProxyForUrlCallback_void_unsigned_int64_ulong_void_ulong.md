# GetProxyForUrlCallback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x18000a4a0`
- end: `0x18000a68c`
- name: `?GetProxyForUrlCallback@@YAXPEAX_KK0K@Z`
- size: `492`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a4a0`
- `0x18000a6a0`
- `0x18000b22c`
- `0x18000b8d0`
- `0x18000c000`
- `0x1800a1d10`
- `0x1800d8364`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a64a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a64a`

## pseudocode

```c
void __fastcall GetProxyForUrlCallback(
        HINTERNET hInternet,
        __int64 dwContext,
        DWORD dwInternetStatus,
        _DWORD *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  HANDLE v9; // rcx
  _OWORD *v10; // rsi
  unsigned int v11; // r15d
  int *v12; // rdi
  unsigned int v13; // r14d
  unsigned int i; // ebx
  DWORD LastError; // ecx
  void (__fastcall *v16)(__int64, _QWORD, __int64); // rdi
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 j; // rbx
  __int64 dwBufferLength; // [rsp+40h] [rbp-21h] BYREF
  __int128 Buffer; // [rsp+48h] [rbp-19h] BYREF
  HANDLE hObject[2]; // [rsp+58h] [rbp-9h]
  LPVOID pv[2]; // [rsp+68h] [rbp+7h]
  __int64 v24; // [rsp+78h] [rbp+17h]

  Buffer = 0;
  v24 = 0;
  *(_OWORD *)hObject = 0;
  LODWORD(dwBufferLength) = 0;
  *(_OWORD *)pv = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qqDqD(
      (_DWORD)hInternet,
      dwContext,
      dwInternetStatus,
      (_DWORD)hInternet,
      dwContext,
      dwInternetStatus,
      (__int64)lpvStatusInformation,
      dwStatusInformationLength,
      dwBufferLength);
  if ( dwInternetStatus == 2048 )
  {
    if ( dwContext )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)dwContext + 8LL))(dwContext);
  }
  else
  {
    if ( dwInternetStatus == 0x1000000 )
    {
      LODWORD(dwBufferLength) = 56;
      if ( WinHttpQueryOption(hInternet, 0xB4u, &Buffer, (LPDWORD)&dwBufferLength) )
      {
        (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD))(dwContext + 24))(0, &Buffer, *(_QWORD *)(dwContext + 16));
        goto LABEL_7;
      }
      LastError = GetLastError();
      goto LABEL_20;
    }
    if ( dwInternetStatus == 0x200000 && *(_QWORD *)lpvStatusInformation == 6 )
    {
      LastError = lpvStatusInformation[2];
LABEL_20:
      v16 = *(void (__fastcall **)(__int64, _QWORD, __int64))(dwContext + 24);
      v17 = *(_QWORD *)(dwContext + 16);
      v18 = (unsigned int)WinHttpErrorToHRESULT(LastError);
      v16(v18, 0, v17);
    }
  }
LABEL_7:
  v9 = hObject[0];
  v10 = (_OWORD *)*((_QWORD *)&Buffer + 1);
  v11 = Buffer;
  v12 = (int *)pv[1];
  v13 = HIDWORD(pv[0]);
  Buffer = 0;
  *(_OWORD *)hObject = 0;
  if ( v9 )
    CloseHandle(v9);
  if ( v10 )
  {
    for ( i = 0; i < v11; ++i )
      FreeProxyResultEntry<WxCoTaskAllocator>(&v10[2 * i]);
    CoTaskMemFree(v10);
  }
  v24 = 0;
  Buffer = 0;
  *(_OWORD *)hObject = 0;
  *(_OWORD *)pv = 0;
  if ( v12 )
  {
    for ( j = 0; (unsigned int)j < v13; j = (unsigned int)(j + 1) )
      FreeProxyResultEx<WxCoTaskAllocator>(&v12[10 * j]);
    CoTaskMemFree(v12);
  }
}

```

## disassembly

```asm
0x18000a4a0  mov     [rsp-8+arg_10], rbx
0x18000a4a5  push    rbp
0x18000a4a6  push    rsi
0x18000a4a7  push    rdi
0x18000a4a8  push    r14
0x18000a4aa  push    r15
0x18000a4ac  lea     rbp, [rsp-2Fh]
0x18000a4b1  sub     rsp, 90h
0x18000a4b8  mov     rax, cs:__security_cookie
0x18000a4bf  xor     rax, rsp
0x18000a4c2  mov     [rbp+4Fh+var_30], rax
0x18000a4c6  xorps   xmm0, xmm0
0x18000a4c9  xor     eax, eax
0x18000a4cb  movups  [rbp+4Fh+Buffer], xmm0
0x18000a4cf  mov     [rbp+4Fh+var_38], rax
0x18000a4d3  mov     rsi, r9
0x18000a4d6  movups  xmmword ptr [rbp+4Fh+hObject], xmm0
0x18000a4da  mov     dword ptr [rbp+4Fh+dwBufferLength], eax
0x18000a4dd  mov     edi, r8d
0x18000a4e0  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x18000a4e4  mov     rbx, rdx
0x18000a4e7  mov     r14, rcx
0x18000a4ea  test    byte ptr cs:xmmword_180107A60, 20h
0x18000a4f1  jnz     loc_18000A655
0x18000a4f7  cmp     edi, 800h
0x18000a4fd  jz      loc_18000A5B4
0x18000a503  cmp     edi, 1000000h
0x18000a509  jnz     loc_18000A5F7
0x18000a50f  lea     r9, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x18000a513  mov     dword ptr [rbp+4Fh+dwBufferLength], 38h ; '8'
0x18000a51a  lea     r8, [rbp+4Fh+Buffer]; lpBuffer
0x18000a51e  mov     edx, 0B4h; dwOption
0x18000a523  mov     rcx, r14; hInternet
0x18000a526  call    WinHttpQueryOption
0x18000a52b  test    eax, eax
0x18000a52d  jz      loc_18000A677
0x18000a533  mov     r8, [rbx+10h]
0x18000a537  lea     rdx, [rbp+4Fh+Buffer]
0x18000a53b  mov     rax, [rbx+18h]
0x18000a53f  xor     ecx, ecx
0x18000a541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a546  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18000a54a  xorps   xmm0, xmm0
0x18000a54d  mov     rsi, qword ptr [rbp+4Fh+Buffer+8]
0x18000a551  mov     r15d, dword ptr [rbp+4Fh+Buffer]
0x18000a555  mov     rdi, [rbp+4Fh+pv+8]
0x18000a559  mov     r14d, dword ptr [rbp+4Fh+pv+4]
0x18000a55d  movups  [rbp+4Fh+Buffer], xmm0
0x18000a561  movups  xmmword ptr [rbp+4Fh+hObject], xmm0
0x18000a565  test    rcx, rcx
0x18000a568  jnz     loc_18000A681
0x18000a56e  test    rsi, rsi
0x18000a571  jnz     short loc_18000A5CD
0x18000a573  xorps   xmm0, xmm0
0x18000a576  xor     eax, eax
0x18000a578  mov     [rbp+4Fh+var_38], rax
0x18000a57c  movups  [rbp+4Fh+Buffer], xmm0
0x18000a580  movups  xmmword ptr [rbp+4Fh+hObject], xmm0
0x18000a584  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x18000a588  test    rdi, rdi
0x18000a58b  jnz     loc_18000A62C
0x18000a591  mov     rcx, [rbp+4Fh+var_30]
0x18000a595  xor     rcx, rsp; StackCookie
0x18000a598  call    __security_check_cookie
0x18000a59d  mov     rbx, [rsp+0B0h+arg_10]
0x18000a5a5  add     rsp, 90h
0x18000a5ac  pop     r15
0x18000a5ae  pop     r14
0x18000a5b0  pop     rdi
0x18000a5b1  pop     rsi
0x18000a5b2  pop     rbp
0x18000a5b3  retn
0x18000a5b4  test    rbx, rbx
0x18000a5b7  jz      short loc_18000A546
0x18000a5b9  mov     rax, [rbx]
0x18000a5bc  mov     rcx, rbx
0x18000a5bf  mov     rax, [rax+8]
0x18000a5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5c8  jmp     loc_18000A546
0x18000a5cd  xor     ebx, ebx
0x18000a5cf  test    r15d, r15d
0x18000a5d2  jz      short loc_18000A5E9
0x18000a5d4  mov     ecx, ebx
0x18000a5d6  shl     rcx, 5
0x18000a5da  add     rcx, rsi
0x18000a5dd  call    ??$FreeProxyResultEntry@VWxCoTaskAllocator@@@@YAXPEAU_PROXY_RESULT_ENTRY@@@Z; FreeProxyResultEntry<WxCoTaskAllocator>(_PROXY_RESULT_ENTRY *)
0x18000a5e2  inc     ebx
0x18000a5e4  cmp     ebx, r15d
0x18000a5e7  jb      short loc_18000A5D4
0x18000a5e9  mov     rcx, rsi; pv
0x18000a5ec  call    cs:__imp_CoTaskMemFree
0x18000a5f2  jmp     loc_18000A573
0x18000a5f7  cmp     edi, 200000h
0x18000a5fd  jnz     loc_18000A546
0x18000a603  cmp     qword ptr [rsi], 6
0x18000a607  jnz     loc_18000A546
0x18000a60d  mov     ecx, [rsi+8]; unsigned int
0x18000a610  mov     rdi, [rbx+18h]
0x18000a614  mov     rbx, [rbx+10h]
0x18000a618  call    ?WinHttpErrorToHRESULT@@YAJK@Z; WinHttpErrorToHRESULT(ulong)
0x18000a61d  mov     ecx, eax
0x18000a61f  mov     r8, rbx
0x18000a622  mov     rax, rdi
0x18000a625  xor     edx, edx
0x18000a627  jmp     loc_18000A541
0x18000a62c  xor     ebx, ebx
0x18000a62e  test    r14d, r14d
0x18000a631  jz      short loc_18000A647
0x18000a633  lea     rdx, [rbx+rbx*4]
0x18000a637  lea     rcx, [rdi+rdx*8]
0x18000a63b  call    ??$FreeProxyResultEx@VWxCoTaskAllocator@@@@YAXPEAU_PROXY_RESULT@@@Z; FreeProxyResultEx<WxCoTaskAllocator>(_PROXY_RESULT *)
0x18000a640  inc     ebx
0x18000a642  cmp     ebx, r14d
0x18000a645  jb      short loc_18000A633
0x18000a647  mov     rcx, rdi; pv
0x18000a64a  call    cs:__imp_CoTaskMemFree
0x18000a650  jmp     loc_18000A591
0x18000a655  mov     eax, [rbp+4Fh+dwStatusInformationLength]
0x18000a658  mov     r9, r14
0x18000a65b  mov     [rsp+0B0h+var_78], eax
0x18000a65f  mov     [rsp+0B0h+var_80], rsi
0x18000a664  mov     [rsp+0B0h+var_88], edi
0x18000a668  mov     [rsp+0B0h+var_90], rbx
0x18000a66d  call    WPP_SF_qqDqD
0x18000a672  jmp     loc_18000A4F7
0x18000a677  call    cs:__imp_GetLastError
0x18000a67d  mov     ecx, eax
0x18000a67f  jmp     short loc_18000A610
0x18000a681  call    cs:__imp_CloseHandle
0x18000a687  jmp     loc_18000A56E
```
