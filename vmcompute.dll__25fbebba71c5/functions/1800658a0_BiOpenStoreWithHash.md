# BiOpenStoreWithHash

- ea: `0x1800658a0`
- end: `0x180065a6f`
- name: `BiOpenStoreWithHash`
- size: `463`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180053bec`
- `0x180054fe8`

## callees

- `0x180004829`
- `0x180065058`
- `0x1800650c8`
- `0x1800656c0`
- `0x1800658a0`
- `0x180065a78`
- `0x18006a138`
- `0x18006b964`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180065946`
- `ntdll!RtlAllocateHeap` at `0x180065946`
- `ntdll!RtlFreeHeap` at `0x180065a45`
- `ntdll!RtlFreeHeap` at `0x180065a45`

## string_xrefs

- `0x18006598b`: `Store path: "%s"`
- `0x1800659d9`: `BcdOpenStore: Failed to add store from file %ws. StoreFlags: 0x%x Status: %x`
- `0x1800659a5`: `Store will be accessed with offline registry APIs.`
- `0x1800658e7`: `BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x`
- `0x18006590d`: `Opening store. Flags: 0x%x`
- `0x1800659f8`: `GuidCache`

## pseudocode

```c
__int64 __fastcall BiOpenStoreWithHash(const void **a1, __int64 a2, __int64 a3, __int64 *a4)
{
  const void **v4; // rbx
  int v6; // edi
  const wchar_t *v7; // r8
  unsigned int v9; // esi
  __int64 v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // edi
  _DWORD *Heap; // rax
  void *v14; // r14
  _DWORD *v15; // rdi
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdi
  int v19; // eax
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v20 = a3;
  v4 = a1;
  LOBYTE(a1) = 1;
  v6 = BiAcquireBcdSyncMutant(a1);
  if ( v6 >= 0 )
  {
    v20 = 0;
    v9 = 2;
    BiLogMessage(2, L"Opening store. Flags: 0x%x");
    if ( v4 )
    {
      v12 = *(unsigned __int16 *)v4 + 14;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      v14 = Heap;
      if ( Heap )
      {
        Heap[1] = v12;
        v15 = Heap + 3;
        *Heap = 1;
        Heap[2] = 3;
        memcpy_0(Heap + 3, v4[1], *(unsigned __int16 *)v4);
        *((_WORD *)v15 + ((unsigned __int64)*(unsigned __int16 *)v4 >> 1)) = 0;
        BiLogMessage(2, L"Store path: \"%s\"", v15);
        BiLogMessage(2, L"Store will be accessed with offline registry APIs.");
        v17 = BiAddStoreFromFile(v14, 32, v16, &v20);
        v11 = v17;
        if ( v17 >= 0 )
        {
          v18 = v20;
          BiDeleteRegistryValue(v20, L"GuidCache");
          v19 = BiMarkTreatAsSystemStore(v18, 0);
          v11 = v19;
          if ( v19 >= 0 )
            *a4 = v18 | 2;
          else
            BiLogMessage(4, L"Failed to clear system store flag. Status: %x", (unsigned int)v19);
        }
        else
        {
          if ( v17 != -1073741809 )
            v9 = 4;
          BiLogMessage(
            v9,
            L"BcdOpenStore: Failed to add store from file %ws. StoreFlags: 0x%x Status: %x",
            v15,
            32,
            v17);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      }
      else
      {
        v11 = -1073741801;
      }
    }
    else
    {
      v11 = -1073741811;
    }
    LOBYTE(v10) = 1;
    BiReleaseBcdSyncMutant(v10);
    return v11;
  }
  else
  {
    if ( v4 )
      v7 = (const wchar_t *)v4[1];
    else
      v7 = L"NULL";
    BiLogMessage(4, L"BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x", v7);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1800658a0  mov     [rsp+arg_0], rbx
0x1800658a5  mov     [rsp+arg_8], rsi
0x1800658aa  mov     [rsp+arg_10], r8
0x1800658af  push    rdi
0x1800658b0  push    r14
0x1800658b2  push    r15
0x1800658b4  sub     rsp, 30h
0x1800658b8  mov     rbx, rcx
0x1800658bb  mov     r15, r9
0x1800658be  mov     cl, 1
0x1800658c0  call    BiAcquireBcdSyncMutant
0x1800658c5  mov     edi, eax
0x1800658c7  test    eax, eax
0x1800658c9  jns     short loc_1800658FE
0x1800658cb  test    rbx, rbx
0x1800658ce  jz      short loc_1800658D6
0x1800658d0  mov     r8, [rbx+8]
0x1800658d4  jmp     short loc_1800658DD
0x1800658d6  lea     r8, aNull_0; "NULL"
0x1800658dd  mov     r9d, 1
0x1800658e3  mov     [rsp+48h+var_28], edi
0x1800658e7  lea     rdx, aBcdopenstoreFa; "BcdOpenStore: Failed to acquire BCD syn"...
0x1800658ee  lea     ecx, [r9+3]
0x1800658f2  call    BiLogMessage
0x1800658f7  mov     eax, edi
0x1800658f9  jmp     loc_180065A5A
0x1800658fe  mov     r8d, 1
0x180065904  mov     [rsp+48h+arg_10], 0
0x18006590d  lea     rdx, aOpeningStoreFl; "Opening store. Flags: 0x%x"
0x180065914  lea     esi, [r8+1]
0x180065918  mov     ecx, esi
0x18006591a  call    BiLogMessage
0x18006591f  test    rbx, rbx
0x180065922  jnz     short loc_18006592E
0x180065924  mov     ebx, 0C000000Dh
0x180065929  jmp     loc_180065A51
0x18006592e  mov     rcx, gs:60h
0x180065937  xor     edx, edx; Flags
0x180065939  movzx   edi, word ptr [rbx]
0x18006593c  add     edi, 0Eh
0x18006593f  mov     r8d, edi; Size
0x180065942  mov     rcx, [rcx+30h]; HeapHandle
0x180065946  call    cs:__imp_RtlAllocateHeap
0x18006594d  nop     dword ptr [rax+rax+00h]
0x180065952  mov     r14, rax
0x180065955  test    rax, rax
0x180065958  jnz     short loc_180065964
0x18006595a  mov     ebx, 0C0000017h
0x18006595f  jmp     loc_180065A51
0x180065964  mov     [rax+4], edi
0x180065967  lea     rdi, [rax+0Ch]
0x18006596b  mov     dword ptr [rax], 1
0x180065971  mov     rcx, rdi; void *
0x180065974  mov     dword ptr [rax+8], 3
0x18006597b  movzx   r8d, word ptr [rbx]; Size
0x18006597f  mov     rdx, [rbx+8]; Src
0x180065983  call    memcpy_0
0x180065988  movzx   ecx, word ptr [rbx]
0x18006598b  lea     rdx, aStorePathS; "Store path: \"%s\""
0x180065992  shr     rcx, 1
0x180065995  xor     eax, eax
0x180065997  mov     r8, rdi
0x18006599a  mov     [rdi+rcx*2], ax
0x18006599e  mov     ecx, esi
0x1800659a0  call    BiLogMessage
0x1800659a5  lea     rdx, aStoreWillBeAcc; "Store will be accessed with offline reg"...
0x1800659ac  mov     ecx, esi
0x1800659ae  call    BiLogMessage
0x1800659b3  lea     r9, [rsp+48h+arg_10]
0x1800659b8  mov     edx, 20h ; ' '
0x1800659bd  mov     rcx, r14
0x1800659c0  call    BiAddStoreFromFile
0x1800659c5  mov     ebx, eax
0x1800659c7  test    eax, eax
0x1800659c9  jns     short loc_1800659F3
0x1800659cb  mov     ecx, 4
0x1800659d0  mov     [rsp+48h+var_28], eax
0x1800659d4  cmp     eax, 0C000000Fh
0x1800659d9  lea     rdx, aBcdopenstoreFa_0; "BcdOpenStore: Failed to add store from "...
0x1800659e0  mov     r8, rdi
0x1800659e3  cmovnz  esi, ecx
0x1800659e6  lea     r9d, [rcx+1Ch]
0x1800659ea  mov     ecx, esi
0x1800659ec  call    BiLogMessage
0x1800659f1  jmp     short loc_180065A33
0x1800659f3  mov     rdi, [rsp+48h+arg_10]
0x1800659f8  lea     rdx, aGuidcache; "GuidCache"
0x1800659ff  mov     rcx, rdi
0x180065a02  call    BiDeleteRegistryValue
0x180065a07  xor     edx, edx
0x180065a09  mov     rcx, rdi
0x180065a0c  call    BiMarkTreatAsSystemStore
0x180065a11  mov     ebx, eax
0x180065a13  test    eax, eax
0x180065a15  jns     short loc_180065A2D
0x180065a17  mov     r8d, eax
0x180065a1a  lea     rdx, aFailedToClearS; "Failed to clear system store flag. Stat"...
0x180065a21  mov     ecx, 4
0x180065a26  call    BiLogMessage
0x180065a2b  jmp     short loc_180065A33
0x180065a2d  or      rdi, rsi
0x180065a30  mov     [r15], rdi
0x180065a33  mov     rcx, gs:60h
0x180065a3c  mov     r8, r14; P
0x180065a3f  xor     edx, edx; Flags
0x180065a41  mov     rcx, [rcx+30h]; HeapHandle
0x180065a45  call    cs:__imp_RtlFreeHeap
0x180065a4c  nop     dword ptr [rax+rax+00h]
0x180065a51  mov     cl, 1
0x180065a53  call    BiReleaseBcdSyncMutant
0x180065a58  mov     eax, ebx
0x180065a5a  mov     rbx, [rsp+48h+arg_0]
0x180065a5f  mov     rsi, [rsp+48h+arg_8]
0x180065a64  add     rsp, 30h
0x180065a68  pop     r15
0x180065a6a  pop     r14
0x180065a6c  pop     rdi
0x180065a6d  retn
```
