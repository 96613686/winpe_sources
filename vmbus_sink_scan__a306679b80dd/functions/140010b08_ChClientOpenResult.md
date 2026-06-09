# ChClientOpenResult

- ea: `0x140010b08`
- end: `0x140010c9a`
- name: `ChClientOpenResult`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140011920`

## callees

- `0x14000bddc`
- `0x140010b08`
- `0x140010f54`
- `0x140017190`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140010c16`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010c6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010c16`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010c6a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140010ba1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140010bea`
- `ntoskrnl!ExAcquireFastMutex` at `0x140010ba1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140010bea`

## pseudocode

```c
void __fastcall ChClientOpenResult(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rdx
  __int64 v6; // r15
  _BYTE *v7; // r14
  __int64 v8; // r13
  __int64 v9; // rbx
  unsigned int v10; // edi
  int v11; // eax
  void (__fastcall *v12)(__int64, _QWORD); // rbx
  __int64 v13; // rdi

  v5 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 760), 1u) & 0x1F;
  *(_DWORD *)(a1 + 16 * (v5 + 48)) = 26;
  *(_QWORD *)(a1 + 16 * v5 + 776) = MEMORY[0xFFFFF78000000008];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_af99634d4c5d304f7ae1df5facb85a1e_Traceguids, a1, a3);
  }
  v6 = *(_QWORD *)(a1 + 216);
  ExAcquireFastMutex((PFAST_MUTEX)(v6 + 432));
  if ( *(_DWORD *)(a1 + 728) == 1 )
  {
    if ( a3 < 0 )
    {
      ChpReleaseOpenChannelState(a1);
      v11 = 0;
    }
    else
    {
      v7 = *(_BYTE **)(a1 + 232);
      if ( v7 )
      {
        v8 = *(_QWORD *)v7;
        if ( *(_QWORD *)(*(_QWORD *)v7 + 1096LL) )
        {
          v9 = *(_QWORD *)(a1 + 64);
          v10 = *(_DWORD *)(a1 + 672);
          ExAcquireFastMutex((PFAST_MUTEX)(v8 + 240));
          if ( (*(int (__fastcall **)(_BYTE *, _QWORD, __int64))(v8 + 1096))(v7, v10, v9) >= 0 )
            v7[38] = 1;
          ExReleaseFastMutex((PFAST_MUTEX)(v8 + 240));
        }
      }
      v11 = 2;
    }
    *(_DWORD *)(a1 + 728) = v11;
    v12 = *(void (__fastcall **)(__int64, _QWORD))(a1 + 696);
    v13 = *(_QWORD *)(a1 + 704);
    *(_QWORD *)(a1 + 696) = 0;
    *(_QWORD *)(a1 + 704) = 0;
  }
  else
  {
    v13 = 0;
    v12 = 0;
  }
  ExReleaseFastMutex((PFAST_MUTEX)(v6 + 432));
  if ( v12 )
    v12(v13, (unsigned int)a3);
}

```

## disassembly

```asm
0x140010b08  push    rbx
0x140010b0a  push    rbp
0x140010b0b  push    rsi
0x140010b0c  push    rdi
0x140010b0d  push    r12
0x140010b0f  push    r13
0x140010b11  push    r14
0x140010b13  push    r15
0x140010b15  sub     rsp, 38h
0x140010b19  mov     ebx, 1
0x140010b1e  mov     ebp, r8d
0x140010b21  mov     edx, ebx
0x140010b23  mov     rsi, rcx
0x140010b26  lock xadd [rcx+2F8h], edx
0x140010b2e  add     edx, ebx
0x140010b30  sub     edx, ebx
0x140010b32  and     edx, 1Fh
0x140010b35  lea     rax, [rdx+30h]
0x140010b39  add     rax, rax
0x140010b3c  add     rdx, rdx
0x140010b3f  mov     dword ptr [rcx+rax*8], 1Ah
0x140010b46  mov     rax, ds:0FFFFF78000000008h
0x140010b50  mov     [rcx+rdx*8+308h], rax
0x140010b58  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b5f  lea     rax, WPP_GLOBAL_Control
0x140010b66  cmp     rcx, rax
0x140010b69  jz      short loc_140010B93
0x140010b6b  mov     eax, [rcx+2Ch]
0x140010b6e  test    al, 40h
0x140010b70  jz      short loc_140010B93
0x140010b72  cmp     byte ptr [rcx+29h], 5
0x140010b76  jb      short loc_140010B93
0x140010b78  mov     rcx, [rcx+18h]
0x140010b7c  lea     edx, [rbx+0Ah]
0x140010b7f  mov     [rsp+78h+var_58], r8d
0x140010b84  mov     r9, rsi
0x140010b87  lea     r8, WPP_af99634d4c5d304f7ae1df5facb85a1e_Traceguids
0x140010b8e  call    WPP_SF_qd
0x140010b93  mov     r15, [rsi+0D8h]
0x140010b9a  lea     rcx, [r15+1B0h]; FastMutex
0x140010ba1  call    cs:__imp_ExAcquireFastMutex
0x140010ba8  nop     dword ptr [rax+rax+00h]
0x140010bad  cmp     [rsi+2D8h], ebx
0x140010bb3  jnz     loc_140010C5F
0x140010bb9  test    ebp, ebp
0x140010bbb  js      short loc_140010C29
0x140010bbd  mov     r14, [rsi+0E8h]
0x140010bc4  test    r14, r14
0x140010bc7  jz      short loc_140010C22
0x140010bc9  mov     r13, [r14]
0x140010bcc  cmp     qword ptr [r13+448h], 0
0x140010bd4  jz      short loc_140010C22
0x140010bd6  mov     rbx, [rsi+40h]
0x140010bda  lea     r12, [r13+0F0h]
0x140010be1  mov     edi, [rsi+2A0h]
0x140010be7  mov     rcx, r12; FastMutex
0x140010bea  call    cs:__imp_ExAcquireFastMutex
0x140010bf1  nop     dword ptr [rax+rax+00h]
0x140010bf6  mov     rax, [r13+448h]
0x140010bfd  mov     r8, rbx
0x140010c00  mov     edx, edi
0x140010c02  mov     rcx, r14
0x140010c05  call    _guard_dispatch_icall
0x140010c0a  test    eax, eax
0x140010c0c  js      short loc_140010C13
0x140010c0e  mov     byte ptr [r14+26h], 1
0x140010c13  mov     rcx, r12; FastMutex
0x140010c16  call    cs:__imp_ExReleaseFastMutex
0x140010c1d  nop     dword ptr [rax+rax+00h]
0x140010c22  mov     eax, 2
0x140010c27  jmp     short loc_140010C33
0x140010c29  mov     rcx, rsi
0x140010c2c  call    ChpReleaseOpenChannelState
0x140010c31  xor     eax, eax
0x140010c33  mov     [rsi+2D8h], eax
0x140010c39  mov     rbx, [rsi+2B8h]
0x140010c40  mov     rdi, [rsi+2C0h]
0x140010c47  mov     qword ptr [rsi+2B8h], 0
0x140010c52  mov     qword ptr [rsi+2C0h], 0
0x140010c5d  jmp     short loc_140010C63
0x140010c5f  xor     edi, edi
0x140010c61  xor     ebx, ebx
0x140010c63  lea     rcx, [r15+1B0h]; FastMutex
0x140010c6a  call    cs:__imp_ExReleaseFastMutex
0x140010c71  nop     dword ptr [rax+rax+00h]
0x140010c76  test    rbx, rbx
0x140010c79  jz      short loc_140010C88
0x140010c7b  mov     edx, ebp
0x140010c7d  mov     rcx, rdi
0x140010c80  mov     rax, rbx
0x140010c83  call    _guard_dispatch_icall
0x140010c88  add     rsp, 38h
0x140010c8c  pop     r15
0x140010c8e  pop     r14
0x140010c90  pop     r13
0x140010c92  pop     r12
0x140010c94  pop     rdi
0x140010c95  pop     rsi
0x140010c96  pop     rbp
0x140010c97  pop     rbx
0x140010c98  retn
```
