# PacWorkerClient::~PacWorkerClient(void)

- ea: `0x1800c3f00`
- end: `0x1800c402e`
- name: `??1PacWorkerClient@@AEAA@XZ`
- size: `302`
- prototype: `void __fastcall(PacWorkerClient *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180092454`

## callees

- `0x18001b480`
- `0x18008b410`
- `0x180091c08`
- `0x1800a1d10`
- `0x1800c3f00`
- `0x1800c4ebc`
- `0x1800da5b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c4010`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c4010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3faf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3faf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3ffe`
- `KERNELBASE!AppContainerUnregisterSid` at `0x1800c3f43`
- `KERNELBASE!AppContainerUnregisterSid` at `0x1800c3f43`
- `RPCRT4!RpcBindingFree` at `0x1800c3fe7`
- `RPCRT4!RpcBindingFree` at `0x1800c3fe7`

## pseudocode

```c
void __fastcall PacWorkerClient::~PacWorkerClient(PacWorkerClient *this)
{
  int v2; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // eax
  int v6; // ecx
  int v7; // r8d
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-18h] BYREF

  PacWorkerClient::WorkerStop(this);
  if ( *((_DWORD *)this + 1) )
  {
    PacWorkerClient::WorkerReleaseCallbacksServer();
    *((_DWORD *)this + 1) = 0;
  }
  if ( *((_DWORD *)this + 40) )
  {
    v2 = AppContainerUnregisterSid((char *)this + 120);
    if ( v2 < 0 && (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_q_sid_d(v3, 15, v4, (int)this, (char *)this + 120, v2);
    v5 = RemoveActiveAppContainerSids((char *)this + 120);
    if ( v5 < 0 && (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_q_sid_d(v6, 16, v7, (int)this, (char *)this + 120, v5);
  }
  if ( *((_QWORD *)this + 12) )
    WxFreeHeapEx((char *)this + 96);
  v8 = (void *)*((_QWORD *)this + 9);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 9) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 8);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 8) = 0;
  }
  if ( *((_QWORD *)this + 7) )
  {
    Binding = (RPC_BINDING_HANDLE)*((_QWORD *)this + 7);
    RpcBindingFree(&Binding);
    *((_QWORD *)this + 7) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 6);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 6) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800c3f00  mov     [rsp+arg_8], rbx
0x1800c3f05  push    rdi
0x1800c3f06  sub     rsp, 40h
0x1800c3f0a  mov     rax, cs:__security_cookie
0x1800c3f11  xor     rax, rsp
0x1800c3f14  mov     [rsp+48h+var_10], rax
0x1800c3f19  mov     rbx, rcx
0x1800c3f1c  call    ?WorkerStop@PacWorkerClient@@QEAAXXZ; PacWorkerClient::WorkerStop(void)
0x1800c3f21  cmp     dword ptr [rbx+4], 0
0x1800c3f25  jz      short loc_1800C3F33
0x1800c3f27  call    ?WorkerReleaseCallbacksServer@PacWorkerClient@@SAJXZ; PacWorkerClient::WorkerReleaseCallbacksServer(void)
0x1800c3f2c  mov     dword ptr [rbx+4], 0
0x1800c3f33  cmp     dword ptr [rbx+0A0h], 0
0x1800c3f3a  jz      short loc_1800C3F97
0x1800c3f3c  lea     rdi, [rbx+78h]
0x1800c3f40  mov     rcx, rdi
0x1800c3f43  call    cs:__imp_AppContainerUnregisterSid
0x1800c3f49  test    eax, eax
0x1800c3f4b  jns     short loc_1800C3F6C
0x1800c3f4d  test    byte ptr cs:xmmword_180107A50, 20h
0x1800c3f54  jz      short loc_1800C3F6C
0x1800c3f56  mov     dword ptr [rsp+48h+var_20], eax; char
0x1800c3f5a  mov     edx, 0Fh; int
0x1800c3f5f  mov     r9, rbx; int
0x1800c3f62  mov     [rsp+48h+pSid], rdi; pSid
0x1800c3f67  call    WPP_SF_q_sid_d
0x1800c3f6c  mov     rcx, rdi; pSid2
0x1800c3f6f  call    ?RemoveActiveAppContainerSids@@YAJQEAE@Z; RemoveActiveAppContainerSids(uchar * const)
0x1800c3f74  test    eax, eax
0x1800c3f76  jns     short loc_1800C3F97
0x1800c3f78  test    byte ptr cs:xmmword_180107A50, 20h
0x1800c3f7f  jz      short loc_1800C3F97
0x1800c3f81  mov     dword ptr [rsp+48h+var_20], eax; char
0x1800c3f85  mov     edx, 10h; int
0x1800c3f8a  mov     r9, rbx; int
0x1800c3f8d  mov     [rsp+48h+pSid], rdi; pSid
0x1800c3f92  call    WPP_SF_q_sid_d
0x1800c3f97  lea     rcx, [rbx+60h]
0x1800c3f9b  cmp     qword ptr [rcx], 0
0x1800c3f9f  jz      short loc_1800C3FA6
0x1800c3fa1  call    WxFreeHeapEx
0x1800c3fa6  mov     rcx, [rbx+48h]; hObject
0x1800c3faa  test    rcx, rcx
0x1800c3fad  jz      short loc_1800C3FBD
0x1800c3faf  call    cs:__imp_CloseHandle
0x1800c3fb5  mov     qword ptr [rbx+48h], 0
0x1800c3fbd  mov     rcx, [rbx+40h]; hObject
0x1800c3fc1  test    rcx, rcx
0x1800c3fc4  jz      short loc_1800C3FD4
0x1800c3fc6  call    cs:__imp_CloseHandle
0x1800c3fcc  mov     qword ptr [rbx+40h], 0
0x1800c3fd4  mov     rax, [rbx+38h]
0x1800c3fd8  test    rax, rax
0x1800c3fdb  jz      short loc_1800C3FF5
0x1800c3fdd  lea     rcx, [rsp+48h+Binding]; Binding
0x1800c3fe2  mov     [rsp+48h+Binding], rax
0x1800c3fe7  call    cs:__imp_RpcBindingFree
0x1800c3fed  mov     qword ptr [rbx+38h], 0
0x1800c3ff5  mov     rcx, [rbx+30h]; hObject
0x1800c3ff9  test    rcx, rcx
0x1800c3ffc  jz      short loc_1800C400C
0x1800c3ffe  call    cs:__imp_CloseHandle
0x1800c4004  mov     qword ptr [rbx+30h], 0
0x1800c400c  lea     rcx, [rbx+8]; lpCriticalSection
0x1800c4010  call    cs:__imp_DeleteCriticalSection
0x1800c4016  mov     rcx, [rsp+48h+var_10]
0x1800c401b  xor     rcx, rsp; StackCookie
0x1800c401e  call    __security_check_cookie
0x1800c4023  mov     rbx, [rsp+48h+arg_8]
0x1800c4028  add     rsp, 40h
0x1800c402c  pop     rdi
0x1800c402d  retn
```
