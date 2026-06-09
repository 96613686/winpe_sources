# ExtractThreadIdFromPeb(ulong,ulong *,int)

- ea: `0x18002f3f4`
- end: `0x18002f4a5`
- name: `?ExtractThreadIdFromPeb@@YAJKPEAKH@Z`
- size: `177`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned int *lpBuffer, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800248f4`

## callees

- `0x180011ef8`
- `0x18002f3f4`
- `0x18002f4ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f48d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f48d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002f419`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002f419`

## pseudocode

```c
__int64 __fastcall ExtractThreadIdFromPeb(DWORD dwProcessId, unsigned int *lpBuffer, int a3)
{
  HANDLE v5; // rax
  void *v6; // rdi
  signed int LastError; // eax
  unsigned int ThreadIdFromPebHandle; // ebx

  *lpBuffer = 0;
  v5 = OpenProcess(0x410u, 0, dwProcessId);
  v6 = v5;
  if ( (unsigned __int64)v5 + 1 > 1 )
  {
    ThreadIdFromPebHandle = ExtractThreadIdFromPebHandle(v5, lpBuffer, a3);
    CloseHandle(v6);
  }
  else
  {
    LastError = GetLastError();
    ThreadIdFromPebHandle = LastError;
    if ( LastError > 0 )
      ThreadIdFromPebHandle = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
        ThreadIdFromPebHandle);
  }
  return ThreadIdFromPebHandle;
}

```

## disassembly

```asm
0x18002f3f4  mov     [rsp+arg_0], rbx
0x18002f3f9  mov     [rsp+arg_10], rsi
0x18002f3fe  push    rdi
0x18002f3ff  sub     rsp, 20h
0x18002f403  mov     esi, r8d
0x18002f406  mov     rbx, rdx
0x18002f409  mov     dword ptr [rdx], 0
0x18002f40f  mov     r8d, ecx; dwProcessId
0x18002f412  xor     edx, edx; bInheritHandle
0x18002f414  mov     ecx, 410h; dwDesiredAccess
0x18002f419  call    cs:__imp_OpenProcess
0x18002f41f  mov     rdi, rax
0x18002f422  mov     [rsp+28h+arg_8], rax
0x18002f427  lea     rcx, [rax+1]
0x18002f42b  cmp     rcx, 1
0x18002f42f  ja      short loc_18002F47A
0x18002f431  call    cs:__imp_GetLastError
0x18002f437  mov     ebx, eax
0x18002f439  test    eax, eax
0x18002f43b  jle     short loc_18002F446
0x18002f43d  movzx   ebx, ax
0x18002f440  or      ebx, 80070000h
0x18002f446  lea     rax, WPP_GLOBAL_Control
0x18002f44d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f454  cmp     rcx, rax
0x18002f457  jz      short loc_18002F478
0x18002f459  test    byte ptr [rcx+1Ch], 1
0x18002f45d  jz      short loc_18002F478
0x18002f45f  mov     edx, 0Ah
0x18002f464  mov     r9d, ebx
0x18002f467  lea     r8, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids
0x18002f46e  mov     rcx, [rcx+10h]
0x18002f472  call    WPP_SF_d
0x18002f477  nop
0x18002f478  jmp     short loc_18002F493
0x18002f47a  mov     r8d, esi; int
0x18002f47d  mov     rdx, rbx; lpBuffer
0x18002f480  mov     rcx, rdi; hProcess
0x18002f483  call    ?ExtractThreadIdFromPebHandle@@YAJPEAXPEAKH@Z; ExtractThreadIdFromPebHandle(void *,ulong *,int)
0x18002f488  mov     ebx, eax
0x18002f48a  mov     rcx, rdi; hObject
0x18002f48d  call    cs:__imp_CloseHandle
0x18002f493  mov     eax, ebx
0x18002f495  mov     rbx, [rsp+28h+arg_0]
0x18002f49a  mov     rsi, [rsp+28h+arg_10]
0x18002f49f  add     rsp, 20h
0x18002f4a3  pop     rdi
0x18002f4a4  retn
```
