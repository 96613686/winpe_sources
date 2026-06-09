# DescriptorAllocator<SOS_ParentBlockDescriptor,0>::PageDesc::PopWithAddr(uchar *)

- ea: `0x10049ce30`
- end: `0x10049cfe5`
- name: `?PopWithAddr@PageDesc@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAPEAVSOS_ParentBlockDescriptor@@PEAE@Z`
- size: `437`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10049c010`

## callees

- `0x10049ce30`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x10049cec4`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049cf83`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049cec4`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049cf83`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049cef0`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049cf2a`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049cef0`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049cf2a`

## pseudocode

```c
PSLIST_ENTRY __fastcall DescriptorAllocator<SOS_ParentBlockDescriptor,0>::PageDesc::PopWithAddr(
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
  if ( a2 >= (struct _SLIST_ENTRY *)&ListHead[-504] && a2 < (struct _SLIST_ENTRY *)&ListHead[8] )
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
        if ( (PSLIST_HEADER)(Region + 144) != ListHead )
          v6 = Region + 144;
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
0x10049ce30  push    rbp
0x10049ce32  push    rsi
0x10049ce33  push    rdi
0x10049ce34  push    r12
0x10049ce36  sub     rsp, 28h
0x10049ce3a  xor     r12d, r12d
0x10049ce3d  lea     rax, [rcx-1F80h]
0x10049ce44  mov     rbp, rdx
0x10049ce47  mov     rdi, rcx
0x10049ce4a  mov     esi, r12d
0x10049ce4d  cmp     rdx, rax
0x10049ce50  jb      loc_10049CFD8
0x10049ce56  add     rax, 2000h
0x10049ce5c  cmp     rdx, rax
0x10049ce5f  jnb     loc_10049CFD8
0x10049ce65  mov     rdx, [rcx+18h]; ListEntry
0x10049ce69  test    rdx, rdx
0x10049ce6c  jz      short loc_10049CEE3
0x10049ce6e  cmp     rbp, rdx
0x10049ce71  jb      short loc_10049CEE3
0x10049ce73  mov     rsi, r12
0x10049ce76  cmp     rbp, rdx
0x10049ce79  jb      loc_10049CFD8
0x10049ce7f  cmp     rdx, rdi
0x10049ce82  jnb     loc_10049CFD8
0x10049ce88  lfence
0x10049ce8b  lea     rax, [rdx+90h]
0x10049ce92  mov     rcx, r12
0x10049ce95  cmp     rax, rdi
0x10049ce98  cmovnz  rcx, rax
0x10049ce9c  mov     rax, rdx
0x10049ce9f  lock cmpxchg [rdi+18h], rcx
0x10049cea5  jnz     short loc_10049CECA
0x10049cea7  lfence
0x10049ceaa  lock dec dword ptr [rdi+28h]
0x10049ceae  mov     rsi, rdx
0x10049ceb1  cmp     rdx, rbp
0x10049ceb4  jz      loc_10049CFD8
0x10049ceba  lfence
0x10049cebd  lock inc dword ptr [rdi+28h]
0x10049cec1  mov     rcx, rdi; ListHead
0x10049cec4  call    cs:__imp_InterlockedPushEntrySList
0x10049ceca  mov     rdx, [rdi+18h]
0x10049cece  test    rdx, rdx
0x10049ced1  jnz     short loc_10049CE73
0x10049ced3  mov     rsi, r12
0x10049ced6  mov     rax, r12
0x10049ced9  add     rsp, 28h
0x10049cedd  pop     r12
0x10049cedf  pop     rdi
0x10049cee0  pop     rsi
0x10049cee1  pop     rbp
0x10049cee2  retn
0x10049cee3  mov     [rsp+48h+arg_8], rbx
0x10049cee8  mov     rbx, r12
0x10049ceeb  mov     [rsp+48h+arg_0], rbx
0x10049cef0  call    cs:__imp_InterlockedPopEntrySList
0x10049cef6  mov     rsi, rax
0x10049cef9  test    rax, rax
0x10049cefc  jz      loc_10049CFD0
0x10049cf02  mov     [rsp+48h+arg_10], r14
0x10049cf07  mov     rax, r12
0x10049cf0a  mov     [rsp+48h+var_28], r15
0x10049cf0f  nop
0x10049cf10  mov     r14, rsi
0x10049cf13  mov     r15, rsi
0x10049cf16  mov     rdx, rax
0x10049cf19  cmp     rsi, rbp
0x10049cf1c  jz      short loc_10049CF42
0x10049cf1e  mov     [rsi], rbx
0x10049cf21  mov     rcx, rdi; ListHead
0x10049cf24  mov     rbx, rsi
0x10049cf27  mov     rsi, r12
0x10049cf2a  call    cs:__imp_InterlockedPopEntrySList
0x10049cf30  test    rax, rax
0x10049cf33  mov     rdx, rbx; ListEntry
0x10049cf36  cmovnz  rsi, rax
0x10049cf3a  mov     rax, rbx
0x10049cf3d  test    rsi, rsi
0x10049cf40  jnz     short loc_10049CF10
0x10049cf42  mov     r15, [rsp+48h+var_28]
0x10049cf47  mov     r14, [rsp+48h+arg_10]
0x10049cf4c  mov     [rsp+48h+arg_0], rbx
0x10049cf51  test    rdx, rdx
0x10049cf54  jz      short loc_10049CFC5
0x10049cf56  lea     r8, [rsp+48h+arg_0]
0x10049cf5b  mov     rax, rdx
0x10049cf5e  xchg    ax, ax
0x10049cf60  mov     rcx, [rax]
0x10049cf63  cmp     rax, rdx
0x10049cf66  jz      short loc_10049CF75
0x10049cf68  mov     r8, rax
0x10049cf6b  mov     rax, rcx
0x10049cf6e  test    rcx, rcx
0x10049cf71  jnz     short loc_10049CF60
0x10049cf73  jmp     short loc_10049CF80
0x10049cf75  mov     [r8], rcx
0x10049cf78  mov     rbx, [rsp+48h+arg_0]
0x10049cf7d  mov     [rax], r12
0x10049cf80  mov     rcx, rdi; ListHead
0x10049cf83  call    cs:__imp_InterlockedPushEntrySList
0x10049cf89  mov     rdx, rbx
0x10049cf8c  test    rbx, rbx
0x10049cf8f  jz      short loc_10049CFC0
0x10049cf91  lea     r8, [rsp+48h+arg_0]
0x10049cf96  mov     rax, rbx
0x10049cf99  nop     dword ptr [rax+00000000h]
0x10049cfa0  mov     rcx, [rax]
0x10049cfa3  cmp     rax, rbx
0x10049cfa6  jz      short loc_10049CFB5
0x10049cfa8  mov     r8, rax
0x10049cfab  mov     rax, rcx
0x10049cfae  test    rcx, rcx
0x10049cfb1  jnz     short loc_10049CFA0
0x10049cfb3  jmp     short loc_10049CFC0
0x10049cfb5  mov     [r8], rcx
0x10049cfb8  mov     rbx, [rsp+48h+arg_0]
0x10049cfbd  mov     [rax], r12
0x10049cfc0  test    rdx, rdx
0x10049cfc3  jnz     short loc_10049CF80
0x10049cfc5  test    rsi, rsi
0x10049cfc8  jz      short loc_10049CFD3
0x10049cfca  lock dec dword ptr [rdi+28h]
0x10049cfce  jmp     short loc_10049CFD3
0x10049cfd0  mov     rsi, r12
0x10049cfd3  mov     rbx, [rsp+48h+arg_8]
0x10049cfd8  mov     rax, rsi
0x10049cfdb  add     rsp, 28h
0x10049cfdf  pop     r12
0x10049cfe1  pop     rdi
0x10049cfe2  pop     rsi
0x10049cfe3  pop     rbp
0x10049cfe4  retn
```
