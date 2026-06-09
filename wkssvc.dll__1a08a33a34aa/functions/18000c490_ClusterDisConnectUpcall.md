# ClusterDisConnectUpcall

- ea: `0x18000c490`
- end: `0x18000c627`
- name: `ClusterDisConnectUpcall`
- size: `407`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c1b4`
- `0x18000c490`
- `0x18000ea98`
- `0x180024550`
- `0x180036191`
- `0x180037010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18000c4b7`
- `ntdll!RtlAcquireResourceShared` at `0x18000c4b7`
- `ntdll!RtlReleaseResource` at `0x18000c5f5`
- `ntdll!RtlReleaseResource` at `0x18000c5f5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c5aa`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c5aa`

## pseudocode

```c
void __fastcall ClusterDisConnectUpcall(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        const void **a3,
        const void **a4,
        __int64 a5,
        unsigned int a6)
{
  _WORD *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rbx
  unsigned int v12; // eax
  void *v13; // rax
  unsigned int v14; // eax
  unsigned int Reply[14]; // [rsp+30h] [rbp-38h] BYREF

  Reply[0] = 0;
  v9 = 0;
  RtlAcquireResourceShared(&UpcallServerResource, 1u);
  if ( UpcallServerState == 1 )
  {
    v10 = MemoryAlloc(*(unsigned __int16 *)a3 + 2LL);
    v11 = v10;
    if ( v10
      && (memcpy_0(v10, a3[1], *(unsigned __int16 *)a3),
          v11[(unsigned __int64)*(unsigned __int16 *)a3 >> 1] = 0,
          v13 = MemoryAlloc(*(unsigned __int16 *)a4 + 2LL),
          (v9 = v13) != 0) )
    {
      memcpy_0(v13, a4[1], *(unsigned __int16 *)a4);
      v9[(unsigned __int64)*(unsigned __int16 *)a4 >> 1] = 0;
      v12 = (*(__int64 (__fastcall **)(_WORD *, _WORD *, __int64, _QWORD))(pUpcallDispatch + 8))(v11, v9, a5, a6);
    }
    else
    {
      v12 = 14;
    }
  }
  else
  {
    v11 = 0;
    v12 = 87;
  }
  Reply[0] = v12;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 26, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v12);
  }
  v14 = RpcAsyncCompleteCall(pAsync, Reply);
  Reply[0] = v14;
  if ( v14
    && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 27, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v14);
  }
  RtlReleaseResource(&UpcallServerResource);
  if ( v11 )
    MemoryFree(v11);
  if ( v9 )
    MemoryFree(v9);
}

```

## disassembly

```asm
0x18000c490  push    rbx
0x18000c492  push    rbp
0x18000c493  push    rsi
0x18000c494  push    rdi
0x18000c495  push    r14
0x18000c497  sub     rsp, 40h
0x18000c49b  mov     r14, rcx
0x18000c49e  mov     [rsp+68h+Reply], 0
0x18000c4a6  lea     rcx, UpcallServerResource; Resource
0x18000c4ad  mov     dl, 1; Wait
0x18000c4af  mov     rbp, r9
0x18000c4b2  mov     rsi, r8
0x18000c4b5  xor     edi, edi
0x18000c4b7  call    cs:__imp_RtlAcquireResourceShared
0x18000c4be  nop     dword ptr [rax+rax+00h]
0x18000c4c3  cmp     cs:UpcallServerState, 1
0x18000c4ca  jnz     loc_18000C562
0x18000c4d0  movzx   ecx, word ptr [rsi]
0x18000c4d3  add     rcx, 2; unsigned __int64
0x18000c4d7  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000c4dc  mov     rbx, rax
0x18000c4df  test    rax, rax
0x18000c4e2  jnz     short loc_18000C4EB
0x18000c4e4  mov     eax, 0Eh
0x18000c4e9  jmp     short loc_18000C567
0x18000c4eb  movzx   r8d, word ptr [rsi]; Size
0x18000c4ef  mov     rcx, rbx; void *
0x18000c4f2  mov     rdx, [rsi+8]; Src
0x18000c4f6  call    memcpy_0
0x18000c4fb  movzx   ecx, word ptr [rsi]
0x18000c4fe  xor     eax, eax
0x18000c500  shr     rcx, 1
0x18000c503  mov     [rbx+rcx*2], ax
0x18000c507  movzx   ecx, word ptr [rbp+0]
0x18000c50b  add     rcx, 2; unsigned __int64
0x18000c50f  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000c514  mov     rdi, rax
0x18000c517  test    rax, rax
0x18000c51a  jz      short loc_18000C4E4
0x18000c51c  movzx   r8d, word ptr [rbp+0]; Size
0x18000c521  mov     rcx, rax; void *
0x18000c524  mov     rdx, [rbp+8]; Src
0x18000c528  call    memcpy_0
0x18000c52d  movzx   ecx, word ptr [rbp+0]
0x18000c531  xor     eax, eax
0x18000c533  mov     r9d, [rsp+68h+arg_28]
0x18000c53b  mov     rdx, rdi
0x18000c53e  mov     r8, [rsp+68h+arg_20]
0x18000c546  shr     rcx, 1
0x18000c549  mov     [rdi+rcx*2], ax
0x18000c54d  mov     rcx, rbx
0x18000c550  mov     rax, cs:pUpcallDispatch
0x18000c557  mov     rax, [rax+8]
0x18000c55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c560  jmp     short loc_18000C567
0x18000c562  xor     ebx, ebx
0x18000c564  lea     eax, [rbx+57h]
0x18000c567  mov     [rsp+68h+Reply], eax
0x18000c56b  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c572  lea     rsi, WPP_witness_GLOBAL_Control
0x18000c579  cmp     rcx, rsi
0x18000c57c  jz      short loc_18000C5A2
0x18000c57e  test    byte ptr [rcx+1Ch], 1
0x18000c582  jz      short loc_18000C5A2
0x18000c584  cmp     byte ptr [rcx+19h], 3
0x18000c588  jb      short loc_18000C5A2
0x18000c58a  mov     rcx, [rcx+10h]
0x18000c58e  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000c595  mov     edx, 1Ah
0x18000c59a  mov     r9d, eax
0x18000c59d  call    WPP_SF_d
0x18000c5a2  lea     rdx, [rsp+68h+Reply]; Reply
0x18000c5a7  mov     rcx, r14; pAsync
0x18000c5aa  call    cs:__imp_RpcAsyncCompleteCall
0x18000c5b1  nop     dword ptr [rax+rax+00h]
0x18000c5b6  mov     [rsp+68h+Reply], eax
0x18000c5ba  test    eax, eax
0x18000c5bc  jz      short loc_18000C5EE
0x18000c5be  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c5c5  cmp     rcx, rsi
0x18000c5c8  jz      short loc_18000C5EE
0x18000c5ca  test    byte ptr [rcx+1Ch], 1
0x18000c5ce  jz      short loc_18000C5EE
0x18000c5d0  cmp     byte ptr [rcx+19h], 1
0x18000c5d4  jb      short loc_18000C5EE
0x18000c5d6  mov     rcx, [rcx+10h]
0x18000c5da  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000c5e1  mov     edx, 1Bh
0x18000c5e6  mov     r9d, eax
0x18000c5e9  call    WPP_SF_d
0x18000c5ee  lea     rcx, UpcallServerResource; Resource
0x18000c5f5  call    cs:__imp_RtlReleaseResource
0x18000c5fc  nop     dword ptr [rax+rax+00h]
0x18000c601  test    rbx, rbx
0x18000c604  jz      short loc_18000C60E
0x18000c606  mov     rcx, rbx; void *
0x18000c609  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000c60e  test    rdi, rdi
0x18000c611  jz      short loc_18000C61B
0x18000c613  mov     rcx, rdi; void *
0x18000c616  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000c61b  add     rsp, 40h
0x18000c61f  pop     r14
0x18000c621  pop     rdi
0x18000c622  pop     rsi
0x18000c623  pop     rbp
0x18000c624  pop     rbx
0x18000c625  retn
```
