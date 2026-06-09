# WP_IPM::Initialize(ushort *)

- ea: `0x180007958`
- end: `0x180007b32`
- name: `?Initialize@WP_IPM@@QEAAJPEAG@Z`
- size: `474`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800051dc`

## callees

- `0x180001830`
- `0x180007958`
- `0x18000831c`
- `0x18000840c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180007a16`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180007a5e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180007a16`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180007a5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007af8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007af8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800079e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800079e8`
- `iisutil!?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x180007aec`
- `iisutil!?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x180007aec`
- `iisutil!PuDbgPrint` at `0x180007ab6`
- `iisutil!PuDbgPrint` at `0x180007ab6`

## string_xrefs

- `0x1800079a1`: `System\CurrentControlSet\Services\W3SVC\Performance`
- `0x180007a43`: `Failed to create shutdown event.  hr = %x\n`
- `0x180007aaa`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180007a8b`: `Failed to create InitComplete event.  hr = %x\n`

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
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        v10,
        "WP_IPM::Initialize",
        v9,
        IpmMessagePipe);
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
0x180007958  push    rbx
0x18000795a  push    rsi
0x18000795b  push    rdi
0x18000795c  sub     rsp, 40h
0x180007960  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180007967  lea     rbx, [rcx+34h]
0x18000796b  mov     dword ptr [rbx], 0
0x180007971  mov     rsi, rdx
0x180007974  mov     [rsp+58h+hKey], 0
0x18000797d  mov     rdi, rcx
0x180007980  mov     r8, [rax+138h]
0x180007987  cmp     dword ptr [r8+58h], 0
0x18000798c  jnz     short loc_180007A0A
0x18000798e  lea     rax, [rsp+58h+hKey]
0x180007993  mov     r9d, 20019h; samDesired
0x180007999  xor     r8d, r8d; ulOptions
0x18000799c  mov     [rsp+58h+phkResult], rax; phkResult
0x1800079a1  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x1800079a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800079af  call    cs:__imp_RegOpenKeyExW
0x1800079b5  test    eax, eax
0x1800079b7  jnz     short loc_180007A0A
0x1800079b9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800079be  lea     r9, [rsp+58h+Type]; lpType
0x1800079c3  mov     [rsp+58h+Type], eax
0x1800079c7  lea     rdx, aRaiseexception; "RaiseExceptionOnOrphaning"
0x1800079ce  lea     rax, [rsp+58h+cbData]
0x1800079d3  mov     [rsp+58h+cbData], 4
0x1800079db  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800079e0  xor     r8d, r8d; lpReserved
0x1800079e3  mov     [rsp+58h+phkResult], rbx; lpData
0x1800079e8  call    cs:__imp_RegQueryValueExW
0x1800079ee  test    eax, eax
0x1800079f0  jnz     short loc_1800079F9
0x1800079f2  cmp     [rsp+58h+Type], 4
0x1800079f7  jz      short loc_1800079FF
0x1800079f9  mov     dword ptr [rbx], 0
0x1800079ff  mov     rcx, [rsp+58h+hKey]; hKey
0x180007a04  call    cs:__imp_RegCloseKey
0x180007a0a  xor     r9d, r9d; lpName
0x180007a0d  xor     r8d, r8d; bInitialState
0x180007a10  xor     ecx, ecx; lpEventAttributes
0x180007a12  lea     edx, [r9+1]; bManualReset
0x180007a16  call    cs:__imp_CreateEventA
0x180007a1c  mov     [rdi+10h], rax
0x180007a20  test    rax, rax
0x180007a23  jnz     short loc_180007A52
0x180007a25  call    cs:__imp_GetLastError
0x180007a2b  mov     ebx, eax
0x180007a2d  test    eax, eax
0x180007a2f  jle     short loc_180007A3A
0x180007a31  movzx   ebx, ax
0x180007a34  or      ebx, 80070000h
0x180007a3a  test    byte ptr cs:g_dwDebugFlags, 3
0x180007a41  jz      short loc_180007ABC
0x180007a43  lea     rax, aFailedToCreate_3; "Failed to create shutdown event.  hr = "...
0x180007a4a  mov     r8d, 5Fh ; '_'
0x180007a50  jmp     short loc_180007A98
0x180007a52  xor     r9d, r9d; lpName
0x180007a55  xor     r8d, r8d; bInitialState
0x180007a58  xor     ecx, ecx; lpEventAttributes
0x180007a5a  lea     edx, [r9+1]; bManualReset
0x180007a5e  call    cs:__imp_CreateEventA
0x180007a64  mov     [rdi+18h], rax
0x180007a68  test    rax, rax
0x180007a6b  jnz     short loc_180007AD2
0x180007a6d  call    cs:__imp_GetLastError
0x180007a73  mov     ebx, eax
0x180007a75  test    eax, eax
0x180007a77  jle     short loc_180007A82
0x180007a79  movzx   ebx, ax
0x180007a7c  or      ebx, 80070000h
0x180007a82  test    byte ptr cs:g_dwDebugFlags, 3
0x180007a89  jz      short loc_180007ABC
0x180007a8b  lea     rax, aFailedToCreate_0; "Failed to create InitComplete event.  h"...
0x180007a92  mov     r8d, 73h ; 's'
0x180007a98  mov     rcx, cs:g_pDebug
0x180007a9f  lea     r9, aWpIpmInitializ; "WP_IPM::Initialize"
0x180007aa6  mov     dword ptr [rsp+58h+lpcbData], ebx
0x180007aaa  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007ab1  mov     [rsp+58h+phkResult], rax
0x180007ab6  call    cs:__imp_PuDbgPrint
0x180007abc  test    ebx, ebx
0x180007abe  jns     short loc_180007AC8
0x180007ac0  mov     rcx, rdi; this
0x180007ac3  call    ?Terminate@WP_IPM@@QEAAJXZ; WP_IPM::Terminate(void)
0x180007ac8  mov     eax, ebx
0x180007aca  add     rsp, 40h
0x180007ace  pop     rdi
0x180007acf  pop     rsi
0x180007ad0  pop     rbx
0x180007ad1  retn
0x180007ad2  test    rsi, rsi
0x180007ad5  jz      short loc_180007AF8
0x180007ad7  lea     rax, [rdi+8]
0x180007adb  xor     r9d, r9d
0x180007ade  xor     r8d, r8d
0x180007ae1  mov     [rsp+58h+phkResult], rax
0x180007ae6  mov     rdx, rsi
0x180007ae9  mov     rcx, rdi
0x180007aec  call    cs:__imp_?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z; IPM_MESSAGE_PIPE::CreateIpmMessagePipe(IPM_MESSAGE_ACCEPTOR *,ushort const *,int,_SECURITY_ATTRIBUTES *,IPM_MESSAGE_PIPE * *)
0x180007af2  mov     ebx, eax
0x180007af4  test    eax, eax
0x180007af6  js      short loc_180007AC0
0x180007af8  call    cs:__imp_GetCurrentProcessId
0x180007afe  mov     edx, 0Ah
0x180007b03  lea     r9, [rsp+58h+arg_18]
0x180007b08  mov     rcx, rdi
0x180007b0b  mov     [rsp+58h+arg_18], eax
0x180007b0f  lea     r8d, [rdx-6]
0x180007b13  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180007b18  mov     ebx, eax
0x180007b1a  test    eax, eax
0x180007b1c  js      short loc_180007AC0
0x180007b1e  test    rsi, rsi
0x180007b21  jz      short loc_180007AC8
0x180007b23  mov     edx, 1; int
0x180007b28  mov     rcx, rdi; this
0x180007b2b  call    ?SetupCounters@WP_IPM@@AEAAXH@Z; WP_IPM::SetupCounters(int)
0x180007b30  jmp     short loc_180007AC8
```
