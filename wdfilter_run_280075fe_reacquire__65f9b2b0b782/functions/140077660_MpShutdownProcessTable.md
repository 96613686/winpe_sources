# MpShutdownProcessTable

- ea: `0x140077660`
- end: `0x1400777a6`
- name: `MpShutdownProcessTable`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x140030060`
- `0x140077660`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140077733`
- `ntoskrnl!ExDeleteResourceLite` at `0x140077733`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400776eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077748`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077775`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400776eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077748`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077775`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140077705`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007771c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140077705`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007771c`

## pseudocode

```c
void MpShutdownProcessTable()
{
  _QWORD *v0; // rcx
  unsigned int i; // ebx
  _QWORD **v2; // rdx
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  void *v5; // rcx
  unsigned int v6; // edi
  PVOID *v7; // rbx

  v0 = MpProcessTable;
  if ( MpProcessTable )
  {
    if ( *((_QWORD *)MpProcessTable + 48) )
    {
      for ( i = 0; i < 0x80; ++i )
      {
        while ( 1 )
        {
          v0 = MpProcessTable;
          v2 = (_QWORD **)(16LL * i + *((_QWORD *)MpProcessTable + 48));
          v3 = *v2;
          if ( *v2 == v2 )
            break;
          if ( (_QWORD **)v3[1] != v2 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
            __fastfail(3u);
          *v2 = v4;
          v4[1] = v2;
          MpReleaseProcessContext(v3 - 1);
        }
      }
    }
    v5 = (void *)v0[48];
    if ( v5 )
      ExFreePoolWithTag(v5, 0x5470504Du);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpProcessTable + 2);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpProcessTable + 1);
    ExDeleteResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
    ExFreePoolWithTag(MpProcessTable, 0x5470504Du);
    v6 = 0;
    MpProcessTable = 0;
    v7 = (PVOID *)&qword_140026420;
    do
    {
      if ( *v7 )
      {
        ExFreePoolWithTag(*v7, 0x6E6F704Du);
        *v7 = 0;
      }
      ++v6;
      v7 += 3;
    }
    while ( v6 < 0xC );
  }
}

```

## disassembly

```asm
0x140077660  mov     [rsp+arg_0], rbx
0x140077665  push    rdi
0x140077666  sub     rsp, 20h
0x14007766a  mov     rcx, cs:MpProcessTable
0x140077671  test    rcx, rcx
0x140077674  jz      loc_140077793
0x14007767a  cmp     qword ptr [rcx+180h], 0
0x140077682  jz      short loc_1400776D8
0x140077684  xor     ebx, ebx
0x140077686  mov     edi, ebx
0x140077688  shl     rdi, 4
0x14007768c  mov     rcx, cs:MpProcessTable
0x140077693  mov     rdx, [rcx+180h]
0x14007769a  add     rdx, rdi
0x14007769d  mov     rax, [rdx]
0x1400776a0  cmp     rax, rdx
0x1400776a3  jz      short loc_1400776CE
0x1400776a5  cmp     [rax+8], rdx
0x1400776a9  jnz     loc_14007779F
0x1400776af  mov     rcx, [rax]
0x1400776b2  cmp     [rcx+8], rax
0x1400776b6  jnz     loc_14007779F
0x1400776bc  mov     [rdx], rcx
0x1400776bf  mov     [rcx+8], rdx
0x1400776c3  lea     rcx, [rax-8]
0x1400776c7  call    MpReleaseProcessContext
0x1400776cc  jmp     short loc_14007768C
0x1400776ce  inc     ebx
0x1400776d0  cmp     ebx, 80h
0x1400776d6  jb      short loc_140077686
0x1400776d8  mov     rcx, [rcx+180h]; P
0x1400776df  mov     ebx, 5470504Dh
0x1400776e4  test    rcx, rcx
0x1400776e7  jz      short loc_1400776F7
0x1400776e9  mov     edx, ebx; Tag
0x1400776eb  call    cs:__imp_ExFreePoolWithTag
0x1400776f2  nop     dword ptr [rax+rax+00h]
0x1400776f7  mov     rcx, cs:MpProcessTable
0x1400776fe  add     rcx, 100h; Lookaside
0x140077705  call    cs:__imp_ExDeletePagedLookasideList
0x14007770c  nop     dword ptr [rax+rax+00h]
0x140077711  mov     rcx, cs:MpProcessTable
0x140077718  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14007771c  call    cs:__imp_ExDeletePagedLookasideList
0x140077723  nop     dword ptr [rax+rax+00h]
0x140077728  mov     rcx, cs:MpProcessTable
0x14007772f  add     rcx, 8; Resource
0x140077733  call    cs:__imp_ExDeleteResourceLite
0x14007773a  nop     dword ptr [rax+rax+00h]
0x14007773f  mov     rcx, cs:MpProcessTable; P
0x140077746  mov     edx, ebx; Tag
0x140077748  call    cs:__imp_ExFreePoolWithTag
0x14007774f  nop     dword ptr [rax+rax+00h]
0x140077754  xor     edi, edi
0x140077756  mov     cs:MpProcessTable, 0
0x140077761  lea     rbx, qword_140026420
0x140077768  mov     rcx, [rbx]; P
0x14007776b  test    rcx, rcx
0x14007776e  jz      short loc_140077788
0x140077770  mov     edx, 6E6F704Dh; Tag
0x140077775  call    cs:__imp_ExFreePoolWithTag
0x14007777c  nop     dword ptr [rax+rax+00h]
0x140077781  mov     qword ptr [rbx], 0
0x140077788  inc     edi
0x14007778a  add     rbx, 18h
0x14007778e  cmp     edi, 0Ch
0x140077791  jb      short loc_140077768
0x140077793  mov     rbx, [rsp+28h+arg_0]
0x140077798  add     rsp, 20h
0x14007779c  pop     rdi
0x14007779d  retn
0x14007779f  mov     ecx, 3
0x1400777a4  int     29h; Win8: RtlFailFast(ecx)
```
