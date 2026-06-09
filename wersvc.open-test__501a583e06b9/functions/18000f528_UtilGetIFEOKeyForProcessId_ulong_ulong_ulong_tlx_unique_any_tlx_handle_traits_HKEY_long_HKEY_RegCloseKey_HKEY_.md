# UtilGetIFEOKeyForProcessId(ulong,ulong,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)

- ea: `0x18000f528`
- end: `0x18000f5d7`
- name: `?UtilGetIFEOKeyForProcessId@@YAJKKKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180023d0c`
- `0x18002f04c`

## callees

- `0x18000f270`
- `0x18000f528`
- `0x180011f38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5bf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f546`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f546`

## pseudocode

```c
__int64 __fastcall UtilGetIFEOKeyForProcessId(DWORD dwProcessId)
{
  HANDLE v2; // rax
  void *v3; // rdi
  signed int LastError; // eax
  signed int IFEOKeyForProcess; // ebx

  v2 = OpenProcess(0x400u, 0, dwProcessId);
  v3 = v2;
  if ( (unsigned __int64)v2 + 1 > 1 )
  {
    IFEOKeyForProcess = UtilGetIFEOKeyForProcess(v2);
    CloseHandle(v3);
  }
  else
  {
    LastError = GetLastError();
    IFEOKeyForProcess = LastError;
    if ( LastError > 0 )
      IFEOKeyForProcess = (unsigned __int16)LastError | 0x80070000;
    if ( IFEOKeyForProcess >= 0 )
      IFEOKeyForProcess = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        164,
        WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
        dwProcessId,
        IFEOKeyForProcess);
  }
  return (unsigned int)IFEOKeyForProcess;
}

```

## disassembly

```asm
0x18000f528  mov     [rsp+arg_0], rbx
0x18000f52d  mov     [rsp+arg_8], rsi
0x18000f532  push    rdi
0x18000f533  sub     rsp, 30h
0x18000f537  mov     esi, ecx
0x18000f539  mov     r8d, ecx; dwProcessId
0x18000f53c  mov     ecx, 400h; dwDesiredAccess
0x18000f541  xor     edx, edx; bInheritHandle
0x18000f543  mov     rbx, r9
0x18000f546  call    cs:__imp_OpenProcess
0x18000f54c  mov     rdi, rax
0x18000f54f  lea     rdx, [rax+1]
0x18000f553  cmp     rdx, 1
0x18000f557  ja      short loc_18000F5AF
0x18000f559  call    cs:__imp_GetLastError
0x18000f55f  mov     ebx, eax
0x18000f561  test    eax, eax
0x18000f563  jle     short loc_18000F56E
0x18000f565  movzx   ebx, ax
0x18000f568  or      ebx, 80070000h
0x18000f56e  test    ebx, ebx
0x18000f570  mov     eax, 80004005h
0x18000f575  cmovns  ebx, eax
0x18000f578  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f57f  lea     rax, WPP_GLOBAL_Control
0x18000f586  cmp     rcx, rax
0x18000f589  jz      short loc_18000F5C5
0x18000f58b  test    byte ptr [rcx+1Ch], 1
0x18000f58f  jz      short loc_18000F5C5
0x18000f591  mov     rcx, [rcx+10h]
0x18000f595  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000f59c  mov     edx, 0A4h
0x18000f5a1  mov     [rsp+38h+var_18], ebx
0x18000f5a5  mov     r9d, esi
0x18000f5a8  call    WPP_SF_Dd
0x18000f5ad  jmp     short loc_18000F5C5
0x18000f5af  mov     r9, rbx
0x18000f5b2  mov     rcx, rdi; hProcess
0x18000f5b5  call    ?UtilGetIFEOKeyForProcess@@YAJPEAXKKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; UtilGetIFEOKeyForProcess(void *,ulong,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)
0x18000f5ba  mov     rcx, rdi; hObject
0x18000f5bd  mov     ebx, eax
0x18000f5bf  call    cs:__imp_CloseHandle
0x18000f5c5  mov     rsi, [rsp+38h+arg_8]
0x18000f5ca  mov     eax, ebx
0x18000f5cc  mov     rbx, [rsp+38h+arg_0]
0x18000f5d1  add     rsp, 30h
0x18000f5d5  pop     rdi
0x18000f5d6  retn
```
