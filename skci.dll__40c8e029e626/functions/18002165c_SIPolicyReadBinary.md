# SIPolicyReadBinary

- ea: `0x18002165c`
- end: `0x180021709`
- name: `SIPolicyReadBinary`
- size: `173`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e674`
- `0x18001f33c`
- `0x18001f624`

## callees

- `0x18002165c`
- `0x180021710`
- `0x180021748`

## pseudocode

```c
__int64 __fastcall SIPolicyReadBinary(__int64 *a1, _QWORD *a2, unsigned int *a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  unsigned int v8; // r11d
  unsigned int v9; // ecx
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+20h] BYREF

  v10[0] = 0;
  v11 = 0;
  result = SIPolicyReadPrimitive(a1, 4u, &v11);
  if ( (int)result >= 0 )
  {
    v7 = v11 + (-v11 & 3);
    if ( v7 < v11 )
    {
      return 3221225621LL;
    }
    else if ( v7 )
    {
      result = SIPolicyReadBytes(a1, v7, v10);
      if ( (int)result >= 0 )
      {
        v9 = v8;
        if ( v8 >= v7 )
        {
LABEL_9:
          *a2 = v10[0];
          result = (unsigned int)result;
          *a3 = v8;
        }
        else
        {
          while ( !*(_BYTE *)(v9 + v10[0]) )
          {
            if ( ++v9 >= v7 )
              goto LABEL_9;
          }
          return 3236495363LL;
        }
      }
    }
    else
    {
      *a2 = 0;
      result = 0;
      *a3 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002165c  push    rbx
0x18002165e  push    rbp
0x18002165f  push    rsi
0x180021660  push    rdi
0x180021661  sub     rsp, 38h
0x180021665  mov     rdi, r8
0x180021668  mov     [rsp+58h+var_38], 0
0x180021671  mov     rsi, rdx
0x180021674  mov     [rsp+58h+arg_18], 0
0x18002167c  lea     r8, [rsp+58h+arg_18]
0x180021681  mov     edx, 4
0x180021686  mov     rbp, rcx
0x180021689  call    SIPolicyReadPrimitive
0x18002168e  test    eax, eax
0x180021690  js      short loc_1800216FF
0x180021692  mov     r11d, [rsp+58h+arg_18]
0x180021697  mov     ebx, r11d
0x18002169a  neg     ebx
0x18002169c  and     ebx, 3
0x18002169f  add     ebx, r11d
0x1800216a2  cmp     ebx, r11d
0x1800216a5  jb      short loc_1800216FA
0x1800216a7  test    ebx, ebx
0x1800216a9  jnz     short loc_1800216B8
0x1800216ab  mov     qword ptr [rsi], 0
0x1800216b2  xor     eax, eax
0x1800216b4  mov     [rdi], ebx
0x1800216b6  jmp     short loc_1800216FF
0x1800216b8  mov     edx, ebx
0x1800216ba  lea     r8, [rsp+58h+var_38]
0x1800216bf  mov     rcx, rbp
0x1800216c2  call    SIPolicyReadBytes
0x1800216c7  mov     edx, eax
0x1800216c9  test    eax, eax
0x1800216cb  js      short loc_1800216FF
0x1800216cd  mov     r8, [rsp+58h+var_38]
0x1800216d2  mov     ecx, r11d
0x1800216d5  cmp     r11d, ebx
0x1800216d8  jnb     short loc_1800216E9
0x1800216da  mov     eax, ecx
0x1800216dc  cmp     byte ptr [rax+r8], 0
0x1800216e1  jnz     short loc_1800216F3
0x1800216e3  inc     ecx
0x1800216e5  cmp     ecx, ebx
0x1800216e7  jb      short loc_1800216DA
0x1800216e9  mov     [rsi], r8
0x1800216ec  mov     eax, edx
0x1800216ee  mov     [rdi], r11d
0x1800216f1  jmp     short loc_1800216FF
0x1800216f3  mov     eax, 0C0E90003h
0x1800216f8  jmp     short loc_1800216FF
0x1800216fa  mov     eax, 0C0000095h
0x1800216ff  add     rsp, 38h
0x180021703  pop     rdi
0x180021704  pop     rsi
0x180021705  pop     rbp
0x180021706  pop     rbx
0x180021707  retn
```
