# RPC_THREAD_POOL::CreateIoEx(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *),void *,int,RPC_THREAD_POOL_IO * *)

- ea: `0x18006e110`
- end: `0x18006e1dd`
- name: `?CreateIoEx@RPC_THREAD_POOL@@SAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@00K_KPEAU_TP_IO@@@Z0HPEAPEAVRPC_THREAD_POOL_IO@@@Z`
- size: `205`
- prototype: `__int64 __usercall@<rax>(HANDLE fl@<rcx>, PTP_WIN32_IO_CALLBACK pfnio@<rdx>, PVOID pv@<r8>, int@<r9d>, struct RPC_THREAD_POOL_IO **)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063b68`
- `0x18006d4e0`
- `0x18007fc74`
- `0x180081d30`
- `0x18009cd88`
- `0x1800cbbcc`

## callees

- `0x180023020`
- `0x18006e110`
- `0x18006e4c0`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18006e151`
- `ntdll!NtSetInformationFile` at `0x18006e151`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006e1ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006e1ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18006e17a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18006e17a`

## pseudocode

```c
__int64 __fastcall RPC_THREAD_POOL::CreateIoEx(
        HANDLE fl,
        PTP_WIN32_IO_CALLBACK pfnio,
        PVOID pv,
        int a4,
        struct RPC_THREAD_POOL_IO **a5)
{
  __int64 result; // rax
  struct _TP_IO *ThreadpoolIo; // rbx
  struct RPC_THREAD_POOL_IO *v10; // rax
  struct RPC_THREAD_POOL_IO **v11; // rcx
  struct _IO_STATUS_BLOCK v12; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+68h] [rbp+20h] BYREF

  if ( a4 )
  {
    v13 = 2;
    v12 = 0;
    if ( NtSetInformationFile(fl, &v12, &v13, 4u, FileIoCompletionNotificationInformation) < 0 )
      return 14;
  }
  result = RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary();
  if ( (_DWORD)result )
    return result;
  ThreadpoolIo = CreateThreadpoolIo(fl, pfnio, pv, RPC_THREAD_POOL::CallbackEnvironment);
  if ( !ThreadpoolIo )
    return 14;
  v10 = (struct RPC_THREAD_POOL_IO *)AllocWrapper(8u);
  if ( !v10 )
  {
    *a5 = 0;
    CloseThreadpoolIo(ThreadpoolIo);
    return 14;
  }
  v11 = a5;
  *(_QWORD *)v10 = ThreadpoolIo;
  *v11 = v10;
  return 0;
}

```

## disassembly

```asm
0x18006e110  mov     rax, rsp
0x18006e113  mov     [rax+8], rbx
0x18006e117  mov     [rax+10h], rsi
0x18006e11b  push    rdi
0x18006e11c  sub     rsp, 40h
0x18006e120  mov     rdi, r8
0x18006e123  mov     rsi, rdx
0x18006e126  mov     rbx, rcx
0x18006e129  test    r9d, r9d
0x18006e12c  jz      short loc_18006E161
0x18006e12e  xorps   xmm0, xmm0
0x18006e131  mov     dword ptr [rax+20h], 2
0x18006e138  mov     r9d, 4; Length
0x18006e13e  mov     dword ptr [rax-28h], 29h ; ')'
0x18006e145  lea     r8, [rax+20h]; FileInformation
0x18006e149  lea     rdx, [rax-18h]; IoStatusBlock
0x18006e14d  movups  xmmword ptr [rax-18h], xmm0
0x18006e151  call    cs:__imp_NtSetInformationFile
0x18006e158  nop     dword ptr [rax+rax+00h]
0x18006e15d  test    eax, eax
0x18006e15f  js      short loc_18006E1D6
0x18006e161  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18006e166  test    eax, eax
0x18006e168  jnz     short loc_18006E1AA
0x18006e16a  mov     r9, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18006e171  mov     r8, rdi; pv
0x18006e174  mov     rdx, rsi; pfnio
0x18006e177  mov     rcx, rbx; fl
0x18006e17a  call    cs:__imp_CreateThreadpoolIo
0x18006e181  nop     dword ptr [rax+rax+00h]
0x18006e186  mov     rbx, rax
0x18006e189  test    rax, rax
0x18006e18c  jz      short loc_18006E1D6
0x18006e18e  mov     ecx, 8; dwBytes
0x18006e193  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006e198  test    rax, rax
0x18006e19b  jz      short loc_18006E1BB
0x18006e19d  mov     rcx, [rsp+48h+arg_20]
0x18006e1a2  mov     [rax], rbx
0x18006e1a5  mov     [rcx], rax
0x18006e1a8  xor     eax, eax
0x18006e1aa  mov     rbx, [rsp+48h+arg_0]
0x18006e1af  mov     rsi, [rsp+48h+arg_8]
0x18006e1b4  add     rsp, 40h
0x18006e1b8  pop     rdi
0x18006e1b9  retn
0x18006e1bb  mov     rax, [rsp+48h+arg_20]
0x18006e1c0  mov     rcx, rbx; pio
0x18006e1c3  mov     qword ptr [rax], 0
0x18006e1ca  call    cs:__imp_CloseThreadpoolIo
0x18006e1d1  nop     dword ptr [rax+rax+00h]
0x18006e1d6  mov     eax, 0Eh
0x18006e1db  jmp     short loc_18006E1AA
```
