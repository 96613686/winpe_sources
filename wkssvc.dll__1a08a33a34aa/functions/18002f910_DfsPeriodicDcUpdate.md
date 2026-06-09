# DfsPeriodicDcUpdate

- ea: `0x18002f910`
- end: `0x18002fc06`
- name: `DfsPeriodicDcUpdate`
- size: `758`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180005e54`
- `0x180007844`
- `0x18000ace0`
- `0x18000b190`
- `0x18000b290`
- `0x18001fbd0`
- `0x18002f910`
- `0x18002fc0c`
- `0x1800320ac`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18002fa7d`
- `ntdll!WinSqmSetDWORD` at `0x18002fb53`
- `ntdll!WinSqmSetDWORD` at `0x18002fa7d`
- `ntdll!WinSqmSetDWORD` at `0x18002fb53`
- `ntdll!RtlDeregisterWait` at `0x18002f957`
- `ntdll!RtlDeregisterWait` at `0x18002f957`
- `ntdll!RtlRegisterWait` at `0x18002fbbb`
- `ntdll!RtlRegisterWait` at `0x18002fbbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f9fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fbdd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f9fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fbdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002faa2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002faec`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002faa2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002faec`

## pseudocode

```c
void __fastcall DfsPeriodicDcUpdate(PVOID a1, __int64 a2)
{
  char v2; // si
  ULONG ulMilliseconds; // edi
  int v5; // ebx
  unsigned int v6; // edx
  int v7; // ecx
  int DCName; // edi
  int v9; // ebx
  int v10; // eax
  unsigned int DelayInterval; // eax
  BOOL v12; // eax
  int v13; // eax
  _WORD v14[2]; // [rsp+30h] [rbp-29h] BYREF
  BOOL v15; // [rsp+34h] [rbp-25h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v17[3]; // [rsp+48h] [rbp-11h] BYREF

  v2 = a2;
  LOBYTE(v14[0]) = 0;
  if ( (unsigned int)WsIsTerminating(a1, a2) )
    goto LABEL_36;
  ulMilliseconds = -1;
  RtlDeregisterWait(g_WsDomainNameChangeWorkItem);
  v5 = WsInAWorkgroup();
  if ( v2 )
  {
    if ( !v5 )
    {
      v6 = g_ulCount;
LABEL_7:
      v7 = 0;
      if ( v6 > g_ulInitThreshold )
        v7 = 256;
      DCName = DfsGetDCName(v7, v14);
      v9 = 1;
      if ( DCName )
      {
        if ( LOBYTE(v14[0]) || g_ulForce < (unsigned int)g_ulForceThreshold )
          goto LABEL_14;
        DCName = DfsGetDCName(1, v14);
      }
      g_ulForce = 0;
LABEL_14:
      if ( MupEventSignaled )
      {
        v10 = DfsSqmWrapper::gm_IsWinSqmEnabled;
        v14[0] = 0;
        memset(v17, 0, 44);
        if ( DfsSqmWrapper::gm_IsWinSqmEnabled )
        {
          if ( !DfsSqmClient::gm_RegDone )
          {
            if ( !(unsigned int)DfsSqmGetClientDP(393576, 0, 0, (unsigned int)v17, 44) )
            {
              DfsSqmClient::DfsSqmSetClientRegDP((struct DFSC_REGISTRY_SETTINGS *)v17);
              DfsSqmClient::gm_RegDone = 1;
            }
            DelayInterval = DfsGetDelayInterval();
            WinSqmSetDWORD(0, 4540, DelayInterval);
            v10 = DfsSqmWrapper::gm_IsWinSqmEnabled;
          }
          if ( v10 )
          {
            SystemTime = 0;
            GetLocalTime(&SystemTime);
            if ( SystemTime.wHour == 6 * (SystemTime.wHour / 6u) && DfsSqmClient::gm_wHour )
            {
              DfsSqmClient::gm_wHour = SystemTime.wHour % 6u;
              SystemTime = 0;
              GetLocalTime(&SystemTime);
              v12 = 0;
              if ( !SystemTime.wDayOfWeek )
                v12 = DfsSqmClient::gm_wDayOfWeek != 0;
              DfsSqmClient::gm_wDayOfWeek = SystemTime.wDayOfWeek;
              v15 = v12;
              if ( !(unsigned int)DfsSqmGetClientDP(393580, (unsigned int)&v15, 4, (unsigned int)v14, 2)
                && DfsSqmWrapper::gm_IsWinSqmEnabled )
              {
                WinSqmSetDWORD(0, 3924, v14[0]);
              }
            }
            else
            {
              DfsSqmClient::gm_wHour = SystemTime.wHour % 6u;
            }
          }
        }
      }
      else
      {
        SetEvent(hMupEvent);
        MupEventSignaled = 1;
      }
      if ( !DCName || (v13 = g_ulCount, g_ulCount >= (unsigned int)g_ulInitThreshold) )
      {
        v9 = DfsGetDelayInterval();
        v13 = g_ulCount;
      }
      g_ulForce += v9;
      g_ulCount = v9 + v13;
      ulMilliseconds = 60000 * v9;
    }
  }
  else
  {
    WsSetWorkStationDomainName();
    if ( !v5 )
    {
      v6 = 0;
      g_ulCount = 0;
      g_ulForce = g_ulForceThreshold;
      goto LABEL_7;
    }
  }
  if ( RtlRegisterWait(&g_WsDomainNameChangeWorkItem, a1, DfsPeriodicDcUpdate, a1, ulMilliseconds, 0x19u) >= 0 )
    return;
  g_WsDomainNameChangeWorkItem = (HANDLE)-1LL;
LABEL_36:
  SetEvent(WsDfsTearDownDoneEvent);
}

```

## disassembly

```asm
0x18002f910  push    rbp
0x18002f912  push    rbx
0x18002f913  push    rsi
0x18002f914  push    rdi
0x18002f915  push    r14
0x18002f917  push    r15
0x18002f919  lea     rbp, [rsp-2Fh]
0x18002f91e  sub     rsp, 88h
0x18002f925  mov     rax, cs:__security_cookie
0x18002f92c  xor     rax, rsp
0x18002f92f  mov     [rbp+57h+var_38], rax
0x18002f933  xor     r15d, r15d
0x18002f936  mov     sil, dl
0x18002f939  mov     byte ptr [rbp+57h+var_80], r15b
0x18002f93d  mov     r14, rcx
0x18002f940  call    WsIsTerminating
0x18002f945  test    eax, eax
0x18002f947  jnz     loc_18002FBD6
0x18002f94d  mov     rcx, cs:g_WsDomainNameChangeWorkItem; hWaitHandle
0x18002f954  or      edi, 0FFFFFFFFh
0x18002f957  call    cs:__imp_RtlDeregisterWait
0x18002f95e  nop     dword ptr [rax+rax+00h]
0x18002f963  call    WsInAWorkgroup
0x18002f968  mov     ebx, eax
0x18002f96a  test    sil, sil
0x18002f96d  jnz     short loc_18002F993
0x18002f96f  call    WsSetWorkStationDomainName
0x18002f974  test    ebx, ebx
0x18002f976  jnz     loc_18002FB9B
0x18002f97c  mov     eax, cs:g_ulForceThreshold
0x18002f982  mov     edx, r15d
0x18002f985  mov     cs:g_ulCount, edx
0x18002f98b  mov     cs:g_ulForce, eax
0x18002f991  jmp     short loc_18002F9A1
0x18002f993  test    ebx, ebx
0x18002f995  jnz     loc_18002FB9B
0x18002f99b  mov     edx, cs:g_ulCount
0x18002f9a1  cmp     edx, cs:g_ulInitThreshold
0x18002f9a7  mov     ecx, r15d
0x18002f9aa  mov     eax, 100h
0x18002f9af  lea     rdx, [rbp+57h+var_80]
0x18002f9b3  cmova   ecx, eax
0x18002f9b6  call    DfsGetDCName
0x18002f9bb  mov     edi, eax
0x18002f9bd  mov     ebx, 1
0x18002f9c2  test    eax, eax
0x18002f9c4  jz      short loc_18002F9E7
0x18002f9c6  cmp     byte ptr [rbp+57h+var_80], r15b
0x18002f9ca  jnz     short loc_18002F9EE
0x18002f9cc  mov     ecx, cs:g_ulForceThreshold
0x18002f9d2  cmp     cs:g_ulForce, ecx
0x18002f9d8  jb      short loc_18002F9EE
0x18002f9da  lea     rdx, [rbp+57h+var_80]
0x18002f9de  mov     ecx, ebx
0x18002f9e0  call    DfsGetDCName
0x18002f9e5  mov     edi, eax
0x18002f9e7  mov     cs:g_ulForce, r15d
0x18002f9ee  cmp     cs:MupEventSignaled, r15b
0x18002f9f5  jnz     short loc_18002FA15
0x18002f9f7  mov     rcx, cs:hMupEvent; hEvent
0x18002f9fe  call    cs:__imp_SetEvent
0x18002fa05  nop     dword ptr [rax+rax+00h]
0x18002fa0a  mov     cs:MupEventSignaled, bl
0x18002fa10  jmp     loc_18002FB68
0x18002fa15  mov     eax, cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x18002fa1b  xorps   xmm0, xmm0
0x18002fa1e  mov     [rbp+57h+var_80], r15w
0x18002fa23  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18002fa27  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x18002fa2b  movups  [rbp+57h+var_68], xmm0
0x18002fa2f  test    eax, eax
0x18002fa31  jz      loc_18002FB68
0x18002fa37  cmp     cs:?gm_RegDone@DfsSqmClient@@2EA, r15b; uchar DfsSqmClient::gm_RegDone
0x18002fa3e  jnz     short loc_18002FA8F
0x18002fa40  lea     r9, [rbp+57h+var_68]
0x18002fa44  mov     [rsp+0B0h+ulMilliseconds], 2Ch ; ','
0x18002fa4c  xor     r8d, r8d
0x18002fa4f  xor     edx, edx
0x18002fa51  mov     ecx, 60168h
0x18002fa56  call    DfsSqmGetClientDP
0x18002fa5b  test    eax, eax
0x18002fa5d  jnz     short loc_18002FA6E
0x18002fa5f  lea     rcx, [rbp+57h+var_68]; struct DFSC_REGISTRY_SETTINGS *
0x18002fa63  call    ?DfsSqmSetClientRegDP@DfsSqmClient@@SAXPEAUDFSC_REGISTRY_SETTINGS@@@Z; DfsSqmClient::DfsSqmSetClientRegDP(DFSC_REGISTRY_SETTINGS *)
0x18002fa68  mov     cs:?gm_RegDone@DfsSqmClient@@2EA, bl; uchar DfsSqmClient::gm_RegDone
0x18002fa6e  call    DfsGetDelayInterval
0x18002fa73  mov     r8d, eax
0x18002fa76  mov     edx, 11BCh
0x18002fa7b  xor     ecx, ecx
0x18002fa7d  call    cs:__imp_WinSqmSetDWORD
0x18002fa84  nop     dword ptr [rax+rax+00h]
0x18002fa89  mov     eax, cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x18002fa8f  test    eax, eax
0x18002fa91  jz      loc_18002FB68
0x18002fa97  xorps   xmm0, xmm0
0x18002fa9a  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002fa9e  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18002faa2  call    cs:__imp_GetLocalTime
0x18002faa9  nop     dword ptr [rax+rax+00h]
0x18002faae  movzx   ecx, [rbp+57h+SystemTime.wHour]
0x18002fab2  mov     eax, 0AAAAAAABh
0x18002fab7  mul     ecx
0x18002fab9  shr     edx, 2
0x18002fabc  lea     eax, [rdx+rdx*2]
0x18002fabf  add     eax, eax
0x18002fac1  sub     ecx, eax
0x18002fac3  test    cx, cx
0x18002fac6  jnz     loc_18002FB61
0x18002facc  cmp     r15w, cs:?gm_wHour@DfsSqmClient@@2GA; ushort DfsSqmClient::gm_wHour
0x18002fad4  jz      loc_18002FB61
0x18002fada  mov     cs:?gm_wHour@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wHour
0x18002fae1  xorps   xmm0, xmm0
0x18002fae4  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002fae8  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18002faec  call    cs:__imp_GetLocalTime
0x18002faf3  nop     dword ptr [rax+rax+00h]
0x18002faf8  movzx   ecx, [rbp+57h+SystemTime.wDayOfWeek]
0x18002fafc  mov     eax, r15d
0x18002faff  test    cx, cx
0x18002fb02  jnz     short loc_18002FB10
0x18002fb04  xor     edx, edx
0x18002fb06  cmp     dx, cs:?gm_wDayOfWeek@DfsSqmClient@@2GA; ushort DfsSqmClient::gm_wDayOfWeek
0x18002fb0d  cmovnz  eax, ebx
0x18002fb10  mov     cs:?gm_wDayOfWeek@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wDayOfWeek
0x18002fb17  lea     r9, [rbp+57h+var_80]
0x18002fb1b  mov     ecx, 6016Ch
0x18002fb20  mov     [rbp+57h+var_7C], eax
0x18002fb23  mov     r8d, 4
0x18002fb29  mov     [rsp+0B0h+ulMilliseconds], 2
0x18002fb31  lea     rdx, [rbp+57h+var_7C]
0x18002fb35  call    DfsSqmGetClientDP
0x18002fb3a  test    eax, eax
0x18002fb3c  jnz     short loc_18002FB68
0x18002fb3e  cmp     cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA, r15d; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x18002fb45  jz      short loc_18002FB68
0x18002fb47  movzx   r8d, [rbp+57h+var_80]
0x18002fb4c  mov     edx, 0F54h
0x18002fb51  xor     ecx, ecx
0x18002fb53  call    cs:__imp_WinSqmSetDWORD
0x18002fb5a  nop     dword ptr [rax+rax+00h]
0x18002fb5f  jmp     short loc_18002FB68
0x18002fb61  mov     cs:?gm_wHour@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wHour
0x18002fb68  test    edi, edi
0x18002fb6a  jz      short loc_18002FB7A
0x18002fb6c  mov     eax, cs:g_ulCount
0x18002fb72  cmp     eax, cs:g_ulInitThreshold
0x18002fb78  jb      short loc_18002FB87
0x18002fb7a  call    DfsGetDelayInterval
0x18002fb7f  mov     ebx, eax
0x18002fb81  mov     eax, cs:g_ulCount
0x18002fb87  add     cs:g_ulForce, ebx
0x18002fb8d  add     eax, ebx
0x18002fb8f  mov     cs:g_ulCount, eax
0x18002fb95  imul    edi, ebx, 0EA60h
0x18002fb9b  mov     [rsp+0B0h+ulFlags], 19h; ulFlags
0x18002fba3  lea     r8, DfsPeriodicDcUpdate; Callback
0x18002fbaa  mov     r9, r14; pvContext
0x18002fbad  mov     [rsp+0B0h+ulMilliseconds], edi; ulMilliseconds
0x18002fbb1  mov     rdx, r14; hObject
0x18002fbb4  lea     rcx, g_WsDomainNameChangeWorkItem; phNewWaitObject
0x18002fbbb  call    cs:__imp_RtlRegisterWait
0x18002fbc2  nop     dword ptr [rax+rax+00h]
0x18002fbc7  test    eax, eax
0x18002fbc9  jns     short loc_18002FBE9
0x18002fbcb  mov     cs:g_WsDomainNameChangeWorkItem, 0FFFFFFFFFFFFFFFFh
0x18002fbd6  mov     rcx, cs:WsDfsTearDownDoneEvent; hEvent
0x18002fbdd  call    cs:__imp_SetEvent
0x18002fbe4  nop     dword ptr [rax+rax+00h]
0x18002fbe9  mov     rcx, [rbp+57h+var_38]
0x18002fbed  xor     rcx, rsp; StackCookie
0x18002fbf0  call    __security_check_cookie
0x18002fbf5  add     rsp, 88h
0x18002fbfc  pop     r15
0x18002fbfe  pop     r14
0x18002fc00  pop     rdi
0x18002fc01  pop     rsi
0x18002fc02  pop     rbx
0x18002fc03  pop     rbp
0x18002fc04  retn
```
