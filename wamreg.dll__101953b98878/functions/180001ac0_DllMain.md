# DllMain

- ea: `0x180001ac0`
- end: `0x180001c94`
- name: `DllMain`
- size: `468`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180001344`

## callees

- `0x180001044`
- `0x180001084`
- `0x180001ac0`
- `0x1800043e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001b8b`
- `KERNEL32!GetLastError` at `0x180001c0a`
- `KERNEL32!GetLastError` at `0x180001b8b`
- `KERNEL32!GetLastError` at `0x180001c0a`
- `KERNEL32!CloseHandle` at `0x180001bf7`
- `KERNEL32!CloseHandle` at `0x180001bf7`
- `KERNEL32!OutputDebugStringA` at `0x180001b15`
- `KERNEL32!OutputDebugStringA` at `0x180001b15`
- `KERNEL32!DeleteCriticalSection` at `0x180001be5`
- `KERNEL32!DeleteCriticalSection` at `0x180001be5`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180001ad7`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180001ad7`
- `KERNEL32!CreateEventA` at `0x180001b6c`
- `KERNEL32!CreateEventA` at `0x180001b6c`
- `iisutil!IISInitializeCriticalSection` at `0x180001b5c`
- `iisutil!IISInitializeCriticalSection` at `0x180001b5c`
- `iisutil!PuCreateDebugPrintsObject` at `0x180001afc`
- `iisutil!PuCreateDebugPrintsObject` at `0x180001afc`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180001c7a`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180001c7a`
- `iisutil!IISGetPlatformType` at `0x180001add`
- `iisutil!IISGetPlatformType` at `0x180001add`
- `iisutil!PuDbgPrint` at `0x180001bbc`
- `iisutil!PuDbgPrint` at `0x180001c3b`
- `iisutil!PuDbgPrint` at `0x180001bbc`
- `iisutil!PuDbgPrint` at `0x180001c3b`

## string_xrefs

- `0x180001b0e`: `Unable to Create Debug Print Object \n`
- `0x180001baa`: `Failed to create m_hWriteLock(Event). error = %08x`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // edi
  int v4; // eax
  _QWORD *v5; // rax
  DWORD LastError; // eax
  DWORD v7; // eax
  CWmRgSrvFactory *v8; // rsi

  v3 = 1;
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    v4 = IISGetPlatformType();
    g_dwDebugFlags = 8;
    g_PlatformType = v4;
    g_pDebug = PuCreateDebugPrintsObject("WAMREG", 1);
    if ( !g_pDebug )
      OutputDebugStringA("Unable to Create Debug Print Object \n");
    v5 = operator new(0x18u);
    if ( !v5 )
    {
      g_pWmRgSrvFactory = 0;
      return 0;
    }
    v5[1] = 0;
    *v5 = &CWmRgSrvFactory::`vftable';
    *((_DWORD *)v5 + 4) = 0;
    _InterlockedAdd((volatile signed __int32 *)&g_dwRefCount, 1u);
    g_pWmRgSrvFactory = (CWmRgSrvFactory *)v5;
    IISInitializeCriticalSection(&CriticalSection);
    hEvent = CreateEventA(0, 1, 1, 0);
    if ( !hEvent )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LastError = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
          125,
          "WamAdmLock::Init",
          "Failed to create m_hWriteLock(Event). error = %08x",
          LastError);
      }
      return 0;
    }
  }
  else if ( !fdwReason )
  {
    DeleteCriticalSection(&CriticalSection);
    if ( hEvent )
    {
      if ( !CloseHandle(hEvent) && (g_dwDebugFlags & 3) != 0 )
      {
        v7 = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
          148,
          "WamAdmLock::UnInit",
          "error in CloseHandle. errno = %d\n",
          v7);
      }
      hEvent = 0;
    }
    v8 = g_pWmRgSrvFactory;
    if ( g_pWmRgSrvFactory )
    {
      CWmRgSrvFactory::~CWmRgSrvFactory(g_pWmRgSrvFactory);
      operator delete(v8);
      g_pWmRgSrvFactory = 0;
    }
    g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
  }
  return v3;
}

```

## disassembly

```asm
0x180001ac0  mov     [rsp+arg_0], rsi
0x180001ac5  push    rdi
0x180001ac6  sub     rsp, 30h
0x180001aca  mov     edi, 1
0x180001acf  cmp     edx, edi
0x180001ad1  jnz     loc_180001BD6
0x180001ad7  call    cs:__imp_DisableThreadLibraryCalls
0x180001add  call    cs:__imp_IISGetPlatformType
0x180001ae3  mov     edx, edi
0x180001ae5  mov     cs:g_dwDebugFlags, 8
0x180001aef  lea     rcx, aWamreg; "WAMREG"
0x180001af6  mov     cs:g_PlatformType, eax
0x180001afc  call    cs:__imp_PuCreateDebugPrintsObject
0x180001b02  mov     cs:g_pDebug, rax
0x180001b09  test    rax, rax
0x180001b0c  jnz     short loc_180001B1B
0x180001b0e  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180001b15  call    cs:__imp_OutputDebugStringA
0x180001b1b  mov     ecx, 18h; Size
0x180001b20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b25  test    rax, rax
0x180001b28  jz      loc_180001BC4
0x180001b2e  lea     rcx, ??_7CWmRgSrvFactory@@6B@; const CWmRgSrvFactory::`vftable'
0x180001b35  mov     qword ptr [rax+8], 0
0x180001b3d  mov     [rax], rcx
0x180001b40  mov     dword ptr [rax+10h], 0
0x180001b47  lock add cs:?g_dwRefCount@@3KA, edi; ulong g_dwRefCount
0x180001b4e  lea     rcx, CriticalSection
0x180001b55  mov     cs:?g_pWmRgSrvFactory@@3PEAVCWmRgSrvFactory@@EA, rax; CWmRgSrvFactory * g_pWmRgSrvFactory
0x180001b5c  call    cs:__imp_IISInitializeCriticalSection
0x180001b62  xor     r9d, r9d; lpName
0x180001b65  mov     r8d, edi; bInitialState
0x180001b68  mov     edx, edi; bManualReset
0x180001b6a  xor     ecx, ecx; lpEventAttributes
0x180001b6c  call    cs:__imp_CreateEventA
0x180001b72  mov     cs:hEvent, rax
0x180001b79  test    rax, rax
0x180001b7c  jnz     loc_180001C87
0x180001b82  test    byte ptr cs:g_dwDebugFlags, 3
0x180001b89  jz      short loc_180001BCF
0x180001b8b  call    cs:__imp_GetLastError
0x180001b91  mov     rcx, cs:g_pDebug
0x180001b98  lea     r9, aWamadmlockInit; "WamAdmLock::Init"
0x180001b9f  mov     [rsp+38h+var_10], eax
0x180001ba3  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180001baa  lea     rax, aFailedToCreate; "Failed to create m_hWriteLock(Event). e"...
0x180001bb1  mov     r8d, 7Dh ; '}'
0x180001bb7  mov     [rsp+38h+var_18], rax
0x180001bbc  call    cs:__imp_PuDbgPrint
0x180001bc2  jmp     short loc_180001BCF
0x180001bc4  mov     cs:?g_pWmRgSrvFactory@@3PEAVCWmRgSrvFactory@@EA, 0; CWmRgSrvFactory * g_pWmRgSrvFactory
0x180001bcf  xor     edi, edi
0x180001bd1  jmp     loc_180001C87
0x180001bd6  test    edx, edx
0x180001bd8  jnz     loc_180001C87
0x180001bde  lea     rcx, CriticalSection; lpCriticalSection
0x180001be5  call    cs:__imp_DeleteCriticalSection
0x180001beb  mov     rcx, cs:hEvent; hObject
0x180001bf2  test    rcx, rcx
0x180001bf5  jz      short loc_180001C4C
0x180001bf7  call    cs:__imp_CloseHandle
0x180001bfd  test    eax, eax
0x180001bff  jnz     short loc_180001C41
0x180001c01  test    byte ptr cs:g_dwDebugFlags, 3
0x180001c08  jz      short loc_180001C41
0x180001c0a  call    cs:__imp_GetLastError
0x180001c10  mov     rcx, cs:g_pDebug
0x180001c17  lea     r9, aWamadmlockUnin; "WamAdmLock::UnInit"
0x180001c1e  mov     [rsp+38h+var_10], eax
0x180001c22  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180001c29  lea     rax, aErrorInCloseha; "error in CloseHandle. errno = %d\n"
0x180001c30  mov     r8d, 94h
0x180001c36  mov     [rsp+38h+var_18], rax
0x180001c3b  call    cs:__imp_PuDbgPrint
0x180001c41  mov     cs:hEvent, 0
0x180001c4c  mov     rsi, cs:?g_pWmRgSrvFactory@@3PEAVCWmRgSrvFactory@@EA; CWmRgSrvFactory * g_pWmRgSrvFactory
0x180001c53  test    rsi, rsi
0x180001c56  jz      short loc_180001C73
0x180001c58  mov     rcx, rsi; this
0x180001c5b  call    ??1CWmRgSrvFactory@@QEAA@XZ; CWmRgSrvFactory::~CWmRgSrvFactory(void)
0x180001c60  mov     rcx, rsi; Block
0x180001c63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001c68  mov     cs:?g_pWmRgSrvFactory@@3PEAVCWmRgSrvFactory@@EA, 0; CWmRgSrvFactory * g_pWmRgSrvFactory
0x180001c73  mov     rcx, cs:g_pDebug
0x180001c7a  call    cs:__imp_PuDeleteDebugPrintsObject
0x180001c80  mov     cs:g_pDebug, rax
0x180001c87  mov     rsi, [rsp+38h+arg_0]
0x180001c8c  mov     eax, edi
0x180001c8e  add     rsp, 30h
0x180001c92  pop     rdi
0x180001c93  retn
```
