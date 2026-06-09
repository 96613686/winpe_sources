# CServiceControlInterface::EnableDisable(ushort const *,int)

- ea: `0x18001dea4`
- end: `0x18001df5c`
- name: `?EnableDisable@CServiceControlInterface@@AEAAKPEBGH@Z`
- size: `184`
- prototype: `unsigned int __fastcall(CServiceControlInterface *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001de70`
- `0x18001de90`

## callees

- `0x18001dea4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ded3`
- `KERNEL32!GetLastError` at `0x18001df2c`
- `KERNEL32!GetLastError` at `0x18001ded3`
- `KERNEL32!GetLastError` at `0x18001df2c`
- `ADVAPI32!CloseServiceHandle` at `0x18001df3d`
- `ADVAPI32!CloseServiceHandle` at `0x18001df3d`
- `ADVAPI32!OpenServiceW` at `0x18001debf`
- `ADVAPI32!OpenServiceW` at `0x18001debf`
- `ADVAPI32!ChangeServiceConfigW` at `0x18001df1c`
- `ADVAPI32!ChangeServiceConfigW` at `0x18001df1c`

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
0x18001dea4  mov     [rsp+arg_0], rbx
0x18001dea9  mov     [rsp+arg_8], rsi
0x18001deae  push    rdi
0x18001deaf  sub     rsp, 60h
0x18001deb3  mov     rcx, [rcx]; hSCManager
0x18001deb6  mov     esi, r8d
0x18001deb9  xor     ebx, ebx
0x18001debb  lea     r8d, [rbx+2]; dwDesiredAccess
0x18001debf  call    cs:__imp_OpenServiceW
0x18001dec6  nop     dword ptr [rax+rax+00h]
0x18001decb  mov     rdi, rax
0x18001dece  test    rax, rax
0x18001ded1  jnz     short loc_18001DEE3
0x18001ded3  call    cs:__imp_GetLastError
0x18001deda  nop     dword ptr [rax+rax+00h]
0x18001dedf  mov     ebx, eax
0x18001dee1  jmp     short loc_18001DF49
0x18001dee3  mov     [rsp+68h+lpDisplayName], rbx; lpDisplayName
0x18001dee8  neg     esi
0x18001deea  mov     [rsp+68h+lpPassword], rbx; lpPassword
0x18001deef  mov     rcx, rdi; hService
0x18001def2  sbb     r8d, r8d
0x18001def5  mov     [rsp+68h+lpServiceStartName], rbx; lpServiceStartName
0x18001defa  mov     [rsp+68h+lpDependencies], rbx; lpDependencies
0x18001deff  and     r8d, 0FFFFFFFEh
0x18001df03  or      edx, 0FFFFFFFFh; dwServiceType
0x18001df06  mov     [rsp+68h+lpdwTagId], rbx; lpdwTagId
0x18001df0b  add     r8d, 4; dwStartType
0x18001df0f  mov     [rsp+68h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x18001df14  mov     r9d, edx; dwErrorControl
0x18001df17  mov     [rsp+68h+lpBinaryPathName], rbx; lpBinaryPathName
0x18001df1c  call    cs:__imp_ChangeServiceConfigW
0x18001df23  nop     dword ptr [rax+rax+00h]
0x18001df28  test    eax, eax
0x18001df2a  jnz     short loc_18001DF3A
0x18001df2c  call    cs:__imp_GetLastError
0x18001df33  nop     dword ptr [rax+rax+00h]
0x18001df38  mov     ebx, eax
0x18001df3a  mov     rcx, rdi; hSCObject
0x18001df3d  call    cs:__imp_CloseServiceHandle
0x18001df44  nop     dword ptr [rax+rax+00h]
0x18001df49  mov     rsi, [rsp+68h+arg_8]
0x18001df4e  mov     eax, ebx
0x18001df50  mov     rbx, [rsp+68h+arg_0]
0x18001df55  add     rsp, 60h
0x18001df59  pop     rdi
0x18001df5a  retn
```
