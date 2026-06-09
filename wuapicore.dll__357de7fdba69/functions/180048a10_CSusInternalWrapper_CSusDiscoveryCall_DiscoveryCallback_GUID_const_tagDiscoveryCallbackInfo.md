# CSusInternalWrapper::CSusDiscoveryCall::DiscoveryCallback(_GUID const &,tagDiscoveryCallbackInfo)

- ea: `0x180048a10`
- end: `0x180048d0a`
- name: `?DiscoveryCallback@CSusDiscoveryCall@CSusInternalWrapper@@EEAAJAEBU_GUID@@UtagDiscoveryCallbackInfo@@@Z`
- size: `762`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180041410`
- `0x1800432ec`
- `0x180048a10`
- `0x180081a38`
- `0x18008dff0`
- `0x180090bc8`
- `0x18009b24c`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048ca5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048ca5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048bea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048b04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048b04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048af2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048af2`

## string_xrefs

- `0x180048ac2`: `create callback info`
- `0x180048a78`: `Discovery call failed due to self-update; will retry.`

## pseudocode

```c
__int64 __fastcall CSusInternalWrapper::CSusDiscoveryCall::DiscoveryCallback(__int64 a1, _OWORD *a2, __int64 a3)
{
  struct CSusInternalWrapper::CSusCallbackInfo *v6; // rax
  struct CSusInternalWrapper::CSusCallbackInfo *v7; // rbx
  int v8; // edi
  HANDLE ProcessHeap; // rax
  _OWORD *v10; // rax
  __int128 v11; // xmm1
  __int64 v12; // xmm0_8
  __int64 v13; // r15
  unsigned int v14; // r14d
  __int64 v15; // rbp
  _BYTE *v16; // rax
  void *v17; // rcx
  __int64 v18; // r8
  _BYTE *v19; // rdx
  char v20; // al
  _BYTE *v21; // rax
  __int64 v23; // [rsp+20h] [rbp-48h]

  WUTrace(
    0,
    0,
    0x10000,
    5,
    0,
    L"CSusInternalWrapper::CSusDiscoveryCall::DiscoveryCallback Called.  callbackInfo - cchData[%lu]",
    *(_DWORD *)(a3 + 8));
  if ( *(_DWORD *)a3 == 4 && *(_DWORD *)(a3 + 4) == -2145124325 )
  {
    WUTrace(0, 0, 0x10000, 5, 0, L"Discovery call failed due to self-update; will retry.");
    CSusInternalWrapper::CSusCall::AddRefOnCallForSelfUpdate((CSusInternalWrapper::CSusCall *)(a1 - 144));
    return 0;
  }
  while ( 1 )
  {
    v6 = (struct CSusInternalWrapper::CSusCallbackInfo *)operator new(
                                                           0x28u,
                                                           (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
      break;
    NeedToRetryAfterWait(-2147024882, L"create callback info");
  }
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *(_QWORD *)v6 = &CSusInternalWrapper::CDiscoveryCallbackInfo::`vftable';
  *((_QWORD *)v6 + 4) = 0;
  while ( 1 )
  {
    v8 = 0;
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 8u, 0x28u);
    *((_QWORD *)v7 + 3) = v10;
    if ( !v10 )
    {
      v8 = -2147024882;
LABEL_24:
      SusFree(*((void **)v7 + 3));
      *((_QWORD *)v7 + 3) = 0;
      goto LABEL_25;
    }
    v11 = *(_OWORD *)(a3 + 16);
    *v10 = *(_OWORD *)a3;
    v12 = *(_QWORD *)(a3 + 32);
    v10[1] = v11;
    *((_QWORD *)v10 + 4) = v12;
    v13 = *((_QWORD *)v7 + 3);
    if ( *(_QWORD *)(v13 + 16) )
    {
      v14 = *(_DWORD *)(v13 + 8);
      if ( v14 )
        break;
    }
LABEL_25:
    if ( v8 >= 0 )
      goto LABEL_29;
    if ( !(unsigned int)NeedToRetryAfterWait(v8, L"initialize callback info") )
      goto LABEL_41;
  }
  v15 = v14;
  v16 = CoTaskMemAlloc(v14);
  v17 = v16;
  if ( !v16 )
  {
    v8 = -2147024882;
    goto LABEL_24;
  }
  if ( v14 > 0x7FFFFFFF )
  {
    v8 = -2147024809;
    *v16 = 0;
LABEL_23:
    CoTaskMemFree(v17);
    goto LABEL_24;
  }
  if ( v14 > 0x7FFFFFFE )
  {
    v8 = -2147024809;
    *v16 = 0;
    goto LABEL_23;
  }
  v18 = *(_QWORD *)(v13 + 16) - (_QWORD)v16;
  v19 = v16;
  do
  {
    v20 = v19[v18];
    if ( !v20 )
      break;
    *v19++ = v20;
    --v15;
  }
  while ( v15 );
  v21 = v19 - 1;
  if ( v15 )
    v21 = v19;
  *v21 = 0;
  v8 = v15 == 0 ? 0x8007007A : 0;
  if ( !v15 )
    goto LABEL_23;
  *((_QWORD *)v7 + 4) = v17;
LABEL_29:
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 - 144 + 96));
  if ( *(_DWORD *)(a1 - 136) == GUID_NULL.Data1
    && *(_DWORD *)(a1 - 132) == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)(a1 - 128) == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)(a1 - 124) == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    *(_OWORD *)(a1 - 136) = *a2;
  }
  if ( *(_DWORD *)(a1 - 116) )
    goto LABEL_39;
  if ( *(_DWORD *)(a1 - 120) )
    goto LABEL_38;
  v8 = CSusInternalWrapper::CSusCall::EnqueueCallback((PVOID)(a1 - 144), v7);
  if ( v8 >= 0 )
  {
    v7 = 0;
LABEL_38:
    *(_DWORD *)(a1 - 116) = 1;
LABEL_39:
    v8 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 - 144 + 96));
  if ( v8 >= 0 )
    goto LABEL_42;
LABEL_41:
  LODWORD(v23) = v8;
  WUTrace(0, 0, 0x10000, 5, v23, L"DiscoveryCallback failed");
LABEL_42:
  if ( v7 )
    (**(void (__fastcall ***)(struct CSusInternalWrapper::CSusCallbackInfo *, __int64))v7)(v7, 1);
  return 0;
}

```

## disassembly

```asm
0x180048a10  mov     r11, rsp
0x180048a13  mov     [r11+8], rbx
0x180048a17  mov     [r11+10h], rbp
0x180048a1b  mov     [r11+20h], rsi
0x180048a1f  push    rdi
0x180048a20  push    r12
0x180048a22  push    r13
0x180048a24  push    r14
0x180048a26  push    r15
0x180048a28  sub     rsp, 40h
0x180048a2c  mov     eax, [r8+8]
0x180048a30  xor     r14d, r14d
0x180048a33  mov     [rsp+68h+var_38], eax
0x180048a37  mov     r13, r8
0x180048a3a  lea     rax, aCsusinternalwr; "CSusInternalWrapper::CSusDiscoveryCall:"...
0x180048a41  mov     r12, rdx
0x180048a44  mov     rsi, rcx
0x180048a47  mov     [r11-40h], rax
0x180048a4b  lea     ebx, [r14+5]
0x180048a4f  mov     [r11-48h], r14
0x180048a53  mov     edi, 10000h
0x180048a58  mov     r9d, ebx
0x180048a5b  mov     r8d, edi
0x180048a5e  xor     edx, edx
0x180048a60  xor     ecx, ecx
0x180048a62  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180048a67  cmp     dword ptr [r13+0], 4
0x180048a6c  jnz     short loc_180048AA9
0x180048a6e  cmp     dword ptr [r13+4], 8024001Bh
0x180048a76  jnz     short loc_180048AA9
0x180048a78  lea     rax, aDiscoveryCallF; "Discovery call failed due to self-updat"...
0x180048a7f  mov     r9d, ebx
0x180048a82  mov     [rsp+68h+var_40], rax
0x180048a87  mov     r8d, edi
0x180048a8a  xor     edx, edx
0x180048a8c  mov     [rsp+68h+var_48], r14
0x180048a91  xor     ecx, ecx
0x180048a93  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180048a98  lea     rcx, [rsi-90h]; this
0x180048a9f  call    ?AddRefOnCallForSelfUpdate@CSusCall@CSusInternalWrapper@@QEAAXXZ; CSusInternalWrapper::CSusCall::AddRefOnCallForSelfUpdate(void)
0x180048aa4  jmp     loc_180048CEA
0x180048aa9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180048ab0  mov     ecx, 28h ; '('; unsigned __int64
0x180048ab5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048aba  mov     rbx, rax
0x180048abd  test    rax, rax
0x180048ac0  jnz     short loc_180048AD5
0x180048ac2  lea     rdx, aCreateCallback_0; "create callback info"
0x180048ac9  mov     ecx, 8007000Eh; int
0x180048ace  call    ?NeedToRetryAfterWait@@YAHJPEB_W@Z; NeedToRetryAfterWait(long,wchar_t const *)
0x180048ad3  jmp     short loc_180048AA9
0x180048ad5  mov     [rax+8], r14
0x180048ad9  mov     [rax+10h], r14
0x180048add  mov     [rax+18h], r14
0x180048ae1  lea     rax, ??_7CDiscoveryCallbackInfo@CSusInternalWrapper@@6B@; const CSusInternalWrapper::CDiscoveryCallbackInfo::`vftable'
0x180048ae8  mov     [rbx], rax
0x180048aeb  mov     [rbx+20h], r14
0x180048aef  mov     edi, r14d
0x180048af2  call    cs:__imp_GetProcessHeap
0x180048af8  mov     edx, 8; dwFlags
0x180048afd  mov     rcx, rax; hHeap
0x180048b00  lea     r8d, [rdx+20h]; dwBytes
0x180048b04  call    cs:__imp_HeapAlloc
0x180048b0a  mov     [rbx+18h], rax
0x180048b0e  test    rax, rax
0x180048b11  jnz     short loc_180048B1D
0x180048b13  mov     edi, 8007000Eh
0x180048b18  jmp     loc_180048BF0
0x180048b1d  movups  xmm0, xmmword ptr [r13+0]
0x180048b22  movups  xmm1, xmmword ptr [r13+10h]
0x180048b27  movups  xmmword ptr [rax], xmm0
0x180048b2a  movsd   xmm0, qword ptr [r13+20h]
0x180048b30  movups  xmmword ptr [rax+10h], xmm1
0x180048b34  movsd   qword ptr [rax+20h], xmm0
0x180048b39  mov     r15, [rbx+18h]
0x180048b3d  cmp     [r15+10h], r14
0x180048b41  jz      loc_180048C02
0x180048b47  mov     r14d, [r15+8]
0x180048b4b  test    r14d, r14d
0x180048b4e  jz      loc_180048BFF
0x180048b54  mov     ecx, r14d; cb
0x180048b57  mov     ebp, r14d
0x180048b5a  call    cs:__imp_CoTaskMemAlloc
0x180048b60  mov     rcx, rax; pv
0x180048b63  test    rax, rax
0x180048b66  jnz     short loc_180048B72
0x180048b68  mov     edi, 8007000Eh
0x180048b6d  xor     r14d, r14d
0x180048b70  jmp     short loc_180048BF0
0x180048b72  mov     r8, [r15+10h]
0x180048b76  cmp     r14d, 7FFFFFFFh
0x180048b7d  jbe     short loc_180048B98
0x180048b7f  mov     r15d, 80070057h
0x180048b85  xor     r14d, r14d
0x180048b88  mov     eax, r15d
0x180048b8b  mov     edi, r15d
0x180048b8e  test    rbp, rbp
0x180048b91  jz      short loc_180048BE4
0x180048b93  mov     [rcx], r14b
0x180048b96  jmp     short loc_180048BEA
0x180048b98  cmp     r14d, 7FFFFFFEh
0x180048b9f  jbe     short loc_180048BAE
0x180048ba1  xor     r14d, r14d
0x180048ba4  mov     edi, 80070057h
0x180048ba9  mov     [rax], r14b
0x180048bac  jmp     short loc_180048BEA
0x180048bae  sub     r8, rcx
0x180048bb1  mov     rdx, rcx
0x180048bb4  xor     r14d, r14d
0x180048bb7  mov     al, [r8+rdx]
0x180048bbb  test    al, al
0x180048bbd  jz      short loc_180048BCA
0x180048bbf  mov     [rdx], al
0x180048bc1  inc     rdx
0x180048bc4  sub     rbp, 1
0x180048bc8  jnz     short loc_180048BB7
0x180048bca  test    rbp, rbp
0x180048bcd  lea     rax, [rdx-1]
0x180048bd1  cmovnz  rax, rdx
0x180048bd5  neg     rbp
0x180048bd8  mov     [rax], r14b
0x180048bdb  sbb     eax, eax
0x180048bdd  not     eax
0x180048bdf  and     eax, 8007007Ah
0x180048be4  mov     edi, eax
0x180048be6  test    eax, eax
0x180048be8  jns     short loc_180048C21
0x180048bea  call    cs:__imp_CoTaskMemFree
0x180048bf0  mov     rcx, [rbx+18h]; lpMem
0x180048bf4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180048bf9  mov     [rbx+18h], r14
0x180048bfd  jmp     short loc_180048C02
0x180048bff  xor     r14d, r14d
0x180048c02  test    edi, edi
0x180048c04  jns     short loc_180048C25
0x180048c06  lea     rdx, aInitializeCall; "initialize callback info"
0x180048c0d  mov     ecx, edi; int
0x180048c0f  call    ?NeedToRetryAfterWait@@YAHJPEB_W@Z; NeedToRetryAfterWait(long,wchar_t const *)
0x180048c14  test    eax, eax
0x180048c16  jnz     loc_180048AEF
0x180048c1c  jmp     loc_180048CAF
0x180048c21  mov     [rbx+20h], rcx
0x180048c25  lea     rdi, [rsi-90h]
0x180048c2c  lea     rbp, [rdi+60h]
0x180048c30  mov     rcx, rbp; lpCriticalSection
0x180048c33  call    cs:__imp_EnterCriticalSection
0x180048c39  mov     eax, cs:GUID_NULL.Data1
0x180048c3f  cmp     [rsi-88h], eax
0x180048c45  jnz     short loc_180048C78
0x180048c47  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180048c4d  cmp     [rsi-84h], eax
0x180048c53  jnz     short loc_180048C78
0x180048c55  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180048c5b  cmp     [rsi-80h], eax
0x180048c5e  jnz     short loc_180048C78
0x180048c60  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180048c66  cmp     [rsi-7Ch], eax
0x180048c69  jnz     short loc_180048C78
0x180048c6b  movups  xmm0, xmmword ptr [r12]
0x180048c70  movdqu  xmmword ptr [rsi-88h], xmm0
0x180048c78  cmp     [rsi-74h], r14d
0x180048c7c  jnz     short loc_180048C9F
0x180048c7e  cmp     [rsi-78h], r14d
0x180048c82  jnz     short loc_180048C98
0x180048c84  mov     rdx, rbx; struct CSusInternalWrapper::CSusCallbackInfo *
0x180048c87  mov     rcx, rdi; Parameter
0x180048c8a  call    ?EnqueueCallback@CSusCall@CSusInternalWrapper@@IEAAJPEAVCSusCallbackInfo@2@@Z; CSusInternalWrapper::CSusCall::EnqueueCallback(CSusInternalWrapper::CSusCallbackInfo *)
0x180048c8f  mov     edi, eax
0x180048c91  test    eax, eax
0x180048c93  js      short loc_180048CA2
0x180048c95  mov     rbx, r14
0x180048c98  mov     dword ptr [rsi-74h], 1
0x180048c9f  mov     edi, r14d
0x180048ca2  mov     rcx, rbp; lpCriticalSection
0x180048ca5  call    cs:__imp_LeaveCriticalSection
0x180048cab  test    edi, edi
0x180048cad  jns     short loc_180048CD2
0x180048caf  xor     edx, edx
0x180048cb1  lea     rax, aDiscoverycallb; "DiscoveryCallback failed"
0x180048cb8  mov     [rsp+68h+var_40], rax
0x180048cbd  xor     ecx, ecx
0x180048cbf  mov     r8d, 10000h
0x180048cc5  mov     dword ptr [rsp+68h+var_48], edi
0x180048cc9  lea     r9d, [rdx+5]
0x180048ccd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180048cd2  test    rbx, rbx
0x180048cd5  jz      short loc_180048CEA
0x180048cd7  mov     rax, [rbx]
0x180048cda  mov     edx, 1
0x180048cdf  mov     rcx, rbx
0x180048ce2  mov     rax, [rax]
0x180048ce5  call    _guard_dispatch_icall
0x180048cea  lea     r11, [rsp+68h+var_28]
0x180048cef  xor     eax, eax
0x180048cf1  mov     rbx, [r11+30h]
0x180048cf5  mov     rbp, [r11+38h]
0x180048cf9  mov     rsi, [r11+48h]
0x180048cfd  mov     rsp, r11
0x180048d00  pop     r15
0x180048d02  pop     r14
0x180048d04  pop     r13
0x180048d06  pop     r12
0x180048d08  pop     rdi
0x180048d09  retn
```
