# CService::Shutdown(void)

- ea: `0x180003cd0`
- end: `0x180003ec5`
- name: `?Shutdown@CService@@QEAAXXZ`
- size: `501`
- prototype: `void __fastcall(CService *this, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800031b0`
- `0x180003b60`

## callees

- `0x180003cd0`
- `0x180007f28`
- `0x18000937c`
- `0x18000de4c`
- `0x18000dfd4`
- `0x18000e3e4`
- `0x18000e53c`
- `0x18000ea58`
- `0x18000ea84`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d6c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180003d19`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180003d19`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003e76`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003e76`

## string_xrefs

- `0x180003e08`: `SERVICE_STOPPED`

## pseudocode

```c
void __fastcall CService::Shutdown(CService *this, unsigned int a2)
{
  CWPDTraceControl *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void *v5; // rcx
  signed int LastError; // eax
  void *v7; // rcx
  CPnPNotification *v8; // rdi
  CPnPNotification *v9; // rcx
  struct _SERVICE_STATUS *v10; // rdx
  signed int v11; // eax

  v3 = (CWPDTraceControl *)*((_QWORD *)this + 9);
  if ( v3 )
  {
    CWPDTraceControl::StopTracing(v3);
    v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 9);
    if ( v4 )
      (**v4)(v4, 1);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
  {
    if ( !UnregisterWait(v5) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
          (unsigned int)LastError);
      }
    }
    *((_QWORD *)this + 6) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 7);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 7) = 0;
  }
  v8 = g_PnPNotification;
  if ( g_PnPNotification )
  {
    CPnPNotification::Uninitialize(g_PnPNotification);
    operator delete(v8);
    g_PnPNotification = 0;
  }
  if ( g_WPDBus )
  {
    operator delete(g_WPDBus);
    g_WPDBus = 0;
  }
  if ( g_GroupPolicy )
  {
    CGroupPolicy::`scalar deleting destructor'(g_GroupPolicy, a2);
    g_GroupPolicy = 0;
  }
  if ( g_BthActiveConnector )
  {
    CBthActiveConnector::`scalar deleting destructor'(g_BthActiveConnector, a2);
    g_BthActiveConnector = 0;
  }
  *((_QWORD *)this + 5) = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
      L"SERVICE_STOPPED");
    v9 = WPP_GLOBAL_Control;
  }
  v10 = (struct _SERVICE_STATUS *)((char *)this + 8);
  if ( *((_DWORD *)this + 3) == 1 )
  {
    if ( v9 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)v9 + 2), 64, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
  }
  else
  {
    v10->dwServiceType = 48;
    *(_QWORD *)((char *)this + 20) = 0;
    *((_DWORD *)this + 3) = 1;
    *(_QWORD *)((char *)this + 28) = 0;
    *((_DWORD *)this + 4) = 1217;
    if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)this, v10) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
          (unsigned int)v11);
      }
    }
  }
}

```

## disassembly

```asm
0x180003cd0  push    rbx
0x180003cd2  push    rbp
0x180003cd3  push    rsi
0x180003cd4  push    rdi
0x180003cd5  sub     rsp, 28h
0x180003cd9  mov     rbx, rcx
0x180003cdc  xor     esi, esi
0x180003cde  mov     rcx, [rcx+48h]; this
0x180003ce2  test    rcx, rcx
0x180003ce5  jz      short loc_180003D09
0x180003ce7  call    ?StopTracing@CWPDTraceControl@@QEAAXXZ; CWPDTraceControl::StopTracing(void)
0x180003cec  mov     rcx, [rbx+48h]
0x180003cf0  test    rcx, rcx
0x180003cf3  jz      short loc_180003D05
0x180003cf5  mov     rax, [rcx]
0x180003cf8  mov     edx, 1
0x180003cfd  mov     rax, [rax]
0x180003d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d05  mov     [rbx+48h], rsi
0x180003d09  mov     rcx, [rbx+30h]; WaitHandle
0x180003d0d  lea     rbp, WPP_GLOBAL_Control
0x180003d14  test    rcx, rcx
0x180003d17  jz      short loc_180003D63
0x180003d19  call    cs:__imp_UnregisterWait
0x180003d1f  test    eax, eax
0x180003d21  jnz     short loc_180003D5F
0x180003d23  call    cs:__imp_GetLastError
0x180003d29  test    eax, eax
0x180003d2b  jle     short loc_180003D35
0x180003d2d  movzx   eax, ax
0x180003d30  or      eax, 80070000h
0x180003d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d3c  cmp     rcx, rbp
0x180003d3f  jz      short loc_180003D5F
0x180003d41  test    byte ptr [rcx+1Ch], 4
0x180003d45  jz      short loc_180003D5F
0x180003d47  mov     rcx, [rcx+10h]
0x180003d4b  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003d52  mov     edx, 3Eh ; '>'
0x180003d57  mov     r9d, eax
0x180003d5a  call    WPP_SF_d
0x180003d5f  mov     [rbx+30h], rsi
0x180003d63  mov     rcx, [rbx+38h]; hObject
0x180003d67  test    rcx, rcx
0x180003d6a  jz      short loc_180003D76
0x180003d6c  call    cs:__imp_CloseHandle
0x180003d72  mov     [rbx+38h], rsi
0x180003d76  mov     rdi, cs:?g_PnPNotification@@3PEAVCPnPNotification@@EA; CPnPNotification * g_PnPNotification
0x180003d7d  test    rdi, rdi
0x180003d80  jz      short loc_180003D9E
0x180003d82  mov     rcx, rdi; this
0x180003d85  call    ?Uninitialize@CPnPNotification@@QEAAJXZ; CPnPNotification::Uninitialize(void)
0x180003d8a  mov     edx, 18h
0x180003d8f  mov     rcx, rdi; Block
0x180003d92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003d97  mov     cs:?g_PnPNotification@@3PEAVCPnPNotification@@EA, rsi; CPnPNotification * g_PnPNotification
0x180003d9e  mov     rcx, cs:?g_WPDBus@@3PEAVCWPDBus@@EA; Block
0x180003da5  test    rcx, rcx
0x180003da8  jz      short loc_180003DBB
0x180003daa  mov     edx, 4
0x180003daf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003db4  mov     cs:?g_WPDBus@@3PEAVCWPDBus@@EA, rsi; CWPDBus * g_WPDBus
0x180003dbb  mov     rcx, cs:?g_GroupPolicy@@3PEAVCGroupPolicy@@EA; this
0x180003dc2  test    rcx, rcx
0x180003dc5  jz      short loc_180003DD3
0x180003dc7  call    ??_GCGroupPolicy@@QEAAPEAXI@Z; CGroupPolicy::`scalar deleting destructor'(uint)
0x180003dcc  mov     cs:?g_GroupPolicy@@3PEAVCGroupPolicy@@EA, rsi; CGroupPolicy * g_GroupPolicy
0x180003dd3  mov     rcx, cs:?g_BthActiveConnector@@3PEAVCBthActiveConnector@@EA; this
0x180003dda  test    rcx, rcx
0x180003ddd  jz      short loc_180003DEB
0x180003ddf  call    ??_GCBthActiveConnector@@QEAAPEAXI@Z; CBthActiveConnector::`scalar deleting destructor'(uint)
0x180003de4  mov     cs:?g_BthActiveConnector@@3PEAVCBthActiveConnector@@EA, rsi; CBthActiveConnector * g_BthActiveConnector
0x180003deb  mov     [rbx+28h], rsi
0x180003def  mov     rcx, cs:WPP_GLOBAL_Control
0x180003df6  cmp     rcx, rbp
0x180003df9  jz      short loc_180003E27
0x180003dfb  test    dword ptr [rcx+1Ch], 200h
0x180003e02  jz      short loc_180003E27
0x180003e04  mov     rcx, [rcx+10h]
0x180003e08  lea     r9, aServiceStopped; "SERVICE_STOPPED"
0x180003e0f  mov     edx, 3Fh ; '?'
0x180003e14  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003e1b  call    WPP_SF_S
0x180003e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e27  cmp     dword ptr [rbx+0Ch], 1
0x180003e2b  lea     rdx, [rbx+8]; lpServiceStatus
0x180003e2f  jnz     short loc_180003E57
0x180003e31  cmp     rcx, rbp
0x180003e34  jz      loc_180003EBC
0x180003e3a  test    byte ptr [rcx+1Ch], 2
0x180003e3e  jz      short loc_180003EBC
0x180003e40  mov     rcx, [rcx+10h]
0x180003e44  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003e4b  mov     edx, 40h ; '@'
0x180003e50  call    WPP_SF_
0x180003e55  jmp     short loc_180003EBC
0x180003e57  mov     dword ptr [rdx], 30h ; '0'
0x180003e5d  mov     [rbx+14h], rsi
0x180003e61  mov     dword ptr [rbx+0Ch], 1
0x180003e68  mov     [rbx+1Ch], rsi
0x180003e6c  mov     dword ptr [rdx+8], 4C1h
0x180003e73  mov     rcx, [rbx]; hServiceStatus
0x180003e76  call    cs:__imp_SetServiceStatus
0x180003e7c  test    eax, eax
0x180003e7e  jnz     short loc_180003EBC
0x180003e80  call    cs:__imp_GetLastError
0x180003e86  test    eax, eax
0x180003e88  jle     short loc_180003E92
0x180003e8a  movzx   eax, ax
0x180003e8d  or      eax, 80070000h
0x180003e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e99  cmp     rcx, rbp
0x180003e9c  jz      short loc_180003EBC
0x180003e9e  test    byte ptr [rcx+1Ch], 2
0x180003ea2  jz      short loc_180003EBC
0x180003ea4  mov     rcx, [rcx+10h]
0x180003ea8  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003eaf  mov     edx, 41h ; 'A'
0x180003eb4  mov     r9d, eax
0x180003eb7  call    WPP_SF_d
0x180003ebc  add     rsp, 28h
0x180003ec0  pop     rdi
0x180003ec1  pop     rsi
0x180003ec2  pop     rbp
0x180003ec3  pop     rbx
0x180003ec4  retn
```
