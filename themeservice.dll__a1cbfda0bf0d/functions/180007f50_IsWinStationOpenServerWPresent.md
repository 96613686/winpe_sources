# IsWinStationOpenServerWPresent

- ea: `0x180007f50`
- end: `0x180007f9e`
- name: `IsWinStationOpenServerWPresent`
- size: `78`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce50`

## callees

- `0x180007f50`
- `0x1800080de`

## pseudocode

```c
char IsWinStationOpenServerWPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180016750 == 1 )
    return 1;
  if ( dword_180016750 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"@B", &v1) < 0 )
    return 0;
  result = v1;
  dword_180016750 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180007f50  sub     rsp, 28h
0x180007f54  mov     ecx, cs:dword_180016750
0x180007f5a  sub     ecx, 1
0x180007f5d  jz      short loc_180007F97
0x180007f5f  cmp     ecx, 1
0x180007f62  jz      short loc_180007F93
0x180007f64  lea     rdx, [rsp+28h+arg_0]
0x180007f69  mov     [rsp+28h+arg_0], 0
0x180007f6e  lea     rcx, aB; "@B"
0x180007f75  call    ApiSetQueryApiSetPresence_0
0x180007f7a  test    eax, eax
0x180007f7c  js      short loc_180007F93
0x180007f7e  mov     al, [rsp+28h+arg_0]
0x180007f82  mov     cl, al
0x180007f84  neg     cl
0x180007f86  sbb     edx, edx
0x180007f88  add     edx, 2
0x180007f8b  mov     cs:dword_180016750, edx
0x180007f91  jmp     short loc_180007F99
0x180007f93  xor     al, al
0x180007f95  jmp     short loc_180007F99
0x180007f97  mov     al, 1
0x180007f99  add     rsp, 28h
0x180007f9d  retn
```
