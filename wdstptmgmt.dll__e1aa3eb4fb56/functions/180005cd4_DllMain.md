# DllMain

- ea: `0x180005cd4`
- end: `0x180005d5e`
- name: `DllMain`
- size: `138`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001de4`

## callees

- `0x180005cd4`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180005d24`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180005d24`
- `WdsCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x180005cf5`
- `WdsCommonLib!?Initialize@CTrace@@QEAAKPEBGH@Z` at `0x180005cf5`
- `WdsCommonLib!?Shutdown@CTrace@@QEAAKXZ` at `0x180005d47`
- `WdsCommonLib!?Shutdown@CTrace@@QEAAKXZ` at `0x180005d47`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax

  g_hInstance = hinstDLL;
  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
      CTrace::Shutdown((CTrace *)qword_18003B770);
    return 1;
  }
  CTrace::Initialize((CTrace *)qword_18003B770, L"WDSTPTMGMT", 0);
  g_ErrLibTraceFunction = ErrLibTrace;
  g_ErrLibTraceFunctionEx = ErrLibTraceEx;
  DisableThreadLibraryCalls(g_hInstance);
  result = 0;
  if ( !ATL::CAtlBaseModule::m_bInitFailed )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180005cd4  sub     rsp, 28h
0x180005cd8  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x180005cdf  cmp     edx, 1
0x180005ce2  jnz     short loc_180005D3C
0x180005ce4  xor     r8d, r8d
0x180005ce7  lea     rdx, aWdstptmgmt; "WDSTPTMGMT"
0x180005cee  lea     rcx, qword_18003B770
0x180005cf5  call    cs:__imp_?Initialize@CTrace@@QEAAKPEBGH@Z; CTrace::Initialize(ushort const *,int)
0x180005cfc  nop     dword ptr [rax+rax+00h]
0x180005d01  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hLibModule
0x180005d08  lea     rax, ?ErrLibTrace@@YAXPEBGZZ; ErrLibTrace(ushort const *,...)
0x180005d0f  mov     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rax; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005d16  lea     rax, ?ErrLibTraceEx@@YAXKPEBGZZ; ErrLibTraceEx(ulong,ushort const *,...)
0x180005d1d  mov     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rax; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180005d24  call    cs:__imp_DisableThreadLibraryCalls
0x180005d2b  nop     dword ptr [rax+rax+00h]
0x180005d30  xor     eax, eax
0x180005d32  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, al; bool ATL::CAtlBaseModule::m_bInitFailed
0x180005d38  jz      short loc_180005D53
0x180005d3a  jmp     short loc_180005D58
0x180005d3c  test    edx, edx
0x180005d3e  jnz     short loc_180005D53
0x180005d40  lea     rcx, qword_18003B770
0x180005d47  call    cs:__imp_?Shutdown@CTrace@@QEAAKXZ; CTrace::Shutdown(void)
0x180005d4e  nop     dword ptr [rax+rax+00h]
0x180005d53  mov     eax, 1
0x180005d58  add     rsp, 28h
0x180005d5c  retn
```
