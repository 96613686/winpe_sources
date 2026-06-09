# LBSVirtualChannelState::Initialize(ulong)

- ea: `0x180020a9c`
- end: `0x180020b5c`
- name: `?Initialize@LBSVirtualChannelState@@QEAAJK@Z`
- size: `192`
- prototype: `int(LBSVirtualChannelState *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fc58`

## callees

- `0x18000185c`
- `0x18001f810`
- `0x180020a9c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180020b0f`
- `KERNEL32!CreateEventW` at `0x180020b0f`
- `RPCRT4!I_RpcAllocate` at `0x180020ac7`
- `RPCRT4!I_RpcAllocate` at `0x180020ac7`

## pseudocode

```c
__int64 __fastcall LBSVirtualChannelState::Initialize(LBSVirtualChannelState *this, unsigned int a2)
{
  __int64 v3; // rsi
  __int64 v4; // rax
  bool v5; // cf
  unsigned int v6; // eax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 i; // rbx
  LB_USE_COUNT_CONTAINER *v10; // rcx

  v3 = a2;
  v4 = 144LL * a2;
  if ( !is_mul_ok(a2, 0x90u) )
    v4 = -1;
  v5 = __CFADD__(v4, 8);
  v6 = v4 + 8;
  if ( v5 )
    v6 = -1;
  v7 = I_RpcAllocate(v6);
  if ( v7 )
  {
    v8 = v7 + 1;
    *v7 = v3;
    `vector constructor iterator'(
      v7 + 1,
      0x90u,
      (unsigned int)v3,
      (void *(*)(void *))LB_USE_COUNT_CONTAINER::LB_USE_COUNT_CONTAINER);
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 1) = v8;
  if ( v8 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= (unsigned int)v3 )
      {
        *((_DWORD *)this + 4) = v3;
        return 0;
      }
      *(_QWORD *)(*((_QWORD *)this + 1) + 144 * i + 48) = CreateEventW(0, 1, 0, 0);
      v10 = (LB_USE_COUNT_CONTAINER *)*((_QWORD *)this + 1);
      if ( !*((_QWORD *)v10 + 18 * i + 6) )
        break;
      *((_QWORD *)v10 + 18 * i + 16) = this;
    }
    if ( v10 )
      LB_USE_COUNT_CONTAINER::`vector deleting destructor'(v10, 18 * i);
  }
  return 14;
}

```

## disassembly

```asm
0x180020a9c  push    rbx
0x180020a9e  push    rbp
0x180020a9f  push    rsi
0x180020aa0  push    rdi
0x180020aa1  sub     rsp, 28h
0x180020aa5  mov     rdi, rcx
0x180020aa8  mov     esi, edx
0x180020aaa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020ab1  mov     eax, 90h
0x180020ab6  mul     rsi
0x180020ab9  cmovb   rax, rcx
0x180020abd  add     rax, 8
0x180020ac1  cmovb   rax, rcx
0x180020ac5  mov     ecx, eax; Size
0x180020ac7  call    cs:__imp_I_RpcAllocate
0x180020acd  test    rax, rax
0x180020ad0  jz      short loc_180020AF2
0x180020ad2  lea     rbx, [rax+8]
0x180020ad6  mov     [rax], rsi
0x180020ad9  mov     rcx, rbx; void *
0x180020adc  lea     r9, ??0LB_USE_COUNT_CONTAINER@@QEAA@XZ; void *(*)(void *)
0x180020ae3  mov     r8d, esi; unsigned __int64
0x180020ae6  mov     edx, 90h; unsigned __int64
0x180020aeb  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180020af0  jmp     short loc_180020AF4
0x180020af2  xor     ebx, ebx
0x180020af4  mov     [rdi+8], rbx
0x180020af8  test    rbx, rbx
0x180020afb  jz      short loc_180020B47
0x180020afd  xor     ebx, ebx
0x180020aff  cmp     ebx, esi
0x180020b01  jnb     short loc_180020B55
0x180020b03  xor     r9d, r9d; lpName
0x180020b06  xor     r8d, r8d; bInitialState
0x180020b09  xor     ecx, ecx; lpEventAttributes
0x180020b0b  lea     edx, [r9+1]; bManualReset
0x180020b0f  call    cs:__imp_CreateEventW
0x180020b15  mov     rcx, [rdi+8]
0x180020b19  lea     rdx, [rbx+rbx*8]
0x180020b1d  add     rdx, rdx; unsigned int
0x180020b20  mov     [rcx+rdx*8+30h], rax
0x180020b25  mov     rcx, [rdi+8]; this
0x180020b29  cmp     qword ptr [rcx+rdx*8+30h], 0
0x180020b2f  jz      short loc_180020B3D
0x180020b31  mov     [rcx+rdx*8+80h], rdi
0x180020b39  inc     ebx
0x180020b3b  jmp     short loc_180020AFF
0x180020b3d  test    rcx, rcx
0x180020b40  jz      short loc_180020B47
0x180020b42  call    ??_ELB_USE_COUNT_CONTAINER@@QEAAPEAXI@Z; LB_USE_COUNT_CONTAINER::`vector deleting destructor'(uint)
0x180020b47  mov     eax, 0Eh
0x180020b4c  add     rsp, 28h
0x180020b50  pop     rdi
0x180020b51  pop     rsi
0x180020b52  pop     rbp
0x180020b53  pop     rbx
0x180020b54  retn
0x180020b55  mov     [rdi+10h], esi
0x180020b58  xor     eax, eax
0x180020b5a  jmp     short loc_180020B4C
```
