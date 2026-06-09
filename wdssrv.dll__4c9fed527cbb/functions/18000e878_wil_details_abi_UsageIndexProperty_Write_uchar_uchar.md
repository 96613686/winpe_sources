# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000e878`
- end: `0x18000e981`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `265`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bc4c`

## callees

- `0x18000e878`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e8e6`
- `msvcrt!memcpy_s` at `0x18000e91a`
- `msvcrt!memcpy_s` at `0x18000e94d`
- `msvcrt!memcpy_s` at `0x18000e8e6`
- `msvcrt!memcpy_s` at `0x18000e91a`
- `msvcrt!memcpy_s` at `0x18000e94d`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v4; // rbx
  char *v7; // r14
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v4, v10, v8, v9);
  v4 = v7;
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v4 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v4, a3 - v4, (char *)this + 8, 2u);
      v4 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v4[v12] > a3 )
    return 0;
  memcpy_s(v4, a3 - v4, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v4[*v11];
  return result;
}

```

## disassembly

```asm
0x18000e878  mov     r11, rsp
0x18000e87b  mov     [r11+10h], rbx
0x18000e87f  mov     [r11+18h], rsi
0x18000e883  mov     [r11+20h], rdi
0x18000e887  push    r12
0x18000e889  push    r14
0x18000e88b  push    r15
0x18000e88d  sub     rsp, 20h
0x18000e891  cmp     byte ptr [rcx+2], 1
0x18000e895  mov     rdi, r8
0x18000e898  mov     rbx, [rdx]
0x18000e89b  mov     r12, rdx
0x18000e89e  mov     rsi, rcx
0x18000e8a1  jnz     short loc_18000E8C8
0x18000e8a3  lea     r14, [rbx+2]
0x18000e8a7  cmp     r14, r8
0x18000e8aa  ja      loc_18000E93C
0x18000e8b0  movzx   eax, word ptr [rcx+4]
0x18000e8b4  lea     r8, [r11+8]
0x18000e8b8  mov     r9d, 2
0x18000e8be  mov     [rsp+38h+arg_0], ax
0x18000e8c3  mov     edx, r9d
0x18000e8c6  jmp     short loc_18000E8E3
0x18000e8c8  cmp     byte ptr [rcx+2], 2
0x18000e8cc  jnz     short loc_18000E8F5
0x18000e8ce  lea     r14, [rbx+4]
0x18000e8d2  cmp     r14, rdi
0x18000e8d5  ja      short loc_18000E93C
0x18000e8d7  mov     edx, 4; DestinationSize
0x18000e8dc  lea     r8, [rcx+4]; Source
0x18000e8e0  mov     r9d, edx; SourceSize
0x18000e8e3  mov     rcx, rbx; Destination
0x18000e8e6  call    cs:__imp_memcpy_s
0x18000e8ed  nop     dword ptr [rax+rax+00h]
0x18000e8f2  mov     rbx, r14
0x18000e8f5  cmp     word ptr [rsi], 0
0x18000e8f9  jnz     short loc_18000E92B
0x18000e8fb  lea     r15, [rbx+2]
0x18000e8ff  cmp     r15, rdi
0x18000e902  ja      short loc_18000E93C
0x18000e904  lea     r14, [rsi+8]
0x18000e908  mov     rdx, rdi
0x18000e90b  sub     rdx, rbx; DestinationSize
0x18000e90e  mov     r8, r14; Source
0x18000e911  mov     r9d, 2; SourceSize
0x18000e917  mov     rcx, rbx; Destination
0x18000e91a  call    cs:__imp_memcpy_s
0x18000e921  nop     dword ptr [rax+rax+00h]
0x18000e926  mov     rbx, r15
0x18000e929  jmp     short loc_18000E92F
0x18000e92b  lea     r14, [rsi+8]
0x18000e92f  movzx   r9d, word ptr [r14]; SourceSize
0x18000e933  lea     rax, [r9+rbx]
0x18000e937  cmp     rax, rdi
0x18000e93a  jbe     short loc_18000E940
0x18000e93c  xor     al, al
0x18000e93e  jmp     short loc_18000E966
0x18000e940  mov     r8, [rsi+18h]; Source
0x18000e944  sub     rdi, rbx
0x18000e947  mov     rdx, rdi; DestinationSize
0x18000e94a  mov     rcx, rbx; Destination
0x18000e94d  call    cs:__imp_memcpy_s
0x18000e954  nop     dword ptr [rax+rax+00h]
0x18000e959  movzx   ecx, word ptr [r14]
0x18000e95d  mov     al, 1
0x18000e95f  add     rcx, rbx
0x18000e962  mov     [r12], rcx
0x18000e966  mov     rbx, [rsp+38h+arg_8]
0x18000e96b  mov     rsi, [rsp+38h+arg_10]
0x18000e970  mov     rdi, [rsp+38h+arg_18]
0x18000e975  add     rsp, 20h
0x18000e979  pop     r15
0x18000e97b  pop     r14
0x18000e97d  pop     r12
0x18000e97f  retn
```
