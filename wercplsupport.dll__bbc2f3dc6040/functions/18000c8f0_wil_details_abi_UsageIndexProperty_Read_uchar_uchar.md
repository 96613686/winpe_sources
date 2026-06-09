# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000c8f0`
- end: `0x18000c9d9`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ab20`
- `0x18000cf04`
- `0x18000d28c`

## callees

- `0x18000c8f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c93f`
- `msvcrt!memcpy_s` at `0x18000c974`
- `msvcrt!memcpy_s` at `0x18000c99f`
- `msvcrt!memcpy_s` at `0x18000c93f`
- `msvcrt!memcpy_s` at `0x18000c974`
- `msvcrt!memcpy_s` at `0x18000c99f`

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
0x18000c8f0  mov     rax, rsp
0x18000c8f3  mov     [rax+10h], rbx
0x18000c8f7  mov     [rax+18h], rbp
0x18000c8fb  push    rsi
0x18000c8fc  push    rdi
0x18000c8fd  push    r12
0x18000c8ff  push    r14
0x18000c901  push    r15
0x18000c903  sub     rsp, 20h
0x18000c907  xor     r15d, r15d
0x18000c90a  mov     rsi, r8
0x18000c90d  cmp     byte ptr [rcx+2], 1
0x18000c911  mov     r12, rdx
0x18000c914  mov     r8, [rdx]; Source
0x18000c917  mov     rdi, rcx
0x18000c91a  jnz     short loc_18000C94F
0x18000c91c  lea     rbx, [r8+2]
0x18000c920  cmp     rbx, rsi
0x18000c923  ja      loc_18000C9B4
0x18000c929  lea     ebp, [r15+2]
0x18000c92d  mov     [rcx+10h], r8
0x18000c931  mov     r9d, ebp; SourceSize
0x18000c934  mov     [rax+8], r15w
0x18000c939  mov     edx, ebp; DestinationSize
0x18000c93b  lea     rcx, [rax+8]; Destination
0x18000c93f  call    cs:__imp_memcpy_s
0x18000c945  movzx   eax, [rsp+48h+arg_0]
0x18000c94a  mov     [rdi+4], eax
0x18000c94d  jmp     short loc_18000C97A
0x18000c94f  mov     ebp, 2
0x18000c954  mov     rbx, r8
0x18000c957  cmp     [rcx+2], bpl
0x18000c95b  jnz     short loc_18000C97A
0x18000c95d  lea     rbx, [r8+4]
0x18000c961  cmp     rbx, rsi
0x18000c964  ja      short loc_18000C9B4
0x18000c966  lea     edx, [rbp+2]; DestinationSize
0x18000c969  mov     [rcx+10h], r8
0x18000c96d  mov     r9d, edx; SourceSize
0x18000c970  add     rcx, 4; Destination
0x18000c974  call    cs:__imp_memcpy_s
0x18000c97a  movzx   eax, word ptr [rdi]
0x18000c97d  lea     r14, [rdi+8]
0x18000c981  mov     [r14], ax
0x18000c985  test    ax, ax
0x18000c988  jnz     short loc_18000C9A8
0x18000c98a  lea     r15, [rbx+2]
0x18000c98e  cmp     r15, rsi
0x18000c991  ja      short loc_18000C9B4
0x18000c993  mov     r9, rbp; SourceSize
0x18000c996  mov     r8, rbx; Source
0x18000c999  mov     rdx, rbp; DestinationSize
0x18000c99c  mov     rcx, r14; Destination
0x18000c99f  call    cs:__imp_memcpy_s
0x18000c9a5  mov     rbx, r15
0x18000c9a8  movzx   ecx, word ptr [r14]
0x18000c9ac  add     rcx, rbx
0x18000c9af  cmp     rcx, rsi
0x18000c9b2  jbe     short loc_18000C9B8
0x18000c9b4  xor     al, al
0x18000c9b6  jmp     short loc_18000C9C2
0x18000c9b8  mov     [rdi+18h], rbx
0x18000c9bc  mov     al, 1
0x18000c9be  mov     [r12], rcx
0x18000c9c2  mov     rbx, [rsp+48h+arg_8]
0x18000c9c7  mov     rbp, [rsp+48h+arg_10]
0x18000c9cc  add     rsp, 20h
0x18000c9d0  pop     r15
0x18000c9d2  pop     r14
0x18000c9d4  pop     r12
0x18000c9d6  pop     rdi
0x18000c9d7  pop     rsi
0x18000c9d8  retn
```
