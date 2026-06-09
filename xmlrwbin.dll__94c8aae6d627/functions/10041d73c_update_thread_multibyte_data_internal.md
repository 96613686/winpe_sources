# update_thread_multibyte_data_internal

- ea: `0x10041d73c`
- end: `0x10041d7f4`
- name: `update_thread_multibyte_data_internal`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x10041d4c4`
- `0x10041d868`

## callees

- `0x10041b1a4`
- `0x10041bba0`
- `0x10041bc00`
- `0x10041c24c`
- `0x10041d73c`

## pseudocode

```c
volatile signed __int32 *__fastcall update_thread_multibyte_data_internal(__int64 a1, volatile signed __int32 **a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rax

  if ( (_globallocalestatus & *(_DWORD *)(a1 + 936)) != 0 && *(_QWORD *)(a1 + 144) )
  {
    v4 = *(volatile signed __int32 **)(a1 + 136);
  }
  else
  {
    _acrt_lock(5);
    v4 = *(volatile signed __int32 **)(a1 + 136);
    if ( v4 != *a2 )
    {
      if ( v4
        && _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1
        && v4 != (volatile signed __int32 *)_acrt_initial_multibyte_data )
      {
        free_base((void *)v4);
      }
      v5 = *a2;
      *(_QWORD *)(a1 + 136) = *a2;
      _InterlockedIncrement(v5);
      v4 = v5;
    }
    _acrt_unlock(5);
  }
  if ( !v4 )
    abort();
  return v4;
}

```

## disassembly

```asm
0x10041d73c  mov     [rsp+arg_8], rbx
0x10041d741  mov     [rsp+arg_10], rsi
0x10041d746  push    rdi
0x10041d747  sub     rsp, 20h
0x10041d74b  mov     rsi, rdx
0x10041d74e  mov     rdi, rcx
0x10041d751  mov     eax, cs:__globallocalestatus
0x10041d757  test    [rcx+3A8h], eax
0x10041d75d  jz      short loc_10041D772
0x10041d75f  cmp     qword ptr [rcx+90h], 0
0x10041d767  jz      short loc_10041D772
0x10041d769  mov     rbx, [rcx+88h]
0x10041d770  jmp     short loc_10041D7D6
0x10041d772  mov     ecx, 5
0x10041d777  call    __acrt_lock
0x10041d77c  nop
0x10041d77d  mov     rbx, [rdi+88h]
0x10041d784  mov     [rsp+28h+Block], rbx
0x10041d789  cmp     rbx, [rsi]
0x10041d78c  jz      short loc_10041D7CC
0x10041d78e  test    rbx, rbx
0x10041d791  jz      short loc_10041D7B5
0x10041d793  or      eax, 0FFFFFFFFh
0x10041d796  lock xadd [rbx], eax
0x10041d79a  cmp     eax, 1
0x10041d79d  jnz     short loc_10041D7B5
0x10041d79f  lea     rax, __acrt_initial_multibyte_data
0x10041d7a6  mov     rcx, [rsp+28h+Block]; Block
0x10041d7ab  cmp     rcx, rax
0x10041d7ae  jz      short loc_10041D7B5
0x10041d7b0  call    _free_base
0x10041d7b5  mov     rax, [rsi]
0x10041d7b8  mov     [rdi+88h], rax
0x10041d7bf  mov     [rsp+28h+Block], rax
0x10041d7c4  lock inc dword ptr [rax]
0x10041d7c7  mov     rbx, [rsp+28h+Block]
0x10041d7cc  mov     ecx, 5
0x10041d7d1  call    __acrt_unlock
0x10041d7d6  test    rbx, rbx
0x10041d7d9  jz      short loc_10041D7EE
0x10041d7db  mov     rax, rbx
0x10041d7de  mov     rbx, [rsp+28h+arg_8]
0x10041d7e3  mov     rsi, [rsp+28h+arg_10]
0x10041d7e8  add     rsp, 20h
0x10041d7ec  pop     rdi
0x10041d7ed  retn
0x10041d7ee  call    abort
```
