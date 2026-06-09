# wfdClientCreateContext(_WFD_CLIENT_CONTEXT * *)

- ea: `0x180003c7c`
- end: `0x180003f30`
- name: `?wfdClientCreateContext@@YAKPEAPEAU_WFD_CLIENT_CONTEXT@@@Z`
- size: `692`
- prototype: `unsigned int __fastcall(struct _WFD_CLIENT_CONTEXT **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800038fc`
- `0x180053cf8`

## callees

- `0x180003c7c`
- `0x1800053c0`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x18001a5bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180003d01`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180003d01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f0b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003d1e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180003d72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180003d72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180003efa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180003efa`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180003ce7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180003ce7`

## pseudocode

```c
__int64 __fastcall wfdClientCreateContext(struct _WFD_CLIENT_CONTEXT **a1)
{
  union DOT11_OUI_HEADER *v2; // rcx
  char *v3; // rax
  char *v4; // rbx
  int v5; // ebp
  DWORD v6; // eax
  DWORD v7; // edi
  HANDLE EventA; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  union DOT11_OUI_HEADER *v11; // rcx
  __int64 v12; // rdx
  DWORD LastError; // eax
  struct _TP_CLEANUP_GROUP *v14; // rcx
  void *v15; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 34, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v3 = (char *)AllocWLMem(0x138u);
    v4 = v3;
    if ( !v3 )
    {
      LastError = GetLastError();
      v7 = LastError;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
        return v7;
      if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
        goto LABEL_10;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, LastError);
      goto LABEL_9;
    }
    v5 = 0;
    memset_0(v3, 0, 0x138u);
    v6 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v4 + 40), 0x70u);
    v7 = v6;
    if ( v6 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
      {
        goto LABEL_35;
      }
      v12 = 37;
    }
    else
    {
      EventA = CreateEventA(0, 0, 0, 0);
      *((_QWORD *)v4 + 26) = EventA;
      if ( EventA )
      {
        InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 168));
        *((_DWORD *)v4 + 58) = 3;
        *((_QWORD *)v4 + 30) = 0;
        *((_QWORD *)v4 + 31) = 0;
        *((_QWORD *)v4 + 32) = 0;
        *((_QWORD *)v4 + 33) = 0;
        *((_QWORD *)v4 + 34) = 0;
        *((_QWORD *)v4 + 35) = 0;
        *((_DWORD *)v4 + 72) = 0;
        *((_DWORD *)v4 + 73) = 1;
        *((_DWORD *)v4 + 74) = 72;
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
        *((_QWORD *)v4 + 38) = ThreadpoolCleanupGroup;
        if ( ThreadpoolCleanupGroup )
        {
          *((_QWORD *)v4 + 31) = ThreadpoolCleanupGroup;
          *((_QWORD *)v4 + 32) = 0;
          *a1 = (struct _WFD_CLIENT_CONTEXT *)v4;
LABEL_9:
          v2 = WPP_GLOBAL_Control;
          goto LABEL_10;
        }
        v5 = 1;
        v7 = GetLastError();
LABEL_35:
        v14 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)v4 + 38);
        if ( v14 )
          CloseThreadpoolCleanupGroup(v14);
        if ( v5 )
          DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 168));
        v15 = (void *)*((_QWORD *)v4 + 26);
        if ( v15 )
          CloseHandle(v15);
        FreeWLMem(v4);
        goto LABEL_9;
      }
      v6 = GetLastError();
      v7 = v6;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
      {
        goto LABEL_35;
      }
      v12 = 38;
    }
    WPP_SF_d(*((_QWORD *)v11 + 12), v12, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v6);
    goto LABEL_35;
  }
  v7 = 87;
  if ( v2 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return v7;
  if ( *((_BYTE *)v2 + 105) && (*((_DWORD *)v2 + 27) & 0x1000) != 0 )
  {
    WPP_SF_(*((_QWORD *)v2 + 12), 35, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    goto LABEL_9;
  }
LABEL_10:
  if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v2 + 105) >= 4u
    && (*((_BYTE *)v2 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v2 + 12), 39, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180003c7c  push    rbx
0x180003c7e  push    rbp
0x180003c7f  push    rsi
0x180003c80  push    rdi
0x180003c81  push    r12
0x180003c83  push    r15
0x180003c85  sub     rsp, 28h
0x180003c89  mov     rsi, rcx
0x180003c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c93  lea     r15, WPP_GLOBAL_Control
0x180003c9a  lea     r12, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003ca1  cmp     rcx, r15
0x180003ca4  jz      short loc_180003CB0
0x180003ca6  cmp     byte ptr [rcx+69h], 4
0x180003caa  jnb     loc_180003E46
0x180003cb0  test    rsi, rsi
0x180003cb3  jz      loc_180003DE5
0x180003cb9  mov     edi, 138h
0x180003cbe  mov     ecx, edi; dwBytes
0x180003cc0  call    AllocWLMem
0x180003cc5  mov     rbx, rax
0x180003cc8  test    rax, rax
0x180003ccb  jz      loc_180003E6D
0x180003cd1  mov     r8d, edi; Size
0x180003cd4  xor     edx, edx; Val
0x180003cd6  mov     rcx, rax; void *
0x180003cd9  xor     ebp, ebp
0x180003cdb  call    memset_0
0x180003ce0  lea     rcx, [rbx+28h]; pAsync
0x180003ce4  lea     edx, [rbp+70h]; Size
0x180003ce7  call    cs:__imp_RpcAsyncInitializeHandle
0x180003ced  mov     edi, eax
0x180003cef  test    eax, eax
0x180003cf1  jnz     loc_180003DB4
0x180003cf7  xor     r9d, r9d; lpName
0x180003cfa  xor     r8d, r8d; bInitialState
0x180003cfd  xor     edx, edx; bManualReset
0x180003cff  xor     ecx, ecx; lpEventAttributes
0x180003d01  call    cs:__imp_CreateEventA
0x180003d07  mov     [rbx+0D0h], rax
0x180003d0e  test    rax, rax
0x180003d11  jz      loc_180003ECB
0x180003d17  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180003d1e  call    cs:__imp_InitializeCriticalSection
0x180003d24  mov     dword ptr [rbx+0E8h], 3
0x180003d2e  mov     [rbx+0F0h], rbp
0x180003d35  mov     [rbx+0F8h], rbp
0x180003d3c  mov     [rbx+100h], rbp
0x180003d43  mov     [rbx+108h], rbp
0x180003d4a  mov     [rbx+110h], rbp
0x180003d51  mov     [rbx+118h], rbp
0x180003d58  mov     [rbx+120h], ebp
0x180003d5e  mov     dword ptr [rbx+124h], 1
0x180003d68  mov     dword ptr [rbx+128h], 48h ; 'H'
0x180003d72  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180003d78  mov     [rbx+130h], rax
0x180003d7f  test    rax, rax
0x180003d82  jz      loc_180003E34
0x180003d88  mov     [rbx+0F8h], rax
0x180003d8f  mov     [rbx+100h], rbp
0x180003d96  mov     [rsi], rbx
0x180003d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180003da0  cmp     rcx, r15
0x180003da3  jnz     short loc_180003E0F
0x180003da5  mov     eax, edi
0x180003da7  add     rsp, 28h
0x180003dab  pop     r15
0x180003dad  pop     r12
0x180003daf  pop     rdi
0x180003db0  pop     rsi
0x180003db1  pop     rbp
0x180003db2  pop     rbx
0x180003db3  retn
0x180003db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dbb  cmp     rcx, r15
0x180003dbe  jz      loc_180003EEE
0x180003dc4  cmp     byte ptr [rcx+69h], 1
0x180003dc8  jb      loc_180003EEE
0x180003dce  test    dword ptr [rcx+6Ch], 1000h
0x180003dd5  jz      loc_180003EEE
0x180003ddb  mov     edx, 25h ; '%'
0x180003de0  jmp     loc_180003EBA
0x180003de5  mov     edi, 57h ; 'W'
0x180003dea  cmp     rcx, r15
0x180003ded  jz      short loc_180003DA5
0x180003def  cmp     byte ptr [rcx+69h], 1
0x180003df3  jb      short loc_180003DA0
0x180003df5  test    dword ptr [rcx+6Ch], 1000h
0x180003dfc  jz      short loc_180003DA0
0x180003dfe  mov     rcx, [rcx+60h]
0x180003e02  lea     edx, [rdi-34h]
0x180003e05  mov     r8, r12
0x180003e08  call    WPP_SF_
0x180003e0d  jmp     short loc_180003D99
0x180003e0f  cmp     byte ptr [rcx+69h], 4
0x180003e13  jb      short loc_180003DA5
0x180003e15  test    byte ptr [rcx+6Ch], 2
0x180003e19  jz      short loc_180003DA5
0x180003e1b  mov     rcx, [rcx+60h]
0x180003e1f  mov     edx, 27h ; '''
0x180003e24  mov     r9d, edi
0x180003e27  mov     r8, r12
0x180003e2a  call    WPP_SF_d
0x180003e2f  jmp     loc_180003DA5
0x180003e34  mov     ebp, 1
0x180003e39  call    cs:__imp_GetLastError
0x180003e3f  mov     edi, eax
0x180003e41  jmp     loc_180003EEE
0x180003e46  test    byte ptr [rcx+6Ch], 2
0x180003e4a  jz      loc_180003CB0
0x180003e50  mov     rcx, [rcx+60h]
0x180003e54  mov     edx, 22h ; '"'
0x180003e59  mov     r8, r12
0x180003e5c  call    WPP_SF_
0x180003e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e68  jmp     loc_180003CB0
0x180003e6d  call    cs:__imp_GetLastError
0x180003e73  mov     edi, eax
0x180003e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e7c  cmp     rcx, r15
0x180003e7f  jz      loc_180003DA5
0x180003e85  cmp     byte ptr [rcx+69h], 1
0x180003e89  jb      loc_180003DA0
0x180003e8f  test    dword ptr [rcx+6Ch], 1000h
0x180003e96  jz      loc_180003DA0
0x180003e9c  mov     rcx, [rcx+60h]
0x180003ea0  mov     edx, 24h ; '$'
0x180003ea5  mov     r9d, eax
0x180003ea8  mov     r8, r12
0x180003eab  call    WPP_SF_d
0x180003eb0  jmp     loc_180003D99
0x180003eb5  mov     edx, 26h ; '&'
0x180003eba  mov     rcx, [rcx+60h]
0x180003ebe  mov     r9d, eax
0x180003ec1  mov     r8, r12
0x180003ec4  call    WPP_SF_d
0x180003ec9  jmp     short loc_180003EEE
0x180003ecb  call    cs:__imp_GetLastError
0x180003ed1  mov     edi, eax
0x180003ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eda  cmp     rcx, r15
0x180003edd  jz      short loc_180003EEE
0x180003edf  cmp     byte ptr [rcx+69h], 1
0x180003ee3  jb      short loc_180003EEE
0x180003ee5  test    dword ptr [rcx+6Ch], 1000h
0x180003eec  jnz     short loc_180003EB5
0x180003eee  mov     rcx, [rbx+130h]; ptpcg
0x180003ef5  test    rcx, rcx
0x180003ef8  jz      short loc_180003F00
0x180003efa  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180003f00  test    ebp, ebp
0x180003f02  jz      short loc_180003F11
0x180003f04  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180003f0b  call    cs:__imp_DeleteCriticalSection
0x180003f11  mov     rcx, [rbx+0D0h]; hObject
0x180003f18  test    rcx, rcx
0x180003f1b  jz      short loc_180003F23
0x180003f1d  call    cs:__imp_CloseHandle
0x180003f23  mov     rcx, rbx
0x180003f26  call    FreeWLMem
0x180003f2b  jmp     loc_180003D99
```
