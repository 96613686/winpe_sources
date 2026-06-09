# GetTiToken(void * *)

- ea: `0x14007e468`
- end: `0x14007e510`
- name: `?GetTiToken@@YAHPEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007e078`

## callees

- `0x14007d9b8`
- `0x14007e468`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14007e4bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14007e4bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007e4ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007e4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e4ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007e4ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007e4f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007e4f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14007e49f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14007e49f`

## pseudocode

```c
__int64 __fastcall GetTiToken(void **a1)
{
  unsigned int v2; // ebx
  HANDLE CurrentProcess; // rax
  struct _SID_AND_ATTRIBUTES v5; // [rsp+20h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF
  PSID Sid; // [rsp+50h] [rbp+20h] BYREF

  TokenHandle = 0;
  Sid = 0;
  v5 = 0;
  v2 = ConvertStringSidToSidW(L"S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464", &Sid);
  if ( v2 )
  {
    CurrentProcess = GetCurrentProcess();
    v2 = OpenProcessToken(CurrentProcess, 0x1Au, &TokenHandle);
    if ( v2 )
    {
      v5.Sid = Sid;
      v5.Attributes = 7;
      v2 = ChangeToken(TokenHandle, &v5, a1);
      CloseHandle(TokenHandle);
    }
    LocalFree(Sid);
  }
  return v2;
}

```

## disassembly

```asm
0x14007e468  mov     [rsp-8+arg_0], rbx
0x14007e46d  mov     [rsp-8+arg_18], rdi
0x14007e472  push    rbp
0x14007e473  mov     rbp, rsp
0x14007e476  sub     rsp, 30h
0x14007e47a  mov     rdi, rcx
0x14007e47d  mov     [rbp+TokenHandle], 0
0x14007e485  xorps   xmm0, xmm0
0x14007e488  mov     [rbp+Sid], 0
0x14007e490  lea     rcx, aS1580956008885; "S-1-5-80-956008885-3418522649-183103804"...
0x14007e497  lea     rdx, [rbp+Sid]; Sid
0x14007e49b  movups  xmmword ptr [rbp+var_10.Sid], xmm0
0x14007e49f  call    cs:__imp_ConvertStringSidToSidW
0x14007e4a5  mov     ebx, eax
0x14007e4a7  test    eax, eax
0x14007e4a9  jz      short loc_14007E4FE
0x14007e4ab  call    cs:__imp_GetCurrentProcess
0x14007e4b1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14007e4b5  mov     edx, 1Ah; DesiredAccess
0x14007e4ba  mov     rcx, rax; ProcessHandle
0x14007e4bd  call    cs:__imp_OpenProcessToken
0x14007e4c3  mov     ebx, eax
0x14007e4c5  test    eax, eax
0x14007e4c7  jz      short loc_14007E4F4
0x14007e4c9  mov     rax, [rbp+Sid]
0x14007e4cd  lea     rdx, [rbp+var_10]; struct _SID_AND_ATTRIBUTES *
0x14007e4d1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14007e4d5  mov     r8, rdi; void **
0x14007e4d8  mov     [rbp+var_10.Sid], rax
0x14007e4dc  mov     [rbp+var_10.Attributes], 7
0x14007e4e3  call    ?ChangeToken@@YAHPEAXPEAU_SID_AND_ATTRIBUTES@@PEAPEAX@Z; ChangeToken(void *,_SID_AND_ATTRIBUTES *,void * *)
0x14007e4e8  mov     rcx, [rbp+TokenHandle]; hObject
0x14007e4ec  mov     ebx, eax
0x14007e4ee  call    cs:__imp_CloseHandle
0x14007e4f4  mov     rcx, [rbp+Sid]; hMem
0x14007e4f8  call    cs:__imp_LocalFree
0x14007e4fe  mov     rdi, [rsp+30h+arg_18]
0x14007e503  mov     eax, ebx
0x14007e505  mov     rbx, [rsp+30h+arg_0]
0x14007e50a  add     rsp, 30h
0x14007e50e  pop     rbp
0x14007e50f  retn
```
