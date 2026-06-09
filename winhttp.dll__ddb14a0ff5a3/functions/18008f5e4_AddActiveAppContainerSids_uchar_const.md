# AddActiveAppContainerSids(uchar * const)

- ea: `0x18008f5e4`
- end: `0x18008f778`
- name: `?AddActiveAppContainerSids@@YAJQEAE@Z`
- size: `404`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180091a24`

## callees

- `0x1800081a0`
- `0x18001b480`
- `0x18008f5e4`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008f6f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008f6f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008f726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008f726`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008f6b3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008f6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f6bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f6bd`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008f634`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008f634`

## pseudocode

```c
__int64 __fastcall AddActiveAppContainerSids(PSID pSourceSid)
{
  __int64 v2; // rcx
  signed int v3; // ebx
  unsigned int v4; // edi
  __int64 v5; // rsi
  __int64 Heap; // rax
  _QWORD *v7; // rdi
  signed int LastError; // eax
  _QWORD *v9; // rax
  __int64 v11; // [rsp+20h] [rbp-18h]
  __int64 v12; // [rsp+28h] [rbp-10h] BYREF

  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 12, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids);
  if ( InitOnceExecuteOnce(&g_ActiveAppContainerSidsListInit, (PINIT_ONCE_FN)ActiveAppContainerSidsInitOnce, 0, 0) )
  {
    v5 = 0;
    HIDWORD(v11) = 0;
    v12 = 0;
    Heap = WxAllocateHeapEx(v2, 56);
    v7 = (_QWORD *)Heap;
    if ( Heap )
    {
      v12 = Heap;
      *(_OWORD *)Heap = 0;
      v5 = Heap;
      *(_OWORD *)(Heap + 16) = 0;
      *(_OWORD *)(Heap + 32) = 0;
      *(_QWORD *)(Heap + 48) = 0;
      if ( CopySid(0x28u, (PSID)(Heap + 16), pSourceSid) )
      {
        v3 = 0;
        EnterCriticalSection(&g_csActiveAppContainerSids);
        v9 = (_QWORD *)qword_180107D18;
        if ( *(struct _LIST_ENTRY **)qword_180107D18 != &g_ActiveAppContainerSidsListHead )
          __fastfail(3u);
        *v7 = &g_ActiveAppContainerSidsListHead;
        v7[1] = v9;
        *v9 = v7;
        qword_180107D18 = (__int64)v7;
        LeaveCriticalSection(&g_csActiveAppContainerSids);
        v5 = 0;
        v12 = 0;
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147418113;
        v4 = v3;
        HIDWORD(v11) = 77;
      }
    }
    else
    {
      v3 = -2147024882;
      v4 = -2147024882;
      HIDWORD(v11) = 73;
    }
    if ( v5 )
      WxFreeHeapEx(&v12);
  }
  else
  {
    v3 = -2147467259;
    HIDWORD(v11) = 71;
    v4 = -2147467259;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 13, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids, (unsigned int)v3, v11);
  return v4;
}

```

## disassembly

```asm
0x18008f5e4  mov     [rsp+arg_8], rbx
0x18008f5e9  mov     [rsp+arg_10], rsi
0x18008f5ee  push    rdi
0x18008f5ef  sub     rsp, 30h
0x18008f5f3  mov     rbx, rcx
0x18008f5f6  mov     [rsp+38h+var_14], 0
0x18008f5fe  test    byte ptr cs:xmmword_180107A60, 20h
0x18008f605  jz      short loc_18008F620
0x18008f607  mov     edx, 0Ch
0x18008f60c  lea     r8, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids
0x18008f613  mov     ecx, 405h
0x18008f618  mov     r9, rbx
0x18008f61b  call    WPP_SF_q
0x18008f620  xor     r9d, r9d; Context
0x18008f623  lea     rdx, ?ActiveAppContainerSidsInitOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18008f62a  xor     r8d, r8d; Parameter
0x18008f62d  lea     rcx, ?g_ActiveAppContainerSidsListInit@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18008f634  call    cs:__imp_InitOnceExecuteOnce
0x18008f63a  test    eax, eax
0x18008f63c  jnz     short loc_18008F652
0x18008f63e  mov     ebx, 80004005h
0x18008f643  mov     [rsp+38h+var_14], 47h ; 'G'
0x18008f64b  mov     edi, ebx
0x18008f64d  jmp     loc_18008F744
0x18008f652  xor     esi, esi
0x18008f654  mov     [rsp+38h+var_14], 0
0x18008f65c  mov     [rsp+38h+var_10], rsi
0x18008f661  lea     edx, [rsi+38h]
0x18008f664  call    WxAllocateHeapEx
0x18008f669  mov     rdi, rax
0x18008f66c  test    rax, rax
0x18008f66f  jnz     short loc_18008F68D
0x18008f671  mov     ebx, 8007000Eh
0x18008f676  mov     [rsp+38h+var_14], 4Ch ; 'L'
0x18008f67e  mov     edi, ebx
0x18008f680  mov     [rsp+38h+var_14], 49h ; 'I'
0x18008f688  jmp     loc_18008F735
0x18008f68d  xorps   xmm0, xmm0
0x18008f690  mov     [rsp+38h+var_10], rdi
0x18008f695  movups  xmmword ptr [rdi], xmm0
0x18008f698  xor     eax, eax
0x18008f69a  mov     rsi, rdi
0x18008f69d  movups  xmmword ptr [rdi+10h], xmm0
0x18008f6a1  movups  xmmword ptr [rdi+20h], xmm0
0x18008f6a5  mov     [rdi+30h], rax
0x18008f6a9  lea     rdx, [rdi+10h]; pDestinationSid
0x18008f6ad  mov     r8, rbx; pSourceSid
0x18008f6b0  lea     ecx, [rax+28h]; nDestinationSidLength
0x18008f6b3  call    cs:__imp_CopySid
0x18008f6b9  test    eax, eax
0x18008f6bb  jnz     short loc_18008F6E7
0x18008f6bd  call    cs:__imp_GetLastError
0x18008f6c3  mov     ebx, eax
0x18008f6c5  test    eax, eax
0x18008f6c7  jle     short loc_18008F6D2
0x18008f6c9  movzx   ebx, ax
0x18008f6cc  or      ebx, 80070000h
0x18008f6d2  test    ebx, ebx
0x18008f6d4  js      short loc_18008F6DB
0x18008f6d6  mov     ebx, 8000FFFFh
0x18008f6db  mov     edi, ebx
0x18008f6dd  mov     [rsp+38h+var_14], 4Dh ; 'M'
0x18008f6e5  jmp     short loc_18008F735
0x18008f6e7  lea     rcx, ?g_csActiveAppContainerSids@@3VWxCriticalSection@@A; lpCriticalSection
0x18008f6ee  xor     ebx, ebx
0x18008f6f0  call    cs:__imp_EnterCriticalSection
0x18008f6f6  mov     rax, cs:qword_180107D18
0x18008f6fd  lea     rcx, ?g_ActiveAppContainerSidsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ActiveAppContainerSidsListHead
0x18008f704  cmp     [rax], rcx
0x18008f707  jz      short loc_18008F70E
0x18008f709  lea     ecx, [rbx+3]
0x18008f70c  int     29h; Win8: RtlFailFast(ecx)
0x18008f70e  mov     [rdi], rcx
0x18008f711  lea     rcx, ?g_csActiveAppContainerSids@@3VWxCriticalSection@@A; lpCriticalSection
0x18008f718  mov     [rdi+8], rax
0x18008f71c  mov     [rax], rdi
0x18008f71f  mov     cs:qword_180107D18, rdi
0x18008f726  call    cs:__imp_LeaveCriticalSection
0x18008f72c  xor     esi, esi
0x18008f72e  mov     [rsp+38h+var_10], rsi
0x18008f733  xor     edi, edi
0x18008f735  test    rsi, rsi
0x18008f738  jz      short loc_18008F744
0x18008f73a  lea     rcx, [rsp+38h+var_10]
0x18008f73f  call    WxFreeHeapEx
0x18008f744  test    byte ptr cs:xmmword_180107A60, 20h
0x18008f74b  jz      short loc_18008F766
0x18008f74d  mov     edx, 0Dh
0x18008f752  lea     r8, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids
0x18008f759  mov     ecx, 405h
0x18008f75e  mov     r9d, ebx
0x18008f761  call    WPP_SF_d
0x18008f766  mov     rbx, [rsp+38h+arg_8]
0x18008f76b  mov     eax, edi
0x18008f76d  mov     rsi, [rsp+38h+arg_10]
0x18008f772  add     rsp, 30h
0x18008f776  pop     rdi
0x18008f777  retn
```
