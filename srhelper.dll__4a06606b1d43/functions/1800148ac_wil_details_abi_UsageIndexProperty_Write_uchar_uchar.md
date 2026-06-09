# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800148ac`
- end: `0x180014985`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800130e0`

## callees

- `0x1800148ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001490c`
- `msvcrt!memcpy_s` at `0x180014937`
- `msvcrt!memcpy_s` at `0x180014964`
- `msvcrt!memcpy_s` at `0x18001490c`
- `msvcrt!memcpy_s` at `0x180014937`
- `msvcrt!memcpy_s` at `0x180014964`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x1800148ac  push    rbx
0x1800148ae  push    rsi
0x1800148af  push    rdi
0x1800148b0  push    r12
0x1800148b2  push    r14
0x1800148b4  push    r15
0x1800148b6  sub     rsp, 28h
0x1800148ba  mov     rsi, rcx
0x1800148bd  mov     rdi, r8
0x1800148c0  mov     rcx, [rdx]; Destination
0x1800148c3  mov     r12, rdx
0x1800148c6  cmp     byte ptr [rsi+2], 1
0x1800148ca  jnz     short loc_1800148EE
0x1800148cc  lea     rbx, [rcx+2]
0x1800148d0  cmp     rbx, r8
0x1800148d3  ja      short loc_180014953
0x1800148d5  movzx   eax, word ptr [rsi+4]
0x1800148d9  lea     r8, [rsp+58h+arg_0]
0x1800148de  mov     r9d, 2
0x1800148e4  mov     [rsp+58h+arg_0], ax
0x1800148e9  mov     edx, r9d
0x1800148ec  jmp     short loc_18001490C
0x1800148ee  cmp     byte ptr [rsi+2], 2
0x1800148f2  mov     rbx, rcx
0x1800148f5  jnz     short loc_180014912
0x1800148f7  lea     rbx, [rcx+4]
0x1800148fb  cmp     rbx, rdi
0x1800148fe  ja      short loc_180014953
0x180014900  mov     edx, 4; DestinationSize
0x180014905  lea     r8, [rsi+4]; Source
0x180014909  mov     r9d, edx; SourceSize
0x18001490c  call    cs:__imp_memcpy_s
0x180014912  cmp     word ptr [rsi], 0
0x180014916  jnz     short loc_180014942
0x180014918  lea     r15, [rbx+2]
0x18001491c  cmp     r15, rdi
0x18001491f  ja      short loc_180014953
0x180014921  lea     r14, [rsi+8]
0x180014925  mov     rdx, rdi
0x180014928  sub     rdx, rbx; DestinationSize
0x18001492b  mov     r8, r14; Source
0x18001492e  mov     r9d, 2; SourceSize
0x180014934  mov     rcx, rbx; Destination
0x180014937  call    cs:__imp_memcpy_s
0x18001493d  mov     rbx, r15
0x180014940  jmp     short loc_180014946
0x180014942  lea     r14, [rsi+8]
0x180014946  movzx   r9d, word ptr [r14]; SourceSize
0x18001494a  lea     rax, [r9+rbx]
0x18001494e  cmp     rax, rdi
0x180014951  jbe     short loc_180014957
0x180014953  xor     al, al
0x180014955  jmp     short loc_180014977
0x180014957  mov     r8, [rsi+18h]; Source
0x18001495b  sub     rdi, rbx
0x18001495e  mov     rdx, rdi; DestinationSize
0x180014961  mov     rcx, rbx; Destination
0x180014964  call    cs:__imp_memcpy_s
0x18001496a  movzx   ecx, word ptr [r14]
0x18001496e  mov     al, 1
0x180014970  add     rcx, rbx
0x180014973  mov     [r12], rcx
0x180014977  add     rsp, 28h
0x18001497b  pop     r15
0x18001497d  pop     r14
0x18001497f  pop     r12
0x180014981  pop     rdi
0x180014982  pop     rsi
0x180014983  pop     rbx
0x180014984  retn
```
