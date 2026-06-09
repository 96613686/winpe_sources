# std::_Copy_memmove_n<uchar *,uchar *>(uchar *,unsigned __int64,uchar *)

- ea: `0x18000a0fc`
- end: `0x18000a129`
- name: `??$_Copy_memmove_n@PEAEPEAE@std@@YAPEAEPEAE_K0@Z`
- size: `45`
- prototype: `__int64 __fastcall(void *Src, size_t Size, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009fe0`

## callees

- `0x18000feb4`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove_n<unsigned char *,unsigned char *>(void *Src, size_t Size, void *a3)
{
  memmove_0(a3, Src, Size);
  return (__int64)a3 + Size;
}

```

## disassembly

```asm
0x18000a0fc  mov     [rsp+arg_0], rbx
0x18000a101  push    rdi
0x18000a102  sub     rsp, 20h
0x18000a106  mov     rdi, r8
0x18000a109  mov     rbx, rdx
0x18000a10c  mov     r8, rdx; Size
0x18000a10f  mov     rdx, rcx; Src
0x18000a112  mov     rcx, rdi; void *
0x18000a115  call    memmove_0
0x18000a11a  lea     rax, [rbx+rdi]
0x18000a11e  mov     rbx, [rsp+28h+arg_0]
0x18000a123  add     rsp, 20h
0x18000a127  pop     rdi
0x18000a128  retn
```
