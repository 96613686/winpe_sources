# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x180004124`
- end: `0x18000415e`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001010c`
- `0x1800103d6`
- `0x1800105c2`
- `0x180010616`
- `0x180010814`

## callees

- `0x180004060`
- `0x180004124`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::~vector<unsigned char>(__int64 a1)
{
  _QWORD *v2; // rcx

  v2 = *(_QWORD **)a1;
  if ( v2 )
  {
    std::_Deallocate<16>(v2, *(_QWORD *)(a1 + 16) - (_QWORD)v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180004124  push    rbx
0x180004126  sub     rsp, 20h
0x18000412a  mov     rbx, rcx
0x18000412d  mov     rcx, [rcx]
0x180004130  test    rcx, rcx
0x180004133  jz      short loc_180004158
0x180004135  mov     rdx, [rbx+10h]
0x180004139  sub     rdx, rcx
0x18000413c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004141  mov     qword ptr [rbx], 0
0x180004148  mov     qword ptr [rbx+8], 0
0x180004150  mov     qword ptr [rbx+10h], 0
0x180004158  add     rsp, 20h
0x18000415c  pop     rbx
0x18000415d  retn
```
