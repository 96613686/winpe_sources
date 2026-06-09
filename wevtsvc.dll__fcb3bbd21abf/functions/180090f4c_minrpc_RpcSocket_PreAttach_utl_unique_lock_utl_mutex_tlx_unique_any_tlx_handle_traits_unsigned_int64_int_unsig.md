# minrpc::RpcSocket::PreAttach(utl::unique_lock<utl::mutex> &,tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>> &&)

- ea: `0x180090f4c`
- end: `0x180090ffc`
- name: `?PreAttach@RpcSocket@minrpc@@AEAA_NAEAV?$unique_lock@Vmutex@utl@@@utl@@$$QEAV?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180091110`
- `0x1800d2b3c`

## callees

- `0x180090f4c`
- `0x18009129c`
- `0x1800d2ad8`
- `0x1800d2e78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180090fae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180090fae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180090fc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180090fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090fce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090fce`

## string_xrefs

- `0x180090fe0`: `PreAttach[CreateThreadpoolIo]`

## pseudocode

```c
char __fastcall minrpc::RpcSocket::PreAttach(char *pv, __int64 a2, __int64 a3)
{
  char v5; // di
  unsigned int v6; // eax
  const char *v7; // r9
  __int64 v8; // r8
  PTP_IO ThreadpoolIo; // rax
  struct _TP_IO *v10; // rcx
  signed int LastError; // eax

  v5 = 0;
  tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>::operator=(
    pv + 24,
    a3);
  v6 = minrpc::RpcSocket::IoState::TryReserve((minrpc::RpcSocket::IoState *)(pv + 40), 0x10000u);
  *((_DWORD *)pv + 17) = v6;
  if ( v6 >= 0x10000 )
  {
    ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)pv + 3), minrpc::RpcSocket::IoCompletionCallbackStatic, pv, 0);
    v10 = (struct _TP_IO *)*((_QWORD *)pv + 4);
    *((_QWORD *)pv + 4) = ThreadpoolIo;
    if ( v10 )
      CloseThreadpoolIo(v10);
    if ( *((_QWORD *)pv + 4) )
      return 1;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = "PreAttach[CreateThreadpoolIo]";
    v8 = (unsigned int)LastError;
  }
  else
  {
    v7 = "PreAttach[Allocate]";
    v8 = 2147942414LL;
  }
  minrpc::RpcSocket::DisconnectLocked(pv, a2, v8, v7);
  return v5;
}

```

## disassembly

```asm
0x180090f4c  push    rbx
0x180090f4e  push    rsi
0x180090f4f  push    rdi
0x180090f50  push    r14
0x180090f52  sub     rsp, 28h
0x180090f56  mov     rsi, rdx
0x180090f59  mov     rbx, rcx
0x180090f5c  mov     rdx, r8
0x180090f5f  add     rcx, 18h
0x180090f63  xor     dil, dil
0x180090f66  call    ??4?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>>::operator=(tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>> &&)
0x180090f6b  lea     rcx, [rbx+28h]; this
0x180090f6f  mov     edx, 10000h; unsigned int
0x180090f74  call    ?TryReserve@IoState@RpcSocket@minrpc@@QEAAII@Z; minrpc::RpcSocket::IoState::TryReserve(uint)
0x180090f79  mov     [rbx+44h], eax
0x180090f7c  cmp     eax, 10000h
0x180090f81  jnb     short loc_180090F9D
0x180090f83  lea     r9, aPreattachAlloc; "PreAttach[Allocate]"
0x180090f8a  mov     r8d, 8007000Eh
0x180090f90  mov     rdx, rsi
0x180090f93  mov     rcx, rbx
0x180090f96  call    ?DisconnectLocked@RpcSocket@minrpc@@QEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@JPEBD@Z; minrpc::RpcSocket::DisconnectLocked(utl::unique_lock<utl::mutex> &,long,char const *)
0x180090f9b  jmp     short loc_180090FEF
0x180090f9d  mov     rcx, [rbx+18h]; fl
0x180090fa1  lea     rdx, ?IoCompletionCallbackStatic@RpcSocket@minrpc@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180090fa8  xor     r9d, r9d; pcbe
0x180090fab  mov     r8, rbx; pv
0x180090fae  call    cs:__imp_CreateThreadpoolIo
0x180090fb4  mov     rcx, [rbx+20h]; pio
0x180090fb8  mov     [rbx+20h], rax
0x180090fbc  test    rcx, rcx
0x180090fbf  jz      short loc_180090FC7
0x180090fc1  call    cs:__imp_CloseThreadpoolIo
0x180090fc7  cmp     qword ptr [rbx+20h], 0
0x180090fcc  jnz     short loc_180090FEC
0x180090fce  call    cs:__imp_GetLastError
0x180090fd4  test    eax, eax
0x180090fd6  jle     short loc_180090FE0
0x180090fd8  movzx   eax, ax
0x180090fdb  or      eax, 80070000h
0x180090fe0  lea     r9, aPreattachCreat; "PreAttach[CreateThreadpoolIo]"
0x180090fe7  mov     r8d, eax
0x180090fea  jmp     short loc_180090F90
0x180090fec  mov     dil, 1
0x180090fef  mov     al, dil
0x180090ff2  add     rsp, 28h
0x180090ff6  pop     r14
0x180090ff8  pop     rdi
0x180090ff9  pop     rsi
0x180090ffa  pop     rbx
0x180090ffb  retn
```
