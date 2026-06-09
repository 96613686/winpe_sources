# InitializeWaits(void)

- ea: `0x180105e50`
- end: `0x180105f7f`
- name: `?InitializeWaits@@YAJXZ`
- size: `303`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800f7900`

## callees

- `0x180105e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105f51`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180105eb8`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180105eb8`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180105f32`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180105f32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105e92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105e92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180105ece`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180105ece`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180105eef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180105eef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180105f0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180105f0d`

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
0x180105e50  mov     [rsp+arg_0], rbx
0x180105e55  mov     [rsp+arg_8], rsi
0x180105e5a  push    rdi
0x180105e5b  sub     rsp, 30h
0x180105e5f  xor     ebx, ebx
0x180105e61  lea     rdi, ?g_TrackRegistry@@3PAUTrackRegistry@@A; TrackRegistry near * g_TrackRegistry
0x180105e68  lea     rax, ?gScmActivator@@3VCScmActivator@@A; CScmActivator gScmActivator
0x180105e6f  cmp     rdi, rax
0x180105e72  jz      loc_180105F6C
0x180105e78  mov     rdx, [rdi+18h]; lpSubKey
0x180105e7c  lea     rsi, [rdi+20h]
0x180105e80  mov     rcx, [rdi+10h]; hKey
0x180105e84  mov     r9d, 10h; samDesired
0x180105e8a  xor     r8d, r8d; ulOptions
0x180105e8d  mov     [rsp+38h+phkResult], rsi; phkResult
0x180105e92  call    cs:__imp_RegOpenKeyExW
0x180105e99  nop     dword ptr [rax+rax+00h]
0x180105e9e  cmp     eax, 2
0x180105ea1  jz      loc_180105F42
0x180105ea7  test    eax, eax
0x180105ea9  jnz     loc_180105F51
0x180105eaf  mov     rcx, [rsi]; hObject
0x180105eb2  lea     edx, [rax+2]; dwMask
0x180105eb5  mov     r8d, edx; dwFlags
0x180105eb8  call    cs:__imp_SetHandleInformation
0x180105ebf  nop     dword ptr [rax+rax+00h]
0x180105ec4  xor     r9d, r9d; lpName
0x180105ec7  xor     r8d, r8d; bInitialState
0x180105eca  xor     edx, edx; bManualReset
0x180105ecc  xor     ecx, ecx; lpEventAttributes
0x180105ece  call    cs:__imp_CreateEventW
0x180105ed5  nop     dword ptr [rax+rax+00h]
0x180105eda  mov     [rdi], rax
0x180105edd  test    rax, rax
0x180105ee0  jz      short loc_180105F51
0x180105ee2  xor     r8d, r8d; pcbe
0x180105ee5  lea     rcx, ?RegistryChanged@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180105eec  mov     rdx, rdi; pv
0x180105eef  call    cs:__imp_CreateThreadpoolWait
0x180105ef6  nop     dword ptr [rax+rax+00h]
0x180105efb  mov     [rdi+8], rax
0x180105eff  test    rax, rax
0x180105f02  jz      short loc_180105F51
0x180105f04  mov     rdx, [rdi]; h
0x180105f07  xor     r8d, r8d; pftTimeout
0x180105f0a  mov     rcx, rax; pwa
0x180105f0d  call    cs:__imp_SetThreadpoolWait
0x180105f14  nop     dword ptr [rax+rax+00h]
0x180105f19  mov     r9, [rdi]; hEvent
0x180105f1c  mov     edx, 1; bWatchSubtree
0x180105f21  mov     rcx, [rsi]; hKey
0x180105f24  mov     r8d, 10000005h; dwNotifyFilter
0x180105f2a  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x180105f32  call    cs:__imp_RegNotifyChangeKeyValue
0x180105f39  nop     dword ptr [rax+rax+00h]
0x180105f3e  test    eax, eax
0x180105f40  jnz     short loc_180105F4B
0x180105f42  add     rdi, 30h ; '0'
0x180105f46  jmp     loc_180105E68
0x180105f4b  jg      short loc_180105F63
0x180105f4d  mov     ebx, eax
0x180105f4f  jmp     short loc_180105F6C
0x180105f51  call    cs:__imp_GetLastError
0x180105f58  nop     dword ptr [rax+rax+00h]
0x180105f5d  mov     ebx, eax
0x180105f5f  test    eax, eax
0x180105f61  jle     short loc_180105F6C
0x180105f63  movzx   ebx, ax
0x180105f66  or      ebx, 80070000h
0x180105f6c  mov     rsi, [rsp+38h+arg_8]
0x180105f71  mov     eax, ebx
0x180105f73  mov     rbx, [rsp+38h+arg_0]
0x180105f78  add     rsp, 30h
0x180105f7c  pop     rdi
0x180105f7d  retn
```
