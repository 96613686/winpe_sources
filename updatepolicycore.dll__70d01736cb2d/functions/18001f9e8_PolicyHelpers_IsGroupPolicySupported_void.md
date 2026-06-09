# PolicyHelpers::IsGroupPolicySupported(void)

- ea: `0x18001f9e8`
- end: `0x18001faa5`
- name: `?IsGroupPolicySupported@PolicyHelpers@@SA_NXZ`
- size: `189`
- prototype: `char(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180016f10`
- `0x180016f30`
- `0x18001a320`

## callees

- `0x18001f9e8`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001fa6f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001fa6f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001fa35`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001fa35`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fa7c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fa85`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fa7c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001fa85`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001fa50`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001fa50`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001fa18`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001fa18`

## string_xrefs

- `0x18001fa2c`: `ServicesActive`

## pseudocode

```c
char PolicyHelpers::IsGroupPolicySupported(void)
{
  char v0; // bl
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  int v5; // [rsp+20h] [rbp-18h] BYREF

  v5 = 0;
  v0 = 1;
  RtlGetDeviceFamilyInfoEnum(0, &v5, 0);
  if ( v5 == 16 )
    return 0;
  v1 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"gpsvc", 1u);
    if ( v3 )
    {
      CloseServiceHandle(v3);
    }
    else if ( GetLastError() == 1060 )
    {
      OutputDebugStringW(L"gpsvc does NOT EXIST\n");
      v0 = 0;
    }
    CloseServiceHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18001f9e8  mov     [rsp+arg_0], rbx
0x18001f9ed  push    rdi
0x18001f9ee  sub     rsp, 30h
0x18001f9f2  mov     rax, cs:__security_cookie
0x18001f9f9  xor     rax, rsp
0x18001f9fc  mov     [rsp+38h+var_10], rax
0x18001fa01  xor     r8d, r8d
0x18001fa04  mov     [rsp+38h+var_18], 0
0x18001fa0c  lea     rdx, [rsp+38h+var_18]
0x18001fa11  xor     ecx, ecx
0x18001fa13  mov     ebx, 1
0x18001fa18  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001fa1e  cmp     [rsp+38h+var_18], 10h
0x18001fa23  jnz     short loc_18001FA29
0x18001fa25  xor     bl, bl
0x18001fa27  jmp     short loc_18001FA8B
0x18001fa29  mov     r8d, ebx; dwDesiredAccess
0x18001fa2c  lea     rdx, DatabaseName; "ServicesActive"
0x18001fa33  xor     ecx, ecx; lpMachineName
0x18001fa35  call    cs:__imp_OpenSCManagerW
0x18001fa3b  mov     rdi, rax
0x18001fa3e  test    rax, rax
0x18001fa41  jz      short loc_18001FA8B
0x18001fa43  mov     r8d, ebx; dwDesiredAccess
0x18001fa46  lea     rdx, ServiceName; "gpsvc"
0x18001fa4d  mov     rcx, rax; hSCManager
0x18001fa50  call    cs:__imp_OpenServiceW
0x18001fa56  test    rax, rax
0x18001fa59  jnz     short loc_18001FA79
0x18001fa5b  call    cs:__imp_GetLastError
0x18001fa61  cmp     eax, 424h
0x18001fa66  jnz     short loc_18001FA82
0x18001fa68  lea     rcx, aGpsvcDoesNotEx; "gpsvc does NOT EXIST\n"
0x18001fa6f  call    cs:__imp_OutputDebugStringW
0x18001fa75  xor     bl, bl
0x18001fa77  jmp     short loc_18001FA82
0x18001fa79  mov     rcx, rax; hSCObject
0x18001fa7c  call    cs:__imp_CloseServiceHandle
0x18001fa82  mov     rcx, rdi; hSCObject
0x18001fa85  call    cs:__imp_CloseServiceHandle
0x18001fa8b  mov     al, bl
0x18001fa8d  mov     rcx, [rsp+38h+var_10]
0x18001fa92  xor     rcx, rsp; StackCookie
0x18001fa95  call    __security_check_cookie
0x18001fa9a  mov     rbx, [rsp+38h+arg_0]
0x18001fa9f  add     rsp, 30h
0x18001faa3  pop     rdi
0x18001faa4  retn
```
