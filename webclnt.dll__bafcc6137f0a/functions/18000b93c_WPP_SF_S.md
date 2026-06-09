# WPP_SF_S

- ea: `0x18000b93c`
- end: `0x18000b996`
- name: `WPP_SF_S`
- size: `90`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *)`
- caller_count: `64`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000235c`
- `0x180002bac`
- `0x180002ca0`
- `0x180003458`
- `0x180004288`
- `0x180004344`
- `0x1800044a8`
- `0x1800049bc`
- `0x180005970`
- `0x180005a38`
- `0x180005d38`
- `0x180006670`
- `0x180006a90`
- `0x180006d20`
- `0x180007b50`
- `0x180007e10`
- `0x180008c50`
- `0x1800091e0`
- `0x180009480`
- `0x180009740`
- `0x18000a010`
- `0x18000a370`
- `0x18000a6e0`
- `0x18000a770`
- `0x18000b060`
- `0x18000d9e4`
- `0x18000fce0`
- `0x180010028`
- `0x180010478`
- `0x180011c8c`
- `0x180012468`
- `0x180012e2c`
- `0x180013054`
- `0x18001507c`
- `0x180016d24`
- `0x180017624`
- `0x18001832c`
- `0x180019454`
- `0x1800196d0`
- `0x18001ad0c`
- `0x18001ca70`
- `0x18001db70`
- `0x18001dfc0`
- `0x18001ead0`
- `0x18001f190`
- `0x180021008`
- `0x180021628`
- `0x180021f00`
- `0x180022870`
- `0x1800229b0`

## callees

- `0x18000b93c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b98b`
- `ntdll!EtwTraceMessage` at `0x18000b98b`

## pseudocode

```c
__int64 __fastcall WPP_SF_S(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x18000b93c  sub     rsp, 48h
0x18000b940  xor     r11d, r11d
0x18000b943  test    r9, r9
0x18000b946  jz      short loc_18000B960
0x18000b948  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b94c  inc     rax
0x18000b94f  cmp     [r9+rax*2], r11w
0x18000b954  jnz     short loc_18000B94C
0x18000b956  lea     rax, ds:2[rax*2]
0x18000b95e  jmp     short loc_18000B965
0x18000b960  mov     eax, 0Ah
0x18000b965  test    r9, r9
0x18000b968  mov     [rsp+48h+var_18], r11
0x18000b96d  lea     r10, aNull_0; "NULL"
0x18000b974  mov     [rsp+48h+var_20], rax
0x18000b979  cmovz   r9, r10
0x18000b97d  mov     [rsp+48h+var_28], r9
0x18000b982  movzx   r9d, dx
0x18000b986  mov     edx, 2Bh ; '+'
0x18000b98b  call    cs:__imp_EtwTraceMessage
0x18000b991  add     rsp, 48h
0x18000b995  retn
```
