# WanpCreateConnEntry

- ea: `0x14000f57c`
- end: `0x14000f722`
- name: `WanpCreateConnEntry`
- size: `422`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000f3fc`
- `0x1400124bc`

## callees

- `0x1400032dc`
- `0x1400051c0`
- `0x1400054c0`
- `0x14000f57c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f598`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f598`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6b9`
- `ntoskrnl!ExAllocatePool2` at `0x14000f682`
- `ntoskrnl!ExAllocatePool2` at `0x14000f682`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f5ec`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f5ec`

## pseudocode

```c
void *__fastcall WanpCreateConnEntry(int a1, char a2)
{
  __int64 v2; // rsi
  PVOID v4; // rax
  void *v5; // rbx
  unsigned int v6; // edx
  unsigned int i; // r8d
  int v8; // eax
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  void *Pool2; // rax
  void *v13; // rdi
  __int64 v14; // rcx
  int v15; // eax

  v2 = a1;
  v4 = ExAllocateFromNPagedLookasideList(&g_llConnBlocks);
  v5 = v4;
  if ( v4 )
  {
    memset(v4, 0, 0x130u);
    *((_DWORD *)v5 + 31) = 3;
    *((_DWORD *)v5 + 25) = v2;
    *((_BYTE *)v5 + 4) = a2;
    *(_DWORD *)v5 = 1852793687;
    *((_DWORD *)v5 + 68) = 1;
    *((_DWORD *)v5 + 70) = 1400;
    KeInitializeSpinLock((PKSPIN_LOCK)v5 + 11);
    v6 = g_ulNextConnIndex;
    for ( i = 0; i < g_ulConnTableSize; ++i )
    {
      if ( !*((_QWORD *)g_puipConnTable + v6) )
      {
        *((_QWORD *)g_puipConnTable + v6) = v5;
        ++g_rgulConns[v2];
        v8 = g_ulNextConnIndex;
        *((_DWORD *)v5 + 26) = v6;
        g_ulNextConnIndex = (v8 + 1) % (unsigned int)g_ulConnTableSize;
        return v5;
      }
      v6 = (v6 + 1) % g_ulConnTableSize;
    }
    v10 = (unsigned int)(g_ulConnTableSize + 32);
    if ( (unsigned int)v10 >= g_ulConnTableSize )
    {
      v11 = 8 * v10;
      if ( v11 <= 0xFFFFFFFF )
      {
        Pool2 = (void *)ExAllocatePool2(64, (unsigned int)v11, 1668313687);
        v13 = Pool2;
        if ( Pool2 )
        {
          memmove(Pool2, g_puipConnTable, 8LL * (unsigned int)g_ulConnTableSize);
          ExFreePoolWithTag(g_puipConnTable, 0);
          v14 = (unsigned int)g_ulConnTableSize;
          ++g_rgulConns[v2];
          g_puipConnTable = v13;
          *((_QWORD *)v13 + v14) = v5;
          *((_DWORD *)v5 + 26) = g_ulConnTableSize;
          v15 = g_ulConnTableSize + 1;
          g_ulConnTableSize += 32;
          g_ulNextConnIndex = v15;
          return v5;
        }
      }
    }
    FreeConnection(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x14000f57c  mov     [rsp+arg_0], rbx
0x14000f581  mov     [rsp+arg_8], rsi
0x14000f586  push    rdi
0x14000f587  sub     rsp, 20h
0x14000f58b  movsxd  rsi, ecx
0x14000f58e  mov     dil, dl
0x14000f591  lea     rcx, g_llConnBlocks; Lookaside
0x14000f598  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000f59f  nop     dword ptr [rax+rax+00h]
0x14000f5a4  mov     rbx, rax
0x14000f5a7  test    rax, rax
0x14000f5aa  jz      loc_14000F70F
0x14000f5b0  xor     edx, edx; Val
0x14000f5b2  mov     r8d, 130h; Size
0x14000f5b8  mov     rcx, rax; void *
0x14000f5bb  call    memset
0x14000f5c0  lea     rcx, [rbx+58h]; SpinLock
0x14000f5c4  mov     dword ptr [rbx+7Ch], 3
0x14000f5cb  mov     [rbx+64h], esi
0x14000f5ce  mov     [rbx+4], dil
0x14000f5d2  mov     dword ptr [rbx], 6E6F6357h
0x14000f5d8  mov     dword ptr [rbx+110h], 1
0x14000f5e2  mov     dword ptr [rbx+118h], 578h
0x14000f5ec  call    cs:__imp_KeInitializeSpinLock
0x14000f5f3  nop     dword ptr [rax+rax+00h]
0x14000f5f8  mov     edx, cs:g_ulNextConnIndex
0x14000f5fe  xor     r8d, r8d
0x14000f601  mov     ecx, cs:g_ulConnTableSize
0x14000f607  cmp     r8d, ecx
0x14000f60a  jnb     short loc_14000F658
0x14000f60c  mov     r9, cs:g_puipConnTable
0x14000f613  mov     eax, edx
0x14000f615  cmp     qword ptr [r9+rax*8], 0
0x14000f61a  jz      short loc_14000F628
0x14000f61c  lea     eax, [rdx+1]
0x14000f61f  xor     edx, edx
0x14000f621  div     ecx
0x14000f623  inc     r8d
0x14000f626  jmp     short loc_14000F601
0x14000f628  mov     [r9+rax*8], rbx
0x14000f62c  lea     r8, g_rgulConns
0x14000f633  inc     dword ptr [r8+rsi*4]
0x14000f637  mov     eax, cs:g_ulNextConnIndex
0x14000f63d  mov     [rbx+68h], edx
0x14000f640  inc     eax
0x14000f642  xor     edx, edx
0x14000f644  div     cs:g_ulConnTableSize
0x14000f64a  mov     cs:g_ulNextConnIndex, edx
0x14000f650  mov     rax, rbx
0x14000f653  jmp     loc_14000F711
0x14000f658  lea     eax, [rcx+20h]
0x14000f65b  cmp     eax, ecx
0x14000f65d  jb      loc_14000F707
0x14000f663  shl     rax, 3
0x14000f667  mov     ecx, 0FFFFFFFFh
0x14000f66c  cmp     rax, rcx
0x14000f66f  ja      loc_14000F707
0x14000f675  mov     edx, eax
0x14000f677  mov     ecx, 40h ; '@'
0x14000f67c  mov     r8d, 63707257h
0x14000f682  call    cs:__imp_ExAllocatePool2
0x14000f689  nop     dword ptr [rax+rax+00h]
0x14000f68e  mov     rdi, rax
0x14000f691  test    rax, rax
0x14000f694  jz      short loc_14000F707
0x14000f696  mov     r8d, cs:g_ulConnTableSize
0x14000f69d  mov     rcx, rax; void *
0x14000f6a0  mov     rdx, cs:g_puipConnTable; Src
0x14000f6a7  shl     r8, 3; Size
0x14000f6ab  call    memmove
0x14000f6b0  mov     rcx, cs:g_puipConnTable; P
0x14000f6b7  xor     edx, edx; Tag
0x14000f6b9  call    cs:__imp_ExFreePoolWithTag
0x14000f6c0  nop     dword ptr [rax+rax+00h]
0x14000f6c5  mov     ecx, cs:g_ulConnTableSize
0x14000f6cb  lea     r8, g_rgulConns
0x14000f6d2  inc     dword ptr [r8+rsi*4]
0x14000f6d6  mov     cs:g_puipConnTable, rdi
0x14000f6dd  mov     [rdi+rcx*8], rbx
0x14000f6e1  mov     eax, cs:g_ulConnTableSize
0x14000f6e7  mov     [rbx+68h], eax
0x14000f6ea  mov     ecx, cs:g_ulConnTableSize
0x14000f6f0  lea     eax, [rcx+1]
0x14000f6f3  add     ecx, 20h ; ' '
0x14000f6f6  mov     cs:g_ulConnTableSize, ecx
0x14000f6fc  mov     cs:g_ulNextConnIndex, eax
0x14000f702  jmp     loc_14000F650
0x14000f707  mov     rcx, rbx; Entry
0x14000f70a  call    FreeConnection
0x14000f70f  xor     eax, eax
0x14000f711  mov     rbx, [rsp+28h+arg_0]
0x14000f716  mov     rsi, [rsp+28h+arg_8]
0x14000f71b  add     rsp, 20h
0x14000f71f  pop     rdi
0x14000f720  retn
```
