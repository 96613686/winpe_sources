# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Remove(ushort)

- ea: `0x1800055b0`
- end: `0x180005651`
- name: `?Remove@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHG@Z`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005cf4`
- `0x180009590`

## callees

- `0x180004b50`
- `0x180004c10`
- `0x1800055b0`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Remove(
        __int64 *a1)
{
  __int64 v2; // rdi
  __int16 *v3; // rbx
  _WORD *v4; // r8
  unsigned __int64 v5; // r10
  __int16 *v6; // rdx
  _WORD *v7; // r9
  __int64 i; // rcx
  __int16 v9; // ax
  __int64 v10; // rbx

  v2 = *(int *)(*a1 - 16);
  if ( (int)((*(_DWORD *)(*a1 - 12) - v2) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v2);
  v3 = (__int16 *)*a1;
  v4 = (_WORD *)*a1;
  v5 = *a1 + 2 * v2;
  if ( *a1 < v5 )
  {
    do
    {
      v6 = v3 + 1;
      if ( *v3 != 13 )
      {
        v7 = v4 + 1;
        for ( i = 0; v4 != v7 && !i; i = 1 )
        {
          v9 = *v3++;
          *v4++ = v9;
        }
      }
      v3 = v6;
    }
    while ( (unsigned __int64)v6 < v5 );
  }
  v10 = v3 - v4;
  *v4 = 0;
  ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)(v2 - v10));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800055b0  mov     [rsp+arg_0], rbx
0x1800055b5  mov     [rsp+arg_8], rsi
0x1800055ba  push    rdi
0x1800055bb  sub     rsp, 20h
0x1800055bf  mov     rax, [rcx]
0x1800055c2  mov     edx, 1
0x1800055c7  mov     rsi, rcx
0x1800055ca  sub     edx, [rax-8]
0x1800055cd  movsxd  rdi, dword ptr [rax-10h]
0x1800055d1  mov     eax, [rax-0Ch]
0x1800055d4  sub     eax, edi
0x1800055d6  or      edx, eax
0x1800055d8  jge     short loc_1800055E1
0x1800055da  mov     edx, edi
0x1800055dc  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800055e1  mov     rbx, [rsi]
0x1800055e4  mov     r8, rbx
0x1800055e7  lea     r10, [rbx+rdi*2]
0x1800055eb  cmp     rbx, r10
0x1800055ee  jnb     short loc_180005627
0x1800055f0  cmp     word ptr [rbx], 0Dh
0x1800055f4  lea     rdx, [rbx+2]
0x1800055f8  jz      short loc_18000561F
0x1800055fa  lea     r9, [r8+2]
0x1800055fe  xor     ecx, ecx
0x180005600  jmp     short loc_18000561A
0x180005602  cmp     rcx, 1
0x180005606  jnb     short loc_18000561F
0x180005608  movzx   eax, word ptr [rbx]
0x18000560b  add     rbx, 2
0x18000560f  mov     [r8], ax
0x180005613  add     r8, 2
0x180005617  inc     rcx
0x18000561a  cmp     r8, r9
0x18000561d  jnz     short loc_180005602
0x18000561f  mov     rbx, rdx
0x180005622  cmp     rdx, r10
0x180005625  jb      short loc_1800055F0
0x180005627  xor     ecx, ecx
0x180005629  sub     rbx, r8
0x18000562c  sar     rbx, 1
0x18000562f  sub     edi, ebx
0x180005631  mov     [r8], cx
0x180005635  mov     edx, edi
0x180005637  mov     rcx, rsi
0x18000563a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18000563f  mov     rsi, [rsp+28h+arg_8]
0x180005644  mov     eax, ebx
0x180005646  mov     rbx, [rsp+28h+arg_0]
0x18000564b  add     rsp, 20h
0x18000564f  pop     rdi
0x180005650  retn
```
