# IsGetServicingModeStatePresent

- ea: `0x180004368`
- end: `0x1800043b6`
- name: `IsGetServicingModeStatePresent`
- size: `78`
- prototype: `char()`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000dcb0`
- `0x18000f340`
- `0x18000f8a0`

## callees

- `0x180004368`
- `0x180004465`

## pseudocode

```c
char IsGetServicingModeStatePresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800283F0 == 1 )
    return 1;
  if ( dword_1800283F0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"HJ", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800283F0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180004368  sub     rsp, 28h
0x18000436c  mov     ecx, cs:dword_1800283F0
0x180004372  sub     ecx, 1
0x180004375  jz      short loc_1800043AF
0x180004377  cmp     ecx, 1
0x18000437a  jz      short loc_1800043AB
0x18000437c  lea     rdx, [rsp+28h+arg_0]
0x180004381  mov     [rsp+28h+arg_0], 0
0x180004386  lea     rcx, aHj; "HJ"
0x18000438d  call    ApiSetQueryApiSetPresence_0
0x180004392  test    eax, eax
0x180004394  js      short loc_1800043AB
0x180004396  mov     al, [rsp+28h+arg_0]
0x18000439a  mov     cl, al
0x18000439c  neg     cl
0x18000439e  sbb     edx, edx
0x1800043a0  add     edx, 2
0x1800043a3  mov     cs:dword_1800283F0, edx
0x1800043a9  jmp     short loc_1800043B1
0x1800043ab  xor     al, al
0x1800043ad  jmp     short loc_1800043B1
0x1800043af  mov     al, 1
0x1800043b1  add     rsp, 28h
0x1800043b5  retn
```
