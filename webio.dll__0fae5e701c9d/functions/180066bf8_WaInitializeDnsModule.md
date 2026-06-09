# WaInitializeDnsModule

- ea: `0x180066bf8`
- end: `0x180066cd9`
- name: `WaInitializeDnsModule`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180041954`

## callees

- `0x18002e460`
- `0x180066bf8`
- `0x1800722f0`
- `0x180072c70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180066c3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180066c3d`
- `WS2_32!__imp_WSAStartup` at `0x180066c2d`
- `WS2_32!__imp_WSAStartup` at `0x180066c2d`

## pseudocode

```c
int WaInitializeDnsModule()
{
  int result; // eax
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  __int64 v2; // rcx
  struct WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  result = WSAStartup(0x202u, &WSAData);
  if ( !result )
  {
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    WaDnsCacheCleanupGroup = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      WaDnsCacheEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
      *(_OWORD *)&WaDnsCacheEnvironment.RaceDll = 0;
      WaDnsCacheEnvironment.Version = 3;
      result = 0;
      WaDnsCacheEnvironment.Pool = 0;
      WaDnsCacheEnvironment.FinalizationCallback = 0;
      WaDnsCacheEnvironment.u.Flags = 0;
      WaDnsCacheEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
      WaDnsCacheEnvironment.Size = 72;
      WaDnsCacheEnvironment.CleanupGroupCancelCallback = 0;
      WaDnsModuleInitialized = 1;
    }
    else
    {
      return WaGetLastError(v2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180066bf8  sub     rsp, 1D8h
0x180066bff  mov     rax, cs:__security_cookie
0x180066c06  xor     rax, rsp
0x180066c09  mov     [rsp+1D8h+var_18], rax
0x180066c11  xor     edx, edx; Val
0x180066c13  lea     rcx, [rsp+1D8h+WSAData]; void *
0x180066c18  mov     r8d, 198h; Size
0x180066c1e  call    memset_0
0x180066c23  mov     ecx, 202h; wVersionRequested
0x180066c28  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x180066c2d  call    cs:__imp_WSAStartup
0x180066c34  nop     dword ptr [rax+rax+00h]
0x180066c39  test    eax, eax
0x180066c3b  jnz     short loc_180066CB9
0x180066c3d  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180066c44  nop     dword ptr [rax+rax+00h]
0x180066c49  mov     cs:WaDnsCacheCleanupGroup, rax
0x180066c50  test    rax, rax
0x180066c53  jz      short loc_180066CD2
0x180066c55  xorps   xmm0, xmm0
0x180066c58  mov     cs:WaDnsCacheEnvironment.CleanupGroup, rax
0x180066c5f  movdqu  xmmword ptr cs:WaDnsCacheEnvironment.RaceDll, xmm0
0x180066c67  mov     cs:WaDnsCacheEnvironment.Version, 3
0x180066c71  xor     eax, eax
0x180066c73  mov     cs:WaDnsCacheEnvironment.Pool, 0
0x180066c7e  mov     cs:WaDnsCacheEnvironment.FinalizationCallback, 0
0x180066c89  mov     dword ptr cs:WaDnsCacheEnvironment.u, 0
0x180066c93  mov     cs:WaDnsCacheEnvironment.CallbackPriority, 1
0x180066c9d  mov     cs:WaDnsCacheEnvironment.Size, 48h ; 'H'
0x180066ca7  mov     cs:WaDnsCacheEnvironment.CleanupGroupCancelCallback, 0
0x180066cb2  mov     cs:WaDnsModuleInitialized, 1
0x180066cb9  mov     rcx, [rsp+1D8h+var_18]
0x180066cc1  xor     rcx, rsp; StackCookie
0x180066cc4  call    __security_check_cookie
0x180066cc9  add     rsp, 1D8h
0x180066cd0  retn
0x180066cd2  call    WaGetLastError
0x180066cd7  jmp     short loc_180066CB9
```
