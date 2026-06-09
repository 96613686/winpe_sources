# InsertIntoTable

- ea: `0x18002b450`
- end: `0x18002b682`
- name: `InsertIntoTable`
- size: `562`
- prototype: `__int64 __fastcall(int, int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002a460`
- `0x18002a508`

## callees

- `0x18002a7b4`
- `0x18002b450`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003fb7c`
- `0x18003fb88`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002b5c0`
- `KERNEL32!HeapAlloc` at `0x18002b5c0`
- `KERNEL32!Sleep` at `0x18002b4b8`
- `KERNEL32!Sleep` at `0x18002b4b8`

## string_xrefs

- `0x18002b527`: `Trying to insert an item already in the perm ID array`

## pseudocode

```c
__int64 __fastcall InsertIntoTable(int a1, int a2, __int64 a3, unsigned int a4)
{
  unsigned int v5; // r13d
  __int64 v6; // rbx
  int v8; // esi
  _DWORD *v9; // rdi
  unsigned int v10; // r15d
  int v11; // ebp
  int v12; // ecx
  int v13; // r14d
  bool v14; // cc
  const char *v15; // r9
  _DWORD *v16; // rax
  _DWORD *v17; // r14
  int v18; // r15d
  int v19; // [rsp+30h] [rbp-48h]
  __int64 v20[8]; // [rsp+38h] [rbp-40h] BYREF

  v20[0] = 0;
  v5 = a4;
  GetProviderSortedArray(*(unsigned int *)(a3 + 32), v20);
  v6 = v20[0];
  if ( !v20[0] )
    return TRACELogPrint(65538, "Couldn't find the provider in the permanent array list!");
  while ( _InterlockedExchange((volatile __int32 *)v6, 1) == 1 )
    Sleep(0xAu);
  if ( a1 )
  {
    v8 = *(_DWORD *)(v6 + 20);
    v9 = *(_DWORD **)(v6 + 8);
    v10 = *(_DWORD *)(v6 + 16);
  }
  else
  {
    v8 = *(_DWORD *)(v6 + 36);
    v9 = *(_DWORD **)(v6 + 24);
    v10 = *(_DWORD *)(v6 + 32);
  }
  v11 = 0;
  if ( v8 )
  {
    v12 = v8 - 1;
    v19 = v8 - 1;
    v13 = (v8 - 1) / 2 + (v8 - 1) % 2;
    if ( v8 - 1 >= 0 )
    {
      do
      {
        v14 = v9[2 * v13] <= a4;
        if ( v9[2 * v13] == a4 )
        {
          TRACELogPrint(65538, "Trying to insert an item already in the perm ID array");
          v15 = "Line";
          if ( !a1 )
            v15 = "Phone";
          TRACELogPrint(65538, "Provider %ls, %hs array, ID 0x%lu", (const wchar_t *)(a3 + 1196), v15, a4);
          v12 = v19;
          v14 = v9[2 * v13] <= a4;
        }
        if ( v14 )
        {
          v11 = v13 + 1;
        }
        else
        {
          v12 = v13 - 1;
          v19 = v13 - 1;
        }
        v13 = (v12 + v11) / 2 + (v12 + v11) % 2;
      }
      while ( v12 >= v11 );
      v6 = v20[0];
      v5 = a4;
    }
  }
  if ( v8 < v10 )
    goto LABEL_25;
  v16 = HeapAlloc(ghTapisrvHeap, 8u, 16 * v10);
  v17 = v16;
  if ( v16 )
  {
    memcpy_0(v16, v9, 8LL * v10);
    ServerFree(v9);
    v18 = 2 * v10;
    v9 = v17;
    if ( a1 )
    {
      *(_DWORD *)(v6 + 16) = v18;
      *(_QWORD *)(v6 + 8) = v17;
    }
    else
    {
      *(_DWORD *)(v6 + 32) = v18;
      *(_QWORD *)(v6 + 24) = v17;
    }
LABEL_25:
    if ( v11 >= v8 )
    {
      if ( v11 > v8 )
        TRACELogPrint(262146, "InsertIntoTable: lLow %d > dwCurrentElements %d", v11, v8);
    }
    else
    {
      memmove_0(&v9[2 * v11 + 2], &v9[2 * v11], 8LL * (unsigned int)(v8 - v11));
    }
    v9[2 * v11] = v5;
    v9[2 * v11 + 1] = a2;
    if ( a1 )
      ++*(_DWORD *)(v6 + 20);
    else
      ++*(_DWORD *)(v6 + 36);
  }
  return (unsigned int)_InterlockedExchange((volatile __int32 *)v6, 0);
}

```

## disassembly

```asm
0x18002b450  mov     rax, rsp
0x18002b453  mov     [rax+8], rbx
0x18002b457  mov     [rax+20h], r9d
0x18002b45b  mov     [rax+18h], r8
0x18002b45f  mov     [rax+10h], edx
0x18002b462  push    rbp
0x18002b463  push    rsi
0x18002b464  push    rdi
0x18002b465  push    r12
0x18002b467  push    r13
0x18002b469  push    r14
0x18002b46b  push    r15
0x18002b46d  sub     rsp, 40h
0x18002b471  mov     r12d, ecx
0x18002b474  mov     qword ptr [rax-40h], 0
0x18002b47c  mov     ecx, [r8+20h]
0x18002b480  lea     rdx, [rax-40h]
0x18002b484  mov     r13d, r9d
0x18002b487  call    GetProviderSortedArray
0x18002b48c  mov     rbx, [rsp+78h+var_40]
0x18002b491  test    rbx, rbx
0x18002b494  jnz     short loc_18002B4AC
0x18002b496  lea     rdx, aCouldnTFindThe; "Couldn't find the provider in the perma"...
0x18002b49d  mov     ecx, 10002h
0x18002b4a2  call    TRACELogPrint
0x18002b4a7  jmp     loc_18002B66A
0x18002b4ac  mov     edi, 1
0x18002b4b1  jmp     short loc_18002B4BE
0x18002b4b3  mov     ecx, 0Ah; dwMilliseconds
0x18002b4b8  call    cs:__imp_Sleep
0x18002b4be  mov     eax, edi
0x18002b4c0  xchg    eax, [rbx]
0x18002b4c2  cmp     eax, edi
0x18002b4c4  jz      short loc_18002B4B3
0x18002b4c6  test    r12d, r12d
0x18002b4c9  jz      short loc_18002B4D8
0x18002b4cb  mov     esi, [rbx+14h]
0x18002b4ce  mov     rdi, [rbx+8]
0x18002b4d2  mov     r15d, [rbx+10h]
0x18002b4d6  jmp     short loc_18002B4E3
0x18002b4d8  mov     esi, [rbx+24h]
0x18002b4db  mov     rdi, [rbx+18h]
0x18002b4df  mov     r15d, [rbx+20h]
0x18002b4e3  xor     ebp, ebp
0x18002b4e5  mov     [rsp+78h+var_44], r15d
0x18002b4ea  test    esi, esi
0x18002b4ec  jz      loc_18002B5A8
0x18002b4f2  lea     ecx, [rsi-1]
0x18002b4f5  mov     eax, ecx
0x18002b4f7  mov     [rsp+78h+var_48], ecx
0x18002b4fb  cdq
0x18002b4fc  lea     r8d, [rbp+2]
0x18002b500  idiv    r8d
0x18002b503  lea     r14d, [rax+rdx]
0x18002b507  test    ecx, ecx
0x18002b509  js      loc_18002B5A8
0x18002b50f  mov     ebx, [rsp+78h+arg_18]
0x18002b516  mov     r15, [rsp+78h+arg_10]
0x18002b51e  movsxd  r13, r14d
0x18002b521  cmp     [rdi+r13*8], ebx
0x18002b525  jnz     short loc_18002B577
0x18002b527  lea     rdx, aTryingToInsert; "Trying to insert an item already in the"...
0x18002b52e  mov     ecx, 10002h
0x18002b533  call    TRACELogPrint
0x18002b538  lea     rax, aPhone; "Phone"
0x18002b53f  mov     [rsp+78h+var_58], ebx
0x18002b543  test    r12d, r12d
0x18002b546  lea     r9, aLine; "Line"
0x18002b54d  lea     r8, [r15+4ACh]
0x18002b554  mov     ecx, 10002h
0x18002b559  cmovz   r9, rax
0x18002b55d  lea     rdx, aProviderLsHsAr; "Provider %ls, %hs array, ID 0x%lu"
0x18002b564  call    TRACELogPrint
0x18002b569  mov     ecx, [rsp+78h+var_48]
0x18002b56d  mov     r8d, 2
0x18002b573  cmp     [rdi+r13*8], ebx
0x18002b577  jbe     short loc_18002B583
0x18002b579  lea     ecx, [r14-1]
0x18002b57d  mov     [rsp+78h+var_48], ecx
0x18002b581  jmp     short loc_18002B587
0x18002b583  lea     ebp, [r14+1]
0x18002b587  lea     eax, [rcx+rbp]
0x18002b58a  cdq
0x18002b58b  idiv    r8d
0x18002b58e  lea     r14d, [rax+rdx]
0x18002b592  cmp     ecx, ebp
0x18002b594  jge     short loc_18002B51E
0x18002b596  mov     rbx, [rsp+78h+var_40]
0x18002b59b  mov     r15d, [rsp+78h+var_44]
0x18002b5a0  mov     r13d, [rsp+78h+arg_18]
0x18002b5a8  cmp     esi, r15d
0x18002b5ab  jb      short loc_18002B609
0x18002b5ad  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002b5b4  mov     r8d, r15d
0x18002b5b7  shl     r8d, 4; dwBytes
0x18002b5bb  mov     edx, 8; dwFlags
0x18002b5c0  call    cs:__imp_HeapAlloc
0x18002b5c6  mov     r14, rax
0x18002b5c9  test    rax, rax
0x18002b5cc  jz      loc_18002B666
0x18002b5d2  mov     r8d, r15d
0x18002b5d5  mov     rdx, rdi; Src
0x18002b5d8  shl     r8, 3; Size
0x18002b5dc  mov     rcx, rax; void *
0x18002b5df  call    memcpy_0
0x18002b5e4  mov     rcx, rdi; lpMem
0x18002b5e7  call    ServerFree
0x18002b5ec  add     r15d, r15d
0x18002b5ef  mov     rdi, r14
0x18002b5f2  test    r12d, r12d
0x18002b5f5  jz      short loc_18002B601
0x18002b5f7  mov     [rbx+10h], r15d
0x18002b5fb  mov     [rbx+8], r14
0x18002b5ff  jmp     short loc_18002B609
0x18002b601  mov     [rbx+20h], r15d
0x18002b605  mov     [rbx+18h], r14
0x18002b609  cmp     ebp, esi
0x18002b60b  jge     short loc_18002B62E
0x18002b60d  movsxd  rax, ebp
0x18002b610  sub     esi, ebp
0x18002b612  mov     r8d, esi
0x18002b615  shl     r8, 3; Size
0x18002b619  lea     rdx, [rdi+rax*8]; Src
0x18002b61d  lea     eax, [rbp+1]
0x18002b620  movsxd  rcx, eax
0x18002b623  lea     rcx, [rdi+rcx*8]; void *
0x18002b627  call    memmove_0
0x18002b62c  jmp     short loc_18002B647
0x18002b62e  jle     short loc_18002B647
0x18002b630  mov     r9d, esi
0x18002b633  lea     rdx, aInsertintotabl; "InsertIntoTable: lLow %d > dwCurrentEle"...
0x18002b63a  mov     r8d, ebp
0x18002b63d  mov     ecx, 40002h
0x18002b642  call    TRACELogPrint
0x18002b647  mov     ecx, [rsp+78h+arg_8]
0x18002b64e  movsxd  rax, ebp
0x18002b651  mov     [rdi+rax*8], r13d
0x18002b655  mov     [rdi+rax*8+4], ecx
0x18002b659  test    r12d, r12d
0x18002b65c  jz      short loc_18002B663
0x18002b65e  inc     dword ptr [rbx+14h]
0x18002b661  jmp     short loc_18002B666
0x18002b663  inc     dword ptr [rbx+24h]
0x18002b666  xor     eax, eax
0x18002b668  xchg    eax, [rbx]
0x18002b66a  mov     rbx, [rsp+78h+arg_0]
0x18002b672  add     rsp, 40h
0x18002b676  pop     r15
0x18002b678  pop     r14
0x18002b67a  pop     r13
0x18002b67c  pop     r12
0x18002b67e  pop     rdi
0x18002b67f  pop     rsi
0x18002b680  pop     rbp
0x18002b681  retn
```
