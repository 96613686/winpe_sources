# comp_alloc_compress_memory

- ea: `0x14000a578`
- end: `0x14000a761`
- name: `comp_alloc_compress_memory`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140011270`

## callees

- `0x14000a578`
- `0x14000a768`
- `0x14000a8cc`
- `0x14000c754`
- `0x14000ce48`
- `0x14000d36c`
- `0x140011640`

## pseudocode

```c
__int64 __fastcall comp_alloc_compress_memory(__int64 a1)
{
  unsigned int v1; // r9d
  unsigned int v2; // edx
  int v3; // r8d
  __int64 (__fastcall *v5)(__int64); // rax
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int mem_window_alloc_size; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax

  v1 = *(_DWORD *)(a1 + 8);
  v2 = 4;
  v3 = 4;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 17280) = 0;
  *(_QWORD *)(a1 + 17288) = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 17272) = 0;
  *(_QWORD *)(a1 + 9600) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 2176) = 0;
  do
    v2 += 1 << dec_extra_bits[v3++];
  while ( v2 < v1 );
  v5 = *(__int64 (__fastcall **)(__int64))(a1 + 17312);
  *(_DWORD *)(a1 + 2208) = v3;
  v6 = v5(0x40000);
  *(_QWORD *)(a1 + 16) = v6;
  if ( !v6 )
    goto LABEL_14;
  v7 = 4LL * (unsigned int)get_mem_window_alloc_size(a1);
  if ( v7 > 0xFFFFFFFF )
    goto LABEL_14;
  v8 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 17312))((unsigned int)v7);
  *(_QWORD *)(a1 + 17280) = v8;
  if ( !v8 )
    goto LABEL_14;
  v9 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 17312))((unsigned int)v7);
  *(_QWORD *)(a1 + 17288) = v9;
  if ( !v9 )
    goto LABEL_14;
  mem_window_alloc_size = get_mem_window_alloc_size(a1);
  v11 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 17312))(mem_window_alloc_size);
  *(_QWORD *)(a1 + 17272) = v11;
  if ( !v11 )
    goto LABEL_14;
  *(_QWORD *)a1 = v11;
  v12 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(0x10000);
  *(_QWORD *)(a1 + 72) = v12;
  if ( !v12 )
    goto LABEL_14;
  v13 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(0x20000);
  *(_QWORD *)(a1 + 64) = v13;
  if ( !v13 )
    goto LABEL_14;
  v14 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(0x2000);
  *(_QWORD *)(a1 + 80) = v14;
  if ( v14
    && (create_slot_lookup_table(a1), create_ones_table(a1), (unsigned int)init_compressed_output_buffer(a1))
    && (v15 = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(98640), (*(_QWORD *)(a1 + 9600) = v15) != 0) )
  {
    *(_DWORD *)(a1 + 2216) = 1;
    return 1;
  }
  else
  {
LABEL_14:
    comp_free_compress_memory(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x14000a578  mov     [rsp+arg_0], rbx
0x14000a57d  push    rdi
0x14000a57e  sub     rsp, 20h
0x14000a582  mov     r9d, [rcx+8]
0x14000a586  mov     edx, 4
0x14000a58b  mov     r8d, edx
0x14000a58e  mov     qword ptr [rcx+10h], 0
0x14000a596  mov     rbx, rcx
0x14000a599  mov     qword ptr [rcx+4380h], 0
0x14000a5a4  mov     qword ptr [rcx+4388h], 0
0x14000a5af  mov     qword ptr [rcx], 0
0x14000a5b6  mov     qword ptr [rcx+4378h], 0
0x14000a5c1  mov     qword ptr [rcx+2580h], 0
0x14000a5cc  mov     qword ptr [rcx+48h], 0
0x14000a5d4  mov     qword ptr [rcx+40h], 0
0x14000a5dc  mov     qword ptr [rcx+50h], 0
0x14000a5e4  mov     qword ptr [rcx+880h], 0
0x14000a5ef  mov     ecx, r8d
0x14000a5f2  lea     rax, dec_extra_bits
0x14000a5f9  mov     cl, [rcx+rax]
0x14000a5fc  mov     eax, 1
0x14000a601  shl     eax, cl
0x14000a603  add     edx, eax
0x14000a605  inc     r8d
0x14000a608  cmp     edx, r9d
0x14000a60b  jb      short loc_14000A5EF
0x14000a60d  mov     rax, [rbx+43A0h]
0x14000a614  mov     ecx, 40000h
0x14000a619  mov     [rbx+8A0h], r8d
0x14000a620  call    _guard_dispatch_icall
0x14000a625  mov     [rbx+10h], rax
0x14000a629  test    rax, rax
0x14000a62c  jz      loc_14000A74B
0x14000a632  mov     rcx, rbx
0x14000a635  call    get_mem_window_alloc_size
0x14000a63a  mov     edi, eax
0x14000a63c  mov     eax, 0FFFFFFFFh
0x14000a641  shl     rdi, 2
0x14000a645  cmp     rdi, rax
0x14000a648  ja      loc_14000A74B
0x14000a64e  mov     rax, [rbx+43A0h]
0x14000a655  mov     ecx, edi
0x14000a657  call    _guard_dispatch_icall
0x14000a65c  mov     [rbx+4380h], rax
0x14000a663  test    rax, rax
0x14000a666  jz      loc_14000A74B
0x14000a66c  mov     rax, [rbx+43A0h]
0x14000a673  mov     ecx, edi
0x14000a675  call    _guard_dispatch_icall
0x14000a67a  mov     [rbx+4388h], rax
0x14000a681  test    rax, rax
0x14000a684  jz      loc_14000A74B
0x14000a68a  mov     rcx, rbx
0x14000a68d  call    get_mem_window_alloc_size
0x14000a692  mov     ecx, eax
0x14000a694  mov     rax, [rbx+43A0h]
0x14000a69b  call    _guard_dispatch_icall
0x14000a6a0  mov     [rbx+4378h], rax
0x14000a6a7  test    rax, rax
0x14000a6aa  jz      loc_14000A74B
0x14000a6b0  mov     [rbx], rax
0x14000a6b3  mov     ecx, 10000h
0x14000a6b8  mov     rax, [rbx+43A0h]
0x14000a6bf  call    _guard_dispatch_icall
0x14000a6c4  mov     [rbx+48h], rax
0x14000a6c8  test    rax, rax
0x14000a6cb  jz      short loc_14000A74B
0x14000a6cd  mov     rax, [rbx+43A0h]
0x14000a6d4  mov     ecx, 20000h
0x14000a6d9  call    _guard_dispatch_icall
0x14000a6de  mov     [rbx+40h], rax
0x14000a6e2  test    rax, rax
0x14000a6e5  jz      short loc_14000A74B
0x14000a6e7  mov     rax, [rbx+43A0h]
0x14000a6ee  mov     ecx, 2000h
0x14000a6f3  call    _guard_dispatch_icall
0x14000a6f8  mov     [rbx+50h], rax
0x14000a6fc  test    rax, rax
0x14000a6ff  jz      short loc_14000A74B
0x14000a701  mov     rcx, rbx
0x14000a704  call    create_slot_lookup_table
0x14000a709  mov     rcx, rbx
0x14000a70c  call    create_ones_table
0x14000a711  mov     rcx, rbx
0x14000a714  call    init_compressed_output_buffer
0x14000a719  test    eax, eax
0x14000a71b  jz      short loc_14000A74B
0x14000a71d  mov     rax, [rbx+43A0h]
0x14000a724  mov     ecx, 18150h
0x14000a729  call    _guard_dispatch_icall
0x14000a72e  mov     [rbx+2580h], rax
0x14000a735  test    rax, rax
0x14000a738  jz      short loc_14000A74B
0x14000a73a  mov     dword ptr [rbx+8A8h], 1
0x14000a744  mov     eax, 1
0x14000a749  jmp     short loc_14000A755
0x14000a74b  mov     rcx, rbx
0x14000a74e  call    comp_free_compress_memory
0x14000a753  xor     eax, eax
0x14000a755  mov     rbx, [rsp+28h+arg_0]
0x14000a75a  add     rsp, 20h
0x14000a75e  pop     rdi
0x14000a75f  retn
```
