# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000b3f0`
- end: `0x18000b48f`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c158`
- `0x18000c6d8`
- `0x18000ebec`
- `0x18000f440`
- `0x18000fa10`

## callees

- `0x18000b3f0`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r11
  __int64 v6; // r9
  unsigned __int16 *v7; // rax
  int v8; // ecx
  __int64 v9; // rax
  unsigned __int16 *v10; // rcx
  unsigned int v11; // r8d
  __int64 v12; // r10

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    return (unsigned int)-2147024809;
  v6 = a2;
  v7 = a1;
  while ( *v7 )
  {
    ++v7;
    if ( !--v6 )
    {
      v8 = -2147024809;
      v9 = 0;
      goto LABEL_7;
    }
  }
  v9 = a2 - v6;
  v8 = 0;
LABEL_7:
  if ( v8 < 0 )
    return (unsigned int)v8;
  v10 = &a1[v9];
  v11 = 0;
  v12 = a2 - v9;
  if ( a2 == v9 )
  {
LABEL_12:
    --v10;
    v11 = -2147024774;
  }
  else
  {
    while ( v3 && *a3 )
    {
      *v10++ = *a3++;
      --v3;
      if ( !--v12 )
        goto LABEL_12;
    }
  }
  *v10 = 0;
  return v11;
}

```

## disassembly

```asm
0x18000b3f0  mov     [rsp+arg_0], rbx
0x18000b3f5  lea     rax, [rdx-1]
0x18000b3f9  mov     r11d, 7FFFFFFEh
0x18000b3ff  mov     rbx, r8
0x18000b402  mov     r10, rdx
0x18000b405  mov     r8, rcx
0x18000b408  cmp     rax, r11
0x18000b40b  ja      short loc_18000B486
0x18000b40d  mov     r9, rdx
0x18000b410  mov     rax, rcx
0x18000b413  cmp     word ptr [rax], 0
0x18000b417  jz      short loc_18000B42E
0x18000b419  add     rax, 2
0x18000b41d  sub     r9, 1
0x18000b421  jnz     short loc_18000B413
0x18000b423  xor     edx, edx
0x18000b425  mov     ecx, 80070057h
0x18000b42a  mov     eax, edx
0x18000b42c  jmp     short loc_18000B438
0x18000b42e  mov     rax, r10
0x18000b431  sub     rax, r9
0x18000b434  xor     edx, edx
0x18000b436  mov     ecx, edx
0x18000b438  test    ecx, ecx
0x18000b43a  js      short loc_18000B48B
0x18000b43c  lea     rcx, [r8+rax*2]
0x18000b440  mov     r8d, edx
0x18000b443  sub     r10, rax
0x18000b446  jz      short loc_18000B469
0x18000b448  test    r11, r11
0x18000b44b  jz      short loc_18000B47A
0x18000b44d  movzx   eax, word ptr [rbx]
0x18000b450  test    ax, ax
0x18000b453  jz      short loc_18000B475
0x18000b455  mov     [rcx], ax
0x18000b458  add     rbx, 2
0x18000b45c  add     rcx, 2
0x18000b460  dec     r11
0x18000b463  sub     r10, 1
0x18000b467  jnz     short loc_18000B448
0x18000b469  sub     rcx, 2
0x18000b46d  mov     r8d, 8007007Ah
0x18000b473  jmp     short loc_18000B47A
0x18000b475  test    r10, r10
0x18000b478  jz      short loc_18000B469
0x18000b47a  mov     [rcx], dx
0x18000b47d  mov     eax, r8d
0x18000b480  mov     rbx, [rsp+arg_0]
0x18000b485  retn
0x18000b486  mov     ecx, 80070057h
0x18000b48b  mov     eax, ecx
0x18000b48d  jmp     short loc_18000B480
```
