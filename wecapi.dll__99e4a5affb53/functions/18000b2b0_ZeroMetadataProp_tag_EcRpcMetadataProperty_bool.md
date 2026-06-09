# ZeroMetadataProp(tag_EcRpcMetadataProperty &,bool)

- ea: `0x18000b2b0`
- end: `0x18000b379`
- name: `?ZeroMetadataProp@@YAXAEAUtag_EcRpcMetadataProperty@@_N@Z`
- size: `201`
- prototype: `void(struct tag_EcRpcMetadataProperty *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a640`
- `0x18000ad88`

## callees

- `0x1800026c0`
- `0x18000a6b0`
- `0x18000b2b0`

## pseudocode

```c
void __fastcall ZeroMetadataProp(struct tag_EcRpcMetadataProperty *a1, char a2)
{
  struct tag_EcRpcMetadataProperty *v2; // rbx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  _BYTE *v6; // rcx
  __int64 j; // rax
  void *v8; // rcx
  __int64 v9; // rax
  _BYTE *v10; // rcx
  _BYTE *v11; // rax
  __int64 v12; // rcx
  __int64 i; // rcx
  __int64 v14; // rax

  v2 = a1;
  v3 = *(_DWORD *)a1 - 4;
  if ( !v3 )
  {
    if ( a2 )
    {
      v11 = (_BYTE *)*((_QWORD *)v2 + 1);
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&v11[2 * v12] );
      for ( i = 2 * v12; i; --i )
        *v11++ = 0;
    }
    v8 = (void *)*((_QWORD *)v2 + 1);
    goto LABEL_20;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    if ( a2 )
    {
      v9 = *((unsigned int *)v2 + 2);
      v10 = (_BYTE *)*((_QWORD *)v2 + 2);
      if ( *((_DWORD *)v2 + 2) )
      {
        do
        {
          *v10++ = 0;
          --v9;
        }
        while ( v9 );
      }
    }
    goto LABEL_8;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      if ( a2 )
      {
        v6 = (_BYTE *)*((_QWORD *)v2 + 2);
        for ( j = 4LL * *((unsigned int *)v2 + 2); j; --j )
          *v6++ = 0;
      }
LABEL_8:
      v8 = (void *)*((_QWORD *)v2 + 2);
LABEL_20:
      operator delete(v8);
    }
  }
  else
  {
    CleanupStringVector(*((_DWORD *)v2 + 2), *((unsigned __int16 ***)v2 + 2), a2);
  }
  v14 = 24;
  do
  {
    *(_BYTE *)v2 = 0;
    v2 = (struct tag_EcRpcMetadataProperty *)((char *)v2 + 1);
    --v14;
  }
  while ( v14 );
}

```

## disassembly

```asm
0x18000b2b0  mov     [rsp+arg_0], rbx
0x18000b2b5  push    rdi
0x18000b2b6  sub     rsp, 20h
0x18000b2ba  mov     rbx, rcx
0x18000b2bd  xor     edi, edi
0x18000b2bf  mov     ecx, [rcx]
0x18000b2c1  sub     ecx, 4
0x18000b2c4  jz      short loc_18000B32E
0x18000b2c6  sub     ecx, 1
0x18000b2c9  jz      short loc_18000B310
0x18000b2cb  sub     ecx, 1
0x18000b2ce  jz      short loc_18000B2FF
0x18000b2d0  cmp     ecx, 1
0x18000b2d3  jnz     loc_18000B35D
0x18000b2d9  test    dl, dl
0x18000b2db  jz      short loc_18000B2F9
0x18000b2dd  mov     eax, [rbx+8]
0x18000b2e0  mov     rcx, [rbx+10h]
0x18000b2e4  shl     rax, 2
0x18000b2e8  test    rax, rax
0x18000b2eb  jz      short loc_18000B2F9
0x18000b2ed  mov     [rcx], dil
0x18000b2f0  inc     rcx
0x18000b2f3  sub     rax, 1
0x18000b2f7  jnz     short loc_18000B2ED
0x18000b2f9  mov     rcx, [rbx+10h]
0x18000b2fd  jmp     short loc_18000B358
0x18000b2ff  mov     ecx, [rbx+8]; unsigned int
0x18000b302  mov     r8b, dl; bool
0x18000b305  mov     rdx, [rbx+10h]; unsigned __int16 **
0x18000b309  call    ?CleanupStringVector@@YAXKPEAPEAG_N@Z; CleanupStringVector(ulong,ushort * *,bool)
0x18000b30e  jmp     short loc_18000B35D
0x18000b310  test    dl, dl
0x18000b312  jz      short loc_18000B2F9
0x18000b314  mov     eax, [rbx+8]
0x18000b317  mov     rcx, [rbx+10h]
0x18000b31b  test    rax, rax
0x18000b31e  jz      short loc_18000B2F9
0x18000b320  mov     [rcx], dil
0x18000b323  inc     rcx
0x18000b326  sub     rax, 1
0x18000b32a  jnz     short loc_18000B320
0x18000b32c  jmp     short loc_18000B2F9
0x18000b32e  test    dl, dl
0x18000b330  jz      short loc_18000B354
0x18000b332  mov     rax, [rbx+8]
0x18000b336  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b33a  inc     rcx
0x18000b33d  cmp     [rax+rcx*2], di
0x18000b341  jnz     short loc_18000B33A
0x18000b343  add     rcx, rcx
0x18000b346  jz      short loc_18000B354
0x18000b348  mov     [rax], dil
0x18000b34b  inc     rax
0x18000b34e  sub     rcx, 1
0x18000b352  jnz     short loc_18000B348
0x18000b354  mov     rcx, [rbx+8]; void *
0x18000b358  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b35d  mov     eax, 18h
0x18000b362  mov     [rbx], dil
0x18000b365  inc     rbx
0x18000b368  sub     rax, 1
0x18000b36c  jnz     short loc_18000B362
0x18000b36e  mov     rbx, [rsp+28h+arg_0]
0x18000b373  add     rsp, 20h
0x18000b377  pop     rdi
0x18000b378  retn
```
