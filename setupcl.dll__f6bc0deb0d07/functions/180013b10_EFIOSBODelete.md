# EFIOSBODelete

- ea: `0x180013b10`
- end: `0x180013bc4`
- name: `EFIOSBODelete`
- size: `180`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001378c`

## callees

- `0x180012ce8`
- `0x180012d4c`
- `0x180013b10`
- `0x180018010`

## pseudocode

```c
void __fastcall EFIOSBODelete(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v9 = 0;
    v2 = OSBOGetFirstBootEntry(a1, &v9);
    v3 = a1[8];
    if ( v2 )
    {
      do
      {
        v4 = *(_QWORD *)(v2 + 3144);
        (*(void (__fastcall **)(__int64))(v2 + 3152))(v2);
        v2 = v4;
      }
      while ( v4 );
    }
    v5 = a1[6];
    if ( v5 )
      SBE_FREE(v5);
    if ( v3 )
    {
      do
      {
        v6 = *(_QWORD *)(v3 + 2096);
        SBE_FREE(v3);
        v3 = v6;
      }
      while ( v6 );
    }
    v7 = a1[10];
    if ( v7 )
      SBE_FREE(v7);
    v8 = a1[18];
    if ( v8 )
      SBE_FREE(v8);
    SBE_FREE(a1);
  }
}

```

## disassembly

```asm
0x180013b10  test    rcx, rcx
0x180013b13  jz      locret_180013BC3
0x180013b19  mov     rax, rsp
0x180013b1c  mov     [rax+10h], rbx
0x180013b20  mov     [rax+18h], rsi
0x180013b24  push    rdi
0x180013b25  sub     rsp, 20h
0x180013b29  lea     rdx, [rax+8]
0x180013b2d  mov     dword ptr [rax+8], 0
0x180013b34  mov     rdi, rcx
0x180013b37  call    OSBOGetFirstBootEntry
0x180013b3c  mov     rsi, [rdi+40h]
0x180013b40  test    rax, rax
0x180013b43  jz      short loc_180013B63
0x180013b45  mov     rbx, [rax+0C48h]
0x180013b4c  mov     rcx, rax
0x180013b4f  mov     rax, [rax+0C50h]
0x180013b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b5b  mov     rax, rbx
0x180013b5e  test    rbx, rbx
0x180013b61  jnz     short loc_180013B45
0x180013b63  mov     rcx, [rdi+30h]
0x180013b67  test    rcx, rcx
0x180013b6a  jz      short loc_180013B71
0x180013b6c  call    SBE_FREE
0x180013b71  test    rsi, rsi
0x180013b74  jz      short loc_180013B8D
0x180013b76  mov     rbx, [rsi+830h]
0x180013b7d  mov     rcx, rsi
0x180013b80  call    SBE_FREE
0x180013b85  mov     rsi, rbx
0x180013b88  test    rbx, rbx
0x180013b8b  jnz     short loc_180013B76
0x180013b8d  mov     rcx, [rdi+50h]
0x180013b91  test    rcx, rcx
0x180013b94  jz      short loc_180013B9B
0x180013b96  call    SBE_FREE
0x180013b9b  mov     rcx, [rdi+90h]
0x180013ba2  test    rcx, rcx
0x180013ba5  jz      short loc_180013BAC
0x180013ba7  call    SBE_FREE
0x180013bac  mov     rcx, rdi
0x180013baf  call    SBE_FREE
0x180013bb4  mov     rbx, [rsp+28h+arg_8]
0x180013bb9  mov     rsi, [rsp+28h+arg_10]
0x180013bbe  add     rsp, 20h
0x180013bc2  pop     rdi
0x180013bc3  retn
```
