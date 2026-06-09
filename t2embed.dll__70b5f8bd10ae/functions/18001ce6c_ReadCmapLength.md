# ReadCmapLength

- ea: `0x18001ce6c`
- end: `0x18001cf21`
- name: `ReadCmapLength`
- size: `181`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180016f54`
- `0x180017330`
- `0x18001d5f8`
- `0x18001dc84`

## callees

- `0x18000ee40`
- `0x180016e44`
- `0x18001ce6c`

## pseudocode

```c
__int64 __fastcall ReadCmapLength(__int64 a1, _WORD *a2, unsigned int a3, _WORD *a4)
{
  __int16 v5; // di
  __int64 result; // rax
  _WORD *v7; // rdx
  int v8; // r8d
  __int64 v9; // r11
  __int64 v10; // r8
  int v11; // ecx
  _WORD *v12; // rdx
  __int16 v13; // r8
  __int64 v14; // r10
  unsigned __int16 v15; // [rsp+40h] [rbp+18h] BYREF

  v5 = a3;
  result = ReadWord(a1, a2, a3);
  if ( (_WORD)result )
    return result;
  v10 = (unsigned int)(v8 + 2);
  if ( !*v7
    || *v7 == 1
    || *v7 == 2
    || *v7 == 3
    || *v7 == 4
    || *v7 == 5
    || *v7 == 6
    || (v11 = (unsigned __int16)*v7 - 7, *v7 == 7) )
  {
    v15 = 0;
    result = ReadWord(v9, &v15, v10);
    if ( (_WORD)result )
      return result;
    *(_DWORD *)(v14 + 4) = v15;
    goto LABEL_16;
  }
  v12 = v7 + 2;
  if ( v11 != 7 )
    v10 = (unsigned int)(v10 + 2);
  result = ReadLong(v9, v12, v10);
  if ( !(_WORD)result )
  {
LABEL_16:
    if ( a4 )
      *a4 = v13 - v5 + 4;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001ce6c  mov     [rsp+arg_0], rbx
0x18001ce71  mov     [rsp+arg_8], rsi
0x18001ce76  push    rdi
0x18001ce77  sub     rsp, 20h
0x18001ce7b  mov     rbx, r9
0x18001ce7e  mov     edi, r8d
0x18001ce81  mov     r10, rdx
0x18001ce84  mov     r11, rcx
0x18001ce87  call    ReadWord
0x18001ce8c  xor     esi, esi
0x18001ce8e  test    ax, ax
0x18001ce91  jnz     short loc_18001CF11
0x18001ce93  movzx   ecx, word ptr [rdx]
0x18001ce96  add     r8d, 2
0x18001ce9a  test    ecx, ecx
0x18001ce9c  jz      short loc_18001CEDD
0x18001ce9e  sub     ecx, 1
0x18001cea1  jz      short loc_18001CEDD
0x18001cea3  sub     ecx, 1
0x18001cea6  jz      short loc_18001CEDD
0x18001cea8  sub     ecx, 1
0x18001ceab  jz      short loc_18001CEDD
0x18001cead  sub     ecx, 1
0x18001ceb0  jz      short loc_18001CEDD
0x18001ceb2  sub     ecx, 1
0x18001ceb5  jz      short loc_18001CEDD
0x18001ceb7  sub     ecx, 1
0x18001ceba  jz      short loc_18001CEDD
0x18001cebc  sub     ecx, 1
0x18001cebf  jz      short loc_18001CEDD
0x18001cec1  add     rdx, 4
0x18001cec5  cmp     ecx, 7
0x18001cec8  mov     rcx, r11
0x18001cecb  jz      short loc_18001CED1
0x18001cecd  add     r8d, 2
0x18001ced1  call    ReadLong
0x18001ced6  test    ax, ax
0x18001ced9  jnz     short loc_18001CF11
0x18001cedb  jmp     short loc_18001CEFD
0x18001cedd  lea     rdx, [rsp+28h+arg_10]
0x18001cee2  mov     [rsp+28h+arg_10], si
0x18001cee7  mov     rcx, r11
0x18001ceea  call    ReadWord
0x18001ceef  test    ax, ax
0x18001cef2  jnz     short loc_18001CF11
0x18001cef4  movzx   eax, [rsp+28h+arg_10]
0x18001cef9  mov     [r10+4], eax
0x18001cefd  test    rbx, rbx
0x18001cf00  jz      short loc_18001CF0F
0x18001cf02  sub     r8w, di
0x18001cf06  add     r8w, 4
0x18001cf0b  mov     [rbx], r8w
0x18001cf0f  mov     eax, esi
0x18001cf11  mov     rbx, [rsp+28h+arg_0]
0x18001cf16  mov     rsi, [rsp+28h+arg_8]
0x18001cf1b  add     rsp, 20h
0x18001cf1f  pop     rdi
0x18001cf20  retn
```
