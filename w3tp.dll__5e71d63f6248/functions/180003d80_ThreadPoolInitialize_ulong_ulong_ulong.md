# ThreadPoolInitialize(ulong,ulong,ulong)

- ea: `0x180003d80`
- end: `0x180003eb6`
- name: `?ThreadPoolInitialize@@YAJKKK@Z`
- size: `310`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800037c0`
- `0x180003878`
- `0x180003950`
- `0x180003a80`
- `0x180003d80`
- `0x180003fb0`
- `0x1800041a6`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e37`
- `iisutil!PuDbgPrint` at `0x180003dca`
- `iisutil!PuDbgPrint` at `0x180003dca`

## string_xrefs

- `0x180003daa`: `W3TP: ThreadPoolInitialize() already called\n`
- `0x180003db1`: `ThreadPoolInitialize`
- `0x180003dc3`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_functions.cxx`
- `0x180003dfe`: `System\CurrentControlSet\Services\InetInfo\Parameters`
- `0x180003e6b`: `System\CurrentControlSet\Services\InetInfo\Parameters`
- `0x180003e1e`: `ThreadPoolType`

## pseudocode

```c
__int64 __fastcall ThreadPoolInitialize(unsigned int a1, int a2)
{
  unsigned int RegDword; // ebx
  int v4; // ecx
  int ThreadPool; // eax
  _BYTE v7[40]; // [rsp+30h] [rbp-68h] BYREF
  int v8; // [rsp+58h] [rbp-40h]
  HKEY hKey; // [rsp+B8h] [rbp+20h] BYREF

  RegDword = a1;
  if ( _InterlockedIncrement(&g_cInitializeCount) )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_functions.cxx",
        139,
        "ThreadPoolInitialize",
        "W3TP: ThreadPoolInitialize() already called\n");
    return 0;
  }
  hKey = 0;
  if ( a1 != -1 )
    goto LABEL_8;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\InetInfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    RegDword = I_ThreadPoolReadRegDword(hKey, L"ThreadPoolType", 0);
    RegCloseKey(hKey);
LABEL_8:
    if ( RegDword == 1 )
      return (unsigned int)WIN32_COMPLETION_PACKET::InitializeStatic();
  }
  memset_0(v7, 0, 0x54u);
  v4 = InitializeThreadPoolConfigWithDefaults((struct THREAD_POOL_CONFIG *)v7);
  if ( v4 >= 0 )
  {
    v4 = OverrideThreadPoolConfigWithRegistry(
           (struct THREAD_POOL_CONFIG *)v7,
           L"System\\CurrentControlSet\\Services\\InetInfo\\Parameters");
    if ( v4 >= 0 )
    {
      v8 = a2;
      ThreadPool = THREAD_POOL::CreateThreadPool(&g_pThreadPool, (struct THREAD_POOL_CONFIG *)v7);
      v4 = 0;
      if ( !ThreadPool )
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003d80  mov     [rsp+arg_0], rbx
0x180003d85  push    rdi
0x180003d86  sub     rsp, 90h
0x180003d8d  mov     edi, edx
0x180003d8f  mov     ebx, ecx
0x180003d91  lock inc cs:?g_cInitializeCount@@3JA; long g_cInitializeCount
0x180003d98  jz      short loc_180003DD7
0x180003d9a  test    cs:g_dwDebugFlags, 3
0x180003da1  jz      short loc_180003DD0
0x180003da3  mov     rcx, cs:g_pDebug
0x180003daa  lea     rax, aW3tpThreadpool_0; "W3TP: ThreadPoolInitialize() already ca"...
0x180003db1  lea     r9, aThreadpoolinit_0; "ThreadPoolInitialize"
0x180003db8  mov     [rsp+98h+phkResult], rax
0x180003dbd  mov     r8d, 8Bh
0x180003dc3  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003dca  call    cs:__imp_PuDbgPrint
0x180003dd0  xor     ecx, ecx
0x180003dd2  jmp     loc_180003EA3
0x180003dd7  mov     [rsp+98h+hKey], 0
0x180003de3  cmp     ecx, 0FFFFFFFFh
0x180003de6  jnz     short loc_180003E3D
0x180003de8  lea     rax, [rsp+98h+hKey]
0x180003df0  mov     r9d, 20019h; samDesired
0x180003df6  xor     r8d, r8d; ulOptions
0x180003df9  mov     [rsp+98h+phkResult], rax; phkResult
0x180003dfe  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\In"...
0x180003e05  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003e0c  call    cs:__imp_RegOpenKeyExW
0x180003e12  test    eax, eax
0x180003e14  jnz     short loc_180003E4B
0x180003e16  mov     rcx, [rsp+98h+hKey]; HKEY
0x180003e1e  lea     rdx, aThreadpooltype; "ThreadPoolType"
0x180003e25  xor     r8d, r8d; unsigned int
0x180003e28  call    ?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z; I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)
0x180003e2d  mov     rcx, [rsp+98h+hKey]; hKey
0x180003e35  mov     ebx, eax
0x180003e37  call    cs:__imp_RegCloseKey
0x180003e3d  cmp     ebx, 1
0x180003e40  jnz     short loc_180003E4B
0x180003e42  call    ?InitializeStatic@WIN32_COMPLETION_PACKET@@SAJXZ; WIN32_COMPLETION_PACKET::InitializeStatic(void)
0x180003e47  mov     ecx, eax
0x180003e49  jmp     short loc_180003EA3
0x180003e4b  xor     edx, edx; Val
0x180003e4d  lea     rcx, [rsp+98h+var_68]; void *
0x180003e52  lea     r8d, [rdx+54h]; Size
0x180003e56  call    memset_0
0x180003e5b  lea     rcx, [rsp+98h+var_68]; struct THREAD_POOL_CONFIG *
0x180003e60  call    ?InitializeThreadPoolConfigWithDefaults@@YAJPEAUTHREAD_POOL_CONFIG@@@Z; InitializeThreadPoolConfigWithDefaults(THREAD_POOL_CONFIG *)
0x180003e65  mov     ecx, eax
0x180003e67  test    eax, eax
0x180003e69  js      short loc_180003EA3
0x180003e6b  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\In"...
0x180003e72  lea     rcx, [rsp+98h+var_68]; struct THREAD_POOL_CONFIG *
0x180003e77  call    ?OverrideThreadPoolConfigWithRegistry@@YAJPEAUTHREAD_POOL_CONFIG@@PEBG@Z; OverrideThreadPoolConfigWithRegistry(THREAD_POOL_CONFIG *,ushort const *)
0x180003e7c  mov     ecx, eax
0x180003e7e  test    eax, eax
0x180003e80  js      short loc_180003EA3
0x180003e82  lea     rdx, [rsp+98h+var_68]; struct THREAD_POOL_CONFIG *
0x180003e87  mov     [rsp+98h+var_40], edi
0x180003e8b  lea     rcx, ?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; struct THREAD_POOL **
0x180003e92  call    ?CreateThreadPool@THREAD_POOL@@SAHPEAPEAV1@PEAUTHREAD_POOL_CONFIG@@@Z; THREAD_POOL::CreateThreadPool(THREAD_POOL * *,THREAD_POOL_CONFIG *)
0x180003e97  xor     ecx, ecx
0x180003e99  mov     edx, 80004005h
0x180003e9e  test    eax, eax
0x180003ea0  cmovz   ecx, edx
0x180003ea3  mov     rbx, [rsp+98h+arg_0]
0x180003eab  mov     eax, ecx
0x180003ead  add     rsp, 90h
0x180003eb4  pop     rdi
0x180003eb5  retn
```
