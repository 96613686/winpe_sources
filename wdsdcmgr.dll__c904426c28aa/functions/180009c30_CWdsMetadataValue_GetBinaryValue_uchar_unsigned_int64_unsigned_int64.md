# CWdsMetadataValue::GetBinaryValue(uchar *,unsigned __int64,unsigned __int64 *)

- ea: `0x180009c30`
- end: `0x180009c8e`
- name: `?GetBinaryValue@CWdsMetadataValue@@QEBAKPEAE_KPEA_K@Z`
- size: `94`
- prototype: `__int64 __fastcall(CWdsMetadataValue *this, unsigned __int8 *, size_t, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042f4`
- `0x1800105d0`
- `0x180011000`
- `0x1800123a0`

## callees

- `0x180009c30`
- `0x180014d58`
- `0x180015c85`

## pseudocode

```c
__int64 __fastcall CWdsMetadataValue::GetBinaryValue(
        CWdsMetadataValue *this,
        unsigned __int8 *a2,
        size_t a3,
        unsigned __int64 *a4)
{
  unsigned int v4; // ebx
  size_t v6; // r8

  v4 = 0;
  if ( *(_DWORD *)this == 7 )
  {
    *a4 = *((_QWORD *)this + 2);
    if ( a2 )
    {
      v6 = *((_QWORD *)this + 2);
      if ( v6 <= a3 )
        memcpy_0(a2, *((const void **)this + 1), v6);
      else
        return 122;
    }
  }
  else
  {
    return ElValidateWin32(0xDu, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x6FDu);
  }
  return v4;
}

```

## disassembly

```asm
0x180009c30  push    rbx
0x180009c32  sub     rsp, 20h
0x180009c36  xor     ebx, ebx
0x180009c38  mov     r11, r8
0x180009c3b  cmp     dword ptr [rcx], 7
0x180009c3e  mov     r10, rdx
0x180009c41  jnz     short loc_180009C6D
0x180009c43  mov     rax, [rcx+10h]
0x180009c47  mov     [r9], rax
0x180009c4a  test    rdx, rdx
0x180009c4d  jz      short loc_180009C86
0x180009c4f  mov     r8, [rcx+10h]; Size
0x180009c53  cmp     r8, r11
0x180009c56  jbe     short loc_180009C5F
0x180009c58  mov     ebx, 7Ah ; 'z'
0x180009c5d  jmp     short loc_180009C86
0x180009c5f  mov     rdx, [rcx+8]; Src
0x180009c63  mov     rcx, r10; void *
0x180009c66  call    memcpy_0
0x180009c6b  jmp     short loc_180009C86
0x180009c6d  mov     r9d, 6FDh; unsigned int
0x180009c73  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009c7a  mov     ecx, 0Dh; unsigned int
0x180009c7f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009c84  mov     ebx, eax
0x180009c86  mov     eax, ebx
0x180009c88  add     rsp, 20h
0x180009c8c  pop     rbx
0x180009c8d  retn
```
