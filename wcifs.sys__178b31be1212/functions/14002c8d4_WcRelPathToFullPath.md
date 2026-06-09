# WcRelPathToFullPath

- ea: `0x14002c8d4`
- end: `0x14002ca23`
- name: `WcRelPathToFullPath`
- size: `335`
- prototype: `int __fastcall(USHORT *pusResult, unsigned __int16, const void *, const void *, USHORT)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001a62c`
- `0x14002bf4c`

## callees

- `0x1400020c4`
- `0x1400024d4`
- `0x140007dc0`
- `0x14002c8d4`

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
        wil_details_featureDescriptors_a->DeviceExtension,
        a2,
        14,
        v9,
        (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
        v14,
        35);
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
0x14002c8d4  push    rbx
0x14002c8d6  push    rsi
0x14002c8d7  push    rdi
0x14002c8d8  push    r12
0x14002c8da  push    r14
0x14002c8dc  push    r15
0x14002c8de  sub     rsp, 48h
0x14002c8e2  movzx   r14d, [rsp+78h+arg_20]
0x14002c8eb  mov     r15, r9
0x14002c8ee  movzx   eax, word ptr [rcx+2]
0x14002c8f2  mov     r11, r8
0x14002c8f5  movzx   esi, dx
0x14002c8f8  mov     rdi, rcx
0x14002c8fb  add     r14d, esi
0x14002c8fe  cmp     eax, r14d
0x14002c901  jnb     short loc_14002C92F
0x14002c903  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c90a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c911  jz      loc_14002C9C7
0x14002c917  mov     [rsp+78h+var_40], 0C0000023h
0x14002c91f  mov     r9d, 0Ah
0x14002c925  mov     dword ptr [rsp+78h+var_48], 66h ; 'f'
0x14002c92d  jmp     short loc_14002C997
0x14002c92f  mov     rcx, [rcx+8]; void *
0x14002c933  mov     r8, rsi; Size
0x14002c936  mov     rdx, r11; Src
0x14002c939  call    memmove
0x14002c93e  mov     r9, [rdi+8]
0x14002c942  xor     r12d, r12d
0x14002c945  add     r9, rsi
0x14002c948  mov     edx, 5Ch ; '\'
0x14002c94d  test    si, si
0x14002c950  jz      short loc_14002C959
0x14002c952  cmp     [r9-2], dx
0x14002c957  jnz     short loc_14002C961
0x14002c959  mov     bl, r12b
0x14002c95c  test    si, si
0x14002c95f  jnz     short loc_14002C9D8
0x14002c961  movzx   eax, word ptr [rdi+2]
0x14002c965  mov     ecx, r14d
0x14002c968  add     rcx, 2
0x14002c96c  cmp     rax, rcx
0x14002c96f  jnb     short loc_14002C9CE
0x14002c971  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c978  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c97f  jz      short loc_14002C9C7
0x14002c981  mov     [rsp+78h+var_40], 0C0000023h
0x14002c989  mov     r9d, 0Bh
0x14002c98f  mov     dword ptr [rsp+78h+var_48], 77h ; 'w'
0x14002c997  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002c99e  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x14002c9a5  mov     [rsp+78h+var_50], rax
0x14002c9aa  mov     r8d, 0Eh
0x14002c9b0  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x14002c9b7  mov     dl, 2
0x14002c9b9  mov     [rsp+78h+var_58], rax
0x14002c9be  mov     rcx, [rcx+40h]
0x14002c9c2  call    WPP_RECORDER_SF_sDd
0x14002c9c7  mov     eax, 0C0000023h
0x14002c9cc  jmp     short loc_14002CA14
0x14002c9ce  mov     [r9], dx
0x14002c9d2  mov     bl, 1
0x14002c9d4  add     r9, 2
0x14002c9d8  movzx   r8d, [rsp+78h+arg_20]; Size
0x14002c9e1  mov     rdx, r15; Src
0x14002c9e4  mov     rcx, r9; void *
0x14002c9e7  call    memmove
0x14002c9ec  movzx   edx, [rsp+78h+arg_20]; usAddend
0x14002c9f4  mov     r8, rdi; pusResult
0x14002c9f7  movzx   ecx, si; usAugend
0x14002c9fa  call    RtlUShortAdd
0x14002c9ff  test    eax, eax
0x14002ca01  js      short loc_14002CA14
0x14002ca03  test    bl, bl
0x14002ca05  jz      short loc_14002CA14
0x14002ca07  movzx   edx, word ptr [rdi]; usAddend
0x14002ca0a  mov     ecx, 2; usAugend
0x14002ca0f  call    RtlUShortAdd
0x14002ca14  add     rsp, 48h
0x14002ca18  pop     r15
0x14002ca1a  pop     r14
0x14002ca1c  pop     r12
0x14002ca1e  pop     rdi
0x14002ca1f  pop     rsi
0x14002ca20  pop     rbx
0x14002ca21  retn
```
