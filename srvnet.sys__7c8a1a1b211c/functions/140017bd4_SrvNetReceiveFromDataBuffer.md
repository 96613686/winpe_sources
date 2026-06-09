# SrvNetReceiveFromDataBuffer

- ea: `0x140017bd4`
- end: `0x140017c9e`
- name: `SrvNetReceiveFromDataBuffer`
- size: `202`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002650`
- `0x1400027a0`
- `0x140018620`

## callees

- `0x140002060`
- `0x140017bd4`
- `0x14002a4c0`

## import_xrefs

- `TDI!TdiCopyBufferToMdl` at `0x140017c3d`
- `TDI!TdiCopyBufferToMdl` at `0x140017c3d`

## pseudocode

```c
__int64 __fastcall SrvNetReceiveFromDataBuffer(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rcx
  ULONG v3; // ebp
  _QWORD *v5; // rbx
  unsigned int v6; // edi
  ULONG v8; // ecx
  ULONG v9; // edx
  ULONG v10; // eax
  __int64 v11; // rax
  _QWORD *v12; // rcx
  ULONG BytesCopied; // [rsp+60h] [rbp+8h] BYREF

  v2 = (_QWORD *)(a1 + 88);
  v3 = 0;
  v5 = (_QWORD *)*v2;
  if ( (_QWORD *)*v2 == v2 )
  {
    v6 = -1073741595;
  }
  else
  {
    v8 = *(_DWORD *)a2;
    BytesCopied = 0;
    v9 = *((_DWORD *)v5 + 16);
    if ( v8 >= *((_DWORD *)v5 + 9) - v9 )
      v8 = *((_DWORD *)v5 + 9) - v9;
    if ( v8 )
    {
      v6 = TdiCopyBufferToMdl((PVOID)v5[3], v9, v8, *(PMDL *)(a2 + 8), 0, &BytesCopied);
      v10 = BytesCopied;
      *((_DWORD *)v5 + 16) += BytesCopied;
      v3 = v10;
      v9 = *((_DWORD *)v5 + 16);
      if ( !v6 && v9 != *((_DWORD *)v5 + 9) )
        v6 = -2147483643;
    }
    else
    {
      v6 = 0;
      v3 = 0;
    }
    if ( v9 == *((_DWORD *)v5 + 9) )
    {
      v11 = *v5;
      if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v12 = (_QWORD *)v5[1], (_QWORD *)*v12 != v5) )
        __fastfail(3u);
      *v12 = v11;
      *(_QWORD *)(v11 + 8) = v12;
      SrvNetFreeBuffer((unsigned __int16 *)v5);
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a2 + 16))(v6, v3, a2);
}

```

## disassembly

```asm
0x140017bd4  push    rbx
0x140017bd6  push    rbp
0x140017bd7  push    rsi
0x140017bd8  push    rdi
0x140017bd9  sub     rsp, 38h
0x140017bdd  add     rcx, 58h ; 'X'
0x140017be1  xor     ebp, ebp
0x140017be3  mov     rsi, rdx
0x140017be6  mov     rbx, [rcx]
0x140017be9  cmp     rbx, rcx
0x140017bec  jnz     short loc_140017C0D
0x140017bee  mov     edi, 0C00000E5h
0x140017bf3  mov     rax, [rsi+10h]
0x140017bf7  mov     r8, rsi
0x140017bfa  mov     edx, ebp
0x140017bfc  mov     ecx, edi
0x140017bfe  call    _guard_dispatch_icall
0x140017c03  add     rsp, 38h
0x140017c07  pop     rdi
0x140017c08  pop     rsi
0x140017c09  pop     rbp
0x140017c0a  pop     rbx
0x140017c0b  retn
0x140017c0d  mov     ecx, [rsi]
0x140017c0f  mov     [rsp+58h+arg_0], ebp
0x140017c13  mov     eax, [rbx+24h]
0x140017c16  mov     edx, [rbx+40h]; SourceOffset
0x140017c19  sub     eax, edx
0x140017c1b  cmp     ecx, eax
0x140017c1d  cmovnb  ecx, eax
0x140017c20  test    ecx, ecx
0x140017c22  jz      short loc_140017C68
0x140017c24  mov     r9, [rsi+8]; DestinationMdlChain
0x140017c28  lea     rax, [rsp+58h+arg_0]
0x140017c2d  mov     r8d, ecx; SourceBytesToCopy
0x140017c30  mov     [rsp+58h+BytesCopied], rax; BytesCopied
0x140017c35  mov     rcx, [rbx+18h]; SourceBuffer
0x140017c39  mov     [rsp+58h+DestinationOffset], ebp; DestinationOffset
0x140017c3d  call    cs:__imp_TdiCopyBufferToMdl
0x140017c44  nop     dword ptr [rax+rax+00h]
0x140017c49  mov     edi, eax
0x140017c4b  mov     eax, [rsp+58h+arg_0]
0x140017c4f  add     [rbx+40h], eax
0x140017c52  mov     ebp, eax
0x140017c54  mov     edx, [rbx+40h]
0x140017c57  test    edi, edi
0x140017c59  jnz     short loc_140017C6C
0x140017c5b  cmp     edx, [rbx+24h]
0x140017c5e  mov     eax, 80000005h
0x140017c63  cmovnz  edi, eax
0x140017c66  jmp     short loc_140017C6C
0x140017c68  xor     edi, edi
0x140017c6a  mov     ebp, ecx
0x140017c6c  cmp     edx, [rbx+24h]
0x140017c6f  jnz     short loc_140017BF3
0x140017c71  mov     rax, [rbx]
0x140017c74  cmp     [rax+8], rbx
0x140017c78  jnz     short loc_140017C97
0x140017c7a  mov     rcx, [rbx+8]
0x140017c7e  cmp     [rcx], rbx
0x140017c81  jnz     short loc_140017C97
0x140017c83  mov     [rcx], rax
0x140017c86  mov     [rax+8], rcx
0x140017c8a  mov     rcx, rbx; Entry
0x140017c8d  call    SrvNetFreeBuffer
0x140017c92  jmp     loc_140017BF3
0x140017c97  mov     ecx, 3
0x140017c9c  int     29h; Win8: RtlFailFast(ecx)
```
