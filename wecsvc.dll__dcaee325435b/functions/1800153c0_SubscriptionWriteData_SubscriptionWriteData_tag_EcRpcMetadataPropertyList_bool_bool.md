# SubscriptionWriteData::SubscriptionWriteData(tag_EcRpcMetadataPropertyList &,bool,bool)

- ea: `0x1800153c0`
- end: `0x180015427`
- name: `??0SubscriptionWriteData@@QEAA@AEAUtag_EcRpcMetadataPropertyList@@_N1@Z`
- size: `103`
- prototype: `SubscriptionWriteData *__fastcall(SubscriptionWriteData *this, struct tag_EcRpcMetadataPropertyList *, char, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001483c`

## callees

- `0x180003430`
- `0x1800153c0`

## pseudocode

```c
SubscriptionWriteData *__fastcall SubscriptionWriteData::SubscriptionWriteData(
        SubscriptionWriteData *this,
        struct tag_EcRpcMetadataPropertyList *a2,
        char a3,
        char a4)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  _BYTE *v7; // rcx

  *(_QWORD *)this = a2;
  *((_BYTE *)this + 8) = a4;
  if ( a3 )
  {
    v5 = 16;
    do
    {
      *(_BYTE *)a2 = 0;
      a2 = (struct tag_EcRpcMetadataPropertyList *)((char *)a2 + 1);
      --v5;
    }
    while ( v5 );
    v6 = 768;
    *(_QWORD *)(*(_QWORD *)this + 8LL) = operator new(0x300u);
    **(_DWORD **)this = 32;
    v7 = *(_BYTE **)(*(_QWORD *)this + 8LL);
    do
    {
      *v7++ = 0;
      --v6;
    }
    while ( v6 );
  }
  return this;
}

```

## disassembly

```asm
0x1800153c0  mov     [rsp+arg_0], rbx
0x1800153c5  push    rdi
0x1800153c6  sub     rsp, 20h
0x1800153ca  mov     [rcx], rdx
0x1800153cd  mov     rbx, rcx
0x1800153d0  mov     [rcx+8], r9b
0x1800153d4  test    r8b, r8b
0x1800153d7  jz      short loc_180015419
0x1800153d9  mov     eax, 10h
0x1800153de  mov     byte ptr [rdx], 0
0x1800153e1  inc     rdx
0x1800153e4  sub     rax, 1
0x1800153e8  jnz     short loc_1800153DE
0x1800153ea  mov     edi, 300h
0x1800153ef  mov     ecx, edi; dwBytes
0x1800153f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800153f6  mov     rcx, [rbx]
0x1800153f9  mov     [rcx+8], rax
0x1800153fd  mov     rax, [rbx]
0x180015400  mov     dword ptr [rax], 20h ; ' '
0x180015406  mov     rax, [rbx]
0x180015409  mov     rcx, [rax+8]
0x18001540d  mov     byte ptr [rcx], 0
0x180015410  inc     rcx
0x180015413  sub     rdi, 1
0x180015417  jnz     short loc_18001540D
0x180015419  mov     rax, rbx
0x18001541c  mov     rbx, [rsp+28h+arg_0]
0x180015421  add     rsp, 20h
0x180015425  pop     rdi
0x180015426  retn
```
