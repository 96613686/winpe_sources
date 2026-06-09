# IsGetWindowThreadProcessIdPresent

- ea: `0x180002034`
- end: `0x180002082`
- name: `IsGetWindowThreadProcessIdPresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180012ef8`

## callees

- `0x180001f7d`
- `0x180002034`

## pseudocode

```c
char IsGetWindowThreadProcessIdPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001D820 == 1 )
    return 1;
  if ( dword_18001D820 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001D820 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180002034  sub     rsp, 28h
0x180002038  mov     ecx, cs:dword_18001D820
0x18000203e  sub     ecx, 1
0x180002041  jz      short loc_18000207B
0x180002043  cmp     ecx, 1
0x180002046  jz      short loc_180002077
0x180002048  lea     rdx, [rsp+28h+arg_0]
0x18000204d  mov     [rsp+28h+arg_0], 0
0x180002052  lea     rcx, asc_180015150; ">@"
0x180002059  call    ApiSetQueryApiSetPresence_0
0x18000205e  test    eax, eax
0x180002060  js      short loc_180002077
0x180002062  mov     al, [rsp+28h+arg_0]
0x180002066  mov     cl, al
0x180002068  neg     cl
0x18000206a  sbb     edx, edx
0x18000206c  add     edx, 2
0x18000206f  mov     cs:dword_18001D820, edx
0x180002075  jmp     short loc_18000207D
0x180002077  xor     al, al
0x180002079  jmp     short loc_18000207D
0x18000207b  mov     al, 1
0x18000207d  add     rsp, 28h
0x180002081  retn
```
