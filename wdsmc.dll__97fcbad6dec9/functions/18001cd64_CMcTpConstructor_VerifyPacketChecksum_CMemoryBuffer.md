# CMcTpConstructor::VerifyPacketChecksum(CMemoryBuffer *)

- ea: `0x18001cd64`
- end: `0x18001ce56`
- name: `?VerifyPacketChecksum@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(CMcTpConstructor *this, struct CMemoryBuffer *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015c34`

## callees

- `0x18001cd64`
- `0x1800227d4`
- `0x180026d3a`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x18001ce15`
- `WS2_32!__imp_ntohl` at `0x18001ce15`
- `WS2_32!__imp_ntohs` at `0x18001cdea`
- `WS2_32!__imp_ntohs` at `0x18001cdea`

## string_xrefs

- `0x18001cda5`: `((((m_uSecurityMode) & 0xffff) == (3)) || ((((m_uSecurityMode)>>16)&0xffff) == (3)))`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::VerifyPacketChecksum(
        CMcTpConstructor *this,
        struct CMemoryBuffer *a2,
        __int64 a3,
        int a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  unsigned int v7; // ebp
  bool v8; // zf
  unsigned int v9; // ebp
  int v10; // esi
  unsigned __int64 v11; // rdx
  int v12; // eax

  v4 = 0;
  v5 = *((_QWORD *)a2 + 5);
  v7 = *((_DWORD *)a2 + 12);
  if ( (unsigned __int16)*(_DWORD *)this != 3 && HIWORD(*(_DWORD *)this) != 3 )
    WdsAssert(
      "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp",
      0x16Eu,
      "((((m_uSecurityMode) & 0xffff) == (3)) || ((((m_uSecurityMode)>>16)&0xffff) == (3)))",
      a4,
      0);
  if ( v7 >= 9 && *(_WORD *)v5 == *(_WORD *)"WD" )
  {
    if ( *(_BYTE *)(v5 + 2) != 3 )
      return (unsigned int)-1054801649;
    if ( ntohs(*(_WORD *)(v5 + 3)) == 4 )
    {
      v8 = v7 == 9;
      v9 = v7 - 9;
      v10 = 0;
      v11 = 0;
      if ( !v8 )
      {
        do
        {
          v12 = *(unsigned __int8 *)(v11 + v5 + 9);
          ++v11;
          v10 += v12;
        }
        while ( v11 < v9 );
      }
      if ( ~v10 == ntohl(*(_DWORD *)(v5 + 5)) )
      {
        memmove_0(*((void **)a2 + 5), (const void *)(v5 + 9), v9);
        *((_DWORD *)a2 + 12) = v9;
        return v4;
      }
    }
  }
  return 13;
}

```

## disassembly

```asm
0x18001cd64  mov     rax, rsp
0x18001cd67  mov     [rax+8], rbx
0x18001cd6b  mov     [rax+10h], rbp
0x18001cd6f  mov     [rax+18h], rsi
0x18001cd73  mov     [rax+20h], rdi
0x18001cd77  push    r13
0x18001cd79  push    r14
0x18001cd7b  push    r15
0x18001cd7d  sub     rsp, 30h
0x18001cd81  mov     r8d, [rcx]
0x18001cd84  xor     ebx, ebx
0x18001cd86  mov     rdi, [rdx+28h]
0x18001cd8a  mov     r15, rdx
0x18001cd8d  mov     ebp, [rdx+30h]
0x18001cd90  movzx   eax, r8w
0x18001cd94  lea     esi, [rbx+3]
0x18001cd97  cmp     eax, esi
0x18001cd99  jz      short loc_18001CDC1
0x18001cd9b  shr     r8d, 10h
0x18001cd9f  cmp     r8w, si
0x18001cda3  jz      short loc_18001CDC1
0x18001cda5  lea     r8, aMUsecuritymode_0; "((((m_uSecurityMode) & 0xffff) == (3)) "...
0x18001cdac  mov     [rsp+48h+var_28], ebx; int
0x18001cdb0  mov     edx, 16Eh; unsigned int
0x18001cdb5  lea     rcx, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001cdbc  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001cdc1  cmp     ebp, 9
0x18001cdc4  jnb     short loc_18001CDCD
0x18001cdc6  mov     ebx, 0Dh
0x18001cdcb  jmp     short loc_18001CE35
0x18001cdcd  movzx   eax, word ptr [rdi]
0x18001cdd0  cmp     ax, word ptr cs:aWd; "WD"
0x18001cdd7  jnz     short loc_18001CDC6
0x18001cdd9  cmp     [rdi+2], sil
0x18001cddd  jz      short loc_18001CDE6
0x18001cddf  mov     ebx, 0C121010Fh
0x18001cde4  jmp     short loc_18001CE35
0x18001cde6  movzx   ecx, word ptr [rdi+3]; netshort
0x18001cdea  call    cs:__imp_ntohs
0x18001cdf0  cmp     ax, 4
0x18001cdf4  jnz     short loc_18001CDC6
0x18001cdf6  add     ebp, 0FFFFFFF7h
0x18001cdf9  mov     esi, ebx
0x18001cdfb  mov     r14d, ebp
0x18001cdfe  mov     rdx, rbx
0x18001ce01  jz      short loc_18001CE12
0x18001ce03  movzx   eax, byte ptr [rdx+rdi+9]
0x18001ce08  inc     rdx
0x18001ce0b  add     esi, eax
0x18001ce0d  cmp     rdx, r14
0x18001ce10  jb      short loc_18001CE03
0x18001ce12  mov     ecx, [rdi+5]; netlong
0x18001ce15  call    cs:__imp_ntohl
0x18001ce1b  not     esi
0x18001ce1d  cmp     esi, eax
0x18001ce1f  jnz     short loc_18001CDC6
0x18001ce21  mov     rcx, [r15+28h]; void *
0x18001ce25  lea     rdx, [rdi+9]; Src
0x18001ce29  mov     r8, r14; Size
0x18001ce2c  call    memmove_0
0x18001ce31  mov     [r15+30h], ebp
0x18001ce35  mov     rbp, [rsp+48h+arg_8]
0x18001ce3a  mov     eax, ebx
0x18001ce3c  mov     rbx, [rsp+48h+arg_0]
0x18001ce41  mov     rsi, [rsp+48h+arg_10]
0x18001ce46  mov     rdi, [rsp+48h+arg_18]
0x18001ce4b  add     rsp, 30h
0x18001ce4f  pop     r15
0x18001ce51  pop     r14
0x18001ce53  pop     r13
0x18001ce55  retn
```
