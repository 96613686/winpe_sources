# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180025758`
- end: `0x180025841`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180012804`
- `0x180023e14`
- `0x180024e2c`
- `0x1800252bc`
- `0x180026638`

## callees

- `0x180025758`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800257a7`
- `msvcrt!memcpy_s` at `0x1800257dc`
- `msvcrt!memcpy_s` at `0x180025807`
- `msvcrt!memcpy_s` at `0x1800257a7`
- `msvcrt!memcpy_s` at `0x1800257dc`
- `msvcrt!memcpy_s` at `0x180025807`

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
0x180025758  mov     rax, rsp
0x18002575b  mov     [rax+10h], rbx
0x18002575f  mov     [rax+18h], rbp
0x180025763  push    rsi
0x180025764  push    rdi
0x180025765  push    r12
0x180025767  push    r14
0x180025769  push    r15
0x18002576b  sub     rsp, 20h
0x18002576f  xor     r15d, r15d
0x180025772  mov     rsi, r8
0x180025775  cmp     byte ptr [rcx+2], 1
0x180025779  mov     r12, rdx
0x18002577c  mov     r8, [rdx]; Source
0x18002577f  mov     rdi, rcx
0x180025782  jnz     short loc_1800257B7
0x180025784  lea     rbx, [r8+2]
0x180025788  cmp     rbx, rsi
0x18002578b  ja      loc_18002581C
0x180025791  lea     ebp, [r15+2]
0x180025795  mov     [rcx+10h], r8
0x180025799  mov     r9d, ebp; SourceSize
0x18002579c  mov     [rax+8], r15w
0x1800257a1  mov     edx, ebp; DestinationSize
0x1800257a3  lea     rcx, [rax+8]; Destination
0x1800257a7  call    cs:__imp_memcpy_s
0x1800257ad  movzx   eax, [rsp+48h+arg_0]
0x1800257b2  mov     [rdi+4], eax
0x1800257b5  jmp     short loc_1800257E2
0x1800257b7  mov     ebp, 2
0x1800257bc  mov     rbx, r8
0x1800257bf  cmp     [rcx+2], bpl
0x1800257c3  jnz     short loc_1800257E2
0x1800257c5  lea     rbx, [r8+4]
0x1800257c9  cmp     rbx, rsi
0x1800257cc  ja      short loc_18002581C
0x1800257ce  lea     edx, [rbp+2]; DestinationSize
0x1800257d1  mov     [rcx+10h], r8
0x1800257d5  mov     r9d, edx; SourceSize
0x1800257d8  add     rcx, 4; Destination
0x1800257dc  call    cs:__imp_memcpy_s
0x1800257e2  movzx   eax, word ptr [rdi]
0x1800257e5  lea     r14, [rdi+8]
0x1800257e9  mov     [r14], ax
0x1800257ed  test    ax, ax
0x1800257f0  jnz     short loc_180025810
0x1800257f2  lea     r15, [rbx+2]
0x1800257f6  cmp     r15, rsi
0x1800257f9  ja      short loc_18002581C
0x1800257fb  mov     r9, rbp; SourceSize
0x1800257fe  mov     r8, rbx; Source
0x180025801  mov     rdx, rbp; DestinationSize
0x180025804  mov     rcx, r14; Destination
0x180025807  call    cs:__imp_memcpy_s
0x18002580d  mov     rbx, r15
0x180025810  movzx   ecx, word ptr [r14]
0x180025814  add     rcx, rbx
0x180025817  cmp     rcx, rsi
0x18002581a  jbe     short loc_180025820
0x18002581c  xor     al, al
0x18002581e  jmp     short loc_18002582A
0x180025820  mov     [rdi+18h], rbx
0x180025824  mov     al, 1
0x180025826  mov     [r12], rcx
0x18002582a  mov     rbx, [rsp+48h+arg_8]
0x18002582f  mov     rbp, [rsp+48h+arg_10]
0x180025834  add     rsp, 20h
0x180025838  pop     r15
0x18002583a  pop     r14
0x18002583c  pop     r12
0x18002583e  pop     rdi
0x18002583f  pop     rsi
0x180025840  retn
```
