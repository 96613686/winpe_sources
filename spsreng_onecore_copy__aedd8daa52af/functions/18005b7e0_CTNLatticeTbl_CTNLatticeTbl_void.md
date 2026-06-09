# CTNLatticeTbl::~CTNLatticeTbl(void)

- ea: `0x18005b7e0`
- end: `0x18005b889`
- name: `??1CTNLatticeTbl@@QEAA@XZ`
- size: `169`
- prototype: `void __fastcall(CTNLatticeTbl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b574`

## callees

- `0x180002aac`
- `0x180006abc`
- `0x180055780`
- `0x18005b7e0`
- `0x18005b8b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b836`

## pseudocode

```c
void __fastcall CTNLatticeTbl::~CTNLatticeTbl(CTNLatticeTbl *this)
{
  __int64 i; // rdi
  void *v3; // r8

  if ( !*((_DWORD *)this + 39) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 36); i = (unsigned int)(i + 1) )
    {
      if ( *(int *)CChunkedArray<long>::operator[]((char *)this + 24, (unsigned int)i) > 0
        && *(_QWORD *)(*((_QWORD *)this + 1) + 8 * i) )
      {
        if ( (*(_BYTE *)(CChunkedArray<SPTEXTBUFWORD_SERIALIZED>::operator[]((char *)this + 104, (unsigned int)i) + 4)
            & 8) != 0 )
          CoTaskMemFree(v3);
        else
          CWinHeap::Free((CWinHeap *)&g_heap, v3);
      }
    }
  }
  CGrowableArrayVoid::~CGrowableArrayVoid((CTNLatticeTbl *)((char *)this + 104));
  CGrowableArrayVoid::~CGrowableArrayVoid((CTNLatticeTbl *)((char *)this + 64));
  CGrowableArrayVoid::~CGrowableArrayVoid((CTNLatticeTbl *)((char *)this + 24));
  CGrowableArrayVoid::~CGrowableArrayVoid(this);
}

```

## disassembly

```asm
0x18005b7e0  mov     [rsp+arg_0], rbx
0x18005b7e5  mov     [rsp+arg_8], rsi
0x18005b7ea  push    rdi
0x18005b7eb  sub     rsp, 20h
0x18005b7ef  cmp     dword ptr [rcx+9Ch], 0
0x18005b7f6  mov     rbx, rcx
0x18005b7f9  jnz     short loc_18005B857
0x18005b7fb  xor     edi, edi
0x18005b7fd  cmp     [rcx+90h], edi
0x18005b803  jbe     short loc_18005B857
0x18005b805  mov     edx, edi
0x18005b807  lea     rcx, [rbx+18h]
0x18005b80b  call    ??A?$CChunkedArray@J@@QEAAAEAJK@Z; CChunkedArray<long>::operator[](ulong)
0x18005b810  cmp     dword ptr [rax], 0
0x18005b813  jle     short loc_18005B84D
0x18005b815  mov     rax, [rbx+8]
0x18005b819  mov     r8, [rax+rdi*8]
0x18005b81d  test    r8, r8
0x18005b820  jz      short loc_18005B84D
0x18005b822  lea     rcx, [rbx+68h]
0x18005b826  mov     edx, edi
0x18005b828  call    ??A?$CChunkedArray@USPTEXTBUFWORD_SERIALIZED@@@@QEAAAEAUSPTEXTBUFWORD_SERIALIZED@@K@Z; CChunkedArray<SPTEXTBUFWORD_SERIALIZED>::operator[](ulong)
0x18005b82d  test    byte ptr [rax+4], 8
0x18005b831  jz      short loc_18005B83E
0x18005b833  mov     rcx, r8; pv
0x18005b836  call    cs:__imp_CoTaskMemFree
0x18005b83c  jmp     short loc_18005B84D
0x18005b83e  mov     rdx, r8; void *
0x18005b841  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18005b848  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18005b84d  inc     edi
0x18005b84f  cmp     edi, [rbx+90h]
0x18005b855  jb      short loc_18005B805
0x18005b857  lea     rcx, [rbx+68h]; this
0x18005b85b  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18005b860  lea     rcx, [rbx+40h]; this
0x18005b864  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18005b869  lea     rcx, [rbx+18h]; this
0x18005b86d  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18005b872  mov     rcx, rbx; this
0x18005b875  mov     rbx, [rsp+28h+arg_0]
0x18005b87a  mov     rsi, [rsp+28h+arg_8]
0x18005b87f  add     rsp, 20h
0x18005b883  pop     rdi
0x18005b884  jmp     ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
```
