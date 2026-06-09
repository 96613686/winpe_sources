# IsGetThreadDesktopPresent

- ea: `0x140003734`
- end: `0x140003782`
- name: `IsGetThreadDesktopPresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001bb34`

## callees

- `0x140003728`
- `0x140003734`

## pseudocode

```c
char IsGetThreadDesktopPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_14002C5C0 == 1 )
    return 1;
  if ( dword_14002C5C0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"LN", &v1) < 0 )
    return 0;
  result = v1;
  dword_14002C5C0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x140003734  sub     rsp, 28h
0x140003738  mov     ecx, cs:dword_14002C5C0
0x14000373e  sub     ecx, 1
0x140003741  jz      short loc_14000377B
0x140003743  cmp     ecx, 1
0x140003746  jz      short loc_140003777
0x140003748  lea     rdx, [rsp+28h+arg_0]
0x14000374d  mov     [rsp+28h+arg_0], 0
0x140003752  lea     rcx, aLn; "LN"
0x140003759  call    ApiSetQueryApiSetPresence_0
0x14000375e  test    eax, eax
0x140003760  js      short loc_140003777
0x140003762  mov     al, [rsp+28h+arg_0]
0x140003766  mov     cl, al
0x140003768  neg     cl
0x14000376a  sbb     edx, edx
0x14000376c  add     edx, 2
0x14000376f  mov     cs:dword_14002C5C0, edx
0x140003775  jmp     short loc_14000377D
0x140003777  xor     al, al
0x140003779  jmp     short loc_14000377D
0x14000377b  mov     al, 1
0x14000377d  add     rsp, 28h
0x140003781  retn
```
