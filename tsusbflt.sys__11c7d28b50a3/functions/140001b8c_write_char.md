# write_char

- ea: `0x140001b8c`
- end: `0x140001bdb`
- name: `write_char`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001150`

## callees

- `0x140001b8c`
- `0x140001c1c`

## pseudocode

```c
__int16 __fastcall write_char(wchar_t a1, FILE *a2, _DWORD *a3)
{
  int flag; // eax

  flag = a2->_flag;
  if ( (flag & 0x40) == 0 || a2->_base )
  {
    LOWORD(flag) = fputwc_nolock(a1, a2);
    if ( (_WORD)flag == 0xFFFF && (flag = a2->_flag, (flag & 0x20) != 0) )
      *a3 = -1;
    else
      ++*a3;
  }
  else
  {
    ++*a3;
  }
  return flag;
}

```

## disassembly

```asm
0x140001b8c  mov     [rsp+arg_0], rbx
0x140001b91  push    rdi
0x140001b92  sub     rsp, 20h
0x140001b96  mov     eax, [rdx+18h]
0x140001b99  mov     rbx, r8
0x140001b9c  mov     rdi, rdx
0x140001b9f  test    al, 40h
0x140001ba1  jz      short loc_140001BAF
0x140001ba3  cmp     qword ptr [rdx+10h], 0
0x140001ba8  jnz     short loc_140001BAF
0x140001baa  inc     dword ptr [r8]
0x140001bad  jmp     short loc_140001BCF
0x140001baf  call    _fputwc_nolock
0x140001bb4  mov     ecx, 0FFFFh
0x140001bb9  cmp     ax, cx
0x140001bbc  jnz     short loc_140001BCD
0x140001bbe  mov     eax, [rdi+18h]
0x140001bc1  test    al, 20h
0x140001bc3  jz      short loc_140001BCD
0x140001bc5  mov     dword ptr [rbx], 0FFFFFFFFh
0x140001bcb  jmp     short loc_140001BCF
0x140001bcd  inc     dword ptr [rbx]
0x140001bcf  mov     rbx, [rsp+28h+arg_0]
0x140001bd4  add     rsp, 20h
0x140001bd8  pop     rdi
0x140001bd9  retn
```
