# InsertEntry

- ea: `0x140008cf0`
- end: `0x140008de8`
- name: `InsertEntry`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400084bc`

## callees

- `0x140005038`
- `0x140008cf0`
- `0x140008df0`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140008d0a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140008d0a`

## pseudocode

```c
_DWORD *__fastcall InsertEntry(int a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // rsi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  _DWORD *result; // rax
  unsigned int v11; // eax
  __int64 v12; // rcx
  _QWORD *v13; // rdx

  v5 = a2;
  v8 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a3 + 64));
  v9 = v8;
  if ( v8 )
  {
    memset(v8, 0, *(unsigned int *)(a3 + 16));
    v9[4] = v5;
    ++*(_DWORD *)(a3 + 36);
    v11 = InsertInPendingList(a1, v5, a3, (_DWORD)v9, a4);
    v12 = *(_QWORD *)(a3 + 8LL * v11 + 192);
    if ( !v12 || (int)v5 - *(_DWORD *)(v12 + 16) < 0 )
      *(_QWORD *)(a3 + 8LL * v11 + 192) = v9;
    v13 = (_QWORD *)(*(_QWORD *)(a3 + 56) + 16 * ((v5 >> *(_DWORD *)(a3 + 48)) & *(unsigned int *)(a3 + 44)));
    do
      v13 = (_QWORD *)*v13;
    while ( v13 != (_QWORD *)(*(_QWORD *)(a3 + 56) + 16 * ((v5 >> *(_DWORD *)(a3 + 48)) & *(unsigned int *)(a3 + 44)))
         && *((_DWORD *)v13 - 16) - (int)v5 < 0 );
    *((_QWORD *)v9 + 10) = v13;
    *((_QWORD *)v9 + 11) = v13[1];
    *(_QWORD *)v13[1] = v9 + 20;
    result = v9;
    v13[1] = v9 + 20;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140008cf0  push    rbx
0x140008cf2  push    rbp
0x140008cf3  push    rsi
0x140008cf4  push    rdi
0x140008cf5  push    r14
0x140008cf7  sub     rsp, 30h
0x140008cfb  mov     r14, rcx
0x140008cfe  mov     esi, edx
0x140008d00  lea     rcx, [r8+40h]; Lookaside
0x140008d04  mov     rbp, r9
0x140008d07  mov     rdi, r8
0x140008d0a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140008d11  nop     dword ptr [rax+rax+00h]
0x140008d16  mov     rbx, rax
0x140008d19  test    rax, rax
0x140008d1c  jnz     short loc_140008D52
0x140008d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d25  lea     rax, WPP_GLOBAL_Control
0x140008d2c  cmp     rcx, rax
0x140008d2f  jz      short loc_140008D4B
0x140008d31  mov     eax, [rcx+2Ch]
0x140008d34  test    al, 2
0x140008d36  jz      short loc_140008D4B
0x140008d38  mov     rcx, [rcx+18h]
0x140008d3c  lea     edx, [rbx+0Dh]
0x140008d3f  lea     r8, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids
0x140008d46  call    WPP_SF_
0x140008d4b  xor     eax, eax
0x140008d4d  jmp     loc_140008DDC
0x140008d52  mov     r8d, [rdi+10h]; Size
0x140008d56  xor     edx, edx; Val
0x140008d58  mov     rcx, rbx; void *
0x140008d5b  call    memset
0x140008d60  mov     [rbx+10h], esi
0x140008d63  mov     r9, rbx
0x140008d66  inc     dword ptr [rdi+24h]
0x140008d69  mov     r8, rdi
0x140008d6c  mov     edx, esi
0x140008d6e  mov     [rsp+58h+var_38], rbp
0x140008d73  mov     rcx, r14
0x140008d76  call    InsertInPendingList
0x140008d7b  mov     r8d, eax
0x140008d7e  mov     rcx, [rdi+r8*8+0C0h]
0x140008d86  test    rcx, rcx
0x140008d89  jz      short loc_140008D90
0x140008d8b  cmp     esi, [rcx+10h]
0x140008d8e  jns     short loc_140008D98
0x140008d90  mov     [rdi+r8*8+0C0h], rbx
0x140008d98  mov     ecx, [rdi+30h]
0x140008d9b  mov     rdx, rsi
0x140008d9e  shr     rdx, cl
0x140008da1  mov     ecx, [rdi+2Ch]
0x140008da4  and     rcx, rdx
0x140008da7  shl     rcx, 4
0x140008dab  add     rcx, [rdi+38h]
0x140008daf  mov     rdx, rcx
0x140008db2  mov     rdx, [rdx]
0x140008db5  cmp     rdx, rcx
0x140008db8  jz      short loc_140008DBF
0x140008dba  cmp     [rdx-40h], esi
0x140008dbd  js      short loc_140008DB2
0x140008dbf  lea     rcx, [rbx+50h]
0x140008dc3  mov     [rcx], rdx
0x140008dc6  mov     rax, [rdx+8]
0x140008dca  mov     [rbx+58h], rax
0x140008dce  mov     rax, [rdx+8]
0x140008dd2  mov     [rax], rcx
0x140008dd5  mov     rax, rbx
0x140008dd8  mov     [rdx+8], rcx
0x140008ddc  add     rsp, 30h
0x140008de0  pop     r14
0x140008de2  pop     rdi
0x140008de3  pop     rsi
0x140008de4  pop     rbp
0x140008de5  pop     rbx
0x140008de6  retn
```
