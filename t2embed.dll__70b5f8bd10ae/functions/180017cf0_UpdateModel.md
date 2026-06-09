# UpdateModel

- ea: `0x180017cf0`
- end: `0x180017dd3`
- name: `UpdateModel`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017920`

## callees

- `0x180006400`
- `0x180017cf0`
- `0x18001c9ec`

## pseudocode

```c
void __fastcall UpdateModel(__int64 a1, int a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbp
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // r15
  __int64 v10; // rax

  if ( a2 > 0 )
  {
    v3 = a2;
    v4 = *(unsigned __int8 *)(a2 + *(_QWORD *)a1);
    _mm_lfence();
    v5 = *(_QWORD *)(a1 + 120);
    if ( v5 )
    {
      *(_QWORD *)(a1 + 120) = *(_QWORD *)(v5 + 8);
    }
    else
    {
      v8 = *(_DWORD *)(a1 + 128);
      if ( v8 >= 4095 )
      {
        v9 = *(_QWORD *)(a1 + 136);
        v10 = MTX_mem_malloc(*(_QWORD *)(a1 + 144), 0x10000);
        *(_QWORD *)(a1 + 136) = v10;
        if ( !v10 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        *(_QWORD *)(*(_QWORD *)(a1 + 136) + 65528LL) = v9;
        v8 = 0;
      }
      v5 = *(_QWORD *)(a1 + 136) + 16LL * v8;
      *(_DWORD *)(a1 + 128) = v8 + 1;
    }
    v6 = *(unsigned __int8 *)(v3 + *(_QWORD *)a1 - 1);
    *(_DWORD *)v5 = v3 - 1;
    v7 = v4 | (v6 << 8);
    *(_QWORD *)(v5 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 8 * v7);
    *(_QWORD *)(*(_QWORD *)(a1 + 112) + 8 * v7) = v5;
  }
}

```

## disassembly

```asm
0x180017cf0  test    edx, edx
0x180017cf2  jle     short locret_180017D5E
0x180017cf4  push    rbx
0x180017cf5  push    rdi
0x180017cf6  sub     rsp, 28h
0x180017cfa  mov     rax, [rcx]
0x180017cfd  mov     rbx, rcx
0x180017d00  mov     [rsp+38h+arg_0], rbp
0x180017d05  movsxd  rdi, edx
0x180017d08  mov     [rsp+38h+arg_8], rsi
0x180017d0d  movzx   ebp, byte ptr [rdi+rax]
0x180017d11  lfence
0x180017d14  mov     r8, [rcx+78h]
0x180017d18  test    r8, r8
0x180017d1b  jz      short loc_180017D5F
0x180017d1d  mov     rax, [r8+8]
0x180017d21  mov     [rcx+78h], rax
0x180017d25  mov     rax, [rbx]
0x180017d28  mov     rsi, [rsp+38h+arg_8]
0x180017d2d  movzx   edx, byte ptr [rdi+rax-1]
0x180017d32  lea     eax, [rdi-1]
0x180017d35  mov     [r8], eax
0x180017d38  mov     rax, [rbx+70h]
0x180017d3c  shl     rdx, 8
0x180017d40  or      rdx, rbp
0x180017d43  mov     rbp, [rsp+38h+arg_0]
0x180017d48  mov     rcx, [rax+rdx*8]
0x180017d4c  mov     [r8+8], rcx
0x180017d50  mov     rax, [rbx+70h]
0x180017d54  mov     [rax+rdx*8], r8
0x180017d58  add     rsp, 28h
0x180017d5c  pop     rdi
0x180017d5d  pop     rbx
0x180017d5e  retn
0x180017d5f  mov     eax, [rcx+80h]
0x180017d65  mov     [rsp+38h+arg_10], r14
0x180017d6a  cmp     eax, 0FFFh
0x180017d6f  jge     short loc_180017D8E
0x180017d71  mov     r14, [rsp+38h+arg_10]
0x180017d76  movsxd  r8, eax
0x180017d79  shl     r8, 4
0x180017d7d  add     r8, [rbx+88h]
0x180017d84  inc     eax
0x180017d86  mov     [rbx+80h], eax
0x180017d8c  jmp     short loc_180017D25
0x180017d8e  mov     [rsp+38h+var_18], r15
0x180017d93  mov     edx, 10000h
0x180017d98  mov     r15, [rcx+88h]
0x180017d9f  mov     rcx, [rcx+90h]
0x180017da6  call    MTX_mem_malloc
0x180017dab  mov     [rbx+88h], rax
0x180017db2  test    rax, rax
0x180017db5  jnz     short loc_180017DBC
0x180017db7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017dbc  mov     rax, [rbx+88h]
0x180017dc3  mov     [rax+0FFF8h], r15
0x180017dca  xor     eax, eax
0x180017dcc  mov     r15, [rsp+38h+var_18]
0x180017dd1  jmp     short loc_180017D71
```
