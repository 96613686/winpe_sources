# WaGetCurrentThreadToken

- ea: `0x180014f30`
- end: `0x1800151bb`
- name: `WaGetCurrentThreadToken`
- size: `651`
- prototype: ``
- caller_count: `14`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012ab0`
- `0x180013870`
- `0x1800156f0`
- `0x180019a20`
- `0x18001e5b8`
- `0x180025860`
- `0x18002c250`
- `0x18002e1a4`
- `0x18002e2c4`
- `0x180035390`
- `0x18003b970`
- `0x1800442f0`
- `0x18005176c`
- `0x180054354`

## callees

- `0x180013820`
- `0x180014f30`
- `0x1800180e0`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014f7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014f7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014f5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001504e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001504e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150bb`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180014fa9`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180014fa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800150f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800150f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001507f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001507f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001503a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800150ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001503a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800150ab`

## pseudocode

```c
__int64 __fastcall WaGetCurrentThreadToken(__int64 *a1)
{
  HANDLE CurrentThread; // rax
  __int64 v3; // rdx
  DWORD v4; // edi
  DWORD LastError; // eax
  void *v7; // r15
  void *v8; // rcx
  _QWORD *v9; // r14
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 *v12; // rcx
  int v13; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  __int64 v16; // [rsp+40h] [rbp-19h] BYREF
  char v17[16]; // [rsp+50h] [rbp-9h] BYREF
  void **v18; // [rsp+60h] [rbp+7h]
  __int64 v19; // [rsp+68h] [rbp+Fh]
  __int64 *v20; // [rsp+70h] [rbp+17h]
  int v21; // [rsp+78h] [rbp+1Fh]
  int v22; // [rsp+7Ch] [rbp+23h]
  void **p_TokenHandle; // [rsp+80h] [rbp+27h]
  __int64 v24; // [rsp+88h] [rbp+2Fh]

  TokenHandle = (void *)-1LL;
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
  *a1 = v3;
  if ( v3 && EventEnabled(WEB_ETW_PROVIDER_ID_Context, &ThreadTokenGet) )
  {
    v7 = (void *)*a1;
    v8 = (void *)*a1;
    TokenInformationLength = 0;
    v9 = 0;
    if ( !GetTokenInformation(v8, TokenUser, 0, 0, &TokenInformationLength) )
    {
      if ( GetLastError() != 122 )
        return v4;
      v11 = g_fWxHeapExtensionInitialized
          ? (_QWORD *)((__int64 (__fastcall *)(_QWORD))qword_1800AE528)(TokenInformationLength)
          : HeapAlloc(g_hWxProcessHeap, 0, TokenInformationLength);
      v9 = v11;
      if ( !v11 )
        return v4;
      if ( !GetTokenInformation(v7, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
      {
        GetLastError();
        TokenHandle = v9;
        WxFreeHeapEx(&TokenHandle);
        return v4;
      }
    }
    if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v12 = (__int64 *)*v9;
      v16 = *a1;
      v18 = (void **)&v16;
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
    else if ( !v9 )
    {
      return v4;
    }
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v9);
    else
      HeapFree(g_hWxProcessHeap, 0, v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180014f30  mov     [rsp-8+arg_18], rbx
0x180014f35  push    rbp
0x180014f36  push    rsi
0x180014f37  push    rdi
0x180014f38  lea     rbp, [rsp-47h]
0x180014f3d  sub     rsp, 0A0h
0x180014f44  mov     rax, cs:__security_cookie
0x180014f4b  xor     rax, rsp
0x180014f4e  mov     [rbp+57h+var_20], rax
0x180014f52  mov     rbx, rcx
0x180014f55  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180014f5d  call    cs:__imp_GetCurrentThread
0x180014f64  nop     dword ptr [rax+rax+00h]
0x180014f69  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180014f6d  mov     edx, 2000Ch; DesiredAccess
0x180014f72  mov     rcx, rax; ThreadHandle
0x180014f75  mov     r8d, 1; OpenAsSelf
0x180014f7b  call    cs:__imp_OpenThreadToken
0x180014f82  nop     dword ptr [rax+rax+00h]
0x180014f87  test    eax, eax
0x180014f89  jz      short loc_180014FDB
0x180014f8b  mov     rdx, [rbp+57h+TokenHandle]
0x180014f8f  xor     esi, esi
0x180014f91  mov     edi, esi
0x180014f93  mov     [rbx], rdx
0x180014f96  test    rdx, rdx
0x180014f99  jz      short loc_180014FB9
0x180014f9b  mov     rcx, cs:WEB_ETW_PROVIDER_ID_Context; RegHandle
0x180014fa2  lea     rdx, ThreadTokenGet; EventDescriptor
0x180014fa9  call    cs:__imp_EventEnabled
0x180014fb0  nop     dword ptr [rax+rax+00h]
0x180014fb5  test    al, al
0x180014fb7  jnz     short loc_18001500A
0x180014fb9  mov     eax, edi
0x180014fbb  mov     rcx, [rbp+57h+var_20]
0x180014fbf  xor     rcx, rsp; StackCookie
0x180014fc2  call    __security_check_cookie
0x180014fc7  mov     rbx, [rsp+0B0h+arg_18]
0x180014fcf  add     rsp, 0A0h
0x180014fd6  pop     rdi
0x180014fd7  pop     rsi
0x180014fd8  pop     rbp
0x180014fd9  retn
0x180014fdb  call    cs:__imp_GetLastError
0x180014fe2  nop     dword ptr [rax+rax+00h]
0x180014fe7  test    eax, eax
0x180014fe9  mov     ecx, 54Fh
0x180014fee  cmovz   eax, ecx
0x180014ff1  lea     ecx, [rax-3F0h]
0x180014ff7  neg     ecx
0x180014ff9  sbb     rdx, rdx
0x180014ffc  xor     esi, esi
0x180014ffe  cmp     eax, 3F0h
0x180015003  mov     edi, esi
0x180015005  cmovnz  edi, eax
0x180015008  jmp     short loc_180014F93
0x18001500a  mov     [rsp+0B0h+arg_8], r14
0x180015012  lea     rax, [rbp+57h+TokenInformationLength]
0x180015016  mov     [rsp+0B0h+arg_10], r15
0x18001501e  xor     r9d, r9d; TokenInformationLength
0x180015021  mov     r15, [rbx]
0x180015024  xor     r8d, r8d; TokenInformation
0x180015027  mov     rcx, r15; TokenHandle
0x18001502a  mov     [rbp+57h+TokenInformationLength], esi
0x18001502d  mov     edx, 1; TokenInformationClass
0x180015032  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180015037  mov     r14, rsi
0x18001503a  call    cs:__imp_GetTokenInformation
0x180015041  nop     dword ptr [rax+rax+00h]
0x180015046  test    eax, eax
0x180015048  jnz     loc_180015115
0x18001504e  call    cs:__imp_GetLastError
0x180015055  nop     dword ptr [rax+rax+00h]
0x18001505a  cmp     eax, 7Ah ; 'z'
0x18001505d  jnz     loc_180015100
0x180015063  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18001506a  mov     ecx, [rbp+57h+TokenInformationLength]
0x18001506d  jnz     loc_1800151AA
0x180015073  mov     r8d, ecx; dwBytes
0x180015076  xor     edx, edx; dwFlags
0x180015078  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001507f  call    cs:__imp_HeapAlloc
0x180015086  nop     dword ptr [rax+rax+00h]
0x18001508b  mov     r14, rax
0x18001508e  test    rax, rax
0x180015091  jz      short loc_180015100
0x180015093  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180015097  lea     rax, [rbp+57h+TokenInformationLength]
0x18001509b  mov     r8, r14; TokenInformation
0x18001509e  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800150a3  mov     edx, 1; TokenInformationClass
0x1800150a8  mov     rcx, r15; TokenHandle
0x1800150ab  call    cs:__imp_GetTokenInformation
0x1800150b2  nop     dword ptr [rax+rax+00h]
0x1800150b7  test    eax, eax
0x1800150b9  jnz     short loc_180015115
0x1800150bb  call    cs:__imp_GetLastError
0x1800150c2  nop     dword ptr [rax+rax+00h]
0x1800150c7  lea     rcx, [rbp+57h+TokenHandle]
0x1800150cb  mov     [rbp+57h+TokenHandle], r14
0x1800150cf  call    WxFreeHeapEx
0x1800150d4  jmp     short loc_180015100
0x1800150d6  test    r14, r14
0x1800150d9  jz      short loc_180015100
0x1800150db  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x1800150e2  jnz     loc_18001518D
0x1800150e8  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800150ef  mov     r8, r14; lpMem
0x1800150f2  xor     edx, edx; dwFlags
0x1800150f4  call    cs:__imp_HeapFree
0x1800150fb  nop     dword ptr [rax+rax+00h]
0x180015100  mov     r14, [rsp+0B0h+arg_8]
0x180015108  mov     r15, [rsp+0B0h+arg_10]
0x180015110  jmp     loc_180014FB9
0x180015115  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x18001511c  jz      short loc_1800150D6
0x18001511e  mov     rax, [rbx]
0x180015121  mov     rcx, [r14]
0x180015124  mov     [rbp+57h+var_70], rax
0x180015128  lea     rax, [rbp+57h+var_70]
0x18001512c  mov     [rbp+57h+var_50], rax
0x180015130  mov     eax, 8
0x180015135  mov     [rbp+57h+var_48], rax
0x180015139  mov     dword ptr [rbp+57h+TokenHandle], edi
0x18001513c  test    rcx, rcx
0x18001513f  jz      short loc_1800151A1
0x180015141  movzx   eax, byte ptr [rcx+1]
0x180015145  lea     eax, ds:8[rax*4]
0x18001514c  mov     [rbp+57h+var_38], eax
0x18001514f  lea     rdx, ThreadTokenGet
0x180015156  lea     rax, [rbp+57h+TokenHandle]
0x18001515a  mov     [rbp+57h+var_40], rcx
0x18001515e  mov     [rbp+57h+var_30], rax
0x180015162  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180015169  lea     rax, [rbp+57h+var_60]
0x18001516d  mov     [rbp+57h+var_34], esi
0x180015170  mov     r9d, 4
0x180015176  mov     [rsp+0B0h+ReturnLength], rax
0x18001517b  mov     [rbp+57h+var_28], 4
0x180015183  call    McGenEventWrite_EventWriteTransfer
0x180015188  jmp     loc_1800150DB
0x18001518d  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180015194  mov     rcx, r14
0x180015197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001519c  jmp     loc_180015100
0x1800151a1  lea     rcx, qword_18009D050
0x1800151a8  jmp     short loc_18001514C
0x1800151aa  mov     rax, cs:qword_1800AE528
0x1800151b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151b6  jmp     loc_18001508B
```
