# IsDeleteLinkFileWorkerPresent

- ea: `0x18000e9c0`
- end: `0x18000ea0e`
- name: `IsDeleteLinkFileWorkerPresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x1800078d0`
- `0x180008410`
- `0x180008450`
- `0x1800084b0`
- `0x1800088a0`
- `0x180008a10`
- `0x180008ba0`
- `0x180008e30`
- `0x1800097d0`
- `0x180009830`
- `0x180011ab0`
- `0x180011ae0`
- `0x180011b20`
- `0x180011b70`
- `0x180011c60`
- `0x180011ca0`
- `0x180011cf0`
- `0x180011da0`
- `0x180011df0`
- `0x180011e90`

## callees

- `0x18000e9c0`
- `0x18000ee32`

## pseudocode

```c
char IsDeleteLinkFileWorkerPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800283B8 == 1 )
    return 1;
  if ( dword_1800283B8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"BD", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800283B8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000e9c0  sub     rsp, 28h
0x18000e9c4  mov     ecx, cs:dword_1800283B8
0x18000e9ca  sub     ecx, 1
0x18000e9cd  jz      short loc_18000EA07
0x18000e9cf  cmp     ecx, 1
0x18000e9d2  jz      short loc_18000EA03
0x18000e9d4  lea     rdx, [rsp+28h+arg_0]
0x18000e9d9  mov     [rsp+28h+arg_0], 0
0x18000e9de  lea     rcx, aBd_0; "BD"
0x18000e9e5  call    ApiSetQueryApiSetPresence_0
0x18000e9ea  test    eax, eax
0x18000e9ec  js      short loc_18000EA03
0x18000e9ee  mov     al, [rsp+28h+arg_0]
0x18000e9f2  mov     cl, al
0x18000e9f4  neg     cl
0x18000e9f6  sbb     edx, edx
0x18000e9f8  add     edx, 2
0x18000e9fb  mov     cs:dword_1800283B8, edx
0x18000ea01  jmp     short loc_18000EA09
0x18000ea03  xor     al, al
0x18000ea05  jmp     short loc_18000EA09
0x18000ea07  mov     al, 1
0x18000ea09  add     rsp, 28h
0x18000ea0d  retn
```
