# PNP_Local_InstallDevInst

- ea: `0x1800121f0`
- end: `0x180012691`
- name: `PNP_Local_InstallDevInst`
- size: `1185`
- prototype: `unsigned int __fastcall(struct _RPC_ASYNC_STATE *, void *, WCHAR *, __int64, __int64, DWORD *, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180008660`
- `0x180009420`
- `0x18000be30`
- `0x18000bf60`
- `0x18000e4e0`
- `0x18000f110`
- `0x18000fa50`
- `0x18001091c`
- `0x1800117d4`
- `0x180011964`
- `0x1800121f0`
- `0x180013d90`
- `0x180014468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001247f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001247f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800124a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800124a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012464`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001258c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001258c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180012425`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180012425`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800125fb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800125fb`
- `RPCRT4!I_RpcMapWin32Status` at `0x180012431`
- `RPCRT4!I_RpcMapWin32Status` at `0x180012431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012643`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012643`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001244a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001244a`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800124fc`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800124fc`

## pseudocode

```c
unsigned int __fastcall PNP_Local_InstallDevInst(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        WCHAR *a3,
        __int64 a4,
        __int64 a5,
        DWORD *a6,
        int a7)
{
  int v8; // ebx
  int v9; // esi
  __m128i *v10; // rcx
  __m128i v11; // xmm7
  int v12; // eax
  __int128 *v13; // r8
  __int128 v14; // xmm6
  DWORD v15; // r14d
  RPC_STATUS v16; // eax
  DWORD LastError; // eax
  int ClientTokenSessionId; // r12d
  DWORD v19; // ebx
  unsigned int result; // eax
  _QWORD *v21; // rcx
  int Reply; // [rsp+50h] [rbp-A8h] BYREF
  int v23; // [rsp+54h] [rbp-A4h]
  unsigned int Pid; // [rsp+58h] [rbp-A0h] BYREF
  DWORD pSessionId; // [rsp+5Ch] [rbp-9Ch] BYREF
  DWORD v26; // [rsp+60h] [rbp-98h]
  int v27; // [rsp+64h] [rbp-94h]
  ULONG pulStatus; // [rsp+68h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-88h] BYREF
  unsigned int v30; // [rsp+78h] [rbp-80h]
  DWORD v31; // [rsp+7Ch] [rbp-7Ch]
  ULONG pulProblemNumber[4]; // [rsp+80h] [rbp-78h] BYREF
  __m128i v33; // [rsp+90h] [rbp-68h]
  __int128 v34; // [rsp+A0h] [rbp-58h]

  Reply = 0;
  v31 = 0;
  Pid = 0;
  pSessionId = 0;
  pulStatus = 0;
  pulProblemNumber[0] = 0;
  hObject = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  if ( (PnpServiceInstallOptions & 1) == 0 )
  {
    Reply = 50;
    goto LABEL_68;
  }
  if ( !(unsigned int)IsClientLocal()
    || !(unsigned int)UserDriverInstallAllowed() && !(unsigned int)VerifyClientAccessToObject(2) )
  {
    goto LABEL_7;
  }
  if ( (a7 & 0xFFFFFC00) != 0 )
  {
    Reply = 4;
    goto LABEL_68;
  }
  v23 = 1;
  v30 = (a7 & 1) + 2;
  v8 = 1;
  if ( (a7 & 2) != 0 )
    v8 = 5;
  v23 = v8;
  if ( (a7 & 4) != 0 )
  {
    v8 |= 8u;
    v23 = v8;
  }
  if ( (a7 & 8) != 0 )
  {
    v8 |= 0x10u;
    v23 = v8;
  }
  if ( (a7 & 0x40) != 0 )
  {
    v8 |= 0x100u;
    v23 = v8;
  }
  if ( (a7 & 0x80u) != 0 )
  {
    v8 |= 0x200u;
    v23 = v8;
  }
  if ( (a7 & 0x100) != 0 )
  {
    v8 |= 0x1000u;
    v23 = v8;
  }
  if ( (a7 & 0x200) != 0 )
  {
    v8 |= 0x2000u;
    v23 = v8;
  }
  v9 = (a7 & 0x10) != 0;
  v27 = v9;
  if ( *(_DWORD *)a4 > 1u )
    goto LABEL_27;
  v10 = *(__m128i **)(a4 + 8);
  if ( !v10 )
  {
LABEL_29:
    Reply = 31;
    goto LABEL_68;
  }
  v11 = 0;
  if ( *(_DWORD *)a4 == 1 )
  {
    v11 = *v10;
    v33 = *v10;
    v12 = Reply;
  }
  else
  {
    v12 = 59;
    Reply = 59;
  }
  if ( !v12 )
  {
    if ( *(_DWORD *)a5 > 1u )
    {
LABEL_27:
      Reply = 52;
      goto LABEL_68;
    }
    v13 = *(__int128 **)(a5 + 8);
    if ( !v13 )
      goto LABEL_29;
    *(_QWORD *)&v14 = 0;
    if ( *(_DWORD *)a5 == 1 )
    {
      v14 = *v13;
      v34 = *v13;
    }
    else
    {
      v12 = 59;
      Reply = 59;
    }
    if ( !v12 )
    {
      if ( !(unsigned int)GetClientUserToken(&hObject) )
        goto LABEL_7;
      v15 = 0;
      v26 = 0;
      Pid = 0;
      v16 = I_RpcBindingInqLocalClientPID(a2, &Pid);
      if ( v16 )
      {
        LastError = I_RpcMapWin32Status(v16);
      }
      else
      {
        pSessionId = -1;
        if ( ProcessIdToSessionId(Pid, &pSessionId) )
          goto LABEL_46;
        LastError = GetLastError();
      }
      v26 = LastError;
      v15 = LastError;
LABEL_46:
      SetLastError(v15);
      if ( !v15 )
      {
        if ( (v9 & 1) != 0 )
          goto LABEL_55;
        EnterCriticalSection(&PnpInstallProcessLock);
        if ( (unsigned int)IsNestedProcess(Pid) )
        {
          v9 |= 3u;
          v27 = v9;
        }
        LeaveCriticalSection(&PnpInstallProcessLock);
        if ( (v9 & 2) != 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
        }
        if ( (v9 & 1) != 0 )
        {
LABEL_55:
          v8 &= ~0x10u;
          v23 = v8;
        }
        ClientTokenSessionId = GetClientTokenSessionId();
        if ( ClientTokenSessionId == (unsigned int)WTSGetServiceSessionId() )
        {
          v8 &= ~0x10u;
          v23 = v8;
          ClientTokenSessionId = GetDeviceSessionId(a3);
        }
        if ( ClientTokenSessionId == -1 )
        {
          v8 &= ~0x10u;
          v23 = v8;
          ClientTokenSessionId = -2;
        }
        *a6 = 0;
        if ( (unsigned int)QueueDeviceInstallEntry(
                             v30,
                             hObject,
                             a3,
                             v11.m128i_i64[0],
                             _mm_srli_si128(v11, 8).m128i_u64[0],
                             v14,
                             ClientTokenSessionId,
                             Pid,
                             v8,
                             v9) )
          v19 = v31;
        else
          v19 = GetLastError();
        if ( !v19 && !(unsigned int)GetDeviceStatus(a3, &pulStatus, pulProblemNumber) && (pulStatus & 0x100) != 0 )
          Reply = 34;
        *a6 = v19;
        goto LABEL_68;
      }
LABEL_7:
      Reply = 51;
    }
  }
LABEL_68:
  result = RpcAsyncCompleteCall(a1, &Reply);
  if ( !result )
  {
LABEL_72:
    v21 = WPP_GLOBAL_Control;
    goto LABEL_73;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, result);
    goto LABEL_72;
  }
LABEL_73:
  if ( hObject )
  {
    result = CloseHandle(hObject);
    v21 = WPP_GLOBAL_Control;
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x10000000) != 0 )
    return WPP_SF_(v21[2], 19, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800121f0  mov     rax, rsp
0x1800121f3  mov     [rax+18h], r8
0x1800121f7  mov     [rax+10h], rdx
0x1800121fb  mov     [rax+8], rcx
0x1800121ff  push    rbx
0x180012200  push    rsi
0x180012201  push    r12
0x180012203  push    r14
0x180012205  push    r15
0x180012207  sub     rsp, 0D0h
0x18001220e  movaps  xmmword ptr [rax-38h], xmm6
0x180012212  movaps  xmmword ptr [rax-48h], xmm7
0x180012216  mov     r14, r9
0x180012219  mov     [rsp+0F8h+Reply], 0
0x180012221  mov     dword ptr [rax-7Ch], 0
0x180012228  mov     [rsp+0F8h+Pid], 0
0x180012230  mov     [rsp+0F8h+pSessionId], 0
0x180012238  mov     [rsp+0F8h+pulStatus], 0
0x180012240  mov     dword ptr [rax-78h], 0
0x180012247  mov     [rsp+0F8h+hObject], 0
0x180012250  lea     r12, WPP_GLOBAL_Control
0x180012257  mov     rcx, cs:WPP_GLOBAL_Control
0x18001225e  cmp     rcx, r12
0x180012261  jz      short loc_180012282
0x180012263  test    dword ptr [rcx+1Ch], 10000000h
0x18001226a  jz      short loc_180012282
0x18001226c  mov     edx, 10h
0x180012271  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012278  mov     rcx, [rcx+10h]
0x18001227c  call    WPP_SF_
0x180012281  nop
0x180012282  mov     r15d, 1
0x180012288  test    byte ptr cs:PnpServiceInstallOptions, r15b
0x18001228f  jnz     short loc_18001229E
0x180012291  mov     [rsp+0F8h+Reply], 32h ; '2'
0x180012299  jmp     loc_1800125D3
0x18001229e  call    IsClientLocal
0x1800122a3  test    eax, eax
0x1800122a5  jnz     short loc_1800122B4
0x1800122a7  mov     [rsp+0F8h+Reply], 33h ; '3'
0x1800122af  jmp     loc_1800125D3
0x1800122b4  call    UserDriverInstallAllowed
0x1800122b9  test    eax, eax
0x1800122bb  jnz     short loc_1800122C9
0x1800122bd  lea     ecx, [rax+2]
0x1800122c0  call    VerifyClientAccessToObject
0x1800122c5  test    eax, eax
0x1800122c7  jz      short loc_1800122A7
0x1800122c9  mov     ecx, [rsp+0F8h+arg_30]
0x1800122d0  test    ecx, 0FFFFFC00h
0x1800122d6  jz      short loc_1800122E5
0x1800122d8  mov     [rsp+0F8h+Reply], 4
0x1800122e0  jmp     loc_1800125D3
0x1800122e5  mov     [rsp+0F8h+var_A4], r15d
0x1800122ea  mov     eax, ecx
0x1800122ec  and     eax, r15d
0x1800122ef  add     eax, 2
0x1800122f2  mov     [rsp+0F8h+var_80], eax
0x1800122f6  test    cl, 2
0x1800122f9  mov     ebx, r15d
0x1800122fc  mov     eax, 5
0x180012301  cmovnz  ebx, eax
0x180012304  mov     [rsp+0F8h+var_A4], ebx
0x180012308  test    cl, 4
0x18001230b  jz      short loc_180012314
0x18001230d  or      ebx, 8
0x180012310  mov     [rsp+0F8h+var_A4], ebx
0x180012314  test    cl, 8
0x180012317  jz      short loc_180012320
0x180012319  or      ebx, 10h
0x18001231c  mov     [rsp+0F8h+var_A4], ebx
0x180012320  test    cl, 40h
0x180012323  jz      short loc_18001232D
0x180012325  bts     ebx, 8
0x180012329  mov     [rsp+0F8h+var_A4], ebx
0x18001232d  test    cl, cl
0x18001232f  jns     short loc_180012339
0x180012331  bts     ebx, 9
0x180012335  mov     [rsp+0F8h+var_A4], ebx
0x180012339  bt      ecx, 8
0x18001233d  jnb     short loc_180012347
0x18001233f  bts     ebx, 0Ch
0x180012343  mov     [rsp+0F8h+var_A4], ebx
0x180012347  bt      ecx, 9
0x18001234b  jnb     short loc_180012355
0x18001234d  bts     ebx, 0Dh
0x180012351  mov     [rsp+0F8h+var_A4], ebx
0x180012355  test    cl, 10h
0x180012358  mov     esi, 0
0x18001235d  cmovnz  esi, r15d
0x180012361  mov     [rsp+0F8h+var_94], esi
0x180012365  mov     eax, [r14]
0x180012368  cmp     eax, r15d
0x18001236b  jbe     short loc_18001237A
0x18001236d  mov     [rsp+0F8h+Reply], 34h ; '4'
0x180012375  jmp     loc_1800125D3
0x18001237a  mov     rcx, [r14+8]
0x18001237e  test    rcx, rcx
0x180012381  jnz     short loc_180012390
0x180012383  mov     [rsp+0F8h+Reply], 1Fh
0x18001238b  jmp     loc_1800125D3
0x180012390  xorps   xmm7, xmm7
0x180012393  cmp     eax, r15d
0x180012396  jz      short loc_1800123A3
0x180012398  mov     eax, 3Bh ; ';'
0x18001239d  mov     [rsp+0F8h+Reply], eax
0x1800123a1  jmp     short loc_1800123B2
0x1800123a3  movups  xmm7, xmmword ptr [rcx]
0x1800123a6  movups  [rsp+0F8h+var_68], xmm7
0x1800123ae  mov     eax, [rsp+0F8h+Reply]
0x1800123b2  test    eax, eax
0x1800123b4  jnz     loc_1800125D3
0x1800123ba  mov     rdx, [rsp+0F8h+arg_20]
0x1800123c2  mov     ecx, [rdx]
0x1800123c4  cmp     ecx, r15d
0x1800123c7  ja      short loc_18001236D
0x1800123c9  mov     r8, [rdx+8]
0x1800123cd  test    r8, r8
0x1800123d0  jz      short loc_180012383
0x1800123d2  xorps   xmm6, xmm6
0x1800123d5  cmp     ecx, r15d
0x1800123d8  jz      short loc_1800123E5
0x1800123da  mov     eax, 3Bh ; ';'
0x1800123df  mov     [rsp+0F8h+Reply], eax
0x1800123e3  jmp     short loc_1800123F1
0x1800123e5  movups  xmm6, xmmword ptr [r8]
0x1800123e9  movups  [rsp+0F8h+var_58], xmm6
0x1800123f1  test    eax, eax
0x1800123f3  jnz     loc_1800125D3
0x1800123f9  lea     rcx, [rsp+0F8h+hObject]
0x1800123fe  call    GetClientUserToken
0x180012403  test    eax, eax
0x180012405  jz      loc_1800122A7
0x18001240b  xor     r14d, r14d
0x18001240e  mov     [rsp+0F8h+var_98], r14d
0x180012413  mov     [rsp+0F8h+Pid], r14d
0x180012418  lea     rdx, [rsp+0F8h+Pid]; Pid
0x18001241d  mov     rcx, [rsp+0F8h+Binding]; Binding
0x180012425  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001242b  test    eax, eax
0x18001242d  jz      short loc_180012439
0x18001242f  mov     ecx, eax; Status
0x180012431  call    cs:__imp_I_RpcMapWin32Status
0x180012437  jmp     short loc_18001245A
0x180012439  mov     [rsp+0F8h+pSessionId], 0FFFFFFFFh
0x180012441  lea     rdx, [rsp+0F8h+pSessionId]; pSessionId
0x180012446  mov     ecx, [rsp+0F8h+Pid]; dwProcessId
0x18001244a  call    cs:__imp_ProcessIdToSessionId
0x180012450  test    eax, eax
0x180012452  jnz     short loc_180012461
0x180012454  call    cs:__imp_GetLastError
0x18001245a  mov     [rsp+0F8h+var_98], eax
0x18001245e  mov     r14d, eax
0x180012461  mov     ecx, r14d; dwErrCode
0x180012464  call    cs:__imp_SetLastError
0x18001246a  test    r14d, r14d
0x18001246d  jnz     loc_1800122A7
0x180012473  test    r15b, sil
0x180012476  jnz     short loc_1800124DF
0x180012478  lea     rcx, PnpInstallProcessLock; lpCriticalSection
0x18001247f  call    cs:__imp_EnterCriticalSection
0x180012485  mov     ecx, [rsp+0F8h+Pid]
0x180012489  call    IsNestedProcess
0x18001248e  test    eax, eax
0x180012490  jz      short loc_1800124A0
0x180012492  or      esi, r15d
0x180012495  mov     [rsp+0F8h+var_94], esi
0x180012499  or      esi, 2
0x18001249c  mov     [rsp+0F8h+var_94], esi
0x1800124a0  lea     rcx, PnpInstallProcessLock; lpCriticalSection
0x1800124a7  call    cs:__imp_LeaveCriticalSection
0x1800124ad  test    sil, 2
0x1800124b1  jz      short loc_1800124DA
0x1800124b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124ba  cmp     rcx, r12
0x1800124bd  jz      short loc_1800124DA
0x1800124bf  test    [rcx+1Ch], r15b
0x1800124c3  jz      short loc_1800124DA
0x1800124c5  mov     edx, 11h
0x1800124ca  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x1800124d1  mov     rcx, [rcx+10h]
0x1800124d5  call    WPP_SF_
0x1800124da  test    r15b, sil
0x1800124dd  jz      short loc_1800124EE
0x1800124df  mov     r14d, 0FFFFFFEFh
0x1800124e5  and     ebx, r14d
0x1800124e8  mov     [rsp+0F8h+var_A4], ebx
0x1800124ec  jmp     short loc_1800124F4
0x1800124ee  mov     r14d, 0FFFFFFEFh
0x1800124f4  call    GetClientTokenSessionId
0x1800124f9  mov     r12d, eax
0x1800124fc  call    cs:__imp_WTSGetServiceSessionId
0x180012502  cmp     r12d, eax
0x180012505  jnz     short loc_18001251E
0x180012507  and     ebx, r14d
0x18001250a  mov     [rsp+0F8h+var_A4], ebx
0x18001250e  mov     rcx, [rsp+0F8h+pDeviceID]
0x180012516  call    GetDeviceSessionId
0x18001251b  mov     r12d, eax
0x18001251e  cmp     r12d, 0FFFFFFFFh
0x180012522  jnz     short loc_180012531
0x180012524  and     ebx, r14d
0x180012527  mov     [rsp+0F8h+var_A4], ebx
0x18001252b  mov     r12d, 0FFFFFFFEh
0x180012531  mov     r14, [rsp+0F8h+arg_28]
0x180012539  mov     dword ptr [r14], 0
0x180012540  mov     [rsp+0F8h+var_B0], esi
0x180012544  mov     [rsp+0F8h+var_B8], ebx
0x180012548  mov     eax, [rsp+0F8h+Pid]
0x18001254c  mov     [rsp+0F8h+var_C0], eax
0x180012550  mov     [rsp+0F8h+var_C8], r12d
0x180012555  movsd   [rsp+0F8h+var_D0], xmm6
0x18001255b  movdqa  xmm0, xmm7
0x18001255f  psrldq  xmm0, 8
0x180012564  movq    [rsp+0F8h+var_D8], xmm0
0x18001256a  movq    r9, xmm7
0x18001256f  mov     rsi, [rsp+0F8h+pDeviceID]
0x180012577  mov     r8, rsi
0x18001257a  mov     rdx, [rsp+0F8h+hObject]
0x18001257f  mov     ecx, [rsp+0F8h+var_80]
0x180012583  call    QueueDeviceInstallEntry
0x180012588  test    eax, eax
0x18001258a  jnz     short loc_180012596
0x18001258c  call    cs:__imp_GetLastError
0x180012592  mov     ebx, eax
0x180012594  jmp     short loc_18001259A
0x180012596  mov     ebx, [rsp+0F8h+var_7C]
0x18001259a  test    ebx, ebx
0x18001259c  jnz     short loc_1800125C9
0x18001259e  lea     r8, [rsp+0F8h+pulProblemNumber]; pulProblemNumber
0x1800125a6  lea     rdx, [rsp+0F8h+pulStatus]; pulStatus
0x1800125ab  mov     rcx, rsi; pDeviceID
0x1800125ae  call    GetDeviceStatus
0x1800125b3  test    eax, eax
0x1800125b5  jnz     short loc_1800125C9
0x1800125b7  test    [rsp+0F8h+pulStatus], 100h
0x1800125bf  jz      short loc_1800125C9
0x1800125c1  mov     [rsp+0F8h+Reply], 22h ; '"'
0x1800125c9  mov     [r14], ebx
0x1800125cc  lea     r12, WPP_GLOBAL_Control
0x1800125d3  jmp     short loc_1800125EE
0x1800125d5  mov     ecx, eax
0x1800125d7  lea     r8, [rsp+0F8h+Reply]
0x1800125dc  call    PnPExceptionHandler
0x1800125e1  lea     r12, WPP_GLOBAL_Control
0x1800125e8  mov     r15d, 1
0x1800125ee  lea     rdx, [rsp+0F8h+Reply]; Reply
0x1800125f3  mov     rcx, [rsp+0F8h+pAsync]; pAsync
0x1800125fb  call    cs:__imp_RpcAsyncCompleteCall
0x180012601  test    eax, eax
0x180012603  jz      short loc_18001262F
0x180012605  mov     rcx, cs:WPP_GLOBAL_Control
0x18001260c  cmp     rcx, r12
0x18001260f  jz      short loc_180012636
0x180012611  test    [rcx+1Ch], r15b
0x180012615  jz      short loc_180012636
0x180012617  mov     edx, 12h
0x18001261c  mov     r9d, eax
0x18001261f  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012626  mov     rcx, [rcx+10h]
0x18001262a  call    WPP_SF_d
0x18001262f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012636  cmp     [rsp+0F8h+hObject], 0
0x18001263c  jz      short loc_180012650
0x18001263e  mov     rcx, [rsp+0F8h+hObject]; hObject
0x180012643  call    cs:__imp_CloseHandle
0x180012649  mov     rcx, cs:WPP_GLOBAL_Control
0x180012650  cmp     rcx, r12
0x180012653  jz      short loc_180012673
0x180012655  test    dword ptr [rcx+1Ch], 10000000h
0x18001265c  jz      short loc_180012673
0x18001265e  mov     edx, 13h
0x180012663  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18001266a  mov     rcx, [rcx+10h]
0x18001266e  call    WPP_SF_
0x180012673  lea     r11, [rsp+0F8h+var_28]
0x18001267b  movaps  xmm6, xmmword ptr [r11-10h]
0x180012680  movaps  xmm7, xmmword ptr [r11-20h]
0x180012685  mov     rsp, r11
0x180012688  pop     r15
0x18001268a  pop     r14
0x18001268c  pop     r12
0x18001268e  pop     rsi
0x18001268f  pop     rbx
0x180012690  retn
0x1800191cf  push    rbp
0x1800191d1  sub     rsp, 50h
0x1800191d5  mov     rbp, rdx
0x1800191d8  mov     eax, 1
0x1800191dd  add     rsp, 50h
0x1800191e1  pop     rbp
0x1800191e2  retn
```
