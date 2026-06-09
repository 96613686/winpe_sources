# IsUserServerDllInitializationMinPresent

- ea: `0x18000148c`
- end: `0x1800014da`
- name: `IsUserServerDllInitializationMinPresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001060`

## callees

- `0x18000148c`
- `0x18000156b`

## pseudocode

```c
char IsUserServerDllInitializationMinPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800055A0 == 1 )
    return 1;
  if ( dword_1800055A0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"BD", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800055A0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000148c  sub     rsp, 28h
0x180001490  mov     ecx, cs:dword_1800055A0
0x180001496  sub     ecx, 1
0x180001499  jz      short loc_1800014D3
0x18000149b  cmp     ecx, 1
0x18000149e  jz      short loc_1800014CF
0x1800014a0  lea     rdx, [rsp+28h+arg_0]
0x1800014a5  mov     [rsp+28h+arg_0], 0
0x1800014aa  lea     rcx, aBd; "BD"
0x1800014b1  call    ApiSetQueryApiSetPresence_0
0x1800014b6  test    eax, eax
0x1800014b8  js      short loc_1800014CF
0x1800014ba  mov     al, [rsp+28h+arg_0]
0x1800014be  mov     cl, al
0x1800014c0  neg     cl
0x1800014c2  sbb     edx, edx
0x1800014c4  add     edx, 2
0x1800014c7  mov     cs:dword_1800055A0, edx
0x1800014cd  jmp     short loc_1800014D5
0x1800014cf  xor     al, al
0x1800014d1  jmp     short loc_1800014D5
0x1800014d3  mov     al, 1
0x1800014d5  add     rsp, 28h
0x1800014d9  retn
```
