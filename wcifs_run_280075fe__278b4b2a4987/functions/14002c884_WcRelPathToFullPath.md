# WcRelPathToFullPath

- ea: `0x14002c884`
- end: `0x14002c9d3`
- name: `WcRelPathToFullPath`
- size: `335`
- prototype: `__int64 __usercall@<rax>(USHORT *pusResult@<rcx>, __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001a62c`
- `0x14002befc`

## callees

- `0x1400020c4`
- `0x1400024d4`
- `0x140007dc0`
- `0x14002c884`

## pseudocode

```c
int __fastcall WcRelPathToFullPath(USHORT *pusResult, unsigned __int16 a2, const void *a3, const void *a4, USHORT a5)
{
  __int64 v6; // rsi
  unsigned int v8; // r14d
  int v9; // r9d
  _WORD *v10; // r9
  char v11; // bl
  int result; // eax
  USHORT *v13; // r8
  char v14; // [rsp+30h] [rbp-48h]

  v6 = a2;
  v8 = a2 + a5;
  if ( pusResult[1] < v8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 10;
      v14 = 102;
LABEL_10:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        14,
        v9,
        (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
        v14,
        -1073741789);
      return -1073741789;
    }
    return -1073741789;
  }
  memmove(*((void **)pusResult + 1), a3, a2);
  v10 = (_WORD *)(v6 + *((_QWORD *)pusResult + 1));
  HIBYTE(a2) = 0;
  if ( (_WORD)v6 && *(v10 - 1) != 92 || (v11 = 0, !(_WORD)v6) )
  {
    if ( pusResult[1] < (unsigned __int64)v8 + 2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = 11;
        v14 = 119;
        goto LABEL_10;
      }
      return -1073741789;
    }
    *v10 = 92;
    v11 = 1;
    ++v10;
  }
  memmove(v10, a4, a5);
  result = RtlUShortAdd(v6, a5, pusResult);
  if ( result >= 0 )
  {
    if ( v11 )
      return RtlUShortAdd(2u, *pusResult, v13);
  }
  return result;
}

```

## disassembly

```asm
0x14002c884  push    rbx
0x14002c886  push    rsi
0x14002c887  push    rdi
0x14002c888  push    r12
0x14002c88a  push    r14
0x14002c88c  push    r15
0x14002c88e  sub     rsp, 48h
0x14002c892  movzx   r14d, [rsp+78h+arg_20]
0x14002c89b  mov     r15, r9
0x14002c89e  movzx   eax, word ptr [rcx+2]
0x14002c8a2  mov     r11, r8
0x14002c8a5  movzx   esi, dx
0x14002c8a8  mov     rdi, rcx
0x14002c8ab  add     r14d, esi
0x14002c8ae  cmp     eax, r14d
0x14002c8b1  jnb     short loc_14002C8DF
0x14002c8b3  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c8ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c8c1  jz      loc_14002C977
0x14002c8c7  mov     [rsp+78h+var_40], 0C0000023h
0x14002c8cf  mov     r9d, 0Ah
0x14002c8d5  mov     dword ptr [rsp+78h+var_48], 66h ; 'f'
0x14002c8dd  jmp     short loc_14002C947
0x14002c8df  mov     rcx, [rcx+8]; void *
0x14002c8e3  mov     r8, rsi; Size
0x14002c8e6  mov     rdx, r11; Src
0x14002c8e9  call    memmove
0x14002c8ee  mov     r9, [rdi+8]
0x14002c8f2  xor     r12d, r12d
0x14002c8f5  add     r9, rsi
0x14002c8f8  mov     edx, 5Ch ; '\'
0x14002c8fd  test    si, si
0x14002c900  jz      short loc_14002C909
0x14002c902  cmp     [r9-2], dx
0x14002c907  jnz     short loc_14002C911
0x14002c909  mov     bl, r12b
0x14002c90c  test    si, si
0x14002c90f  jnz     short loc_14002C988
0x14002c911  movzx   eax, word ptr [rdi+2]
0x14002c915  mov     ecx, r14d
0x14002c918  add     rcx, 2
0x14002c91c  cmp     rax, rcx
0x14002c91f  jnb     short loc_14002C97E
0x14002c921  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c928  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c92f  jz      short loc_14002C977
0x14002c931  mov     [rsp+78h+var_40], 0C0000023h
0x14002c939  mov     r9d, 0Bh
0x14002c93f  mov     dword ptr [rsp+78h+var_48], 77h ; 'w'
0x14002c947  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c94e  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x14002c955  mov     [rsp+78h+var_50], rax
0x14002c95a  mov     r8d, 0Eh
0x14002c960  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x14002c967  mov     dl, 2
0x14002c969  mov     [rsp+78h+var_58], rax
0x14002c96e  mov     rcx, [rcx+40h]
0x14002c972  call    WPP_RECORDER_SF_sDd
0x14002c977  mov     eax, 0C0000023h
0x14002c97c  jmp     short loc_14002C9C4
0x14002c97e  mov     [r9], dx
0x14002c982  mov     bl, 1
0x14002c984  add     r9, 2
0x14002c988  movzx   r8d, [rsp+78h+arg_20]; Size
0x14002c991  mov     rdx, r15; Src
0x14002c994  mov     rcx, r9; void *
0x14002c997  call    memmove
0x14002c99c  movzx   edx, [rsp+78h+arg_20]; usAddend
0x14002c9a4  mov     r8, rdi; pusResult
0x14002c9a7  movzx   ecx, si; usAugend
0x14002c9aa  call    RtlUShortAdd
0x14002c9af  test    eax, eax
0x14002c9b1  js      short loc_14002C9C4
0x14002c9b3  test    bl, bl
0x14002c9b5  jz      short loc_14002C9C4
0x14002c9b7  movzx   edx, word ptr [rdi]; usAddend
0x14002c9ba  mov     ecx, 2; usAugend
0x14002c9bf  call    RtlUShortAdd
0x14002c9c4  add     rsp, 48h
0x14002c9c8  pop     r15
0x14002c9ca  pop     r14
0x14002c9cc  pop     r12
0x14002c9ce  pop     rdi
0x14002c9cf  pop     rsi
0x14002c9d0  pop     rbx
0x14002c9d1  retn
```
