# IsCreateWindowExWPresent

- ea: `0x1800117b8`
- end: `0x180011806`
- name: `IsCreateWindowExWPresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001dec0`

## callees

- `0x1800117b8`
- `0x1800119c1`

## pseudocode

```c
char IsCreateWindowExWPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18002C518 == 1 )
    return 1;
  if ( dword_18002C518 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_18002C518 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800117b8  sub     rsp, 28h
0x1800117bc  mov     ecx, cs:dword_18002C518
0x1800117c2  sub     ecx, 1
0x1800117c5  jz      short loc_1800117FF
0x1800117c7  cmp     ecx, 1
0x1800117ca  jz      short loc_1800117FB
0x1800117cc  lea     rdx, [rsp+28h+arg_0]
0x1800117d1  mov     [rsp+28h+arg_0], 0
0x1800117d6  lea     rcx, asc_1800220C0; ">@"
0x1800117dd  call    ApiSetQueryApiSetPresence_0
0x1800117e2  test    eax, eax
0x1800117e4  js      short loc_1800117FB
0x1800117e6  mov     al, [rsp+28h+arg_0]
0x1800117ea  mov     cl, al
0x1800117ec  neg     cl
0x1800117ee  sbb     edx, edx
0x1800117f0  add     edx, 2
0x1800117f3  mov     cs:dword_18002C518, edx
0x1800117f9  jmp     short loc_180011801
0x1800117fb  xor     al, al
0x1800117fd  jmp     short loc_180011801
0x1800117ff  mov     al, 1
0x180011801  add     rsp, 28h
0x180011805  retn
```
