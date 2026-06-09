# SqospCleanupDevice

- ea: `0x140011008`
- end: `0x1400110be`
- name: `SqospCleanupDevice`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140012850`

## callees

- `0x140003ec0`
- `0x140011008`

## import_xrefs

- `ntoskrnl!PcwCloseInstance` at `0x140011026`
- `ntoskrnl!PcwCloseInstance` at `0x140011026`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011083`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011083`
- `ntoskrnl!IoFreeWorkItem` at `0x140011098`
- `ntoskrnl!IoFreeWorkItem` at `0x140011098`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140011036`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14001106a`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140011036`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14001106a`

## pseudocode

```c
__int64 __fastcall SqospCleanupDevice(__int64 a1)
{
  struct _PCW_INSTANCE *v2; // rcx
  unsigned int *v3; // rdi
  unsigned int v4; // esi
  unsigned __int64 v5; // rcx
  struct _IO_WORKITEM *v6; // rcx

  v2 = *(struct _PCW_INSTANCE **)(a1 + 152);
  if ( v2 )
    PcwCloseInstance(v2);
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 48));
  v3 = *(unsigned int **)(a1 + 144);
  if ( v3 )
  {
    v4 = *v3;
    while ( (--v4 & 0x80000000) == 0 )
    {
      v5 = (unsigned __int64)v4 << 7;
      if ( *((_BYTE *)v3 + v5 + 176) )
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)v3 + v5 + 64));
    }
    ExFreePoolWithTag(v3, 0x46535153u);
  }
  v6 = *(struct _IO_WORKITEM **)(a1 + 40);
  if ( v6 )
    IoFreeWorkItem(v6);
  return SqospFreeUnicodeString(a1 + 24);
}

```

## disassembly

```asm
0x140011008  mov     [rsp+arg_0], rbx
0x14001100d  mov     [rsp+arg_8], rsi
0x140011012  push    rdi
0x140011013  sub     rsp, 20h
0x140011017  mov     rbx, rcx
0x14001101a  mov     rcx, [rcx+98h]; Instance
0x140011021  test    rcx, rcx
0x140011024  jz      short loc_140011032
0x140011026  call    cs:__imp_PcwCloseInstance
0x14001102d  nop     dword ptr [rax+rax+00h]
0x140011032  lea     rcx, [rbx+30h]; Lookaside
0x140011036  call    cs:__imp_ExDeleteLookasideListEx
0x14001103d  nop     dword ptr [rax+rax+00h]
0x140011042  mov     rdi, [rbx+90h]
0x140011049  test    rdi, rdi
0x14001104c  jz      short loc_14001108F
0x14001104e  mov     esi, [rdi]
0x140011050  jmp     short loc_140011076
0x140011052  mov     ecx, esi
0x140011054  shl     rcx, 7
0x140011058  mov     al, [rcx+rdi+0B0h]
0x14001105f  test    al, al
0x140011061  jz      short loc_140011076
0x140011063  add     rcx, 40h ; '@'
0x140011067  add     rcx, rdi; Lookaside
0x14001106a  call    cs:__imp_ExDeleteLookasideListEx
0x140011071  nop     dword ptr [rax+rax+00h]
0x140011076  sub     esi, 1
0x140011079  jns     short loc_140011052
0x14001107b  mov     edx, 46535153h; Tag
0x140011080  mov     rcx, rdi; P
0x140011083  call    cs:__imp_ExFreePoolWithTag
0x14001108a  nop     dword ptr [rax+rax+00h]
0x14001108f  mov     rcx, [rbx+28h]; IoWorkItem
0x140011093  test    rcx, rcx
0x140011096  jz      short loc_1400110A4
0x140011098  call    cs:__imp_IoFreeWorkItem
0x14001109f  nop     dword ptr [rax+rax+00h]
0x1400110a4  lea     rcx, [rbx+18h]
0x1400110a8  call    SqospFreeUnicodeString
0x1400110ad  mov     rbx, [rsp+28h+arg_0]
0x1400110b2  mov     rsi, [rsp+28h+arg_8]
0x1400110b7  add     rsp, 20h
0x1400110bb  pop     rdi
0x1400110bc  retn
```
