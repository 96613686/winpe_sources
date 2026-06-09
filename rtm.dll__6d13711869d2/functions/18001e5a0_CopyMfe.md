# CopyMfe

- ea: `0x18001e5a0`
- end: `0x18001e775`
- name: `CopyMfe`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001e77c`
- `0x18001ed64`

## callees

- `0x18001e5a0`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x18001e615`
- `ntdll!NtQuerySystemTime` at `0x18001e701`
- `ntdll!NtQuerySystemTime` at `0x18001e615`
- `ntdll!NtQuerySystemTime` at `0x18001e701`

## pseudocode

```c
__int64 __fastcall CopyMfe(__int64 a1, __int64 a2, _DWORD *a3, int a4)
{
  char v4; // si
  _DWORD *v7; // r8
  unsigned __int64 v8; // rdx
  __int64 result; // rax
  __int64 **v10; // rdi
  unsigned int v11; // r9d
  __int64 *i; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  int v15; // eax
  __int64 **v16; // rdi
  __int64 v17; // r9
  __int64 *j; // r8
  __int64 v19; // rcx
  union _LARGE_INTEGER v20[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = a4;
  *a3 = *(_DWORD *)(a1 + 32);
  a3[1] = *(_DWORD *)(a2 + 104);
  a3[2] = *(_DWORD *)(a2 + 108);
  a3[4] = *(_DWORD *)(a2 + 112);
  a3[3] = *(_DWORD *)(a2 + 120);
  a3[5] = *(_DWORD *)(a2 + 136);
  a3[6] = *(_DWORD *)(a2 + 124);
  a3[7] = *(_DWORD *)(a2 + 128);
  a3[8] = *(_DWORD *)(a2 + 132);
  v20[0].QuadPart = 0;
  if ( a4 )
  {
    NtQuerySystemTime(v20);
    v7 = a3 + 16;
    v8 = (v20[0].QuadPart - *(_QWORD *)(a2 + 176)) / 0x989680uLL;
    a3[9] = v8;
    a3[10] = *(_DWORD *)(a2 + 168) - v8;
    a3[11] = *(_DWORD *)(a2 + 80);
    a3[12] = *(_DWORD *)(a2 + 204);
    a3[13] = *(_DWORD *)(a2 + 208);
    a3[14] = *(_DWORD *)(a2 + 212);
    result = *(unsigned int *)(a2 + 216);
    a3[15] = result;
    if ( (v4 & 2) != 0 )
    {
      *v7 = *(_DWORD *)(a2 + 220);
      v7 = a3 + 21;
      a3[17] = *(_DWORD *)(a2 + 224);
      a3[18] = *(_DWORD *)(a2 + 228);
      a3[19] = *(_DWORD *)(a2 + 232);
      result = *(unsigned int *)(a2 + 236);
      a3[20] = result;
    }
    v10 = (__int64 **)(a2 + 88);
    v11 = 0;
    for ( i = *v10; i != (__int64 *)v10; i = (__int64 *)*i )
    {
      v13 = 7LL * v11++;
      v7[v13] = *((_DWORD *)i + 4);
      v7[v13 + 1] = *((_DWORD *)i + 5);
      v7[v13 + 3] = *((_DWORD *)i + 13);
      v7[v13 + 4] = *((_DWORD *)i + 14);
      v7[v13 + 5] = *((_DWORD *)i + 15);
      result = *((unsigned int *)i + 16);
      v7[v13 + 6] = result;
    }
  }
  else
  {
    a3[12] = *(_DWORD *)(a2 + 80);
    NtQuerySystemTime(v20);
    v14 = (v20[0].QuadPart - *(_QWORD *)(a2 + 176)) / 0x989680uLL;
    a3[9] = v14;
    v15 = *(_DWORD *)(a2 + 168);
    v16 = (__int64 **)(a2 + 88);
    result = (unsigned int)(v15 - v14);
    a3[10] = result;
    v17 = 0;
    for ( j = *v16; j != (__int64 *)v16; j = (__int64 *)*j )
    {
      a3[4 * (unsigned int)v17 + 15] = *((_DWORD *)j + 4);
      result = *((unsigned int *)j + 5);
      v19 = 2 * (v17 + 4);
      v17 = (unsigned int)(v17 + 1);
      a3[2 * v19] = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e5a0  mov     r11, rsp
0x18001e5a3  mov     [r11+8], rbx
0x18001e5a7  mov     [r11+10h], rsi
0x18001e5ab  push    rdi
0x18001e5ac  sub     rsp, 30h
0x18001e5b0  mov     eax, [rcx+20h]
0x18001e5b3  mov     esi, r9d
0x18001e5b6  mov     [r8], eax
0x18001e5b9  mov     rbx, r8
0x18001e5bc  mov     eax, [rdx+68h]
0x18001e5bf  mov     rdi, rdx
0x18001e5c2  mov     [r8+4], eax
0x18001e5c6  lea     rcx, [r11-18h]; SystemTime
0x18001e5ca  mov     eax, [rdx+6Ch]
0x18001e5cd  mov     [r8+8], eax
0x18001e5d1  mov     eax, [rdx+70h]
0x18001e5d4  mov     [r8+10h], eax
0x18001e5d8  mov     eax, [rdx+78h]
0x18001e5db  mov     [r8+0Ch], eax
0x18001e5df  mov     eax, [rdx+88h]
0x18001e5e5  mov     [r8+14h], eax
0x18001e5e9  mov     eax, [rdx+7Ch]
0x18001e5ec  mov     [r8+18h], eax
0x18001e5f0  mov     eax, [rdx+80h]
0x18001e5f6  mov     [r8+1Ch], eax
0x18001e5fa  mov     eax, [rdx+84h]
0x18001e600  mov     [r8+20h], eax
0x18001e604  mov     qword ptr [r11-18h], 0
0x18001e60c  test    r9d, r9d
0x18001e60f  jz      loc_18001E6FA
0x18001e615  call    cs:__imp_NtQuerySystemTime
0x18001e61b  mov     rcx, [rsp+38h+var_18]
0x18001e620  lea     r8, [rbx+40h]
0x18001e624  sub     rcx, [rdi+0B0h]
0x18001e62b  mov     rax, 0D6BF94D5E57A42BDh
0x18001e635  mul     rcx
0x18001e638  shr     rdx, 17h
0x18001e63c  mov     [rbx+24h], edx
0x18001e63f  mov     eax, [rdi+0A8h]
0x18001e645  sub     eax, edx
0x18001e647  mov     [rbx+28h], eax
0x18001e64a  mov     eax, [rdi+50h]
0x18001e64d  mov     [rbx+2Ch], eax
0x18001e650  mov     eax, [rdi+0CCh]
0x18001e656  mov     [rbx+30h], eax
0x18001e659  mov     eax, [rdi+0D0h]
0x18001e65f  mov     [rbx+34h], eax
0x18001e662  mov     eax, [rdi+0D4h]
0x18001e668  mov     [rbx+38h], eax
0x18001e66b  mov     eax, [rdi+0D8h]
0x18001e671  mov     [rbx+3Ch], eax
0x18001e674  test    sil, 2
0x18001e678  jz      short loc_18001E6AB
0x18001e67a  mov     eax, [rdi+0DCh]
0x18001e680  mov     [r8], eax
0x18001e683  lea     r8, [rbx+54h]
0x18001e687  mov     eax, [rdi+0E0h]
0x18001e68d  mov     [rbx+44h], eax
0x18001e690  mov     eax, [rdi+0E4h]
0x18001e696  mov     [rbx+48h], eax
0x18001e699  mov     eax, [rdi+0E8h]
0x18001e69f  mov     [rbx+4Ch], eax
0x18001e6a2  mov     eax, [rdi+0ECh]
0x18001e6a8  mov     [rbx+50h], eax
0x18001e6ab  add     rdi, 58h ; 'X'
0x18001e6af  xor     r9d, r9d
0x18001e6b2  mov     rdx, [rdi]
0x18001e6b5  jmp     short loc_18001E6F3
0x18001e6b7  mov     eax, r9d
0x18001e6ba  imul    rcx, rax, 1Ch
0x18001e6be  mov     eax, [rdx+10h]
0x18001e6c1  inc     r9d
0x18001e6c4  mov     [rcx+r8], eax
0x18001e6c8  mov     eax, [rdx+14h]
0x18001e6cb  mov     [rcx+r8+4], eax
0x18001e6d0  mov     eax, [rdx+34h]
0x18001e6d3  mov     [rcx+r8+0Ch], eax
0x18001e6d8  mov     eax, [rdx+38h]
0x18001e6db  mov     [rcx+r8+10h], eax
0x18001e6e0  mov     eax, [rdx+3Ch]
0x18001e6e3  mov     [rcx+r8+14h], eax
0x18001e6e8  mov     eax, [rdx+40h]
0x18001e6eb  mov     [rcx+r8+18h], eax
0x18001e6f0  mov     rdx, [rdx]
0x18001e6f3  cmp     rdx, rdi
0x18001e6f6  jnz     short loc_18001E6B7
0x18001e6f8  jmp     short loc_18001E765
0x18001e6fa  mov     eax, [rdx+50h]
0x18001e6fd  mov     [r8+30h], eax
0x18001e701  call    cs:__imp_NtQuerySystemTime
0x18001e707  mov     rcx, [rsp+38h+var_18]
0x18001e70c  mov     rax, 0D6BF94D5E57A42BDh
0x18001e716  sub     rcx, [rdi+0B0h]
0x18001e71d  mul     rcx
0x18001e720  shr     rdx, 17h
0x18001e724  mov     [rbx+24h], edx
0x18001e727  mov     eax, [rdi+0A8h]
0x18001e72d  add     rdi, 58h ; 'X'
0x18001e731  sub     eax, edx
0x18001e733  mov     [rbx+28h], eax
0x18001e736  xor     r9d, r9d
0x18001e739  mov     r8, [rdi]
0x18001e73c  jmp     short loc_18001E760
0x18001e73e  mov     eax, [r8+10h]
0x18001e742  mov     ecx, r9d
0x18001e745  add     rcx, rcx
0x18001e748  mov     [rbx+rcx*8+3Ch], eax
0x18001e74c  lea     rcx, [r9+4]
0x18001e750  mov     eax, [r8+14h]
0x18001e754  add     rcx, rcx
0x18001e757  inc     r9d
0x18001e75a  mov     [rbx+rcx*8], eax
0x18001e75d  mov     r8, [r8]
0x18001e760  cmp     r8, rdi
0x18001e763  jnz     short loc_18001E73E
0x18001e765  mov     rbx, [rsp+38h+arg_0]
0x18001e76a  mov     rsi, [rsp+38h+arg_8]
0x18001e76f  add     rsp, 30h
0x18001e773  pop     rdi
0x18001e774  retn
```
