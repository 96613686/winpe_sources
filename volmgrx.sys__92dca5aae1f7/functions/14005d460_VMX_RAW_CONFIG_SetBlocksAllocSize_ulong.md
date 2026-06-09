# VMX_RAW_CONFIG::SetBlocksAllocSize(ulong)

- ea: `0x14005d460`
- end: `0x14005d60e`
- name: `?SetBlocksAllocSize@VMX_RAW_CONFIG@@AEAAJK@Z`
- size: `430`
- prototype: `__int64 __fastcall(VMX_RAW_CONFIG *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400595c0`
- `0x14005961c`
- `0x140059688`

## callees

- `0x1400099d8`
- `0x14001bb80`
- `0x14001be80`
- `0x14005d460`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005d567`
- `ntoskrnl!ExAllocatePool2` at `0x14005d567`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d5fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d5fd`

## pseudocode

```c
__int64 __fastcall VMX_RAW_CONFIG::SetBlocksAllocSize(VMX_RAW_CONFIG *this, unsigned int a2)
{
  __int64 v3; // rdi
  char *Pool2; // r14
  __int64 v5; // rbp
  __int64 v6; // rdx
  unsigned int v7; // r8d
  char *v8; // rax
  void *v9; // rcx
  __int64 result; // rax

  v3 = a2;
  if ( a2 == *((_DWORD *)this + 33) )
    return 0;
  if ( !a2 )
  {
    Pool2 = 0;
LABEL_4:
    v5 = *((unsigned int *)this + 33);
    if ( (unsigned int)v3 < (unsigned int)v5 )
    {
      if ( (_DWORD)v3 )
        memmove(Pool2, *((const void **)this + 17), 24 * v3);
    }
    else
    {
      if ( (_DWORD)v5 )
        memmove(Pool2, *((const void **)this + 17), 24 * v5);
      memset(&Pool2[24 * v5], 0, 24LL * (unsigned int)(v3 - v5));
      v6 = *((unsigned int *)this + 33);
      v7 = 0;
      v8 = &Pool2[24 * v6];
      if ( (_DWORD)v3 != (_DWORD)v6 )
      {
        do
        {
          *((_DWORD *)v8 + 2) = -1;
          v8 += 24;
          ++v7;
        }
        while ( v7 < (int)v3 - *((_DWORD *)this + 33) );
      }
    }
    v9 = (void *)*((_QWORD *)this + 17);
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
    *((_QWORD *)this + 17) = Pool2;
    result = 0;
    *((_DWORD *)this + 33) = v3;
    return result;
  }
  Pool2 = (char *)ExAllocatePool2(258, 24LL * a2, 1816292694);
  if ( Pool2 )
    goto LABEL_4;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 46, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids, 3221225626LL);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14005d460  mov     [rsp+arg_18], rbx
0x14005d465  push    rdi
0x14005d466  sub     rsp, 20h
0x14005d46a  mov     rbx, rcx
0x14005d46d  mov     edi, edx
0x14005d46f  cmp     edx, [rcx+84h]
0x14005d475  jz      loc_14005D555
0x14005d47b  mov     [rsp+28h+arg_8], rsi
0x14005d480  lea     rsi, [rdi+rdi*2]
0x14005d484  shl     rsi, 3
0x14005d488  mov     [rsp+28h+arg_10], r14
0x14005d48d  test    edx, edx
0x14005d48f  jnz     loc_14005D559
0x14005d495  xor     r14d, r14d
0x14005d498  mov     [rsp+28h+arg_0], rbp
0x14005d49d  mov     ebp, [rbx+84h]
0x14005d4a3  cmp     edi, ebp
0x14005d4a5  jb      loc_14005D5C5
0x14005d4ab  lea     rcx, ds:0[rbp*2]
0x14005d4b3  add     rcx, rbp
0x14005d4b6  lea     rsi, ds:0[rcx*8]
0x14005d4be  test    ebp, ebp
0x14005d4c0  jnz     loc_14005D5E4
0x14005d4c6  mov     eax, edi
0x14005d4c8  lea     rcx, [rsi+r14]; void *
0x14005d4cc  sub     eax, ebp
0x14005d4ce  xor     edx, edx; Val
0x14005d4d0  lea     r8, [rax+rax*2]
0x14005d4d4  shl     r8, 3; Size
0x14005d4d8  call    memset
0x14005d4dd  mov     edx, [rbx+84h]
0x14005d4e3  xor     r8d, r8d
0x14005d4e6  lea     rax, [rdx+rdx*2]
0x14005d4ea  lea     rax, [r14+rax*8]
0x14005d4ee  cmp     edi, edx
0x14005d4f0  jz      short loc_14005D51B
0x14005d4f2  nop     dword ptr [rax+00h]
0x14005d4f6  nop     word ptr [rax+rax+00000000h]
0x14005d500  mov     dword ptr [rax+8], 0FFFFFFFFh
0x14005d507  lea     rax, [rax+18h]
0x14005d50b  mov     ecx, edi
0x14005d50d  inc     r8d
0x14005d510  sub     ecx, [rbx+84h]
0x14005d516  cmp     r8d, ecx
0x14005d519  jb      short loc_14005D500
0x14005d51b  mov     rcx, [rbx+88h]; P
0x14005d522  mov     rbp, [rsp+28h+arg_0]
0x14005d527  test    rcx, rcx
0x14005d52a  jnz     loc_14005D5FB
0x14005d530  mov     [rbx+88h], r14
0x14005d537  xor     eax, eax
0x14005d539  mov     [rbx+84h], edi
0x14005d53f  mov     rsi, [rsp+28h+arg_8]
0x14005d544  mov     r14, [rsp+28h+arg_10]
0x14005d549  mov     rbx, [rsp+28h+arg_18]
0x14005d54e  add     rsp, 20h
0x14005d552  pop     rdi
0x14005d553  retn
0x14005d555  xor     eax, eax
0x14005d557  jmp     short loc_14005D549
0x14005d559  mov     r8d, 6C426D56h
0x14005d55f  mov     rdx, rsi
0x14005d562  mov     ecx, 102h
0x14005d567  call    cs:__imp_ExAllocatePool2
0x14005d56e  nop     dword ptr [rax+rax+00h]
0x14005d573  mov     r14, rax
0x14005d576  test    rax, rax
0x14005d579  jnz     loc_14005D498
0x14005d57f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d586  lea     rax, WPP_GLOBAL_Control
0x14005d58d  cmp     rcx, rax
0x14005d590  jz      short loc_14005D5BB
0x14005d592  mov     edx, [rcx+2Ch]
0x14005d595  test    dl, 40h
0x14005d598  jz      short loc_14005D5BB
0x14005d59a  cmp     byte ptr [rcx+29h], 2
0x14005d59e  jb      short loc_14005D5BB
0x14005d5a0  mov     rcx, [rcx+18h]
0x14005d5a4  lea     r8, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids
0x14005d5ab  mov     edx, 2Eh ; '.'
0x14005d5b0  mov     r9d, 0C000009Ah
0x14005d5b6  call    WPP_SF_d
0x14005d5bb  mov     eax, 0C000009Ah
0x14005d5c0  jmp     loc_14005D53F
0x14005d5c5  test    edi, edi
0x14005d5c7  jz      loc_14005D51B
0x14005d5cd  mov     rdx, [rbx+88h]; Src
0x14005d5d4  mov     r8, rsi; Size
0x14005d5d7  mov     rcx, r14; void *
0x14005d5da  call    memmove
0x14005d5df  jmp     loc_14005D51B
0x14005d5e4  mov     rdx, [rbx+88h]; Src
0x14005d5eb  mov     r8, rsi; Size
0x14005d5ee  mov     rcx, r14; void *
0x14005d5f1  call    memmove
0x14005d5f6  jmp     loc_14005D4C6
0x14005d5fb  xor     edx, edx; Tag
0x14005d5fd  call    cs:__imp_ExFreePoolWithTag
0x14005d604  nop     dword ptr [rax+rax+00h]
0x14005d609  jmp     loc_14005D530
```
