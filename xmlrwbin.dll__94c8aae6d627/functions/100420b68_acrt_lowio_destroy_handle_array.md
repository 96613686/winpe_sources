# __acrt_lowio_destroy_handle_array

- ea: `0x100420b68`
- end: `0x100420bb8`
- name: `__acrt_lowio_destroy_handle_array`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10041e6f0`

## callees

- `0x10041c24c`
- `0x100420b68`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x100420b91`
- `KERNEL32!DeleteCriticalSection` at `0x100420b91`

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
0x100420b68  test    rcx, rcx
0x100420b6b  jz      short locret_100420BB7
0x100420b6d  mov     [rsp+arg_0], rbx
0x100420b72  mov     [rsp+arg_8], rsi
0x100420b77  push    rdi
0x100420b78  sub     rsp, 20h
0x100420b7c  lea     rsi, [rcx+1200h]
0x100420b83  mov     rbx, rcx
0x100420b86  mov     rdi, rcx
0x100420b89  cmp     rcx, rsi
0x100420b8c  jz      short loc_100420BA0
0x100420b8e  mov     rcx, rdi; lpCriticalSection
0x100420b91  call    cs:__imp_DeleteCriticalSection
0x100420b97  add     rdi, 48h ; 'H'
0x100420b9b  cmp     rdi, rsi
0x100420b9e  jnz     short loc_100420B8E
0x100420ba0  mov     rcx, rbx; Block
0x100420ba3  call    _free_base
0x100420ba8  mov     rbx, [rsp+28h+arg_0]
0x100420bad  mov     rsi, [rsp+28h+arg_8]
0x100420bb2  add     rsp, 20h
0x100420bb6  pop     rdi
0x100420bb7  retn
```
