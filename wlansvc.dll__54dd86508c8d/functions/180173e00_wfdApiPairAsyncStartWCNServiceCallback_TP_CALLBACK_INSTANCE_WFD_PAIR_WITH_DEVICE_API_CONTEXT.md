# wfdApiPairAsyncStartWCNServiceCallback(_TP_CALLBACK_INSTANCE *,_WFD_PAIR_WITH_DEVICE_API_CONTEXT *)

- ea: `0x180173e00`
- end: `0x180174340`
- name: `?wfdApiPairAsyncStartWCNServiceCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAU_WFD_PAIR_WITH_DEVICE_API_CONTEXT@@@Z`
- size: `1344`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180106340`
- `0x180148674`
- `0x180148b6c`
- `0x180173e00`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18017412d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18017412d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180174038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801741f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180174038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801741f7`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180174085`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180174085`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1801742e3`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1801742e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180174070`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18017415e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180174179`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801741aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180174070`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18017415e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180174179`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801741aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801742bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801742cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801742bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801742cc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180173e85`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180173e85`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180173eec`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180173eec`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180173f4a`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180173f4a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18017402e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18017414b`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18017402e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18017414b`

## pseudocode

```c
void __fastcall wfdApiPairAsyncStartWCNServiceCallback(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context)
{
  struct _TP_CALLBACK_INSTANCE *v3; // rdi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r12
  DWORD v6; // eax
  DWORD v7; // ebx
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // r15
  DWORD LastError; // eax
  DWORD v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD TickCount; // r14d
  unsigned int v15; // esi
  PVOID *v16; // rcx
  DWORD v17; // edi
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  void *v21; // rdx
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-40h] BYREF
  PTP_CALLBACK_INSTANCE v23; // [rsp+48h] [rbp-38h]
  BYTE Buffer[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h]
  int v26; // [rsp+70h] [rbp-10h]

  v23 = Instance;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v26 = 0;
  v25 = 0;
  v3 = Instance;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids);
  }
  v4 = OpenSCManagerW(0, 0, 0xF003Fu);
  v5 = v4;
  if ( v4 )
  {
    v8 = OpenServiceW(v4, L"wcncsvc", 0xF01FFu);
    v9 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids, LastError);
      }
      goto LABEL_78;
    }
    if ( StartServiceW(v8, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 47, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids);
      }
      if ( QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        v7 = 0;
        TickCount = GetTickCount();
        v15 = DWORD1(v25);
        if ( *(_DWORD *)&Buffer[4] == 2 && !CallbackMayRunLong(v3) )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_43;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 49, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids);
        }
        while ( 1 )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
          if ( *(_DWORD *)&Buffer[4] != 2 )
            goto LABEL_67;
          v17 = DWORD2(v25) / 0xA;
          if ( DWORD2(v25) / 0xA >= 0x3E8 )
          {
            if ( v17 > 0x2710 )
              v17 = 10000;
          }
          else
          {
            v17 = 100;
          }
          if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 105) >= 4u && (*((_BYTE *)v16 + 108) & 1) != 0 )
            WPP_SF_d(v16[12], 50, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids, v17);
          Sleep(v17);
          if ( !QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
            break;
          if ( DWORD1(v25) <= v15 )
          {
            if ( *(_DWORD *)&Buffer[4] != 4 && GetTickCount() - TickCount > DWORD2(v25) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 105)
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                v19 = GetTickCount();
                WPP_SF_ddDDD(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  52,
                  &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids,
                  v15,
                  DWORD1(v25),
                  TickCount,
                  v19,
                  DWORD2(v25));
              }
              v7 = 1053;
              goto LABEL_77;
            }
          }
          else
          {
            v18 = GetTickCount();
            v15 = DWORD1(v25);
            TickCount = v18;
          }
        }
        v20 = GetLastError();
        v7 = v20;
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids, v20);
          v16 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v7 )
        {
LABEL_67:
          if ( *(_DWORD *)&Buffer[4] == 4 )
          {
            if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 105) >= 3u && (*((_BYTE *)v16 + 108) & 1) != 0 )
              WPP_SF_(v16[12], 53, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids);
          }
          else
          {
            if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 105) && (*((_BYTE *)v16 + 108) & 1) != 0 )
              WPP_SF_dddd(
                v16[12],
                54,
                &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids,
                *(unsigned int *)&Buffer[4],
                *(_DWORD *)&Buffer[12],
                DWORD1(v25),
                DWORD2(v25));
            v7 = 1062;
          }
          goto LABEL_77;
        }
        goto LABEL_77;
      }
      v11 = GetLastError();
      v7 = v11;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v13 = 48;
        goto LABEL_26;
      }
    }
    else
    {
      v7 = GetLastError();
      if ( v7 == 1056 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids);
        }
        v7 = 0;
        goto LABEL_77;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v11 = GetLastError();
        v12 = WPP_GLOBAL_Control;
        v13 = 46;
LABEL_26:
        WPP_SF_d(v12[12], v13, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids, v11);
      }
    }
LABEL_77:
    CloseServiceHandle(v9);
    v3 = v23;
LABEL_78:
    CloseServiceHandle(v5);
    goto LABEL_79;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 43, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids, v6);
  }
LABEL_79:
  v21 = (void *)Context[132];
  *((_DWORD *)Context + 266) = v7;
  SetEventWhenCallbackReturns(v3, v21);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, &WPP_f9315378723b3ee03c5c992df849b65d_Traceguids, v7);
  }
}

```

## disassembly

```asm
0x180173e00  mov     [rsp-38h+arg_10], rbx
0x180173e05  push    rbp
0x180173e06  push    rsi
0x180173e07  push    rdi
0x180173e08  push    r12
0x180173e0a  push    r13
0x180173e0c  push    r14
0x180173e0e  push    r15
0x180173e10  mov     rbp, rsp
0x180173e13  sub     rsp, 80h
0x180173e1a  mov     rax, cs:__security_cookie
0x180173e21  xor     rax, rsp
0x180173e24  mov     [rbp+var_8], rax
0x180173e28  xorps   xmm0, xmm0
0x180173e2b  mov     [rbp+var_38], rcx
0x180173e2f  xor     eax, eax
0x180173e31  mov     [rbp+var_40], 0
0x180173e38  movups  xmmword ptr [rbp+Buffer], xmm0
0x180173e3c  mov     [rbp+var_10], eax
0x180173e3f  mov     r13, rdx
0x180173e42  movups  [rbp+var_20], xmm0
0x180173e46  mov     rdi, rcx
0x180173e49  mov     rcx, cs:WPP_GLOBAL_Control
0x180173e50  lea     rsi, WPP_GLOBAL_Control
0x180173e57  cmp     rcx, rsi
0x180173e5a  jz      short loc_180173E7B
0x180173e5c  cmp     byte ptr [rcx+69h], 4
0x180173e60  jb      short loc_180173E7B
0x180173e62  test    byte ptr [rcx+6Ch], 1
0x180173e66  jz      short loc_180173E7B
0x180173e68  mov     rcx, [rcx+60h]
0x180173e6c  lea     edx, [rax+2Ah]
0x180173e6f  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x180173e76  call    WPP_SF_
0x180173e7b  xor     edx, edx; lpDatabaseName
0x180173e7d  xor     ecx, ecx; lpMachineName
0x180173e7f  mov     r8d, 0F003Fh; dwDesiredAccess
0x180173e85  call    cs:__imp_OpenSCManagerW
0x180173e8b  mov     r12, rax
0x180173e8e  test    rax, rax
0x180173e91  jnz     short loc_180173EDC
0x180173e93  call    cs:__imp_GetLastError
0x180173e99  mov     ebx, eax
0x180173e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180173ea2  cmp     rcx, rsi
0x180173ea5  jz      loc_1801742D2
0x180173eab  cmp     byte ptr [rcx+69h], 1
0x180173eaf  jb      loc_1801742D2
0x180173eb5  test    byte ptr [rcx+6Ch], 1
0x180173eb9  jz      loc_1801742D2
0x180173ebf  mov     rcx, [rcx+60h]
0x180173ec3  lea     edx, [r12+2Bh]
0x180173ec8  mov     r9d, eax
0x180173ecb  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x180173ed2  call    WPP_SF_d
0x180173ed7  jmp     loc_1801742D2
0x180173edc  mov     r8d, 0F01FFh; dwDesiredAccess
0x180173ee2  lea     rdx, aWcncsvc; "wcncsvc"
0x180173ee9  mov     rcx, r12; hSCManager
0x180173eec  call    cs:__imp_OpenServiceW
0x180173ef2  mov     r15, rax
0x180173ef5  test    rax, rax
0x180173ef8  jnz     short loc_180173F42
0x180173efa  call    cs:__imp_GetLastError
0x180173f00  mov     ebx, eax
0x180173f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180173f09  cmp     rcx, rsi
0x180173f0c  jz      loc_1801742C9
0x180173f12  cmp     byte ptr [rcx+69h], 1
0x180173f16  jb      loc_1801742C9
0x180173f1c  test    byte ptr [rcx+6Ch], 1
0x180173f20  jz      loc_1801742C9
0x180173f26  mov     rcx, [rcx+60h]
0x180173f2a  lea     edx, [r15+2Ch]
0x180173f2e  mov     r9d, eax
0x180173f31  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x180173f38  call    WPP_SF_d
0x180173f3d  jmp     loc_1801742C9
0x180173f42  xor     r8d, r8d; lpServiceArgVectors
0x180173f45  xor     edx, edx; dwNumServiceArgs
0x180173f47  mov     rcx, r15; hService
0x180173f4a  call    cs:__imp_StartServiceW
0x180173f50  test    eax, eax
0x180173f52  jnz     loc_180173FE9
0x180173f58  call    cs:__imp_GetLastError
0x180173f5e  mov     ebx, eax
0x180173f60  cmp     eax, 420h
0x180173f65  jnz     short loc_180173F9B
0x180173f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180173f6e  cmp     rcx, rsi
0x180173f71  jz      short loc_180173F94
0x180173f73  cmp     byte ptr [rcx+69h], 3
0x180173f77  jb      short loc_180173F94
0x180173f79  test    byte ptr [rcx+6Ch], 1
0x180173f7d  jz      short loc_180173F94
0x180173f7f  mov     rcx, [rcx+60h]
0x180173f83  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x180173f8a  mov     edx, 2Dh ; '-'
0x180173f8f  call    WPP_SF_
0x180173f94  xor     ebx, ebx
0x180173f96  jmp     loc_1801742BC
0x180173f9b  mov     rax, cs:WPP_GLOBAL_Control
0x180173fa2  cmp     rax, rsi
0x180173fa5  jz      loc_1801742BC
0x180173fab  cmp     byte ptr [rax+69h], 1
0x180173faf  jb      loc_1801742BC
0x180173fb5  test    byte ptr [rax+6Ch], 1
0x180173fb9  jz      loc_1801742BC
0x180173fbf  call    cs:__imp_GetLastError
0x180173fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180173fcc  mov     edx, 2Eh ; '.'
0x180173fd1  mov     rcx, [rcx+60h]
0x180173fd5  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x180173fdc  mov     r9d, eax
0x180173fdf  call    WPP_SF_d
0x180173fe4  jmp     loc_1801742BC
0x180173fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180173ff0  cmp     rcx, rsi
0x180173ff3  jz      short loc_180174016
0x180173ff5  cmp     byte ptr [rcx+69h], 3
0x180173ff9  jb      short loc_180174016
0x180173ffb  test    byte ptr [rcx+6Ch], 1
0x180173fff  jz      short loc_180174016
0x180174001  mov     rcx, [rcx+60h]
0x180174005  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x18017400c  mov     edx, 2Fh ; '/'
0x180174011  call    WPP_SF_
0x180174016  lea     rax, [rbp+var_40]
0x18017401a  mov     r9d, 24h ; '$'; cbBufSize
0x180174020  lea     r8, [rbp+Buffer]; lpBuffer
0x180174024  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180174029  xor     edx, edx; InfoLevel
0x18017402b  mov     rcx, r15; hService
0x18017402e  call    cs:__imp_QueryServiceStatusEx
0x180174034  test    eax, eax
0x180174036  jnz     short loc_18017406E
0x180174038  call    cs:__imp_GetLastError
0x18017403e  mov     ebx, eax
0x180174040  mov     rcx, cs:WPP_GLOBAL_Control
0x180174047  cmp     rcx, rsi
0x18017404a  jz      loc_1801742BC
0x180174050  cmp     byte ptr [rcx+69h], 1
0x180174054  jb      loc_1801742BC
0x18017405a  test    byte ptr [rcx+6Ch], 1
0x18017405e  jz      loc_1801742BC
0x180174064  mov     edx, 30h ; '0'
0x180174069  jmp     loc_180173FD1
0x18017406e  xor     ebx, ebx
0x180174070  call    cs:__imp_GetTickCount
0x180174076  cmp     dword ptr [rbp+Buffer+4], 2
0x18017407a  mov     r14d, eax
0x18017407d  mov     esi, dword ptr [rbp+var_20+4]
0x180174080  jnz     short loc_1801740C1
0x180174082  mov     rcx, rdi; pci
0x180174085  call    cs:__imp_CallbackMayRunLong
0x18017408b  test    eax, eax
0x18017408d  jnz     short loc_1801740C1
0x18017408f  mov     rcx, cs:WPP_GLOBAL_Control
0x180174096  lea     r8, WPP_GLOBAL_Control
0x18017409d  cmp     rcx, r8
0x1801740a0  jz      short loc_1801740CF
0x1801740a2  cmp     byte ptr [rcx+69h], 2
0x1801740a6  jb      short loc_1801740CF
0x1801740a8  test    byte ptr [rcx+6Ch], 1
0x1801740ac  jz      short loc_1801740CF
0x1801740ae  mov     rcx, [rcx+60h]
0x1801740b2  lea     edx, [rbx+31h]
0x1801740b5  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x1801740bc  call    WPP_SF_
0x1801740c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801740c8  lea     r8, WPP_GLOBAL_Control
0x1801740cf  cmp     dword ptr [rbp+Buffer+4], 2
0x1801740d3  mov     r9d, 2710h
0x1801740d9  jnz     loc_180174243
0x1801740df  mov     eax, 0CCCCCCCDh
0x1801740e4  mul     dword ptr [rbp+var_20+8]
0x1801740e7  mov     edi, edx
0x1801740e9  shr     edi, 3
0x1801740ec  cmp     edi, 3E8h
0x1801740f2  jnb     short loc_1801740FB
0x1801740f4  mov     edi, 64h ; 'd'
0x1801740f9  jmp     short loc_180174102
0x1801740fb  cmp     edi, r9d
0x1801740fe  cmova   edi, r9d
0x180174102  cmp     rcx, r8
0x180174105  jz      short loc_18017412B
0x180174107  cmp     byte ptr [rcx+69h], 4
0x18017410b  jb      short loc_18017412B
0x18017410d  test    byte ptr [rcx+6Ch], 1
0x180174111  jz      short loc_18017412B
0x180174113  mov     rcx, [rcx+60h]
0x180174117  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x18017411e  mov     edx, 32h ; '2'
0x180174123  mov     r9d, edi
0x180174126  call    WPP_SF_d
0x18017412b  mov     ecx, edi; dwMilliseconds
0x18017412d  call    cs:__imp_Sleep
0x180174133  lea     rax, [rbp+var_40]
0x180174137  mov     r9d, 24h ; '$'; cbBufSize
0x18017413d  lea     r8, [rbp+Buffer]; lpBuffer
0x180174141  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180174146  xor     edx, edx; InfoLevel
0x180174148  mov     rcx, r15; hService
0x18017414b  call    cs:__imp_QueryServiceStatusEx
0x180174151  test    eax, eax
0x180174153  jz      loc_1801741F7
0x180174159  cmp     dword ptr [rbp+var_20+4], esi
0x18017415c  jbe     short loc_18017416F
0x18017415e  call    cs:__imp_GetTickCount
0x180174164  mov     esi, dword ptr [rbp+var_20+4]
0x180174167  mov     r14d, eax
0x18017416a  jmp     loc_1801740C1
0x18017416f  cmp     dword ptr [rbp+Buffer+4], 4
0x180174173  jz      loc_1801740C1
0x180174179  call    cs:__imp_GetTickCount
0x18017417f  sub     eax, r14d
0x180174182  cmp     eax, dword ptr [rbp+var_20+8]
0x180174185  jbe     loc_1801740C1
0x18017418b  mov     rax, cs:WPP_GLOBAL_Control
0x180174192  lea     rcx, WPP_GLOBAL_Control
0x180174199  cmp     rax, rcx
0x18017419c  jz      short loc_1801741E6
0x18017419e  cmp     byte ptr [rax+69h], 1
0x1801741a2  jb      short loc_1801741E6
0x1801741a4  test    byte ptr [rax+6Ch], 1
0x1801741a8  jz      short loc_1801741E6
0x1801741aa  call    cs:__imp_GetTickCount
0x1801741b0  mov     ecx, dword ptr [rbp+var_20+8]
0x1801741b3  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x1801741ba  mov     [rsp+80h+var_48], ecx
0x1801741be  mov     edx, 34h ; '4'
0x1801741c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801741ca  mov     r9d, esi
0x1801741cd  mov     [rsp+80h+var_50], eax
0x1801741d1  mov     eax, dword ptr [rbp+var_20+4]
0x1801741d4  mov     [rsp+80h+var_58], r14d
0x1801741d9  mov     rcx, [rcx+60h]
0x1801741dd  mov     dword ptr [rsp+80h+pcbBytesNeeded], eax
0x1801741e1  call    WPP_SF_ddDDD
0x1801741e6  mov     ebx, 41Dh
0x1801741eb  lea     rsi, WPP_GLOBAL_Control
0x1801741f2  jmp     loc_1801742BC
0x1801741f7  call    cs:__imp_GetLastError
0x1801741fd  mov     ebx, eax
0x1801741ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180174206  lea     rsi, WPP_GLOBAL_Control
0x18017420d  cmp     rcx, rsi
0x180174210  jz      short loc_18017423D
0x180174212  cmp     byte ptr [rcx+69h], 1
0x180174216  jb      short loc_18017423D
0x180174218  test    byte ptr [rcx+6Ch], 1
0x18017421c  jz      short loc_18017423D
0x18017421e  mov     rcx, [rcx+60h]
0x180174222  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x180174229  mov     edx, 33h ; '3'
0x18017422e  mov     r9d, eax
0x180174231  call    WPP_SF_d
0x180174236  mov     rcx, cs:WPP_GLOBAL_Control
0x18017423d  test    ebx, ebx
0x18017423f  jnz     short loc_1801742BC
0x180174241  jmp     short loc_18017424A
0x180174243  lea     rsi, WPP_GLOBAL_Control
0x18017424a  cmp     dword ptr [rbp+Buffer+4], 4
0x18017424e  jnz     short loc_180174278
0x180174250  cmp     rcx, rsi
0x180174253  jz      short loc_1801742BC
0x180174255  cmp     byte ptr [rcx+69h], 3
0x180174259  jb      short loc_1801742BC
0x18017425b  test    byte ptr [rcx+6Ch], 1
0x18017425f  jz      short loc_1801742BC
0x180174261  mov     rcx, [rcx+60h]
0x180174265  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x18017426c  mov     edx, 35h ; '5'
0x180174271  call    WPP_SF_
0x180174276  jmp     short loc_1801742BC
0x180174278  cmp     rcx, rsi
0x18017427b  jz      short loc_1801742B7
0x18017427d  cmp     byte ptr [rcx+69h], 1
0x180174281  jb      short loc_1801742B7
0x180174283  test    byte ptr [rcx+6Ch], 1
0x180174287  jz      short loc_1801742B7
0x180174289  mov     eax, dword ptr [rbp+var_20+8]
0x18017428c  lea     r8, WPP_f9315378723b3ee03c5c992df849b65d_Traceguids
0x180174293  mov     r9d, dword ptr [rbp+Buffer+4]
0x180174297  mov     edx, 36h ; '6'
0x18017429c  mov     rcx, [rcx+60h]
0x1801742a0  mov     [rsp+80h+var_50], eax
0x1801742a4  mov     eax, dword ptr [rbp+var_20+4]
0x1801742a7  mov     [rsp+80h+var_58], eax
0x1801742ab  mov     eax, dword ptr [rbp+Buffer+0Ch]
0x1801742ae  mov     dword ptr [rsp+80h+pcbBytesNeeded], eax
0x1801742b2  call    WPP_SF_dddd
0x1801742b7  mov     ebx, 426h
0x1801742bc  mov     rcx, r15; hSCObject
0x1801742bf  call    cs:__imp_CloseServiceHandle
0x1801742c5  mov     rdi, [rbp+var_38]
0x1801742c9  mov     rcx, r12; hSCObject
0x1801742cc  call    cs:__imp_CloseServiceHandle
0x1801742d2  mov     rdx, [r13+420h]; evt
0x1801742d9  mov     rcx, rdi; pci
  ... truncated ...
```
