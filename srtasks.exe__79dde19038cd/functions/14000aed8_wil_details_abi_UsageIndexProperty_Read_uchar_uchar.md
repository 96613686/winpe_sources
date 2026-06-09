# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000aed8`
- end: `0x14000afc1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000985c`
- `0x14000b500`
- `0x14000b888`

## callees

- `0x14000aed8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000af27`
- `msvcrt!memcpy_s` at `0x14000af5c`
- `msvcrt!memcpy_s` at `0x14000af87`
- `msvcrt!memcpy_s` at `0x14000af27`
- `msvcrt!memcpy_s` at `0x14000af5c`
- `msvcrt!memcpy_s` at `0x14000af87`

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
0x14000aed8  mov     rax, rsp
0x14000aedb  mov     [rax+10h], rbx
0x14000aedf  mov     [rax+18h], rbp
0x14000aee3  push    rsi
0x14000aee4  push    rdi
0x14000aee5  push    r12
0x14000aee7  push    r14
0x14000aee9  push    r15
0x14000aeeb  sub     rsp, 20h
0x14000aeef  xor     r15d, r15d
0x14000aef2  mov     rsi, r8
0x14000aef5  cmp     byte ptr [rcx+2], 1
0x14000aef9  mov     r12, rdx
0x14000aefc  mov     r8, [rdx]; Source
0x14000aeff  mov     rdi, rcx
0x14000af02  jnz     short loc_14000AF37
0x14000af04  lea     rbx, [r8+2]
0x14000af08  cmp     rbx, rsi
0x14000af0b  ja      loc_14000AF9C
0x14000af11  lea     ebp, [r15+2]
0x14000af15  mov     [rcx+10h], r8
0x14000af19  mov     r9d, ebp; SourceSize
0x14000af1c  mov     [rax+8], r15w
0x14000af21  mov     edx, ebp; DestinationSize
0x14000af23  lea     rcx, [rax+8]; Destination
0x14000af27  call    cs:__imp_memcpy_s
0x14000af2d  movzx   eax, [rsp+48h+arg_0]
0x14000af32  mov     [rdi+4], eax
0x14000af35  jmp     short loc_14000AF62
0x14000af37  mov     ebp, 2
0x14000af3c  mov     rbx, r8
0x14000af3f  cmp     [rcx+2], bpl
0x14000af43  jnz     short loc_14000AF62
0x14000af45  lea     rbx, [r8+4]
0x14000af49  cmp     rbx, rsi
0x14000af4c  ja      short loc_14000AF9C
0x14000af4e  lea     edx, [rbp+2]; DestinationSize
0x14000af51  mov     [rcx+10h], r8
0x14000af55  mov     r9d, edx; SourceSize
0x14000af58  add     rcx, 4; Destination
0x14000af5c  call    cs:__imp_memcpy_s
0x14000af62  movzx   eax, word ptr [rdi]
0x14000af65  lea     r14, [rdi+8]
0x14000af69  mov     [r14], ax
0x14000af6d  test    ax, ax
0x14000af70  jnz     short loc_14000AF90
0x14000af72  lea     r15, [rbx+2]
0x14000af76  cmp     r15, rsi
0x14000af79  ja      short loc_14000AF9C
0x14000af7b  mov     r9, rbp; SourceSize
0x14000af7e  mov     r8, rbx; Source
0x14000af81  mov     rdx, rbp; DestinationSize
0x14000af84  mov     rcx, r14; Destination
0x14000af87  call    cs:__imp_memcpy_s
0x14000af8d  mov     rbx, r15
0x14000af90  movzx   ecx, word ptr [r14]
0x14000af94  add     rcx, rbx
0x14000af97  cmp     rcx, rsi
0x14000af9a  jbe     short loc_14000AFA0
0x14000af9c  xor     al, al
0x14000af9e  jmp     short loc_14000AFAA
0x14000afa0  mov     [rdi+18h], rbx
0x14000afa4  mov     al, 1
0x14000afa6  mov     [r12], rcx
0x14000afaa  mov     rbx, [rsp+48h+arg_8]
0x14000afaf  mov     rbp, [rsp+48h+arg_10]
0x14000afb4  add     rsp, 20h
0x14000afb8  pop     r15
0x14000afba  pop     r14
0x14000afbc  pop     r12
0x14000afbe  pop     rdi
0x14000afbf  pop     rsi
0x14000afc0  retn
```
