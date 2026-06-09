# CDesktopManager::UpdateRemotingMode(void)

- ea: `0x180086e50`
- end: `0x180086fc2`
- name: `?UpdateRemotingMode@CDesktopManager@@AEAA_NXZ`
- size: `370`
- prototype: `bool __fastcall(CDesktopManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18006e044`
- `0x180086db4`

## callees

- `0x18006e978`
- `0x180086e50`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180086ead`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180086ead`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086ea1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086ea1`
- `USER32!GetSystemMetrics` at `0x180086e70`
- `USER32!GetSystemMetrics` at `0x180086e70`
- `WINSTA!WinStationFreePropertyValue` at `0x180086f59`
- `WINSTA!WinStationFreePropertyValue` at `0x180086f9e`
- `WINSTA!WinStationFreePropertyValue` at `0x180086f59`
- `WINSTA!WinStationFreePropertyValue` at `0x180086f9e`
- `WINSTA!WinStationGetConnectionProperty` at `0x180086ef7`
- `WINSTA!WinStationGetConnectionProperty` at `0x180086f84`
- `WINSTA!WinStationGetConnectionProperty` at `0x180086ef7`
- `WINSTA!WinStationGetConnectionProperty` at `0x180086f84`
- `WINSTA!WinStationQueryInformationW` at `0x180086ed1`
- `WINSTA!WinStationQueryInformationW` at `0x180086ed1`

## pseudocode

```c
char __fastcall CDesktopManager::UpdateRemotingMode(CDesktopManager *this)
{
  int v1; // edi
  DWORD CurrentProcessId; // eax
  __int64 v4; // rdx
  char v5; // al
  __int64 v6; // rcx
  DWORD pSessionId; // [rsp+60h] [rbp+28h] BYREF
  int v9; // [rsp+68h] [rbp+30h] BYREF
  int v10; // [rsp+70h] [rbp+38h] BYREF
  __int64 v11; // [rsp+78h] [rbp+40h] BYREF

  v1 = *((_DWORD *)this + 8);
  *((_QWORD *)this + 4) = 0;
  if ( GetSystemMetrics(4096) )
  {
    pSessionId = 0;
    v10 = 0;
    v9 = 0;
    v11 = 0;
    CurrentProcessId = GetCurrentProcessId();
    ProcessIdToSessionId(CurrentProcessId, &pSessionId);
    if ( (unsigned __int8)WinStationQueryInformationW(0, pSessionId, 39, &v9, 4, &v10) && v9 == 5 )
    {
      if ( (unsigned __int8)WinStationGetConnectionProperty(
                              0xFFFFFFFFLL,
                              PROPERTY_TYPE_GET_REMOTEAPP_HD_SUPPORT_LEVEL,
                              &v11) )
      {
        v4 = v11;
        if ( *(_WORD *)v11 == 1 )
        {
          if ( *(_DWORD *)(v11 + 8) == 1 || *(_DWORD *)(v11 + 8) == 2 )
          {
            v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)CDesktopManager::s_pDesktopManagerInstance + 8) + 16LL))(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 8));
            v4 = v11;
            *((_DWORD *)this + 8) = (v5 != 0) + 5;
          }
          else if ( *(_DWORD *)(v11 + 8) == 3 )
          {
            *((_DWORD *)this + 8) = 7;
          }
          else
          {
            *((_DWORD *)this + 8) = 2;
          }
        }
        WinStationFreePropertyValue(v4);
        v11 = 0;
      }
      else
      {
        *((_DWORD *)this + 8) = 4;
      }
    }
    else
    {
      *((_DWORD *)this + 8) = 1;
    }
    if ( (unsigned __int8)WinStationGetConnectionProperty(
                            0xFFFFFFFFLL,
                            PROPERTY_TYPE_GET_SCREEN_CAPTURE_PROTECT_MODE,
                            &v11) )
    {
      v6 = v11;
      if ( *(_WORD *)v11 == 1 )
        *((_DWORD *)this + 9) = *(_DWORD *)(v11 + 8);
      WinStationFreePropertyValue(v6);
    }
  }
  if ( *((_DWORD *)this + 8) == v1 )
    return 0;
  CDesktopManager::UpdateWindowShadows(this);
  return 1;
}

```

## disassembly

```asm
0x180086e50  push    rbp
0x180086e52  push    rbx
0x180086e53  push    rdi
0x180086e54  push    r14
0x180086e56  mov     rbp, rsp
0x180086e59  sub     rsp, 38h
0x180086e5d  mov     edi, [rcx+20h]
0x180086e60  mov     rbx, rcx
0x180086e63  mov     qword ptr [rcx+20h], 0
0x180086e6b  mov     ecx, 1000h; nIndex
0x180086e70  call    cs:__imp_GetSystemMetrics
0x180086e76  mov     r14d, 1
0x180086e7c  test    eax, eax
0x180086e7e  jz      loc_180086FA4
0x180086e84  mov     [rbp+pSessionId], 0
0x180086e8b  mov     [rbp+arg_10], 0
0x180086e92  mov     [rbp+arg_8], 0
0x180086e99  mov     [rbp+arg_18], 0
0x180086ea1  call    cs:__imp_GetCurrentProcessId
0x180086ea7  mov     ecx, eax; dwProcessId
0x180086ea9  lea     rdx, [rbp+pSessionId]; pSessionId
0x180086ead  call    cs:__imp_ProcessIdToSessionId
0x180086eb3  mov     edx, [rbp+pSessionId]
0x180086eb6  lea     rax, [rbp+arg_10]
0x180086eba  mov     [rsp+38h+var_10], rax
0x180086ebf  lea     r9, [rbp+arg_8]
0x180086ec3  lea     r8d, [r14+26h]
0x180086ec7  mov     [rsp+38h+var_18], 4
0x180086ecf  xor     ecx, ecx
0x180086ed1  call    cs:__imp_WinStationQueryInformationW
0x180086ed7  test    al, al
0x180086ed9  jz      loc_180086F72
0x180086edf  cmp     [rbp+arg_8], 5
0x180086ee3  jnz     loc_180086F72
0x180086ee9  lea     r8, [rbp+arg_18]
0x180086eed  or      ecx, 0FFFFFFFFh
0x180086ef0  lea     rdx, PROPERTY_TYPE_GET_REMOTEAPP_HD_SUPPORT_LEVEL
0x180086ef7  call    cs:__imp_WinStationGetConnectionProperty
0x180086efd  test    al, al
0x180086eff  jz      short loc_180086F69
0x180086f01  mov     rdx, [rbp+arg_18]
0x180086f05  cmp     [rdx], r14w
0x180086f09  jnz     short loc_180086F56
0x180086f0b  mov     ecx, [rdx+8]
0x180086f0e  sub     ecx, r14d
0x180086f11  jz      short loc_180086F2F
0x180086f13  sub     ecx, r14d
0x180086f16  jz      short loc_180086F2F
0x180086f18  cmp     ecx, r14d
0x180086f1b  jz      short loc_180086F26
0x180086f1d  mov     dword ptr [rbx+20h], 2
0x180086f24  jmp     short loc_180086F56
0x180086f26  mov     dword ptr [rbx+20h], 7
0x180086f2d  jmp     short loc_180086F56
0x180086f2f  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180086f36  mov     rcx, [rax+40h]
0x180086f3a  mov     rax, [rcx]
0x180086f3d  mov     rax, [rax+10h]
0x180086f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f46  mov     rdx, [rbp+arg_18]
0x180086f4a  neg     al
0x180086f4c  sbb     ecx, ecx
0x180086f4e  neg     ecx
0x180086f50  add     ecx, 5
0x180086f53  mov     [rbx+20h], ecx
0x180086f56  mov     rcx, rdx
0x180086f59  call    cs:__imp_WinStationFreePropertyValue
0x180086f5f  mov     [rbp+arg_18], 0
0x180086f67  jmp     short loc_180086F76
0x180086f69  mov     dword ptr [rbx+20h], 4
0x180086f70  jmp     short loc_180086F76
0x180086f72  mov     [rbx+20h], r14d
0x180086f76  lea     r8, [rbp+arg_18]
0x180086f7a  or      ecx, 0FFFFFFFFh
0x180086f7d  lea     rdx, PROPERTY_TYPE_GET_SCREEN_CAPTURE_PROTECT_MODE
0x180086f84  call    cs:__imp_WinStationGetConnectionProperty
0x180086f8a  test    al, al
0x180086f8c  jz      short loc_180086FA4
0x180086f8e  mov     rcx, [rbp+arg_18]
0x180086f92  cmp     [rcx], r14w
0x180086f96  jnz     short loc_180086F9E
0x180086f98  mov     edx, [rcx+8]
0x180086f9b  mov     [rbx+24h], edx
0x180086f9e  call    cs:__imp_WinStationFreePropertyValue
0x180086fa4  cmp     [rbx+20h], edi
0x180086fa7  jz      short loc_180086FB6
0x180086fa9  mov     rcx, rbx; this
0x180086fac  call    ?UpdateWindowShadows@CDesktopManager@@QEAAXXZ; CDesktopManager::UpdateWindowShadows(void)
0x180086fb1  mov     al, r14b
0x180086fb4  jmp     short loc_180086FB8
0x180086fb6  xor     al, al
0x180086fb8  add     rsp, 38h
0x180086fbc  pop     r14
0x180086fbe  pop     rdi
0x180086fbf  pop     rbx
0x180086fc0  pop     rbp
0x180086fc1  retn
```
