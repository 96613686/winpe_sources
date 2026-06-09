# IsAddAppContainerAccessWorkerPresent

- ea: `0x18000e96c`
- end: `0x18000e9ba`
- name: `IsAddAppContainerAccessWorkerPresent`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800119c0`
- `0x180011a10`
- `0x180011a60`
- `0x180011c20`
- `0x180011d40`

## callees

- `0x18000e96c`
- `0x18000ee32`

## pseudocode

```c
char IsAddAppContainerAccessWorkerPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800283C0 == 1 )
    return 1;
  if ( dword_1800283C0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"BD", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800283C0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000e96c  sub     rsp, 28h
0x18000e970  mov     ecx, cs:dword_1800283C0
0x18000e976  sub     ecx, 1
0x18000e979  jz      short loc_18000E9B3
0x18000e97b  cmp     ecx, 1
0x18000e97e  jz      short loc_18000E9AF
0x18000e980  lea     rdx, [rsp+28h+arg_0]
0x18000e985  mov     [rsp+28h+arg_0], 0
0x18000e98a  lea     rcx, aBd; "BD"
0x18000e991  call    ApiSetQueryApiSetPresence_0
0x18000e996  test    eax, eax
0x18000e998  js      short loc_18000E9AF
0x18000e99a  mov     al, [rsp+28h+arg_0]
0x18000e99e  mov     cl, al
0x18000e9a0  neg     cl
0x18000e9a2  sbb     edx, edx
0x18000e9a4  add     edx, 2
0x18000e9a7  mov     cs:dword_1800283C0, edx
0x18000e9ad  jmp     short loc_18000E9B5
0x18000e9af  xor     al, al
0x18000e9b1  jmp     short loc_18000E9B5
0x18000e9b3  mov     al, 1
0x18000e9b5  add     rsp, 28h
0x18000e9b9  retn
```
