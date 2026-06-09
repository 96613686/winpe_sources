# DllMain

- ea: `0x180001db0`
- end: `0x180001ed3`
- name: `DllMain`
- size: `291`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001314`

## callees

- `0x180001db0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001df5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001df5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001e28`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e38`
- `iisutil!PuCreateDebugPrintsObject` at `0x180001ddc`
- `iisutil!PuCreateDebugPrintsObject` at `0x180001ddc`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180001e04`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180001e04`
- `iisutil!PuDbgPrint` at `0x180001eaa`
- `iisutil!PuDbgPrint` at `0x180001eaa`
- `iisutil!PuDbgPrintError` at `0x180001e7e`
- `iisutil!PuDbgPrintError` at `0x180001e7e`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180001eb9`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180001eb9`

## string_xrefs

- `0x180001dee`: `Unable to Create Debug Print Object \n`
- `0x180001dfd`: `System\CurrentControlSet\Services\W3LogSvc\Parameters`
- `0x180001e65`: `DllMain`
- `0x180001e93`: `DllMain`
- `0x180001e73`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\main.cpp`
- `0x180001ea3`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\main.cpp`
- `0x180001e53`: `Disabling thread library calls failed\n`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx
  int DebugFlagsFromRegStr; // eax
  signed int LastError; // eax

  v4 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_pDebug = PuCreateDebugPrintsObject("w3logsvc", 9, lpvReserved);
      if ( !g_pDebug )
        OutputDebugStringA("Unable to Create Debug Print Object \n");
      DebugFlagsFromRegStr = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3LogSvc\\Parameters", 0);
      g_dwDebugFlags = DebugFlagsFromRegStr;
      if ( g_pDebug && *(_DWORD *)(g_pDebug + 640) )
      {
        v4 = DisableThreadLibraryCalls(hinstDLL);
        if ( !v4 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
              125,
              "DllMain",
              LastError,
              "Disabling thread library calls failed\n");
        }
      }
      else
      {
        v4 = 0;
        if ( (DebugFlagsFromRegStr & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
            110,
            "DllMain",
            "Debug print object is not valid\n");
      }
    }
  }
  else
  {
    g_pDebug = PuDeleteDebugPrintsObject(g_pDebug, fdwReason, lpvReserved);
  }
  return v4;
}

```

## disassembly

```asm
0x180001db0  mov     [rsp+arg_0], rbx
0x180001db5  push    rdi
0x180001db6  sub     rsp, 30h
0x180001dba  mov     rdi, rcx
0x180001dbd  mov     ebx, 1
0x180001dc2  test    edx, edx
0x180001dc4  jz      loc_180001EB2
0x180001dca  cmp     edx, ebx
0x180001dcc  jnz     loc_180001EC6
0x180001dd2  lea     edx, [rbx+8]
0x180001dd5  lea     rcx, aW3logsvc_0; "w3logsvc"
0x180001ddc  call    cs:__imp_PuCreateDebugPrintsObject
0x180001de2  mov     cs:g_pDebug, rax
0x180001de9  test    rax, rax
0x180001dec  jnz     short loc_180001DFB
0x180001dee  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180001df5  call    cs:__imp_OutputDebugStringA
0x180001dfb  xor     edx, edx
0x180001dfd  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180001e04  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180001e0a  mov     rcx, cs:g_pDebug
0x180001e11  mov     cs:g_dwDebugFlags, eax
0x180001e17  test    rcx, rcx
0x180001e1a  jz      short loc_180001E86
0x180001e1c  cmp     dword ptr [rcx+280h], 0
0x180001e23  jz      short loc_180001E86
0x180001e25  mov     rcx, rdi; hLibModule
0x180001e28  call    cs:__imp_DisableThreadLibraryCalls
0x180001e2e  mov     ebx, eax
0x180001e30  test    eax, eax
0x180001e32  jnz     loc_180001EC6
0x180001e38  call    cs:__imp_GetLastError
0x180001e3e  test    eax, eax
0x180001e40  jle     short loc_180001E4A
0x180001e42  movzx   eax, ax
0x180001e45  or      eax, 80070000h
0x180001e4a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001e51  jz      short loc_180001EC6
0x180001e53  lea     rcx, aDisablingThrea; "Disabling thread library calls failed\n"
0x180001e5a  mov     r8d, 7Dh ; '}'
0x180001e60  mov     [rsp+38h+var_10], rcx
0x180001e65  lea     r9, aDllmain; "DllMain"
0x180001e6c  mov     rcx, cs:g_pDebug
0x180001e73  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001e7a  mov     dword ptr [rsp+38h+var_18], eax
0x180001e7e  call    cs:__imp_PuDbgPrintError
0x180001e84  jmp     short loc_180001EC6
0x180001e86  xor     ebx, ebx
0x180001e88  test    al, 3
0x180001e8a  jz      short loc_180001EC6
0x180001e8c  lea     rax, aDebugPrintObje; "Debug print object is not valid\n"
0x180001e93  lea     r9, aDllmain; "DllMain"
0x180001e9a  mov     [rsp+38h+var_18], rax
0x180001e9f  lea     r8d, [rbx+6Eh]
0x180001ea3  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001eaa  call    cs:__imp_PuDbgPrint
0x180001eb0  jmp     short loc_180001EC6
0x180001eb2  mov     rcx, cs:g_pDebug
0x180001eb9  call    cs:__imp_PuDeleteDebugPrintsObject
0x180001ebf  mov     cs:g_pDebug, rax
0x180001ec6  mov     eax, ebx
0x180001ec8  mov     rbx, [rsp+38h+arg_0]
0x180001ecd  add     rsp, 30h
0x180001ed1  pop     rdi
0x180001ed2  retn
```
