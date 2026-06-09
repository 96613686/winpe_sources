# PfRbPrefetchStateMachine

- ea: `0x1800169a0`
- end: `0x180016e4a`
- name: `PfRbPrefetchStateMachine`
- size: `1194`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x1800167cc`

## callees

- `0x180015e14`
- `0x1800164bc`
- `0x1800169a0`
- `0x180016e50`
- `0x180016f10`
- `0x180016f70`
- `0x1800170b0`
- `0x180064ad8`
- `0x18006bdf8`
- `0x1800900a4`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016beb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e3f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180016dcf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180016dcf`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180016e34`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180016e34`

## pseudocode

```c
DWORD __fastcall PfRbPrefetchStateMachine(__int64 a1)
{
  _QWORD *v1; // r15
  int *v2; // r13
  __int64 v4; // r11
  int v5; // edi
  int v6; // ebx
  __int64 v7; // rdx
  int i; // ecx
  int j; // edx
  int v10; // eax
  __int64 v11; // r11
  unsigned int v12; // eax
  unsigned int v13; // r12d
  int v14; // r14d
  int v15; // r12d
  DWORD result; // eax
  int v17; // r12d
  void *v18; // rcx
  __int64 v19; // r13
  int v20; // eax
  int v21; // eax
  _BOOL8 v22; // r8
  HANDLE Thread; // rax
  TRACEHANDLE v24; // rcx
  int v25; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-55h]
  unsigned __int64 v27; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int64 v28; // [rsp+40h] [rbp-49h] BYREF
  __int64 v29; // [rsp+48h] [rbp-41h]
  _EVENT_TRACE_HEADER EventTrace; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int64 *v31; // [rsp+80h] [rbp-9h]
  int v32; // [rsp+88h] [rbp-1h]

  v1 = (_QWORD *)(a1 + 1944);
  v2 = (int *)(a1 + 3888);
  v4 = 176 * ((*(_DWORD *)(a1 + 40) - 1) & 1LL) + a1 + 48;
  v5 = 7;
  v29 = v4;
  v6 = 0;
  v28 = 0;
  v25 = 0;
  v27 = 0;
  do
  {
    if ( *(_QWORD *)(v4 + 8LL * (unsigned int)v5 + 104) - *(_QWORD *)(a1 + 8LL * (unsigned int)v5 + 400) > 0x800u )
      break;
    --v5;
  }
  while ( v5 >= 0 );
  v7 = *(_QWORD *)(a1 + 6824);
  for ( i = 7; i >= 0; --i )
  {
    if ( *(_DWORD *)(v7 + 4LL * (unsigned int)i + 4) > 0x400u )
      break;
  }
  for ( j = 7; j >= 0; --j )
  {
    if ( *(_DWORD *)(a1 + 4LL * (unsigned int)j + 6988) > 0x300u )
      break;
  }
  if ( i <= j )
  {
    for ( i = 7; i >= 0; --i )
    {
      if ( *(_DWORD *)(a1 + 4LL * (unsigned int)i + 6988) > 0x300u )
        break;
    }
  }
  v10 = *((_DWORD *)v1 + 3);
  if ( v5 <= i )
    v5 = i;
  if ( (v10 & 0x10) != 0 )
  {
    v10 &= ~0x10u;
    v5 = 7;
    *((_DWORD *)v1 + 3) = v10;
  }
  if ( (v10 & 0x40) != 0 )
  {
    if ( v2[16] > -1 )
      v6 = 1;
    *((_DWORD *)v1 + 3) = v10 & 0xFFFFFFBF;
    v25 = v6;
  }
  if ( v5 < 1 || v5 < v2[16] )
  {
    v5 = v2[16];
  }
  else
  {
    v6 |= 1u;
    v25 = v6;
  }
  PfRbPrefetchSetThresholds(a1, (unsigned int)v5);
  if ( v5 <= -1 )
  {
    v13 = 0;
  }
  else
  {
    v12 = PfRbPrefetchProcessMemInfo(a1, v11, (unsigned int)v5, &v25);
    v6 = v25;
    v13 = v12;
  }
  v26 = v13;
  PfRbPrefetchPolicyCheck(a1, (unsigned int)v5);
  PfRbPrefetchEnable(a1, 2);
  if ( *((_DWORD *)v1 + 9) != 28 )
  {
    if ( *((_DWORD *)v1 + 9) )
      v6 |= 8u;
    else
      v6 |= 0x10u;
  }
  v27 = __PAIR64__(v6, v13);
  if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 460LL) & 8) != 0 )
    PfLgpTraceEvent(*(_QWORD *)&PfSvcGlobals + 384LL, 18, &v27, 8);
  v14 = *((_DWORD *)v1 + 2);
  while ( 1 )
  {
    v25 = v14;
    v15 = v14;
    if ( !v14 )
      break;
    if ( v14 == 1 )
    {
      v17 = v2[16];
      if ( (v6 & 1) != 0 )
        PfRbCursorSetPriority(v2);
      if ( !*(_QWORD *)v2 )
      {
        if ( (v6 & 4) == 0 )
          goto LABEL_31;
        v22 = v5 >= v17 && v2[16] >= 3;
        result = PfRbPrefetchRebuildDb(a1, v26, v22);
        if ( result )
          goto LABEL_32;
        v6 &= 0xFFFFFFEE;
        *(_QWORD *)(a1 + 8LL * v5 + 400) = *(_QWORD *)(v29 + 8LL * v5 + 104);
        *(_DWORD *)(*(_QWORD *)(a1 + 6824) + 4LL * (unsigned int)v5 + 4) = 0;
        *(_DWORD *)(a1 + 4LL * (unsigned int)v5 + 6988) = 0;
      }
      if ( (v6 & 4) == 0 )
        goto LABEL_31;
      v18 = (void *)v1[5];
      v14 = 2;
      *((_DWORD *)v1 + 3) |= 1u;
      *((_DWORD *)v1 + 9) = 28;
      SetEvent(v18);
      v15 = v25;
      v6 &= ~8u;
      goto LABEL_45;
    }
    if ( v14 != 2 )
    {
      if ( v14 != 3 || (v6 & 1) == 0 || *((_DWORD *)v1 + 513) )
      {
LABEL_31:
        PfRbPrefetchPolicyUpdate(a1, v14 == 2);
        result = 0;
        goto LABEL_32;
      }
      v14 = 0;
      goto LABEL_45;
    }
    if ( (v6 & 1) == 0 && (v6 & 8) == 0 )
    {
      if ( (v6 & 2) == 0 )
        goto LABEL_62;
      if ( (v6 & 0x10) != 0 )
        goto LABEL_63;
    }
    v6 &= ~0x10u;
    v20 = PfRbPrefetchControl(v1, 4);
    v14 = 1;
    if ( (v6 & 1) == 0 && !v20 )
      v6 |= 0x10u;
LABEL_62:
    if ( (v6 & 0x10) != 0 )
    {
LABEL_63:
      v21 = v2[16];
      if ( v21 > 1 )
      {
        v5 = v21 - 1;
        v25 = v6 | 1;
        PfRbPrefetchSetThresholds(a1, (unsigned int)(v21 - 1));
        v26 = PfRbPrefetchProcessMemInfo(a1, v29, (unsigned int)v5, &v25);
        PfRbPrefetchControl(v1, 4);
        v6 = v25;
        v14 = 1;
        goto LABEL_46;
      }
      PfRbPrefetchControl(v1, 1);
      v14 = 3;
    }
LABEL_45:
    if ( v14 == v15 )
      goto LABEL_31;
LABEL_46:
    v19 = *(_QWORD *)&PfSvcGlobals;
    v28 = __PAIR64__(v14, v15);
    if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 460LL) & 1) != 0 )
    {
      memset_0(&EventTrace, 0, 0x40u);
      v24 = *(_QWORD *)(v19 + 448);
      EventTrace.GuidPtr = (ULONGLONG)PfLgEventGuid;
      EventTrace.Size = 64;
      v31 = &v28;
      EventTrace.UserTime = 1703936;
      EventTrace.Class.Type = 11;
      v32 = 8;
      TraceEvent(v24, &EventTrace);
    }
    v2 = (int *)(v1 + 243);
  }
  PfRbCursorSetPriority(v2);
  if ( (v6 & 4) == 0 )
    goto LABEL_31;
  Thread = CreateThread(0, 0, PfRbPrefetchWorker, v1, 0, 0);
  *v1 = Thread;
  if ( Thread )
  {
    v14 = 1;
    v6 |= 1u;
    goto LABEL_46;
  }
  result = GetLastError();
LABEL_32:
  *((_DWORD *)v1 + 2) = v14;
  return result;
}

```

## disassembly

```asm
0x1800169a0  push    rbp
0x1800169a2  push    rbx
0x1800169a3  push    rsi
0x1800169a4  push    rdi
0x1800169a5  push    r12
0x1800169a7  push    r13
0x1800169a9  push    r14
0x1800169ab  push    r15
0x1800169ad  lea     rbp, [rsp-1Fh]
0x1800169b2  sub     rsp, 0A8h
0x1800169b9  mov     rax, cs:__security_cookie
0x1800169c0  xor     rax, rsp
0x1800169c3  mov     [rbp+57h+var_50], rax
0x1800169c7  mov     eax, [rcx+28h]
0x1800169ca  lea     r11, [rcx+30h]
0x1800169ce  mov     r8d, 1
0x1800169d4  lea     r15, [rcx+798h]
0x1800169db  sub     eax, r8d
0x1800169de  lea     r13, [r15+798h]
0x1800169e5  and     rax, r8
0x1800169e8  mov     rsi, rcx
0x1800169eb  imul    rax, 0B0h
0x1800169f2  lea     r9d, [r8+6]
0x1800169f6  add     r11, rax
0x1800169f9  mov     edi, r9d
0x1800169fc  xor     r14d, r14d
0x1800169ff  mov     [rbp+57h+var_98], r11
0x180016a03  mov     ebx, r14d
0x180016a06  mov     [rbp+57h+var_A0], r14
0x180016a0a  mov     [rbp+57h+var_B0], ebx
0x180016a0d  mov     [rbp+57h+var_A8], r14
0x180016a11  mov     eax, edi
0x180016a13  mov     rcx, [r11+rax*8+68h]
0x180016a18  sub     rcx, [rsi+rax*8+190h]
0x180016a20  cmp     rcx, 800h
0x180016a27  jbe     loc_180016BA5
0x180016a2d  mov     rdx, [rsi+1AA8h]
0x180016a34  mov     ecx, r9d
0x180016a37  mov     eax, ecx
0x180016a39  cmp     dword ptr [rdx+rax*4+4], 400h
0x180016a41  ja      short loc_180016A48
0x180016a43  sub     ecx, r8d
0x180016a46  jns     short loc_180016A37
0x180016a48  mov     edx, r9d
0x180016a4b  mov     r10d, 300h
0x180016a51  mov     eax, edx
0x180016a53  cmp     [rsi+rax*4+1B4Ch], r10d
0x180016a5b  ja      short loc_180016A62
0x180016a5d  sub     edx, r8d
0x180016a60  jns     short loc_180016A51
0x180016a62  cmp     ecx, edx
0x180016a64  jg      short loc_180016A7A
0x180016a66  mov     ecx, r9d
0x180016a69  mov     eax, ecx
0x180016a6b  cmp     [rsi+rax*4+1B4Ch], r10d
0x180016a73  ja      short loc_180016A7A
0x180016a75  sub     ecx, r8d
0x180016a78  jns     short loc_180016A69
0x180016a7a  mov     eax, [r15+0Ch]
0x180016a7e  cmp     edi, ecx
0x180016a80  cmovle  edi, ecx
0x180016a83  test    al, 10h
0x180016a85  jnz     loc_180016C2A
0x180016a8b  test    al, 40h
0x180016a8d  jnz     loc_180016C39
0x180016a93  cmp     edi, r8d
0x180016a96  jl      loc_180016B9C
0x180016a9c  cmp     edi, [r13+40h]
0x180016aa0  jl      loc_180016B9C
0x180016aa6  or      ebx, r8d
0x180016aa9  mov     [rbp+57h+var_B0], ebx
0x180016aac  mov     edx, edi
0x180016aae  mov     rcx, rsi
0x180016ab1  call    PfRbPrefetchSetThresholds
0x180016ab6  cmp     edi, 0FFFFFFFFh
0x180016ab9  jle     loc_180016B80
0x180016abf  lea     r9, [rbp+57h+var_B0]
0x180016ac3  mov     r8d, edi
0x180016ac6  mov     rdx, r11
0x180016ac9  mov     rcx, rsi
0x180016acc  call    PfRbPrefetchProcessMemInfo
0x180016ad1  mov     ebx, [rbp+57h+var_B0]
0x180016ad4  mov     r12d, eax
0x180016ad7  mov     edx, edi
0x180016ad9  mov     [rbp+57h+var_AC], r12d
0x180016add  mov     rcx, rsi
0x180016ae0  call    PfRbPrefetchPolicyCheck
0x180016ae5  mov     r8d, eax
0x180016ae8  mov     edx, 2
0x180016aed  mov     rcx, rsi
0x180016af0  call    PfRbPrefetchEnable
0x180016af5  cmp     dword ptr [r15+24h], 1Ch
0x180016afa  jnz     loc_180016C51
0x180016b00  mov     rcx, cs:PfSvcGlobals
0x180016b07  add     rcx, 180h
0x180016b0e  mov     dword ptr [rbp+57h+var_A8], r12d
0x180016b12  mov     dword ptr [rbp+57h+var_A8+4], ebx
0x180016b15  test    byte ptr [rcx+4Ch], 8
0x180016b19  jnz     loc_180016C67
0x180016b1f  mov     r14d, [r15+8]
0x180016b23  mov     [rbp+57h+var_B0], r14d
0x180016b27  mov     r12d, r14d
0x180016b2a  mov     ecx, r14d
0x180016b2d  test    r14d, r14d
0x180016b30  jz      loc_180016D9D
0x180016b36  sub     ecx, 1
0x180016b39  jz      short loc_180016BB3
0x180016b3b  sub     ecx, 1
0x180016b3e  jz      loc_180016C7F
0x180016b44  cmp     ecx, 1
0x180016b47  jz      short loc_180016B88
0x180016b49  xor     edx, edx
0x180016b4b  mov     rcx, rsi
0x180016b4e  cmp     r14d, 2
0x180016b52  setz    dl
0x180016b55  call    PfRbPrefetchPolicyUpdate
0x180016b5a  xor     eax, eax
0x180016b5c  mov     [r15+8], r14d
0x180016b60  mov     rcx, [rbp+57h+var_50]
0x180016b64  xor     rcx, rsp; StackCookie
0x180016b67  call    __security_check_cookie
0x180016b6c  add     rsp, 0A8h
0x180016b73  pop     r15
0x180016b75  pop     r14
0x180016b77  pop     r13
0x180016b79  pop     r12
0x180016b7b  pop     rdi
0x180016b7c  pop     rsi
0x180016b7d  pop     rbx
0x180016b7e  pop     rbp
0x180016b7f  retn
0x180016b80  mov     r12d, r14d
0x180016b83  jmp     loc_180016AD7
0x180016b88  test    bl, 1
0x180016b8b  jz      short loc_180016B49
0x180016b8d  cmp     dword ptr [r15+804h], 0
0x180016b95  jnz     short loc_180016B49
0x180016b97  xor     r14d, r14d
0x180016b9a  jmp     short loc_180016BF8
0x180016b9c  mov     edi, [r13+40h]
0x180016ba0  jmp     loc_180016AAC
0x180016ba5  sub     edi, r8d
0x180016ba8  js      loc_180016A2D
0x180016bae  jmp     loc_180016A11
0x180016bb3  mov     r12d, [r13+40h]
0x180016bb7  test    bl, 1
0x180016bba  jnz     loc_180016D23
0x180016bc0  cmp     qword ptr [r13+0], 0
0x180016bc5  jz      loc_180016D32
0x180016bcb  test    bl, 4
0x180016bce  jz      loc_180016B49
0x180016bd4  mov     rcx, [r15+28h]; hEvent
0x180016bd8  mov     r14d, 2
0x180016bde  or      dword ptr [r15+0Ch], 1
0x180016be3  mov     dword ptr [r15+24h], 1Ch
0x180016beb  call    cs:__imp_SetEvent
0x180016bf1  mov     r12d, [rbp+57h+var_B0]
0x180016bf5  and     ebx, 0FFFFFFF7h
0x180016bf8  cmp     r14d, r12d
0x180016bfb  jz      loc_180016B49
0x180016c01  mov     r13, cs:PfSvcGlobals
0x180016c08  mov     dword ptr [rbp+57h+var_A0], r12d
0x180016c0c  mov     dword ptr [rbp+57h+var_A0+4], r14d
0x180016c10  test    byte ptr [r13+1CCh], 1
0x180016c18  jnz     loc_180016DEB
0x180016c1e  lea     r13, [r15+798h]
0x180016c25  jmp     loc_180016B23
0x180016c2a  and     eax, 0FFFFFFEFh
0x180016c2d  mov     edi, r9d
0x180016c30  mov     [r15+0Ch], eax
0x180016c34  jmp     loc_180016A8B
0x180016c39  cmp     dword ptr [r13+40h], 0FFFFFFFFh
0x180016c3e  cmovg   ebx, r8d
0x180016c42  and     eax, 0FFFFFFBFh
0x180016c45  mov     [r15+0Ch], eax
0x180016c49  mov     [rbp+57h+var_B0], ebx
0x180016c4c  jmp     loc_180016A93
0x180016c51  cmp     [r15+24h], r14d
0x180016c55  jnz     short loc_180016C5F
0x180016c57  or      ebx, 10h
0x180016c5a  jmp     loc_180016B00
0x180016c5f  or      ebx, 8
0x180016c62  jmp     loc_180016B00
0x180016c67  mov     r9d, 8
0x180016c6d  lea     r8, [rbp+57h+var_A8]
0x180016c71  lea     edx, [r9+0Ah]
0x180016c75  call    PfLgpTraceEvent
0x180016c7a  jmp     loc_180016B1F
0x180016c7f  test    bl, 1
0x180016c82  jnz     short loc_180016C93
0x180016c84  test    bl, 8
0x180016c87  jnz     short loc_180016C93
0x180016c89  test    bl, 2
0x180016c8c  jz      short loc_180016CB5
0x180016c8e  test    bl, 10h
0x180016c91  jnz     short loc_180016CBE
0x180016c93  mov     edx, 4
0x180016c98  mov     rcx, r15
0x180016c9b  and     ebx, 0FFFFFFEFh
0x180016c9e  call    PfRbPrefetchControl
0x180016ca3  mov     r14d, 1
0x180016ca9  test    r14b, bl
0x180016cac  jnz     short loc_180016CB5
0x180016cae  test    eax, eax
0x180016cb0  jnz     short loc_180016CB5
0x180016cb2  or      ebx, 10h
0x180016cb5  test    bl, 10h
0x180016cb8  jz      loc_180016BF8
0x180016cbe  mov     eax, [r13+40h]
0x180016cc2  cmp     eax, 1
0x180016cc5  jle     short loc_180016D0B
0x180016cc7  lea     edi, [rax-1]
0x180016cca  or      ebx, 1
0x180016ccd  mov     edx, edi
0x180016ccf  mov     [rbp+57h+var_B0], ebx
0x180016cd2  mov     rcx, rsi
0x180016cd5  call    PfRbPrefetchSetThresholds
0x180016cda  mov     rdx, [rbp+57h+var_98]
0x180016cde  lea     r9, [rbp+57h+var_B0]
0x180016ce2  mov     r8d, edi
0x180016ce5  mov     rcx, rsi
0x180016ce8  call    PfRbPrefetchProcessMemInfo
0x180016ced  mov     edx, 4
0x180016cf2  mov     [rbp+57h+var_AC], eax
0x180016cf5  mov     rcx, r15
0x180016cf8  call    PfRbPrefetchControl
0x180016cfd  mov     ebx, [rbp+57h+var_B0]
0x180016d00  mov     r14d, 1
0x180016d06  jmp     loc_180016C01
0x180016d0b  mov     edx, 1
0x180016d10  mov     rcx, r15
0x180016d13  call    PfRbPrefetchControl
0x180016d18  mov     r14d, 3
0x180016d1e  jmp     loc_180016BF8
0x180016d23  mov     edx, edi
0x180016d25  mov     rcx, r13; void *
0x180016d28  call    PfRbCursorSetPriority
0x180016d2d  jmp     loc_180016BC0
0x180016d32  test    bl, 4
0x180016d35  jz      loc_180016B49
0x180016d3b  cmp     edi, r12d
0x180016d3e  jl      short loc_180016D4F
0x180016d40  cmp     dword ptr [r13+40h], 3
0x180016d45  jl      short loc_180016D4F
0x180016d47  mov     r8d, 1
0x180016d4d  jmp     short loc_180016D52
0x180016d4f  xor     r8d, r8d
0x180016d52  mov     edx, [rbp+57h+var_AC]
0x180016d55  mov     rcx, rsi
0x180016d58  call    PfRbPrefetchRebuildDb
0x180016d5d  test    eax, eax
0x180016d5f  jnz     loc_180016B5C
0x180016d65  mov     rax, [rbp+57h+var_98]
0x180016d69  and     ebx, 0FFFFFFEEh
0x180016d6c  movsxd  rcx, edi
0x180016d6f  mov     rax, [rax+rcx*8+68h]
0x180016d74  mov     [rsi+rcx*8+190h], rax
0x180016d7c  mov     rax, [rsi+1AA8h]
0x180016d83  mov     ecx, edi
0x180016d85  mov     dword ptr [rax+rcx*4+4], 0
0x180016d8d  mov     dword ptr [rsi+rcx*4+1B4Ch], 0
0x180016d98  jmp     loc_180016BCB
0x180016d9d  mov     edx, edi
0x180016d9f  mov     rcx, r13; void *
0x180016da2  call    PfRbCursorSetPriority
0x180016da7  test    bl, 4
0x180016daa  jz      loc_180016B49
0x180016db0  mov     [rsp+0E0h+lpThreadId], 0; lpThreadId
0x180016db9  lea     r8, PfRbPrefetchWorker; lpStartAddress
0x180016dc0  mov     r9, r15; lpParameter
0x180016dc3  mov     [rsp+0E0h+dwCreationFlags], 0; dwCreationFlags
0x180016dcb  xor     edx, edx; dwStackSize
0x180016dcd  xor     ecx, ecx; lpThreadAttributes
0x180016dcf  call    cs:__imp_CreateThread
0x180016dd5  mov     [r15], rax
0x180016dd8  test    rax, rax
0x180016ddb  jz      short loc_180016E3F
0x180016ddd  mov     r14d, 1
0x180016de3  or      ebx, r14d
0x180016de6  jmp     loc_180016C01
0x180016deb  mov     r12d, 40h ; '@'
0x180016df1  lea     rcx, [rbp+57h+EventTrace]; void *
0x180016df5  mov     r8d, r12d; Size
0x180016df8  xor     edx, edx; Val
0x180016dfa  call    memset_0
0x180016dff  mov     rcx, [r13+1C0h]; TraceHandle
0x180016e06  lea     rax, PfLgEventGuid
0x180016e0d  mov     qword ptr [rbp+57h+EventTrace.18h], rax
0x180016e11  lea     rdx, [rbp+57h+EventTrace]; EventTrace
0x180016e15  lea     rax, [rbp+57h+var_A0]
0x180016e19  mov     [rbp+57h+EventTrace.Size], r12w
0x180016e1e  mov     [rbp+57h+var_60], rax
0x180016e22  mov     dword ptr [rbp+57h+EventTrace.28h+4], 1A0000h
0x180016e29  mov     byte ptr [rbp+57h+EventTrace.4], 0Bh
0x180016e2d  mov     [rbp+57h+var_58], 8
0x180016e34  call    cs:__imp_TraceEvent
0x180016e3a  jmp     loc_180016C1E
0x180016e3f  call    cs:__imp_GetLastError
0x180016e45  jmp     loc_180016B5C
```
