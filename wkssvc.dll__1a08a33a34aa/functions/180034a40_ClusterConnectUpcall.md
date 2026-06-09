# ClusterConnectUpcall

- ea: `0x180034a40`
- end: `0x180034c1c`
- name: `ClusterConnectUpcall`
- size: `476`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c1b4`
- `0x18000ea98`
- `0x18001fbd0`
- `0x180024550`
- `0x180034a40`
- `0x180036191`
- `0x180037010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180034a94`
- `ntdll!RtlAcquireResourceShared` at `0x180034a94`
- `ntdll!RtlReleaseResource` at `0x180034bd4`
- `ntdll!RtlReleaseResource` at `0x180034bd4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180034b89`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180034b89`

## pseudocode

```c
void __fastcall ClusterConnectUpcall(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        const void **a3,
        const void **a4,
        __int64 a5,
        __int128 *a6,
        int a7)
{
  _WORD *v10; // rdi
  _WORD *v11; // rax
  _WORD *v12; // rbx
  unsigned int v13; // eax
  void *v14; // rax
  unsigned int v15; // eax
  unsigned int Reply; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+38h] [rbp-40h] BYREF

  Reply = 0;
  v10 = 0;
  v17 = *a6;
  RtlAcquireResourceShared(&UpcallServerResource, 1u);
  if ( UpcallServerState == 1 )
  {
    v11 = MemoryAlloc(*(unsigned __int16 *)a3 + 2LL);
    v12 = v11;
    if ( v11
      && (memcpy_0(v11, a3[1], *(unsigned __int16 *)a3),
          v12[(unsigned __int64)*(unsigned __int16 *)a3 >> 1] = 0,
          v14 = MemoryAlloc(*(unsigned __int16 *)a4 + 2LL),
          (v10 = v14) != 0) )
    {
      memcpy_0(v14, a4[1], *(unsigned __int16 *)a4);
      v10[(unsigned __int64)*(unsigned __int16 *)a4 >> 1] = 0;
      v13 = (*(__int64 (__fastcall **)(_WORD *, _WORD *, __int64, __int128 *, int))pUpcallDispatch)(
              v12,
              v10,
              a5,
              &v17,
              a7);
    }
    else
    {
      v13 = 14;
    }
  }
  else
  {
    v12 = 0;
    v13 = 87;
  }
  Reply = v13;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 24, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v13);
  }
  v15 = RpcAsyncCompleteCall(pAsync, &Reply);
  Reply = v15;
  if ( v15
    && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 25, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v15);
  }
  RtlReleaseResource(&UpcallServerResource);
  if ( v12 )
    MemoryFree(v12);
  if ( v10 )
    MemoryFree(v10);
}

```

## disassembly

```asm
0x180034a40  mov     [rsp+arg_8], rbx
0x180034a45  push    rbp
0x180034a46  push    rsi
0x180034a47  push    rdi
0x180034a48  push    r14
0x180034a4a  push    r15
0x180034a4c  sub     rsp, 50h
0x180034a50  mov     rax, cs:__security_cookie
0x180034a57  xor     rax, rsp
0x180034a5a  mov     [rsp+78h+var_30], rax
0x180034a5f  mov     rax, [rsp+78h+arg_28]
0x180034a67  mov     r14, rcx
0x180034a6a  mov     r15, [rsp+78h+arg_20]
0x180034a72  lea     rcx, UpcallServerResource; Resource
0x180034a79  mov     dl, 1; Wait
0x180034a7b  mov     [rsp+78h+Reply], 0
0x180034a83  mov     rbp, r9
0x180034a86  mov     rsi, r8
0x180034a89  movups  xmm0, xmmword ptr [rax]
0x180034a8c  xor     edi, edi
0x180034a8e  movdqu  [rsp+78h+var_40], xmm0
0x180034a94  call    cs:__imp_RtlAcquireResourceShared
0x180034a9b  nop     dword ptr [rax+rax+00h]
0x180034aa0  cmp     cs:UpcallServerState, 1
0x180034aa7  jnz     loc_180034B41
0x180034aad  movzx   ecx, word ptr [rsi]
0x180034ab0  add     rcx, 2; unsigned __int64
0x180034ab4  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180034ab9  mov     rbx, rax
0x180034abc  test    rax, rax
0x180034abf  jnz     short loc_180034AC8
0x180034ac1  mov     eax, 0Eh
0x180034ac6  jmp     short loc_180034B46
0x180034ac8  movzx   r8d, word ptr [rsi]; Size
0x180034acc  mov     rcx, rbx; void *
0x180034acf  mov     rdx, [rsi+8]; Src
0x180034ad3  call    memcpy_0
0x180034ad8  movzx   ecx, word ptr [rsi]
0x180034adb  xor     eax, eax
0x180034add  shr     rcx, 1
0x180034ae0  mov     [rbx+rcx*2], ax
0x180034ae4  movzx   ecx, word ptr [rbp+0]
0x180034ae8  add     rcx, 2; unsigned __int64
0x180034aec  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180034af1  mov     rdi, rax
0x180034af4  test    rax, rax
0x180034af7  jz      short loc_180034AC1
0x180034af9  movzx   r8d, word ptr [rbp+0]; Size
0x180034afe  mov     rcx, rax; void *
0x180034b01  mov     rdx, [rbp+8]; Src
0x180034b05  call    memcpy_0
0x180034b0a  movzx   ecx, word ptr [rbp+0]
0x180034b0e  lea     r9, [rsp+78h+var_40]
0x180034b13  shr     rcx, 1
0x180034b16  xor     eax, eax
0x180034b18  mov     r8, r15
0x180034b1b  mov     rdx, rdi
0x180034b1e  mov     [rdi+rcx*2], ax
0x180034b22  mov     rax, cs:pUpcallDispatch
0x180034b29  mov     ecx, [rsp+78h+arg_30]
0x180034b30  mov     [rsp+78h+var_58], ecx
0x180034b34  mov     rcx, rbx
0x180034b37  mov     rax, [rax]
0x180034b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b3f  jmp     short loc_180034B46
0x180034b41  xor     ebx, ebx
0x180034b43  lea     eax, [rbx+57h]
0x180034b46  mov     [rsp+78h+Reply], eax
0x180034b4a  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034b51  lea     rsi, WPP_witness_GLOBAL_Control
0x180034b58  cmp     rcx, rsi
0x180034b5b  jz      short loc_180034B81
0x180034b5d  test    byte ptr [rcx+1Ch], 1
0x180034b61  jz      short loc_180034B81
0x180034b63  cmp     byte ptr [rcx+19h], 3
0x180034b67  jb      short loc_180034B81
0x180034b69  mov     rcx, [rcx+10h]
0x180034b6d  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180034b74  mov     edx, 18h
0x180034b79  mov     r9d, eax
0x180034b7c  call    WPP_SF_d
0x180034b81  lea     rdx, [rsp+78h+Reply]; Reply
0x180034b86  mov     rcx, r14; pAsync
0x180034b89  call    cs:__imp_RpcAsyncCompleteCall
0x180034b90  nop     dword ptr [rax+rax+00h]
0x180034b95  mov     [rsp+78h+Reply], eax
0x180034b99  test    eax, eax
0x180034b9b  jz      short loc_180034BCD
0x180034b9d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034ba4  cmp     rcx, rsi
0x180034ba7  jz      short loc_180034BCD
0x180034ba9  test    byte ptr [rcx+1Ch], 1
0x180034bad  jz      short loc_180034BCD
0x180034baf  cmp     byte ptr [rcx+19h], 1
0x180034bb3  jb      short loc_180034BCD
0x180034bb5  mov     rcx, [rcx+10h]
0x180034bb9  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180034bc0  mov     edx, 19h
0x180034bc5  mov     r9d, eax
0x180034bc8  call    WPP_SF_d
0x180034bcd  lea     rcx, UpcallServerResource; Resource
0x180034bd4  call    cs:__imp_RtlReleaseResource
0x180034bdb  nop     dword ptr [rax+rax+00h]
0x180034be0  test    rbx, rbx
0x180034be3  jz      short loc_180034BED
0x180034be5  mov     rcx, rbx; void *
0x180034be8  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180034bed  test    rdi, rdi
0x180034bf0  jz      short loc_180034BFA
0x180034bf2  mov     rcx, rdi; void *
0x180034bf5  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180034bfa  mov     rcx, [rsp+78h+var_30]
0x180034bff  xor     rcx, rsp; StackCookie
0x180034c02  call    __security_check_cookie
0x180034c07  mov     rbx, [rsp+78h+arg_8]
0x180034c0f  add     rsp, 50h
0x180034c13  pop     r15
0x180034c15  pop     r14
0x180034c17  pop     rdi
0x180034c18  pop     rsi
0x180034c19  pop     rbp
0x180034c1a  retn
```
