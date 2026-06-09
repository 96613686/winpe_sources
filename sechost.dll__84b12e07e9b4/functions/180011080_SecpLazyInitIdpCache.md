# SecpLazyInitIdpCache

- ea: `0x180011080`
- end: `0x1800111e0`
- name: `SecpLazyInitIdpCache`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010efc`

## callees

- `0x180011080`
- `0x18001f940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011165`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011165`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800111d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800111d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011116`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011116`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800110b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800110b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110f9`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001114d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001114d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001117d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001117d`

## pseudocode

```c
__int64 SecpLazyInitIdpCache()
{
  unsigned int v0; // ebx
  LSTATUS v2; // eax
  HANDLE EventW; // rax
  DWORD v4; // eax
  void *v5; // [rsp+40h] [rbp+8h] BYREF

  if ( !g_fNoSupportForIdp )
  {
    v0 = 0;
    if ( g_pIdpCache )
      return v0;
    AcquireSRWLockExclusive(&g_IdpCacheLock);
    if ( !g_pIdpCache )
    {
      if ( g_hkeyIdpRoot )
        goto LABEL_17;
      v2 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\IdentityStore\\Providers",
             0,
             0x20019u,
             &g_hkeyIdpRoot);
      v0 = v2;
      if ( v2 )
      {
        if ( (unsigned int)(v2 - 2) <= 1 )
        {
          v0 = 50;
          g_fNoSupportForIdp = 1;
        }
        goto LABEL_19;
      }
      EventW = CreateEventW(0, 1, 0, 0);
      g_hIdpCacheChangeEvent = EventW;
      v4 = EventW ? RegNotifyChangeKeyValue(g_hkeyIdpRoot, 1, 5u, EventW, 1) : GetLastError();
      v0 = v4;
      if ( !v4 )
      {
LABEL_17:
        v5 = 0;
        v0 = SecpLoadIdpCache(&v5);
        if ( !v0 )
          g_pIdpCache = v5;
      }
      else
      {
        if ( g_hIdpCacheChangeEvent )
        {
          CloseHandle(g_hIdpCacheChangeEvent);
          g_hIdpCacheChangeEvent = 0;
        }
        RegCloseKey(g_hkeyIdpRoot);
        g_hkeyIdpRoot = 0;
      }
    }
LABEL_19:
    ReleaseSRWLockExclusive(&g_IdpCacheLock);
    return v0;
  }
  return 50;
}

```

## disassembly

```asm
0x180011080  push    rbx
0x180011082  sub     rsp, 30h
0x180011086  cmp     cs:g_fNoSupportForIdp, 0
0x18001108d  jnz     short loc_1800110A5
0x18001108f  mov     rax, cs:g_pIdpCache
0x180011096  xor     ebx, ebx
0x180011098  test    rax, rax
0x18001109b  jz      short loc_1800110AC
0x18001109d  mov     eax, ebx
0x18001109f  add     rsp, 30h
0x1800110a3  pop     rbx
0x1800110a4  retn
0x1800110a5  mov     eax, 32h ; '2'
0x1800110aa  jmp     short loc_18001109F
0x1800110ac  lea     rcx, g_IdpCacheLock; SRWLock
0x1800110b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800110b9  mov     rax, cs:g_pIdpCache
0x1800110c0  test    rax, rax
0x1800110c3  jnz     loc_1800111CE
0x1800110c9  cmp     cs:g_hkeyIdpRoot, rbx
0x1800110d0  jnz     loc_1800111A9
0x1800110d6  lea     rax, g_hkeyIdpRoot
0x1800110dd  mov     r9d, 20019h; samDesired
0x1800110e3  xor     r8d, r8d; ulOptions
0x1800110e6  mov     [rsp+38h+phkResult], rax; phkResult
0x1800110eb  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\IdentityStore\\Pro"...
0x1800110f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800110f9  call    cs:__imp_RegOpenKeyExW
0x1800110ff  mov     ebx, eax
0x180011101  test    eax, eax
0x180011103  jnz     loc_180011190
0x180011109  xor     r9d, r9d; lpName
0x18001110c  xor     r8d, r8d; bInitialState
0x18001110f  mov     edx, 1; bManualReset
0x180011114  xor     ecx, ecx; lpEventAttributes
0x180011116  call    cs:__imp_CreateEventW
0x18001111c  mov     cs:g_hIdpCacheChangeEvent, rax
0x180011123  test    rax, rax
0x180011126  jnz     short loc_180011130
0x180011128  call    cs:__imp_GetLastError
0x18001112e  jmp     short loc_180011153
0x180011130  mov     rcx, cs:g_hkeyIdpRoot; hKey
0x180011137  mov     r9, rax; hEvent
0x18001113a  mov     edx, 1; bWatchSubtree
0x18001113f  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x180011147  mov     r8d, 5; dwNotifyFilter
0x18001114d  call    cs:__imp_RegNotifyChangeKeyValue
0x180011153  mov     ebx, eax
0x180011155  test    eax, eax
0x180011157  jz      short loc_1800111A9
0x180011159  mov     rcx, cs:g_hIdpCacheChangeEvent; hObject
0x180011160  test    rcx, rcx
0x180011163  jz      short loc_180011176
0x180011165  call    cs:__imp_CloseHandle
0x18001116b  mov     cs:g_hIdpCacheChangeEvent, 0
0x180011176  mov     rcx, cs:g_hkeyIdpRoot; hKey
0x18001117d  call    cs:__imp_RegCloseKey
0x180011183  mov     cs:g_hkeyIdpRoot, 0
0x18001118e  jmp     short loc_1800111CE
0x180011190  add     eax, 0FFFFFFFEh
0x180011193  cmp     eax, 1
0x180011196  ja      short loc_1800111CE
0x180011198  mov     ebx, 32h ; '2'
0x18001119d  mov     cs:g_fNoSupportForIdp, 1
0x1800111a7  jmp     short loc_1800111CE
0x1800111a9  lea     rcx, [rsp+38h+arg_0]
0x1800111ae  mov     [rsp+38h+arg_0], 0
0x1800111b7  call    SecpLoadIdpCache
0x1800111bc  mov     ebx, eax
0x1800111be  test    eax, eax
0x1800111c0  jnz     short loc_1800111CE
0x1800111c2  mov     rax, [rsp+38h+arg_0]
0x1800111c7  mov     cs:g_pIdpCache, rax
0x1800111ce  lea     rcx, g_IdpCacheLock; SRWLock
0x1800111d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800111db  jmp     loc_18001109D
```
