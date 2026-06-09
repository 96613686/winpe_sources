# ConvertOldToEx(_SEC_CHANNEL_BINDINGS *,std::unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter> &)

- ea: `0x180033bb0`
- end: `0x180033ca6`
- name: `?ConvertOldToEx@@YAJPEAU_SEC_CHANNEL_BINDINGS@@AEAV?$unique_ptr@U_SEC_CHANNEL_BINDINGS_EX@@Uupgraded_channel_bindings_deleter@@@std@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180033f78`

## callees

- `0x1800139b4`
- `0x1800338d8`
- `0x180033bb0`
- `0x1800340d4`
- `0x1800377bc`

## pseudocode

```c
__int64 __fastcall ConvertOldToEx(_DWORD *a1, __int64 a2)
{
  unsigned int v4; // edi
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  unsigned int v7; // ebx
  char *v8; // rdi
  char *v9; // rdi
  char *v10; // rcx
  _DWORD *v12; // [rsp+50h] [rbp+8h] BYREF

  v4 = a1[4] + a1[1] + a1[6] + 48;
  v5 = operator new[](v4, (const struct std::nothrow_t *)std::nothrow);
  v12 = v5;
  v6 = v5;
  if ( v5 )
  {
    v5[3] = v4;
    v8 = (char *)(v5 + 12);
    *(_QWORD *)v5 = 1480933955;
    v5[2] = 48;
    v5[4] = *a1;
    v5[5] = a1[1];
    v5[6] = 48;
    memcpy_0(v5 + 12, (char *)a1 + (unsigned int)a1[2], (unsigned int)a1[1]);
    v9 = &v8[a1[1]];
    v6[7] = a1[3];
    v6[8] = a1[4];
    v6[9] = (_DWORD)v9 - (_DWORD)v6;
    memcpy_0(v9, (char *)a1 + (unsigned int)a1[5], (unsigned int)a1[4]);
    v10 = &v9[a1[4]];
    v6[10] = a1[6];
    v6[11] = (_DWORD)v10 - (_DWORD)v6;
    memcpy_0(v10, (char *)a1 + (unsigned int)a1[7], (unsigned int)a1[6]);
    std::unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>::reset(a2, v6);
    v7 = 0;
    v12 = 0;
  }
  else
  {
    v7 = -1073741801;
  }
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v12);
  return v7;
}

```

## disassembly

```asm
0x180033bb0  push    rbx
0x180033bb2  push    rbp
0x180033bb3  push    rsi
0x180033bb4  push    rdi
0x180033bb5  sub     rsp, 28h
0x180033bb9  mov     r8d, [rcx+4]
0x180033bbd  mov     rbp, rdx
0x180033bc0  mov     edi, [rcx+18h]
0x180033bc3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033bca  add     r8d, [rcx+10h]
0x180033bce  mov     rsi, rcx
0x180033bd1  add     edi, 30h ; '0'
0x180033bd4  add     edi, r8d
0x180033bd7  mov     ecx, edi; unsigned __int64
0x180033bd9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180033bde  mov     [rsp+48h+arg_0], rax
0x180033be3  mov     rbx, rax
0x180033be6  test    rax, rax
0x180033be9  jnz     short loc_180033BF5
0x180033beb  mov     ebx, 0C0000017h
0x180033bf0  jmp     loc_180033C91
0x180033bf5  mov     [rax+0Ch], edi
0x180033bf8  lea     rdi, [rax+30h]
0x180033bfc  mov     qword ptr [rax], 58454243h
0x180033c03  mov     rcx, rdi; void *
0x180033c06  mov     dword ptr [rax+8], 30h ; '0'
0x180033c0d  mov     eax, [rsi]
0x180033c0f  mov     [rbx+10h], eax
0x180033c12  mov     eax, [rsi+4]
0x180033c15  mov     [rbx+14h], eax
0x180033c18  mov     eax, edi
0x180033c1a  sub     eax, ebx
0x180033c1c  mov     [rbx+18h], eax
0x180033c1f  mov     edx, [rsi+8]
0x180033c22  mov     r8d, [rsi+4]; Size
0x180033c26  add     rdx, rsi; Src
0x180033c29  call    memcpy_0
0x180033c2e  mov     eax, [rsi+4]
0x180033c31  add     rdi, rax
0x180033c34  mov     eax, [rsi+0Ch]
0x180033c37  mov     [rbx+1Ch], eax
0x180033c3a  mov     rcx, rdi; void *
0x180033c3d  mov     eax, [rsi+10h]
0x180033c40  mov     [rbx+20h], eax
0x180033c43  mov     eax, edi
0x180033c45  sub     eax, ebx
0x180033c47  mov     [rbx+24h], eax
0x180033c4a  mov     edx, [rsi+14h]
0x180033c4d  mov     r8d, [rsi+10h]; Size
0x180033c51  add     rdx, rsi; Src
0x180033c54  call    memcpy_0
0x180033c59  mov     ecx, [rsi+10h]
0x180033c5c  mov     eax, [rsi+18h]
0x180033c5f  add     rcx, rdi; void *
0x180033c62  mov     [rbx+28h], eax
0x180033c65  mov     eax, ecx
0x180033c67  sub     eax, ebx
0x180033c69  mov     [rbx+2Ch], eax
0x180033c6c  mov     edx, [rsi+1Ch]
0x180033c6f  mov     r8d, [rsi+18h]; Size
0x180033c73  add     rdx, rsi; Src
0x180033c76  call    memcpy_0
0x180033c7b  mov     rdx, rbx
0x180033c7e  mov     rcx, rbp
0x180033c81  call    ?reset@?$unique_ptr@U_SEC_CHANNEL_BINDINGS_EX@@Uupgraded_channel_bindings_deleter@@@std@@QEAAXPEAU_SEC_CHANNEL_BINDINGS_EX@@@Z; std::unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>::reset(_SEC_CHANNEL_BINDINGS_EX *)
0x180033c86  xor     ebx, ebx
0x180033c88  mov     [rsp+48h+arg_0], 0
0x180033c91  lea     rcx, [rsp+48h+arg_0]
0x180033c96  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180033c9b  mov     eax, ebx
0x180033c9d  add     rsp, 28h
0x180033ca1  pop     rdi
0x180033ca2  pop     rsi
0x180033ca3  pop     rbp
0x180033ca4  pop     rbx
0x180033ca5  retn
```
