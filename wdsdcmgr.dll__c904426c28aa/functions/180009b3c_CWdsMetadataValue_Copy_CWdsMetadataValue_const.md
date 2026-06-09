# CWdsMetadataValue::Copy(CWdsMetadataValue const *)

- ea: `0x180009b3c`
- end: `0x180009c28`
- name: `?Copy@CWdsMetadataValue@@QEAAKPEBV1@@Z`
- size: `236`
- prototype: `__int64 __fastcall(CWdsMetadataValue *this, const struct CWdsMetadataValue *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000af78`

## callees

- `0x180009838`
- `0x180009b3c`
- `0x180013dcc`
- `0x180014d58`
- `0x1800150b8`
- `0x1800157a4`
- `0x180015c85`

## pseudocode

```c
__int64 __fastcall CWdsMetadataValue::Copy(CWdsMetadataValue *this, const struct CWdsMetadataValue *a2)
{
  void *v2; // rsi
  unsigned int v3; // ebp
  int v6; // eax
  const char *v7; // rdx
  void *v8; // rax
  void *v9; // rsi
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v3 = 0;
  Block = 0;
  if ( this != a2 )
  {
    CWdsMetadataValue::Shutdown(this);
    v6 = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 == 1 )
    {
      v3 = DuplicateStringW(*((const unsigned __int16 **)a2 + 1), (unsigned __int16 **)&Block);
      if ( !ElValidateWin32(v3, v7, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x5B5u) )
      {
        *((_QWORD *)this + 1) = Block;
        *(_DWORD *)this = 1;
        return v3;
      }
      v2 = Block;
    }
    else
    {
      if ( v6 == 7 )
      {
        v8 = operator new[](*((_QWORD *)a2 + 2), (const struct std::nothrow_t *)&std::nothrow);
        v9 = v8;
        if ( v8 )
        {
          memcpy_0(v8, *((const void **)a2 + 1), *((_QWORD *)a2 + 2));
          *(_DWORD *)this = 7;
          *((_QWORD *)this + 1) = v9;
          *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
        }
        else
        {
          return 8;
        }
        return v3;
      }
      *(_DWORD *)this = v6;
      *(_OWORD *)((char *)this + 8) = *(_OWORD *)((char *)a2 + 8);
    }
    if ( v2 )
      operator delete(v2);
  }
  return v3;
}

```

## disassembly

```asm
0x180009b3c  mov     rax, rsp
0x180009b3f  mov     [rax+10h], rbx
0x180009b43  mov     [rax+18h], rbp
0x180009b47  mov     [rax+20h], rsi
0x180009b4b  push    rdi
0x180009b4c  sub     rsp, 20h
0x180009b50  xor     esi, esi
0x180009b52  xor     ebp, ebp
0x180009b54  mov     [rax+8], rsi
0x180009b58  mov     rdi, rdx
0x180009b5b  mov     rbx, rcx
0x180009b5e  cmp     rcx, rdx
0x180009b61  jz      loc_180009C11
0x180009b67  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180009b6c  mov     eax, [rdi]
0x180009b6e  cmp     eax, 1
0x180009b71  jnz     short loc_180009BB3
0x180009b73  mov     rcx, [rdi+8]; unsigned __int16 *
0x180009b77  lea     rdx, [rsp+28h+Block]; unsigned __int16 **
0x180009b7c  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180009b81  mov     r9d, 5B5h; unsigned int
0x180009b87  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009b8e  mov     ecx, eax; unsigned int
0x180009b90  mov     ebp, eax
0x180009b92  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009b97  test    eax, eax
0x180009b99  jnz     short loc_180009BAC
0x180009b9b  mov     rcx, [rsp+28h+Block]
0x180009ba0  mov     [rbx+8], rcx
0x180009ba4  mov     dword ptr [rbx], 1
0x180009baa  jmp     short loc_180009C11
0x180009bac  mov     rsi, [rsp+28h+Block]
0x180009bb1  jmp     short loc_180009C04
0x180009bb3  cmp     eax, 7
0x180009bb6  jnz     short loc_180009BF9
0x180009bb8  mov     rcx, [rdi+10h]; unsigned __int64
0x180009bbc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009bc3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009bc8  mov     rsi, rax
0x180009bcb  test    rax, rax
0x180009bce  jnz     short loc_180009BD5
0x180009bd0  lea     ebp, [rax+8]
0x180009bd3  jmp     short loc_180009C11
0x180009bd5  mov     r8, [rdi+10h]; Size
0x180009bd9  mov     rcx, rsi; void *
0x180009bdc  mov     rdx, [rdi+8]; Src
0x180009be0  call    memcpy_0
0x180009be5  mov     dword ptr [rbx], 7
0x180009beb  mov     [rbx+8], rsi
0x180009bef  mov     rax, [rdi+10h]
0x180009bf3  mov     [rbx+10h], rax
0x180009bf7  jmp     short loc_180009C11
0x180009bf9  mov     [rbx], eax
0x180009bfb  movups  xmm0, xmmword ptr [rdi+8]
0x180009bff  movdqu  xmmword ptr [rbx+8], xmm0
0x180009c04  test    rsi, rsi
0x180009c07  jz      short loc_180009C11
0x180009c09  mov     rcx, rsi; Block
0x180009c0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009c11  mov     rbx, [rsp+28h+arg_8]
0x180009c16  mov     eax, ebp
0x180009c18  mov     rbp, [rsp+28h+arg_10]
0x180009c1d  mov     rsi, [rsp+28h+arg_18]
0x180009c22  add     rsp, 20h
0x180009c26  pop     rdi
0x180009c27  retn
```
