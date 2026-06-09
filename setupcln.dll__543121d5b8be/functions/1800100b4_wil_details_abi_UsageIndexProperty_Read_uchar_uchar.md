# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800100b4`
- end: `0x18001019d`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e4b4`
- `0x18000f514`
- `0x18000f9d0`
- `0x180010654`
- `0x1800112e4`

## callees

- `0x1800100b4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010103`
- `msvcrt!memcpy_s` at `0x180010138`
- `msvcrt!memcpy_s` at `0x180010163`
- `msvcrt!memcpy_s` at `0x180010103`
- `msvcrt!memcpy_s` at `0x180010138`
- `msvcrt!memcpy_s` at `0x180010163`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x1800100b4  mov     rax, rsp
0x1800100b7  mov     [rax+10h], rbx
0x1800100bb  mov     [rax+18h], rbp
0x1800100bf  push    rsi
0x1800100c0  push    rdi
0x1800100c1  push    r12
0x1800100c3  push    r14
0x1800100c5  push    r15
0x1800100c7  sub     rsp, 20h
0x1800100cb  xor     r15d, r15d
0x1800100ce  mov     rsi, r8
0x1800100d1  cmp     byte ptr [rcx+2], 1
0x1800100d5  mov     r12, rdx
0x1800100d8  mov     r8, [rdx]; Source
0x1800100db  mov     rdi, rcx
0x1800100de  jnz     short loc_180010113
0x1800100e0  lea     rbx, [r8+2]
0x1800100e4  cmp     rbx, rsi
0x1800100e7  ja      loc_180010178
0x1800100ed  lea     ebp, [r15+2]
0x1800100f1  mov     [rcx+10h], r8
0x1800100f5  mov     r9d, ebp; SourceSize
0x1800100f8  mov     [rax+8], r15w
0x1800100fd  mov     edx, ebp; DestinationSize
0x1800100ff  lea     rcx, [rax+8]; Destination
0x180010103  call    cs:__imp_memcpy_s
0x180010109  movzx   eax, [rsp+48h+arg_0]
0x18001010e  mov     [rdi+4], eax
0x180010111  jmp     short loc_18001013E
0x180010113  mov     ebp, 2
0x180010118  mov     rbx, r8
0x18001011b  cmp     [rcx+2], bpl
0x18001011f  jnz     short loc_18001013E
0x180010121  lea     rbx, [r8+4]
0x180010125  cmp     rbx, rsi
0x180010128  ja      short loc_180010178
0x18001012a  lea     edx, [rbp+2]; DestinationSize
0x18001012d  mov     [rcx+10h], r8
0x180010131  mov     r9d, edx; SourceSize
0x180010134  add     rcx, 4; Destination
0x180010138  call    cs:__imp_memcpy_s
0x18001013e  movzx   eax, word ptr [rdi]
0x180010141  lea     r14, [rdi+8]
0x180010145  mov     [r14], ax
0x180010149  test    ax, ax
0x18001014c  jnz     short loc_18001016C
0x18001014e  lea     r15, [rbx+2]
0x180010152  cmp     r15, rsi
0x180010155  ja      short loc_180010178
0x180010157  mov     r9, rbp; SourceSize
0x18001015a  mov     r8, rbx; Source
0x18001015d  mov     rdx, rbp; DestinationSize
0x180010160  mov     rcx, r14; Destination
0x180010163  call    cs:__imp_memcpy_s
0x180010169  mov     rbx, r15
0x18001016c  movzx   ecx, word ptr [r14]
0x180010170  add     rcx, rbx
0x180010173  cmp     rcx, rsi
0x180010176  jbe     short loc_18001017C
0x180010178  xor     al, al
0x18001017a  jmp     short loc_180010186
0x18001017c  mov     [rdi+18h], rbx
0x180010180  mov     al, 1
0x180010182  mov     [r12], rcx
0x180010186  mov     rbx, [rsp+48h+arg_8]
0x18001018b  mov     rbp, [rsp+48h+arg_10]
0x180010190  add     rsp, 20h
0x180010194  pop     r15
0x180010196  pop     r14
0x180010198  pop     r12
0x18001019a  pop     rdi
0x18001019b  pop     rsi
0x18001019c  retn
```
