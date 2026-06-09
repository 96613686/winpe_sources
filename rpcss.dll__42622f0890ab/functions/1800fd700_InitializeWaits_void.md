# InitializeWaits(void)

- ea: `0x1800fd700`
- end: `0x1800fd800`
- name: `?InitializeWaits@@YAJXZ`
- size: `256`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800efc7c`

## callees

- `0x1800fd700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd7d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd7d9`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x1800fd75e`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x1800fd75e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800fd7c0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800fd7c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd742`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd742`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fd76e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fd76e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800fd789`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800fd789`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800fd7a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800fd7a1`

## pseudocode

```c
__int64 InitializeWaits(void)
{
  unsigned int v0; // ebx
  struct TrackRegistry near **i; // rdi
  HANDLE *v2; // rsi
  LSTATUS v3; // eax
  struct TrackRegistry *EventW; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  int LastError; // eax

  v0 = 0;
  for ( i = &g_TrackRegistry; i != (struct TrackRegistry near **)&gScmActivator; i += 6 )
  {
    v2 = (HANDLE *)(i + 4);
    v3 = RegOpenKeyExW((HKEY)i[2], (LPCWSTR)i[3], 0, 0x10u, (PHKEY)i + 4);
    if ( v3 != 2 )
    {
      if ( v3
        || (SetHandleInformation(*v2, 2u, 2u),
            EventW = (struct TrackRegistry *)CreateEventW(0, 0, 0, 0),
            (*i = EventW) == 0)
        || (ThreadpoolWait = CreateThreadpoolWait(RegistryChanged, i, 0), (i[1] = ThreadpoolWait) == 0) )
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError <= 0 )
          return v0;
        return (unsigned __int16)LastError | 0x80070000;
      }
      SetThreadpoolWait(ThreadpoolWait, *i, 0);
      LastError = RegNotifyChangeKeyValue((HKEY)*v2, 1, 0x10000005u, *i, 1);
      if ( LastError )
      {
        if ( LastError <= 0 )
          return (unsigned int)LastError;
        return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800fd700  mov     [rsp+arg_0], rbx
0x1800fd705  mov     [rsp+arg_8], rsi
0x1800fd70a  push    rdi
0x1800fd70b  sub     rsp, 30h
0x1800fd70f  xor     ebx, ebx
0x1800fd711  lea     rdi, ?g_TrackRegistry@@3PAUTrackRegistry@@A; TrackRegistry near * g_TrackRegistry
0x1800fd718  lea     rax, ?gScmActivator@@3VCScmActivator@@A; CScmActivator gScmActivator
0x1800fd71f  cmp     rdi, rax
0x1800fd722  jz      loc_1800FD7EE
0x1800fd728  mov     rdx, [rdi+18h]; lpSubKey
0x1800fd72c  lea     rsi, [rdi+20h]
0x1800fd730  mov     rcx, [rdi+10h]; hKey
0x1800fd734  mov     r9d, 10h; samDesired
0x1800fd73a  xor     r8d, r8d; ulOptions
0x1800fd73d  mov     [rsp+38h+phkResult], rsi; phkResult
0x1800fd742  call    cs:__imp_RegOpenKeyExW
0x1800fd748  cmp     eax, 2
0x1800fd74b  jz      short loc_1800FD7CA
0x1800fd74d  test    eax, eax
0x1800fd74f  jnz     loc_1800FD7D9
0x1800fd755  mov     rcx, [rsi]; hObject
0x1800fd758  lea     edx, [rax+2]; dwMask
0x1800fd75b  mov     r8d, edx; dwFlags
0x1800fd75e  call    cs:__imp_SetHandleInformation
0x1800fd764  xor     r9d, r9d; lpName
0x1800fd767  xor     r8d, r8d; bInitialState
0x1800fd76a  xor     edx, edx; bManualReset
0x1800fd76c  xor     ecx, ecx; lpEventAttributes
0x1800fd76e  call    cs:__imp_CreateEventW
0x1800fd774  mov     [rdi], rax
0x1800fd777  test    rax, rax
0x1800fd77a  jz      short loc_1800FD7D9
0x1800fd77c  xor     r8d, r8d; pcbe
0x1800fd77f  lea     rcx, ?RegistryChanged@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800fd786  mov     rdx, rdi; pv
0x1800fd789  call    cs:__imp_CreateThreadpoolWait
0x1800fd78f  mov     [rdi+8], rax
0x1800fd793  test    rax, rax
0x1800fd796  jz      short loc_1800FD7D9
0x1800fd798  mov     rdx, [rdi]; h
0x1800fd79b  xor     r8d, r8d; pftTimeout
0x1800fd79e  mov     rcx, rax; pwa
0x1800fd7a1  call    cs:__imp_SetThreadpoolWait
0x1800fd7a7  mov     r9, [rdi]; hEvent
0x1800fd7aa  mov     edx, 1; bWatchSubtree
0x1800fd7af  mov     rcx, [rsi]; hKey
0x1800fd7b2  mov     r8d, 10000005h; dwNotifyFilter
0x1800fd7b8  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x1800fd7c0  call    cs:__imp_RegNotifyChangeKeyValue
0x1800fd7c6  test    eax, eax
0x1800fd7c8  jnz     short loc_1800FD7D3
0x1800fd7ca  add     rdi, 30h ; '0'
0x1800fd7ce  jmp     loc_1800FD718
0x1800fd7d3  jg      short loc_1800FD7E5
0x1800fd7d5  mov     ebx, eax
0x1800fd7d7  jmp     short loc_1800FD7EE
0x1800fd7d9  call    cs:__imp_GetLastError
0x1800fd7df  mov     ebx, eax
0x1800fd7e1  test    eax, eax
0x1800fd7e3  jle     short loc_1800FD7EE
0x1800fd7e5  movzx   ebx, ax
0x1800fd7e8  or      ebx, 80070000h
0x1800fd7ee  mov     rsi, [rsp+38h+arg_8]
0x1800fd7f3  mov     eax, ebx
0x1800fd7f5  mov     rbx, [rsp+38h+arg_0]
0x1800fd7fa  add     rsp, 30h
0x1800fd7fe  pop     rdi
0x1800fd7ff  retn
```
