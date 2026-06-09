# RfsHashTableCreate

- ea: `0x140029800`
- end: `0x140029912`
- name: `RfsHashTableCreate`
- size: `274`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14004b2c0`
- `0x14004cbc8`
- `0x14004cc40`

## callees

- `0x140029800`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140029826`
- `ntoskrnl!ExAllocatePool2` at `0x140029826`

## pseudocode

```c
__int64 __fastcall RfsHashTableCreate(
        __int64 *a1,
        int a2,
        int a3,
        int a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 Pool2; // rax
  __int64 v14; // r10
  __int64 result; // rax
  unsigned int v16; // r8d
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rcx

  Pool2 = ExAllocatePool2(64, (unsigned int)(32 * (a2 + 2)), 1936216908);
  v14 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = a2;
    v16 = 0;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_DWORD *)(Pool2 + 4) = a4;
    *(_DWORD *)(Pool2 + 8) = 0;
    *(_DWORD *)(Pool2 + 16) = a3;
    *(_QWORD *)(Pool2 + 24) = a6;
    *(_QWORD *)(Pool2 + 32) = a7;
    *(_QWORD *)(Pool2 + 40) = a8;
    *(_QWORD *)(Pool2 + 48) = a9;
    *(_QWORD *)(Pool2 + 56) = Pool2 + 64;
    if ( (a5 & 1) != 0 )
    {
      if ( a2 )
      {
        do
        {
          v17 = v16++;
          v17 *= 32;
          *(_DWORD *)(v17 + *(_QWORD *)(Pool2 + 56) + 12) |= 1u;
          v18 = (_QWORD *)(v17 + *(_QWORD *)(Pool2 + 56) + 16LL);
          v18[1] = v18;
          *v18 = v18;
          *(_DWORD *)(v17 + *(_QWORD *)(Pool2 + 56)) = 0;
        }
        while ( v16 < *(_DWORD *)Pool2 );
      }
    }
    else if ( a2 )
    {
      do
      {
        v19 = 32LL * v16++;
        v20 = (_QWORD *)(v19 + *(_QWORD *)(Pool2 + 56) + 16LL);
        v20[1] = v20;
        *v20 = v20;
        *(_QWORD *)(v19 + *(_QWORD *)(Pool2 + 56)) = 0;
      }
      while ( v16 < *(_DWORD *)Pool2 );
    }
    result = 0;
  }
  else
  {
    result = 3221225626LL;
  }
  *a1 = v14;
  return result;
}

```

## disassembly

```asm
0x140029800  push    rbx
0x140029802  push    rsi
0x140029803  push    rdi
0x140029804  push    r14
0x140029806  sub     rsp, 28h
0x14002980a  mov     ebx, edx
0x14002980c  mov     esi, r8d
0x14002980f  add     edx, 2
0x140029812  mov     r14, rcx
0x140029815  shl     edx, 5
0x140029818  mov     ecx, 40h ; '@'
0x14002981d  mov     r8d, 7368534Ch
0x140029823  mov     edi, r9d
0x140029826  call    cs:__imp_ExAllocatePool2
0x14002982d  nop     dword ptr [rax+rax+00h]
0x140029832  xor     r9d, r9d
0x140029835  mov     r10, rax
0x140029838  test    rax, rax
0x14002983b  jnz     short loc_140029847
0x14002983d  mov     eax, 0C000009Ah
0x140029842  jmp     loc_140029904
0x140029847  mov     [rax], ebx
0x140029849  mov     r11d, 1
0x14002984f  mov     r8d, r9d
0x140029852  mov     [rax+0Ch], r11d
0x140029856  mov     [rax+4], edi
0x140029859  mov     [rax+8], r9d
0x14002985d  mov     [rax+10h], esi
0x140029860  mov     rax, [rsp+48h+arg_28]
0x140029865  mov     [r10+18h], rax
0x140029869  mov     rax, [rsp+48h+arg_30]
0x140029871  mov     [r10+20h], rax
0x140029875  mov     rax, [rsp+48h+arg_38]
0x14002987d  mov     [r10+28h], rax
0x140029881  mov     rax, [rsp+48h+arg_40]
0x140029889  mov     [r10+30h], rax
0x14002988d  lea     rax, [r10+40h]
0x140029891  mov     [r10+38h], rax
0x140029895  test    [rsp+48h+arg_20], r11b
0x14002989a  jz      short loc_1400298D4
0x14002989c  test    ebx, ebx
0x14002989e  jz      short loc_140029901
0x1400298a0  mov     rax, [r10+38h]
0x1400298a4  mov     edx, r8d
0x1400298a7  add     r8d, r11d
0x1400298aa  shl     rdx, 5
0x1400298ae  or      [rdx+rax+0Ch], r11d
0x1400298b3  mov     rcx, [r10+38h]
0x1400298b7  add     rcx, 10h
0x1400298bb  add     rcx, rdx
0x1400298be  mov     [rcx+8], rcx
0x1400298c2  mov     [rcx], rcx
0x1400298c5  mov     rax, [r10+38h]
0x1400298c9  mov     [rdx+rax], r9d
0x1400298cd  cmp     r8d, [r10]
0x1400298d0  jb      short loc_1400298A0
0x1400298d2  jmp     short loc_140029901
0x1400298d4  test    ebx, ebx
0x1400298d6  jz      short loc_140029901
0x1400298d8  mov     rcx, [r10+38h]
0x1400298dc  mov     edx, r8d
0x1400298df  add     rcx, 10h
0x1400298e3  shl     rdx, 5
0x1400298e7  add     r8d, r11d
0x1400298ea  add     rcx, rdx
0x1400298ed  mov     [rcx+8], rcx
0x1400298f1  mov     [rcx], rcx
0x1400298f4  mov     rax, [r10+38h]
0x1400298f8  mov     [rdx+rax], r9
0x1400298fc  cmp     r8d, [r10]
0x1400298ff  jb      short loc_1400298D8
0x140029901  mov     eax, r9d
0x140029904  mov     [r14], r10
0x140029907  add     rsp, 28h
0x14002990b  pop     r14
0x14002990d  pop     rdi
0x14002990e  pop     rsi
0x14002990f  pop     rbx
0x140029910  retn
```
