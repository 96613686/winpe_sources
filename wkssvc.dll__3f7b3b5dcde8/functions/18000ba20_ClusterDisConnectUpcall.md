# ClusterDisConnectUpcall

- ea: `0x18000ba20`
- end: `0x18000bba4`
- name: `ClusterDisConnectUpcall`
- size: `388`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, __int64, const void **, const void **, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b76c`
- `0x18000ba20`
- `0x18000dd68`
- `0x180022b7c`
- `0x180033159`
- `0x180034010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18000ba47`
- `ntdll!RtlAcquireResourceShared` at `0x18000ba47`
- `ntdll!RtlReleaseResource` at `0x18000bb79`
- `ntdll!RtlReleaseResource` at `0x18000bb79`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000bb34`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000bb34`

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
0x18000ba20  push    rbx
0x18000ba22  push    rbp
0x18000ba23  push    rsi
0x18000ba24  push    rdi
0x18000ba25  push    r14
0x18000ba27  sub     rsp, 40h
0x18000ba2b  mov     r14, rcx
0x18000ba2e  mov     [rsp+68h+Reply], 0
0x18000ba36  lea     rcx, UpcallServerResource; Resource
0x18000ba3d  mov     dl, 1; Wait
0x18000ba3f  mov     rbp, r9
0x18000ba42  mov     rsi, r8
0x18000ba45  xor     edi, edi
0x18000ba47  call    cs:__imp_RtlAcquireResourceShared
0x18000ba4d  cmp     cs:UpcallServerState, 1
0x18000ba54  jnz     loc_18000BAEC
0x18000ba5a  movzx   ecx, word ptr [rsi]
0x18000ba5d  add     rcx, 2; unsigned __int64
0x18000ba61  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000ba66  mov     rbx, rax
0x18000ba69  test    rax, rax
0x18000ba6c  jnz     short loc_18000BA75
0x18000ba6e  mov     eax, 0Eh
0x18000ba73  jmp     short loc_18000BAF1
0x18000ba75  movzx   r8d, word ptr [rsi]; Size
0x18000ba79  mov     rcx, rbx; void *
0x18000ba7c  mov     rdx, [rsi+8]; Src
0x18000ba80  call    memcpy_0
0x18000ba85  movzx   ecx, word ptr [rsi]
0x18000ba88  xor     eax, eax
0x18000ba8a  shr     rcx, 1
0x18000ba8d  mov     [rbx+rcx*2], ax
0x18000ba91  movzx   ecx, word ptr [rbp+0]
0x18000ba95  add     rcx, 2; unsigned __int64
0x18000ba99  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000ba9e  mov     rdi, rax
0x18000baa1  test    rax, rax
0x18000baa4  jz      short loc_18000BA6E
0x18000baa6  movzx   r8d, word ptr [rbp+0]; Size
0x18000baab  mov     rcx, rax; void *
0x18000baae  mov     rdx, [rbp+8]; Src
0x18000bab2  call    memcpy_0
0x18000bab7  movzx   ecx, word ptr [rbp+0]
0x18000babb  xor     eax, eax
0x18000babd  mov     r9d, [rsp+68h+arg_28]
0x18000bac5  mov     rdx, rdi
0x18000bac8  mov     r8, [rsp+68h+arg_20]
0x18000bad0  shr     rcx, 1
0x18000bad3  mov     [rdi+rcx*2], ax
0x18000bad7  mov     rcx, rbx
0x18000bada  mov     rax, cs:pUpcallDispatch
0x18000bae1  mov     rax, [rax+8]
0x18000bae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baea  jmp     short loc_18000BAF1
0x18000baec  xor     ebx, ebx
0x18000baee  lea     eax, [rbx+57h]
0x18000baf1  mov     [rsp+68h+Reply], eax
0x18000baf5  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000bafc  lea     rsi, WPP_witness_GLOBAL_Control
0x18000bb03  cmp     rcx, rsi
0x18000bb06  jz      short loc_18000BB2C
0x18000bb08  test    byte ptr [rcx+1Ch], 1
0x18000bb0c  jz      short loc_18000BB2C
0x18000bb0e  cmp     byte ptr [rcx+19h], 3
0x18000bb12  jb      short loc_18000BB2C
0x18000bb14  mov     rcx, [rcx+10h]
0x18000bb18  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000bb1f  mov     edx, 1Ah
0x18000bb24  mov     r9d, eax
0x18000bb27  call    WPP_SF_d
0x18000bb2c  lea     rdx, [rsp+68h+Reply]; Reply
0x18000bb31  mov     rcx, r14; pAsync
0x18000bb34  call    cs:__imp_RpcAsyncCompleteCall
0x18000bb3a  mov     [rsp+68h+Reply], eax
0x18000bb3e  test    eax, eax
0x18000bb40  jz      short loc_18000BB72
0x18000bb42  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000bb49  cmp     rcx, rsi
0x18000bb4c  jz      short loc_18000BB72
0x18000bb4e  test    byte ptr [rcx+1Ch], 1
0x18000bb52  jz      short loc_18000BB72
0x18000bb54  cmp     byte ptr [rcx+19h], 1
0x18000bb58  jb      short loc_18000BB72
0x18000bb5a  mov     rcx, [rcx+10h]
0x18000bb5e  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000bb65  mov     edx, 1Bh
0x18000bb6a  mov     r9d, eax
0x18000bb6d  call    WPP_SF_d
0x18000bb72  lea     rcx, UpcallServerResource; Resource
0x18000bb79  call    cs:__imp_RtlReleaseResource
0x18000bb7f  test    rbx, rbx
0x18000bb82  jz      short loc_18000BB8C
0x18000bb84  mov     rcx, rbx; void *
0x18000bb87  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000bb8c  test    rdi, rdi
0x18000bb8f  jz      short loc_18000BB99
0x18000bb91  mov     rcx, rdi; void *
0x18000bb94  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000bb99  add     rsp, 40h
0x18000bb9d  pop     r14
0x18000bb9f  pop     rdi
0x18000bba0  pop     rsi
0x18000bba1  pop     rbp
0x18000bba2  pop     rbx
0x18000bba3  retn
```
