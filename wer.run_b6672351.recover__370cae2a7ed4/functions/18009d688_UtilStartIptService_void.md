# UtilStartIptService(void)

- ea: `0x18009d688`
- end: `0x18009d827`
- name: `?UtilStartIptService@@YA_NXZ`
- size: `415`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180092c2c`

## callees

- `0x180020680`
- `0x18009d688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d7c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d7c8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009d716`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009d716`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009d783`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009d783`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d7f6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d805`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d7f6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d805`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d6a1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d6a1`

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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, LastError);
        }
      }
      CloseServiceHandle(v5);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v6);
    }
    CloseServiceHandle(v2);
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v3 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v3);
  }
  return started;
}

```

## disassembly

```asm
0x18009d688  mov     [rsp+arg_0], rbx
0x18009d68d  mov     [rsp+arg_8], rsi
0x18009d692  push    rdi
0x18009d693  sub     rsp, 20h
0x18009d697  xor     ebx, ebx
0x18009d699  xor     edx, edx; lpDatabaseName
0x18009d69b  xor     ecx, ecx; lpMachineName
0x18009d69d  lea     r8d, [rbx+1]; dwDesiredAccess
0x18009d6a1  call    cs:__imp_OpenSCManagerW
0x18009d6a8  nop     dword ptr [rax+rax+00h]
0x18009d6ad  mov     rsi, rax
0x18009d6b0  test    rax, rax
0x18009d6b3  jnz     short loc_18009D706
0x18009d6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d6bc  lea     rax, WPP_GLOBAL_Control
0x18009d6c3  cmp     rcx, rax
0x18009d6c6  jz      loc_18009D811
0x18009d6cc  test    byte ptr [rcx+1Ch], 1
0x18009d6d0  jz      loc_18009D811
0x18009d6d6  call    cs:__imp_GetLastError
0x18009d6dd  nop     dword ptr [rax+rax+00h]
0x18009d6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d6e9  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009d6f0  mov     edx, 0ABh
0x18009d6f5  mov     r9d, eax
0x18009d6f8  mov     rcx, [rcx+10h]
0x18009d6fc  call    WPP_SF_d
0x18009d701  jmp     loc_18009D811
0x18009d706  mov     r8d, 10h; dwDesiredAccess
0x18009d70c  lea     rdx, aIpt_0; "Ipt"
0x18009d713  mov     rcx, rsi; hSCManager
0x18009d716  call    cs:__imp_OpenServiceW
0x18009d71d  nop     dword ptr [rax+rax+00h]
0x18009d722  mov     rdi, rax
0x18009d725  test    rax, rax
0x18009d728  jnz     short loc_18009D77B
0x18009d72a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d731  lea     rax, WPP_GLOBAL_Control
0x18009d738  cmp     rcx, rax
0x18009d73b  jz      loc_18009D802
0x18009d741  test    byte ptr [rcx+1Ch], 4
0x18009d745  jz      loc_18009D802
0x18009d74b  call    cs:__imp_GetLastError
0x18009d752  nop     dword ptr [rax+rax+00h]
0x18009d757  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d75e  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009d765  mov     edx, 0ACh
0x18009d76a  mov     r9d, eax
0x18009d76d  mov     rcx, [rcx+10h]
0x18009d771  call    WPP_SF_d
0x18009d776  jmp     loc_18009D802
0x18009d77b  xor     r8d, r8d; lpServiceArgVectors
0x18009d77e  xor     edx, edx; dwNumServiceArgs
0x18009d780  mov     rcx, rdi; hService
0x18009d783  call    cs:__imp_StartServiceW
0x18009d78a  nop     dword ptr [rax+rax+00h]
0x18009d78f  mov     ebx, eax
0x18009d791  test    eax, eax
0x18009d793  jnz     short loc_18009D7F3
0x18009d795  call    cs:__imp_GetLastError
0x18009d79c  nop     dword ptr [rax+rax+00h]
0x18009d7a1  cmp     eax, 420h
0x18009d7a6  jnz     short loc_18009D7AF
0x18009d7a8  mov     ebx, 1
0x18009d7ad  jmp     short loc_18009D7F3
0x18009d7af  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d7b6  lea     rax, WPP_GLOBAL_Control
0x18009d7bd  cmp     rcx, rax
0x18009d7c0  jz      short loc_18009D7F3
0x18009d7c2  test    byte ptr [rcx+1Ch], 4
0x18009d7c6  jz      short loc_18009D7F3
0x18009d7c8  call    cs:__imp_GetLastError
0x18009d7cf  nop     dword ptr [rax+rax+00h]
0x18009d7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d7db  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009d7e2  mov     edx, 0ADh
0x18009d7e7  mov     r9d, eax
0x18009d7ea  mov     rcx, [rcx+10h]
0x18009d7ee  call    WPP_SF_d
0x18009d7f3  mov     rcx, rdi; hSCObject
0x18009d7f6  call    cs:__imp_CloseServiceHandle
0x18009d7fd  nop     dword ptr [rax+rax+00h]
0x18009d802  mov     rcx, rsi; hSCObject
0x18009d805  call    cs:__imp_CloseServiceHandle
0x18009d80c  nop     dword ptr [rax+rax+00h]
0x18009d811  mov     rsi, [rsp+28h+arg_8]
0x18009d816  test    ebx, ebx
0x18009d818  mov     rbx, [rsp+28h+arg_0]
0x18009d81d  setnz   al
0x18009d820  add     rsp, 20h
0x18009d824  pop     rdi
0x18009d825  retn
```
