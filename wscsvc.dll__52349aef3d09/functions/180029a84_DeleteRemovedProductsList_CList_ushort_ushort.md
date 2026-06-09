# DeleteRemovedProductsList(CList<ushort *,ushort *> *)

- ea: `0x180029a84`
- end: `0x180029ad4`
- name: `?DeleteRemovedProductsList@@YAXPEAV?$CList@PEAGPEAG@@@Z`
- size: `80`
- prototype: `void __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001d9e0`
- `0x180029720`

## callees

- `0x180009f40`
- `0x180029a84`
- `0x180029e74`
- `0x180030efc`
- `0x1800319bc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ab0`

## pseudocode

```c
void __fastcall DeleteRemovedProductsList(void *Block)
{
  void *Next; // rax
  __int64 HeadPosition; // [rsp+30h] [rbp+8h] BYREF

  if ( Block )
  {
    HeadPosition = CList<unsigned short *,unsigned short *>::GetHeadPosition(Block);
    while ( HeadPosition )
    {
      Next = (void *)CList<unsigned short *,unsigned short *>::GetNext(Block, &HeadPosition);
      LocalFree(Next);
    }
    CList<CDetectoid *,CDetectoid *>::~CList<CDetectoid *,CDetectoid *>((__int64)Block);
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x180029a84  test    rcx, rcx
0x180029a87  jz      short locret_180029AD3
0x180029a89  push    rbx
0x180029a8a  sub     rsp, 20h
0x180029a8e  mov     rbx, rcx
0x180029a91  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x180029a96  mov     [rsp+28h+arg_0], rax
0x180029a9b  test    rax, rax
0x180029a9e  jz      short loc_180029ABE
0x180029aa0  lea     rdx, [rsp+28h+arg_0]
0x180029aa5  mov     rcx, rbx
0x180029aa8  call    ?GetNext@?$CList@PEAGPEAG@@QEAAPEAGAEAPEAU_CListElement@@@Z; CList<ushort *,ushort *>::GetNext(_CListElement * &)
0x180029aad  mov     rcx, rax; hMem
0x180029ab0  call    cs:__imp_LocalFree
0x180029ab6  cmp     [rsp+28h+arg_0], 0
0x180029abc  jnz     short loc_180029AA0
0x180029abe  mov     rcx, rbx
0x180029ac1  call    ??1?$CList@PEAVCDetectoid@@PEAV1@@@QEAA@XZ; CList<CDetectoid *,CDetectoid *>::~CList<CDetectoid *,CDetectoid *>(void)
0x180029ac6  mov     rcx, rbx; Block
0x180029ac9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029ace  add     rsp, 20h
0x180029ad2  pop     rbx
0x180029ad3  retn
```
