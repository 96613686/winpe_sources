# RtlCopyFromUser

- ea: `0x1400d4e8c`
- end: `0x1400d4eec`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `49`
- callee_count: `3`
- tags: ``

## callers

- `0x1400134f4`
- `0x14001ce38`
- `0x140021428`
- `0x14002a460`
- `0x140038870`
- `0x14003ffbc`
- `0x140040250`
- `0x1400406a4`
- `0x140040e04`
- `0x140041234`
- `0x1400416dc`
- `0x14004244c`
- `0x140042afc`
- `0x140042c40`
- `0x140043038`
- `0x140044378`
- `0x14005c1e0`
- `0x140064ea0`
- `0x140066b20`
- `0x1400671bc`
- `0x140089b8c`
- `0x14009c610`
- `0x1400a1a40`
- `0x1400ad5c4`
- `0x1400adaf8`
- `0x1400addd0`
- `0x1400adfe8`
- `0x1400aec78`
- `0x1400af1cc`
- `0x1400b0bc0`
- `0x1400b10f8`
- `0x1400b15f4`
- `0x1400b17a4`
- `0x1400b18ac`
- `0x1400b2164`
- `0x1400b3d38`
- `0x1400b6c24`
- `0x1400b6e68`
- `0x1400bb42c`
- `0x1400be778`
- `0x1400be910`
- `0x1400bed44`
- `0x1400c32c4`
- `0x1400c3614`
- `0x1400e0338`
- `0x1400e19d8`
- `0x1400e1a08`
- `0x1400fdde4`
- `0x140107010`

## callees

- `0x1400442ac`
- `0x1400d4e8c`
- `0x1400f38f0`

## pseudocode

```c
__int64 (*__fastcall RtlCopyFromUser(void *a1, void *Src, size_t Size))(void)
{
  __int64 (*result)(void); // rax

  result = _uma_functions;
  if ( _uma_functions )
    return (__int64 (*)(void))_uma_functions();
  if ( Size )
  {
    ProbeForRead(Src, Size, 1u);
    return (__int64 (*)(void))RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x1400d4e8c  mov     [rsp+arg_0], rbx
0x1400d4e91  mov     [rsp+arg_8], rsi
0x1400d4e96  push    rdi
0x1400d4e97  sub     rsp, 20h
0x1400d4e9b  mov     rax, cs:__uma_functions
0x1400d4ea2  mov     rbx, r8
0x1400d4ea5  mov     rdi, rdx
0x1400d4ea8  mov     rsi, rcx
0x1400d4eab  test    rax, rax
0x1400d4eae  jz      short loc_1400D4EB7
0x1400d4eb0  call    rax ; __uma_functions
0x1400d4eb2  nop     dword ptr [rax]
0x1400d4eb5  jmp     short loc_1400D4EDB
0x1400d4eb7  test    rbx, rbx
0x1400d4eba  jz      short loc_1400D4EDB
0x1400d4ebc  mov     r8d, 1; Alignment
0x1400d4ec2  mov     rdx, rbx; Length
0x1400d4ec5  mov     rcx, rdi; Address
0x1400d4ec8  call    ProbeForRead
0x1400d4ecd  mov     r8, rbx; Size
0x1400d4ed0  mov     rdx, rdi; Src
0x1400d4ed3  mov     rcx, rsi; void *
0x1400d4ed6  call    RtlCopyVolatileMemory
0x1400d4edb  mov     rbx, [rsp+28h+arg_0]
0x1400d4ee0  mov     rsi, [rsp+28h+arg_8]
0x1400d4ee5  add     rsp, 20h
0x1400d4ee9  pop     rdi
0x1400d4eea  retn
```
