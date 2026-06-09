# DataStream::Read(void *,ulong,ulong *)

- ea: `0x100412c70`
- end: `0x100412cb6`
- name: `?Read@DataStream@@UEAAJPEAXKPEAK@Z`
- size: `70`
- prototype: `__int64 __fastcall(DataStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100412c70`
- `0x100412db0`
- `0x100414090`

## pseudocode

```c
__int64 __fastcall DataStream::Read(DataStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v5; // ebx

  v5 = a3;
  if ( a3 > *((_DWORD *)this + 6) )
    v5 = *((_DWORD *)this + 6);
  DataStream::InternalRead(this, a2, v5);
  if ( a4 )
    *a4 = v5;
  return 0;
}

```

## disassembly

```asm
0x100412c70  mov     [rsp+arg_0], rbx
0x100412c75  mov     [rsp+arg_8], rsi
0x100412c7a  push    rdi
0x100412c7b  sub     rsp, 40h
0x100412c7f  mov     rsi, r9
0x100412c82  mov     ebx, r8d
0x100412c85  xor     edi, edi
0x100412c87  cmp     r8d, [rcx+18h]
0x100412c8b  cmova   ebx, [rcx+18h]
0x100412c8f  mov     r8d, ebx; unsigned int
0x100412c92  call    ?InternalRead@DataStream@@AEAAXPEAXK@Z; DataStream::InternalRead(void *,ulong)
0x100412c97  test    rsi, rsi
0x100412c9a  jz      short loc_100412C9E
0x100412c9c  mov     [rsi], ebx
0x100412c9e  jmp     short loc_100412CA4
0x100412ca0  mov     edi, [rsp+48h+var_28]
0x100412ca4  mov     eax, edi
0x100412ca6  mov     rbx, [rsp+48h+arg_0]
0x100412cab  mov     rsi, [rsp+48h+arg_8]
0x100412cb0  add     rsp, 40h
0x100412cb4  pop     rdi
0x100412cb5  retn
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```
