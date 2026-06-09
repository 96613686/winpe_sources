# SplIpcInitialize(void)

- ea: `0x14003b7dc`
- end: `0x14003ba9e`
- name: `?SplIpcInitialize@@YAJXZ`
- size: `706`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003c9d0`
- `0x140048140`

## callees

- `0x1400160a0`
- `0x14002abc0`
- `0x14002b810`
- `0x14003b7dc`

## import_xrefs

- `ntdll!NtAlpcCreatePort` at `0x14003b916`
- `ntdll!NtAlpcCreatePort` at `0x14003b916`
- `ntdll!NtAlpcConnectPort` at `0x14003ba07`
- `ntdll!NtAlpcConnectPort` at `0x14003ba07`
- `ntdll!RtlFreeSid` at `0x14003ba75`
- `ntdll!RtlFreeSid` at `0x14003ba75`
- `ntdll!RtlInitUnicodeString` at `0x14003b847`
- `ntdll!RtlInitUnicodeString` at `0x14003b847`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003b969`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003b969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b88a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ba4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ba4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003ba65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003ba65`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003b86c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003b86c`

## string_xrefs

- `0x14003b8b5`: `[%s] Failed to convert ALPC port security descriptor 0x%x`
- `0x14003b926`: `[%s] Failed to create PrintSpoolerIPC ALPC port 0x%x`
- `0x14003b975`: `[%s] Failed to initialize SYSTEM account SID 0x%x`

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
0x14003b7dc  mov     [rsp-8+arg_0], rbx
0x14003b7e1  mov     [rsp-8+arg_8], rdi
0x14003b7e6  push    rbp
0x14003b7e7  lea     rbp, [rsp-70h]
0x14003b7ec  sub     rsp, 170h
0x14003b7f3  mov     rax, cs:__security_cookie
0x14003b7fa  xor     rax, rsp
0x14003b7fd  mov     [rbp+70h+var_10], rax
0x14003b801  xorps   xmm1, xmm1
0x14003b804  lea     rcx, [rbp+70h+var_60]; void *
0x14003b808  xor     edi, edi
0x14003b80a  xorps   xmm0, xmm0
0x14003b80d  xor     edx, edx; Val
0x14003b80f  mov     [rsp+170h+SecurityDescriptor], rdi
0x14003b814  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x14003b818  lea     r8d, [rdi+48h]; Size
0x14003b81c  movups  [rsp+170h+var_100], xmm1
0x14003b821  movups  [rbp+70h+var_F0], xmm1
0x14003b825  movups  [rbp+70h+var_E0], xmm1
0x14003b829  call    memset_0
0x14003b82e  lea     rdx, aPrintspoolerip; "\\PrintSpoolerIPC"
0x14003b835  mov     [rsp+170h+var_108], rdi
0x14003b83a  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x14003b83e  mov     dword ptr [rbp+70h+IdentifierAuthority.Value], edi
0x14003b841  mov     word ptr [rbp+70h+IdentifierAuthority.Value+4], 500h
0x14003b847  call    cs:__imp_RtlInitUnicodeString
0x14003b84d  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, dil; bool g_bSpoolerIsChildProcess
0x14003b854  jnz     loc_14003B932
0x14003b85a  xor     r9d, r9d; SecurityDescriptorSize
0x14003b85d  lea     r8, [rsp+170h+SecurityDescriptor]; SecurityDescriptor
0x14003b862  lea     edx, [rdi+1]; StringSDRevision
0x14003b865  lea     rcx, aDAFaSyA0x01S15; "D:(A;;FA;;;SY)(A;;0x01;;;S-1-5-99-21639"...
0x14003b86c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14003b872  test    eax, eax
0x14003b874  jnz     short loc_14003B8D5
0x14003b876  call    cs:__imp_GetLastError
0x14003b87c  test    eax, eax
0x14003b87e  jg      short loc_14003B88A
0x14003b880  call    cs:__imp_GetLastError
0x14003b886  mov     ebx, eax
0x14003b888  jmp     short loc_14003B899
0x14003b88a  call    cs:__imp_GetLastError
0x14003b890  movzx   ebx, ax
0x14003b893  or      ebx, 0C0070000h
0x14003b899  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, dil; bool g_bSpoolerIsChildProcess
0x14003b8a0  lea     rax, aHost; "Host"
0x14003b8a7  lea     r8, aWorker; "Worker"
0x14003b8ae  mov     r9d, ebx
0x14003b8b1  cmovz   r8, rax
0x14003b8b5  lea     rdx, aSFailedToConve; "[%s] Failed to convert ALPC port securi"...
0x14003b8bc  lea     rcx, aSplipcinitiali; "SplIpcInitialize"
0x14003b8c3  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b8c8  test    ebx, ebx
0x14003b8ca  jz      loc_14003BA5B
0x14003b8d0  jmp     loc_14003BA42
0x14003b8d5  lea     rax, [rbp+70h+DestinationString]
0x14003b8d9  mov     dword ptr [rsp+170h+var_100], 30h ; '0'
0x14003b8e1  mov     qword ptr [rbp+70h+var_F0], rax
0x14003b8e5  lea     r8, [rbp+70h+var_60]
0x14003b8e9  mov     rax, [rsp+170h+SecurityDescriptor]
0x14003b8ee  lea     rdx, [rsp+170h+var_100]
0x14003b8f3  lea     rcx, ?g_IPCConnectionPortHandle@@3PEAXEA; void * g_IPCConnectionPortHandle
0x14003b8fa  mov     qword ptr [rbp+70h+var_E0], rax
0x14003b8fe  mov     qword ptr [rsp+170h+var_100+8], rdi
0x14003b903  mov     dword ptr [rbp+70h+var_F0+8], 40h ; '@'
0x14003b90a  mov     qword ptr [rbp+70h+var_E0+8], rdi
0x14003b90e  mov     [rbp+70h+var_50], 400h
0x14003b916  call    cs:__imp_NtAlpcCreatePort
0x14003b91c  mov     ebx, eax
0x14003b91e  test    eax, eax
0x14003b920  jz      loc_14003BA5B
0x14003b926  lea     rdx, aSFailedToCreat; "[%s] Failed to create PrintSpoolerIPC A"...
0x14003b92d  jmp     loc_14003BA1A
0x14003b932  lea     rax, [rsp+170h+var_108]
0x14003b937  mov     [rbp+70h+var_D0], 0FFFFFFFFFA0A1F00h
0x14003b93f  mov     [rsp+170h+Sid], rax; Sid
0x14003b944  lea     rcx, [rbp+70h+IdentifierAuthority]; IdentifierAuthority
0x14003b948  mov     [rsp+170h+SubAuthority7], edi; SubAuthority7
0x14003b94c  xor     r9d, r9d; SubAuthority1
0x14003b94f  mov     [rsp+170h+SubAuthority6], edi; SubAuthority6
0x14003b953  mov     dl, 1; SubAuthorityCount
0x14003b955  mov     [rsp+170h+SubAuthority5], edi; SubAuthority5
0x14003b959  mov     [rsp+170h+SubAuthority4], edi; SubAuthority4
0x14003b95d  mov     [rsp+170h+SubAuthority3], edi; SubAuthority3
0x14003b961  lea     r8d, [r9+12h]; SubAuthority0
0x14003b965  mov     [rsp+170h+SubAuthority2], edi; SubAuthority2
0x14003b969  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003b96f  mov     ebx, eax
0x14003b971  test    eax, eax
0x14003b973  jz      short loc_14003B981
0x14003b975  lea     rdx, aSFailedToIniti; "[%s] Failed to initialize SYSTEM accoun"...
0x14003b97c  jmp     loc_14003BA1A
0x14003b981  xor     edx, edx; Val
0x14003b983  lea     rcx, [rbp+70h+var_B0]; void *
0x14003b987  lea     r8d, [rdx+48h]; Size
0x14003b98b  call    memset_0
0x14003b990  mov     ecx, 20000h
0x14003b995  mov     [rbp+70h+var_A0], 400h
0x14003b99d  lea     rax, [rbp+70h+var_D0]
0x14003b9a1  mov     [rbp+70h+var_B0], ecx
0x14003b9a4  mov     [rsp+170h+Sid], rax
0x14003b9a9  lea     r9, [rbp+70h+var_B0]
0x14003b9ad  mov     rax, [rsp+170h+var_108]
0x14003b9b2  lea     rdx, [rbp+70h+DestinationString]
0x14003b9b6  mov     qword ptr [rsp+170h+SubAuthority7], rdi
0x14003b9bb  xorps   xmm0, xmm0
0x14003b9be  mov     qword ptr [rsp+170h+SubAuthority6], rdi
0x14003b9c3  xor     r8d, r8d
0x14003b9c6  mov     qword ptr [rsp+170h+SubAuthority5], rdi
0x14003b9cb  mov     qword ptr [rsp+170h+SubAuthority4], rdi
0x14003b9d0  mov     qword ptr [rsp+170h+SubAuthority3], rax
0x14003b9d5  mov     [rsp+170h+SubAuthority2], ecx
0x14003b9d9  lea     rcx, ?g_IPCCommunicationPortHandle@@3PEAXEA; void * g_IPCCommunicationPortHandle
0x14003b9e0  mov     [rbp+70h+var_AC], 0Ch
0x14003b9e8  mov     [rbp+70h+var_A4], 101h
0x14003b9ee  mov     dword ptr [rsp+170h+var_100], 30h ; '0'
0x14003b9f6  mov     qword ptr [rsp+170h+var_100+8], rdi
0x14003b9fb  mov     dword ptr [rbp+70h+var_F0+8], edi
0x14003b9fe  mov     qword ptr [rbp+70h+var_F0], rdi
0x14003ba02  movdqu  [rbp+70h+var_E0], xmm0
0x14003ba07  call    cs:__imp_NtAlpcConnectPort
0x14003ba0d  mov     ebx, eax
0x14003ba0f  test    eax, eax
0x14003ba11  jz      short loc_14003BA5B
0x14003ba13  lea     rdx, aSFailedToConne; "[%s] Failed to connect to PrintSpoolerI"...
0x14003ba1a  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, dil; bool g_bSpoolerIsChildProcess
0x14003ba21  lea     rax, aHost; "Host"
0x14003ba28  lea     r8, aWorker; "Worker"
0x14003ba2f  mov     r9d, ebx
0x14003ba32  cmovz   r8, rax
0x14003ba36  lea     rcx, aSplipcinitiali; "SplIpcInitialize"
0x14003ba3d  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ba42  mov     rcx, cs:?g_IPCCommunicationPortHandle@@3PEAXEA; hObject
0x14003ba49  test    rcx, rcx
0x14003ba4c  jz      short loc_14003BA5B
0x14003ba4e  call    cs:__imp_CloseHandle
0x14003ba54  mov     cs:?g_IPCCommunicationPortHandle@@3PEAXEA, rdi; void * g_IPCCommunicationPortHandle
0x14003ba5b  mov     rcx, [rsp+170h+SecurityDescriptor]; hMem
0x14003ba60  test    rcx, rcx
0x14003ba63  jz      short loc_14003BA6B
0x14003ba65  call    cs:__imp_LocalFree
0x14003ba6b  mov     rcx, [rsp+170h+var_108]; Sid
0x14003ba70  test    rcx, rcx
0x14003ba73  jz      short loc_14003BA7B
0x14003ba75  call    cs:__imp_RtlFreeSid
0x14003ba7b  mov     eax, ebx
0x14003ba7d  mov     rcx, [rbp+70h+var_10]
0x14003ba81  xor     rcx, rsp; StackCookie
0x14003ba84  call    __security_check_cookie
0x14003ba89  lea     r11, [rsp+170h+var_s0]
0x14003ba91  mov     rbx, [r11+10h]
0x14003ba95  mov     rdi, [r11+18h]
0x14003ba99  mov     rsp, r11
0x14003ba9c  pop     rbp
0x14003ba9d  retn
```
