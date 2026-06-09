# IsXerGetMachineStorePathPresent

- ea: `0x140003194`
- end: `0x1400031e2`
- name: `IsXerGetMachineStorePathPresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e49c`

## callees

- `0x140003194`
- `0x140003728`

## pseudocode

```c
char IsXerGetMachineStorePathPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_14002C5A8 == 1 )
    return 1;
  if ( dword_14002C5A8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"46", &v1) < 0 )
    return 0;
  result = v1;
  dword_14002C5A8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x140003194  sub     rsp, 28h
0x140003198  mov     ecx, cs:dword_14002C5A8
0x14000319e  sub     ecx, 1
0x1400031a1  jz      short loc_1400031DB
0x1400031a3  cmp     ecx, 1
0x1400031a6  jz      short loc_1400031D7
0x1400031a8  lea     rdx, [rsp+28h+arg_0]
0x1400031ad  mov     [rsp+28h+arg_0], 0
0x1400031b2  lea     rcx, a46; "46"
0x1400031b9  call    ApiSetQueryApiSetPresence_0
0x1400031be  test    eax, eax
0x1400031c0  js      short loc_1400031D7
0x1400031c2  mov     al, [rsp+28h+arg_0]
0x1400031c6  mov     cl, al
0x1400031c8  neg     cl
0x1400031ca  sbb     edx, edx
0x1400031cc  add     edx, 2
0x1400031cf  mov     cs:dword_14002C5A8, edx
0x1400031d5  jmp     short loc_1400031DD
0x1400031d7  xor     al, al
0x1400031d9  jmp     short loc_1400031DD
0x1400031db  mov     al, 1
0x1400031dd  add     rsp, 28h
0x1400031e1  retn
```
