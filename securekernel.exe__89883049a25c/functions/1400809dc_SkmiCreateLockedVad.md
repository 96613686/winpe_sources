# SkmiCreateLockedVad

- ea: `0x1400809dc`
- end: `0x140080ae7`
- name: `SkmiCreateLockedVad`
- size: `267`
- prototype: `__int64 __fastcall(unsigned __int64, __int64, __int64, unsigned int, __int64 *)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c554`
- `0x1400280b0`
- `0x14005bbe8`
- `0x1400603cc`
- `0x140066464`
- `0x14006b310`
- `0x140087dd8`

## callees

- `0x14000b084`
- `0x14000f0f0`
- `0x1400809dc`

## pseudocode

```c
__int64 __fastcall SkmiCreateLockedVad(unsigned __int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 *a5)
{
  __int64 Pool; // rbx
  unsigned __int64 v7; // rsi
  __int64 result; // rax
  int v9; // eax
  int v10; // edi
  _QWORD *StackBase; // rdx
  __int64 v12; // rdx

  Pool = a3;
  *a5 = 0;
  if ( a1 < 0x10000 )
    return 3221225496LL;
  v7 = a1 + a2 - 1;
  if ( v7 < a1 || v7 > 0x7FFFFFFEFFFFLL )
    return 3221225496LL;
  if ( !a3 )
  {
    Pool = SkAllocatePool(512, a4, 1684100685);
    if ( !Pool )
      return 3221225626LL;
  }
  *(_QWORD *)(Pool + 48) = 0;
  *(_DWORD *)(Pool + 24) = a1 >> 12;
  v9 = *(_DWORD *)(Pool + 32);
  *(_DWORD *)(Pool + 36) = 1;
  *(_QWORD *)(Pool + 40) = 0;
  v10 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(a1 >> 44)) & 0xFFF;
  *(_DWORD *)(Pool + 28) = v7 >> 12;
  *(_DWORD *)(Pool + 32) = v10 ^ (v10 ^ (v7 >> 44 << 12)) & 0xFFF000;
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
  {
    v12 = StackBase[18];
    if ( v12 )
      --*(_WORD *)(v12 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(Pool + 40);
  result = 0;
  *a5 = Pool;
  return result;
}

```

## disassembly

```asm
0x1400809dc  push    rbx
0x1400809de  push    rsi
0x1400809df  push    rdi
0x1400809e0  push    r14
0x1400809e2  sub     rsp, 28h
0x1400809e6  mov     r14, [rsp+48h+arg_20]
0x1400809eb  mov     rbx, r8
0x1400809ee  mov     rdi, rcx
0x1400809f1  mov     qword ptr [r14], 0
0x1400809f8  cmp     rcx, 10000h
0x1400809ff  jb      loc_140080AD7
0x140080a05  lea     rsi, [rdx-1]
0x140080a09  add     rsi, rcx
0x140080a0c  cmp     rsi, rcx
0x140080a0f  jb      loc_140080AD7
0x140080a15  mov     rax, 7FFFFFFEFFFFh
0x140080a1f  cmp     rsi, rax
0x140080a22  ja      loc_140080AD7
0x140080a28  test    rbx, rbx
0x140080a2b  jnz     short loc_140080A52
0x140080a2d  mov     edx, r9d
0x140080a30  mov     ecx, 200h
0x140080a35  mov     r8d, 6461564Dh
0x140080a3b  call    SkAllocatePool
0x140080a40  mov     rbx, rax
0x140080a43  test    rax, rax
0x140080a46  jnz     short loc_140080A52
0x140080a48  mov     eax, 0C000009Ah
0x140080a4d  jmp     loc_140080ADC
0x140080a52  mov     rax, rdi
0x140080a55  mov     qword ptr [rbx+30h], 0
0x140080a5d  shr     rax, 0Ch
0x140080a61  lea     rcx, [rbx+28h]
0x140080a65  mov     [rbx+18h], eax
0x140080a68  mov     eax, [rbx+20h]
0x140080a6b  shr     rdi, 2Ch
0x140080a6f  xor     edi, eax
0x140080a71  mov     dword ptr [rbx+24h], 1
0x140080a78  and     edi, 0FFFh
0x140080a7e  mov     qword ptr [rcx], 0
0x140080a85  xor     edi, eax
0x140080a87  mov     rax, rsi
0x140080a8a  shr     rsi, 2Ch
0x140080a8e  shl     esi, 0Ch
0x140080a91  xor     esi, edi
0x140080a93  shr     rax, 0Ch
0x140080a97  and     esi, 0FFF000h
0x140080a9d  mov     [rbx+1Ch], eax
0x140080aa0  xor     esi, edi
0x140080aa2  mov     [rbx+20h], esi
0x140080aa5  mov     rdx, gs:8
0x140080aae  test    rdx, rdx
0x140080ab1  jz      short loc_140080ACB
0x140080ab3  mov     rdx, [rdx+90h]
0x140080aba  test    rdx, rdx
0x140080abd  jz      short loc_140080ACB
0x140080abf  mov     rax, qword ptr cs:xmmword_140167150
0x140080ac6  dec     word ptr [rdx+rax]
0x140080aca  nop
0x140080acb  call    SkAcquirePushLockExclusive
0x140080ad0  xor     eax, eax
0x140080ad2  mov     [r14], rbx
0x140080ad5  jmp     short loc_140080ADC
0x140080ad7  mov     eax, 0C0000018h
0x140080adc  add     rsp, 28h
0x140080ae0  pop     r14
0x140080ae2  pop     rdi
0x140080ae3  pop     rsi
0x140080ae4  pop     rbx
0x140080ae5  retn
```
