# TdipMultiSzStrStr

- ea: `0x140002590`
- end: `0x14000261f`
- name: `TdipMultiSzStrStr`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001df0`
- `0x1400032e0`

## callees

- `0x140002590`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x1400025d9`
- `ntoskrnl!_wcsnicmp` at `0x1400025d9`

## pseudocode

```c
bool __fastcall TdipMultiSzStrStr(_QWORD *a1, const wchar_t **a2)
{
  int v4; // edi
  size_t v5; // r8
  const wchar_t *v6; // rdx
  __int64 v7; // rax

  if ( !a1 )
    return 0;
  v4 = 0;
  if ( *a1 )
  {
    do
    {
      v5 = (unsigned __int64)*(unsigned __int16 *)a2 >> 1;
      v6 = (const wchar_t *)a1[v4];
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      if ( v5 == v7 && !_wcsnicmp(a2[1], v6, v5) )
        break;
      ++v4;
    }
    while ( a1[v4] );
  }
  return a1[v4] != 0;
}

```

## disassembly

```asm
0x140002590  mov     [rsp+arg_8], rbx
0x140002595  push    rsi
0x140002596  sub     rsp, 20h
0x14000259a  mov     rsi, rdx
0x14000259d  mov     rbx, rcx
0x1400025a0  test    rcx, rcx
0x1400025a3  jz      short loc_140002611
0x1400025a5  mov     [rsp+28h+arg_0], rdi
0x1400025aa  xor     edi, edi
0x1400025ac  cmp     [rcx], rdi
0x1400025af  jz      short loc_1400025F5
0x1400025b1  movzx   r8d, word ptr [rsi]
0x1400025b5  movsxd  rax, edi
0x1400025b8  shr     r8, 1; MaxCount
0x1400025bb  mov     rdx, [rbx+rax*8]; Str2
0x1400025bf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400025c6  inc     rax
0x1400025c9  cmp     word ptr [rdx+rax*2], 0
0x1400025ce  jnz     short loc_1400025C6
0x1400025d0  cmp     r8, rax
0x1400025d3  jnz     short loc_1400025E9
0x1400025d5  mov     rcx, [rsi+8]; Str1
0x1400025d9  call    cs:__imp__wcsnicmp
0x1400025e0  nop     dword ptr [rax+rax+00h]
0x1400025e5  test    eax, eax
0x1400025e7  jz      short loc_1400025F5
0x1400025e9  inc     edi
0x1400025eb  movsxd  rax, edi
0x1400025ee  cmp     qword ptr [rbx+rax*8], 0
0x1400025f3  jnz     short loc_1400025B1
0x1400025f5  movsxd  rax, edi
0x1400025f8  mov     rdi, [rsp+28h+arg_0]
0x1400025fd  cmp     qword ptr [rbx+rax*8], 0
0x140002602  setnz   al
0x140002605  mov     rbx, [rsp+28h+arg_8]
0x14000260a  add     rsp, 20h
0x14000260e  pop     rsi
0x14000260f  retn
0x140002611  mov     rbx, [rsp+28h+arg_8]
0x140002616  xor     al, al
0x140002618  add     rsp, 20h
0x14000261c  pop     rsi
0x14000261d  retn
```
