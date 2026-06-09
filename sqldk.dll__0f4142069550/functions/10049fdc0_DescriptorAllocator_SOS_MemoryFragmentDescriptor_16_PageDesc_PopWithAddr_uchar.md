# DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::PageDesc::PopWithAddr(uchar *)

- ea: `0x10049fdc0`
- end: `0x10049ff8a`
- name: `?PopWithAddr@PageDesc@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@QEAAPEAVSOS_MemoryFragmentDescriptor@@PEAE@Z`
- size: `458`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10049fc80`

## callees

- `0x10049fdc0`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x10049fe38`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049ff17`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049fe38`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049ff17`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049fe7b`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049fea7`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049fe7b`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049fea7`

## pseudocode

```c
ULONGLONG __fastcall DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::PageDesc::PopWithAddr(
        PSLIST_HEADER ListHead,
        ULONGLONG a2)
{
  ULONGLONG Region; // rdx
  signed __int64 v5; // rcx
  ULONGLONG result; // rax
  struct _SLIST_ENTRY *v7; // rbx
  __int64 v8; // rbp
  PSLIST_ENTRY v9; // rax
  struct _SLIST_ENTRY *v10; // rdi
  PSLIST_ENTRY v11; // rax
  struct _SLIST_ENTRY *v12; // rdx
  struct _SLIST_ENTRY *v13; // rcx
  struct _SLIST_ENTRY *Next; // rax
  struct _SLIST_ENTRY *v15; // r8
  struct _SLIST_ENTRY *v16; // rax
  struct _SLIST_ENTRY *v17; // rcx
  struct _SLIST_ENTRY *v18; // [rsp+40h] [rbp+8h] BYREF

  if ( a2 < (unsigned __int64)&ListHead[-507] || a2 >= (unsigned __int64)&ListHead[5] )
    return 0;
  Region = ListHead[1].Region;
  if ( Region && a2 >= Region )
  {
    while ( a2 >= Region && Region < (unsigned __int64)ListHead )
    {
      _mm_lfence();
      v5 = 0;
      if ( (PSLIST_HEADER)(Region + 48) != ListHead )
        v5 = Region + 48;
      if ( Region == _InterlockedCompareExchange64((volatile signed __int64 *)&ListHead[1].Region, v5, Region) )
      {
        _mm_lfence();
        _InterlockedDecrement((volatile signed __int32 *)&ListHead[2].HeaderX64 + 2);
        if ( Region == a2 )
          return Region;
        _mm_lfence();
        _InterlockedIncrement((volatile signed __int32 *)&ListHead[2].HeaderX64 + 2);
        InterlockedPushEntrySList(ListHead, (PSLIST_ENTRY)(Region + 16));
      }
      Region = ListHead[1].Region;
      if ( !Region )
        return 0;
    }
    return 0;
  }
  v7 = 0;
  v8 = 0;
  v18 = 0;
  v9 = InterlockedPopEntrySList(ListHead);
  if ( v9 )
    v8 = (__int64)&v9[-1];
  v10 = 0;
  if ( v8 )
  {
    do
    {
      if ( v8 == a2 )
        break;
      v10 = (struct _SLIST_ENTRY *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = v7;
      v8 = 0;
      v7 = v10;
      v11 = InterlockedPopEntrySList(ListHead);
      if ( v11 )
        v8 = (__int64)&v11[-1];
    }
    while ( v8 );
    v18 = v7;
  }
  v12 = v10 - 1;
  if ( !v10 )
    v12 = 0;
  if ( v12 )
  {
    v13 = (struct _SLIST_ENTRY *)&v18;
    if ( v10 )
    {
      while ( 1 )
      {
        Next = v10->Next;
        if ( v10 == &v12[1] )
          break;
        v13 = v10;
        v10 = v10->Next;
        if ( !Next )
          goto LABEL_31;
      }
      v13->Next = Next;
      v7 = v18;
      v10->Next = 0;
    }
    while ( 1 )
    {
LABEL_31:
      InterlockedPushEntrySList(ListHead, v12 + 1);
      v12 = v7 - 1;
      if ( !v7 )
        v12 = 0;
      if ( !v12 )
        break;
      v15 = (struct _SLIST_ENTRY *)&v18;
      if ( v7 )
      {
        v16 = v7;
        while ( 1 )
        {
          v17 = v16->Next;
          if ( v16 == &v12[1] )
            break;
          v15 = v16;
          v16 = v16->Next;
          if ( !v17 )
            goto LABEL_31;
        }
        v15->Next = v17;
        v7 = v18;
        v16->Next = 0;
      }
    }
  }
  result = v8;
  if ( v8 )
    _InterlockedDecrement((volatile signed __int32 *)&ListHead[2].HeaderX64 + 2);
  return result;
}

```

## disassembly

```asm
0x10049fdc0  push    rsi
0x10049fdc2  push    r14
0x10049fdc4  push    r15
0x10049fdc6  sub     rsp, 20h
0x10049fdca  xor     r15d, r15d
0x10049fdcd  lea     rax, [rcx-1FB0h]
0x10049fdd4  mov     r14, rdx
0x10049fdd7  mov     rsi, rcx
0x10049fdda  cmp     rdx, rax
0x10049fddd  jb      short loc_10049FE47
0x10049fddf  add     rax, 2000h
0x10049fde5  cmp     rdx, rax
0x10049fde8  jnb     short loc_10049FE47
0x10049fdea  mov     rdx, [rcx+18h]
0x10049fdee  test    rdx, rdx
0x10049fdf1  jz      short loc_10049FE61
0x10049fdf3  cmp     r14, rdx
0x10049fdf6  jb      short loc_10049FE61
0x10049fdf8  cmp     r14, rdx
0x10049fdfb  jb      short loc_10049FE47
0x10049fdfd  cmp     rdx, rsi
0x10049fe00  jnb     short loc_10049FE47
0x10049fe02  lfence
0x10049fe05  lea     rax, [rdx+30h]
0x10049fe09  mov     rcx, r15
0x10049fe0c  cmp     rax, rsi
0x10049fe0f  cmovnz  rcx, rax
0x10049fe13  mov     rax, rdx
0x10049fe16  lock cmpxchg [rsi+18h], rcx
0x10049fe1c  jnz     short loc_10049FE3E
0x10049fe1e  lfence
0x10049fe21  lock dec dword ptr [rsi+28h]
0x10049fe25  cmp     rdx, r14
0x10049fe28  jz      short loc_10049FE54
0x10049fe2a  lfence
0x10049fe2d  lock inc dword ptr [rsi+28h]
0x10049fe31  add     rdx, 10h; ListEntry
0x10049fe35  mov     rcx, rsi; ListHead
0x10049fe38  call    cs:__imp_InterlockedPushEntrySList
0x10049fe3e  mov     rdx, [rsi+18h]
0x10049fe42  test    rdx, rdx
0x10049fe45  jnz     short loc_10049FDF8
0x10049fe47  mov     rax, r15
0x10049fe4a  add     rsp, 20h
0x10049fe4e  pop     r15
0x10049fe50  pop     r14
0x10049fe52  pop     rsi
0x10049fe53  retn
0x10049fe54  mov     rax, rdx
0x10049fe57  add     rsp, 20h
0x10049fe5b  pop     r15
0x10049fe5d  pop     r14
0x10049fe5f  pop     rsi
0x10049fe60  retn
0x10049fe61  mov     [rsp+38h+arg_8], rbx
0x10049fe66  mov     rbx, r15
0x10049fe69  mov     [rsp+38h+arg_10], rbp
0x10049fe6e  mov     rbp, r15
0x10049fe71  mov     [rsp+38h+arg_0], rbx
0x10049fe76  mov     [rsp+38h+arg_18], rdi
0x10049fe7b  call    cs:__imp_InterlockedPopEntrySList
0x10049fe81  test    rax, rax
0x10049fe84  jz      short loc_10049FE8A
0x10049fe86  lea     rbp, [rax-10h]
0x10049fe8a  mov     rdi, r15
0x10049fe8d  test    rbp, rbp
0x10049fe90  jz      short loc_10049FEC0
0x10049fe92  cmp     rbp, r14
0x10049fe95  jz      short loc_10049FEBB
0x10049fe97  lea     rdi, [rbp+10h]
0x10049fe9b  mov     rcx, rsi; ListHead
0x10049fe9e  mov     [rdi], rbx
0x10049fea1  mov     rbp, r15
0x10049fea4  mov     rbx, rdi
0x10049fea7  call    cs:__imp_InterlockedPopEntrySList
0x10049fead  test    rax, rax
0x10049feb0  jz      short loc_10049FEB6
0x10049feb2  lea     rbp, [rax-10h]
0x10049feb6  test    rbp, rbp
0x10049feb9  jnz     short loc_10049FE92
0x10049febb  mov     [rsp+38h+arg_0], rbx
0x10049fec0  test    rdi, rdi
0x10049fec3  lea     rdx, [rdi-10h]
0x10049fec7  cmovz   rdx, r15
0x10049fecb  test    rdx, rdx
0x10049fece  jz      loc_10049FF65
0x10049fed4  lea     rcx, [rsp+38h+arg_0]
0x10049fed9  test    rdi, rdi
0x10049fedc  jz      short loc_10049FF04
0x10049fede  lea     r8, [rdx+10h]
0x10049fee2  mov     rax, [rdi]
0x10049fee5  cmp     rdi, r8
0x10049fee8  jz      short loc_10049FEF7
0x10049feea  mov     rcx, rdi
0x10049feed  mov     rdi, rax
0x10049fef0  test    rax, rax
0x10049fef3  jnz     short loc_10049FEE2
0x10049fef5  jmp     short loc_10049FF10
0x10049fef7  mov     [rcx], rax
0x10049fefa  mov     rbx, [rsp+38h+arg_0]
0x10049feff  mov     [rdi], r15
0x10049ff02  jmp     short loc_10049FF10
0x10049ff04  test    rdx, rdx
0x10049ff07  jz      short loc_10049FF65
0x10049ff09  nop     dword ptr [rax]
0x10049ff0c  nop     dword ptr [rax+00h]
0x10049ff10  add     rdx, 10h; ListEntry
0x10049ff14  mov     rcx, rsi; ListHead
0x10049ff17  call    cs:__imp_InterlockedPushEntrySList
0x10049ff1d  test    rbx, rbx
0x10049ff20  lea     rdx, [rbx-10h]
0x10049ff24  cmovz   rdx, r15
0x10049ff28  test    rdx, rdx
0x10049ff2b  jz      short loc_10049FF65
0x10049ff2d  lea     r8, [rsp+38h+arg_0]
0x10049ff32  test    rbx, rbx
0x10049ff35  jz      short loc_10049FF60
0x10049ff37  mov     rax, rbx
0x10049ff3a  lea     r9, [rdx+10h]
0x10049ff3e  xchg    ax, ax
0x10049ff40  mov     rcx, [rax]
0x10049ff43  cmp     rax, r9
0x10049ff46  jz      short loc_10049FF55
0x10049ff48  mov     r8, rax
0x10049ff4b  mov     rax, rcx
0x10049ff4e  test    rcx, rcx
0x10049ff51  jnz     short loc_10049FF40
0x10049ff53  jmp     short loc_10049FF60
0x10049ff55  mov     [r8], rcx
0x10049ff58  mov     rbx, [rsp+38h+arg_0]
0x10049ff5d  mov     [rax], r15
0x10049ff60  test    rdx, rdx
0x10049ff63  jnz     short loc_10049FF10
0x10049ff65  mov     rdi, [rsp+38h+arg_18]
0x10049ff6a  mov     rax, rbp
0x10049ff6d  mov     rbx, [rsp+38h+arg_8]
0x10049ff72  test    rbp, rbp
0x10049ff75  jz      short loc_10049FF7B
0x10049ff77  lock dec dword ptr [rsi+28h]
0x10049ff7b  mov     rbp, [rsp+38h+arg_10]
0x10049ff80  add     rsp, 20h
0x10049ff84  pop     r15
0x10049ff86  pop     r14
0x10049ff88  pop     rsi
0x10049ff89  retn
```
