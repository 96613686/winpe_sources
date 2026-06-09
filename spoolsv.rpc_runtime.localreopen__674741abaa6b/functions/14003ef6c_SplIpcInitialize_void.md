# SplIpcInitialize(void)

- ea: `0x14003ef6c`
- end: `0x14003f271`
- name: `?SplIpcInitialize@@YAJXZ`
- size: `773`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140040270`
- `0x14004c580`

## callees

- `0x14001748c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x14003ef6c`

## import_xrefs

- `ntdll!NtAlpcCreatePort` at `0x14003f0c4`
- `ntdll!NtAlpcCreatePort` at `0x14003f0c4`
- `ntdll!NtAlpcConnectPort` at `0x14003f1c1`
- `ntdll!NtAlpcConnectPort` at `0x14003f1c1`
- `ntdll!RtlFreeSid` at `0x14003f241`
- `ntdll!RtlFreeSid` at `0x14003f241`
- `ntdll!RtlInitUnicodeString` at `0x14003efd7`
- `ntdll!RtlInitUnicodeString` at `0x14003efd7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003f11d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003f11d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003f032`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f20e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f20e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003f22b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003f22b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003f002`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003f002`

## string_xrefs

- `0x14003f063`: `[%s] Failed to convert ALPC port security descriptor 0x%x`
- `0x14003f0da`: `[%s] Failed to create PrintSpoolerIPC ALPC port 0x%x`
- `0x14003f12f`: `[%s] Failed to initialize SYSTEM account SID 0x%x`

## pseudocode

```c
__int64 SplIpcInitialize(void)
{
  unsigned int LastError; // ebx
  const char *v1; // r8
  unsigned __int16 *v2; // rdx
  const char *v3; // r8
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  __int128 v7; // [rsp+70h] [rbp-90h] BYREF
  __int128 v8; // [rsp+80h] [rbp-80h]
  __int128 v9; // [rsp+90h] [rbp-70h]
  __int64 v10; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  int v13; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v14; // [rsp+C4h] [rbp-3Ch]
  __int16 v15; // [rsp+CCh] [rbp-34h]
  __int64 v16; // [rsp+D0h] [rbp-30h]
  _BYTE v17[16]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v18; // [rsp+120h] [rbp+20h]

  SecurityDescriptor = 0;
  DestinationString = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  memset_0(v17, 0, 0x48u);
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  RtlInitUnicodeString(&DestinationString, L"\\PrintSpoolerIPC");
  if ( g_bSpoolerIsChildProcess )
  {
    v10 = -100000000;
    LastError = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( LastError )
    {
      v2 = L"[%s] Failed to initialize SYSTEM account SID 0x%x";
    }
    else
    {
      memset_0(&v13, 0, 0x48u);
      v16 = 1024;
      v13 = 0x20000;
      v14 = 12;
      v15 = 257;
      LODWORD(v7) = 48;
      *((_QWORD *)&v7 + 1) = 0;
      DWORD2(v8) = 0;
      *(_QWORD *)&v8 = 0;
      v9 = 0;
      LastError = NtAlpcConnectPort(
                    &g_IPCCommunicationPortHandle,
                    &DestinationString,
                    0,
                    &v13,
                    0x20000,
                    Sid,
                    0,
                    0,
                    0,
                    0,
                    &v10);
      if ( !LastError )
        goto LABEL_21;
      v2 = L"[%s] Failed to connect to PrintSpoolerIPC ALPC port 0x%x";
    }
    goto LABEL_16;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;FA;;;SY)(A;;0x01;;;S-1-5-99-216390572-1995538116-3857911515-2404958512-2623887229)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    LODWORD(v7) = 48;
    *(_QWORD *)&v8 = &DestinationString;
    v9 = (unsigned __int64)SecurityDescriptor;
    *((_QWORD *)&v7 + 1) = 0;
    DWORD2(v8) = 64;
    v18 = 1024;
    LastError = NtAlpcCreatePort(&g_IPCConnectionPortHandle, &v7, v17);
    if ( !LastError )
      goto LABEL_21;
    v2 = L"[%s] Failed to create PrintSpoolerIPC ALPC port 0x%x";
LABEL_16:
    v3 = "Worker";
    if ( !g_bSpoolerIsChildProcess )
      v3 = "Host";
    SpoolerServiceTelemetry::WriteDbgTraceError("SplIpcInitialize", v2, v3, LastError);
    goto LABEL_19;
  }
  if ( (int)GetLastError() > 0 )
    LastError = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    LastError = GetLastError();
  v1 = "Worker";
  if ( !g_bSpoolerIsChildProcess )
    v1 = "Host";
  SpoolerServiceTelemetry::WriteDbgTraceError(
    "SplIpcInitialize",
    L"[%s] Failed to convert ALPC port security descriptor 0x%x",
    v1,
    LastError);
  if ( LastError )
  {
LABEL_19:
    if ( g_IPCCommunicationPortHandle )
    {
      CloseHandle(g_IPCCommunicationPortHandle);
      g_IPCCommunicationPortHandle = 0;
    }
  }
LABEL_21:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( Sid )
    RtlFreeSid(Sid);
  return LastError;
}

```

## disassembly

```asm
0x14003ef6c  mov     [rsp-8+arg_0], rbx
0x14003ef71  mov     [rsp-8+arg_8], rdi
0x14003ef76  push    rbp
0x14003ef77  lea     rbp, [rsp-70h]
0x14003ef7c  sub     rsp, 170h
0x14003ef83  mov     rax, cs:__security_cookie
0x14003ef8a  xor     rax, rsp
0x14003ef8d  mov     [rbp+70h+var_10], rax
0x14003ef91  xorps   xmm1, xmm1
0x14003ef94  lea     rcx, [rbp+70h+var_60]; void *
0x14003ef98  xor     edi, edi
0x14003ef9a  xorps   xmm0, xmm0
0x14003ef9d  xor     edx, edx; Val
0x14003ef9f  mov     [rsp+170h+SecurityDescriptor], rdi
0x14003efa4  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x14003efa8  lea     r8d, [rdi+48h]; Size
0x14003efac  movups  [rsp+170h+var_100], xmm1
0x14003efb1  movups  [rbp+70h+var_F0], xmm1
0x14003efb5  movups  [rbp+70h+var_E0], xmm1
0x14003efb9  call    memset_0
0x14003efbe  lea     rdx, aPrintspoolerip; "\\PrintSpoolerIPC"
0x14003efc5  mov     [rsp+170h+var_108], rdi
0x14003efca  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x14003efce  mov     dword ptr [rbp+70h+IdentifierAuthority.Value], edi
0x14003efd1  mov     word ptr [rbp+70h+IdentifierAuthority.Value+4], 500h
0x14003efd7  call    cs:__imp_RtlInitUnicodeString
0x14003efde  nop     dword ptr [rax+rax+00h]
0x14003efe3  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, dil; bool g_bSpoolerIsChildProcess
0x14003efea  jnz     loc_14003F0E6
0x14003eff0  xor     r9d, r9d; SecurityDescriptorSize
0x14003eff3  lea     r8, [rsp+170h+SecurityDescriptor]; SecurityDescriptor
0x14003eff8  lea     edx, [rdi+1]; StringSDRevision
0x14003effb  lea     rcx, aDAFaSyA0x01S15; "D:(A;;FA;;;SY)(A;;0x01;;;S-1-5-99-21639"...
0x14003f002  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14003f009  nop     dword ptr [rax+rax+00h]
0x14003f00e  test    eax, eax
0x14003f010  jnz     short loc_14003F083
0x14003f012  call    cs:__imp_GetLastError
0x14003f019  nop     dword ptr [rax+rax+00h]
0x14003f01e  test    eax, eax
0x14003f020  jg      short loc_14003F032
0x14003f022  call    cs:__imp_GetLastError
0x14003f029  nop     dword ptr [rax+rax+00h]
0x14003f02e  mov     ebx, eax
0x14003f030  jmp     short loc_14003F047
0x14003f032  call    cs:__imp_GetLastError
0x14003f039  nop     dword ptr [rax+rax+00h]
0x14003f03e  movzx   ebx, ax
0x14003f041  or      ebx, 0C0070000h
0x14003f047  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, dil; bool g_bSpoolerIsChildProcess
0x14003f04e  lea     rax, aHost; "Host"
0x14003f055  lea     r8, aWorker; "Worker"
0x14003f05c  mov     r9d, ebx
0x14003f05f  cmovz   r8, rax
0x14003f063  lea     rdx, aSFailedToConve; "[%s] Failed to convert ALPC port securi"...
0x14003f06a  lea     rcx, aSplipcinitiali; "SplIpcInitialize"
0x14003f071  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003f076  test    ebx, ebx
0x14003f078  jz      loc_14003F221
0x14003f07e  jmp     loc_14003F202
0x14003f083  lea     rax, [rbp+70h+DestinationString]
0x14003f087  mov     dword ptr [rsp+170h+var_100], 30h ; '0'
0x14003f08f  mov     qword ptr [rbp+70h+var_F0], rax
0x14003f093  lea     r8, [rbp+70h+var_60]
0x14003f097  mov     rax, [rsp+170h+SecurityDescriptor]
0x14003f09c  lea     rdx, [rsp+170h+var_100]
0x14003f0a1  lea     rcx, ?g_IPCConnectionPortHandle@@3PEAXEA; void * g_IPCConnectionPortHandle
0x14003f0a8  mov     qword ptr [rbp+70h+var_E0], rax
0x14003f0ac  mov     qword ptr [rsp+170h+var_100+8], rdi
0x14003f0b1  mov     dword ptr [rbp+70h+var_F0+8], 40h ; '@'
0x14003f0b8  mov     qword ptr [rbp+70h+var_E0+8], rdi
0x14003f0bc  mov     [rbp+70h+var_50], 400h
0x14003f0c4  call    cs:__imp_NtAlpcCreatePort
0x14003f0cb  nop     dword ptr [rax+rax+00h]
0x14003f0d0  mov     ebx, eax
0x14003f0d2  test    eax, eax
0x14003f0d4  jz      loc_14003F221
0x14003f0da  lea     rdx, aSFailedToCreat; "[%s] Failed to create PrintSpoolerIPC A"...
0x14003f0e1  jmp     loc_14003F1DA
0x14003f0e6  lea     rax, [rsp+170h+var_108]
0x14003f0eb  mov     [rbp+70h+var_D0], 0FFFFFFFFFA0A1F00h
0x14003f0f3  mov     [rsp+170h+Sid], rax; Sid
0x14003f0f8  lea     rcx, [rbp+70h+IdentifierAuthority]; IdentifierAuthority
0x14003f0fc  mov     [rsp+170h+SubAuthority7], edi; SubAuthority7
0x14003f100  xor     r9d, r9d; SubAuthority1
0x14003f103  mov     [rsp+170h+SubAuthority6], edi; SubAuthority6
0x14003f107  mov     dl, 1; SubAuthorityCount
0x14003f109  mov     [rsp+170h+SubAuthority5], edi; SubAuthority5
0x14003f10d  mov     [rsp+170h+SubAuthority4], edi; SubAuthority4
0x14003f111  mov     [rsp+170h+SubAuthority3], edi; SubAuthority3
0x14003f115  lea     r8d, [r9+12h]; SubAuthority0
0x14003f119  mov     [rsp+170h+SubAuthority2], edi; SubAuthority2
0x14003f11d  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003f124  nop     dword ptr [rax+rax+00h]
0x14003f129  mov     ebx, eax
0x14003f12b  test    eax, eax
0x14003f12d  jz      short loc_14003F13B
0x14003f12f  lea     rdx, aSFailedToIniti; "[%s] Failed to initialize SYSTEM accoun"...
0x14003f136  jmp     loc_14003F1DA
0x14003f13b  xor     edx, edx; Val
0x14003f13d  lea     rcx, [rbp+70h+var_B0]; void *
0x14003f141  lea     r8d, [rdx+48h]; Size
0x14003f145  call    memset_0
0x14003f14a  mov     ecx, 20000h
0x14003f14f  mov     [rbp+70h+var_A0], 400h
0x14003f157  lea     rax, [rbp+70h+var_D0]
0x14003f15b  mov     [rbp+70h+var_B0], ecx
0x14003f15e  mov     [rsp+170h+Sid], rax
0x14003f163  lea     r9, [rbp+70h+var_B0]
0x14003f167  mov     rax, [rsp+170h+var_108]
0x14003f16c  lea     rdx, [rbp+70h+DestinationString]
0x14003f170  mov     qword ptr [rsp+170h+SubAuthority7], rdi
0x14003f175  xorps   xmm0, xmm0
0x14003f178  mov     qword ptr [rsp+170h+SubAuthority6], rdi
0x14003f17d  xor     r8d, r8d
0x14003f180  mov     qword ptr [rsp+170h+SubAuthority5], rdi
0x14003f185  mov     qword ptr [rsp+170h+SubAuthority4], rdi
0x14003f18a  mov     qword ptr [rsp+170h+SubAuthority3], rax
0x14003f18f  mov     [rsp+170h+SubAuthority2], ecx
0x14003f193  lea     rcx, ?g_IPCCommunicationPortHandle@@3PEAXEA; void * g_IPCCommunicationPortHandle
0x14003f19a  mov     [rbp+70h+var_AC], 0Ch
0x14003f1a2  mov     [rbp+70h+var_A4], 101h
0x14003f1a8  mov     dword ptr [rsp+170h+var_100], 30h ; '0'
0x14003f1b0  mov     qword ptr [rsp+170h+var_100+8], rdi
0x14003f1b5  mov     dword ptr [rbp+70h+var_F0+8], edi
0x14003f1b8  mov     qword ptr [rbp+70h+var_F0], rdi
0x14003f1bc  movdqu  [rbp+70h+var_E0], xmm0
0x14003f1c1  call    cs:__imp_NtAlpcConnectPort
0x14003f1c8  nop     dword ptr [rax+rax+00h]
0x14003f1cd  mov     ebx, eax
0x14003f1cf  test    eax, eax
0x14003f1d1  jz      short loc_14003F221
0x14003f1d3  lea     rdx, aSFailedToConne; "[%s] Failed to connect to PrintSpoolerI"...
0x14003f1da  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, dil; bool g_bSpoolerIsChildProcess
0x14003f1e1  lea     rax, aHost; "Host"
0x14003f1e8  lea     r8, aWorker; "Worker"
0x14003f1ef  mov     r9d, ebx
0x14003f1f2  cmovz   r8, rax
0x14003f1f6  lea     rcx, aSplipcinitiali; "SplIpcInitialize"
0x14003f1fd  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003f202  mov     rcx, cs:?g_IPCCommunicationPortHandle@@3PEAXEA; hObject
0x14003f209  test    rcx, rcx
0x14003f20c  jz      short loc_14003F221
0x14003f20e  call    cs:__imp_CloseHandle
0x14003f215  nop     dword ptr [rax+rax+00h]
0x14003f21a  mov     cs:?g_IPCCommunicationPortHandle@@3PEAXEA, rdi; void * g_IPCCommunicationPortHandle
0x14003f221  mov     rcx, [rsp+170h+SecurityDescriptor]; hMem
0x14003f226  test    rcx, rcx
0x14003f229  jz      short loc_14003F237
0x14003f22b  call    cs:__imp_LocalFree
0x14003f232  nop     dword ptr [rax+rax+00h]
0x14003f237  mov     rcx, [rsp+170h+var_108]; Sid
0x14003f23c  test    rcx, rcx
0x14003f23f  jz      short loc_14003F24D
0x14003f241  call    cs:__imp_RtlFreeSid
0x14003f248  nop     dword ptr [rax+rax+00h]
0x14003f24d  mov     eax, ebx
0x14003f24f  mov     rcx, [rbp+70h+var_10]
0x14003f253  xor     rcx, rsp; StackCookie
0x14003f256  call    __security_check_cookie
0x14003f25b  lea     r11, [rsp+170h+var_s0]
0x14003f263  mov     rbx, [r11+10h]
0x14003f267  mov     rdi, [r11+18h]
0x14003f26b  mov     rsp, r11
0x14003f26e  pop     rbp
0x14003f26f  retn
```
