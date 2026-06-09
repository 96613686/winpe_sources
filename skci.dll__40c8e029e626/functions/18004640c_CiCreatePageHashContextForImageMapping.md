# CiCreatePageHashContextForImageMapping

- ea: `0x18004640c`
- end: `0x180046609`
- name: `CiCreatePageHashContextForImageMapping`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180046610`

## callees

- `0x180006f10`
- `0x180010a88`
- `0x180045ee0`
- `0x1800461f8`
- `0x18004640c`

## import_xrefs

- `securekernel!SkFreePool` at `0x1800465d4`
- `securekernel!SkFreePool` at `0x1800465d4`

## pseudocode

```c
__int64 __fastcall CiCreatePageHashContextForImageMapping(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _QWORD *a6,
        ULONG *a7)
{
  unsigned int v9; // eax
  unsigned int v10; // r15d
  unsigned int v11; // r8d
  __int64 v12; // r9
  unsigned int v13; // ebp
  unsigned int v14; // edx
  ULONG v15; // esi
  unsigned int v16; // ecx
  unsigned int v17; // eax
  int PageHash; // ebx
  char *PoolHelper; // rax
  char *v20; // rdi
  int v21; // r9d
  _DWORD *v22; // r13
  int v24; // [rsp+28h] [rbp-60h]
  __int64 v25; // [rsp+30h] [rbp-58h]
  __int64 v26; // [rsp+38h] [rbp-50h]
  ULONG pulResult; // [rsp+A8h] [rbp+20h] BYREF

  pulResult = 0;
  if ( (a4 & 0xFFF) != 0 || a2 > a4 )
    return (unsigned int)-1073741701;
  v9 = (a2 + 4095) & 0xFFFFF000;
  v10 = v9;
  if ( v9 < a2 )
    return (unsigned int)-1073741675;
  v11 = *(unsigned __int16 *)(a1 + 6);
  v12 = a1 + *(unsigned __int16 *)(a1 + 20);
  v13 = v9 >> 12;
  v14 = 0;
  v15 = 1;
  while ( v14 < v11 )
  {
    v16 = *(_DWORD *)(v12 + 40 * (v14 + 1LL));
    v17 = (v16 + 4095) & 0xFFFFF000;
    if ( v17 < v16 || (v17 >> 12) + v13 < v13 )
      return (unsigned int)-1073741675;
    v13 += v17 >> 12;
    ++v14;
  }
  PageHash = RtlULongLongToULong(36LL * v13, &pulResult);
  if ( PageHash >= 0 )
  {
    if ( pulResult + 104 >= pulResult )
    {
      PoolHelper = (char *)SkAllocatePoolHelper(256, pulResult + 104, 1668499779);
      v20 = PoolHelper;
      if ( !PoolHelper )
        return (unsigned int)-1073741801;
      v21 = a5;
      v22 = PoolHelper + 104;
      *(_DWORD *)PoolHelper = a2;
      *((_QWORD *)PoolHelper + 12) = PoolHelper + 104;
      *((_DWORD *)PoolHelper + 20) = 32780;
      *((_DWORD *)PoolHelper + 23) = v13;
      *((_DWORD *)PoolHelper + 21) = 32;
      *((_DWORD *)PoolHelper + 22) = 36;
      *((_DWORD *)PoolHelper + 1) = v21;
      PageHash = CiCalculateFirstPageHash(
                   32780,
                   a3,
                   a4,
                   v21,
                   (__int64)(PoolHelper + 108),
                   v24,
                   v25,
                   v26,
                   (__int64)(PoolHelper + 16),
                   (unsigned int *)PoolHelper + 2);
      if ( PageHash >= 0 )
      {
        *v22 = 0;
        pulResult = 1;
        if ( v10 == 4096 )
        {
LABEL_17:
          *a6 = v20;
          *a7 = v15;
          return (unsigned int)PageHash;
        }
        PageHash = CiAddPagesToPageHashContext(
                     (_DWORD)v22,
                     v13,
                     (unsigned int)&pulResult,
                     (int)a3 + 4096,
                     v10 - 4096,
                     4096);
        if ( PageHash >= 0 )
        {
          v15 = pulResult;
          goto LABEL_17;
        }
      }
      SkFreePool(1, v20);
      return (unsigned int)PageHash;
    }
    return (unsigned int)-1073741675;
  }
  return (unsigned int)PageHash;
}

```

## disassembly

```asm
0x18004640c  mov     rax, rsp
0x18004640f  mov     [rax+8], rbx
0x180046413  mov     [rax+18h], r8
0x180046417  push    rbp
0x180046418  push    rsi
0x180046419  push    rdi
0x18004641a  push    r12
0x18004641c  push    r13
0x18004641e  push    r14
0x180046420  push    r15
0x180046422  sub     rsp, 50h
0x180046426  mov     dword ptr [rax+20h], 0
0x18004642d  mov     r12d, r9d
0x180046430  mov     r14d, edx
0x180046433  test    r9d, 0FFFh
0x18004643a  jnz     loc_1800465E9
0x180046440  cmp     edx, r9d
0x180046443  ja      loc_1800465E9
0x180046449  lea     eax, [rdx+0FFFh]
0x18004644f  mov     r10d, 0FFFFF000h
0x180046455  and     eax, r10d
0x180046458  mov     r15d, eax
0x18004645b  cmp     eax, edx
0x18004645d  jb      loc_1800465E2
0x180046463  movzx   r9d, word ptr [rcx+14h]
0x180046468  mov     ebp, eax
0x18004646a  movzx   r8d, word ptr [rcx+6]
0x18004646f  add     r9, rcx
0x180046472  shr     ebp, 0Ch
0x180046475  xor     edx, edx
0x180046477  lea     esi, [rdx+1]
0x18004647a  cmp     edx, r8d
0x18004647d  jnb     short loc_1800464B1
0x18004647f  mov     eax, edx
0x180046481  add     rax, rsi
0x180046484  lea     rax, [rax+rax*4]
0x180046488  mov     ecx, [r9+rax*8]
0x18004648c  lea     eax, [rcx+0FFFh]
0x180046492  and     eax, r10d
0x180046495  cmp     eax, ecx
0x180046497  jb      loc_1800465E2
0x18004649d  shr     eax, 0Ch
0x1800464a0  lea     ecx, [rax+rbp]
0x1800464a3  cmp     ecx, ebp
0x1800464a5  jb      loc_1800465E2
0x1800464ab  mov     ebp, ecx
0x1800464ad  add     edx, esi
0x1800464af  jmp     short loc_18004647A
0x1800464b1  mov     eax, ebp
0x1800464b3  lea     rdx, [rsp+88h+pulResult]; pulResult
0x1800464bb  lea     rcx, [rax+rax*8]
0x1800464bf  shl     rcx, 2; ullOperand
0x1800464c3  call    RtlULongLongToULong
0x1800464c8  mov     ebx, eax
0x1800464ca  test    eax, eax
0x1800464cc  js      loc_1800465EE
0x1800464d2  mov     eax, [rsp+88h+pulResult]
0x1800464d9  lea     ecx, [rax+68h]
0x1800464dc  cmp     ecx, eax
0x1800464de  jb      loc_1800465E2
0x1800464e4  mov     edx, ecx
0x1800464e6  mov     r8d, 63734943h
0x1800464ec  mov     ecx, 100h
0x1800464f1  call    SkAllocatePoolHelper
0x1800464f6  mov     rdi, rax
0x1800464f9  test    rax, rax
0x1800464fc  jnz     short loc_180046508
0x1800464fe  mov     ebx, 0C0000017h
0x180046503  jmp     loc_1800465EE
0x180046508  mov     r9d, [rsp+88h+arg_20]
0x180046510  lea     r13, [rax+68h]
0x180046514  mov     [rax], r14d
0x180046517  lea     r8, [rdi+6Ch]
0x18004651b  mov     r14, [rsp+88h+arg_10]
0x180046523  lea     rdx, [rdi+10h]
0x180046527  mov     ecx, 800Ch
0x18004652c  mov     [rax+60h], r13
0x180046530  mov     [rax+50h], ecx
0x180046533  mov     [rax+5Ch], ebp
0x180046536  mov     dword ptr [rax+54h], 20h ; ' '
0x18004653d  mov     dword ptr [rax+58h], 24h ; '$'
0x180046544  mov     [rax+4], r9d
0x180046548  add     rax, 8
0x18004654c  mov     [rsp+88h+var_40], rax
0x180046551  mov     [rsp+88h+var_48], rdx
0x180046556  mov     rdx, r14
0x180046559  mov     [rsp+88h+var_68], r8
0x18004655e  mov     r8d, r12d
0x180046561  call    CiCalculateFirstPageHash
0x180046566  mov     ebx, eax
0x180046568  test    eax, eax
0x18004656a  js      short loc_1800465CF
0x18004656c  lea     eax, [r15-1000h]
0x180046573  mov     dword ptr [r13+0], 0
0x18004657b  mov     [rsp+88h+pulResult], esi
0x180046582  test    eax, eax
0x180046584  jz      short loc_1800465B8
0x180046586  lea     r9, [r14+1000h]
0x18004658d  mov     [rsp+88h+var_60], 1000h
0x180046595  lea     r8, [rsp+88h+pulResult]
0x18004659d  mov     dword ptr [rsp+88h+var_68], eax
0x1800465a1  mov     edx, ebp
0x1800465a3  mov     rcx, r13
0x1800465a6  call    CiAddPagesToPageHashContext
0x1800465ab  mov     ebx, eax
0x1800465ad  test    eax, eax
0x1800465af  js      short loc_1800465CF
0x1800465b1  mov     esi, [rsp+88h+pulResult]
0x1800465b8  mov     rax, [rsp+88h+arg_28]
0x1800465c0  mov     [rax], rdi
0x1800465c3  mov     rax, [rsp+88h+arg_30]
0x1800465cb  mov     [rax], esi
0x1800465cd  jmp     short loc_1800465EE
0x1800465cf  mov     rdx, rdi
0x1800465d2  mov     ecx, esi
0x1800465d4  call    cs:__imp_SkFreePool
0x1800465db  nop     dword ptr [rax+rax+00h]
0x1800465e0  jmp     short loc_1800465EE
0x1800465e2  mov     ebx, 0C0000095h
0x1800465e7  jmp     short loc_1800465EE
0x1800465e9  mov     ebx, 0C000007Bh
0x1800465ee  mov     eax, ebx
0x1800465f0  mov     rbx, [rsp+88h+arg_0]
0x1800465f8  add     rsp, 50h
0x1800465fc  pop     r15
0x1800465fe  pop     r14
0x180046600  pop     r13
0x180046602  pop     r12
0x180046604  pop     rdi
0x180046605  pop     rsi
0x180046606  pop     rbp
0x180046607  retn
```
