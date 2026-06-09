# UtilStartIptService(void)

- ea: `0x1800990b0`
- end: `0x180099215`
- name: `?UtilStartIptService@@YA_NXZ`
- size: `357`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18008eb7c`

## callees

- `0x18001fe24`
- `0x1800990b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800990f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009919c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800991c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800990f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009919c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800991c9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180099132`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180099132`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180099190`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180099190`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991f1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991fa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991f1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800991fa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800990c9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800990c9`

## pseudocode

```c
bool UtilStartIptService(void)
{
  BOOL started; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD v3; // eax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  DWORD v6; // eax
  DWORD LastError; // eax

  started = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v4 = OpenServiceW(v1, L"Ipt", 0x10u);
    v5 = v4;
    if ( v4 )
    {
      started = StartServiceW(v4, 0, 0);
      if ( !started )
      {
        if ( GetLastError() == 1056 )
        {
          started = 1;
        }
        else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
        }
      }
      CloseServiceHandle(v5);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    }
    CloseServiceHandle(v2);
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v3 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v3);
  }
  return started;
}

```

## disassembly

```asm
0x1800990b0  mov     [rsp+arg_0], rbx
0x1800990b5  mov     [rsp+arg_8], rsi
0x1800990ba  push    rdi
0x1800990bb  sub     rsp, 20h
0x1800990bf  xor     ebx, ebx
0x1800990c1  xor     edx, edx; lpDatabaseName
0x1800990c3  xor     ecx, ecx; lpMachineName
0x1800990c5  lea     r8d, [rbx+1]; dwDesiredAccess
0x1800990c9  call    cs:__imp_OpenSCManagerW
0x1800990cf  mov     rsi, rax
0x1800990d2  test    rax, rax
0x1800990d5  jnz     short loc_180099122
0x1800990d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800990de  lea     rax, WPP_GLOBAL_Control
0x1800990e5  cmp     rcx, rax
0x1800990e8  jz      loc_180099200
0x1800990ee  test    byte ptr [rcx+1Ch], 1
0x1800990f2  jz      loc_180099200
0x1800990f8  call    cs:__imp_GetLastError
0x1800990fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180099105  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009910c  mov     edx, 0ABh
0x180099111  mov     r9d, eax
0x180099114  mov     rcx, [rcx+10h]
0x180099118  call    WPP_SF_d
0x18009911d  jmp     loc_180099200
0x180099122  mov     r8d, 10h; dwDesiredAccess
0x180099128  lea     rdx, aIpt_0; "Ipt"
0x18009912f  mov     rcx, rsi; hSCManager
0x180099132  call    cs:__imp_OpenServiceW
0x180099138  mov     rdi, rax
0x18009913b  test    rax, rax
0x18009913e  jnz     short loc_180099188
0x180099140  mov     rcx, cs:WPP_GLOBAL_Control
0x180099147  lea     rax, WPP_GLOBAL_Control
0x18009914e  cmp     rcx, rax
0x180099151  jz      loc_1800991F7
0x180099157  test    byte ptr [rcx+1Ch], 4
0x18009915b  jz      loc_1800991F7
0x180099161  call    cs:__imp_GetLastError
0x180099167  mov     rcx, cs:WPP_GLOBAL_Control
0x18009916e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180099175  mov     edx, 0ACh
0x18009917a  mov     r9d, eax
0x18009917d  mov     rcx, [rcx+10h]
0x180099181  call    WPP_SF_d
0x180099186  jmp     short loc_1800991F7
0x180099188  xor     r8d, r8d; lpServiceArgVectors
0x18009918b  xor     edx, edx; dwNumServiceArgs
0x18009918d  mov     rcx, rdi; hService
0x180099190  call    cs:__imp_StartServiceW
0x180099196  mov     ebx, eax
0x180099198  test    eax, eax
0x18009919a  jnz     short loc_1800991EE
0x18009919c  call    cs:__imp_GetLastError
0x1800991a2  cmp     eax, 420h
0x1800991a7  jnz     short loc_1800991B0
0x1800991a9  mov     ebx, 1
0x1800991ae  jmp     short loc_1800991EE
0x1800991b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800991b7  lea     rax, WPP_GLOBAL_Control
0x1800991be  cmp     rcx, rax
0x1800991c1  jz      short loc_1800991EE
0x1800991c3  test    byte ptr [rcx+1Ch], 4
0x1800991c7  jz      short loc_1800991EE
0x1800991c9  call    cs:__imp_GetLastError
0x1800991cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800991d6  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800991dd  mov     edx, 0ADh
0x1800991e2  mov     r9d, eax
0x1800991e5  mov     rcx, [rcx+10h]
0x1800991e9  call    WPP_SF_d
0x1800991ee  mov     rcx, rdi; hSCObject
0x1800991f1  call    cs:__imp_CloseServiceHandle
0x1800991f7  mov     rcx, rsi; hSCObject
0x1800991fa  call    cs:__imp_CloseServiceHandle
0x180099200  mov     rsi, [rsp+28h+arg_8]
0x180099205  test    ebx, ebx
0x180099207  mov     rbx, [rsp+28h+arg_0]
0x18009920c  setnz   al
0x18009920f  add     rsp, 20h
0x180099213  pop     rdi
0x180099214  retn
```
