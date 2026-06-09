# CServiceControlInterface::EnableDisable(ushort const *,int)

- ea: `0x18001cf44`
- end: `0x18001cffc`
- name: `?EnableDisable@CServiceControlInterface@@AEAAKPEBGH@Z`
- size: `184`
- prototype: `unsigned int __fastcall(CServiceControlInterface *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001cf10`
- `0x18001cf30`

## callees

- `0x18001cf44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001cf73`
- `KERNEL32!GetLastError` at `0x18001cfcc`
- `KERNEL32!GetLastError` at `0x18001cf73`
- `KERNEL32!GetLastError` at `0x18001cfcc`
- `ADVAPI32!ChangeServiceConfigW` at `0x18001cfbc`
- `ADVAPI32!ChangeServiceConfigW` at `0x18001cfbc`
- `ADVAPI32!OpenServiceW` at `0x18001cf5f`
- `ADVAPI32!OpenServiceW` at `0x18001cf5f`
- `ADVAPI32!CloseServiceHandle` at `0x18001cfdd`
- `ADVAPI32!CloseServiceHandle` at `0x18001cfdd`

## pseudocode

```c
__int64 __fastcall CServiceControlInterface::EnableDisable(SC_HANDLE *this, const unsigned __int16 *a2, int a3)
{
  DWORD LastError; // ebx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi

  LastError = 0;
  v5 = OpenServiceW(*this, a2, 2u);
  v6 = v5;
  if ( v5 )
  {
    if ( !ChangeServiceConfigW(v5, 0xFFFFFFFF, a3 != 0 ? 2 : 4, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      LastError = GetLastError();
    CloseServiceHandle(v6);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18001cf44  mov     [rsp+arg_0], rbx
0x18001cf49  mov     [rsp+arg_8], rsi
0x18001cf4e  push    rdi
0x18001cf4f  sub     rsp, 60h
0x18001cf53  mov     rcx, [rcx]; hSCManager
0x18001cf56  mov     esi, r8d
0x18001cf59  xor     ebx, ebx
0x18001cf5b  lea     r8d, [rbx+2]; dwDesiredAccess
0x18001cf5f  call    cs:__imp_OpenServiceW
0x18001cf66  nop     dword ptr [rax+rax+00h]
0x18001cf6b  mov     rdi, rax
0x18001cf6e  test    rax, rax
0x18001cf71  jnz     short loc_18001CF83
0x18001cf73  call    cs:__imp_GetLastError
0x18001cf7a  nop     dword ptr [rax+rax+00h]
0x18001cf7f  mov     ebx, eax
0x18001cf81  jmp     short loc_18001CFE9
0x18001cf83  mov     [rsp+68h+lpDisplayName], rbx; lpDisplayName
0x18001cf88  neg     esi
0x18001cf8a  mov     [rsp+68h+lpPassword], rbx; lpPassword
0x18001cf8f  mov     rcx, rdi; hService
0x18001cf92  sbb     r8d, r8d
0x18001cf95  mov     [rsp+68h+lpServiceStartName], rbx; lpServiceStartName
0x18001cf9a  mov     [rsp+68h+lpDependencies], rbx; lpDependencies
0x18001cf9f  and     r8d, 0FFFFFFFEh
0x18001cfa3  or      edx, 0FFFFFFFFh; dwServiceType
0x18001cfa6  mov     [rsp+68h+lpdwTagId], rbx; lpdwTagId
0x18001cfab  add     r8d, 4; dwStartType
0x18001cfaf  mov     [rsp+68h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x18001cfb4  mov     r9d, edx; dwErrorControl
0x18001cfb7  mov     [rsp+68h+lpBinaryPathName], rbx; lpBinaryPathName
0x18001cfbc  call    cs:__imp_ChangeServiceConfigW
0x18001cfc3  nop     dword ptr [rax+rax+00h]
0x18001cfc8  test    eax, eax
0x18001cfca  jnz     short loc_18001CFDA
0x18001cfcc  call    cs:__imp_GetLastError
0x18001cfd3  nop     dword ptr [rax+rax+00h]
0x18001cfd8  mov     ebx, eax
0x18001cfda  mov     rcx, rdi; hSCObject
0x18001cfdd  call    cs:__imp_CloseServiceHandle
0x18001cfe4  nop     dword ptr [rax+rax+00h]
0x18001cfe9  mov     rsi, [rsp+68h+arg_8]
0x18001cfee  mov     eax, ebx
0x18001cff0  mov     rbx, [rsp+68h+arg_0]
0x18001cff5  add     rsp, 60h
0x18001cff9  pop     rdi
0x18001cffa  retn
```
