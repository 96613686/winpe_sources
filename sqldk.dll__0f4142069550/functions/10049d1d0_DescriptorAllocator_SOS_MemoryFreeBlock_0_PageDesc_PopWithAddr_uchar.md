# DescriptorAllocator<SOS_MemoryFreeBlock,0>::PageDesc::PopWithAddr(uchar *)

- ea: `0x10049d1d0`
- end: `0x10049d385`
- name: `?PopWithAddr@PageDesc@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@QEAAPEAVSOS_MemoryFreeBlock@@PEAE@Z`
- size: `437`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10049c560`
- `0x1004a8200`

## callees

- `0x10049d1d0`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x10049d261`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049d323`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049d261`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049d323`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049d28d`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049d2ca`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049d28d`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049d2ca`

## pseudocode

```c
PSLIST_ENTRY __fastcall DescriptorAllocator<SOS_MemoryFreeBlock,0>::PageDesc::PopWithAddr(
        PSLIST_HEADER ListHead,
        struct _SLIST_ENTRY *a2)
{
  PSLIST_ENTRY v4; // rsi
  ULONGLONG Region; // rdx
  signed __int64 v6; // rcx
  struct _SLIST_ENTRY *v8; // rbx
  struct _SLIST_ENTRY *v9; // rax
  struct _SLIST_ENTRY *v10; // rdx
  PSLIST_ENTRY v11; // rax
  struct _SLIST_ENTRY *v12; // r8
  struct _SLIST_ENTRY *v13; // rax
  struct _SLIST_ENTRY *Next; // rcx
  struct _SLIST_ENTRY *v15; // r8
  struct _SLIST_ENTRY *v16; // rax
  struct _SLIST_ENTRY *v17; // rcx
  struct _SLIST_ENTRY *v18; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  if ( a2 >= (struct _SLIST_ENTRY *)&ListHead[-508] && a2 < (struct _SLIST_ENTRY *)&ListHead[4] )
  {
    Region = ListHead[1].Region;
    if ( Region && (unsigned __int64)a2 >= Region )
    {
      while ( 1 )
      {
        v4 = 0;
        if ( (unsigned __int64)a2 < Region || Region >= (unsigned __int64)ListHead )
          break;
        _mm_lfence();
        v6 = 0;
        if ( (PSLIST_HEADER)(Region + 64) != ListHead )
          v6 = Region + 64;
        if ( Region == _InterlockedCompareExchange64((volatile signed __int64 *)&ListHead[1].Region, v6, Region) )
        {
          _mm_lfence();
          _InterlockedDecrement((volatile signed __int32 *)&ListHead[2].HeaderX64 + 2);
          v4 = (PSLIST_ENTRY)Region;
          if ( (struct _SLIST_ENTRY *)Region == a2 )
            return v4;
          _mm_lfence();
          _InterlockedIncrement((volatile signed __int32 *)&ListHead[2].HeaderX64 + 2);
          InterlockedPushEntrySList(ListHead, (PSLIST_ENTRY)Region);
        }
        Region = ListHead[1].Region;
        if ( !Region )
          return 0;
      }
    }
    else
    {
      v8 = 0;
      v18 = 0;
      v4 = InterlockedPopEntrySList(ListHead);
      if ( v4 )
      {
        v9 = 0;
        do
        {
          v10 = v9;
          if ( v4 == a2 )
            break;
          v4->Next = v8;
          v8 = v4;
          v4 = 0;
          v11 = InterlockedPopEntrySList(ListHead);
          v10 = v8;
          if ( v11 )
            v4 = v11;
          v9 = v8;
        }
        while ( v4 );
        v18 = v8;
        if ( v10 )
        {
          v12 = (struct _SLIST_ENTRY *)&v18;
          v13 = v10;
          while ( 1 )
          {
            Next = v13->Next;
            if ( v13 == v10 )
              break;
            v12 = v13;
            v13 = v13->Next;
            if ( !Next )
              goto LABEL_26;
          }
          v12->Next = Next;
          v8 = v18;
          v13->Next = 0;
          do
          {
LABEL_26:
            InterlockedPushEntrySList(ListHead, v10);
            v10 = v8;
            if ( v8 )
            {
              v15 = (struct _SLIST_ENTRY *)&v18;
              v16 = v8;
              while ( 1 )
              {
                v17 = v16->Next;
                if ( v16 == v8 )
                  break;
                v15 = v16;
                v16 = v16->Next;
                if ( !v17 )
                  goto LABEL_32;
              }
              v15->Next = v17;
              v8 = v18;
              v16->Next = 0;
            }
LABEL_32:
            ;
          }
          while ( v10 );
        }
        if ( v4 )
          _InterlockedDecrement((volatile signed __int32 *)&ListHead[2].HeaderX64 + 2);
      }
      else
      {
        return 0;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x10049d1d0  push    rbp
0x10049d1d2  push    rsi
0x10049d1d3  push    rdi
0x10049d1d4  push    r12
0x10049d1d6  sub     rsp, 28h
0x10049d1da  xor     r12d, r12d
0x10049d1dd  lea     rax, [rcx-1FC0h]
0x10049d1e4  mov     rbp, rdx
0x10049d1e7  mov     rdi, rcx
0x10049d1ea  mov     esi, r12d
0x10049d1ed  cmp     rdx, rax
0x10049d1f0  jb      loc_10049D378
0x10049d1f6  add     rax, 2000h
0x10049d1fc  cmp     rdx, rax
0x10049d1ff  jnb     loc_10049D378
0x10049d205  mov     rdx, [rcx+18h]; ListEntry
0x10049d209  test    rdx, rdx
0x10049d20c  jz      short loc_10049D280
0x10049d20e  cmp     rbp, rdx
0x10049d211  jb      short loc_10049D280
0x10049d213  mov     rsi, r12
0x10049d216  cmp     rbp, rdx
0x10049d219  jb      loc_10049D378
0x10049d21f  cmp     rdx, rdi
0x10049d222  jnb     loc_10049D378
0x10049d228  lfence
0x10049d22b  lea     rax, [rdx+40h]
0x10049d22f  mov     rcx, r12
0x10049d232  cmp     rax, rdi
0x10049d235  cmovnz  rcx, rax
0x10049d239  mov     rax, rdx
0x10049d23c  lock cmpxchg [rdi+18h], rcx
0x10049d242  jnz     short loc_10049D267
0x10049d244  lfence
0x10049d247  lock dec dword ptr [rdi+28h]
0x10049d24b  mov     rsi, rdx
0x10049d24e  cmp     rdx, rbp
0x10049d251  jz      loc_10049D378
0x10049d257  lfence
0x10049d25a  lock inc dword ptr [rdi+28h]
0x10049d25e  mov     rcx, rdi; ListHead
0x10049d261  call    cs:__imp_InterlockedPushEntrySList
0x10049d267  mov     rdx, [rdi+18h]
0x10049d26b  test    rdx, rdx
0x10049d26e  jnz     short loc_10049D213
0x10049d270  mov     rsi, r12
0x10049d273  mov     rax, r12
0x10049d276  add     rsp, 28h
0x10049d27a  pop     r12
0x10049d27c  pop     rdi
0x10049d27d  pop     rsi
0x10049d27e  pop     rbp
0x10049d27f  retn
0x10049d280  mov     [rsp+48h+arg_8], rbx
0x10049d285  mov     rbx, r12
0x10049d288  mov     [rsp+48h+arg_0], rbx
0x10049d28d  call    cs:__imp_InterlockedPopEntrySList
0x10049d293  mov     rsi, rax
0x10049d296  test    rax, rax
0x10049d299  jz      loc_10049D370
0x10049d29f  mov     [rsp+48h+arg_10], r14
0x10049d2a4  mov     rax, r12
0x10049d2a7  mov     [rsp+48h+var_28], r15
0x10049d2ac  nop     dword ptr [rax]
0x10049d2af  nop
0x10049d2b0  mov     r14, rsi
0x10049d2b3  mov     r15, rsi
0x10049d2b6  mov     rdx, rax
0x10049d2b9  cmp     rsi, rbp
0x10049d2bc  jz      short loc_10049D2E2
0x10049d2be  mov     [rsi], rbx
0x10049d2c1  mov     rcx, rdi; ListHead
0x10049d2c4  mov     rbx, rsi
0x10049d2c7  mov     rsi, r12
0x10049d2ca  call    cs:__imp_InterlockedPopEntrySList
0x10049d2d0  test    rax, rax
0x10049d2d3  mov     rdx, rbx; ListEntry
0x10049d2d6  cmovnz  rsi, rax
0x10049d2da  mov     rax, rbx
0x10049d2dd  test    rsi, rsi
0x10049d2e0  jnz     short loc_10049D2B0
0x10049d2e2  mov     r15, [rsp+48h+var_28]
0x10049d2e7  mov     r14, [rsp+48h+arg_10]
0x10049d2ec  mov     [rsp+48h+arg_0], rbx
0x10049d2f1  test    rdx, rdx
0x10049d2f4  jz      short loc_10049D365
0x10049d2f6  lea     r8, [rsp+48h+arg_0]
0x10049d2fb  mov     rax, rdx
0x10049d2fe  xchg    ax, ax
0x10049d300  mov     rcx, [rax]
0x10049d303  cmp     rax, rdx
0x10049d306  jz      short loc_10049D315
0x10049d308  mov     r8, rax
0x10049d30b  mov     rax, rcx
0x10049d30e  test    rcx, rcx
0x10049d311  jnz     short loc_10049D300
0x10049d313  jmp     short loc_10049D320
0x10049d315  mov     [r8], rcx
0x10049d318  mov     rbx, [rsp+48h+arg_0]
0x10049d31d  mov     [rax], r12
0x10049d320  mov     rcx, rdi; ListHead
0x10049d323  call    cs:__imp_InterlockedPushEntrySList
0x10049d329  mov     rdx, rbx
0x10049d32c  test    rbx, rbx
0x10049d32f  jz      short loc_10049D360
0x10049d331  lea     r8, [rsp+48h+arg_0]
0x10049d336  mov     rax, rbx
0x10049d339  nop     dword ptr [rax+00000000h]
0x10049d340  mov     rcx, [rax]
0x10049d343  cmp     rax, rbx
0x10049d346  jz      short loc_10049D355
0x10049d348  mov     r8, rax
0x10049d34b  mov     rax, rcx
0x10049d34e  test    rcx, rcx
0x10049d351  jnz     short loc_10049D340
0x10049d353  jmp     short loc_10049D360
0x10049d355  mov     [r8], rcx
0x10049d358  mov     rbx, [rsp+48h+arg_0]
0x10049d35d  mov     [rax], r12
0x10049d360  test    rdx, rdx
0x10049d363  jnz     short loc_10049D320
0x10049d365  test    rsi, rsi
0x10049d368  jz      short loc_10049D373
0x10049d36a  lock dec dword ptr [rdi+28h]
0x10049d36e  jmp     short loc_10049D373
0x10049d370  mov     rsi, r12
0x10049d373  mov     rbx, [rsp+48h+arg_8]
0x10049d378  mov     rax, rsi
0x10049d37b  add     rsp, 28h
0x10049d37f  pop     r12
0x10049d381  pop     rdi
0x10049d382  pop     rsi
0x10049d383  pop     rbp
0x10049d384  retn
```
