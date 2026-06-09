# IsDeleteLinkFileWorkerPresent

- ea: `0x18000f670`
- end: `0x18000f6be`
- name: `IsDeleteLinkFileWorkerPresent`
- size: `78`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180008980`
- `0x180008bf0`
- `0x180008c40`
- `0x180008cb0`
- `0x1800090f0`
- `0x180009280`
- `0x180009420`
- `0x1800096d0`
- `0x18000a100`
- `0x18000a160`
- `0x180012a40`
- `0x180012a70`
- `0x180012ab0`
- `0x180012b00`
- `0x180012bf0`
- `0x180012c30`
- `0x180012c80`
- `0x180012d40`
- `0x180012da0`
- `0x180012e50`

## callees

- `0x18000f670`
- `0x18000fae2`

## pseudocode

```c
char IsDeleteLinkFileWorkerPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800294B8 == 1 )
    return 1;
  if ( dword_1800294B8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"BD", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800294B8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000f670  sub     rsp, 28h
0x18000f674  mov     ecx, cs:dword_1800294B8
0x18000f67a  sub     ecx, 1
0x18000f67d  jz      short loc_18000F6B7
0x18000f67f  cmp     ecx, 1
0x18000f682  jz      short loc_18000F6B3
0x18000f684  lea     rdx, [rsp+28h+arg_0]
0x18000f689  mov     [rsp+28h+arg_0], 0
0x18000f68e  lea     rcx, aBd_0; "BD"
0x18000f695  call    ApiSetQueryApiSetPresence_0
0x18000f69a  test    eax, eax
0x18000f69c  js      short loc_18000F6B3
0x18000f69e  mov     al, [rsp+28h+arg_0]
0x18000f6a2  mov     cl, al
0x18000f6a4  neg     cl
0x18000f6a6  sbb     edx, edx
0x18000f6a8  add     edx, 2
0x18000f6ab  mov     cs:dword_1800294B8, edx
0x18000f6b1  jmp     short loc_18000F6B9
0x18000f6b3  xor     al, al
0x18000f6b5  jmp     short loc_18000F6B9
0x18000f6b7  mov     al, 1
0x18000f6b9  add     rsp, 28h
0x18000f6bd  retn
```
