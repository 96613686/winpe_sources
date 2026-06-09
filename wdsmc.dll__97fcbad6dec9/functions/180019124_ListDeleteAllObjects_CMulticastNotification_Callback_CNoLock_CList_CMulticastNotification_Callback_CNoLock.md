# ListDeleteAllObjects<CMulticastNotification::Callback,CNoLock>(CList<CMulticastNotification::Callback,CNoLock> *)

- ea: `0x180019124`
- end: `0x1800191b8`
- name: `??$ListDeleteAllObjects@UCallback@CMulticastNotification@@VCNoLock@@@@YAXPEAV?$CList@UCallback@CMulticastNotification@@VCNoLock@@@@@Z`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005a4c`
- `0x180018f20`

## callees

- `0x180019124`
- `0x18001a9a8`

## pseudocode

```c
void __fastcall ListDeleteAllObjects<CMulticastNotification::Callback,CNoLock>(__int64 a1)
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
      v6 = v4[2];
      *(_QWORD *)a1 = v6;
      *(_QWORD *)(v6 + 24) = 0;
      v1 = *(_QWORD **)a1;
      goto LABEL_10;
    }
    if ( v1 == v5 )
    {
      v7 = v5[3];
      *(_QWORD *)(a1 + 8) = v7;
      *(_QWORD *)(v7 + 16) = 0;
      goto LABEL_8;
    }
    v8 = v1 + 2;
    v1 = (_QWORD *)v1[2];
    *(_QWORD *)(v3[3] + 16LL) = v1;
    *(_QWORD *)(*v8 + 24LL) = v3[3];
LABEL_10:
    --*(_DWORD *)(a1 + 20);
    operator delete(v3);
  }
}

```

## disassembly

```asm
0x180019124  mov     [rsp+arg_0], rbx
0x180019129  push    rdi
0x18001912a  sub     rsp, 20h
0x18001912e  mov     rbx, [rcx]
0x180019131  mov     rdi, rcx
0x180019134  jmp     short loc_1800191A8
0x180019136  mov     rcx, rbx; void *
0x180019139  test    rbx, rbx
0x18001913c  jz      short loc_18001919E
0x18001913e  mov     rax, [rdi]
0x180019141  mov     rdx, [rdi+8]
0x180019145  cmp     rax, rdx
0x180019148  jnz     short loc_180019155
0x18001914a  and     qword ptr [rdi+8], 0
0x18001914f  and     qword ptr [rdi], 0
0x180019153  jmp     short loc_18001917D
0x180019155  cmp     rbx, rax
0x180019158  jnz     short loc_18001916B
0x18001915a  mov     rax, [rax+10h]
0x18001915e  mov     [rdi], rax
0x180019161  and     qword ptr [rax+18h], 0
0x180019166  mov     rbx, [rdi]
0x180019169  jmp     short loc_18001919B
0x18001916b  cmp     rbx, rdx
0x18001916e  jnz     short loc_180019181
0x180019170  mov     rax, [rdx+18h]
0x180019174  mov     [rdi+8], rax
0x180019178  and     qword ptr [rax+10h], 0
0x18001917d  xor     ebx, ebx
0x18001917f  jmp     short loc_18001919B
0x180019181  mov     rax, [rcx+18h]
0x180019185  lea     rdx, [rbx+10h]
0x180019189  mov     rbx, [rdx]
0x18001918c  mov     [rax+10h], rbx
0x180019190  mov     rdx, [rdx]
0x180019193  mov     rax, [rcx+18h]
0x180019197  mov     [rdx+18h], rax
0x18001919b  dec     dword ptr [rdi+14h]
0x18001919e  test    rcx, rcx
0x1800191a1  jz      short loc_1800191A8
0x1800191a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800191a8  test    rbx, rbx
0x1800191ab  jnz     short loc_180019136
0x1800191ad  mov     rbx, [rsp+28h+arg_0]
0x1800191b2  add     rsp, 20h
0x1800191b6  pop     rdi
0x1800191b7  retn
```
