# pSetupGetFileTitle

- ea: `0x18001812c`
- end: `0x180018176`
- name: `pSetupGetFileTitle`
- size: `74`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800101e8`
- `0x180016818`
- `0x180016f7c`
- `0x180017058`
- `0x180017500`

## callees

- `0x18001812c`

## pseudocode

```c
unsigned __int16 *__fastcall pSetupGetFileTitle(unsigned __int16 *a1)
{
  unsigned __int16 v1; // dx
  unsigned __int16 *result; // rax

  v1 = *a1;
  if ( (unsigned __int16)(*a1 - 65) <= 0x19u )
    goto LABEL_11;
  if ( v1 < 0x61u )
  {
LABEL_13:
    result = a1;
    goto LABEL_9;
  }
  if ( v1 <= 0x7Au )
  {
LABEL_11:
    if ( a1[1] == 58 )
    {
      a1 += 2;
      v1 = *a1;
    }
    goto LABEL_13;
  }
  result = a1;
  do
  {
    ++a1;
    if ( v1 == 92 || v1 == 47 )
      result = a1;
    v1 = *a1;
LABEL_9:
    ;
  }
  while ( v1 );
  return result;
}

```

## disassembly

```asm
0x18001812c  movzx   edx, word ptr [rcx]
0x18001812f  lea     eax, [rdx-41h]
0x180018132  cmp     ax, 19h
0x180018136  jbe     short loc_180018163
0x180018138  cmp     dx, 61h ; 'a'
0x18001813c  jb      short loc_180018171
0x18001813e  cmp     dx, 7Ah ; 'z'
0x180018142  jbe     short loc_180018163
0x180018144  mov     rax, rcx
0x180018147  add     rcx, 2
0x18001814b  cmp     dx, 5Ch ; '\'
0x18001814f  jz      short loc_180018157
0x180018151  cmp     dx, 2Fh ; '/'
0x180018155  jnz     short loc_18001815A
0x180018157  mov     rax, rcx
0x18001815a  movzx   edx, word ptr [rcx]
0x18001815d  test    dx, dx
0x180018160  jnz     short loc_180018147
0x180018162  retn
0x180018163  cmp     word ptr [rcx+2], 3Ah ; ':'
0x180018168  jnz     short loc_180018171
0x18001816a  add     rcx, 4
0x18001816e  movzx   edx, word ptr [rcx]
0x180018171  mov     rax, rcx
0x180018174  jmp     short loc_18001815D
```
