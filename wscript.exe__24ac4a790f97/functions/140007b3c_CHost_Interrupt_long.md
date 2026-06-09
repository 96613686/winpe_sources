# CHost::Interrupt(long)

- ea: `0x140007b3c`
- end: `0x140007c0e`
- name: `?Interrupt@CHost@@QEAAJJ@Z`
- size: `210`
- prototype: `__int64 __fastcall(CHost *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140002cd0`
- `0x14000e86c`
- `0x14000fc40`

## callees

- `0x14000169c`
- `0x140001864`
- `0x140007b3c`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall CHost::Interrupt(CHost *this, __int32 a2)
{
  CCriticalSection *v2; // rsi
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  _QWORD v9[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  __int64 v13; // [rsp+60h] [rbp-18h]
  __int32 v14; // [rsp+68h] [rbp-10h]
  int v15; // [rsp+6Ch] [rbp-Ch]

  v2 = (CHost *)((char *)this + 696);
  _InterlockedExchange((volatile __int32 *)this + 10, a2);
  v9[0] = 0;
  v11 = 0;
  v15 = 0;
  v9[1] = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = a2;
  if ( !(unsigned int)CCriticalSection::Enter((CHost *)((char *)this + 696)) )
    return 2147500037LL;
  v5 = *((_QWORD *)this + 79);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64))(**(_QWORD **)(v5 + 96) + 112LL))(
           *(_QWORD *)(v5 + 96),
           4294967293LL,
           v9,
           2);
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
  }
  else
  {
    v8 = *((_QWORD *)this + 85);
    v7 = -2147467259;
    if ( v8 )
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 32LL))(v8, v9);
  }
  CCriticalSection::Leave(v2);
  return v7;
}

```

## disassembly

```asm
0x140007b3c  push    rbp
0x140007b3e  push    rbx
0x140007b3f  push    rsi
0x140007b40  push    rdi
0x140007b41  mov     rbp, rsp
0x140007b44  sub     rsp, 78h
0x140007b48  mov     eax, edx
0x140007b4a  lea     rsi, [rcx+2B8h]
0x140007b51  xchg    eax, [rcx+28h]
0x140007b54  mov     rdi, rcx
0x140007b57  mov     [rbp+var_48], 0
0x140007b5f  xorps   xmm0, xmm0
0x140007b62  mov     [rbp+var_28], 0
0x140007b6a  mov     rcx, rsi; this
0x140007b6d  mov     [rbp+var_C], 0
0x140007b74  mov     [rbp+var_40], 0
0x140007b7c  movdqa  [rbp+var_38], xmm0
0x140007b81  mov     [rbp+var_20], 0
0x140007b89  mov     [rbp+var_18], 0
0x140007b91  mov     [rbp+var_10], edx
0x140007b94  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x140007b99  test    eax, eax
0x140007b9b  jnz     short loc_140007BA4
0x140007b9d  mov     eax, 80004005h
0x140007ba2  jmp     short loc_140007C05
0x140007ba4  mov     rcx, [rdi+278h]
0x140007bab  test    rcx, rcx
0x140007bae  jz      short loc_140007BD8
0x140007bb0  mov     rcx, [rcx+60h]
0x140007bb4  lea     r8, [rbp+var_48]
0x140007bb8  mov     r9d, 2
0x140007bbe  mov     edx, 0FFFFFFFDh
0x140007bc3  mov     rax, [rcx]
0x140007bc6  mov     rax, [rax+70h]
0x140007bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bcf  xor     ebx, ebx
0x140007bd1  test    eax, eax
0x140007bd3  cmovs   ebx, eax
0x140007bd6  jmp     short loc_140007BFB
0x140007bd8  mov     rcx, [rdi+2A8h]
0x140007bdf  mov     ebx, 80004005h
0x140007be4  test    rcx, rcx
0x140007be7  jz      short loc_140007BFB
0x140007be9  mov     rax, [rcx]
0x140007bec  lea     rdx, [rbp+var_48]
0x140007bf0  mov     rax, [rax+20h]
0x140007bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bf9  mov     ebx, eax
0x140007bfb  mov     rcx, rsi; this
0x140007bfe  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x140007c03  mov     eax, ebx
0x140007c05  add     rsp, 78h
0x140007c09  pop     rdi
0x140007c0a  pop     rsi
0x140007c0b  pop     rbx
0x140007c0c  pop     rbp
0x140007c0d  retn
```
