# DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallPartialPageAsActive(DescriptorAllocator<SOS_MemoryFreeBlock,0>::PageDesc *,uint,ushort,bool)

- ea: `0x100432f40`
- end: `0x100432f9c`
- name: `?InstallPartialPageAsActive@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@AEAA_NPEAUPageDesc@1@IG_N@Z`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1004325b0`
- `0x1004a7c90`

## callees

- `0x100432f40`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x10042e0a5`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049bcbe`
- `KERNEL32!InterlockedPushEntrySList` at `0x10042e0a5`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049bcbe`
- `KERNEL32!InterlockedPopEntrySList` at `0x10042e0b0`
- `KERNEL32!InterlockedPopEntrySList` at `0x100432fd4`
- `KERNEL32!InterlockedPopEntrySList` at `0x10042e0b0`
- `KERNEL32!InterlockedPopEntrySList` at `0x100432fd4`

## pseudocode

```c
bool __fastcall DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallPartialPageAsActive(
        __int64 a1,
        signed __int64 a2,
        unsigned int a3,
        unsigned __int16 a4,
        char a5)
{
  signed int v5; // eax
  PSLIST_ENTRY v6; // rax
  struct _SLIST_ENTRY *v7; // rdx
  unsigned __int64 v8; // rcx
  signed __int64 v10; // rbx
  unsigned __int16 v11; // r12
  unsigned __int64 v13; // r13
  __int64 v14; // r14
  signed int v15; // esi
  PSLIST_ENTRY v16; // rax
  bool v17; // zf
  signed __int32 v19[22]; // [rsp+0h] [rbp-58h] BYREF
  unsigned __int16 v20; // [rsp+70h] [rbp+18h]
  unsigned __int16 v21; // [rsp+78h] [rbp+20h]

  v10 = 0;
  v11 = a4;
  v20 = a4;
  v13 = *(_QWORD *)(a1 + 1216) + ((unsigned __int64)a3 << *(_BYTE *)(a1 + 1228));
  v21 = a4;
  if ( !a5 )
  {
    if ( a4 + 1 != *(_WORD *)(a1 + 8) )
      JUMPOUT(0x100432F9CLL);
    v21 = 0;
  }
  while ( 2 )
  {
    v14 = 192LL * v11 + a1 + 1280;
    v15 = 0;
    while ( (unsigned int)v15 < 5 )
    {
      v10 = 0;
      v16 = InterlockedPopEntrySList((PSLIST_HEADER)(v14 + 16LL * v15));
      if ( v16 )
        v10 = (signed __int64)&v16[-1];
      if ( !v10 )
        goto LABEL_20;
      while ( 1 )
      {
        v5 = *(_DWORD *)(v10 + 40) >> 5;
        if ( v5 <= v15 )
          break;
        _mm_lfence();
        InterlockedPushEntrySList((PSLIST_HEADER)(v14 + 16LL * (unsigned int)v5), (PSLIST_ENTRY)(v10 + 16));
        v10 = 0;
        v6 = InterlockedPopEntrySList((PSLIST_HEADER)(v14 + 16LL * v15));
        if ( v6 )
          v10 = (signed __int64)&v6[-1];
        if ( !v10 )
          goto LABEL_20;
      }
      *(_DWORD *)(v10 + 48) = 0;
      if ( a2 != _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 8), v10, a2) )
      {
        *(_DWORD *)(v10 + 48) = 2;
        v7 = (struct _SLIST_ENTRY *)(v10 + 16);
        v8 = ((unsigned __int64)*(unsigned int *)(v10 + 40) >> 5)
           + 4 * (*(unsigned __int16 *)(v10 + 44) + 2 * (*(unsigned __int16 *)(v10 + 44) + 10LL));
LABEL_29:
        InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 16 * v8), v7);
        goto LABEL_20;
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
            goto LABEL_20;
        }
        v7 = (struct _SLIST_ENTRY *)(a2 + 16);
        v8 = ((unsigned __int64)*(unsigned int *)(a2 + 40) >> 5) + 4 * (3LL * *(unsigned __int16 *)(a2 + 44) + 20);
        goto LABEL_29;
      }
LABEL_20:
      ++v15;
      if ( v10 )
        break;
    }
    v11 = 0;
    if ( v20 + 1 != *(_WORD *)(a1 + 8) )
      v11 = v20 + 1;
    v20 = v11;
    v17 = v10 == 0;
    if ( !v10 )
    {
      if ( v11 == v21 )
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
0x100432f40  mov     [rsp+arg_0], rbx
0x100432f45  push    rbp
0x100432f46  push    rsi
0x100432f47  push    rdi
0x100432f48  push    r12
0x100432f4a  push    r13
0x100432f4c  push    r14
0x100432f4e  push    r15
0x100432f50  sub     rsp, 20h
0x100432f54  mov     r15, rcx
0x100432f57  mov     r13d, r8d
0x100432f5a  movzx   ecx, byte ptr [rcx+4CCh]
0x100432f61  xor     ebx, ebx
0x100432f63  shl     r13, cl
0x100432f66  movzx   r12d, r9w
0x100432f6a  mov     [rsp+58h+arg_10], r12d
0x100432f6f  mov     rdi, rdx
0x100432f72  add     r13, [r15+4C0h]
0x100432f79  mov     word ptr [rsp+58h+arg_18], r9w
0x100432f7f  cmp     [rsp+58h+arg_20], bl
0x100432f86  jnz     short loc_100432FA0
0x100432f88  lea     eax, [r12+1]
0x100432f8d  mov     [rsp+58h+arg_18], eax
0x100432f91  cmp     ax, [r15+8]
0x100432f96  jz      loc_10049BC8A
0x10042e081  lea     rbx, [rax-10h]
0x10042e085  jmp     loc_100432FE3
0x10042e08b  mov     eax, [rbx+28h]
0x10042e08e  shr     eax, 5
0x10042e091  cmp     eax, esi
0x10042e093  jle     short loc_10042E0C9
0x10042e095  lfence
0x10042e098  mov     ecx, eax
0x10042e09a  lea     rdx, [rbx+10h]; ListEntry
0x10042e09e  shl     rcx, 4
0x10042e0a2  add     rcx, r14; ListHead
0x10042e0a5  call    cs:__imp_InterlockedPushEntrySList
0x10042e0ab  mov     rcx, rbp; ListHead
0x10042e0ae  xor     ebx, ebx
0x10042e0b0  call    cs:__imp_InterlockedPopEntrySList
0x10042e0b6  test    rax, rax
0x10042e0b9  jz      short loc_10042E0BF
0x10042e0bb  lea     rbx, [rax-10h]
0x10042e0bf  test    rbx, rbx
0x10042e0c2  jnz     short loc_10042E08B
0x10042e0c4  jmp     loc_100432FEC
0x10042e0c9  mov     dword ptr [rbx+30h], 0
0x10042e0d0  mov     rax, rdi
0x10042e0d3  lock cmpxchg [r13+8], rbx
0x10042e0d9  jnz     loc_10049BC94
0x10042e0df  test    rdi, rdi
0x10042e0e2  jz      loc_100432FEC
0x10042e0e8  mov     eax, [rdi+28h]
0x10042e0eb  test    eax, eax
0x10042e0ed  jnz     loc_10049BCCB
0x10042e0f3  mov     dword ptr [rdi+30h], 1
0x10042e0fa  lock or [rsp+58h+var_58], eax
0x10042e0fe  mov     eax, [rdi+28h]
0x10042e101  test    eax, eax
0x10042e103  jz      loc_100432FEC
0x10042e109  mov     eax, 1
0x10042e10e  lock cmpxchg [rdi+30h], r12d
0x10042e114  jnz     loc_100432FEC
0x10042e11a  jmp     short loc_10042E11D
0x10042e11d  movzx   eax, word ptr [rdi+2Ch]
0x10042e121  lea     rdx, [rdi+10h]; ListEntry
0x10042e125  lea     rcx, [rax+rax*2]
0x10042e129  mov     eax, [rdi+28h]
0x10042e12c  shr     rax, 5
0x10042e130  lea     rcx, [rcx+14h]
0x10042e134  lea     rcx, [rax+rcx*4]
0x10042e138  jmp     loc_10049BCB7
0x100432fa0  movzx   eax, r12w
0x100432fa4  lea     r14, [r15+500h]
0x100432fab  lea     rcx, [rax+rax*2]
0x100432faf  shl     rcx, 6
0x100432fb3  add     r14, rcx
0x100432fb6  xor     esi, esi
0x100432fb8  lea     r12d, [rsi+2]
0x100432fbc  nop     dword ptr [rax+00h]
0x100432fc0  cmp     esi, 5
0x100432fc3  jnb     short loc_100432FF3
0x100432fc5  movsxd  rbp, esi
0x100432fc8  xor     ebx, ebx
0x100432fca  shl     rbp, 4
0x100432fce  add     rbp, r14
0x100432fd1  mov     rcx, rbp; ListHead
0x100432fd4  call    cs:__imp_InterlockedPopEntrySList
0x100432fda  test    rax, rax
0x100432fdd  jnz     loc_10042E081
0x100432fe3  test    rbx, rbx
0x100432fe6  jnz     loc_10042E08B
0x100432fec  inc     esi
0x100432fee  test    rbx, rbx
0x100432ff1  jz      short loc_100432FC0
0x100432ff3  mov     eax, [rsp+58h+arg_10]
0x100432ff7  xor     r12d, r12d
0x100432ffa  inc     ax
0x100432ffd  cmp     ax, [r15+8]
0x100433002  cmovnz  r12w, ax
0x100433007  mov     [rsp+58h+arg_10], r12d
0x10043300c  test    rbx, rbx
0x10043300f  jnz     short loc_10043301C
0x100433011  cmp     r12w, word ptr [rsp+58h+arg_18]
0x100433017  jnz     short loc_100432FA0
0x100433019  test    rbx, rbx
0x10043301c  mov     rbx, [rsp+58h+arg_0]
0x100433021  setnz   al
0x100433024  add     rsp, 20h
0x100433028  pop     r15
0x10043302a  pop     r14
0x10043302c  pop     r13
0x10043302e  pop     r12
0x100433030  pop     rdi
0x100433031  pop     rsi
0x100433032  pop     rbp
0x100433033  retn
0x10049bc8a  mov     [rsp+58h+arg_18], ebx
0x10049bc8e  jmp     loc_100432FA0
0x10049bc94  mov     [rbx+30h], r12d
0x10049bc98  lea     rdx, [rbx+10h]
0x10049bc9c  movzx   eax, word ptr [rbx+2Ch]
0x10049bca0  mov     r8d, [rbx+28h]
0x10049bca4  shr     r8, 5
0x10049bca8  lea     rcx, [rax+0Ah]
0x10049bcac  lea     rcx, [rax+rcx*2]
0x10049bcb0  lea     rcx, [r8+rcx*4]
0x10049bcb4  jmp     short loc_10049BCB7
0x10049bcb7  shl     rcx, 4
0x10049bcbb  add     rcx, r15; ListHead
0x10049bcbe  call    cs:__imp_InterlockedPushEntrySList
0x10049bcc4  nop
0x10049bcc5  jmp     loc_100432FEC
0x10049bccb  mov     [rdi+30h], r12d
0x10049bccf  jmp     loc_10042E11D
```
