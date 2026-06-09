# CallerIdentity::IsHostedWindow(HWND__ *,int *)

- ea: `0x1800e00b8`
- end: `0x1800e0247`
- name: `?IsHostedWindow@CallerIdentity@@YAJPEAUHWND__@@PEAH@Z`
- size: `399`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086280`

## callees

- `0x180054130`
- `0x1800e00b8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e012e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e012e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e014c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e014c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e01a7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e01a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e01eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e01eb`
- `USER32!GetClassNameW` at `0x1800e00ff`
- `USER32!GetClassNameW` at `0x1800e00ff`
- `USER32!GetWindow` at `0x1800e0207`
- `USER32!GetWindow` at `0x1800e0207`
- `USER32!GetWindowThreadProcessId` at `0x1800e018b`
- `USER32!GetWindowThreadProcessId` at `0x1800e018b`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800e0160`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800e01cc`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800e0160`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800e01cc`

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
0x1800e00b8  mov     [rsp+arg_10], rbx
0x1800e00bd  mov     [rsp+arg_18], rsi
0x1800e00c2  push    rdi
0x1800e00c3  sub     rsp, 270h
0x1800e00ca  mov     rax, cs:__security_cookie
0x1800e00d1  xor     rax, rsp
0x1800e00d4  mov     [rsp+278h+var_18], rax
0x1800e00dc  mov     rsi, rdx
0x1800e00df  mov     dword ptr [rdx], 0
0x1800e00e5  mov     rbx, rcx
0x1800e00e8  test    rbx, rbx
0x1800e00eb  jz      loc_1800E021F
0x1800e00f1  mov     r8d, 104h; nMaxCount
0x1800e00f7  lea     rdx, [rsp+278h+ClassName]; lpClassName
0x1800e00fc  mov     rcx, rbx; hWnd
0x1800e00ff  call    cs:__imp_GetClassNameW
0x1800e0106  nop     dword ptr [rax+rax+00h]
0x1800e010b  test    eax, eax
0x1800e010d  jle     loc_1800E01FF
0x1800e0113  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e0117  mov     [rsp+278h+bIgnoreCase], 1; bIgnoreCase
0x1800e011f  or      edx, r9d; cchCount1
0x1800e0122  lea     r8, aApplicationhos; "ApplicationHostBridgeWindow"
0x1800e0129  lea     rcx, [rsp+278h+ClassName]; lpString1
0x1800e012e  call    cs:__imp_CompareStringOrdinal
0x1800e0135  nop     dword ptr [rax+rax+00h]
0x1800e013a  cmp     eax, 2
0x1800e013d  jnz     loc_1800E01FF
0x1800e0143  mov     [rsp+278h+var_240], 0
0x1800e014c  call    cs:__imp_GetCurrentProcess
0x1800e0153  nop     dword ptr [rax+rax+00h]
0x1800e0158  mov     rcx, rax
0x1800e015b  lea     rdx, [rsp+278h+var_240]
0x1800e0160  call    cs:__imp_GetProcessUIContextInformation
0x1800e0167  nop     dword ptr [rax+rax+00h]
0x1800e016c  test    eax, eax
0x1800e016e  jz      loc_1800E01F9
0x1800e0174  cmp     dword ptr [rsp+278h+var_240], 2
0x1800e0179  jnz     short loc_1800E01F9
0x1800e017b  lea     rdx, [rsp+278h+dwProcessId]; lpdwProcessId
0x1800e0180  mov     [rsp+278h+dwProcessId], 0
0x1800e0188  mov     rcx, rbx; hWnd
0x1800e018b  call    cs:__imp_GetWindowThreadProcessId
0x1800e0192  nop     dword ptr [rax+rax+00h]
0x1800e0197  test    eax, eax
0x1800e0199  jz      short loc_1800E01FF
0x1800e019b  mov     r8d, [rsp+278h+dwProcessId]; dwProcessId
0x1800e01a0  xor     edx, edx; bInheritHandle
0x1800e01a2  mov     ecx, 1000h; dwDesiredAccess
0x1800e01a7  call    cs:__imp_OpenProcess
0x1800e01ae  nop     dword ptr [rax+rax+00h]
0x1800e01b3  mov     rdi, rax
0x1800e01b6  test    rax, rax
0x1800e01b9  jz      short loc_1800E01FF
0x1800e01bb  lea     rdx, [rsp+278h+var_238]
0x1800e01c0  mov     [rsp+278h+var_238], 0
0x1800e01c9  mov     rcx, rax
0x1800e01cc  call    cs:__imp_GetProcessUIContextInformation
0x1800e01d3  nop     dword ptr [rax+rax+00h]
0x1800e01d8  test    eax, eax
0x1800e01da  jz      short loc_1800E01E8
0x1800e01dc  xor     ecx, ecx
0x1800e01de  cmp     dword ptr [rsp+278h+var_238], 2
0x1800e01e3  setz    cl
0x1800e01e6  mov     [rsi], ecx
0x1800e01e8  mov     rcx, rdi; hObject
0x1800e01eb  call    cs:__imp_CloseHandle
0x1800e01f2  nop     dword ptr [rax+rax+00h]
0x1800e01f7  jmp     short loc_1800E01FF
0x1800e01f9  mov     dword ptr [rsi], 1
0x1800e01ff  mov     edx, 4; uCmd
0x1800e0204  mov     rcx, rbx; hWnd
0x1800e0207  call    cs:__imp_GetWindow
0x1800e020e  nop     dword ptr [rax+rax+00h]
0x1800e0213  cmp     dword ptr [rsi], 0
0x1800e0216  mov     rbx, rax
0x1800e0219  jz      loc_1800E00E8
0x1800e021f  xor     eax, eax
0x1800e0221  mov     rcx, [rsp+278h+var_18]
0x1800e0229  xor     rcx, rsp; StackCookie
0x1800e022c  call    __security_check_cookie
0x1800e0231  lea     r11, [rsp+278h+var_8]
0x1800e0239  mov     rbx, [r11+20h]
0x1800e023d  mov     rsi, [r11+28h]
0x1800e0241  mov     rsp, r11
0x1800e0244  pop     rdi
0x1800e0245  retn
```
