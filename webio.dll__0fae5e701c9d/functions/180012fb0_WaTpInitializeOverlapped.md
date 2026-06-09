# WaTpInitializeOverlapped

- ea: `0x180012fb0`
- end: `0x18001327b`
- name: `WaTpInitializeOverlapped`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008059c`

## callees

- `0x180012fb0`
- `0x180013820`
- `0x1800180e0`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001300f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001300f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ff1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001308a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001316a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001308a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001316a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001305c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001305c`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18001303c`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18001303c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001312e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001312e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800130ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001315a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800130ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001315a`

## pseudocode

```c
__int64 __fastcall WaTpInitializeOverlapped(__int64 a1)
{
  HANDLE CurrentThread; // rax
  __int64 v3; // rdx
  DWORD v4; // edi
  bool v5; // zf
  __int64 result; // rax
  DWORD LastError; // eax
  _QWORD *v8; // rsi
  void *v9; // r14
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 *v12; // rcx
  int v13; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  __int128 v16; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-9h] BYREF
  __int128 *v18; // [rsp+60h] [rbp+7h]
  __int64 v19; // [rsp+68h] [rbp+Fh]
  __int64 *v20; // [rsp+70h] [rbp+17h]
  int v21; // [rsp+78h] [rbp+1Fh]
  int v22; // [rsp+7Ch] [rbp+23h]
  void **p_TokenHandle; // [rsp+80h] [rbp+27h]
  __int64 v24; // [rsp+88h] [rbp+2Fh]

  TokenHandle = (void *)-1LL;
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 48) = 0;
  *(_DWORD *)a1 = 1448038484;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    v3 = (__int64)TokenHandle;
    v4 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1359;
    v3 = -(__int64)(LastError != 1008);
    v4 = 0;
    if ( LastError != 1008 )
      v4 = LastError;
  }
  *(_QWORD *)(a1 + 40) = v3;
  if ( v3 && EventEnabled(WEB_ETW_PROVIDER_ID_Context, &ThreadTokenGet) )
  {
    v8 = 0;
    v9 = *(void **)(a1 + 40);
    TokenInformationLength = 0;
    if ( !GetTokenInformation(v9, TokenUser, 0, 0, &TokenInformationLength) )
    {
      if ( GetLastError() != 122 )
        goto LABEL_5;
      v11 = g_fWxHeapExtensionInitialized
          ? (_QWORD *)((__int64 (__fastcall *)(_QWORD))qword_1800AE528)(TokenInformationLength)
          : HeapAlloc(g_hWxProcessHeap, 0, TokenInformationLength);
      v8 = v11;
      if ( !v11 )
        goto LABEL_5;
      if ( !GetTokenInformation(v9, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
      {
        GetLastError();
        TokenHandle = v8;
        WxFreeHeapEx(&TokenHandle);
        goto LABEL_5;
      }
    }
    if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v12 = (__int64 *)*v8;
      *(_QWORD *)&v16 = *(_QWORD *)(a1 + 40);
      v18 = &v16;
      v13 = 8;
      v19 = 8;
      LODWORD(TokenHandle) = v4;
      if ( v12 )
        v13 = 4 * *((unsigned __int8 *)v12 + 1) + 8;
      else
        v12 = &qword_18009D050;
      v21 = v13;
      v20 = v12;
      p_TokenHandle = &TokenHandle;
      v22 = 0;
      v24 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, &ThreadTokenGet, v10, 4, v17);
    }
    else if ( !v8 )
    {
      goto LABEL_5;
    }
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v8);
    else
      HeapFree(g_hWxProcessHeap, 0, v8);
  }
LABEL_5:
  v16 = 0;
  v5 = EventActivityIdControl(1u, (LPGUID)(a1 + 48)) == 0;
  result = v4;
  if ( !v5 )
    *(_OWORD *)(a1 + 48) = 0;
  return result;
}

```

## disassembly

```asm
0x180012fb0  push    rbp
0x180012fb2  push    rbx
0x180012fb3  push    rdi
0x180012fb4  lea     rbp, [rsp-47h]
0x180012fb9  sub     rsp, 0A0h
0x180012fc0  mov     rax, cs:__security_cookie
0x180012fc7  xor     rax, rsp
0x180012fca  mov     [rbp+57h+var_20], rax
0x180012fce  xorps   xmm0, xmm0
0x180012fd1  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180012fd9  movups  xmmword ptr [rcx], xmm0
0x180012fdc  mov     rbx, rcx
0x180012fdf  movups  xmmword ptr [rcx+10h], xmm0
0x180012fe3  movups  xmmword ptr [rcx+20h], xmm0
0x180012fe7  movups  xmmword ptr [rcx+30h], xmm0
0x180012feb  mov     dword ptr [rcx], 564F5054h
0x180012ff1  call    cs:__imp_GetCurrentThread
0x180012ff8  nop     dword ptr [rax+rax+00h]
0x180012ffd  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180013001  mov     edx, 2000Ch; DesiredAccess
0x180013006  mov     rcx, rax; ThreadHandle
0x180013009  mov     r8d, 1; OpenAsSelf
0x18001300f  call    cs:__imp_OpenThreadToken
0x180013016  nop     dword ptr [rax+rax+00h]
0x18001301b  test    eax, eax
0x18001301d  jz      short loc_18001308A
0x18001301f  mov     rdx, [rbp+57h+TokenHandle]
0x180013023  xor     edi, edi
0x180013025  mov     [rbx+28h], rdx
0x180013029  test    rdx, rdx
0x18001302c  jz      short loc_18001304C
0x18001302e  mov     rcx, cs:WEB_ETW_PROVIDER_ID_Context; RegHandle
0x180013035  lea     rdx, ThreadTokenGet; EventDescriptor
0x18001303c  call    cs:__imp_EventEnabled
0x180013043  nop     dword ptr [rax+rax+00h]
0x180013048  test    al, al
0x18001304a  jnz     short loc_1800130BA
0x18001304c  xorps   xmm0, xmm0
0x18001304f  lea     rdx, [rbx+30h]; ActivityId
0x180013053  mov     ecx, 1; ControlCode
0x180013058  movups  [rbp+57h+var_70], xmm0
0x18001305c  call    cs:__imp_EventActivityIdControl
0x180013063  nop     dword ptr [rax+rax+00h]
0x180013068  test    eax, eax
0x18001306a  mov     eax, edi
0x18001306c  jnz     loc_18001326F
0x180013072  mov     rcx, [rbp+57h+var_20]
0x180013076  xor     rcx, rsp; StackCookie
0x180013079  call    __security_check_cookie
0x18001307e  add     rsp, 0A0h
0x180013085  pop     rdi
0x180013086  pop     rbx
0x180013087  pop     rbp
0x180013088  retn
0x18001308a  call    cs:__imp_GetLastError
0x180013091  nop     dword ptr [rax+rax+00h]
0x180013096  test    eax, eax
0x180013098  mov     ecx, 54Fh
0x18001309d  cmovz   eax, ecx
0x1800130a0  lea     ecx, [rax-3F0h]
0x1800130a6  neg     ecx
0x1800130a8  sbb     rdx, rdx
0x1800130ab  xor     edi, edi
0x1800130ad  cmp     eax, 3F0h
0x1800130b2  cmovnz  edi, eax
0x1800130b5  jmp     loc_180013025
0x1800130ba  mov     [rsp+0B0h+arg_8], rsi
0x1800130c2  lea     rax, [rbp+57h+TokenInformationLength]
0x1800130c6  mov     [rsp+0B0h+arg_10], r14
0x1800130ce  xor     esi, esi
0x1800130d0  mov     r14, [rbx+28h]
0x1800130d4  xor     r9d, r9d; TokenInformationLength
0x1800130d7  mov     rcx, r14; TokenHandle
0x1800130da  mov     [rbp+57h+TokenInformationLength], esi
0x1800130dd  xor     r8d, r8d; TokenInformation
0x1800130e0  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800130e5  mov     edx, 1; TokenInformationClass
0x1800130ea  call    cs:__imp_GetTokenInformation
0x1800130f1  nop     dword ptr [rax+rax+00h]
0x1800130f6  test    eax, eax
0x1800130f8  jnz     loc_1800131C4
0x1800130fe  call    cs:__imp_GetLastError
0x180013105  nop     dword ptr [rax+rax+00h]
0x18001310a  cmp     eax, 7Ah ; 'z'
0x18001310d  jnz     loc_1800131AF
0x180013113  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, esi; int g_fWxHeapExtensionInitialized
0x180013119  mov     ecx, [rbp+57h+TokenInformationLength]
0x18001311c  jnz     loc_18001325E
0x180013122  mov     r8d, ecx; dwBytes
0x180013125  xor     edx, edx; dwFlags
0x180013127  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001312e  call    cs:__imp_HeapAlloc
0x180013135  nop     dword ptr [rax+rax+00h]
0x18001313a  mov     rsi, rax
0x18001313d  test    rax, rax
0x180013140  jz      short loc_1800131AF
0x180013142  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180013146  lea     rax, [rbp+57h+TokenInformationLength]
0x18001314a  mov     r8, rsi; TokenInformation
0x18001314d  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180013152  mov     edx, 1; TokenInformationClass
0x180013157  mov     rcx, r14; TokenHandle
0x18001315a  call    cs:__imp_GetTokenInformation
0x180013161  nop     dword ptr [rax+rax+00h]
0x180013166  test    eax, eax
0x180013168  jnz     short loc_1800131C4
0x18001316a  call    cs:__imp_GetLastError
0x180013171  nop     dword ptr [rax+rax+00h]
0x180013176  lea     rcx, [rbp+57h+TokenHandle]
0x18001317a  mov     [rbp+57h+TokenHandle], rsi
0x18001317e  call    WxFreeHeapEx
0x180013183  jmp     short loc_1800131AF
0x180013185  test    rsi, rsi
0x180013188  jz      short loc_1800131AF
0x18001318a  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180013191  jnz     loc_180013241
0x180013197  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001319e  mov     r8, rsi; lpMem
0x1800131a1  xor     edx, edx; dwFlags
0x1800131a3  call    cs:__imp_HeapFree
0x1800131aa  nop     dword ptr [rax+rax+00h]
0x1800131af  mov     rsi, [rsp+0B0h+arg_8]
0x1800131b7  mov     r14, [rsp+0B0h+arg_10]
0x1800131bf  jmp     loc_18001304C
0x1800131c4  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x1800131cb  jz      short loc_180013185
0x1800131cd  mov     rax, [rbx+28h]
0x1800131d1  mov     rcx, [rsi]
0x1800131d4  mov     qword ptr [rbp+57h+var_70], rax
0x1800131d8  lea     rax, [rbp+57h+var_70]
0x1800131dc  mov     [rbp+57h+var_50], rax
0x1800131e0  mov     eax, 8
0x1800131e5  mov     [rbp+57h+var_48], rax
0x1800131e9  mov     dword ptr [rbp+57h+TokenHandle], edi
0x1800131ec  test    rcx, rcx
0x1800131ef  jz      short loc_180013255
0x1800131f1  movzx   eax, byte ptr [rcx+1]
0x1800131f5  lea     eax, ds:8[rax*4]
0x1800131fc  mov     [rbp+57h+var_38], eax
0x1800131ff  lea     rdx, ThreadTokenGet
0x180013206  lea     rax, [rbp+57h+TokenHandle]
0x18001320a  mov     [rbp+57h+var_40], rcx
0x18001320e  mov     [rbp+57h+var_30], rax
0x180013212  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180013219  lea     rax, [rbp+57h+var_60]
0x18001321d  mov     [rbp+57h+var_34], 0
0x180013224  mov     r9d, 4
0x18001322a  mov     [rsp+0B0h+ReturnLength], rax
0x18001322f  mov     [rbp+57h+var_28], 4
0x180013237  call    McGenEventWrite_EventWriteTransfer
0x18001323c  jmp     loc_18001318A
0x180013241  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180013248  mov     rcx, rsi
0x18001324b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013250  jmp     loc_1800131AF
0x180013255  lea     rcx, qword_18009D050
0x18001325c  jmp     short loc_1800131FC
0x18001325e  mov     rax, cs:qword_1800AE528
0x180013265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001326a  jmp     loc_18001313A
0x18001326f  xorps   xmm0, xmm0
0x180013272  movups  xmmword ptr [rbx+30h], xmm0
0x180013276  jmp     loc_180013072
```
