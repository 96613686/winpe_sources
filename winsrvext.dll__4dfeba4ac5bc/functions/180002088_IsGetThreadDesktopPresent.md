# IsGetThreadDesktopPresent

- ea: `0x180002088`
- end: `0x1800020d6`
- name: `IsGetThreadDesktopPresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012ef8`

## callees

- `0x180001f7d`
- `0x180002088`

## pseudocode

```c
char IsGetThreadDesktopPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001D83C == 1 )
    return 1;
  if ( dword_18001D83C == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"LN", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001D83C = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180002088  sub     rsp, 28h
0x18000208c  mov     ecx, cs:dword_18001D83C
0x180002092  sub     ecx, 1
0x180002095  jz      short loc_1800020CF
0x180002097  cmp     ecx, 1
0x18000209a  jz      short loc_1800020CB
0x18000209c  lea     rdx, [rsp+28h+arg_0]
0x1800020a1  mov     [rsp+28h+arg_0], 0
0x1800020a6  lea     rcx, aLn; "LN"
0x1800020ad  call    ApiSetQueryApiSetPresence_0
0x1800020b2  test    eax, eax
0x1800020b4  js      short loc_1800020CB
0x1800020b6  mov     al, [rsp+28h+arg_0]
0x1800020ba  mov     cl, al
0x1800020bc  neg     cl
0x1800020be  sbb     edx, edx
0x1800020c0  add     edx, 2
0x1800020c3  mov     cs:dword_18001D83C, edx
0x1800020c9  jmp     short loc_1800020D1
0x1800020cb  xor     al, al
0x1800020cd  jmp     short loc_1800020D1
0x1800020cf  mov     al, 1
0x1800020d1  add     rsp, 28h
0x1800020d5  retn
```
