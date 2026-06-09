# SdbFindFirstTag

- ea: `0x140014380`
- end: `0x1400143d1`
- name: `SdbFindFirstTag`
- size: `81`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int16)`
- caller_count: `29`
- callee_count: `4`
- tags: ``

## callers

- `0x1400045e0`
- `0x140004df8`
- `0x140006480`
- `0x140008500`
- `0x140013780`
- `0x140014574`
- `0x140014b64`
- `0x140015104`
- `0x1400153a4`
- `0x140015a18`
- `0x140015cbc`
- `0x14001651c`
- `0x140017be4`
- `0x140018840`
- `0x140019410`
- `0x14001a24c`
- `0x14001a878`
- `0x14001aa54`
- `0x14001ae04`
- `0x14001b4b0`
- `0x14001b7e8`
- `0x14001bf38`
- `0x14001c290`
- `0x14001cd7c`
- `0x14001d494`
- `0x14001d808`
- `0x14001f90c`
- `0x1400242ac`
- `0x14002b138`

## callees

- `0x140014380`
- `0x140015e14`
- `0x140016070`
- `0x140016148`

## pseudocode

```c
__int64 __fastcall SdbFindFirstTag(__int64 a1, unsigned int a2, __int16 a3)
{
  unsigned int v3; // edi
  unsigned int i; // eax
  unsigned int v8; // ebx

  v3 = 0;
  for ( i = SdbGetFirstChild(); ; i = SdbGetNextChild(a1, a2, v8) )
  {
    v8 = i;
    if ( !i )
      break;
    if ( (unsigned __int16)SdbGetTagFromTagID(a1, i) == a3 )
      return v8;
  }
  return v3;
}

```

## disassembly

```asm
0x140014380  push    rbx
0x140014382  push    rbp
0x140014383  push    rsi
0x140014384  push    rdi
0x140014385  push    r14
0x140014387  sub     rsp, 20h
0x14001438b  xor     edi, edi
0x14001438d  movzx   r14d, r8w
0x140014391  mov     ebp, edx
0x140014393  mov     rsi, rcx
0x140014396  call    SdbGetFirstChild
0x14001439b  jmp     short loc_1400143BA
0x14001439d  mov     edx, ebx
0x14001439f  mov     rcx, rsi
0x1400143a2  call    SdbGetTagFromTagID
0x1400143a7  cmp     ax, r14w
0x1400143ab  jz      short loc_1400143C2
0x1400143ad  mov     r8d, ebx
0x1400143b0  mov     edx, ebp
0x1400143b2  mov     rcx, rsi
0x1400143b5  call    SdbGetNextChild
0x1400143ba  mov     ebx, eax
0x1400143bc  test    eax, eax
0x1400143be  jnz     short loc_14001439D
0x1400143c0  jmp     short loc_1400143C4
0x1400143c2  mov     edi, ebx
0x1400143c4  mov     eax, edi
0x1400143c6  add     rsp, 20h
0x1400143ca  pop     r14
0x1400143cc  pop     rdi
0x1400143cd  pop     rsi
0x1400143ce  pop     rbp
0x1400143cf  pop     rbx
0x1400143d0  retn
```
