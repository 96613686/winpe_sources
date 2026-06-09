# SsCheckAccessForShareChange

- ea: `0x18002b1dc`
- end: `0x18002b30b`
- name: `SsCheckAccessForShareChange`
- size: `303`
- prototype: `__int64 __fastcall(const WCHAR *, void *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003f60`
- `0x18002949c`
- `0x180029884`
- `0x18002abf0`

## callees

- `0x18000a370`
- `0x18000a460`
- `0x180020de8`
- `0x1800215e8`
- `0x18002b1dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b2da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b2da`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b27d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b27d`
- `RPCRT4!RpcImpersonateClient` at `0x18002b20d`
- `RPCRT4!RpcImpersonateClient` at `0x18002b20d`
- `RPCRT4!RpcRevertToSelf` at `0x18002b2cc`
- `RPCRT4!RpcRevertToSelf` at `0x18002b2e0`
- `RPCRT4!RpcRevertToSelf` at `0x18002b2cc`
- `RPCRT4!RpcRevertToSelf` at `0x18002b2e0`

## pseudocode

```c
__int64 __fastcall SsCheckAccessForShareChange(const WCHAR *a1, void *a2)
{
  int DriveType; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  DWORD LastError; // eax

  DriveType = SsGetDriveType(a2);
  if ( DriveType != 2 && DriveType != 5 )
  {
    v5 = RpcImpersonateClient(0);
    v6 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids, v5);
      }
      return v6;
    }
    FileW = CreateFileW((LPCWSTR)a2, 0x81u, 3u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids,
          (_DWORD)a2,
          LastError);
      }
      RpcRevertToSelf();
      return v6;
    }
    CloseHandle(FileW);
    RpcRevertToSelf();
  }
  return SsCheckAccess((__int64)SsShareChangeSecurityObject, a1, 0x10u);
}

```

## disassembly

```asm
0x18002b1dc  mov     [rsp+arg_0], rbx
0x18002b1e1  mov     [rsp+arg_8], rsi
0x18002b1e6  push    rdi
0x18002b1e7  sub     rsp, 40h
0x18002b1eb  mov     rsi, rcx
0x18002b1ee  mov     rdi, rdx
0x18002b1f1  mov     rcx, rdx; Src
0x18002b1f4  call    SsGetDriveType
0x18002b1f9  cmp     eax, 2
0x18002b1fc  jz      loc_18002B2E6
0x18002b202  cmp     eax, 5
0x18002b205  jz      loc_18002B2E6
0x18002b20b  xor     ecx, ecx; BindingHandle
0x18002b20d  call    cs:__imp_RpcImpersonateClient
0x18002b213  mov     ebx, eax
0x18002b215  test    eax, eax
0x18002b217  jz      short loc_18002B257
0x18002b219  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b220  lea     rdx, WPP_GLOBAL_Control
0x18002b227  cmp     rcx, rdx
0x18002b22a  jz      short loc_18002B250
0x18002b22c  test    byte ptr [rcx+1Ch], 4
0x18002b230  jz      short loc_18002B250
0x18002b232  cmp     byte ptr [rcx+19h], 1
0x18002b236  jb      short loc_18002B250
0x18002b238  mov     rcx, [rcx+10h]
0x18002b23c  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x18002b243  mov     edx, 29h ; ')'
0x18002b248  mov     r9d, eax
0x18002b24b  call    WPP_SF_d
0x18002b250  mov     eax, ebx
0x18002b252  jmp     loc_18002B2FB
0x18002b257  mov     r8d, 3; dwShareMode
0x18002b25d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002b266  mov     [rsp+48h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002b26e  xor     r9d, r9d; lpSecurityAttributes
0x18002b271  mov     rcx, rdi; lpFileName
0x18002b274  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002b279  lea     edx, [r8+7Eh]; dwDesiredAccess
0x18002b27d  call    cs:__imp_CreateFileW
0x18002b283  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b287  jnz     short loc_18002B2D7
0x18002b289  call    cs:__imp_GetLastError
0x18002b28f  mov     ebx, eax
0x18002b291  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b298  lea     rdx, WPP_GLOBAL_Control
0x18002b29f  cmp     rcx, rdx
0x18002b2a2  jz      short loc_18002B2CC
0x18002b2a4  test    byte ptr [rcx+1Ch], 4
0x18002b2a8  jz      short loc_18002B2CC
0x18002b2aa  cmp     byte ptr [rcx+19h], 1
0x18002b2ae  jb      short loc_18002B2CC
0x18002b2b0  mov     rcx, [rcx+10h]
0x18002b2b4  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x18002b2bb  mov     edx, 2Ah ; '*'
0x18002b2c0  mov     [rsp+48h+dwCreationDisposition], eax
0x18002b2c4  mov     r9, rdi
0x18002b2c7  call    WPP_SF_Sd
0x18002b2cc  call    cs:__imp_RpcRevertToSelf
0x18002b2d2  jmp     loc_18002B250
0x18002b2d7  mov     rcx, rax; hObject
0x18002b2da  call    cs:__imp_CloseHandle
0x18002b2e0  call    cs:__imp_RpcRevertToSelf
0x18002b2e6  mov     r8d, 10h
0x18002b2ec  lea     rcx, SsShareChangeSecurityObject
0x18002b2f3  mov     rdx, rsi
0x18002b2f6  call    SsCheckAccess
0x18002b2fb  mov     rbx, [rsp+48h+arg_0]
0x18002b300  mov     rsi, [rsp+48h+arg_8]
0x18002b305  add     rsp, 40h
0x18002b309  pop     rdi
0x18002b30a  retn
```
