# ShutdownWindowsWrapper(_WLSM_GLOBAL_CONTEXT *,ulong)

- ea: `0x140032e54`
- end: `0x1400332b2`
- name: `?ShutdownWindowsWrapper@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@K@Z`
- size: `1118`
- prototype: `unsigned int(struct _WLSM_GLOBAL_CONTEXT *, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14004c400`
- `0x140065950`
- `0x140084e20`
- `0x1400872a8`

## callees

- `0x1400057f4`
- `0x140032e54`
- `0x140041c34`
- `0x14004df08`
- `0x140053720`
- `0x14005ec90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140032f8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003312d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140032f8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003312d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140033059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400331f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140033059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400331f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003304b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003311b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400331e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003304b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003311b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400331e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003306d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003306d`
- `ntdll!EtwEventEnabled` at `0x140032e9c`
- `ntdll!EtwEventEnabled` at `0x140033256`
- `ntdll!EtwEventEnabled` at `0x140032e9c`
- `ntdll!EtwEventEnabled` at `0x140033256`
- `ntdll!EtwEventWrite` at `0x140032ecb`
- `ntdll!EtwEventWrite` at `0x140033285`
- `ntdll!EtwEventWrite` at `0x140032ecb`
- `ntdll!EtwEventWrite` at `0x140033285`
- `ntdll!NtPowerInformation` at `0x140033011`
- `ntdll!NtPowerInformation` at `0x1400331af`
- `ntdll!NtPowerInformation` at `0x140033011`
- `ntdll!NtPowerInformation` at `0x1400331af`
- `ntdll!RtlGetActiveConsoleId` at `0x140032f2f`
- `ntdll!RtlGetActiveConsoleId` at `0x1400330d0`
- `ntdll!RtlGetActiveConsoleId` at `0x140032f2f`
- `ntdll!RtlGetActiveConsoleId` at `0x1400330d0`
- `ext-ms-win-ntuser-misc-l1-1-0!ExitWindowsEx` at `0x140033063`
- `ext-ms-win-ntuser-misc-l1-1-0!ExitWindowsEx` at `0x140033063`

## pseudocode

```c
__int64 __fastcall ShutdownWindowsWrapper(struct _WLSM_GLOBAL_CONTEXT *a1, UINT a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  int v6; // ebx
  CUser *v7; // rcx
  __int64 v8; // rdx
  HANDLE ProcessHeap; // rax
  char *v10; // rax
  void *v11; // rbx
  NTSTATUS v12; // eax
  HANDLE v13; // rax
  CUser *v14; // rcx
  __int64 v15; // rbx
  int v16; // ebx
  CUser *v17; // rcx
  __int64 v18; // rdx
  HANDLE v19; // rax
  char *v20; // rax
  void *v21; // rbx
  NTSTATUS v22; // eax
  HANDLE v23; // rax
  unsigned __int16 v24; // ax
  _DWORD v26[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 InputBuffer; // [rsp+38h] [rbp-28h] BYREF
  __int128 v28; // [rsp+48h] [rbp-18h]

  LastError = 0;
  v26[0] = a2;
  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_ShutdownWindows_Start) )
  {
    *(_QWORD *)&InputBuffer = v26;
    *((_QWORD *)&InputBuffer + 1) = 4;
    EtwEventWrite(g_TraceRegHandle, WLEvt_ShutdownWindows_Start, 1, &InputBuffer);
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, a2);
  }
  InputBuffer = 0;
  v28 = 0;
  if ( a1 )
  {
    v5 = *((_QWORD *)a1 + 2);
    if ( v5 )
    {
      v6 = *(_DWORD *)(v5 + 88);
      if ( (unsigned int)((__int64 (*)(void))RtlGetActiveConsoleId)() == v6 )
      {
        ProcessHeap = GetProcessHeap();
        v10 = (char *)HeapAlloc(ProcessHeap, 8u, 0x2Au);
        v11 = v10;
        if ( v10 )
        {
          *(_DWORD *)v10 = 1;
          *((_DWORD *)v10 + 2) = 1;
          *((_DWORD *)v10 + 1) = 42;
          *(_OWORD *)(v10 + 12) = *(_OWORD *)L"ExitWindowsEx";
          *(_OWORD *)(v10 + 22) = *(_OWORD *)L"indowsEx";
          *((_WORD *)v10 + 19) = 0;
          *((_QWORD *)&InputBuffer + 1) = 42;
          DWORD2(v28) = 17;
          *(_QWORD *)&InputBuffer = v10;
          v12 = NtPowerInformation(TraceApplicationPowerMessage|0x40, &InputBuffer, 0x20u, 0, 0);
          if ( v12 < 0
            && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              153,
              WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
              (unsigned int)v12);
          }
          v13 = GetProcessHeap();
          HeapFree(v13, 0, v11);
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 152;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v8 = 151;
LABEL_15:
          WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
        }
      }
    }
  }
  if ( !ExitWindowsEx(a2, 0) )
  {
    LastError = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, a2);
    }
  }
  InputBuffer = 0;
  v28 = 0;
  if ( a1 )
  {
    v15 = *((_QWORD *)a1 + 2);
    if ( v15 )
    {
      v16 = *(_DWORD *)(v15 + 88);
      if ( (unsigned int)RtlGetActiveConsoleId(v14) == v16 )
      {
        v19 = GetProcessHeap();
        v20 = (char *)HeapAlloc(v19, 8u, 0x2Au);
        v21 = v20;
        if ( v20 )
        {
          *(_DWORD *)v20 = 1;
          *(_QWORD *)(v20 + 4) = 42;
          *(_OWORD *)(v20 + 12) = *(_OWORD *)L"ExitWindowsEx";
          *(_OWORD *)(v20 + 22) = *(_OWORD *)L"indowsEx";
          *((_WORD *)v20 + 19) = 0;
          *((_QWORD *)&InputBuffer + 1) = 42;
          DWORD2(v28) = 17;
          *(_QWORD *)&InputBuffer = v20;
          v22 = NtPowerInformation(TraceApplicationPowerMessage|0x40, &InputBuffer, 0x20u, 0, 0);
          if ( v22 < 0
            && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              153,
              WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
              (unsigned int)v22);
          }
          v23 = GetProcessHeap();
          HeapFree(v23, 0, v21);
        }
        else
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v18 = 152;
            goto LABEL_39;
          }
        }
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v18 = 151;
LABEL_39:
          WPP_SF_(*((_QWORD *)v17 + 2), v18, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
        }
      }
    }
  }
  if ( LastError )
  {
    v24 = 4;
    v26[0] = LastError;
    v26[1] = a2;
    if ( LastError != 995 )
      v24 = 1;
    CGlobalStore::ReportApplicationEvent(*(CGlobalStore **)a1, v24, 0xC0000FA4, 8u, v26, 0);
  }
  v26[0] = LastError;
  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_ShutdownWindows_Stop) )
  {
    *(_QWORD *)&InputBuffer = v26;
    *((_QWORD *)&InputBuffer + 1) = 4;
    EtwEventWrite(g_TraceRegHandle, WLEvt_ShutdownWindows_Stop, 1, &InputBuffer);
  }
  return LastError;
}

```

## disassembly

```asm
0x140032e54  mov     [rsp-28h+arg_10], rbx
0x140032e59  mov     [rsp-28h+arg_18], rsi
0x140032e5e  push    rbp
0x140032e5f  push    rdi
0x140032e60  push    r12
0x140032e62  push    r13
0x140032e64  push    r14
0x140032e66  mov     rbp, rsp
0x140032e69  sub     rsp, 60h
0x140032e6d  mov     rax, cs:__security_cookie
0x140032e74  xor     rax, rsp
0x140032e77  mov     [rbp+var_8], rax
0x140032e7b  xor     edi, edi
0x140032e7d  mov     [rbp+var_30], edx
0x140032e80  mov     r14, rcx
0x140032e83  mov     esi, edx
0x140032e85  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140032e8c  lea     r13d, [rdi+1]
0x140032e90  test    rcx, rcx
0x140032e93  jz      short loc_140032ED1
0x140032e95  lea     rdx, WLEvt_ShutdownWindows_Start
0x140032e9c  call    cs:__imp_EtwEventEnabled
0x140032ea2  test    al, al
0x140032ea4  jz      short loc_140032ED1
0x140032ea6  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140032ead  lea     rax, [rbp+var_30]
0x140032eb1  lea     r9, [rbp+InputBuffer]
0x140032eb5  mov     qword ptr [rbp+InputBuffer], rax
0x140032eb9  mov     r8d, r13d
0x140032ebc  mov     qword ptr [rbp+InputBuffer+8], 4
0x140032ec4  lea     rdx, WLEvt_ShutdownWindows_Start
0x140032ecb  call    cs:__imp_EtwEventWrite
0x140032ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ed8  lea     r12, WPP_GLOBAL_Control
0x140032edf  cmp     rcx, r12
0x140032ee2  jz      short loc_140032F0B
0x140032ee4  test    dword ptr [rcx+1Ch], 2000h
0x140032eeb  jz      short loc_140032F0B
0x140032eed  cmp     byte ptr [rcx+19h], 5
0x140032ef1  jb      short loc_140032F0B
0x140032ef3  mov     rcx, [rcx+10h]
0x140032ef7  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140032efe  mov     edx, 50h ; 'P'
0x140032f03  mov     r9d, esi
0x140032f06  call    WPP_SF_d
0x140032f0b  xorps   xmm0, xmm0
0x140032f0e  movups  [rbp+InputBuffer], xmm0
0x140032f12  movups  [rbp+var_18], xmm0
0x140032f16  test    r14, r14
0x140032f19  jz      loc_14003305F
0x140032f1f  mov     rbx, [r14+10h]
0x140032f23  test    rbx, rbx
0x140032f26  jz      loc_14003305F
0x140032f2c  mov     ebx, [rbx+58h]
0x140032f2f  call    cs:__imp_RtlGetActiveConsoleId
0x140032f35  cmp     eax, ebx
0x140032f37  jz      short loc_140032F7A
0x140032f39  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f40  cmp     rcx, r12
0x140032f43  jz      loc_14003305F
0x140032f49  test    dword ptr [rcx+1Ch], 1000h
0x140032f50  jz      loc_14003305F
0x140032f56  cmp     byte ptr [rcx+19h], 5
0x140032f5a  jb      loc_14003305F
0x140032f60  mov     edx, 97h
0x140032f65  mov     rcx, [rcx+10h]
0x140032f69  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140032f70  call    WPP_SF_
0x140032f75  jmp     loc_14003305F
0x140032f7a  call    cs:__imp_GetProcessHeap
0x140032f80  mov     edx, 8; dwFlags
0x140032f85  mov     rcx, rax; hHeap
0x140032f88  lea     r8d, [rdx+22h]; dwBytes
0x140032f8c  call    cs:__imp_HeapAlloc
0x140032f92  mov     rbx, rax
0x140032f95  test    rax, rax
0x140032f98  jnz     short loc_140032FC5
0x140032f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032fa1  cmp     rcx, r12
0x140032fa4  jz      loc_14003305F
0x140032faa  test    [rcx+1Ch], r13b
0x140032fae  jz      loc_14003305F
0x140032fb4  cmp     byte ptr [rcx+19h], 2
0x140032fb8  jb      loc_14003305F
0x140032fbe  mov     edx, 98h
0x140032fc3  jmp     short loc_140032F65
0x140032fc5  mov     [rax], r13d
0x140032fc8  lea     rdx, [rbp+InputBuffer]; InputBuffer
0x140032fcc  mov     [rax+8], r13d
0x140032fd0  mov     ecx, 2Ah ; '*'
0x140032fd5  mov     [rax+4], ecx
0x140032fd8  xor     r9d, r9d; OutputBuffer
0x140032fdb  movups  xmm0, xmmword ptr cs:aExitwindowsex_0; "ExitWindowsEx"
0x140032fe2  lea     r8d, [rcx-0Ah]; InputBufferLength
0x140032fe6  movups  xmmword ptr [rax+0Ch], xmm0
0x140032fea  movups  xmm1, xmmword ptr cs:aExitwindowsex_0+0Ah; "indowsEx"
0x140032ff1  movups  xmmword ptr [rax+16h], xmm1
0x140032ff5  xor     eax, eax
0x140032ff7  mov     [rbx+26h], ax
0x140032ffb  mov     qword ptr [rbp+InputBuffer+8], rcx
0x140032fff  mov     dword ptr [rbp+var_18+8], 11h
0x140033006  lea     ecx, [rax+5Eh]; PowerInformationLevel
0x140033009  mov     qword ptr [rbp+InputBuffer], rbx
0x14003300d  mov     [rsp+60h+OutputBufferLength], eax; OutputBufferLength
0x140033011  call    cs:__imp_NtPowerInformation
0x140033017  test    eax, eax
0x140033019  jns     short loc_14003304B
0x14003301b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033022  cmp     rcx, r12
0x140033025  jz      short loc_14003304B
0x140033027  test    [rcx+1Ch], r13b
0x14003302b  jz      short loc_14003304B
0x14003302d  cmp     byte ptr [rcx+19h], 2
0x140033031  jb      short loc_14003304B
0x140033033  mov     rcx, [rcx+10h]
0x140033037  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14003303e  mov     edx, 99h
0x140033043  mov     r9d, eax
0x140033046  call    WPP_SF_d
0x14003304b  call    cs:__imp_GetProcessHeap
0x140033051  mov     r8, rbx; lpMem
0x140033054  xor     edx, edx; dwFlags
0x140033056  mov     rcx, rax; hHeap
0x140033059  call    cs:__imp_HeapFree
0x14003305f  xor     edx, edx; dwReason
0x140033061  mov     ecx, esi; uFlags
0x140033063  call    cs:__imp_ExitWindowsEx
0x140033069  test    eax, eax
0x14003306b  jnz     short loc_1400330AC
0x14003306d  call    cs:__imp_GetLastError
0x140033073  mov     edi, eax
0x140033075  mov     rcx, cs:WPP_GLOBAL_Control
0x14003307c  cmp     rcx, r12
0x14003307f  jz      short loc_1400330AC
0x140033081  test    dword ptr [rcx+1Ch], 2000h
0x140033088  jz      short loc_1400330AC
0x14003308a  cmp     byte ptr [rcx+19h], 5
0x14003308e  jb      short loc_1400330AC
0x140033090  mov     rcx, [rcx+10h]
0x140033094  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14003309b  mov     edx, 51h ; 'Q'
0x1400330a0  mov     [rsp+60h+OutputBufferLength], eax
0x1400330a4  mov     r9d, esi
0x1400330a7  call    WPP_SF_DD
0x1400330ac  xorps   xmm0, xmm0
0x1400330af  movups  [rbp+InputBuffer], xmm0
0x1400330b3  movups  [rbp+var_18], xmm0
0x1400330b7  test    r14, r14
0x1400330ba  jz      loc_1400331FD
0x1400330c0  mov     rbx, [r14+10h]
0x1400330c4  test    rbx, rbx
0x1400330c7  jz      loc_1400331FD
0x1400330cd  mov     ebx, [rbx+58h]
0x1400330d0  call    cs:__imp_RtlGetActiveConsoleId
0x1400330d6  cmp     eax, ebx
0x1400330d8  jz      short loc_14003311B
0x1400330da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400330e1  cmp     rcx, r12
0x1400330e4  jz      loc_1400331FD
0x1400330ea  test    dword ptr [rcx+1Ch], 1000h
0x1400330f1  jz      loc_1400331FD
0x1400330f7  cmp     byte ptr [rcx+19h], 5
0x1400330fb  jb      loc_1400331FD
0x140033101  mov     edx, 97h
0x140033106  mov     rcx, [rcx+10h]
0x14003310a  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140033111  call    WPP_SF_
0x140033116  jmp     loc_1400331FD
0x14003311b  call    cs:__imp_GetProcessHeap
0x140033121  mov     edx, 8; dwFlags
0x140033126  mov     rcx, rax; hHeap
0x140033129  lea     r8d, [rdx+22h]; dwBytes
0x14003312d  call    cs:__imp_HeapAlloc
0x140033133  mov     rbx, rax
0x140033136  test    rax, rax
0x140033139  jnz     short loc_140033166
0x14003313b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033142  cmp     rcx, r12
0x140033145  jz      loc_1400331FD
0x14003314b  test    [rcx+1Ch], r13b
0x14003314f  jz      loc_1400331FD
0x140033155  cmp     byte ptr [rcx+19h], 2
0x140033159  jb      loc_1400331FD
0x14003315f  mov     edx, 98h
0x140033164  jmp     short loc_140033106
0x140033166  mov     [rax], r13d
0x140033169  lea     rdx, [rbp+InputBuffer]; InputBuffer
0x14003316d  mov     ecx, 2Ah ; '*'
0x140033172  xor     r9d, r9d; OutputBuffer
0x140033175  mov     [rax+4], rcx
0x140033179  movups  xmm0, xmmword ptr cs:aExitwindowsex_0; "ExitWindowsEx"
0x140033180  lea     r8d, [rcx-0Ah]; InputBufferLength
0x140033184  movups  xmmword ptr [rax+0Ch], xmm0
0x140033188  movups  xmm1, xmmword ptr cs:aExitwindowsex_0+0Ah; "indowsEx"
0x14003318f  movups  xmmword ptr [rax+16h], xmm1
0x140033193  xor     eax, eax
0x140033195  mov     [rbx+26h], ax
0x140033199  mov     qword ptr [rbp+InputBuffer+8], rcx
0x14003319d  mov     dword ptr [rbp+var_18+8], 11h
0x1400331a4  lea     ecx, [rax+5Eh]; PowerInformationLevel
0x1400331a7  mov     qword ptr [rbp+InputBuffer], rbx
0x1400331ab  mov     [rsp+60h+OutputBufferLength], eax; OutputBufferLength
0x1400331af  call    cs:__imp_NtPowerInformation
0x1400331b5  test    eax, eax
0x1400331b7  jns     short loc_1400331E9
0x1400331b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331c0  cmp     rcx, r12
0x1400331c3  jz      short loc_1400331E9
0x1400331c5  test    [rcx+1Ch], r13b
0x1400331c9  jz      short loc_1400331E9
0x1400331cb  cmp     byte ptr [rcx+19h], 2
0x1400331cf  jb      short loc_1400331E9
0x1400331d1  mov     rcx, [rcx+10h]
0x1400331d5  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400331dc  mov     edx, 99h
0x1400331e1  mov     r9d, eax
0x1400331e4  call    WPP_SF_d
0x1400331e9  call    cs:__imp_GetProcessHeap
0x1400331ef  mov     r8, rbx; lpMem
0x1400331f2  xor     edx, edx; dwFlags
0x1400331f4  mov     rcx, rax; hHeap
0x1400331f7  call    cs:__imp_HeapFree
0x1400331fd  test    edi, edi
0x1400331ff  jz      short loc_140033240
0x140033201  cmp     edi, 3E3h
0x140033207  mov     qword ptr [rsp+60h+var_38], 0; unsigned int
0x140033210  mov     eax, 4
0x140033215  mov     [rbp+var_30], edi
0x140033218  lea     rcx, [rbp+var_30]
0x14003321c  mov     [rbp+var_2C], esi
0x14003321f  cmovnz  ax, r13w
0x140033224  mov     qword ptr [rsp+60h+OutputBufferLength], rcx; void *
0x140033229  mov     rcx, [r14]; this
0x14003322c  mov     r9d, 8; unsigned int
0x140033232  movzx   edx, ax; unsigned __int16
0x140033235  mov     r8d, 0C0000FA4h; unsigned int
0x14003323b  call    ?ReportApplicationEvent@CGlobalStore@@QEAAKGKKPEAXKZZ; CGlobalStore::ReportApplicationEvent(ushort,ulong,ulong,void *,ulong,...)
0x140033240  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140033247  mov     [rbp+var_30], edi
0x14003324a  test    rcx, rcx
0x14003324d  jz      short loc_14003328B
0x14003324f  lea     rdx, WLEvt_ShutdownWindows_Stop
0x140033256  call    cs:__imp_EtwEventEnabled
0x14003325c  test    al, al
0x14003325e  jz      short loc_14003328B
0x140033260  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140033267  lea     rax, [rbp+var_30]
0x14003326b  lea     r9, [rbp+InputBuffer]
0x14003326f  mov     qword ptr [rbp+InputBuffer], rax
0x140033273  mov     r8d, r13d
0x140033276  mov     qword ptr [rbp+InputBuffer+8], 4
0x14003327e  lea     rdx, WLEvt_ShutdownWindows_Stop
0x140033285  call    cs:__imp_EtwEventWrite
0x14003328b  mov     eax, edi
0x14003328d  mov     rcx, [rbp+var_8]
0x140033291  xor     rcx, rsp; StackCookie
0x140033294  call    __security_check_cookie
0x140033299  lea     r11, [rsp+60h+var_s0]
0x14003329e  mov     rbx, [r11+40h]
0x1400332a2  mov     rsi, [r11+48h]
0x1400332a6  mov     rsp, r11
0x1400332a9  pop     r14
0x1400332ab  pop     r13
0x1400332ad  pop     r12
0x1400332af  pop     rdi
0x1400332b0  pop     rbp
0x1400332b1  retn
```
