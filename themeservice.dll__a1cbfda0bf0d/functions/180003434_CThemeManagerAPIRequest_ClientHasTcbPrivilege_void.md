# CThemeManagerAPIRequest::ClientHasTcbPrivilege(void)

- ea: `0x180003434`
- end: `0x1800034bb`
- name: `?ClientHasTcbPrivilege@CThemeManagerAPIRequest@@AEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(CThemeManagerAPIRequest *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800021d0`
- `0x180002270`
- `0x180002b64`
- `0x1800030ec`
- `0x180003280`
- `0x18000b180`

## callees

- `0x180003434`
- `0x1800034c4`
- `0x1800034f0`
- `0x18000674c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003458`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034a4`

## pseudocode

```c
__int64 __fastcall CThemeManagerAPIRequest::ClientHasTcbPrivilege(CThemeManagerAPIRequest *this)
{
  __int64 v1; // rcx
  unsigned int v2; // edx
  unsigned int v3; // ebx
  void *v5; // [rsp+20h] [rbp-28h] BYREF
  _OWORD v6[2]; // [rsp+28h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 17);
  TokenHandle = 0;
  if ( OpenProcessToken(*(HANDLE *)(v1 + 96), 8u, &TokenHandle) )
  {
    v5 = TokenHandle;
    v6[0] = 0;
    v3 = !CTokenInformation::UserHasPrivilege((CTokenInformation *)&v5, v2) ? 0xC0000022 : 0;
    ReleaseMemoryWorker((char *)v6 + 8);
    ReleaseMemoryWorker(v6);
    CloseHandle(TokenHandle);
  }
  else
  {
    return (unsigned int)CStatusCode::StatusCodeOfLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x180003434  push    rbx
0x180003436  sub     rsp, 40h
0x18000343a  mov     rcx, [rcx+88h]
0x180003441  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180003446  mov     [rsp+48h+TokenHandle], 0
0x18000344f  mov     edx, 8; DesiredAccess
0x180003454  mov     rcx, [rcx+60h]; ProcessHandle
0x180003458  call    cs:__imp_OpenProcessToken
0x18000345e  test    eax, eax
0x180003460  jz      short loc_1800034B2
0x180003462  mov     rax, [rsp+48h+TokenHandle]
0x180003467  lea     rcx, [rsp+48h+var_28]; this
0x18000346c  xorps   xmm0, xmm0
0x18000346f  mov     [rsp+48h+var_28], rax
0x180003474  movdqu  [rsp+48h+var_20], xmm0
0x18000347a  call    ?UserHasPrivilege@CTokenInformation@@QEAA_NK@Z; CTokenInformation::UserHasPrivilege(ulong)
0x18000347f  neg     al
0x180003481  lea     rcx, [rsp+48h+var_20+8]
0x180003486  sbb     ebx, ebx
0x180003488  not     ebx
0x18000348a  and     ebx, 0C0000022h
0x180003490  call    ReleaseMemoryWorker
0x180003495  lea     rcx, [rsp+48h+var_20]
0x18000349a  call    ReleaseMemoryWorker
0x18000349f  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800034a4  call    cs:__imp_CloseHandle
0x1800034aa  mov     eax, ebx
0x1800034ac  add     rsp, 40h
0x1800034b0  pop     rbx
0x1800034b1  retn
0x1800034b2  call    ?StatusCodeOfLastError@CStatusCode@@SAJXZ; CStatusCode::StatusCodeOfLastError(void)
0x1800034b7  mov     ebx, eax
0x1800034b9  jmp     short loc_1800034AA
```
