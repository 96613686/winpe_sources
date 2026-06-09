# ElevatedDataCollectorCreate(void *,ushort,void *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180020468`
- end: `0x180020605`
- name: `?ElevatedDataCollectorCreate@@YAJPEAXG0PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(HANDLE hTargetProcessHandle, __int16, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180019178`

## callees

- `0x1800029d0`
- `0x180006134`
- `0x180007cf8`
- `0x180011ef8`
- `0x18001fb94`
- `0x180020468`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002055a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002055a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800204a0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800204a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002058e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002058e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800205e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800205e1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180020584`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180020584`

## string_xrefs

- `0x1800204ae`: `-datacollectorcreate %u %I64u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ElevatedDataCollectorCreate(HANDLE hTargetProcessHandle, __int16 a2, __int64 a3, __int64 a4)
{
  DWORD ProcessId; // eax
  signed int ElevatedProcessAsUser; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE *v12; // rbx
  HANDLE v13; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  HANDLE hSourceHandle; // [rsp+40h] [rbp-148h] BYREF
  __int64 v18; // [rsp+48h] [rbp-140h] BYREF
  wchar_t v19[128]; // [rsp+50h] [rbp-138h] BYREF

  hSourceHandle = 0;
  v18 = a3;
  ProcessId = GetProcessId(hTargetProcessHandle);
  ElevatedProcessAsUser = StringCchPrintfW(v19, 0x80u, L"-datacollectorcreate %u %I64u", ProcessId, a3);
  if ( ElevatedProcessAsUser >= 0 )
  {
    ElevatedProcessAsUser = CreateElevatedProcessAsUser(
                              (_DWORD)hTargetProcessHandle,
                              (unsigned int)v19,
                              (unsigned int)&v18,
                              1,
                              a2,
                              (__int64)&hSourceHandle,
                              6);
    if ( ElevatedProcessAsUser >= 0 )
    {
      v12 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(a4);
      v13 = hSourceHandle;
      hSourceHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, v13, hTargetProcessHandle, v12, 0x120001u, 0, 1u) )
      {
        ElevatedProcessAsUser = 0;
      }
      else
      {
        LastError = GetLastError();
        ElevatedProcessAsUser = LastError;
        if ( LastError > 0 )
          ElevatedProcessAsUser = (unsigned __int16)LastError | 0x80070000;
        if ( ElevatedProcessAsUser >= 0 )
          ElevatedProcessAsUser = -2147467259;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 116;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 115;
LABEL_6:
        WPP_SF_d(v10[2], v11, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)ElevatedProcessAsUser);
      }
    }
  }
  if ( (unsigned __int64)hSourceHandle + 1 > 1 )
    CloseHandle(hSourceHandle);
  return (unsigned int)ElevatedProcessAsUser;
}

```

## disassembly

```asm
0x180020468  push    rbx
0x18002046a  push    rbp
0x18002046b  push    rsi
0x18002046c  push    rdi
0x18002046d  sub     rsp, 168h
0x180020474  mov     rax, cs:__security_cookie
0x18002047b  xor     rax, rsp
0x18002047e  mov     [rsp+188h+var_38], rax
0x180020486  mov     rbp, r9
0x180020489  mov     rbx, r8
0x18002048c  movzx   edi, dx
0x18002048f  mov     rsi, rcx
0x180020492  mov     [rsp+188h+hSourceHandle], 0
0x18002049b  mov     [rsp+188h+var_140], rbx
0x1800204a0  call    cs:__imp_GetProcessId
0x1800204a6  mov     r9d, eax
0x1800204a9  mov     qword ptr [rsp+188h+dwDesiredAccess], rbx
0x1800204ae  lea     r8, aDatacollectorc; "-datacollectorcreate %u %I64u"
0x1800204b5  mov     edx, 80h; unsigned __int64
0x1800204ba  lea     rcx, [rsp+188h+var_138]; wchar_t *
0x1800204bf  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800204c4  mov     ebx, eax
0x1800204c6  test    eax, eax
0x1800204c8  js      loc_1800205D2
0x1800204ce  mov     [rsp+188h+dwOptions], 6
0x1800204d6  lea     rax, [rsp+188h+hSourceHandle]
0x1800204db  mov     qword ptr [rsp+188h+bInheritHandle], rax
0x1800204e0  mov     word ptr [rsp+188h+dwDesiredAccess], di
0x1800204e5  mov     r9d, 1
0x1800204eb  lea     r8, [rsp+188h+var_140]
0x1800204f0  lea     rdx, [rsp+188h+var_138]
0x1800204f5  mov     rcx, rsi
0x1800204f8  call    ?CreateElevatedProcessAsUser@@YAJPEAXPEA_WPEAPEAXKGPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K@Z; CreateElevatedProcessAsUser(void *,wchar_t *,void * *,ulong,ushort,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x1800204fd  mov     ebx, eax
0x1800204ff  test    eax, eax
0x180020501  jns     short loc_180020541
0x180020503  lea     rax, WPP_GLOBAL_Control
0x18002050a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020511  cmp     rcx, rax
0x180020514  jz      loc_1800205D2
0x18002051a  test    byte ptr [rcx+1Ch], 1
0x18002051e  jz      loc_1800205D2
0x180020524  mov     edx, 73h ; 's'
0x180020529  mov     r9d, ebx
0x18002052c  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x180020533  mov     rcx, [rcx+10h]
0x180020537  call    WPP_SF_d
0x18002053c  jmp     loc_1800205D2
0x180020541  mov     rcx, rbp
0x180020544  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180020549  mov     rbx, rax
0x18002054c  mov     rdi, [rsp+188h+hSourceHandle]
0x180020551  mov     [rsp+188h+hSourceHandle], 0
0x18002055a  call    cs:__imp_GetCurrentProcess
0x180020560  mov     [rsp+188h+dwOptions], 1; dwOptions
0x180020568  mov     [rsp+188h+bInheritHandle], 0; bInheritHandle
0x180020570  mov     [rsp+188h+dwDesiredAccess], 120001h; dwDesiredAccess
0x180020578  mov     r9, rbx; lpTargetHandle
0x18002057b  mov     r8, rsi; hTargetProcessHandle
0x18002057e  mov     rdx, rdi; hSourceHandle
0x180020581  mov     rcx, rax; hSourceProcessHandle
0x180020584  call    cs:__imp_DuplicateHandle
0x18002058a  test    eax, eax
0x18002058c  jnz     short loc_1800205D0
0x18002058e  call    cs:__imp_GetLastError
0x180020594  mov     ebx, eax
0x180020596  test    eax, eax
0x180020598  jle     short loc_1800205A3
0x18002059a  movzx   ebx, ax
0x18002059d  or      ebx, 80070000h
0x1800205a3  mov     eax, 80004005h
0x1800205a8  test    ebx, ebx
0x1800205aa  cmovns  ebx, eax
0x1800205ad  lea     rax, WPP_GLOBAL_Control
0x1800205b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205bb  cmp     rcx, rax
0x1800205be  jz      short loc_1800205D2
0x1800205c0  test    byte ptr [rcx+1Ch], 1
0x1800205c4  jz      short loc_1800205D2
0x1800205c6  mov     edx, 74h ; 't'
0x1800205cb  jmp     loc_180020529
0x1800205d0  xor     ebx, ebx
0x1800205d2  mov     rcx, [rsp+188h+hSourceHandle]; hObject
0x1800205d7  lea     rax, [rcx+1]
0x1800205db  cmp     rax, 1
0x1800205df  jbe     short loc_1800205E7
0x1800205e1  call    cs:__imp_CloseHandle
0x1800205e7  mov     eax, ebx
0x1800205e9  mov     rcx, [rsp+188h+var_38]
0x1800205f1  xor     rcx, rsp; StackCookie
0x1800205f4  call    __security_check_cookie
0x1800205f9  add     rsp, 168h
0x180020600  pop     rdi
0x180020601  pop     rsi
0x180020602  pop     rbp
0x180020603  pop     rbx
0x180020604  retn
```
