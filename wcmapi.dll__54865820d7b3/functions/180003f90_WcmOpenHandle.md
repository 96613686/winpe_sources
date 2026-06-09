# WcmOpenHandle

- ea: `0x180003f90`
- end: `0x180004444`
- name: `WcmOpenHandle`
- size: `1204`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180003eb0`
- `0x180003f90`
- `0x180004450`
- `0x1800044b0`
- `0x180005790`
- `0x180008a90`
- `0x1800111dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000412a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000412a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000410b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000410b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000437d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000437d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000438e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000438e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004163`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004163`
- `RPCRT4!NdrClientCall3` at `0x180004074`
- `RPCRT4!NdrClientCall3` at `0x180004074`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180004404`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180004404`
- `RPCRT4!RpcExceptionFilter` at `0x18001ca0e`
- `RPCRT4!RpcExceptionFilter` at `0x18001ca30`
- `RPCRT4!RpcExceptionFilter` at `0x18001ca0e`
- `RPCRT4!RpcExceptionFilter` at `0x18001ca30`
- `MobileNetworking!HtNewHandle` at `0x1800041c0`
- `MobileNetworking!HtNewHandle` at `0x1800041c0`

## string_xrefs

- `0x180004281`: `ClientCreateContext`
- `0x1800042ed`: `ClientCreateContext`
- `0x18000400c`: `WcmOpenHandle`
- `0x18000424b`: `WcmOpenHandle`

## pseudocode

```c
__int64 __fastcall WcmOpenHandle(int a1, __int64 a2, _DWORD *a3, _QWORD *a4)
{
  DWORD LastError; // edi
  char *v9; // r15
  WcmPolicyManager *v10; // rcx
  unsigned int Pointer; // ebx
  char *v12; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  void *ContextHandle; // [rsp+68h] [rbp-60h] BYREF
  __int64 v20; // [rsp+70h] [rbp-58h] BYREF
  _WORD v21[2]; // [rsp+78h] [rbp-50h] BYREF
  int v22; // [rsp+7Ch] [rbp-4Ch] BYREF

  LastError = 0;
  ContextHandle = 0;
  v20 = 0;
  v22 = 0;
  v9 = 0;
  v21[0] = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids, "WcmOpenHandle");
    v10 = WPP_GLOBAL_Control;
  }
  if ( a3 && a4 && !a2 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_18001F060,
                              0,
                              0,
                              v21,
                              a1,
                              &v22,
                              &ContextHandle).Pointer;
    v10 = WPP_GLOBAL_Control;
    if ( Pointer )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids, Pointer);
        v10 = WPP_GLOBAL_Control;
      }
      if ( Pointer == 1702 || Pointer == 1717 || Pointer == 1726 || Pointer == 1753 )
        Pointer = 1062;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
          "ClientCreateContext");
      }
      v12 = 0;
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap )
      {
        v12 = (char *)HeapAlloc(ProcessHeap, 8u, 0x38u);
        if ( !v12 )
          SetLastError(0xEu);
      }
      if ( v12 )
      {
        *(_OWORD *)v12 = 0;
        *((_OWORD *)v12 + 1) = 0;
        *((_OWORD *)v12 + 2) = 0;
        *((_QWORD *)v12 + 6) = 0;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 16));
        v9 = v12;
      }
      else
      {
        LastError = GetLastError();
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
          (unsigned int)"ClientCreateContext",
          LastError);
        v10 = WPP_GLOBAL_Control;
      }
      if ( LastError )
      {
        Pointer = LastError;
        if ( v10 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) && (*((_BYTE *)v10 + 28) & 1) != 0 )
        {
          v17 = 37;
          v18 = LastError;
LABEL_48:
          WPP_SF_D(*((_QWORD *)v10 + 2), v17, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids, v18);
          goto LABEL_20;
        }
      }
      else
      {
        *(_QWORD *)v9 = ContextHandle;
        v14 = HtNewHandle(g_hHandleTable, v9, 1129074260, ClientDestroyContext, 1, &v20);
        Pointer = v14;
        if ( !v14 )
        {
          *a3 = v22;
          v15 = v20;
          *a4 = v20;
          *((_QWORD *)v9 + 1) = v15;
LABEL_20:
          v10 = WPP_GLOBAL_Control;
          goto LABEL_21;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 38;
          v18 = v14;
          goto LABEL_48;
        }
      }
    }
LABEL_21:
    if ( !Pointer )
      goto LABEL_22;
    goto LABEL_53;
  }
  Pointer = 87;
LABEL_53:
  if ( ContextHandle )
  {
    RpcCloseHandle(&ContextHandle);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    ClientDestroyContext(v9);
    v10 = WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( v10 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 5u && (*((_BYTE *)v10 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v10 + 2),
      39,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmOpenHandle",
      Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180003f90  push    rbx
0x180003f92  push    rsi
0x180003f93  push    rdi
0x180003f94  push    r12
0x180003f96  push    r13
0x180003f98  push    r14
0x180003f9a  push    r15
0x180003f9c  sub     rsp, 90h
0x180003fa3  mov     rax, cs:__security_cookie
0x180003faa  xor     rax, rsp
0x180003fad  mov     [rsp+0C8h+var_48], rax
0x180003fb5  mov     r12, r9
0x180003fb8  mov     r14, r8
0x180003fbb  mov     rbx, rdx
0x180003fbe  mov     r13d, ecx
0x180003fc1  mov     [rsp+0C8h+var_70], r8
0x180003fc6  mov     [rsp+0C8h+var_68], r9
0x180003fcb  xor     edi, edi
0x180003fcd  mov     [rsp+0C8h+ContextHandle], rdi
0x180003fd2  mov     [rsp+0C8h+var_58], rdi
0x180003fd7  mov     [rsp+0C8h+var_4C], edi
0x180003fdb  mov     r15d, edi
0x180003fde  mov     [rsp+0C8h+var_80], rdi
0x180003fe3  mov     [rsp+0C8h+var_50], di
0x180003fe8  lea     rsi, WPP_GLOBAL_Control
0x180003fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ff6  cmp     rcx, rsi
0x180003ff9  jz      short loc_18000402A
0x180003ffb  cmp     byte ptr [rcx+19h], 5
0x180003fff  jb      short loc_18000402A
0x180004001  test    byte ptr [rcx+1Ch], 1
0x180004005  jz      short loc_18000402A
0x180004007  mov     edx, 22h ; '"'
0x18000400c  lea     r9, aWcmopenhandle_0; "WcmOpenHandle"
0x180004013  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000401a  mov     rcx, [rcx+10h]
0x18000401e  call    WPP_SF_s
0x180004023  mov     rcx, cs:WPP_GLOBAL_Control
0x18000402a  test    r14, r14
0x18000402d  jz      loc_180004228
0x180004033  test    r12, r12
0x180004036  jz      loc_180004228
0x18000403c  test    rbx, rbx
0x18000403f  jnz     loc_180004228
0x180004045  mov     [rsp+0C8h+var_78], rdi
0x18000404a  lea     rax, [rsp+0C8h+ContextHandle]
0x18000404f  mov     [rsp+0C8h+var_98], rax
0x180004054  lea     rax, [rsp+0C8h+var_4C]
0x180004059  mov     [rsp+0C8h+var_A0], rax
0x18000405e  mov     [rsp+0C8h+var_A8], r13d
0x180004063  lea     r9, [rsp+0C8h+var_50]
0x180004068  xor     r8d, r8d; pReturnValue
0x18000406b  xor     edx, edx; nProcNum
0x18000406d  lea     rcx, stru_18001F060; pProxyInfo
0x180004074  call    cs:__imp_NdrClientCall3
0x18000407b  nop     dword ptr [rax+rax+00h]
0x180004080  mov     rbx, rax
0x180004083  mov     [rsp+0C8h+var_78], rax
0x180004088  mov     [rsp+0C8h+var_88], eax
0x18000408c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004093  jmp     short loc_1800040F1
0x180004095  mov     ebx, eax
0x180004097  mov     [rsp+0C8h+var_88], eax
0x18000409b  lea     rdx, WPP_GLOBAL_Control
0x1800040a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040a9  cmp     rcx, rdx
0x1800040ac  jz      short loc_1800040D9
0x1800040ae  cmp     byte ptr [rcx+19h], 1
0x1800040b2  jb      short loc_1800040D9
0x1800040b4  test    byte ptr [rcx+1Ch], 1
0x1800040b8  jz      short loc_1800040D9
0x1800040ba  mov     edx, 23h ; '#'
0x1800040bf  mov     r9d, eax
0x1800040c2  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800040c9  mov     rcx, [rcx+10h]
0x1800040cd  call    WPP_SF_D
0x1800040d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040d9  xor     edi, edi
0x1800040db  lea     rsi, WPP_GLOBAL_Control
0x1800040e2  mov     r15, [rsp+0C8h+var_80]
0x1800040e7  mov     r14, [rsp+0C8h+var_70]
0x1800040ec  mov     r12, [rsp+0C8h+var_68]
0x1800040f1  test    ebx, ebx
0x1800040f3  jnz     loc_1800042A4
0x1800040f9  cmp     rcx, rsi
0x1800040fc  jz      short loc_180004108
0x1800040fe  cmp     byte ptr [rcx+19h], 5
0x180004102  jnb     loc_1800042DE
0x180004108  mov     rbx, rdi
0x18000410b  call    cs:__imp_GetProcessHeap
0x180004112  nop     dword ptr [rax+rax+00h]
0x180004117  test    rax, rax
0x18000411a  jz      short loc_180004142
0x18000411c  mov     edx, 8; dwFlags
0x180004121  mov     r8d, 38h ; '8'; dwBytes
0x180004127  mov     rcx, rax; hHeap
0x18000412a  call    cs:__imp_HeapAlloc
0x180004131  nop     dword ptr [rax+rax+00h]
0x180004136  mov     rbx, rax
0x180004139  test    rax, rax
0x18000413c  jz      loc_180004378
0x180004142  test    rbx, rbx
0x180004145  jz      loc_18000438E
0x18000414b  xorps   xmm0, xmm0
0x18000414e  xor     eax, eax
0x180004150  movups  xmmword ptr [rbx], xmm0
0x180004153  movups  xmmword ptr [rbx+10h], xmm0
0x180004157  movups  xmmword ptr [rbx+20h], xmm0
0x18000415b  mov     [rbx+30h], rax
0x18000415f  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004163  call    cs:__imp_InitializeCriticalSection
0x18000416a  nop     dword ptr [rax+rax+00h]
0x18000416f  mov     r15, rbx
0x180004172  mov     [rsp+0C8h+var_80], rbx
0x180004177  mov     rcx, cs:WPP_GLOBAL_Control
0x18000417e  cmp     rcx, rsi
0x180004181  jnz     loc_180004264
0x180004187  test    edi, edi
0x180004189  jnz     loc_180004309
0x18000418f  mov     rax, [rsp+0C8h+ContextHandle]
0x180004194  mov     [r15], rax
0x180004197  lea     rax, [rsp+0C8h+var_58]
0x18000419c  mov     [rsp+0C8h+var_A0], rax
0x1800041a1  mov     [rsp+0C8h+var_A8], 1
0x1800041a9  lea     r9, ?ClientDestroyContext@@YAXPEAX@Z; ClientDestroyContext(void *)
0x1800041b0  mov     r8d, 434C4E54h
0x1800041b6  mov     rdx, r15
0x1800041b9  mov     rcx, cs:g_hHandleTable
0x1800041c0  call    cs:__imp_HtNewHandle
0x1800041c7  nop     dword ptr [rax+rax+00h]
0x1800041cc  mov     ebx, eax
0x1800041ce  mov     [rsp+0C8h+var_88], eax
0x1800041d2  test    eax, eax
0x1800041d4  jnz     loc_1800043BE
0x1800041da  mov     eax, [rsp+0C8h+var_4C]
0x1800041de  mov     [r14], eax
0x1800041e1  mov     rax, [rsp+0C8h+var_58]
0x1800041e6  mov     [r12], rax
0x1800041ea  mov     [r15+8], rax
0x1800041ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041f5  test    ebx, ebx
0x1800041f7  jnz     loc_1800043E4
0x1800041fd  cmp     rcx, rsi
0x180004200  jnz     short loc_180004236
0x180004202  mov     eax, ebx
0x180004204  mov     rcx, [rsp+0C8h+var_48]
0x18000420c  xor     rcx, rsp; StackCookie
0x18000420f  call    __security_check_cookie
0x180004214  add     rsp, 90h
0x18000421b  pop     r15
0x18000421d  pop     r14
0x18000421f  pop     r13
0x180004221  pop     r12
0x180004223  pop     rdi
0x180004224  pop     rsi
0x180004225  pop     rbx
0x180004226  retn
0x180004228  mov     ebx, 57h ; 'W'
0x18000422d  mov     [rsp+0C8h+var_88], ebx
0x180004231  jmp     loc_1800043E4
0x180004236  cmp     byte ptr [rcx+19h], 5
0x18000423a  jb      short loc_180004202
0x18000423c  test    byte ptr [rcx+1Ch], 1
0x180004240  jz      short loc_180004202
0x180004242  mov     edx, 27h ; '''
0x180004247  mov     [rsp+0C8h+var_A8], ebx
0x18000424b  lea     r9, aWcmopenhandle_0; "WcmOpenHandle"
0x180004252  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180004259  mov     rcx, [rcx+10h]
0x18000425d  call    WPP_SF_sL
0x180004262  jmp     short loc_180004202
0x180004264  cmp     byte ptr [rcx+19h], 5
0x180004268  jb      loc_180004187
0x18000426e  test    byte ptr [rcx+1Ch], 1
0x180004272  jz      loc_180004187
0x180004278  mov     edx, 1Fh
0x18000427d  mov     [rsp+0C8h+var_A8], edi
0x180004281  lea     r9, aClientcreateco; "ClientCreateContext"
0x180004288  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18000428f  mov     rcx, [rcx+10h]
0x180004293  call    WPP_SF_sL
0x180004298  mov     rcx, cs:WPP_GLOBAL_Control
0x18000429f  jmp     loc_180004187
0x1800042a4  cmp     rcx, rsi
0x1800042a7  jnz     loc_180004336
0x1800042ad  mov     eax, ebx
0x1800042af  sub     eax, 6A6h
0x1800042b4  jz      loc_18000436E
0x1800042ba  sub     eax, 0Fh
0x1800042bd  jz      loc_18000436E
0x1800042c3  sub     eax, 9
0x1800042c6  jz      loc_18000436E
0x1800042cc  cmp     eax, 1Bh
0x1800042cf  jz      loc_18000436E
0x1800042d5  mov     [rsp+0C8h+var_88], ebx
0x1800042d9  jmp     loc_1800041F5
0x1800042de  test    byte ptr [rcx+1Ch], 1
0x1800042e2  jz      loc_180004108
0x1800042e8  mov     edx, 1Dh
0x1800042ed  lea     r9, aClientcreateco; "ClientCreateContext"
0x1800042f4  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800042fb  mov     rcx, [rcx+10h]
0x1800042ff  call    WPP_SF_s
0x180004304  jmp     loc_180004108
0x180004309  mov     ebx, edi
0x18000430b  mov     [rsp+0C8h+var_88], ebx
0x18000430f  cmp     rcx, rsi
0x180004312  jz      loc_1800041F5
0x180004318  cmp     byte ptr [rcx+19h], 1
0x18000431c  jb      loc_1800041F5
0x180004322  test    byte ptr [rcx+1Ch], 1
0x180004326  jz      loc_1800041F5
0x18000432c  mov     edx, 25h ; '%'
0x180004331  mov     r9d, edi
0x180004334  jmp     short loc_1800043A9
0x180004336  cmp     byte ptr [rcx+19h], 1
0x18000433a  jb      loc_1800042AD
0x180004340  test    byte ptr [rcx+1Ch], 1
0x180004344  jz      loc_1800042AD
0x18000434a  mov     edx, 24h ; '$'
0x18000434f  mov     r9d, ebx
0x180004352  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180004359  mov     rcx, [rcx+10h]
0x18000435d  call    WPP_SF_D
0x180004362  mov     rcx, cs:WPP_GLOBAL_Control
0x180004369  jmp     loc_1800042AD
0x18000436e  mov     ebx, 426h
0x180004373  jmp     loc_1800042D5
0x180004378  mov     ecx, 0Eh; dwErrCode
0x18000437d  call    cs:__imp_SetLastError
0x180004384  nop     dword ptr [rax+rax+00h]
0x180004389  jmp     loc_180004142
0x18000438e  call    cs:__imp_GetLastError
0x180004395  nop     dword ptr [rax+rax+00h]
0x18000439a  mov     edi, eax
0x18000439c  jmp     loc_180004177
0x1800043a1  mov     edx, 26h ; '&'
0x1800043a6  mov     r9d, eax
0x1800043a9  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800043b0  mov     rcx, [rcx+10h]
0x1800043b4  call    WPP_SF_D
0x1800043b9  jmp     loc_1800041EE
0x1800043be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043c5  cmp     rcx, rsi
0x1800043c8  jz      loc_1800041F5
0x1800043ce  cmp     byte ptr [rcx+19h], 1
0x1800043d2  jb      loc_1800041F5
0x1800043d8  test    byte ptr [rcx+1Ch], 1
0x1800043dc  jz      loc_1800041F5
0x1800043e2  jmp     short loc_1800043A1
0x1800043e4  cmp     [rsp+0C8h+ContextHandle], 0
0x1800043ea  jz      short loc_180004427
0x1800043ec  lea     rcx, [rsp+0C8h+ContextHandle]
0x1800043f1  call    RpcCloseHandle
0x1800043f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043fd  jmp     short loc_180004427
0x1800043ff  lea     rcx, [rsp+0C8h+ContextHandle]; ContextHandle
0x180004404  call    cs:__imp_RpcSsDestroyClientContext
0x18000440b  nop     dword ptr [rax+rax+00h]
0x180004410  lea     rsi, WPP_GLOBAL_Control
0x180004417  mov     ebx, [rsp+0C8h+var_88]
0x18000441b  mov     r15, [rsp+0C8h+var_80]
0x180004420  mov     rcx, cs:WPP_GLOBAL_Control
0x180004427  test    r15, r15
0x18000442a  jz      loc_1800041FD
0x180004430  mov     rcx, r15; lpMem
0x180004433  call    ?ClientDestroyContext@@YAXPEAX@Z; ClientDestroyContext(void *)
0x180004438  mov     rcx, cs:WPP_GLOBAL_Control
0x18000443f  jmp     loc_1800041FD
0x18001ca00  push    rbp
0x18001ca02  sub     rsp, 40h
0x18001ca06  mov     rbp, rdx
0x18001ca09  mov     rcx, [rcx]
0x18001ca0c  mov     ecx, [rcx]; ExceptionCode
0x18001ca0e  call    cs:__imp_RpcExceptionFilter
0x18001ca15  nop     dword ptr [rax+rax+00h]
0x18001ca1a  nop
0x18001ca1b  add     rsp, 40h
0x18001ca1f  pop     rbp
0x18001ca20  retn
0x18001ca22  push    rbp
0x18001ca24  sub     rsp, 40h
0x18001ca28  mov     rbp, rdx
0x18001ca2b  mov     rcx, [rcx]
0x18001ca2e  mov     ecx, [rcx]; ExceptionCode
0x18001ca30  call    cs:__imp_RpcExceptionFilter
0x18001ca37  nop     dword ptr [rax+rax+00h]
0x18001ca3c  nop
0x18001ca3d  add     rsp, 40h
0x18001ca41  pop     rbp
0x18001ca42  retn
```
