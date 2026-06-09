# UdfMultiAsyncCompletionRoutine

- ea: `0x140011ea0`
- end: `0x140011fcf`
- name: `UdfMultiAsyncCompletionRoutine`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a2e8`
- `0x140011ea0`
- `0x140012088`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140011f8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f8f`
- `ntoskrnl!IoFreeMdl` at `0x140011fa3`
- `ntoskrnl!IoFreeMdl` at `0x140011fa3`
- `ntoskrnl!IoFreeIrp` at `0x140011fb2`
- `ntoskrnl!IoFreeIrp` at `0x140011fb2`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140011f65`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140011f7e`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140011f65`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140011f7e`

## pseudocode

```c
__int64 __fastcall UdfMultiAsyncCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  __int32 Status; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  struct _ERESOURCE *v8; // rcx
  struct _ERESOURCE *v9; // rcx

  Status = a2->IoStatus.Status;
  if ( Status < 0 )
  {
    _InterlockedExchange((volatile __int32 *)(a3 + 16), Status);
    a1 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
    {
      WPP_SF_Dqq(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        25,
        WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids,
        (unsigned int)a2->IoStatus.Status,
        a2,
        *(_QWORD *)(a3 + 8));
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3, 0xFFFFFFFF) == 1 )
  {
    v6 = *(_QWORD *)(a3 + 24);
    if ( (*(_DWORD *)(v6 + 48) & 0x200000) != 0 )
      UdfReleaseDevice(a1, v6, *(_QWORD *)(a3 + 48));
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 184LL) + 3LL) |= 1u;
    *(_DWORD *)(*(_QWORD *)(a3 + 8) + 48LL) = *(_DWORD *)(a3 + 16);
    *(_QWORD *)(*(_QWORD *)(a3 + 8) + 56LL) = 0;
    v7 = *(_QWORD *)(a3 + 8);
    if ( *(int *)(v7 + 48) >= 0 )
      *(_QWORD *)(v7 + 56) = *(unsigned int *)(a3 + 56);
    v8 = *(struct _ERESOURCE **)(a3 + 32);
    if ( v8 )
      ExReleaseResourceForThreadLite(v8, *(_QWORD *)(a3 + 48));
    v9 = *(struct _ERESOURCE **)(a3 + 40);
    if ( v9 )
      ExReleaseResourceForThreadLite(v9, *(_QWORD *)(a3 + 48));
    ExFreePoolWithTag((PVOID)a3, 0);
    return 0;
  }
  else
  {
    IoFreeMdl(a2->MdlAddress);
    IoFreeIrp(a2);
    return 3221225494LL;
  }
}

```

## disassembly

```asm
0x140011ea0  mov     [rsp+arg_0], rbx
0x140011ea5  push    rdi
0x140011ea6  sub     rsp, 30h
0x140011eaa  mov     eax, [rdx+30h]
0x140011ead  mov     rbx, r8
0x140011eb0  mov     rdi, rdx
0x140011eb3  test    eax, eax
0x140011eb5  jns     short loc_140011EFC
0x140011eb7  xchg    eax, [r8+10h]
0x140011ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ec2  lea     rax, WPP_GLOBAL_Control
0x140011ec9  cmp     rcx, rax
0x140011ecc  jz      short loc_140011EFC
0x140011ece  mov     eax, [rcx+2Ch]
0x140011ed1  test    al, 40h
0x140011ed3  jz      short loc_140011EFC
0x140011ed5  mov     rax, [r8+8]
0x140011ed9  mov     edx, 19h
0x140011ede  mov     r9d, [rdi+30h]
0x140011ee2  lea     r8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids
0x140011ee9  mov     rcx, [rcx+18h]
0x140011eed  mov     [rsp+38h+var_10], rax
0x140011ef2  mov     [rsp+38h+var_18], rdi
0x140011ef7  call    WPP_SF_Dqq
0x140011efc  or      eax, 0FFFFFFFFh
0x140011eff  lock xadd [rbx], eax
0x140011f03  cmp     eax, 1
0x140011f06  jnz     loc_140011F9F
0x140011f0c  mov     rdx, [rbx+18h]
0x140011f10  test    dword ptr [rdx+30h], 200000h
0x140011f17  jz      short loc_140011F22
0x140011f19  mov     r8, [rbx+30h]
0x140011f1d  call    UdfReleaseDevice
0x140011f22  mov     rax, [rbx+8]
0x140011f26  mov     rcx, [rax+0B8h]
0x140011f2d  or      byte ptr [rcx+3], 1
0x140011f31  mov     rcx, [rbx+8]
0x140011f35  mov     eax, [rbx+10h]
0x140011f38  mov     [rcx+30h], eax
0x140011f3b  mov     rax, [rbx+8]
0x140011f3f  mov     qword ptr [rax+38h], 0
0x140011f47  mov     rcx, [rbx+8]
0x140011f4b  cmp     dword ptr [rcx+30h], 0
0x140011f4f  jl      short loc_140011F58
0x140011f51  mov     eax, [rbx+38h]
0x140011f54  mov     [rcx+38h], rax
0x140011f58  mov     rcx, [rbx+20h]; Resource
0x140011f5c  test    rcx, rcx
0x140011f5f  jz      short loc_140011F71
0x140011f61  mov     rdx, [rbx+30h]; ResourceThreadId
0x140011f65  call    cs:__imp_ExReleaseResourceForThreadLite
0x140011f6c  nop     dword ptr [rax+rax+00h]
0x140011f71  mov     rcx, [rbx+28h]; Resource
0x140011f75  test    rcx, rcx
0x140011f78  jz      short loc_140011F8A
0x140011f7a  mov     rdx, [rbx+30h]; ResourceThreadId
0x140011f7e  call    cs:__imp_ExReleaseResourceForThreadLite
0x140011f85  nop     dword ptr [rax+rax+00h]
0x140011f8a  xor     edx, edx; Tag
0x140011f8c  mov     rcx, rbx; P
0x140011f8f  call    cs:__imp_ExFreePoolWithTag
0x140011f96  nop     dword ptr [rax+rax+00h]
0x140011f9b  xor     eax, eax
0x140011f9d  jmp     short loc_140011FC3
0x140011f9f  mov     rcx, [rdi+8]; Mdl
0x140011fa3  call    cs:__imp_IoFreeMdl
0x140011faa  nop     dword ptr [rax+rax+00h]
0x140011faf  mov     rcx, rdi; Irp
0x140011fb2  call    cs:__imp_IoFreeIrp
0x140011fb9  nop     dword ptr [rax+rax+00h]
0x140011fbe  mov     eax, 0C0000016h
0x140011fc3  mov     rbx, [rsp+38h+arg_0]
0x140011fc8  add     rsp, 30h
0x140011fcc  pop     rdi
0x140011fcd  retn
```
