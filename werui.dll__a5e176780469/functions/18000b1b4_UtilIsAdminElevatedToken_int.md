# UtilIsAdminElevatedToken(int *)

- ea: `0x18000b1b4`
- end: `0x18000b280`
- name: `?UtilIsAdminElevatedToken@@YAJPEAH@Z`
- size: `204`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000b82c`

## callees

- `0x180003fe4`
- `0x180005c58`
- `0x180005ddc`
- `0x18000b1b4`
- `0x18000b288`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x18000b20c`
- `ADVAPI32!OpenProcessToken` at `0x18000b20c`
- `KERNEL32!GetCurrentProcess` at `0x18000b1fb`
- `KERNEL32!GetCurrentProcess` at `0x18000b1fb`
- `KERNEL32!GetLastError` at `0x18000b216`
- `KERNEL32!GetLastError` at `0x18000b216`

## pseudocode

```c
__int64 __fastcall UtilIsAdminElevatedToken(int *a1)
{
  unsigned int v2; // ebx
  void **v3; // rbx
  HANDLE CurrentProcess; // rax
  int *v5; // r9
  DWORD LastError; // eax
  NTSTATUS v7; // ebx
  BOOL v8; // eax
  int v10; // [rsp+30h] [rbp+8h] BYREF
  int v11; // [rsp+38h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  v11 = 0;
  v10 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v3 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, v3) )
    {
      v7 = _werDetail::UtilLUAIsElevatedToken(TokenHandle, &v11, &v10, v5);
      if ( (v7 & 0xC0000000) == 0xC0000000 )
      {
        v2 = v7 | 0x10000000;
      }
      else
      {
        v8 = v10 && v11;
        *a1 = v8;
        v2 = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = ERROR_HR_FROM_WIN32(LastError);
    }
  }
  else
  {
    v2 = -2147024809;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18000b1b4  mov     rax, rsp
0x18000b1b7  mov     [rax+20h], rbx
0x18000b1bb  push    rdi
0x18000b1bc  sub     rsp, 20h
0x18000b1c0  mov     qword ptr [rax+18h], 0
0x18000b1c8  mov     rdi, rcx
0x18000b1cb  mov     dword ptr [rax+10h], 0
0x18000b1d2  mov     dword ptr [rax+8], 0
0x18000b1d9  test    rcx, rcx
0x18000b1dc  jnz     short loc_18000B1E8
0x18000b1de  mov     ebx, 80070057h
0x18000b1e3  jmp     loc_18000B269
0x18000b1e8  mov     dword ptr [rcx], 0
0x18000b1ee  lea     rcx, [rsp+28h+TokenHandle]
0x18000b1f3  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000b1f8  mov     rbx, rax
0x18000b1fb  call    cs:__imp_GetCurrentProcess
0x18000b201  mov     r8, rbx; TokenHandle
0x18000b204  mov     edx, 8; DesiredAccess
0x18000b209  mov     rcx, rax; ProcessHandle
0x18000b20c  call    cs:__imp_OpenProcessToken
0x18000b212  test    eax, eax
0x18000b214  jnz     short loc_18000B227
0x18000b216  call    cs:__imp_GetLastError
0x18000b21c  mov     ecx, eax; unsigned int
0x18000b21e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000b223  mov     ebx, eax
0x18000b225  jmp     short loc_18000B269
0x18000b227  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18000b22c  lea     r8, [rsp+28h+arg_0]; int *
0x18000b231  lea     rdx, [rsp+28h+arg_8]; void *
0x18000b236  call    ?UtilLUAIsElevatedToken@_werDetail@@YAJPEAXPEAH1@Z; _werDetail::UtilLUAIsElevatedToken(void *,int *,int *)
0x18000b23b  mov     ecx, 0C0000000h
0x18000b240  mov     ebx, eax
0x18000b242  and     eax, ecx
0x18000b244  cmp     eax, ecx
0x18000b246  jnz     short loc_18000B24E
0x18000b248  bts     ebx, 1Ch
0x18000b24c  jmp     short loc_18000B269
0x18000b24e  cmp     [rsp+28h+arg_0], 0
0x18000b253  jz      short loc_18000B263
0x18000b255  cmp     [rsp+28h+arg_8], 0
0x18000b25a  jz      short loc_18000B263
0x18000b25c  mov     eax, 1
0x18000b261  jmp     short loc_18000B265
0x18000b263  xor     eax, eax
0x18000b265  mov     [rdi], eax
0x18000b267  xor     ebx, ebx
0x18000b269  lea     rcx, [rsp+28h+TokenHandle]
0x18000b26e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18000b273  mov     eax, ebx
0x18000b275  mov     rbx, [rsp+28h+arg_18]
0x18000b27a  add     rsp, 20h
0x18000b27e  pop     rdi
0x18000b27f  retn
```
