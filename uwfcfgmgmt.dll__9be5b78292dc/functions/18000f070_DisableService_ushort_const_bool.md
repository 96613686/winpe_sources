# DisableService(ushort const *,bool)

- ea: `0x18000f070`
- end: `0x18000f176`
- name: `?DisableService@@YAJPEBG_N@Z`
- size: `262`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned __int8)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000ef40`
- `0x18000f258`

## callees

- `0x18000f070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f144`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f15c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f165`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f15c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f165`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000f0ba`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000f0ba`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000f08b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000f08b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000f13a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18000f13a`

## pseudocode

```c
__int64 __fastcall DisableService(LPCWSTR lpServiceName, unsigned __int8 a2)
{
  int v2; // ebp
  unsigned int v4; // ebx
  SC_HANDLE v5; // rsi
  signed int LastError; // eax
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  signed int v9; // eax

  v2 = a2;
  v4 = 0;
  v5 = OpenSCManagerW(0, 0, 0x10000000u);
  if ( !v5 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  v7 = OpenServiceW(v5, lpServiceName, 0x10000000u);
  if ( !v7 )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( (_BYTE)v2 && v8 == 1060 )
    {
      v4 = 1;
      goto LABEL_13;
    }
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
  }
  if ( !ChangeServiceConfigW(v7, 0xFFFFFFFF, v2 + 3, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
  }
LABEL_13:
  CloseServiceHandle(v7);
  CloseServiceHandle(v5);
  return v4;
}

```

## disassembly

```asm
0x18000f070  push    rbx
0x18000f072  push    rbp
0x18000f073  push    rsi
0x18000f074  push    rdi
0x18000f075  sub     rsp, 68h
0x18000f079  movzx   ebp, dl
0x18000f07c  mov     rdi, rcx
0x18000f07f  xor     edx, edx; lpDatabaseName
0x18000f081  xor     ecx, ecx; lpMachineName
0x18000f083  mov     r8d, 10000000h; dwDesiredAccess
0x18000f089  xor     ebx, ebx
0x18000f08b  call    cs:__imp_OpenSCManagerW
0x18000f091  mov     rsi, rax
0x18000f094  test    rax, rax
0x18000f097  jnz     short loc_18000F0AE
0x18000f099  call    cs:__imp_GetLastError
0x18000f09f  mov     ebx, eax
0x18000f0a1  test    eax, eax
0x18000f0a3  jle     short loc_18000F0AE
0x18000f0a5  movzx   ebx, ax
0x18000f0a8  or      ebx, 80070000h
0x18000f0ae  mov     r8d, 10000000h; dwDesiredAccess
0x18000f0b4  mov     rdx, rdi; lpServiceName
0x18000f0b7  mov     rcx, rsi; hSCManager
0x18000f0ba  call    cs:__imp_OpenServiceW
0x18000f0c0  mov     rdi, rax
0x18000f0c3  test    rax, rax
0x18000f0c6  jnz     short loc_18000F0EE
0x18000f0c8  call    cs:__imp_GetLastError
0x18000f0ce  mov     ebx, eax
0x18000f0d0  test    bpl, bpl
0x18000f0d3  jz      short loc_18000F0E1
0x18000f0d5  cmp     eax, 424h
0x18000f0da  jnz     short loc_18000F0E1
0x18000f0dc  lea     ebx, [rdi+1]
0x18000f0df  jmp     short loc_18000F159
0x18000f0e1  test    eax, eax
0x18000f0e3  jle     short loc_18000F0EE
0x18000f0e5  movzx   ebx, ax
0x18000f0e8  or      ebx, 80070000h
0x18000f0ee  mov     [rsp+88h+lpDisplayName], 0; lpDisplayName
0x18000f0f7  lea     r8d, [rbp+3]; dwStartType
0x18000f0fb  mov     [rsp+88h+lpPassword], 0; lpPassword
0x18000f104  or      edx, 0FFFFFFFFh; dwServiceType
0x18000f107  mov     [rsp+88h+lpServiceStartName], 0; lpServiceStartName
0x18000f110  mov     r9d, edx; dwErrorControl
0x18000f113  mov     [rsp+88h+lpDependencies], 0; lpDependencies
0x18000f11c  mov     rcx, rdi; hService
0x18000f11f  mov     [rsp+88h+lpdwTagId], 0; lpdwTagId
0x18000f128  mov     [rsp+88h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18000f131  mov     [rsp+88h+lpBinaryPathName], 0; lpBinaryPathName
0x18000f13a  call    cs:__imp_ChangeServiceConfigW
0x18000f140  test    eax, eax
0x18000f142  jnz     short loc_18000F159
0x18000f144  call    cs:__imp_GetLastError
0x18000f14a  mov     ebx, eax
0x18000f14c  test    eax, eax
0x18000f14e  jle     short loc_18000F159
0x18000f150  movzx   ebx, ax
0x18000f153  or      ebx, 80070000h
0x18000f159  mov     rcx, rdi; hSCObject
0x18000f15c  call    cs:__imp_CloseServiceHandle
0x18000f162  mov     rcx, rsi; hSCObject
0x18000f165  call    cs:__imp_CloseServiceHandle
0x18000f16b  mov     eax, ebx
0x18000f16d  add     rsp, 68h
0x18000f171  pop     rdi
0x18000f172  pop     rsi
0x18000f173  pop     rbp
0x18000f174  pop     rbx
0x18000f175  retn
```
