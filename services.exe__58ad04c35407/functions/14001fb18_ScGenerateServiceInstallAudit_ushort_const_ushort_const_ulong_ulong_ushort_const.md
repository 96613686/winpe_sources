# ScGenerateServiceInstallAudit(ushort const *,ushort const *,ulong,ulong,ushort const *)

- ea: `0x14001fb18`
- end: `0x14001fde8`
- name: `?ScGenerateServiceInstallAudit@@YAKPEBG0KK0@Z`
- size: `720`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140066ef4`

## callees

- `0x14001f99c`
- `0x14001fb18`
- `0x140020400`
- `0x1400575b0`
- `0x14005a9cc`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fdac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fdac`
- `RPCRT4!I_RpcMapWin32Status` at `0x14001fbf4`
- `RPCRT4!I_RpcMapWin32Status` at `0x14001fd03`
- `RPCRT4!I_RpcMapWin32Status` at `0x14001fdc4`
- `RPCRT4!I_RpcMapWin32Status` at `0x14001fbf4`
- `RPCRT4!I_RpcMapWin32Status` at `0x14001fd03`
- `RPCRT4!I_RpcMapWin32Status` at `0x14001fdc4`
- `RPCRT4!RpcImpersonateClient` at `0x14001fbec`
- `RPCRT4!RpcImpersonateClient` at `0x14001fbec`
- `RPCRT4!RpcRevertToSelf` at `0x14001fcfb`
- `RPCRT4!RpcRevertToSelf` at `0x14001fdbc`
- `RPCRT4!RpcRevertToSelf` at `0x14001fcfb`
- `RPCRT4!RpcRevertToSelf` at `0x14001fdbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001fd47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001fd47`
- `ntdll!RtlNtStatusToDosError` at `0x14001fdd4`
- `ntdll!RtlNtStatusToDosError` at `0x14001fdd4`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x14001fd29`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x14001fd29`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x14001fce9`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x14001fce9`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x14001fc9a`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x14001fc9a`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x14001fd38`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x14001fd38`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x14001fd12`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x14001fd12`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x14001fbc3`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x14001fbc3`

## string_xrefs

- `0x14001fc0f`: `Security`

## pseudocode

```c
__int64 __fastcall ScGenerateServiceInstallAudit(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        const unsigned __int16 *a5)
{
  int v5; // edi
  const wchar_t *v10; // rsi
  RPC_STATUS v11; // eax
  NTSTATUS v12; // eax
  DWORD LastError; // ebx
  RPC_STATUS v14; // eax
  RPC_STATUS v16; // eax
  int v17; // [rsp+20h] [rbp-110h]
  unsigned int v18; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  AUTHZ_AUDIT_EVENT_HANDLE hAuditEvent; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-70h] BYREF
  unsigned __int64 v22; // [rsp+C8h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+D0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+D8h] [rbp-58h] BYREF
  _BYTE *v25; // [rsp+E8h] [rbp-48h]
  _BYTE v26[352]; // [rsp+F0h] [rbp-40h] BYREF

  v5 = 0;
  v21 = 0;
  hAuditEvent = 0;
  v24 = 0;
  v25 = 0;
  hMem = 0;
  v19 = 0;
  v22 = 0;
  v18 = 0;
  if ( !(unsigned __int8)IsAuthziInitializeAuditEventTypePresent() )
    return 0;
  memset(v26, 0, sizeof(v26));
  v10 = L"LocalSystem";
  if ( a5 )
    v10 = a5;
  if ( !(unsigned int)AuthziInitializeAuditEventType(0, 1, 4697, 9, &v21) )
    goto LABEL_20;
  if ( (int)GetCallerProcessInfo(&v19, &v22, &v18) < 0
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 10, WPP_0aa217a2f8f235f6a5020605ce4a1f2b_Traceguids);
  }
  v11 = RpcImpersonateClient(0);
  v12 = I_RpcMapWin32Status(v11);
  if ( v12 >= 0 )
  {
    v25 = v26;
    v5 = 1;
    LOWORD(v17) = 9;
    if ( (unsigned int)AuthziInitializeAuditParams(
                         1,
                         &v24,
                         &hMem,
                         L"Security",
                         v17,
                         525,
                         2,
                         a1,
                         2,
                         a2,
                         3,
                         a3,
                         3,
                         a4,
                         2,
                         v10,
                         11,
                         v22,
                         3,
                         v19,
                         3,
                         v18) )
    {
      if ( (unsigned int)AuthziInitializeAuditEvent(
                           0,
                           0,
                           v21,
                           &v24,
                           0,
                           -1,
                           &dword_14009C804,
                           &dword_14009C804,
                           &dword_14009C804,
                           &dword_14009C804,
                           &hAuditEvent) )
      {
        LastError = 0;
        v5 = 0;
        v14 = RpcRevertToSelf();
        I_RpcMapWin32Status(v14);
        if ( (unsigned int)AuthziLogAuditEvent(0, hAuditEvent, 0) )
          goto LABEL_10;
      }
    }
LABEL_20:
    LastError = GetLastError();
    if ( !v5 )
      goto LABEL_10;
    v16 = RpcRevertToSelf();
    v12 = I_RpcMapWin32Status(v16);
    if ( v12 >= 0 )
      goto LABEL_10;
  }
  LastError = RtlNtStatusToDosError(v12);
LABEL_10:
  if ( hAuditEvent )
    AuthzFreeAuditEvent(hAuditEvent);
  if ( v21 )
    AuthziFreeAuditEventType();
  if ( hMem )
    LocalFree(hMem);
  return LastError;
}

```

## disassembly

```asm
0x14001fb18  push    rbp
0x14001fb1a  push    rbx
0x14001fb1b  push    rsi
0x14001fb1c  push    rdi
0x14001fb1d  push    r12
0x14001fb1f  push    r13
0x14001fb21  push    r14
0x14001fb23  push    r15
0x14001fb25  lea     rbp, [rsp-138h]
0x14001fb2d  sub     rsp, 268h
0x14001fb34  mov     rax, cs:__security_cookie
0x14001fb3b  xor     rax, rsp
0x14001fb3e  mov     [rbp+170h+var_50], rax
0x14001fb45  mov     rbx, [rbp+170h+arg_20]
0x14001fb4c  xor     edi, edi
0x14001fb4e  xorps   xmm0, xmm0
0x14001fb51  mov     [rbp+170h+var_1E0], rdi
0x14001fb55  xor     eax, eax
0x14001fb57  mov     [rbp+170h+hAuditEvent], rdi
0x14001fb5b  movups  [rbp+170h+var_1C8], xmm0
0x14001fb5f  mov     [rbp+170h+var_1B8], rax
0x14001fb63  mov     r13d, r9d
0x14001fb66  mov     [rbp+170h+hMem], rdi
0x14001fb6a  mov     r12d, r8d
0x14001fb6d  mov     [rbp+170h+var_1EC], edi
0x14001fb70  mov     r15, rdx
0x14001fb73  mov     [rbp+170h+var_1D8], rdi
0x14001fb77  mov     r14, rcx
0x14001fb7a  mov     [rbp+170h+var_1F0], edi
0x14001fb7d  call    IsAuthziInitializeAuditEventTypePresent
0x14001fb82  test    al, al
0x14001fb84  jz      loc_14001FDE1
0x14001fb8a  xor     edx, edx; Val
0x14001fb8c  lea     rcx, [rbp+170h+var_1B0]; void *
0x14001fb90  mov     r8d, 160h; Size
0x14001fb96  call    memset
0x14001fb9b  test    rbx, rbx
0x14001fb9e  lea     rax, [rbp+170h+var_1E0]
0x14001fba2  lea     rsi, aLocalsystem; "LocalSystem"
0x14001fba9  mov     [rsp+2A0h+var_280], rax
0x14001fbae  cmovnz  rsi, rbx
0x14001fbb2  lea     r9d, [rdi+9]
0x14001fbb6  lea     ebx, [rdi+1]
0x14001fbb9  mov     r8d, 1259h
0x14001fbbf  mov     edx, ebx
0x14001fbc1  xor     ecx, ecx
0x14001fbc3  call    cs:__imp_AuthziInitializeAuditEventType
0x14001fbc9  test    eax, eax
0x14001fbcb  jz      loc_14001FDAC
0x14001fbd1  lea     r8, [rbp+170h+var_1F0]; unsigned int *
0x14001fbd5  lea     rdx, [rbp+170h+var_1D8]; unsigned __int64 *
0x14001fbd9  lea     rcx, [rbp+170h+var_1EC]; unsigned int *
0x14001fbdd  call    ?GetCallerProcessInfo@@YAJPEAKPEA_K0@Z; GetCallerProcessInfo(ulong *,unsigned __int64 *,ulong *)
0x14001fbe2  test    eax, eax
0x14001fbe4  js      loc_14001FD72
0x14001fbea  xor     ecx, ecx; BindingHandle
0x14001fbec  call    cs:__imp_RpcImpersonateClient
0x14001fbf2  mov     ecx, eax; Status
0x14001fbf4  call    cs:__imp_I_RpcMapWin32Status
0x14001fbfa  test    eax, eax
0x14001fbfc  js      loc_14001FDD2
0x14001fc02  mov     edx, 3
0x14001fc07  lea     rax, [rbp+170h+var_1B0]
0x14001fc0b  mov     [rbp+170h+var_1B8], rax
0x14001fc0f  lea     r9, aSecurity; "Security"
0x14001fc16  mov     eax, [rbp+170h+var_1F0]
0x14001fc19  lea     r8, [rbp+170h+hMem]
0x14001fc1d  mov     [rsp+2A0h+var_1F8], eax
0x14001fc24  mov     ecx, ebx
0x14001fc26  mov     eax, [rbp+170h+var_1EC]
0x14001fc29  mov     edi, ebx
0x14001fc2b  mov     [rsp+2A0h+var_200], edx
0x14001fc32  mov     [rsp+2A0h+var_208], eax
0x14001fc39  mov     rax, [rbp+170h+var_1D8]
0x14001fc3d  mov     [rsp+2A0h+var_210], edx
0x14001fc44  mov     [rsp+2A0h+var_218], rax
0x14001fc4c  lea     eax, [rdx-1]
0x14001fc4f  mov     [rsp+2A0h+var_220], 0Bh
0x14001fc5a  mov     [rsp+2A0h+var_228], rsi
0x14001fc5f  mov     [rsp+2A0h+var_230], eax
0x14001fc63  mov     [rsp+2A0h+var_238], r13d
0x14001fc68  mov     [rsp+2A0h+var_240], edx
0x14001fc6c  mov     [rsp+2A0h+var_248], r12d
0x14001fc71  mov     dword ptr [rsp+2A0h+var_250], edx
0x14001fc75  lea     rdx, [rbp+170h+var_1C8]
0x14001fc79  mov     [rsp+2A0h+var_258], r15
0x14001fc7e  mov     dword ptr [rsp+2A0h+var_260], eax
0x14001fc82  mov     [rsp+2A0h+var_268], r14
0x14001fc87  mov     dword ptr [rsp+2A0h+var_270], eax
0x14001fc8b  mov     [rsp+2A0h+var_278], 20Dh
0x14001fc93  mov     word ptr [rsp+2A0h+var_280], 9
0x14001fc9a  call    cs:__imp_AuthziInitializeAuditParams
0x14001fca0  test    eax, eax
0x14001fca2  jz      loc_14001FDAC
0x14001fca8  mov     r8, [rbp+170h+var_1E0]
0x14001fcac  lea     rax, [rbp+170h+hAuditEvent]
0x14001fcb0  mov     [rsp+2A0h+var_250], rax
0x14001fcb5  lea     r9, [rbp+170h+var_1C8]
0x14001fcb9  lea     rax, dword_14009C804
0x14001fcc0  xor     edx, edx
0x14001fcc2  mov     [rsp+2A0h+var_258], rax
0x14001fcc7  xor     ecx, ecx
0x14001fcc9  mov     [rsp+2A0h+var_260], rax
0x14001fcce  mov     [rsp+2A0h+var_268], rax
0x14001fcd3  mov     [rsp+2A0h+var_270], rax
0x14001fcd8  mov     [rsp+2A0h+var_278], 0FFFFFFFFh
0x14001fce0  mov     [rsp+2A0h+var_280], 0
0x14001fce9  call    cs:__imp_AuthziInitializeAuditEvent
0x14001fcef  test    eax, eax
0x14001fcf1  jz      loc_14001FDAC
0x14001fcf7  xor     ebx, ebx
0x14001fcf9  xor     edi, edi
0x14001fcfb  call    cs:__imp_RpcRevertToSelf
0x14001fd01  mov     ecx, eax; Status
0x14001fd03  call    cs:__imp_I_RpcMapWin32Status
0x14001fd09  mov     rdx, [rbp+170h+hAuditEvent]
0x14001fd0d  xor     r8d, r8d
0x14001fd10  xor     ecx, ecx
0x14001fd12  call    cs:__imp_AuthziLogAuditEvent
0x14001fd18  test    eax, eax
0x14001fd1a  jz      loc_14001FDAC
0x14001fd20  mov     rcx, [rbp+170h+hAuditEvent]; hAuditEvent
0x14001fd24  test    rcx, rcx
0x14001fd27  jz      short loc_14001FD2F
0x14001fd29  call    cs:__imp_AuthzFreeAuditEvent
0x14001fd2f  mov     rcx, [rbp+170h+var_1E0]
0x14001fd33  test    rcx, rcx
0x14001fd36  jz      short loc_14001FD3E
0x14001fd38  call    cs:__imp_AuthziFreeAuditEventType
0x14001fd3e  mov     rcx, [rbp+170h+hMem]; hMem
0x14001fd42  test    rcx, rcx
0x14001fd45  jz      short loc_14001FD4D
0x14001fd47  call    cs:__imp_LocalFree
0x14001fd4d  mov     eax, ebx
0x14001fd4f  mov     rcx, [rbp+170h+var_50]
0x14001fd56  xor     rcx, rsp; StackCookie
0x14001fd59  call    __security_check_cookie
0x14001fd5e  add     rsp, 268h
0x14001fd65  pop     r15
0x14001fd67  pop     r14
0x14001fd69  pop     r13
0x14001fd6b  pop     r12
0x14001fd6d  pop     rdi
0x14001fd6e  pop     rsi
0x14001fd6f  pop     rbx
0x14001fd70  pop     rbp
0x14001fd71  retn
0x14001fd72  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd79  lea     rax, WPP_GLOBAL_Control
0x14001fd80  cmp     rcx, rax
0x14001fd83  jz      loc_14001FBEA
0x14001fd89  test    [rcx+1Ch], bl
0x14001fd8c  jz      loc_14001FBEA
0x14001fd92  mov     rcx, [rcx+10h]
0x14001fd96  lea     r8, WPP_0aa217a2f8f235f6a5020605ce4a1f2b_Traceguids
0x14001fd9d  mov     edx, 0Ah
0x14001fda2  call    WPP_SF_
0x14001fda7  jmp     loc_14001FBEA
0x14001fdac  call    cs:__imp_GetLastError
0x14001fdb2  mov     ebx, eax
0x14001fdb4  test    edi, edi
0x14001fdb6  jz      loc_14001FD20
0x14001fdbc  call    cs:__imp_RpcRevertToSelf
0x14001fdc2  mov     ecx, eax; Status
0x14001fdc4  call    cs:__imp_I_RpcMapWin32Status
0x14001fdca  test    eax, eax
0x14001fdcc  jns     loc_14001FD20
0x14001fdd2  mov     ecx, eax; Status
0x14001fdd4  call    cs:__imp_RtlNtStatusToDosError
0x14001fdda  mov     ebx, eax
0x14001fddc  jmp     loc_14001FD20
0x14001fde1  xor     eax, eax
0x14001fde3  jmp     loc_14001FD4F
```
