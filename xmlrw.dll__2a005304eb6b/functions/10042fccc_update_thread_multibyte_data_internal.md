# update_thread_multibyte_data_internal

- ea: `0x10042fccc`
- end: `0x10042fd84`
- name: `update_thread_multibyte_data_internal`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x10042fa54`
- `0x10042fdf8`

## callees

- `0x10042b134`
- `0x10042e130`
- `0x10042e190`
- `0x10042e7dc`
- `0x10042fccc`

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
0x10042fccc  mov     [rsp+arg_8], rbx
0x10042fcd1  mov     [rsp+arg_10], rsi
0x10042fcd6  push    rdi
0x10042fcd7  sub     rsp, 20h
0x10042fcdb  mov     rsi, rdx
0x10042fcde  mov     rdi, rcx
0x10042fce1  mov     eax, cs:__globallocalestatus
0x10042fce7  test    [rcx+3A8h], eax
0x10042fced  jz      short loc_10042FD02
0x10042fcef  cmp     qword ptr [rcx+90h], 0
0x10042fcf7  jz      short loc_10042FD02
0x10042fcf9  mov     rbx, [rcx+88h]
0x10042fd00  jmp     short loc_10042FD66
0x10042fd02  mov     ecx, 5
0x10042fd07  call    __acrt_lock
0x10042fd0c  nop
0x10042fd0d  mov     rbx, [rdi+88h]
0x10042fd14  mov     [rsp+28h+Block], rbx
0x10042fd19  cmp     rbx, [rsi]
0x10042fd1c  jz      short loc_10042FD5C
0x10042fd1e  test    rbx, rbx
0x10042fd21  jz      short loc_10042FD45
0x10042fd23  or      eax, 0FFFFFFFFh
0x10042fd26  lock xadd [rbx], eax
0x10042fd2a  cmp     eax, 1
0x10042fd2d  jnz     short loc_10042FD45
0x10042fd2f  lea     rax, __acrt_initial_multibyte_data
0x10042fd36  mov     rcx, [rsp+28h+Block]; Block
0x10042fd3b  cmp     rcx, rax
0x10042fd3e  jz      short loc_10042FD45
0x10042fd40  call    _free_base
0x10042fd45  mov     rax, [rsi]
0x10042fd48  mov     [rdi+88h], rax
0x10042fd4f  mov     [rsp+28h+Block], rax
0x10042fd54  lock inc dword ptr [rax]
0x10042fd57  mov     rbx, [rsp+28h+Block]
0x10042fd5c  mov     ecx, 5
0x10042fd61  call    __acrt_unlock
0x10042fd66  test    rbx, rbx
0x10042fd69  jz      short loc_10042FD7E
0x10042fd6b  mov     rax, rbx
0x10042fd6e  mov     rbx, [rsp+28h+arg_8]
0x10042fd73  mov     rsi, [rsp+28h+arg_10]
0x10042fd78  add     rsp, 20h
0x10042fd7c  pop     rdi
0x10042fd7d  retn
0x10042fd7e  call    abort
```
