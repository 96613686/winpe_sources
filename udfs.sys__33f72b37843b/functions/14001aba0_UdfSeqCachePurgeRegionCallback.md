# UdfSeqCachePurgeRegionCallback

- ea: `0x14001aba0`
- end: `0x14001ac86`
- name: `UdfSeqCachePurgeRegionCallback`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002c7d8`
- `0x14002c934`

## callees

- `0x140009980`
- `0x14001aba0`

## pseudocode

```c
bool __fastcall UdfSeqCachePurgeRegionCallback(__int64 a1, unsigned int a2, unsigned int a3, _DWORD *a4)
{
  __int64 v5; // r10
  __int64 v7; // rbx
  __int16 v9; // si
  unsigned int v10; // ecx
  unsigned __int16 v11; // r8

  v5 = 32LL * a2;
  v7 = *(_QWORD *)(v5 + a1 + 8);
  if ( v7 == -1 )
    return 0;
  v9 = *(_WORD *)(v5 + a1 + 24);
  *(_QWORD *)(v5 + a1) = *(_QWORD *)(v7 + 32);
  --*a4;
  v10 = *(_DWORD *)(v5 + a1 + 16);
  if ( v10 + *(unsigned __int16 *)(v5 + a1 + 24) > a3 )
  {
    if ( v10 >= a3 )
    {
      *(_QWORD *)(v5 + a1 + 8) = -1;
      UdfSeqCacheUpdateFileRefCount(v7, 0, 0);
    }
    else
    {
      v11 = a3 - *(_WORD *)(v5 + a1 + 16);
      *(_WORD *)(v5 + a1 + 24) = v11;
      *(_QWORD *)(32LL * (a2 + v11) + a1 + 8) = -1;
      *(_DWORD *)(32LL * (a2 + *(unsigned __int16 *)(v5 + a1 + 24)) + a1 + 16) = *(unsigned __int16 *)(v5 + a1 + 24)
                                                                               + *(_DWORD *)(v5 + a1 + 16);
      *(_QWORD *)(32LL * (a2 + *(unsigned __int16 *)(v5 + a1 + 24)) + a1) = *(_QWORD *)(v7 + 32);
      *(_WORD *)(32LL * (a2 + *(unsigned __int16 *)(v5 + a1 + 24)) + a1 + 24) = v9 - *(_WORD *)(v5 + a1 + 24);
    }
  }
  return *a4 == 0;
}

```

## disassembly

```asm
0x14001aba0  mov     [rsp+arg_0], rbx
0x14001aba5  mov     [rsp+arg_8], rsi
0x14001abaa  push    rdi
0x14001abab  sub     rsp, 20h
0x14001abaf  mov     r10d, edx
0x14001abb2  mov     rdi, r9
0x14001abb5  shl     r10, 5
0x14001abb9  mov     r11, rcx
0x14001abbc  mov     r9d, edx
0x14001abbf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001abc3  mov     rbx, [r10+rcx+8]
0x14001abc8  cmp     rbx, rdx
0x14001abcb  jnz     short loc_14001ABD4
0x14001abcd  xor     al, al
0x14001abcf  jmp     loc_14001AC75
0x14001abd4  mov     rax, [rbx+20h]
0x14001abd8  movzx   esi, word ptr [r10+rcx+18h]
0x14001abde  mov     [r10+rcx], rax
0x14001abe2  dec     dword ptr [rdi]
0x14001abe4  movzx   eax, word ptr [r10+r11+18h]
0x14001abea  mov     ecx, [r10+rcx+10h]
0x14001abef  add     eax, ecx
0x14001abf1  cmp     eax, r8d
0x14001abf4  jbe     short loc_14001AC6F
0x14001abf6  cmp     ecx, r8d
0x14001abf9  jnb     short loc_14001AC5D
0x14001abfb  sub     r8w, [r10+r11+10h]
0x14001ac01  movzx   eax, r8w
0x14001ac05  mov     [r10+r11+18h], ax
0x14001ac0b  add     eax, r9d
0x14001ac0e  shl     rax, 5
0x14001ac12  mov     [rax+r11+8], rdx
0x14001ac17  movzx   ecx, word ptr [r10+r11+18h]
0x14001ac1d  mov     edx, [r10+r11+10h]
0x14001ac22  add     edx, ecx
0x14001ac24  add     ecx, r9d
0x14001ac27  shl     rcx, 5
0x14001ac2b  mov     [rcx+r11+10h], edx
0x14001ac30  movzx   ecx, word ptr [r10+r11+18h]
0x14001ac36  mov     rax, [rbx+20h]
0x14001ac3a  add     ecx, r9d
0x14001ac3d  shl     rcx, 5
0x14001ac41  mov     [rcx+r11], rax
0x14001ac45  movzx   eax, word ptr [r10+r11+18h]
0x14001ac4b  sub     si, ax
0x14001ac4e  add     eax, r9d
0x14001ac51  shl     rax, 5
0x14001ac55  mov     [rax+r11+18h], si
0x14001ac5b  jmp     short loc_14001AC6F
0x14001ac5d  mov     [r10+r11+8], rdx
0x14001ac62  xor     r8d, r8d
0x14001ac65  xor     edx, edx
0x14001ac67  mov     rcx, rbx
0x14001ac6a  call    UdfSeqCacheUpdateFileRefCount
0x14001ac6f  cmp     dword ptr [rdi], 0
0x14001ac72  setz    al
0x14001ac75  mov     rbx, [rsp+28h+arg_0]
0x14001ac7a  mov     rsi, [rsp+28h+arg_8]
0x14001ac7f  add     rsp, 20h
0x14001ac83  pop     rdi
0x14001ac84  retn
```
