# CreateSensCache(void)

- ea: `0x18000732c`
- end: `0x180007485`
- name: `?CreateSensCache@@YAHXZ`
- size: `345`
- prototype: `int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800079a8`

## callees

- `0x18000732c`
- `0x18000748c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007436`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007478`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007436`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007376`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007461`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007461`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800073f5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800073f5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800073a0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800073a0`

## string_xrefs

- `0x18000737f`: `SENS Information Cache`

## pseudocode

```c
int CreateSensCache(void)
{
  int result; // eax
  int v1; // ebx
  HANDLE v2; // rax
  _OWORD *v3; // rax
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v5[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v6; // [rsp+68h] [rbp-10h]
  LPVOID lpMem; // [rsp+80h] [rbp+8h] BYREF

  memset(v5, 0, sizeof(v5));
  lpMem = 0;
  v6 = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  result = CreateCachePermissions(&FileMappingAttributes, v5, (struct _ACL **)&lpMem);
  v1 = result;
  if ( result )
  {
    EnterCriticalSection(&gSensLock);
    v2 = CreateFileMappingW(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &FileMappingAttributes,
           4u,
           0,
           0x100u,
           L"SENS Information Cache");
    ghSensFileMap = v2;
    if ( lpMem )
    {
      HeapFree(ghSensHeap, 0, lpMem);
      v2 = ghSensFileMap;
    }
    if ( v2 )
    {
      GetLastError();
      v3 = MapViewOfFile(ghSensFileMap, 2u, 0, 0, 0);
      gpSensCache = v3;
      if ( v3 )
      {
        *v3 = 0;
        v3[1] = 0;
        *((_QWORD *)v3 + 4) = 0;
        *(_DWORD *)v3 = 2;
        *((_DWORD *)v3 + 1) = 40;
        *((_DWORD *)gpSensCache + 2) = GetTickCount();
        LeaveCriticalSection(&gSensLock);
        return 1;
      }
      if ( ghSensFileMap )
      {
        CloseHandle(ghSensFileMap);
        ghSensFileMap = 0;
        gpSensCache = 0;
      }
    }
    LeaveCriticalSection(&gSensLock);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x18000732c  mov     r11, rsp
0x18000732f  push    rbx
0x180007330  sub     rsp, 70h
0x180007334  xorps   xmm0, xmm0
0x180007337  lea     r8, [r11+8]; struct _ACL **
0x18000733b  xor     eax, eax
0x18000733d  lea     rdx, [r11-30h]; void *
0x180007341  movups  [rsp+78h+var_30], xmm0
0x180007346  lea     rcx, [r11-48h]; struct _SECURITY_ATTRIBUTES *
0x18000734a  mov     [r11+8], rax
0x18000734e  movups  [rsp+78h+var_20], xmm0
0x180007353  mov     [r11-10h], rax
0x180007357  movups  xmmword ptr [rsp+78h+FileMappingAttributes.nLength], xmm0
0x18000735c  mov     [r11-38h], rax
0x180007360  call    ?CreateCachePermissions@@YAHPEAU_SECURITY_ATTRIBUTES@@PEAXPEAPEAU_ACL@@@Z; CreateCachePermissions(_SECURITY_ATTRIBUTES *,void *,_ACL * *)
0x180007365  mov     ebx, eax
0x180007367  test    eax, eax
0x180007369  jz      loc_18000743E
0x18000736f  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007376  call    cs:__imp_EnterCriticalSection
0x18000737c  xor     r9d, r9d; dwMaximumSizeHigh
0x18000737f  lea     rax, Name; "SENS Information Cache"
0x180007386  mov     [rsp+78h+lpName], rax; lpName
0x18000738b  lea     rdx, [rsp+78h+FileMappingAttributes]; lpFileMappingAttributes
0x180007390  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180007394  mov     [rsp+78h+dwMaximumSizeLow], 100h; dwMaximumSizeLow
0x18000739c  lea     r8d, [r9+4]; flProtect
0x1800073a0  call    cs:__imp_CreateFileMappingW
0x1800073a6  mov     r8, [rsp+78h+lpMem]; lpMem
0x1800073ae  mov     cs:?ghSensFileMap@@3PEAXEA, rax; void * ghSensFileMap
0x1800073b5  test    r8, r8
0x1800073b8  jz      short loc_1800073D0
0x1800073ba  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x1800073c1  xor     edx, edx; dwFlags
0x1800073c3  call    cs:__imp_HeapFree
0x1800073c9  mov     rax, cs:?ghSensFileMap@@3PEAXEA; void * ghSensFileMap
0x1800073d0  test    rax, rax
0x1800073d3  jz      short loc_18000742F
0x1800073d5  call    cs:__imp_GetLastError
0x1800073db  mov     rcx, cs:?ghSensFileMap@@3PEAXEA; hFileMappingObject
0x1800073e2  xor     r9d, r9d; dwFileOffsetLow
0x1800073e5  xor     r8d, r8d; dwFileOffsetHigh
0x1800073e8  mov     qword ptr [rsp+78h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800073f1  lea     edx, [r9+2]; dwDesiredAccess
0x1800073f5  call    cs:__imp_MapViewOfFile
0x1800073fb  mov     cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA, rax; _SENS_CACHE * gpSensCache
0x180007402  test    rax, rax
0x180007405  jnz     short loc_180007444
0x180007407  mov     rcx, cs:?ghSensFileMap@@3PEAXEA; hObject
0x18000740e  test    rcx, rcx
0x180007411  jz      short loc_18000742F
0x180007413  call    cs:__imp_CloseHandle
0x180007419  mov     cs:?ghSensFileMap@@3PEAXEA, 0; void * ghSensFileMap
0x180007424  mov     cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA, 0; _SENS_CACHE * gpSensCache
0x18000742f  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007436  call    cs:__imp_LeaveCriticalSection
0x18000743c  mov     eax, ebx
0x18000743e  add     rsp, 70h
0x180007442  pop     rbx
0x180007443  retn
0x180007444  xorps   xmm0, xmm0
0x180007447  xor     edx, edx
0x180007449  movups  xmmword ptr [rax], xmm0
0x18000744c  movups  xmmword ptr [rax+10h], xmm0
0x180007450  mov     [rax+20h], rdx
0x180007454  mov     dword ptr [rax], 2
0x18000745a  mov     dword ptr [rax+4], 28h ; '('
0x180007461  call    cs:__imp_GetTickCount
0x180007467  mov     rdx, cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA; _SENS_CACHE * gpSensCache
0x18000746e  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007475  mov     [rdx+8], eax
0x180007478  call    cs:__imp_LeaveCriticalSection
0x18000747e  mov     eax, 1
0x180007483  jmp     short loc_18000743E
```
