# _anonymous_namespace_::security_process_close

- ea: `0x180082ba0`
- end: `0x180082c24`
- name: `_anonymous_namespace_::security_process_close`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008660`
- `0x180082ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180082bc4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180082bc4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082bd4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082bd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082c08`

## string_xrefs

- `0x180082ba6`: `security.process`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::security_process_close(struct lua_State *a1)
{
  HANDLE *v1; // rbx
  HANDLE v2; // rcx
  HANDLE v3; // rcx
  __int64 result; // rax

  v1 = (HANDLE *)luaL_checkudata(a1, 1, "security.process");
  if ( *v1 && WaitForSingleObject(*v1, 0) )
    TerminateProcess(*v1, 0xFFFFFFFF);
  v2 = v1[1];
  if ( v2 )
  {
    v1[1] = 0;
    CloseHandle(v2);
  }
  v1[1] = 0;
  v3 = *v1;
  if ( *v1 )
  {
    *v1 = 0;
    CloseHandle(v3);
  }
  *v1 = 0;
  result = 0;
  *((_DWORD *)v1 + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180082ba0  push    rbx
0x180082ba2  sub     rsp, 20h
0x180082ba6  lea     r8, aSecurityProces_1; "security.process"
0x180082bad  mov     edx, 1; int
0x180082bb2  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x180082bb7  mov     rbx, rax
0x180082bba  mov     rcx, [rax]; hHandle
0x180082bbd  test    rcx, rcx
0x180082bc0  jz      short loc_180082BDA
0x180082bc2  xor     edx, edx; dwMilliseconds
0x180082bc4  call    cs:__imp_WaitForSingleObject
0x180082bca  test    eax, eax
0x180082bcc  jz      short loc_180082BDA
0x180082bce  mov     rcx, [rbx]; hProcess
0x180082bd1  or      edx, 0FFFFFFFFh; uExitCode
0x180082bd4  call    cs:__imp_TerminateProcess
0x180082bda  mov     rcx, [rbx+8]; hObject
0x180082bde  test    rcx, rcx
0x180082be1  jz      short loc_180082BF1
0x180082be3  mov     qword ptr [rbx+8], 0
0x180082beb  call    cs:__imp_CloseHandle
0x180082bf1  mov     qword ptr [rbx+8], 0
0x180082bf9  mov     rcx, [rbx]; hObject
0x180082bfc  test    rcx, rcx
0x180082bff  jz      short loc_180082C0E
0x180082c01  mov     qword ptr [rbx], 0
0x180082c08  call    cs:__imp_CloseHandle
0x180082c0e  mov     qword ptr [rbx], 0
0x180082c15  xor     eax, eax
0x180082c17  mov     dword ptr [rbx+10h], 0
0x180082c1e  add     rsp, 20h
0x180082c22  pop     rbx
0x180082c23  retn
```
