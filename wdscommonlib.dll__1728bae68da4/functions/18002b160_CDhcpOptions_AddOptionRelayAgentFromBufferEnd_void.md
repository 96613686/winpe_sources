# CDhcpOptions::AddOptionRelayAgentFromBufferEnd(void)

- ea: `0x18002b160`
- end: `0x18002b259`
- name: `?AddOptionRelayAgentFromBufferEnd@CDhcpOptions@@QEAAKXZ`
- size: `249`
- prototype: `__int64 __fastcall(CDhcpOptions *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002afa0`

## callees

- `0x18002b160`
- `0x180030362`
- `0x180031010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002b201`
- `msvcrt!memmove_s` at `0x18002b201`

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
0x18002b160  mov     [rsp+arg_0], rbx
0x18002b165  mov     [rsp+arg_8], rbp
0x18002b16a  mov     [rsp+arg_10], rsi
0x18002b16f  push    rdi
0x18002b170  sub     rsp, 20h
0x18002b174  xor     ebx, ebx
0x18002b176  mov     rdi, rcx
0x18002b179  cmp     [rcx+120h], ebx
0x18002b17f  jnz     short loc_18002B18B
0x18002b181  mov     ebx, 1
0x18002b186  jmp     loc_18002B241
0x18002b18b  mov     eax, [rcx+118h]
0x18002b191  mov     r9, [rcx+110h]
0x18002b198  lea     rsi, [rax+r9]
0x18002b19c  movzx   r8d, byte ptr [rsi-1]
0x18002b1a1  test    r8b, r8b
0x18002b1a4  jz      loc_18002B241
0x18002b1aa  mov     r10d, [rcx+11Ch]
0x18002b1b1  lea     ebp, [r8+2]
0x18002b1b5  sub     eax, r10d
0x18002b1b8  mov     ecx, eax
0x18002b1ba  mov     eax, ebp
0x18002b1bc  inc     rax
0x18002b1bf  cmp     rcx, rax
0x18002b1c2  jnb     short loc_18002B1E3
0x18002b1c4  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002b1cb  test    rax, rax
0x18002b1ce  jz      short loc_18002B241
0x18002b1d0  lea     rdx, aNotEnoughSpace; "Not enough space, option 82 information"...
0x18002b1d7  mov     ecx, 80000h
0x18002b1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1e1  jmp     short loc_18002B241
0x18002b1e3  lea     rcx, [r9+r10]
0x18002b1e7  sub     rsi, r8
0x18002b1ea  mov     [rcx+1], r8b
0x18002b1ee  mov     rdx, r8; DestinationSize
0x18002b1f1  mov     byte ptr [rcx], 52h ; 'R'
0x18002b1f4  mov     r9, r8; SourceSize
0x18002b1f7  dec     rsi
0x18002b1fa  add     rcx, 2; Destination
0x18002b1fe  mov     r8, rsi; Source
0x18002b201  call    cs:__imp_memmove_s
0x18002b208  nop     dword ptr [rax+rax+00h]
0x18002b20d  add     [rdi+11Ch], ebp
0x18002b213  mov     r9, [rdi+110h]
0x18002b21a  mov     edx, [rdi+11Ch]
0x18002b220  mov     r8d, [rdi+118h]
0x18002b227  add     rdx, r9
0x18002b22a  cmp     rdx, rsi
0x18002b22d  cmova   rsi, rdx
0x18002b231  xor     edx, edx; Val
0x18002b233  sub     r8, rsi
0x18002b236  mov     rcx, rsi; void *
0x18002b239  add     r8, r9; Size
0x18002b23c  call    memset_0
0x18002b241  mov     rbp, [rsp+28h+arg_8]
0x18002b246  mov     eax, ebx
0x18002b248  mov     rbx, [rsp+28h+arg_0]
0x18002b24d  mov     rsi, [rsp+28h+arg_10]
0x18002b252  add     rsp, 20h
0x18002b256  pop     rdi
0x18002b257  retn
```
