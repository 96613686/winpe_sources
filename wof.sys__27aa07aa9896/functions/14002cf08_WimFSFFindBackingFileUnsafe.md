# WimFSFFindBackingFileUnsafe

- ea: `0x14002cf08`
- end: `0x14002cf75`
- name: `WimFSFFindBackingFileUnsafe`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002c58c`

## callees

- `0x14002cf08`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002cf33`
- `ntoskrnl!RtlCompareMemory` at `0x14002cf33`

## pseudocode

```c
__int64 __fastcall WimFSFFindBackingFileUnsafe(__int64 a1, const void *a2, __int64 a3, volatile signed __int32 **a4)
{
  __int64 *v4; // rsi
  volatile signed __int32 *i; // rbx
  __int64 result; // rax

  v4 = (__int64 *)(a1 + 24);
  for ( i = *(volatile signed __int32 **)(a1 + 24); i != (volatile signed __int32 *)v4; i = *(volatile signed __int32 **)i )
  {
    if ( RtlCompareMemory((const void *)(i + 246), a2, 0x14u) == 20 )
    {
      result = 0;
      if ( a4 )
      {
        *a4 = i;
        _InterlockedIncrement(i + 14);
      }
      return result;
    }
  }
  result = 3221226021LL;
  if ( a4 )
    *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x14002cf08  push    rbx
0x14002cf0a  push    rbp
0x14002cf0b  push    rsi
0x14002cf0c  push    rdi
0x14002cf0d  sub     rsp, 28h
0x14002cf11  lea     rsi, [rcx+18h]
0x14002cf15  mov     rdi, r9
0x14002cf18  mov     rbx, [rsi]
0x14002cf1b  mov     rbp, rdx
0x14002cf1e  cmp     rbx, rsi
0x14002cf21  jz      short loc_14002CF5A
0x14002cf23  lea     rcx, [rbx+3D8h]; Source1
0x14002cf2a  mov     r8d, 14h; Length
0x14002cf30  mov     rdx, rbp; Source2
0x14002cf33  call    cs:__imp_RtlCompareMemory
0x14002cf3a  nop     dword ptr [rax+rax+00h]
0x14002cf3f  cmp     rax, 14h
0x14002cf43  jz      short loc_14002CF4A
0x14002cf45  mov     rbx, [rbx]
0x14002cf48  jmp     short loc_14002CF1E
0x14002cf4a  xor     eax, eax
0x14002cf4c  test    rdi, rdi
0x14002cf4f  jz      short loc_14002CF6B
0x14002cf51  mov     [rdi], rbx
0x14002cf54  lock inc dword ptr [rbx+38h]
0x14002cf58  jmp     short loc_14002CF6B
0x14002cf5a  mov     eax, 0C0000225h
0x14002cf5f  test    rdi, rdi
0x14002cf62  jz      short loc_14002CF6B
0x14002cf64  mov     qword ptr [rdi], 0
0x14002cf6b  add     rsp, 28h
0x14002cf6f  pop     rdi
0x14002cf70  pop     rsi
0x14002cf71  pop     rbp
0x14002cf72  pop     rbx
0x14002cf73  retn
```
