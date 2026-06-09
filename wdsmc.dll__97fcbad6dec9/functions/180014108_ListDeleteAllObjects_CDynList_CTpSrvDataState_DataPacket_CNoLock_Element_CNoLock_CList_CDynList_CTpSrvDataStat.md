# ListDeleteAllObjects<CDynList<CTpSrvDataState::DataPacket,CNoLock>::Element,CNoLock>(CList<CDynList<CTpSrvDataState::DataPacket,CNoLock>::Element,CNoLock> *)

- ea: `0x180014108`
- end: `0x1800141be`
- name: `??$ListDeleteAllObjects@UElement@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@VCNoLock@@@@YAXPEAV?$CList@UElement@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@VCNoLock@@@@@Z`
- size: `182`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001198c`
- `0x180011bbc`
- `0x180013ef8`

## callees

- `0x180014108`
- `0x18001a9a8`

## pseudocode

```c
void __fastcall ListDeleteAllObjects<CDynList<CTpSrvDataState::DataPacket,CNoLock>::Element,CNoLock>(__int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  _QWORD *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rdx

  v1 = *(_QWORD **)a1;
  while ( v1 )
  {
    v3 = v1;
    v4 = *(_QWORD **)a1;
    v5 = *(_QWORD **)(a1 + 8);
    if ( *(_QWORD **)a1 == v5 )
    {
      *(_QWORD *)(a1 + 8) = 0;
      *(_QWORD *)a1 = 0;
LABEL_8:
      v1 = 0;
      goto LABEL_10;
    }
    if ( v1 == v4 )
    {
      v6 = v4[8193];
      *(_QWORD *)a1 = v6;
      *(_QWORD *)(v6 + 65552) = 0;
      v1 = *(_QWORD **)a1;
      goto LABEL_10;
    }
    if ( v1 == v5 )
    {
      v7 = v5[8194];
      *(_QWORD *)(a1 + 8) = v7;
      *(_QWORD *)(v7 + 65544) = 0;
      goto LABEL_8;
    }
    v8 = v1 + 8193;
    v1 = (_QWORD *)v1[8193];
    *(_QWORD *)(v3[8194] + 65544LL) = v1;
    *(_QWORD *)(*v8 + 65552LL) = v3[8194];
LABEL_10:
    --*(_DWORD *)(a1 + 20);
    operator delete(v3);
  }
}

```

## disassembly

```asm
0x180014108  mov     [rsp+arg_0], rbx
0x18001410d  push    rdi
0x18001410e  sub     rsp, 20h
0x180014112  mov     rbx, [rcx]
0x180014115  mov     rdi, rcx
0x180014118  jmp     loc_1800141AA
0x18001411d  mov     rcx, rbx; void *
0x180014120  test    rbx, rbx
0x180014123  jz      short loc_1800141A0
0x180014125  mov     rax, [rdi]
0x180014128  mov     rdx, [rdi+8]
0x18001412c  cmp     rax, rdx
0x18001412f  jnz     short loc_18001413C
0x180014131  and     qword ptr [rdi+8], 0
0x180014136  and     qword ptr [rdi], 0
0x18001413a  jmp     short loc_180014170
0x18001413c  cmp     rbx, rax
0x18001413f  jnz     short loc_180014158
0x180014141  mov     rax, [rax+10008h]
0x180014148  mov     [rdi], rax
0x18001414b  and     qword ptr [rax+10010h], 0
0x180014153  mov     rbx, [rdi]
0x180014156  jmp     short loc_18001419D
0x180014158  cmp     rbx, rdx
0x18001415b  jnz     short loc_180014174
0x18001415d  mov     rax, [rdx+10010h]
0x180014164  mov     [rdi+8], rax
0x180014168  and     qword ptr [rax+10008h], 0
0x180014170  xor     ebx, ebx
0x180014172  jmp     short loc_18001419D
0x180014174  mov     rax, [rcx+10010h]
0x18001417b  lea     rdx, [rbx+10008h]
0x180014182  mov     rbx, [rdx]
0x180014185  mov     [rax+10008h], rbx
0x18001418c  mov     rdx, [rdx]
0x18001418f  mov     rax, [rcx+10010h]
0x180014196  mov     [rdx+10010h], rax
0x18001419d  dec     dword ptr [rdi+14h]
0x1800141a0  test    rcx, rcx
0x1800141a3  jz      short loc_1800141AA
0x1800141a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800141aa  test    rbx, rbx
0x1800141ad  jnz     loc_18001411D
0x1800141b3  mov     rbx, [rsp+28h+arg_0]
0x1800141b8  add     rsp, 20h
0x1800141bc  pop     rdi
0x1800141bd  retn
```
