# SecpReferenceIdpCache

- ea: `0x180010efc`
- end: `0x180011071`
- name: `SecpReferenceIdpCache`
- size: `373`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010c90`
- `0x180010d00`
- `0x180010e20`
- `0x180017a60`

## callees

- `0x180010dc0`
- `0x180010efc`
- `0x180011080`
- `0x18001f940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011064`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010fab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010fab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011059`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010fb8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010fb8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010f7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001100d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010f7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001100d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010f3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010f3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010f5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010f23`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010f23`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180010fe9`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180010fe9`

## pseudocode

```c
__int64 __fastcall SecpReferenceIdpCache(_QWORD *a1)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  DWORD v4; // eax
  __int64 *v5; // rbp
  DWORD LastError; // eax
  unsigned int v7; // eax
  HLOCAL v8; // rcx
  __int64 *v9; // [rsp+48h] [rbp+10h] BYREF

  result = SecpLazyInitIdpCache();
  v3 = result;
  if ( !(_DWORD)result )
  {
    v4 = WaitForSingleObject(g_hIdpCacheChangeEvent, 0);
    if ( v4 )
    {
      if ( v4 == -1 )
      {
        return GetLastError();
      }
      else
      {
        AcquireSRWLockShared(&g_IdpCacheLock);
        _InterlockedIncrement((volatile signed __int32 *)g_pIdpCache + 4);
        *a1 = g_pIdpCache;
        ReleaseSRWLockShared(&g_IdpCacheLock);
      }
    }
    else
    {
      AcquireSRWLockExclusive(&g_IdpCacheLock);
      if ( !g_fUpdatingIdpCache )
      {
        v5 = 0;
        g_fUpdatingIdpCache = 1;
        v9 = 0;
        ReleaseSRWLockExclusive(&g_IdpCacheLock);
        if ( ResetEvent(g_hIdpCacheChangeEvent) )
          LastError = RegNotifyChangeKeyValue(g_hkeyIdpRoot, 1, 5u, g_hIdpCacheChangeEvent, 1);
        else
          LastError = GetLastError();
        v3 = LastError;
        if ( !LastError )
        {
          v7 = SecpLoadIdpCache(&v9);
          v5 = v9;
          v3 = v7;
        }
        AcquireSRWLockExclusive(&g_IdpCacheLock);
        if ( !v3 )
        {
          v8 = g_pIdpCache;
          _InterlockedCompareExchange64(
            (volatile signed __int64 *)&g_pIdpCache,
            (signed __int64)v5,
            (signed __int64)g_pIdpCache);
          SecpReleaseIdpCache(v8);
        }
        g_fUpdatingIdpCache = 0;
      }
      _InterlockedIncrement((volatile signed __int32 *)g_pIdpCache + 4);
      *a1 = g_pIdpCache;
      ReleaseSRWLockExclusive(&g_IdpCacheLock);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180010efc  mov     [rsp+arg_0], rbx
0x180010f01  mov     [rsp+arg_10], rbp
0x180010f06  push    r14
0x180010f08  sub     rsp, 30h
0x180010f0c  mov     r14, rcx
0x180010f0f  call    SecpLazyInitIdpCache
0x180010f14  mov     ebx, eax
0x180010f16  test    eax, eax
0x180010f18  jnz     short loc_180010F67
0x180010f1a  mov     rcx, cs:g_hIdpCacheChangeEvent; hHandle
0x180010f21  xor     edx, edx; dwMilliseconds
0x180010f23  call    cs:__imp_WaitForSingleObject
0x180010f29  test    eax, eax
0x180010f2b  jz      short loc_180010F78
0x180010f2d  cmp     eax, 0FFFFFFFFh
0x180010f30  jz      loc_180011064
0x180010f36  lea     rcx, g_IdpCacheLock; SRWLock
0x180010f3d  call    cs:__imp_AcquireSRWLockShared
0x180010f43  mov     rax, cs:g_pIdpCache
0x180010f4a  lock inc dword ptr [rax+10h]
0x180010f4e  mov     rax, cs:g_pIdpCache
0x180010f55  lea     rcx, g_IdpCacheLock; SRWLock
0x180010f5c  mov     [r14], rax
0x180010f5f  call    cs:__imp_ReleaseSRWLockShared
0x180010f65  mov     eax, ebx
0x180010f67  mov     rbx, [rsp+38h+arg_0]
0x180010f6c  mov     rbp, [rsp+38h+arg_10]
0x180010f71  add     rsp, 30h
0x180010f75  pop     r14
0x180010f77  retn
0x180010f78  lea     rcx, g_IdpCacheLock; SRWLock
0x180010f7f  call    cs:__imp_AcquireSRWLockExclusive
0x180010f85  mov     eax, cs:g_fUpdatingIdpCache
0x180010f8b  test    eax, eax
0x180010f8d  jnz     loc_18001103D
0x180010f93  xor     ebp, ebp
0x180010f95  mov     cs:g_fUpdatingIdpCache, 1
0x180010f9f  lea     rcx, g_IdpCacheLock; SRWLock
0x180010fa6  mov     [rsp+38h+arg_8], rbp
0x180010fab  call    cs:__imp_ReleaseSRWLockExclusive
0x180010fb1  mov     rcx, cs:g_hIdpCacheChangeEvent; hEvent
0x180010fb8  call    cs:__imp_ResetEvent
0x180010fbe  test    eax, eax
0x180010fc0  jnz     short loc_180010FCA
0x180010fc2  call    cs:__imp_GetLastError
0x180010fc8  jmp     short loc_180010FEF
0x180010fca  mov     r9, cs:g_hIdpCacheChangeEvent; hEvent
0x180010fd1  mov     edx, 1; bWatchSubtree
0x180010fd6  mov     rcx, cs:g_hkeyIdpRoot; hKey
0x180010fdd  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x180010fe5  lea     r8d, [rdx+4]; dwNotifyFilter
0x180010fe9  call    cs:__imp_RegNotifyChangeKeyValue
0x180010fef  mov     ebx, eax
0x180010ff1  test    eax, eax
0x180010ff3  jnz     short loc_180011006
0x180010ff5  lea     rcx, [rsp+38h+arg_8]
0x180010ffa  call    SecpLoadIdpCache
0x180010fff  mov     rbp, [rsp+38h+arg_8]
0x180011004  mov     ebx, eax
0x180011006  lea     rcx, g_IdpCacheLock; SRWLock
0x18001100d  call    cs:__imp_AcquireSRWLockExclusive
0x180011013  test    ebx, ebx
0x180011015  jnz     short loc_180011033
0x180011017  mov     rcx, cs:g_pIdpCache; hMem
0x18001101e  mov     rax, cs:g_pIdpCache
0x180011025  lock cmpxchg cs:g_pIdpCache, rbp
0x18001102e  call    SecpReleaseIdpCache
0x180011033  mov     cs:g_fUpdatingIdpCache, 0
0x18001103d  mov     rax, cs:g_pIdpCache
0x180011044  lock inc dword ptr [rax+10h]
0x180011048  mov     rax, cs:g_pIdpCache
0x18001104f  lea     rcx, g_IdpCacheLock; SRWLock
0x180011056  mov     [r14], rax
0x180011059  call    cs:__imp_ReleaseSRWLockExclusive
0x18001105f  jmp     loc_180010F65
0x180011064  call    cs:__imp_GetLastError
0x18001106a  mov     ebx, eax
0x18001106c  jmp     loc_180010F65
```
