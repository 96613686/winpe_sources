# MpShutdownThreadTable

- ea: `0x140088b40`
- end: `0x140088ca1`
- name: `MpShutdownThreadTable`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x1400793b8`
- `0x140088b40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140088c39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088c7f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140088c50`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140088c50`
- `FLTMGR!FltDeletePushLock` at `0x140088c67`
- `FLTMGR!FltDeletePushLock` at `0x140088c67`

## pseudocode

```c
void MpShutdownThreadTable()
{
  _DWORD *v0; // rsi
  _QWORD **v1; // rdi
  _QWORD *v2; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rdx
  _QWORD *i; // rcx
  void *v6; // rcx

  v0 = MpThreadTable;
  if ( MpThreadTable )
  {
    v1 = (_QWORD **)*((_QWORD *)MpThreadTable + 25);
    v2 = v1;
    while ( v2 )
    {
      v3 = (_QWORD *)*v2;
      v2 = v3;
      if ( ((unsigned __int8)v3 & 1) != 0 )
        break;
LABEL_10:
      if ( !v3 )
        goto LABEL_18;
      v4 = v2;
      for ( i = v1; (*i & 1) == 0; i = (_QWORD *)*i )
      {
        if ( (_QWORD *)*i == v2 )
        {
          *i = *v2;
          --v0[48];
          *v2 |= 0x8000000000000002uLL;
          v2 = i;
          goto LABEL_17;
        }
      }
      v4 = 0;
LABEL_17:
      MpReleaseThreadContext(v4 - 1);
    }
    for ( ++v1; (unsigned __int64)v1 < *((_QWORD *)v0 + 25) + 8 * ((unsigned __int64)(unsigned int)v0[49] >> 5); ++v1 )
    {
      v2 = *v1;
      if ( ((unsigned __int8)*v1 & 1) == 0 )
      {
        v3 = *v1;
        goto LABEL_10;
      }
    }
LABEL_18:
    v6 = (void *)*((_QWORD *)MpThreadTable + 25);
    if ( v6 )
      ExFreePoolWithTag(v6, 0x4274504Du);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpThreadTable + 64));
    FltDeletePushLock((PULONG_PTR)MpThreadTable + 1);
    ExFreePoolWithTag(MpThreadTable, 0x5474504Du);
  }
}

```

## disassembly

```asm
0x140088b40  mov     [rsp+arg_0], rbx
0x140088b45  mov     [rsp+arg_8], rbp
0x140088b4a  mov     [rsp+arg_10], rsi
0x140088b4f  push    rdi
0x140088b50  sub     rsp, 20h
0x140088b54  mov     rsi, cs:MpThreadTable
0x140088b5b  test    rsi, rsi
0x140088b5e  jz      loc_140088C8B
0x140088b64  mov     rdi, [rsi+0C8h]
0x140088b6b  mov     rbp, 8000000000000002h
0x140088b75  mov     rbx, rdi
0x140088b78  test    rbx, rbx
0x140088b7b  jz      short loc_140088B99
0x140088b7d  mov     rax, [rbx]
0x140088b80  and     rax, rbp
0x140088b83  cmp     rax, rbp
0x140088b86  jnz     short loc_140088B8F
0x140088b88  mov     eax, ds:0
0x140088b8f  mov     rax, [rbx]
0x140088b92  mov     rbx, rax
0x140088b95  test    al, 1
0x140088b97  jz      short loc_140088BC8
0x140088b99  mov     ecx, [rsi+0C4h]
0x140088b9f  add     rdi, 8
0x140088ba3  mov     rax, [rsi+0C8h]
0x140088baa  shr     rcx, 5
0x140088bae  lea     rdx, [rax+rcx*8]
0x140088bb2  cmp     rdi, rdx
0x140088bb5  jnb     short loc_140088C21
0x140088bb7  mov     rbx, [rdi]
0x140088bba  test    bl, 1
0x140088bbd  jz      short loc_140088BC5
0x140088bbf  add     rdi, 8
0x140088bc3  jmp     short loc_140088BB2
0x140088bc5  mov     rax, rbx
0x140088bc8  test    rax, rax
0x140088bcb  jz      short loc_140088C21
0x140088bcd  mov     rax, [rbx]
0x140088bd0  mov     rdx, rbx
0x140088bd3  and     rax, rbp
0x140088bd6  cmp     rax, rbp
0x140088bd9  jnz     short loc_140088BE2
0x140088bdb  mov     eax, ds:0
0x140088be2  mov     rcx, rdi
0x140088be5  mov     rax, [rcx]
0x140088be8  test    al, 1
0x140088bea  jnz     short loc_140088C0A
0x140088bec  cmp     rax, rbx
0x140088bef  jz      short loc_140088BF6
0x140088bf1  mov     rcx, rax
0x140088bf4  jmp     short loc_140088BE5
0x140088bf6  mov     rax, [rbx]
0x140088bf9  mov     [rcx], rax
0x140088bfc  dec     dword ptr [rsi+0C0h]
0x140088c02  or      [rbx], rbp
0x140088c05  mov     rbx, rcx
0x140088c08  jmp     short loc_140088C13
0x140088c0a  mov     eax, ds:0
0x140088c11  xor     edx, edx
0x140088c13  lea     rcx, [rdx-8]; Entry
0x140088c17  call    MpReleaseThreadContext
0x140088c1c  jmp     loc_140088B78
0x140088c21  mov     rax, cs:MpThreadTable
0x140088c28  mov     rcx, [rax+0C8h]; P
0x140088c2f  test    rcx, rcx
0x140088c32  jz      short loc_140088C45
0x140088c34  mov     edx, 4274504Dh; Tag
0x140088c39  call    cs:__imp_ExFreePoolWithTag
0x140088c40  nop     dword ptr [rax+rax+00h]
0x140088c45  mov     rcx, cs:MpThreadTable
0x140088c4c  add     rcx, 40h ; '@'; Lookaside
0x140088c50  call    cs:__imp_ExDeletePagedLookasideList
0x140088c57  nop     dword ptr [rax+rax+00h]
0x140088c5c  mov     rcx, cs:MpThreadTable
0x140088c63  add     rcx, 8; PushLock
0x140088c67  call    cs:__imp_FltDeletePushLock
0x140088c6e  nop     dword ptr [rax+rax+00h]
0x140088c73  mov     rcx, cs:MpThreadTable; P
0x140088c7a  mov     edx, 5474504Dh; Tag
0x140088c7f  call    cs:__imp_ExFreePoolWithTag
0x140088c86  nop     dword ptr [rax+rax+00h]
0x140088c8b  mov     rbx, [rsp+28h+arg_0]
0x140088c90  mov     rbp, [rsp+28h+arg_8]
0x140088c95  mov     rsi, [rsp+28h+arg_10]
0x140088c9a  add     rsp, 20h
0x140088c9e  pop     rdi
0x140088c9f  retn
```
