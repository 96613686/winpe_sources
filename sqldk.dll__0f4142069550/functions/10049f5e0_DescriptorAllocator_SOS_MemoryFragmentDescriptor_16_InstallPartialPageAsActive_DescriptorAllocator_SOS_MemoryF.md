# DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::InstallPartialPageAsActive(DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::PageDesc *,uint,ushort,bool)

- ea: `0x10049f5e0`
- end: `0x10049f7b7`
- name: `?InstallPartialPageAsActive@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@AEAA_NPEAUPageDesc@1@IG_N@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10049ef50`

## callees

- `0x10049f5e0`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x10049f6af`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049f761`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049f6af`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049f761`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049f678`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049f6ba`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049f678`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049f6ba`

## pseudocode

```c
bool __fastcall DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::InstallPartialPageAsActive(
        __int64 a1,
        signed __int64 a2,
        unsigned int a3,
        unsigned __int16 a4,
        char a5)
{
  signed __int64 v6; // rbx
  unsigned __int16 v7; // r12
  unsigned __int64 v9; // r13
  __int64 v10; // r14
  int v11; // esi
  PSLIST_ENTRY v12; // rax
  __int64 v13; // rcx
  PSLIST_ENTRY v14; // rax
  __int64 v15; // rcx
  struct _SLIST_ENTRY *v16; // rdx
  bool v17; // zf
  signed __int32 v19[22]; // [rsp+0h] [rbp-58h] BYREF
  unsigned __int16 v20; // [rsp+70h] [rbp+18h]
  unsigned __int16 v21; // [rsp+78h] [rbp+20h]

  v6 = 0;
  v7 = a4;
  v20 = a4;
  v9 = *(_QWORD *)(a1 + 1216) + ((unsigned __int64)a3 << *(_BYTE *)(a1 + 1228));
  v21 = a4;
  if ( !a5 )
  {
    v21 = a4 + 1;
    if ( a4 + 1 == *(_WORD *)(a1 + 8) )
      v21 = 0;
  }
  while ( 2 )
  {
    v10 = 192LL * v7 + a1 + 1280;
    v11 = 0;
    while ( (unsigned int)v11 < 5 )
    {
      v6 = 0;
      v12 = InterlockedPopEntrySList((PSLIST_HEADER)(v10 + 16LL * v11));
      if ( v12 )
        v6 = (signed __int64)&v12[-1];
      if ( !v6 )
        goto LABEL_24;
      while ( 1 )
      {
        v13 = *(_DWORD *)(v6 + 40) / 0x2Bu;
        if ( (int)v13 <= v11 )
          break;
        _mm_lfence();
        InterlockedPushEntrySList((PSLIST_HEADER)(v10 + 16 * v13), (PSLIST_ENTRY)(v6 + 16));
        v6 = 0;
        v14 = InterlockedPopEntrySList((PSLIST_HEADER)(v10 + 16LL * v11));
        if ( v14 )
          v6 = (signed __int64)&v14[-1];
        if ( !v6 )
          goto LABEL_24;
      }
      *(_DWORD *)(v6 + 48) = 0;
      if ( a2 != _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 8), v6, a2) )
      {
        *(_DWORD *)(v6 + 48) = 2;
        v15 = *(_DWORD *)(v6 + 40) / 0x2Bu
            + 4 * (*(unsigned __int16 *)(v6 + 44) + 2 * (*(unsigned __int16 *)(v6 + 44) + 10LL));
        v16 = (struct _SLIST_ENTRY *)(v6 + 16);
LABEL_23:
        InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 16 * v15), v16);
        goto LABEL_24;
      }
      if ( a2 )
      {
        if ( *(_DWORD *)(a2 + 40) )
        {
          *(_DWORD *)(a2 + 48) = 2;
        }
        else
        {
          *(_DWORD *)(a2 + 48) = 1;
          _InterlockedOr(v19, 0);
          if ( !*(_DWORD *)(a2 + 40) || _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 48), 2, 1) != 1 )
            goto LABEL_24;
        }
        v15 = *(_DWORD *)(a2 + 40) / 0x2Bu
            + 4 * (*(unsigned __int16 *)(a2 + 44) + 2 * (*(unsigned __int16 *)(a2 + 44) + 10LL));
        v16 = (struct _SLIST_ENTRY *)(a2 + 16);
        goto LABEL_23;
      }
LABEL_24:
      ++v11;
      if ( v6 )
        break;
    }
    v7 = 0;
    if ( v20 + 1 != *(_WORD *)(a1 + 8) )
      v7 = v20 + 1;
    v20 = v7;
    v17 = v6 == 0;
    if ( !v6 )
    {
      if ( v7 == v21 )
      {
        v17 = 1;
        return !v17;
      }
      continue;
    }
    return !v17;
  }
}

```

## disassembly

```asm
0x10049f5e0  mov     [rsp+arg_0], rbx
0x10049f5e5  push    rbp
0x10049f5e6  push    rsi
0x10049f5e7  push    rdi
0x10049f5e8  push    r12
0x10049f5ea  push    r13
0x10049f5ec  push    r14
0x10049f5ee  push    r15
0x10049f5f0  sub     rsp, 20h
0x10049f5f4  mov     r15, rcx
0x10049f5f7  mov     r13d, r8d
0x10049f5fa  movzx   ecx, byte ptr [rcx+4CCh]
0x10049f601  xor     ebx, ebx
0x10049f603  shl     r13, cl
0x10049f606  movzx   r12d, r9w
0x10049f60a  mov     [rsp+58h+arg_10], r12d
0x10049f60f  mov     rdi, rdx
0x10049f612  add     r13, [r15+4C0h]
0x10049f619  mov     word ptr [rsp+58h+arg_18], r9w
0x10049f61f  cmp     [rsp+58h+arg_20], bl
0x10049f626  jnz     short loc_10049F640
0x10049f628  lea     eax, [r12+1]
0x10049f62d  mov     [rsp+58h+arg_18], eax
0x10049f631  cmp     ax, [r15+8]
0x10049f636  jnz     short loc_10049F640
0x10049f638  mov     [rsp+58h+arg_18], ebx
0x10049f63c  nop     dword ptr [rax+00h]
0x10049f640  movzx   eax, r12w
0x10049f644  lea     r14, [r15+500h]
0x10049f64b  lea     rcx, [rax+rax*2]
0x10049f64f  shl     rcx, 6
0x10049f653  add     r14, rcx
0x10049f656  xor     esi, esi
0x10049f658  lea     r12d, [rsi+2]
0x10049f65c  nop     dword ptr [rax+00h]
0x10049f660  cmp     esi, 5
0x10049f663  jnb     loc_10049F772
0x10049f669  movsxd  rbp, esi
0x10049f66c  xor     ebx, ebx
0x10049f66e  shl     rbp, 4
0x10049f672  add     rbp, r14
0x10049f675  mov     rcx, rbp; ListHead
0x10049f678  call    cs:__imp_InterlockedPopEntrySList
0x10049f67e  test    rax, rax
0x10049f681  jz      short loc_10049F687
0x10049f683  lea     rbx, [rax-10h]
0x10049f687  test    rbx, rbx
0x10049f68a  jz      loc_10049F767
0x10049f690  mov     eax, 2FA0BE83h
0x10049f695  mul     dword ptr [rbx+28h]
0x10049f698  mov     ecx, edx
0x10049f69a  shr     ecx, 3
0x10049f69d  cmp     ecx, esi
0x10049f69f  jle     short loc_10049F6D3
0x10049f6a1  lfence
0x10049f6a4  shl     rcx, 4
0x10049f6a8  lea     rdx, [rbx+10h]; ListEntry
0x10049f6ac  add     rcx, r14; ListHead
0x10049f6af  call    cs:__imp_InterlockedPushEntrySList
0x10049f6b5  mov     rcx, rbp; ListHead
0x10049f6b8  xor     ebx, ebx
0x10049f6ba  call    cs:__imp_InterlockedPopEntrySList
0x10049f6c0  test    rax, rax
0x10049f6c3  jz      short loc_10049F6C9
0x10049f6c5  lea     rbx, [rax-10h]
0x10049f6c9  test    rbx, rbx
0x10049f6cc  jnz     short loc_10049F690
0x10049f6ce  jmp     loc_10049F767
0x10049f6d3  mov     dword ptr [rbx+30h], 0
0x10049f6da  mov     rax, rdi
0x10049f6dd  lock cmpxchg [r13+8], rbx
0x10049f6e3  jz      short loc_10049F70A
0x10049f6e5  mov     eax, 2FA0BE83h
0x10049f6ea  mov     [rbx+30h], r12d
0x10049f6ee  mul     dword ptr [rbx+28h]
0x10049f6f1  movzx   eax, word ptr [rbx+2Ch]
0x10049f6f5  shr     edx, 3
0x10049f6f8  lea     rcx, [rax+0Ah]
0x10049f6fc  lea     rcx, [rax+rcx*2]
0x10049f700  lea     rcx, [rdx+rcx*4]
0x10049f704  lea     rdx, [rbx+10h]
0x10049f708  jmp     short loc_10049F75A
0x10049f70a  test    rdi, rdi
0x10049f70d  jz      short loc_10049F767
0x10049f70f  mov     eax, [rdi+28h]
0x10049f712  test    eax, eax
0x10049f714  jnz     short loc_10049F737
0x10049f716  mov     dword ptr [rdi+30h], 1
0x10049f71d  lock or [rsp+58h+var_58], eax
0x10049f721  mov     eax, [rdi+28h]
0x10049f724  test    eax, eax
0x10049f726  jz      short loc_10049F767
0x10049f728  mov     eax, 1
0x10049f72d  lock cmpxchg [rdi+30h], r12d
0x10049f733  jnz     short loc_10049F767
0x10049f735  jmp     short loc_10049F73B
0x10049f737  mov     [rdi+30h], r12d
0x10049f73b  mov     eax, 2FA0BE83h
0x10049f740  mul     dword ptr [rdi+28h]
0x10049f743  movzx   eax, word ptr [rdi+2Ch]
0x10049f747  shr     edx, 3
0x10049f74a  lea     rcx, [rax+0Ah]
0x10049f74e  lea     rcx, [rax+rcx*2]
0x10049f752  lea     rcx, [rdx+rcx*4]
0x10049f756  lea     rdx, [rdi+10h]; ListEntry
0x10049f75a  shl     rcx, 4
0x10049f75e  add     rcx, r15; ListHead
0x10049f761  call    cs:__imp_InterlockedPushEntrySList
0x10049f767  inc     esi
0x10049f769  test    rbx, rbx
0x10049f76c  jz      loc_10049F660
0x10049f772  mov     eax, [rsp+58h+arg_10]
0x10049f776  xor     r12d, r12d
0x10049f779  inc     ax
0x10049f77c  cmp     ax, [r15+8]
0x10049f781  cmovnz  r12w, ax
0x10049f786  mov     [rsp+58h+arg_10], r12d
0x10049f78b  test    rbx, rbx
0x10049f78e  jnz     short loc_10049F79F
0x10049f790  cmp     r12w, word ptr [rsp+58h+arg_18]
0x10049f796  jnz     loc_10049F640
0x10049f79c  test    rbx, rbx
0x10049f79f  mov     rbx, [rsp+58h+arg_0]
0x10049f7a4  setnz   al
0x10049f7a7  add     rsp, 20h
0x10049f7ab  pop     r15
0x10049f7ad  pop     r14
0x10049f7af  pop     r13
0x10049f7b1  pop     r12
0x10049f7b3  pop     rdi
0x10049f7b4  pop     rsi
0x10049f7b5  pop     rbp
0x10049f7b6  retn
```
