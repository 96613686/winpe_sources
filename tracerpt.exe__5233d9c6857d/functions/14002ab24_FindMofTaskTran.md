# FindMofTaskTran

- ea: `0x14002ab24`
- end: `0x14002abf9`
- name: `FindMofTaskTran`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140029fd8`

## callees

- `0x140002730`
- `0x14002ab24`
- `0x14002c4d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ab5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ab5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ab6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ab6f`

## pseudocode

```c
_QWORD *__fastcall FindMofTaskTran(__int16 a1, __int64 a2, int a3)
{
  _QWORD *v3; // rbx
  _QWORD *result; // rax
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rcx
  _DWORD *v10; // rbx
  unsigned int v11; // eax
  int v12; // ecx

  v3 = (_QWORD *)(a2 + 6232);
  for ( result = *(_QWORD **)(a2 + 6232); v3 != result; result = (_QWORD *)*result )
  {
    if ( *((_WORD *)result + 8) == a1 )
      return result;
  }
  if ( !a3 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x28u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v9 = (_QWORD *)v3[1];
  v7[1] = v9;
  *v7 = v3;
  *v9 = v7;
  v3[1] = v7;
  v10 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
    return 0;
  v11 = 64;
  v12 = 0;
  do
  {
    ++v12;
    v11 >>= 1;
  }
  while ( v11 );
  v10[2] = v12;
  *(_QWORD *)v10 = &RptTidHashTable::`vftable';
  *((_QWORD *)v10 + 6) = 0;
  *((_QWORD *)v10 + 5) = 0;
  HashTable<RPT_TID,0,1>::Init(v10);
  result = v8;
  v8[3] = v10;
  *((_WORD *)v8 + 8) = a1;
  return result;
}

```

## disassembly

```asm
0x14002ab24  mov     [rsp+arg_0], rbx
0x14002ab29  mov     [rsp+arg_8], rsi
0x14002ab2e  push    rdi
0x14002ab2f  sub     rsp, 20h
0x14002ab33  lea     rbx, [rdx+1858h]
0x14002ab3a  movzx   esi, cx
0x14002ab3d  mov     rax, [rbx]
0x14002ab40  jmp     short loc_14002AB4F
0x14002ab42  cmp     [rax+10h], si
0x14002ab46  jz      loc_14002ABE9
0x14002ab4c  mov     rax, [rax]
0x14002ab4f  cmp     rbx, rax
0x14002ab52  jnz     short loc_14002AB42
0x14002ab54  test    r8d, r8d
0x14002ab57  jz      loc_14002ABE7
0x14002ab5d  call    cs:__imp_GetProcessHeap
0x14002ab63  mov     edx, 8; dwFlags
0x14002ab68  mov     rcx, rax; hHeap
0x14002ab6b  lea     r8d, [rdx+20h]; dwBytes
0x14002ab6f  call    cs:__imp_HeapAlloc
0x14002ab75  mov     rdi, rax
0x14002ab78  test    rax, rax
0x14002ab7b  jz      short loc_14002ABE7
0x14002ab7d  mov     rcx, [rbx+8]
0x14002ab81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002ab88  mov     [rax+8], rcx
0x14002ab8c  mov     [rax], rbx
0x14002ab8f  mov     [rcx], rax
0x14002ab92  mov     ecx, 38h ; '8'; unsigned __int64
0x14002ab97  mov     [rbx+8], rax
0x14002ab9b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002aba0  mov     rbx, rax
0x14002aba3  test    rax, rax
0x14002aba6  jz      short loc_14002ABE7
0x14002aba8  mov     eax, 40h ; '@'
0x14002abad  xor     ecx, ecx
0x14002abaf  inc     ecx
0x14002abb1  shr     eax, 1
0x14002abb3  jnz     short loc_14002ABAF
0x14002abb5  mov     [rbx+8], ecx
0x14002abb8  lea     rax, ??_7RptTidHashTable@@6B@; const RptTidHashTable::`vftable'
0x14002abbf  mov     rcx, rbx
0x14002abc2  mov     [rbx], rax
0x14002abc5  mov     qword ptr [rbx+30h], 0
0x14002abcd  mov     qword ptr [rbx+28h], 0
0x14002abd5  call    ?Init@?$HashTable@VRPT_TID@@$0A@$00@@QEAAKXZ; HashTable<RPT_TID,0,1>::Init(void)
0x14002abda  mov     rax, rdi
0x14002abdd  mov     [rdi+18h], rbx
0x14002abe1  mov     [rdi+10h], si
0x14002abe5  jmp     short loc_14002ABE9
0x14002abe7  xor     eax, eax
0x14002abe9  mov     rbx, [rsp+28h+arg_0]
0x14002abee  mov     rsi, [rsp+28h+arg_8]
0x14002abf3  add     rsp, 20h
0x14002abf7  pop     rdi
0x14002abf8  retn
```
