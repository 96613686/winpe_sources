# CDhcpOptions::AddOptionRelayAgentFromBufferEnd(void)

- ea: `0x180029f70`
- end: `0x18002a069`
- name: `?AddOptionRelayAgentFromBufferEnd@CDhcpOptions@@QEAAKXZ`
- size: `249`
- prototype: `unsigned int __fastcall(CDhcpOptions *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180029db0`

## callees

- `0x180029f70`
- `0x18002f3ba`
- `0x180030010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002a011`
- `msvcrt!memmove_s` at `0x18002a011`

## pseudocode

```c
__int64 __fastcall CDhcpOptions::AddOptionRelayAgentFromBufferEnd(CDhcpOptions *this)
{
  unsigned int v1; // ebx
  __int64 v3; // rax
  __int64 v4; // r9
  rsize_t v5; // r8
  __int64 v6; // r10
  int v7; // ebp
  _BYTE *v8; // rcx
  void *v9; // rsi
  __int64 v10; // r9

  v1 = 0;
  if ( *((_DWORD *)this + 72) )
  {
    v3 = *((unsigned int *)this + 70);
    v4 = *((_QWORD *)this + 34);
    v5 = *(unsigned __int8 *)(v3 + v4 - 1);
    if ( (_BYTE)v5 )
    {
      v6 = *((unsigned int *)this + 71);
      v7 = v5 + 2;
      if ( (unsigned int)(v3 - v6) >= (unsigned __int64)(unsigned int)(v5 + 2) + 1 )
      {
        v8 = (_BYTE *)(v4 + v6);
        v8[1] = v5;
        *v8 = 82;
        v9 = (void *)(v3 + v4 - v5 - 1);
        memmove_s((void *const)(v4 + v6 + 2), v5, v9, v5);
        *((_DWORD *)this + 71) += v7;
        v10 = *((_QWORD *)this + 34);
        if ( v10 + (unsigned __int64)*((unsigned int *)this + 71) > (unsigned __int64)v9 )
          v9 = (void *)(v10 + *((unsigned int *)this + 71));
        memset_0(v9, 0, v10 + *((unsigned int *)this + 70) - (_QWORD)v9);
      }
      else if ( g_ErrLibTraceFunctionEx )
      {
        g_ErrLibTraceFunctionEx(0x80000u, L"Not enough space, option 82 information will be discarded");
      }
    }
  }
  else
  {
    return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x180029f70  mov     [rsp+arg_0], rbx
0x180029f75  mov     [rsp+arg_8], rbp
0x180029f7a  mov     [rsp+arg_10], rsi
0x180029f7f  push    rdi
0x180029f80  sub     rsp, 20h
0x180029f84  xor     ebx, ebx
0x180029f86  mov     rdi, rcx
0x180029f89  cmp     [rcx+120h], ebx
0x180029f8f  jnz     short loc_180029F9B
0x180029f91  mov     ebx, 1
0x180029f96  jmp     loc_18002A051
0x180029f9b  mov     eax, [rcx+118h]
0x180029fa1  mov     r9, [rcx+110h]
0x180029fa8  lea     rsi, [rax+r9]
0x180029fac  movzx   r8d, byte ptr [rsi-1]
0x180029fb1  test    r8b, r8b
0x180029fb4  jz      loc_18002A051
0x180029fba  mov     r10d, [rcx+11Ch]
0x180029fc1  lea     ebp, [r8+2]
0x180029fc5  sub     eax, r10d
0x180029fc8  mov     ecx, eax
0x180029fca  mov     eax, ebp
0x180029fcc  inc     rax
0x180029fcf  cmp     rcx, rax
0x180029fd2  jnb     short loc_180029FF3
0x180029fd4  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029fdb  test    rax, rax
0x180029fde  jz      short loc_18002A051
0x180029fe0  lea     rdx, aNotEnoughSpace; "Not enough space, option 82 information"...
0x180029fe7  mov     ecx, 80000h
0x180029fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ff1  jmp     short loc_18002A051
0x180029ff3  lea     rcx, [r9+r10]
0x180029ff7  sub     rsi, r8
0x180029ffa  mov     [rcx+1], r8b
0x180029ffe  mov     rdx, r8; DestinationSize
0x18002a001  mov     byte ptr [rcx], 52h ; 'R'
0x18002a004  mov     r9, r8; SourceSize
0x18002a007  dec     rsi
0x18002a00a  add     rcx, 2; Destination
0x18002a00e  mov     r8, rsi; Source
0x18002a011  call    cs:__imp_memmove_s
0x18002a018  nop     dword ptr [rax+rax+00h]
0x18002a01d  add     [rdi+11Ch], ebp
0x18002a023  mov     r9, [rdi+110h]
0x18002a02a  mov     edx, [rdi+11Ch]
0x18002a030  mov     r8d, [rdi+118h]
0x18002a037  add     rdx, r9
0x18002a03a  cmp     rdx, rsi
0x18002a03d  cmova   rsi, rdx
0x18002a041  xor     edx, edx; Val
0x18002a043  sub     r8, rsi
0x18002a046  mov     rcx, rsi; void *
0x18002a049  add     r8, r9; Size
0x18002a04c  call    memset_0
0x18002a051  mov     rbp, [rsp+28h+arg_8]
0x18002a056  mov     eax, ebx
0x18002a058  mov     rbx, [rsp+28h+arg_0]
0x18002a05d  mov     rsi, [rsp+28h+arg_10]
0x18002a062  add     rsp, 20h
0x18002a066  pop     rdi
0x18002a067  retn
```
