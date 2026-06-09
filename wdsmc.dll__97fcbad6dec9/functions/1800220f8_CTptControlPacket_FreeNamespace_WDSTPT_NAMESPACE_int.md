# CTptControlPacket::FreeNamespace(_WDSTPT_NAMESPACE *,int)

- ea: `0x1800220f8`
- end: `0x180022186`
- name: `?FreeNamespace@CTptControlPacket@@SAXPEAU_WDSTPT_NAMESPACE@@H@Z`
- size: `142`
- prototype: `void __fastcall(struct _WDSTPT_NAMESPACE *, int)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800026b8`
- `0x180002960`
- `0x1800039f0`
- `0x180005f18`
- `0x180006488`
- `0x180006bc4`
- `0x180006e48`
- `0x180006f84`
- `0x180021d80`

## callees

- `0x18001a9a8`
- `0x1800220f8`

## pseudocode

```c
void __fastcall CTptControlPacket::FreeNamespace(struct _WDSTPT_NAMESPACE *a1, int a2)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( a1 )
  {
    v4 = (void *)*((_QWORD *)a1 + 2);
    if ( v4 )
    {
      operator delete(v4);
      *((_QWORD *)a1 + 2) = 0;
    }
    v5 = (void *)*((_QWORD *)a1 + 3);
    if ( v5 )
    {
      operator delete(v5);
      *((_QWORD *)a1 + 3) = 0;
    }
    v6 = (void *)*((_QWORD *)a1 + 4);
    if ( v6 )
    {
      operator delete(v6);
      *((_QWORD *)a1 + 4) = 0;
    }
    v7 = (void *)*((_QWORD *)a1 + 5);
    if ( v7 )
    {
      operator delete(v7);
      *((_QWORD *)a1 + 5) = 0;
    }
    v8 = (void *)*((_QWORD *)a1 + 6);
    if ( v8 )
    {
      operator delete(v8);
      *((_QWORD *)a1 + 6) = 0;
    }
    if ( a2 )
      operator delete(a1);
  }
}

```

## disassembly

```asm
0x1800220f8  test    rcx, rcx
0x1800220fb  jz      locret_180022185
0x180022101  mov     [rsp+arg_0], rbx
0x180022106  push    rdi
0x180022107  sub     rsp, 20h
0x18002210b  mov     rbx, rcx
0x18002210e  mov     edi, edx
0x180022110  mov     rcx, [rcx+10h]; void *
0x180022114  test    rcx, rcx
0x180022117  jz      short loc_180022123
0x180022119  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002211e  and     qword ptr [rbx+10h], 0
0x180022123  mov     rcx, [rbx+18h]; void *
0x180022127  test    rcx, rcx
0x18002212a  jz      short loc_180022136
0x18002212c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022131  and     qword ptr [rbx+18h], 0
0x180022136  mov     rcx, [rbx+20h]; void *
0x18002213a  test    rcx, rcx
0x18002213d  jz      short loc_180022149
0x18002213f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022144  and     qword ptr [rbx+20h], 0
0x180022149  mov     rcx, [rbx+28h]; void *
0x18002214d  test    rcx, rcx
0x180022150  jz      short loc_18002215C
0x180022152  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022157  and     qword ptr [rbx+28h], 0
0x18002215c  mov     rcx, [rbx+30h]; void *
0x180022160  test    rcx, rcx
0x180022163  jz      short loc_18002216F
0x180022165  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002216a  and     qword ptr [rbx+30h], 0
0x18002216f  test    edi, edi
0x180022171  jz      short loc_18002217B
0x180022173  mov     rcx, rbx; void *
0x180022176  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002217b  mov     rbx, [rsp+28h+arg_0]
0x180022180  add     rsp, 20h
0x180022184  pop     rdi
0x180022185  retn
```
