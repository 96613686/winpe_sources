# AppendUnicodeString

- ea: `0x140001338`
- end: `0x140001382`
- name: `AppendUnicodeString`
- size: `74`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001390`

## callees

- `0x1400012f0`
- `0x140001338`

## pseudocode

```c
__int64 __fastcall AppendUnicodeString(unsigned __int16 *a1, __int16 *a2)
{
  int v3; // edx

  v3 = 0;
  while ( *a2 )
  {
    v3 = AddToUnicodeString(a1, *a2);
    if ( v3 < 0 )
      break;
    ++a2;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140001338  mov     [rsp+arg_0], rbx
0x14000133d  mov     [rsp+arg_8], rsi
0x140001342  push    rdi
0x140001343  sub     rsp, 20h
0x140001347  xor     esi, esi
0x140001349  mov     rbx, rdx
0x14000134c  mov     edx, esi
0x14000134e  mov     rdi, rcx
0x140001351  jmp     short loc_140001368
0x140001353  movzx   edx, ax
0x140001356  mov     rcx, rdi
0x140001359  call    AddToUnicodeString
0x14000135e  mov     edx, eax
0x140001360  test    eax, eax
0x140001362  js      short loc_140001370
0x140001364  add     rbx, 2
0x140001368  movzx   eax, word ptr [rbx]
0x14000136b  test    ax, ax
0x14000136e  jnz     short loc_140001353
0x140001370  mov     rbx, [rsp+28h+arg_0]
0x140001375  mov     eax, edx
0x140001377  mov     rsi, [rsp+28h+arg_8]
0x14000137c  add     rsp, 20h
0x140001380  pop     rdi
0x140001381  retn
```
