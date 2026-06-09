# CallerIdentity::IsHostedWindow(HWND__ *,int *)

- ea: `0x180076688`
- end: `0x1800767dc`
- name: `?IsHostedWindow@CallerIdentity@@YAJPEAUHWND__@@PEAH@Z`
- size: `340`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004efa0`

## callees

- `0x18002b1b0`
- `0x180076688`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076710`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800766f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800766f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007678d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007678d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180076755`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180076755`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18007673f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18007673f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x1800767a3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x1800767a3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800766cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800766cf`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x18007671e`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180076774`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x18007671e`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180076774`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsHostedWindow(HWND hWnd, _DWORD *a2, int *a3)
{
  HANDLE CurrentProcess; // rax
  HANDLE v6; // rax
  void *v7; // rdi
  DWORD dwProcessId; // [rsp+30h] [rbp-248h] BYREF
  __int64 v10; // [rsp+38h] [rbp-240h] BYREF
  __int64 v11; // [rsp+40h] [rbp-238h] BYREF
  WCHAR ClassName[264]; // [rsp+50h] [rbp-228h] BYREF

  *a2 = 0;
  do
  {
    if ( !hWnd )
      break;
    if ( GetClassNameW(hWnd, ClassName, 260) > 0
      && CompareStringOrdinal(ClassName, -1, L"ApplicationHostBridgeWindow", -1, 1) == 2 )
    {
      v10 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( (unsigned int)GetProcessUIContextInformation(CurrentProcess, &v10) && (_DWORD)v10 == 2 )
      {
        dwProcessId = 0;
        if ( GetWindowThreadProcessId(hWnd, &dwProcessId) )
        {
          v6 = OpenProcess(0x1000u, 0, dwProcessId);
          v7 = v6;
          if ( v6 )
          {
            v11 = 0;
            if ( (unsigned int)GetProcessUIContextInformation(v6, &v11) )
              *a2 = v11 == 2;
            CloseHandle(v7);
          }
        }
      }
      else
      {
        *a2 = 1;
      }
    }
    hWnd = GetWindow(hWnd, 4u);
  }
  while ( !*a2 );
  return 0;
}

```

## disassembly

```asm
0x180076688  mov     [rsp+arg_10], rbx
0x18007668d  mov     [rsp+arg_18], rsi
0x180076692  push    rdi
0x180076693  sub     rsp, 270h
0x18007669a  mov     rax, cs:__security_cookie
0x1800766a1  xor     rax, rsp
0x1800766a4  mov     [rsp+278h+var_18], rax
0x1800766ac  mov     rsi, rdx
0x1800766af  mov     dword ptr [rdx], 0
0x1800766b5  mov     rbx, rcx
0x1800766b8  test    rbx, rbx
0x1800766bb  jz      loc_1800767B5
0x1800766c1  mov     r8d, 104h; nMaxCount
0x1800766c7  lea     rdx, [rsp+278h+ClassName]; lpClassName
0x1800766cc  mov     rcx, rbx; hWnd
0x1800766cf  call    cs:__imp_GetClassNameW
0x1800766d5  test    eax, eax
0x1800766d7  jle     loc_18007679B
0x1800766dd  or      r9d, 0FFFFFFFFh; cchCount2
0x1800766e1  mov     [rsp+278h+bIgnoreCase], 1; bIgnoreCase
0x1800766e9  or      edx, r9d; cchCount1
0x1800766ec  lea     r8, aApplicationhos; "ApplicationHostBridgeWindow"
0x1800766f3  lea     rcx, [rsp+278h+ClassName]; lpString1
0x1800766f8  call    cs:__imp_CompareStringOrdinal
0x1800766fe  cmp     eax, 2
0x180076701  jnz     loc_18007679B
0x180076707  mov     [rsp+278h+var_240], 0
0x180076710  call    cs:__imp_GetCurrentProcess
0x180076716  mov     rcx, rax
0x180076719  lea     rdx, [rsp+278h+var_240]
0x18007671e  call    cs:__imp_GetProcessUIContextInformation
0x180076724  test    eax, eax
0x180076726  jz      short loc_180076795
0x180076728  cmp     dword ptr [rsp+278h+var_240], 2
0x18007672d  jnz     short loc_180076795
0x18007672f  lea     rdx, [rsp+278h+dwProcessId]; lpdwProcessId
0x180076734  mov     [rsp+278h+dwProcessId], 0
0x18007673c  mov     rcx, rbx; hWnd
0x18007673f  call    cs:__imp_GetWindowThreadProcessId
0x180076745  test    eax, eax
0x180076747  jz      short loc_18007679B
0x180076749  mov     r8d, [rsp+278h+dwProcessId]; dwProcessId
0x18007674e  xor     edx, edx; bInheritHandle
0x180076750  mov     ecx, 1000h; dwDesiredAccess
0x180076755  call    cs:__imp_OpenProcess
0x18007675b  mov     rdi, rax
0x18007675e  test    rax, rax
0x180076761  jz      short loc_18007679B
0x180076763  lea     rdx, [rsp+278h+var_238]
0x180076768  mov     [rsp+278h+var_238], 0
0x180076771  mov     rcx, rax
0x180076774  call    cs:__imp_GetProcessUIContextInformation
0x18007677a  test    eax, eax
0x18007677c  jz      short loc_18007678A
0x18007677e  xor     ecx, ecx
0x180076780  cmp     dword ptr [rsp+278h+var_238], 2
0x180076785  setz    cl
0x180076788  mov     [rsi], ecx
0x18007678a  mov     rcx, rdi; hObject
0x18007678d  call    cs:__imp_CloseHandle
0x180076793  jmp     short loc_18007679B
0x180076795  mov     dword ptr [rsi], 1
0x18007679b  mov     edx, 4; uCmd
0x1800767a0  mov     rcx, rbx; hWnd
0x1800767a3  call    cs:__imp_GetWindow
0x1800767a9  cmp     dword ptr [rsi], 0
0x1800767ac  mov     rbx, rax
0x1800767af  jz      loc_1800766B8
0x1800767b5  xor     eax, eax
0x1800767b7  mov     rcx, [rsp+278h+var_18]
0x1800767bf  xor     rcx, rsp; StackCookie
0x1800767c2  call    __security_check_cookie
0x1800767c7  lea     r11, [rsp+278h+var_8]
0x1800767cf  mov     rbx, [r11+20h]
0x1800767d3  mov     rsi, [r11+28h]
0x1800767d7  mov     rsp, r11
0x1800767da  pop     rdi
0x1800767db  retn
```
