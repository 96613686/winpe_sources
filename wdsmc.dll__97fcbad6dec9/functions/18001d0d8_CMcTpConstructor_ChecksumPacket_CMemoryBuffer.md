# CMcTpConstructor::ChecksumPacket(CMemoryBuffer *)

- ea: `0x18001d0d8`
- end: `0x18001d194`
- name: `?ChecksumPacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `188`
- prototype: `unsigned int __fastcall(CMcTpConstructor *__hidden this, struct CMemoryBuffer *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d4f4`

## callees

- `0x18001d0d8`
- `0x1800227d4`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001d16e`
- `WS2_32!__imp_htonl` at `0x18001d16e`
- `WS2_32!__imp_htons` at `0x18001d144`
- `WS2_32!__imp_htons` at `0x18001d144`

## string_xrefs

- `0x18001d113`: `((((m_uSecurityMode) & 0xffff) == (3)) || ((((m_uSecurityMode)>>16)&0xffff) == (3)))`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::ChecksumPacket(
        CMcTpConstructor *this,
        struct CMemoryBuffer *a2,
        __int64 a3,
        int a4)
{
  int v4; // esi
  __int64 v7; // rbp
  __int64 v8; // rbx
  unsigned int v9; // edi
  unsigned __int64 i; // rcx
  int v11; // eax

  v4 = 0;
  if ( (unsigned __int16)*(_DWORD *)this != 3 && HIWORD(*(_DWORD *)this) != 3 )
    WdsAssert(
      "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp",
      0x368u,
      "((((m_uSecurityMode) & 0xffff) == (3)) || ((((m_uSecurityMode)>>16)&0xffff) == (3)))",
      a4,
      0);
  v7 = *((_QWORD *)a2 + 5);
  v8 = *((unsigned int *)this + 25);
  v9 = *((_DWORD *)a2 + 12) - v8;
  *(_BYTE *)(v7 + 2) = 3;
  *(_WORD *)(v7 + 3) = htons(4u);
  for ( i = 0; i < v9; v4 += v11 )
  {
    v11 = *(unsigned __int8 *)(i + v8 + v7);
    ++i;
  }
  *(_DWORD *)(v7 + 5) = htonl(~v4);
  return 0;
}

```

## disassembly

```asm
0x18001d0d8  mov     rax, rsp
0x18001d0db  mov     [rax+8], rbx
0x18001d0df  mov     [rax+10h], rbp
0x18001d0e3  mov     [rax+18h], rsi
0x18001d0e7  mov     [rax+20h], rdi
0x18001d0eb  push    r14
0x18001d0ed  sub     rsp, 30h
0x18001d0f1  mov     r8d, [rcx]
0x18001d0f4  xor     esi, esi
0x18001d0f6  movzx   eax, r8w
0x18001d0fa  mov     rdi, rdx
0x18001d0fd  mov     rbx, rcx
0x18001d100  lea     r14d, [rsi+3]
0x18001d104  cmp     eax, r14d
0x18001d107  jz      short loc_18001D12F
0x18001d109  shr     r8d, 10h
0x18001d10d  cmp     r8w, r14w
0x18001d111  jz      short loc_18001D12F
0x18001d113  lea     r8, aMUsecuritymode_0; "((((m_uSecurityMode) & 0xffff) == (3)) "...
0x18001d11a  mov     [rsp+38h+var_18], esi; int
0x18001d11e  mov     edx, 368h; unsigned int
0x18001d123  lea     rcx, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001d12a  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001d12f  mov     rbp, [rdi+28h]
0x18001d133  mov     ecx, 4; hostshort
0x18001d138  mov     ebx, [rbx+64h]
0x18001d13b  mov     edi, [rdi+30h]
0x18001d13e  sub     edi, ebx
0x18001d140  mov     [rbp+2], r14b
0x18001d144  call    cs:__imp_htons
0x18001d14a  mov     r8d, edi
0x18001d14d  lea     rdx, [rbx+rbp]
0x18001d151  mov     [rbp+3], ax
0x18001d155  mov     rcx, rsi
0x18001d158  test    edi, edi
0x18001d15a  jz      short loc_18001D16A
0x18001d15c  movzx   eax, byte ptr [rcx+rdx]
0x18001d160  inc     rcx
0x18001d163  add     esi, eax
0x18001d165  cmp     rcx, r8
0x18001d168  jb      short loc_18001D15C
0x18001d16a  not     esi
0x18001d16c  mov     ecx, esi; hostlong
0x18001d16e  call    cs:__imp_htonl
0x18001d174  mov     rbx, [rsp+38h+arg_0]
0x18001d179  mov     rsi, [rsp+38h+arg_10]
0x18001d17e  mov     rdi, [rsp+38h+arg_18]
0x18001d183  mov     [rbp+5], eax
0x18001d186  xor     eax, eax
0x18001d188  mov     rbp, [rsp+38h+arg_8]
0x18001d18d  add     rsp, 30h
0x18001d191  pop     r14
0x18001d193  retn
```
