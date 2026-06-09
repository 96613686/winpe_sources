# CWdiHandler::WdipLaunchUserHost(void *)

- ea: `0x1800015b0`
- end: `0x18000161f`
- name: `?WdipLaunchUserHost@CWdiHandler@@CAKPEAX@Z`
- size: `111`
- prototype: `void __fastcall __noreturn(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x1800015b0`
- `0x180001980`
- `0x180002ba0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180001618`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180001618`

## string_xrefs

- `0x1800015ef`: `clientcore\base\diagnosis\pdi\wdi\framework\library\taskhandler.cpp`

## pseudocode

```c
void __fastcall __noreturn CWdiHandler::WdipLaunchUserHost(PVOID Parameter)
{
  HMODULE v1; // rdi
  signed int Args; // eax
  bool v4; // sf

  v1 = (HMODULE)*((_QWORD *)Parameter + 4);
  Args = WdipTriggerHost(*((PVOID *)Parameter + 3));
  v4 = Args < 0;
  if ( Args > 0 )
  {
    Args = (unsigned __int16)Args | 0x80070000;
    v4 = Args < 0;
  }
  if ( v4 )
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\taskhandler.cpp",
      (int)L"CWdiHandler::WdipLaunchUserHost",
      217,
      (int)L"Error = %d",
      Args);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)Parameter + 5) + 32LL))(*((_QWORD *)Parameter + 5), 0);
  FreeLibraryAndExitThread(v1, 0);
}

```

## disassembly

```asm
0x1800015b0  mov     [rsp+arg_0], rbx
0x1800015b5  push    rdi
0x1800015b6  sub     rsp, 30h
0x1800015ba  mov     rdi, [rcx+20h]
0x1800015be  mov     rbx, rcx
0x1800015c1  mov     rcx, [rcx+18h]; Parameter
0x1800015c5  call    WdipTriggerHost
0x1800015ca  test    eax, eax
0x1800015cc  jle     short loc_1800015D8
0x1800015ce  movzx   eax, ax
0x1800015d1  or      eax, 80070000h
0x1800015d6  test    eax, eax
0x1800015d8  jns     short loc_180001601
0x1800015da  movzx   ecx, ax
0x1800015dd  lea     r9, aErrorD_0; "Error = %d"
0x1800015e4  mov     dword ptr [rsp+38h+Args], ecx; Args
0x1800015e8  lea     rdx, aCwdihandlerWdi; "CWdiHandler::WdipLaunchUserHost"
0x1800015ef  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800015f6  mov     r8d, 0D9h; int
0x1800015fc  call    WdipTraceError
0x180001601  mov     rcx, [rbx+28h]
0x180001605  xor     edx, edx
0x180001607  mov     rax, [rcx]
0x18000160a  mov     rax, [rax+20h]
0x18000160e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001613  xor     edx, edx; dwExitCode
0x180001615  mov     rcx, rdi; hLibModule
0x180001618  call    cs:__imp_FreeLibraryAndExitThread
```
