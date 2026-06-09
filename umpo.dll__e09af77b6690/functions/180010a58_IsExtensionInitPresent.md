# IsExtensionInitPresent

- ea: `0x180010a58`
- end: `0x180010aa6`
- name: `IsExtensionInitPresent`
- size: `78`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ed10`

## callees

- `0x180010a58`
- `0x180010aac`

## pseudocode

```c
char IsExtensionInitPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800244E8 == 1 )
    return 1;
  if ( dword_1800244E8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"<>", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800244E8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180010a58  sub     rsp, 28h
0x180010a5c  mov     ecx, cs:dword_1800244E8
0x180010a62  sub     ecx, 1
0x180010a65  jz      short loc_180010A9F
0x180010a67  cmp     ecx, 1
0x180010a6a  jz      short loc_180010A9B
0x180010a6c  lea     rdx, [rsp+28h+arg_0]
0x180010a71  mov     [rsp+28h+arg_0], 0
0x180010a76  lea     rcx, asc_18001A000; "<>"
0x180010a7d  call    ApiSetQueryApiSetPresence_0
0x180010a82  test    eax, eax
0x180010a84  js      short loc_180010A9B
0x180010a86  mov     al, [rsp+28h+arg_0]
0x180010a8a  mov     cl, al
0x180010a8c  neg     cl
0x180010a8e  sbb     edx, edx
0x180010a90  add     edx, 2
0x180010a93  mov     cs:dword_1800244E8, edx
0x180010a99  jmp     short loc_180010AA1
0x180010a9b  xor     al, al
0x180010a9d  jmp     short loc_180010AA1
0x180010a9f  mov     al, 1
0x180010aa1  add     rsp, 28h
0x180010aa5  retn
```
