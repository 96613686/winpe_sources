# LRPC_ADDRESS::LRPC_ADDRESS(long *)

- ea: `0x180094a28`
- end: `0x180094bff`
- name: `??0LRPC_ADDRESS@@QEAA@PEAJ@Z`
- size: `471`
- prototype: `LRPC_ADDRESS *__fastcall(LRPC_ADDRESS *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180094994`

## callees

- `0x180094a28`
- `0x180094c08`
- `0x18009d5f4`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180094a84`
- `ntdll!RtlInitializeSRWLock` at `0x180094a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094bb8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094b20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094b20`

## pseudocode

```c
LRPC_ADDRESS *__fastcall LRPC_ADDRESS::LRPC_ADDRESS(LRPC_ADDRESS *this, int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // eax
  HANDLE EventW; // rax
  CellHeap *v8; // rcx
  LRPC_ADDRESS *result; // rax
  struct tagDebugFreeCell *Cell; // rax
  void *v11; // rcx
  __int64 v12; // rax

  RPC_ADDRESS::RPC_ADDRESS(this);
  *(_QWORD *)this = &LRPC_ADDRESS::`vftable';
  *((_QWORD *)this + 28) = 4;
  *((_QWORD *)this + 27) = (char *)this + 232;
  *(_OWORD *)((char *)this + 232) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_DWORD *)this + 84) = 0;
  RtlInitializeSRWLock((char *)this + 424);
  *((_DWORD *)this + 3) = 0x800000;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 73) = 0;
  v4 = gPageSize;
  *((_DWORD *)this + 83) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  v5 = v4 * gNumberOfProcessors;
  v6 = 4 * v4;
  *((_DWORD *)this + 82) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 46) = 0;
  v5 *= 2;
  *(_OWORD *)((char *)this + 312) = 0;
  *((_DWORD *)this + 76) = v5;
  if ( v5 < v6 )
    *((_DWORD *)this + 76) = v6;
  *((_DWORD *)this + 100) = 0;
  *((_DWORD *)this + 101) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 51) = EventW;
  if ( !EventW )
    *a2 = 14;
  if ( g_fServerSideDebugInfoEnabled )
  {
    Cell = CellHeap::AllocateCell(v8, (int *)this + 88);
    *((_QWORD *)this + 45) = Cell;
    if ( Cell )
    {
      *(_DWORD *)Cell = 0;
      **((_BYTE **)this + 45) = 4;
      *(_BYTE *)(*((_QWORD *)this + 45) + 1LL) = 9;
      *(_BYTE *)(*((_QWORD *)this + 45) + 2LL) = 0;
      v12 = *((_QWORD *)this + 45);
      *(_OWORD *)(v12 + 4) = 0;
      *(_OWORD *)(v12 + 16) = 0;
    }
    else
    {
      v11 = (void *)*((_QWORD *)this + 51);
      *a2 = 14;
      CloseHandle(v11);
    }
  }
  else
  {
    *((_QWORD *)this + 45) = 0;
  }
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 33) = LrpcServerIoHandler;
  result = this;
  *((_QWORD *)this + 46) = 0;
  *((_DWORD *)this + 70) = -623191334;
  *((_DWORD *)this + 104) = 4096;
  return result;
}

```

## disassembly

```asm
0x180094a28  mov     [rsp+arg_0], rbx
0x180094a2d  mov     [rsp+arg_8], rsi
0x180094a32  push    rdi
0x180094a33  sub     rsp, 20h
0x180094a37  mov     rdi, rdx
0x180094a3a  mov     rbx, rcx
0x180094a3d  call    ??0RPC_ADDRESS@@IEAA@XZ; RPC_ADDRESS::RPC_ADDRESS(void)
0x180094a42  xorps   xmm0, xmm0
0x180094a45  lea     rax, ??_7LRPC_ADDRESS@@6B@; const LRPC_ADDRESS::`vftable'
0x180094a4c  mov     [rbx], rax
0x180094a4f  lea     rcx, [rbx+1A8h]
0x180094a56  mov     qword ptr [rbx+0E0h], 4
0x180094a61  lea     rax, [rbx+0E8h]
0x180094a68  mov     [rbx+0D8h], rax
0x180094a6f  xor     esi, esi
0x180094a71  movups  xmmword ptr [rax], xmm0
0x180094a74  movups  xmmword ptr [rax+10h], xmm0
0x180094a78  mov     [rbx+120h], esi
0x180094a7e  mov     [rbx+150h], esi
0x180094a84  call    cs:__imp_RtlInitializeSRWLock
0x180094a8b  nop     dword ptr [rax+rax+00h]
0x180094a90  mov     dword ptr [rbx+0Ch], 800000h
0x180094a97  mov     eax, 7FFE0320h
0x180094a9c  mov     [rbx+0D0h], rsi
0x180094aa3  xorps   xmm0, xmm0
0x180094aa6  mov     [rbx+128h], rsi
0x180094aad  mov     [rbx+124h], esi
0x180094ab3  mov     rax, [rax]
0x180094ab6  mov     ecx, ds:7FFE0004h
0x180094abd  imul    rcx, rax
0x180094ac1  mov     eax, cs:?gPageSize@@3KA; ulong gPageSize
0x180094ac7  shr     rcx, 18h
0x180094acb  mov     [rbx+14Ch], ecx
0x180094ad1  mov     ecx, cs:?gNumberOfProcessors@@3IA; uint gNumberOfProcessors
0x180094ad7  imul    ecx, eax
0x180094ada  shl     eax, 2
0x180094add  mov     [rbx+148h], esi
0x180094ae3  mov     [rbx+158h], rsi
0x180094aea  mov     [rbx+170h], rsi
0x180094af1  add     ecx, ecx
0x180094af3  movups  xmmword ptr [rbx+138h], xmm0
0x180094afa  mov     [rbx+130h], ecx
0x180094b00  cmp     ecx, eax
0x180094b02  jnb     short loc_180094B0A
0x180094b04  mov     [rbx+130h], eax
0x180094b0a  mov     [rbx+190h], esi
0x180094b10  xor     r9d, r9d; lpName
0x180094b13  xor     r8d, r8d; bInitialState
0x180094b16  mov     [rbx+194h], esi
0x180094b1c  xor     edx, edx; bManualReset
0x180094b1e  xor     ecx, ecx; lpEventAttributes
0x180094b20  call    cs:__imp_CreateEventW
0x180094b27  nop     dword ptr [rax+rax+00h]
0x180094b2c  mov     [rbx+198h], rax
0x180094b33  test    rax, rax
0x180094b36  jz      short loc_180094B8B
0x180094b38  cmp     cs:?g_fServerSideDebugInfoEnabled@@3HA, esi; int g_fServerSideDebugInfoEnabled
0x180094b3e  jnz     short loc_180094B93
0x180094b40  mov     [rbx+168h], rsi
0x180094b47  lea     rax, ?LrpcServerIoHandler@@YAXPEAUtagLRPC_IO_TARGET@@PEAX@Z; LrpcServerIoHandler(tagLRPC_IO_TARGET *,void *)
0x180094b4e  mov     [rbx+110h], rsi
0x180094b55  mov     [rbx+108h], rax
0x180094b5c  mov     rax, rbx
0x180094b5f  mov     [rbx+170h], rsi
0x180094b66  mov     rsi, [rsp+28h+arg_8]
0x180094b6b  mov     dword ptr [rbx+118h], 0DADADADAh
0x180094b75  mov     dword ptr [rbx+1A0h], 1000h
0x180094b7f  mov     rbx, [rsp+28h+arg_0]
0x180094b84  add     rsp, 20h
0x180094b88  pop     rdi
0x180094b89  retn
0x180094b8b  mov     dword ptr [rdi], 0Eh
0x180094b91  jmp     short loc_180094B38
0x180094b93  lea     rdx, [rbx+160h]; int *
0x180094b9a  call    ?AllocateCell@CellHeap@@QEAAPEAUtagDebugFreeCell@@PEAH@Z; CellHeap::AllocateCell(int *)
0x180094b9f  mov     [rbx+168h], rax
0x180094ba6  test    rax, rax
0x180094ba9  jnz     short loc_180094BC6
0x180094bab  mov     rcx, [rbx+198h]; hObject
0x180094bb2  mov     dword ptr [rdi], 0Eh
0x180094bb8  call    cs:__imp_CloseHandle
0x180094bbf  nop     dword ptr [rax+rax+00h]
0x180094bc4  jmp     short loc_180094B47
0x180094bc6  mov     [rax], esi
0x180094bc8  xorps   xmm0, xmm0
0x180094bcb  mov     rax, [rbx+168h]
0x180094bd2  mov     byte ptr [rax], 4
0x180094bd5  mov     rax, [rbx+168h]
0x180094bdc  mov     byte ptr [rax+1], 9
0x180094be0  mov     rax, [rbx+168h]
0x180094be7  mov     [rax+2], sil
0x180094beb  mov     rax, [rbx+168h]
0x180094bf2  movups  xmmword ptr [rax+4], xmm0
0x180094bf6  movups  xmmword ptr [rax+10h], xmm0
0x180094bfa  jmp     loc_180094B47
```
