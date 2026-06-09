# __acrt_lowio_destroy_handle_array

- ea: `0x100434118`
- end: `0x100434168`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100430c80`

## callees

- `0x10042e7dc`
- `0x100434118`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x100434141`
- `KERNEL32!DeleteCriticalSection` at `0x100434141`

## pseudocode

```c
void __fastcall _acrt_lowio_destroy_handle_array(char *Block)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi

  if ( Block )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)(Block + 4608);
    v3 = (struct _RTL_CRITICAL_SECTION *)Block;
    do
    {
      DeleteCriticalSection(v3);
      v3 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 72);
    }
    while ( v3 != v1 );
    free_base(Block);
  }
}

```

## disassembly

```asm
0x100434118  test    rcx, rcx
0x10043411b  jz      short locret_100434167
0x10043411d  mov     [rsp+arg_0], rbx
0x100434122  mov     [rsp+arg_8], rsi
0x100434127  push    rdi
0x100434128  sub     rsp, 20h
0x10043412c  lea     rsi, [rcx+1200h]
0x100434133  mov     rbx, rcx
0x100434136  mov     rdi, rcx
0x100434139  cmp     rcx, rsi
0x10043413c  jz      short loc_100434150
0x10043413e  mov     rcx, rdi; lpCriticalSection
0x100434141  call    cs:__imp_DeleteCriticalSection
0x100434147  add     rdi, 48h ; 'H'
0x10043414b  cmp     rdi, rsi
0x10043414e  jnz     short loc_10043413E
0x100434150  mov     rcx, rbx; Block
0x100434153  call    _free_base
0x100434158  mov     rbx, [rsp+28h+arg_0]
0x10043415d  mov     rsi, [rsp+28h+arg_8]
0x100434162  add     rsp, 20h
0x100434166  pop     rdi
0x100434167  retn
```
