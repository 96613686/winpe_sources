# WP_IPM::Initialize(ushort *)

- ea: `0x180008128`
- end: `0x180008347`
- name: `?Initialize@WP_IPM@@QEAAJPEAG@Z`
- size: `543`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000561c`

## callees

- `0x180001890`
- `0x180008128`
- `0x180008c0c`
- `0x180008cfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008269`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800081fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008254`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800081fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008254`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008307`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008307`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800081e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800081e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008183`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008183`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800081c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800081c2`
- `iisutil!?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x1800082f5`
- `iisutil!?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x1800082f5`
- `iisutil!PuDbgPrint` at `0x1800082b8`
- `iisutil!PuDbgPrint` at `0x1800082b8`

## string_xrefs

- `0x180008175`: `System\CurrentControlSet\Services\W3SVC\Performance`
- `0x180008239`: `Failed to create shutdown event.  hr = %x\n`
- `0x1800082ac`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x18000828d`: `Failed to create InitComplete event.  hr = %x\n`

## pseudocode

```c
__int64 __fastcall WP_IPM::Initialize(WP_IPM *this, unsigned __int16 *a2)
{
  W3WP_HOST *v2; // rax
  BYTE *v3; // rbx
  HANDLE EventA; // rax
  signed int v7; // eax
  signed int IpmMessagePipe; // ebx
  const char *v9; // rax
  __int64 v10; // r8
  HANDLE v11; // rax
  signed int LastError; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-30h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD CurrentProcessId; // [rsp+78h] [rbp+20h] BYREF

  v2 = g_pW3WPHost;
  v3 = (BYTE *)this + 52;
  *((_DWORD *)this + 13) = 0;
  hKey = 0;
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 39) + 88LL)
    && !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\W3SVC\\Performance",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"RaiseExceptionOnOrphaning", 0, &Type, v3, &cbData) || Type != 4 )
      *(_DWORD *)v3 = 0;
    RegCloseKey(hKey);
  }
  EventA = CreateEventA(0, 1, 0, 0);
  *((_QWORD *)this + 2) = EventA;
  if ( EventA )
  {
    v11 = CreateEventA(0, 1, 0, 0);
    *((_QWORD *)this + 3) = v11;
    if ( v11 )
    {
      if ( a2 )
      {
        IpmMessagePipe = IPM_MESSAGE_PIPE::CreateIpmMessagePipe(this, a2, 0, 0, (struct IPM_MESSAGE_PIPE **)this + 1);
        if ( IpmMessagePipe < 0 )
          goto LABEL_19;
      }
      CurrentProcessId = GetCurrentProcessId();
      IpmMessagePipe = WP_IPM::WriteMessage(this, 10, 4, &CurrentProcessId);
      if ( IpmMessagePipe < 0 )
        goto LABEL_19;
      if ( a2 )
        WP_IPM::SetupCounters(this, 1);
      return (unsigned int)IpmMessagePipe;
    }
    LastError = GetLastError();
    IpmMessagePipe = LastError;
    if ( LastError > 0 )
      IpmMessagePipe = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = "Failed to create InitComplete event.  hr = %x\n";
      v10 = 115;
      goto LABEL_17;
    }
  }
  else
  {
    v7 = GetLastError();
    IpmMessagePipe = v7;
    if ( v7 > 0 )
      IpmMessagePipe = (unsigned __int16)v7 | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = "Failed to create shutdown event.  hr = %x\n";
      v10 = 95;
LABEL_17:
      LODWORD(lpcbData) = IpmMessagePipe;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        v10,
        "WP_IPM::Initialize",
        v9,
        lpcbData);
    }
  }
  if ( IpmMessagePipe < 0 )
LABEL_19:
    WP_IPM::Terminate(this);
  return (unsigned int)IpmMessagePipe;
}

```

## disassembly

```asm
0x180008128  push    rbx
0x18000812a  push    rsi
0x18000812b  push    rdi
0x18000812c  sub     rsp, 40h
0x180008130  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008137  lea     rbx, [rcx+34h]
0x18000813b  mov     dword ptr [rbx], 0
0x180008141  mov     rsi, rdx
0x180008144  mov     [rsp+58h+hKey], 0
0x18000814d  mov     rdi, rcx
0x180008150  mov     r8, [rax+138h]
0x180008157  cmp     dword ptr [r8+58h], 0
0x18000815c  jnz     loc_1800081F0
0x180008162  lea     rax, [rsp+58h+hKey]
0x180008167  mov     r9d, 20019h; samDesired
0x18000816d  xor     r8d, r8d; ulOptions
0x180008170  mov     [rsp+58h+phkResult], rax; phkResult
0x180008175  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18000817c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008183  call    cs:__imp_RegOpenKeyExW
0x18000818a  nop     dword ptr [rax+rax+00h]
0x18000818f  test    eax, eax
0x180008191  jnz     short loc_1800081F0
0x180008193  mov     rcx, [rsp+58h+hKey]; hKey
0x180008198  lea     r9, [rsp+58h+Type]; lpType
0x18000819d  mov     [rsp+58h+Type], eax
0x1800081a1  lea     rdx, aRaiseexception; "RaiseExceptionOnOrphaning"
0x1800081a8  lea     rax, [rsp+58h+cbData]
0x1800081ad  mov     [rsp+58h+cbData], 4
0x1800081b5  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800081ba  xor     r8d, r8d; lpReserved
0x1800081bd  mov     [rsp+58h+phkResult], rbx; lpData
0x1800081c2  call    cs:__imp_RegQueryValueExW
0x1800081c9  nop     dword ptr [rax+rax+00h]
0x1800081ce  test    eax, eax
0x1800081d0  jnz     short loc_1800081D9
0x1800081d2  cmp     [rsp+58h+Type], 4
0x1800081d7  jz      short loc_1800081DF
0x1800081d9  mov     dword ptr [rbx], 0
0x1800081df  mov     rcx, [rsp+58h+hKey]; hKey
0x1800081e4  call    cs:__imp_RegCloseKey
0x1800081eb  nop     dword ptr [rax+rax+00h]
0x1800081f0  xor     r9d, r9d; lpName
0x1800081f3  xor     r8d, r8d; bInitialState
0x1800081f6  xor     ecx, ecx; lpEventAttributes
0x1800081f8  lea     edx, [r9+1]; bManualReset
0x1800081fc  call    cs:__imp_CreateEventA
0x180008203  nop     dword ptr [rax+rax+00h]
0x180008208  mov     [rdi+10h], rax
0x18000820c  test    rax, rax
0x18000820f  jnz     short loc_180008248
0x180008211  call    cs:__imp_GetLastError
0x180008218  nop     dword ptr [rax+rax+00h]
0x18000821d  mov     ebx, eax
0x18000821f  test    eax, eax
0x180008221  jle     short loc_18000822C
0x180008223  movzx   ebx, ax
0x180008226  or      ebx, 80070000h
0x18000822c  test    byte ptr cs:g_dwDebugFlags, 3
0x180008233  jz      loc_1800082C4
0x180008239  lea     rax, aFailedToCreate_3; "Failed to create shutdown event.  hr = "...
0x180008240  mov     r8d, 5Fh ; '_'
0x180008246  jmp     short loc_18000829A
0x180008248  xor     r9d, r9d; lpName
0x18000824b  xor     r8d, r8d; bInitialState
0x18000824e  xor     ecx, ecx; lpEventAttributes
0x180008250  lea     edx, [r9+1]; bManualReset
0x180008254  call    cs:__imp_CreateEventA
0x18000825b  nop     dword ptr [rax+rax+00h]
0x180008260  mov     [rdi+18h], rax
0x180008264  test    rax, rax
0x180008267  jnz     short loc_1800082DB
0x180008269  call    cs:__imp_GetLastError
0x180008270  nop     dword ptr [rax+rax+00h]
0x180008275  mov     ebx, eax
0x180008277  test    eax, eax
0x180008279  jle     short loc_180008284
0x18000827b  movzx   ebx, ax
0x18000827e  or      ebx, 80070000h
0x180008284  test    byte ptr cs:g_dwDebugFlags, 3
0x18000828b  jz      short loc_1800082C4
0x18000828d  lea     rax, aFailedToCreate_0; "Failed to create InitComplete event.  h"...
0x180008294  mov     r8d, 73h ; 's'
0x18000829a  mov     rcx, cs:g_pDebug
0x1800082a1  lea     r9, aWpIpmInitializ; "WP_IPM::Initialize"
0x1800082a8  mov     dword ptr [rsp+58h+lpcbData], ebx
0x1800082ac  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800082b3  mov     [rsp+58h+phkResult], rax
0x1800082b8  call    cs:__imp_PuDbgPrint
0x1800082bf  nop     dword ptr [rax+rax+00h]
0x1800082c4  test    ebx, ebx
0x1800082c6  jns     short loc_1800082D0
0x1800082c8  mov     rcx, rdi; this
0x1800082cb  call    ?Terminate@WP_IPM@@QEAAJXZ; WP_IPM::Terminate(void)
0x1800082d0  mov     eax, ebx
0x1800082d2  add     rsp, 40h
0x1800082d6  pop     rdi
0x1800082d7  pop     rsi
0x1800082d8  pop     rbx
0x1800082d9  retn
0x1800082db  test    rsi, rsi
0x1800082de  jz      short loc_180008307
0x1800082e0  lea     rax, [rdi+8]
0x1800082e4  xor     r9d, r9d
0x1800082e7  xor     r8d, r8d
0x1800082ea  mov     [rsp+58h+phkResult], rax
0x1800082ef  mov     rdx, rsi
0x1800082f2  mov     rcx, rdi
0x1800082f5  call    cs:__imp_?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z; IPM_MESSAGE_PIPE::CreateIpmMessagePipe(IPM_MESSAGE_ACCEPTOR *,ushort const *,int,_SECURITY_ATTRIBUTES *,IPM_MESSAGE_PIPE * *)
0x1800082fc  nop     dword ptr [rax+rax+00h]
0x180008301  mov     ebx, eax
0x180008303  test    eax, eax
0x180008305  js      short loc_1800082C8
0x180008307  call    cs:__imp_GetCurrentProcessId
0x18000830e  nop     dword ptr [rax+rax+00h]
0x180008313  mov     edx, 0Ah
0x180008318  lea     r9, [rsp+58h+arg_18]
0x18000831d  mov     rcx, rdi
0x180008320  mov     [rsp+58h+arg_18], eax
0x180008324  lea     r8d, [rdx-6]
0x180008328  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x18000832d  mov     ebx, eax
0x18000832f  test    eax, eax
0x180008331  js      short loc_1800082C8
0x180008333  test    rsi, rsi
0x180008336  jz      short loc_1800082D0
0x180008338  mov     edx, 1; int
0x18000833d  mov     rcx, rdi; this
0x180008340  call    ?SetupCounters@WP_IPM@@AEAAXH@Z; WP_IPM::SetupCounters(int)
0x180008345  jmp     short loc_1800082D0
```
