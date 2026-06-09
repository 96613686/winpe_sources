# WapTcpAllocateIoContext

- ea: `0x180013470`
- end: `0x180013818`
- name: `WapTcpAllocateIoContext`
- size: `936`
- prototype: `__int64 __usercall@<rax>(size_t Size@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180051cd4`
- `0x180052950`

## callees

- `0x180013470`
- `0x180013820`
- `0x1800180e0`
- `0x1800722f0`
- `0x180072c70`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001352d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001352d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001350f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001350f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001360a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001367b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001360a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001367b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136ed`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013585`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013585`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180013561`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180013561`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800137a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800137a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800134b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800136ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800134b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800136ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013667`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800136dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013667`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800136dd`

## pseudocode

```c
__int64 __fastcall WapTcpAllocateIoContext(size_t Size, __int64 a2, int a3, __int64 a4, __int64 a5, __int64 a6)
{
  void *v10; // rax
  __int64 v11; // rbx
  HANDLE CurrentThread; // rax
  __int64 v13; // rdx
  DWORD v14; // r14d
  __int64 result; // rax
  DWORD LastError; // eax
  __int64 **v17; // r13
  __int64 v18; // r8
  __int64 **v19; // rax
  __int64 *v20; // rcx
  int v21; // eax
  void *TokenHandle; // [rsp+30h] [rbp-59h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-51h] BYREF
  __int128 v24; // [rsp+40h] [rbp-49h] BYREF
  char v25[16]; // [rsp+50h] [rbp-39h] BYREF
  __int128 *v26; // [rsp+60h] [rbp-29h]
  __int64 v27; // [rsp+68h] [rbp-21h]
  __int64 *v28; // [rsp+70h] [rbp-19h]
  int v29; // [rsp+78h] [rbp-11h]
  int v30; // [rsp+7Ch] [rbp-Dh]
  void **p_TokenHandle; // [rsp+80h] [rbp-9h]
  __int64 v32; // [rsp+88h] [rbp-1h]

  if ( g_fWxHeapExtensionInitialized )
    v10 = (void *)((__int64 (*)(void))qword_1800AE528)();
  else
    v10 = HeapAlloc(g_hWxProcessHeap, 0, Size);
  v11 = (__int64)v10;
  if ( !v10 )
    return 0;
  memset_0(v10, 0, Size);
  TokenHandle = (void *)-1LL;
  *(_OWORD *)(v11 + 16) = 0;
  *(_OWORD *)(v11 + 32) = 0;
  *(_OWORD *)(v11 + 48) = 0;
  *(_OWORD *)(v11 + 64) = 0;
  *(_DWORD *)(v11 + 16) = 1448038484;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    v13 = (__int64)TokenHandle;
    v14 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1359;
    v13 = -(__int64)(LastError != 1008);
    TokenHandle = (void *)v13;
    v14 = 0;
    if ( LastError != 1008 )
      v14 = LastError;
  }
  *(_QWORD *)(v11 + 56) = v13;
  if ( v13 && EventEnabled(WEB_ETW_PROVIDER_ID_Context, &ThreadTokenGet) )
  {
    TokenHandle = *(void **)(v11 + 56);
    TokenInformationLength = 0;
    v17 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      goto LABEL_24;
    if ( GetLastError() != 122 )
      goto LABEL_8;
    v19 = g_fWxHeapExtensionInitialized
        ? (__int64 **)((__int64 (__fastcall *)(_QWORD))qword_1800AE528)(TokenInformationLength)
        : (__int64 **)HeapAlloc(g_hWxProcessHeap, 0, TokenInformationLength);
    v17 = v19;
    if ( !v19 )
      goto LABEL_8;
    if ( GetTokenInformation(TokenHandle, TokenUser, v19, TokenInformationLength, &TokenInformationLength) )
    {
LABEL_24:
      if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
      {
        v20 = *v17;
        *(_QWORD *)&v24 = *(_QWORD *)(v11 + 56);
        v26 = &v24;
        v21 = 8;
        v27 = 8;
        LODWORD(TokenHandle) = v14;
        if ( v20 )
          v21 = 4 * *((unsigned __int8 *)v20 + 1) + 8;
        else
          v20 = &qword_18009D050;
        v29 = v21;
        v28 = v20;
        p_TokenHandle = &TokenHandle;
        v30 = 0;
        v32 = 4;
        McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, &ThreadTokenGet, v18, 4, v25);
      }
      else if ( !v17 )
      {
        goto LABEL_8;
      }
      if ( g_fWxHeapExtensionInitialized )
        g_WxHeapExtensionInterfaces(v17);
      else
        HeapFree(g_hWxProcessHeap, 0, v17);
    }
    else
    {
      GetLastError();
      TokenHandle = v17;
      WxFreeHeapEx(&TokenHandle);
    }
  }
LABEL_8:
  v24 = 0;
  if ( EventActivityIdControl(1u, (LPGUID)(v11 + 64)) )
    *(_OWORD *)(v11 + 64) = 0;
  if ( !v14 )
  {
    *(_DWORD *)v11 = 1481591124;
    *(_DWORD *)(v11 + 4) = 1;
    *(_QWORD *)(v11 + 8) = a2;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 8) + 4LL));
    *(_QWORD *)(v11 + 88) = a5;
    *(_QWORD *)(v11 + 96) = a6;
    result = v11;
    *(_QWORD *)(v11 + 80) = a4;
    *(_DWORD *)(v11 + 104) = 0;
    *(_QWORD *)(v11 + 112) = 0;
    *(_DWORD *)(v11 + 120) = a3;
    return result;
  }
  *(_QWORD *)&v24 = v11;
  WxFreeHeapEx(&v24);
  return 0;
}

```

## disassembly

```asm
0x180013470  push    rbp
0x180013472  push    rbx
0x180013473  push    rsi
0x180013474  push    rdi
0x180013475  push    r12
0x180013477  push    r15
0x180013479  lea     rbp, [rsp-1Fh]
0x18001347e  sub     rsp, 0A8h
0x180013485  mov     rax, cs:__security_cookie
0x18001348c  xor     rax, rsp
0x18001348f  mov     [rbp+47h+var_40], rax
0x180013493  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18001349a  mov     r15, r9
0x18001349d  mov     r12d, r8d
0x1800134a0  mov     rsi, rdx
0x1800134a3  mov     rdi, rcx
0x1800134a6  jnz     loc_1800137D6
0x1800134ac  mov     r8, rcx; dwBytes
0x1800134af  xor     edx, edx; dwFlags
0x1800134b1  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800134b8  call    cs:__imp_HeapAlloc
0x1800134bf  nop     dword ptr [rax+rax+00h]
0x1800134c4  mov     rbx, rax
0x1800134c7  test    rax, rax
0x1800134ca  jz      loc_180013811
0x1800134d0  mov     [rsp+0D0h+arg_10], r13
0x1800134d8  mov     r8, rdi; Size
0x1800134db  xor     edx, edx; Val
0x1800134dd  mov     [rsp+0D0h+var_30], r14
0x1800134e5  mov     rcx, rax; void *
0x1800134e8  call    memset_0
0x1800134ed  xorps   xmm0, xmm0
0x1800134f0  mov     [rbp+47h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800134f8  movups  xmmword ptr [rbx+10h], xmm0
0x1800134fc  movups  xmmword ptr [rbx+20h], xmm0
0x180013500  movups  xmmword ptr [rbx+30h], xmm0
0x180013504  movups  xmmword ptr [rbx+40h], xmm0
0x180013508  mov     dword ptr [rbx+10h], 564F5054h
0x18001350f  call    cs:__imp_GetCurrentThread
0x180013516  nop     dword ptr [rax+rax+00h]
0x18001351b  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x18001351f  mov     edx, 2000Ch; DesiredAccess
0x180013524  mov     rcx, rax; ThreadHandle
0x180013527  mov     r8d, 1; OpenAsSelf
0x18001352d  call    cs:__imp_OpenThreadToken
0x180013534  nop     dword ptr [rax+rax+00h]
0x180013539  test    eax, eax
0x18001353b  jz      loc_18001360A
0x180013541  mov     rdx, [rbp+47h+TokenHandle]
0x180013545  xor     edi, edi
0x180013547  mov     r14d, edi
0x18001354a  mov     [rbx+38h], rdx
0x18001354e  test    rdx, rdx
0x180013551  jz      short loc_180013575
0x180013553  mov     rcx, cs:WEB_ETW_PROVIDER_ID_Context; RegHandle
0x18001355a  lea     rdx, ThreadTokenGet; EventDescriptor
0x180013561  call    cs:__imp_EventEnabled
0x180013568  nop     dword ptr [rax+rax+00h]
0x18001356d  test    al, al
0x18001356f  jnz     loc_180013642
0x180013575  xorps   xmm0, xmm0
0x180013578  lea     rdx, [rbx+40h]; ActivityId
0x18001357c  mov     ecx, 1; ControlCode
0x180013581  movups  [rbp+47h+var_90], xmm0
0x180013585  call    cs:__imp_EventActivityIdControl
0x18001358c  nop     dword ptr [rax+rax+00h]
0x180013591  test    eax, eax
0x180013593  jnz     loc_1800137F8
0x180013599  mov     r13, [rsp+0D0h+arg_10]
0x1800135a1  test    r14d, r14d
0x1800135a4  mov     r14, [rsp+0D0h+var_30]
0x1800135ac  jnz     loc_180013804
0x1800135b2  mov     dword ptr [rbx], 584F4954h
0x1800135b8  mov     dword ptr [rbx+4], 1
0x1800135bf  mov     [rbx+8], rsi
0x1800135c3  mov     rax, [rsi+8]
0x1800135c7  lock inc dword ptr [rax+4]
0x1800135cb  mov     rax, [rbp+47h+arg_20]
0x1800135cf  mov     [rbx+58h], rax
0x1800135d3  mov     rax, [rbp+47h+arg_28]
0x1800135d7  mov     [rbx+60h], rax
0x1800135db  mov     rax, rbx
0x1800135de  mov     [rbx+50h], r15
0x1800135e2  mov     [rbx+68h], edi
0x1800135e5  mov     [rbx+70h], rdi
0x1800135e9  mov     [rbx+78h], r12d
0x1800135ed  mov     rcx, [rbp+47h+var_40]
0x1800135f1  xor     rcx, rsp; StackCookie
0x1800135f4  call    __security_check_cookie
0x1800135f9  add     rsp, 0A8h
0x180013600  pop     r15
0x180013602  pop     r12
0x180013604  pop     rdi
0x180013605  pop     rsi
0x180013606  pop     rbx
0x180013607  pop     rbp
0x180013608  retn
0x18001360a  call    cs:__imp_GetLastError
0x180013611  nop     dword ptr [rax+rax+00h]
0x180013616  test    eax, eax
0x180013618  mov     ecx, 54Fh
0x18001361d  cmovz   eax, ecx
0x180013620  lea     ecx, [rax-3F0h]
0x180013626  neg     ecx
0x180013628  sbb     rdx, rdx
0x18001362b  xor     edi, edi
0x18001362d  cmp     eax, 3F0h
0x180013632  mov     [rbp+47h+TokenHandle], rdx
0x180013636  mov     r14d, edi
0x180013639  cmovnz  r14d, eax
0x18001363d  jmp     loc_18001354A
0x180013642  mov     rax, [rbx+38h]
0x180013646  lea     rcx, [rbp+47h+TokenInformationLength]
0x18001364a  mov     [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x18001364f  xor     r9d, r9d; TokenInformationLength
0x180013652  mov     rcx, rax; TokenHandle
0x180013655  mov     [rbp+47h+TokenHandle], rax
0x180013659  xor     r8d, r8d; TokenInformation
0x18001365c  mov     [rbp+47h+TokenInformationLength], edi
0x18001365f  mov     edx, 1; TokenInformationClass
0x180013664  mov     r13, rdi
0x180013667  call    cs:__imp_GetTokenInformation
0x18001366e  nop     dword ptr [rax+rax+00h]
0x180013673  test    eax, eax
0x180013675  jnz     loc_18001370B
0x18001367b  call    cs:__imp_GetLastError
0x180013682  nop     dword ptr [rax+rax+00h]
0x180013687  cmp     eax, 7Ah ; 'z'
0x18001368a  jnz     loc_180013575
0x180013690  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180013697  mov     ecx, [rbp+47h+TokenInformationLength]
0x18001369a  jnz     loc_1800137E7
0x1800136a0  mov     r8d, ecx; dwBytes
0x1800136a3  xor     edx, edx; dwFlags
0x1800136a5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800136ac  call    cs:__imp_HeapAlloc
0x1800136b3  nop     dword ptr [rax+rax+00h]
0x1800136b8  mov     r13, rax
0x1800136bb  test    rax, rax
0x1800136be  jz      loc_180013575
0x1800136c4  mov     r9d, [rbp+47h+TokenInformationLength]; TokenInformationLength
0x1800136c8  lea     rax, [rbp+47h+TokenInformationLength]
0x1800136cc  mov     rcx, [rbp+47h+TokenHandle]; TokenHandle
0x1800136d0  mov     r8, r13; TokenInformation
0x1800136d3  mov     edx, 1; TokenInformationClass
0x1800136d8  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800136dd  call    cs:__imp_GetTokenInformation
0x1800136e4  nop     dword ptr [rax+rax+00h]
0x1800136e9  test    eax, eax
0x1800136eb  jnz     short loc_18001370B
0x1800136ed  call    cs:__imp_GetLastError
0x1800136f4  nop     dword ptr [rax+rax+00h]
0x1800136f9  lea     rcx, [rbp+47h+TokenHandle]
0x1800136fd  mov     [rbp+47h+TokenHandle], r13
0x180013701  call    WxFreeHeapEx
0x180013706  jmp     loc_180013575
0x18001370b  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x180013712  jz      short loc_180013787
0x180013714  mov     rax, [rbx+38h]
0x180013718  mov     rcx, [r13+0]
0x18001371c  mov     qword ptr [rbp+47h+var_90], rax
0x180013720  lea     rax, [rbp+47h+var_90]
0x180013724  mov     [rbp+47h+var_70], rax
0x180013728  mov     eax, 8
0x18001372d  mov     [rbp+47h+var_68], rax
0x180013731  mov     dword ptr [rbp+47h+TokenHandle], r14d
0x180013735  test    rcx, rcx
0x180013738  jz      loc_1800137CA
0x18001373e  movzx   eax, byte ptr [rcx+1]
0x180013742  lea     eax, ds:8[rax*4]
0x180013749  mov     [rbp+47h+var_58], eax
0x18001374c  lea     rdx, ThreadTokenGet
0x180013753  lea     rax, [rbp+47h+TokenHandle]
0x180013757  mov     [rbp+47h+var_60], rcx
0x18001375b  mov     [rbp+47h+var_50], rax
0x18001375f  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180013766  lea     rax, [rbp+47h+var_80]
0x18001376a  mov     [rbp+47h+var_54], edi
0x18001376d  mov     r9d, 4
0x180013773  mov     [rsp+0D0h+ReturnLength], rax
0x180013778  mov     [rbp+47h+var_48], 4
0x180013780  call    McGenEventWrite_EventWriteTransfer
0x180013785  jmp     short loc_180013790
0x180013787  test    r13, r13
0x18001378a  jz      loc_180013575
0x180013790  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180013797  jnz     short loc_1800137B6
0x180013799  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800137a0  mov     r8, r13; lpMem
0x1800137a3  xor     edx, edx; dwFlags
0x1800137a5  call    cs:__imp_HeapFree
0x1800137ac  nop     dword ptr [rax+rax+00h]
0x1800137b1  jmp     loc_180013575
0x1800137b6  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x1800137bd  mov     rcx, r13
0x1800137c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137c5  jmp     loc_180013575
0x1800137ca  lea     rcx, qword_18009D050
0x1800137d1  jmp     loc_180013749
0x1800137d6  mov     rax, cs:qword_1800AE528
0x1800137dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137e2  jmp     loc_1800134C4
0x1800137e7  mov     rax, cs:qword_1800AE528
0x1800137ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137f3  jmp     loc_1800136B8
0x1800137f8  xorps   xmm0, xmm0
0x1800137fb  movups  xmmword ptr [rbx+40h], xmm0
0x1800137ff  jmp     loc_180013599
0x180013804  lea     rcx, [rbp+47h+var_90]
0x180013808  mov     qword ptr [rbp+47h+var_90], rbx
0x18001380c  call    WxFreeHeapEx
0x180013811  xor     eax, eax
0x180013813  jmp     loc_1800135ED
```
