# GetProcessWaitChainAsync(ulong,__int64,_WDC_WCT_PARAM *,void * *)

- ea: `0x1800295c4`
- end: `0x180029865`
- name: `?GetProcessWaitChainAsync@@YAJK_JPEAU_WDC_WCT_PARAM@@PEAPEAX@Z`
- size: `673`
- prototype: `int(unsigned int, __int64, struct _WDC_WCT_PARAM *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180078890`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18000e268`
- `0x1800295c4`

## import_xrefs

- `ADVAPI32!CloseThreadWaitChainSession` at `0x180029845`
- `ADVAPI32!CloseThreadWaitChainSession` at `0x180029845`
- `ADVAPI32!OpenThreadWaitChainSession` at `0x180029601`
- `ADVAPI32!OpenThreadWaitChainSession` at `0x180029601`
- `ADVAPI32!GetThreadWaitChain` at `0x1800297bf`
- `ADVAPI32!GetThreadWaitChain` at `0x1800297bf`
- `KERNEL32!GetLastError` at `0x180029613`
- `KERNEL32!GetLastError` at `0x1800296ba`
- `KERNEL32!GetLastError` at `0x1800297c9`
- `KERNEL32!GetLastError` at `0x180029613`
- `KERNEL32!GetLastError` at `0x1800296ba`
- `KERNEL32!GetLastError` at `0x1800297c9`
- `USER32!PostMessageW` at `0x1800297f6`
- `USER32!PostMessageW` at `0x1800297f6`

## pseudocode

```c
__int64 __fastcall GetProcessWaitChainAsync(int a1, __int64 a2, struct _WDC_WCT_PARAM *a3, void **a4)
{
  HWCT v7; // rax
  void *v8; // rbp
  signed int LastError; // eax
  signed int i; // ebx
  int v11; // eax
  const char *v12; // rdx
  int v13; // r8d
  void *v14; // r15
  signed int v15; // eax
  unsigned int *v16; // rdi
  void *v17; // rax
  unsigned int v18; // eax
  unsigned int *v19; // r13
  unsigned int v20; // r14d
  DWORD v21; // r9d
  __int64 v22; // r12
  signed int NodeCount; // [rsp+20h] [rbp-58h]
  unsigned __int64 v25; // [rsp+90h] [rbp+18h] BYREF
  void *v26; // [rsp+98h] [rbp+20h] BYREF

  v25 = 0;
  v26 = 0;
  *((_DWORD *)a3 + 9) = 0;
  v7 = OpenThreadWaitChainSession(1u, WdcThreadWaitChainCallback);
  v8 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    i = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        i = (unsigned __int16)LastError | 0x80070000;
      if ( i >= 0 )
        goto LABEL_6;
    }
    else
    {
      i = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\waitchain.cpp",
      "GetProcessWaitChainAsync",
      0,
      L"FAILURE: 0x%08x",
      i);
    return (unsigned int)i;
  }
  if ( v7 != (HWCT)-1LL )
    goto LABEL_6;
  v15 = GetLastError();
  i = v15;
  if ( !v15 )
  {
    i = -2147467259;
LABEL_18:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\waitchain.cpp",
      "GetProcessWaitChainAsync",
      0,
      L"FAILURE: 0x%08x",
      i);
LABEL_41:
    CloseThreadWaitChainSession(v8);
    return (unsigned int)i;
  }
  if ( v15 > 0 )
    i = (unsigned __int16)v15 | 0x80070000;
  if ( i < 0 )
    goto LABEL_18;
LABEL_6:
  v11 = WdcExpandingCall((int (*)(struct _WDC_EXPANDING_CALL *))WdcQueryProcessInformation, &v25, &v26, 0);
  v14 = v26;
  i = v11;
  if ( v11 >= 0 )
  {
    v16 = (unsigned int *)v26;
    do
    {
      if ( !*v16 )
        goto LABEL_36;
      v16 = (unsigned int *)((char *)v16 + *v16);
    }
    while ( v16[20] != a1 || *((_QWORD *)v16 + 4) != a2 );
    if ( !v16[1] )
    {
LABEL_36:
      i = -2147467259;
      goto LABEL_37;
    }
    v17 = WdcAlloc(4488LL * v16[1], v12, v13);
    *(_QWORD *)a3 = v17;
    if ( v17 )
    {
      v18 = v16[1];
      if ( v18 <= 0x7FFFFFFF )
      {
        *((_DWORD *)a3 + 9) = v18;
        v19 = v16 + 64;
        v20 = 0;
        *((_DWORD *)a3 + 6) = v16[1];
        for ( i = 0; v20 < v16[1]; v19 += 20 )
        {
          v21 = v19[12];
          v22 = *(_QWORD *)a3 + 4488LL * v20;
          *(_DWORD *)v22 = 16;
          if ( !GetThreadWaitChain(
                  v8,
                  (DWORD_PTR)a3,
                  0xBu,
                  v21,
                  (LPDWORD)v22,
                  (PWAITCHAIN_NODE_INFO)(v22 + 8),
                  (LPBOOL)(v22 + 4))
            && GetLastError() != 997 )
          {
            *(_DWORD *)v22 = 0;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 9, 0xFFFFFFFF) == 1 )
              PostMessageW(*((HWND *)a3 + 2), 0x403u, 0, 0);
          }
          ++v20;
        }
        qword_1800B5520 = v8;
        goto LABEL_37;
      }
      *((_DWORD *)a3 + 9) = -1;
      i = -2147024362;
    }
    else
    {
      i = -2147024882;
    }
    NodeCount = i;
    goto LABEL_8;
  }
  NodeCount = v11;
LABEL_8:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\waitchain.cpp",
    "GetProcessWaitChainAsync",
    0,
    L"FAILURE: 0x%08x",
    NodeCount);
LABEL_37:
  if ( v14 )
    WdcFree(v14, v12, v13);
  if ( i < 0 && v8 )
    goto LABEL_41;
  return (unsigned int)i;
}

```

## disassembly

```asm
0x1800295c4  mov     rax, rsp
0x1800295c7  mov     [rax+8], rbx
0x1800295cb  mov     [rax+20h], r9
0x1800295cf  push    rbp
0x1800295d0  push    rsi
0x1800295d1  push    rdi
0x1800295d2  push    r12
0x1800295d4  push    r13
0x1800295d6  push    r14
0x1800295d8  push    r15
0x1800295da  sub     rsp, 40h
0x1800295de  xor     r13d, r13d
0x1800295e1  mov     r14, rdx
0x1800295e4  mov     r12d, ecx
0x1800295e7  mov     [rax+18h], r13
0x1800295eb  lea     rdx, ?WdcThreadWaitChainCallback@@YAXPEAX_KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z; callback
0x1800295f2  mov     [rax+20h], r13
0x1800295f6  mov     rsi, r8
0x1800295f9  mov     [r8+24h], r13d
0x1800295fd  lea     ecx, [r13+1]; Flags
0x180029601  call    cs:__imp_OpenThreadWaitChainSession
0x180029607  mov     rbp, rax
0x18002960a  test    rax, rax
0x18002960d  jnz     loc_1800296B0
0x180029613  call    cs:__imp_GetLastError
0x180029619  mov     ebx, eax
0x18002961b  test    eax, eax
0x18002961d  jz      short loc_180029685
0x18002961f  jle     short loc_18002962A
0x180029621  movzx   ebx, ax
0x180029624  or      ebx, 80070000h
0x18002962a  test    ebx, ebx
0x18002962c  js      short loc_18002968A
0x18002962e  xor     r9d, r9d; unsigned int
0x180029631  lea     r8, [rsp+78h+arg_18]; void **
0x180029639  lea     rdx, [rsp+78h+arg_10]; unsigned __int64 *
0x180029641  lea     rcx, ?WdcQueryProcessInformation@@YAJPEAU_WDC_EXPANDING_CALL@@@Z; int (*)(struct _WDC_EXPANDING_CALL *)
0x180029648  call    ?WdcExpandingCall@@YAJP6AJPEAU_WDC_EXPANDING_CALL@@@ZPEA_KPEAPEAXKZZ; WdcExpandingCall(long (*)(_WDC_EXPANDING_CALL *),unsigned __int64 *,void * *,ulong,...)
0x18002964d  mov     r15, [rsp+78h+arg_18]
0x180029655  mov     ebx, eax
0x180029657  test    eax, eax
0x180029659  jns     loc_180029706
0x18002965f  mov     dword ptr [rsp+78h+NodeCount], eax
0x180029663  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002966a  xor     r8d, r8d; int
0x18002966d  lea     rdx, aGetprocesswait; "GetProcessWaitChainAsync"
0x180029674  lea     rcx, aBaseDiagnosisP_51; "base\\diagnosis\\pdui\\perfmon\\mon\\wa"...
0x18002967b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180029680  jmp     loc_18002982C
0x180029685  mov     ebx, 80004005h
0x18002968a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180029691  mov     dword ptr [rsp+78h+NodeCount], ebx
0x180029695  xor     r8d, r8d; int
0x180029698  lea     rdx, aGetprocesswait; "GetProcessWaitChainAsync"
0x18002969f  lea     rcx, aBaseDiagnosisP_51; "base\\diagnosis\\pdui\\perfmon\\mon\\wa"...
0x1800296a6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800296ab  jmp     loc_18002984B
0x1800296b0  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800296b4  jnz     loc_18002962E
0x1800296ba  call    cs:__imp_GetLastError
0x1800296c0  mov     ebx, eax
0x1800296c2  test    eax, eax
0x1800296c4  jz      short loc_1800296DB
0x1800296c6  jle     short loc_1800296D1
0x1800296c8  movzx   ebx, ax
0x1800296cb  or      ebx, 80070000h
0x1800296d1  test    ebx, ebx
0x1800296d3  jns     loc_18002962E
0x1800296d9  jmp     short loc_1800296E0
0x1800296db  mov     ebx, 80004005h
0x1800296e0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800296e7  mov     dword ptr [rsp+78h+NodeCount], ebx
0x1800296eb  xor     r8d, r8d; int
0x1800296ee  lea     rdx, aGetprocesswait; "GetProcessWaitChainAsync"
0x1800296f5  lea     rcx, aBaseDiagnosisP_51; "base\\diagnosis\\pdui\\perfmon\\mon\\wa"...
0x1800296fc  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180029701  jmp     loc_180029842
0x180029706  mov     rdi, r15
0x180029709  cmp     [rdi], r13d
0x18002970c  jz      loc_180029827
0x180029712  mov     eax, [rdi]
0x180029714  add     rdi, rax
0x180029717  cmp     [rdi+50h], r12d
0x18002971b  jnz     short loc_180029709
0x18002971d  cmp     [rdi+20h], r14
0x180029721  jnz     short loc_180029709
0x180029723  cmp     [rdi+4], r13d
0x180029727  jz      loc_180029827
0x18002972d  mov     eax, [rdi+4]
0x180029730  imul    rcx, rax, 1188h; dwBytes
0x180029737  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002973c  mov     [rsi], rax
0x18002973f  test    rax, rax
0x180029742  jnz     short loc_180029752
0x180029744  mov     ebx, 8007000Eh
0x180029749  mov     dword ptr [rsp+78h+NodeCount], ebx
0x18002974d  jmp     loc_180029663
0x180029752  mov     eax, [rdi+4]
0x180029755  cmp     eax, 7FFFFFFFh
0x18002975a  ja      loc_180029816
0x180029760  mov     [rsi+24h], eax
0x180029763  mov     ecx, r13d
0x180029766  mov     eax, [rdi+4]
0x180029769  lea     r13, [rdi+100h]
0x180029770  xor     r14d, r14d
0x180029773  mov     [rsi+18h], eax
0x180029776  xor     ebx, ebx
0x180029778  cmp     [rdi+4], ecx
0x18002977b  jbe     loc_18002980D
0x180029781  mov     r9d, [r13+30h]; ThreadId
0x180029785  mov     r8d, 0Bh; Flags
0x18002978b  mov     eax, r14d
0x18002978e  mov     rdx, rsi; Context
0x180029791  imul    r12, rax, 1188h
0x180029798  add     r12, [rsi]
0x18002979b  lea     rax, [r12+4]
0x1800297a0  mov     dword ptr [r12], 10h
0x1800297a8  mov     [rsp+78h+IsCycle], rax; IsCycle
0x1800297ad  lea     rcx, [r12+8]
0x1800297b2  mov     [rsp+78h+NodeInfoArray], rcx; NodeInfoArray
0x1800297b7  mov     rcx, rbp; WctHandle
0x1800297ba  mov     [rsp+78h+NodeCount], r12; NodeCount
0x1800297bf  call    cs:__imp_GetThreadWaitChain
0x1800297c5  test    eax, eax
0x1800297c7  jnz     short loc_1800297FC
0x1800297c9  call    cs:__imp_GetLastError
0x1800297cf  cmp     eax, 3E5h
0x1800297d4  jz      short loc_1800297FC
0x1800297d6  mov     [r12], ebx
0x1800297da  or      eax, 0FFFFFFFFh
0x1800297dd  lock xadd [rsi+24h], eax
0x1800297e2  cmp     eax, 1
0x1800297e5  jnz     short loc_1800297FC
0x1800297e7  mov     rcx, [rsi+10h]; hWnd
0x1800297eb  xor     r9d, r9d; lParam
0x1800297ee  xor     r8d, r8d; wParam
0x1800297f1  mov     edx, 403h; Msg
0x1800297f6  call    cs:__imp_PostMessageW
0x1800297fc  inc     r14d
0x1800297ff  add     r13, 50h ; 'P'
0x180029803  cmp     r14d, [rdi+4]
0x180029807  jb      loc_180029781
0x18002980d  mov     cs:qword_1800B5520, rbp
0x180029814  jmp     short loc_18002982C
0x180029816  mov     dword ptr [rsi+24h], 0FFFFFFFFh
0x18002981d  mov     ebx, 80070216h
0x180029822  jmp     loc_180029749
0x180029827  mov     ebx, 80004005h
0x18002982c  test    r15, r15
0x18002982f  jz      short loc_180029839
0x180029831  mov     rcx, r15; void *
0x180029834  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180029839  test    ebx, ebx
0x18002983b  jns     short loc_18002984B
0x18002983d  test    rbp, rbp
0x180029840  jz      short loc_18002984B
0x180029842  mov     rcx, rbp; WctHandle
0x180029845  call    cs:__imp_CloseThreadWaitChainSession
0x18002984b  mov     eax, ebx
0x18002984d  mov     rbx, [rsp+78h+arg_0]
0x180029855  add     rsp, 40h
0x180029859  pop     r15
0x18002985b  pop     r14
0x18002985d  pop     r13
0x18002985f  pop     r12
0x180029861  pop     rdi
0x180029862  pop     rsi
0x180029863  pop     rbp
0x180029864  retn
```
