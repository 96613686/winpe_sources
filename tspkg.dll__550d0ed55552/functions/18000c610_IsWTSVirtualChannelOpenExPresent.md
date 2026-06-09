# IsWTSVirtualChannelOpenExPresent

- ea: `0x18000c610`
- end: `0x18000c65e`
- name: `IsWTSVirtualChannelOpenExPresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b000`

## callees

- `0x18000c610`
- `0x18000c8cb`

## pseudocode

```c
char IsWTSVirtualChannelOpenExPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180025498 == 1 )
    return 1;
  if ( dword_180025498 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"DF", &v1) < 0 )
    return 0;
  result = v1;
  dword_180025498 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000c610  sub     rsp, 28h
0x18000c614  mov     ecx, cs:dword_180025498
0x18000c61a  sub     ecx, 1
0x18000c61d  jz      short loc_18000C657
0x18000c61f  cmp     ecx, 1
0x18000c622  jz      short loc_18000C653
0x18000c624  lea     rdx, [rsp+28h+arg_0]
0x18000c629  mov     [rsp+28h+arg_0], 0
0x18000c62e  lea     rcx, aDf; "DF"
0x18000c635  call    ApiSetQueryApiSetPresence_0
0x18000c63a  test    eax, eax
0x18000c63c  js      short loc_18000C653
0x18000c63e  mov     al, [rsp+28h+arg_0]
0x18000c642  mov     cl, al
0x18000c644  neg     cl
0x18000c646  sbb     edx, edx
0x18000c648  add     edx, 2
0x18000c64b  mov     cs:dword_180025498, edx
0x18000c651  jmp     short loc_18000C659
0x18000c653  xor     al, al
0x18000c655  jmp     short loc_18000C659
0x18000c657  mov     al, 1
0x18000c659  add     rsp, 28h
0x18000c65d  retn
```
