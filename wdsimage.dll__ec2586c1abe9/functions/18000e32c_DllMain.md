# DllMain

- ea: `0x18000e32c`
- end: `0x18000e396`
- name: `DllMain`
- size: `106`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001364`

## callees

- `0x18000e32c`

## import_xrefs

- `ImageLib!g_bUseVdsStatic` at `0x18000e351`
- `ImageLib!ImageLibRegisterLogger` at `0x18000e362`
- `ImageLib!ImageLibRegisterLogger` at `0x18000e362`
- `WdsCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x18000e37f`
- `WdsCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x18000e37f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    g_ErrLibTraceFunction = WdsImgTrace;
    g_ErrLibTraceFunctionEx = WdsImgTraceEx;
    g_bUseVdsStatic = 0;
    ImageLibRegisterLogger(&LogCallback, fdwReason, lpvReserved);
    CTrace::Initialize((CTrace *)g_WdsImgTrace, L"WDSIMAGE", 0);
  }
  return 1;
}

```

## disassembly

```asm
0x18000e32c  sub     rsp, 28h
0x18000e330  cmp     edx, 1
0x18000e333  jnz     short loc_18000E38B
0x18000e335  lea     rcx, ?WdsImgTrace@@YAXPEBGZZ; WdsImgTrace(ushort const *,...)
0x18000e33c  mov     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rcx; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000e343  lea     rcx, ?WdsImgTraceEx@@YAXKPEBGZZ; WdsImgTraceEx(ulong,ushort const *,...)
0x18000e34a  mov     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rcx; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000e351  mov     rcx, cs:__imp_?g_bUseVdsStatic@@3HA; int g_bUseVdsStatic
0x18000e358  and     dword ptr [rcx], 0
0x18000e35b  lea     rcx, ?LogCallback@@YAXW4_LIBLOG_SEVERITY@@KPEBGPEAD@Z; LogCallback(_LIBLOG_SEVERITY,ulong,ushort const *,char *)
0x18000e362  call    cs:__imp_ImageLibRegisterLogger
0x18000e369  nop     dword ptr [rax+rax+00h]
0x18000e36e  xor     r8d, r8d
0x18000e371  lea     rdx, aWdsimage; "WDSIMAGE"
0x18000e378  lea     rcx, ?g_WdsImgTrace@@3VCTrace@@A; CTrace g_WdsImgTrace
0x18000e37f  call    cs:__imp_?Initialize@CTrace@@QEAAKPEBGH@Z; CTrace::Initialize(ushort const *,int)
0x18000e386  nop     dword ptr [rax+rax+00h]
0x18000e38b  mov     eax, 1
0x18000e390  add     rsp, 28h
0x18000e394  retn
```
