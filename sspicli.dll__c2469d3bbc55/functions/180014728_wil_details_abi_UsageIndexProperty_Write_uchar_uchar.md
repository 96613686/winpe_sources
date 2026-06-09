# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180014728`
- end: `0x180014801`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012784`

## callees

- `0x180014728`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180014788`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800147b3`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800147e0`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180014788`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800147b3`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800147e0`

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
0x180014728  push    rbx
0x18001472a  push    rsi
0x18001472b  push    rdi
0x18001472c  push    r12
0x18001472e  push    r14
0x180014730  push    r15
0x180014732  sub     rsp, 28h
0x180014736  mov     rsi, rcx
0x180014739  mov     rdi, r8
0x18001473c  mov     rcx, [rdx]; Destination
0x18001473f  mov     r12, rdx
0x180014742  cmp     byte ptr [rsi+2], 1
0x180014746  jnz     short loc_18001476A
0x180014748  lea     rbx, [rcx+2]
0x18001474c  cmp     rbx, r8
0x18001474f  ja      short loc_1800147CF
0x180014751  movzx   eax, word ptr [rsi+4]
0x180014755  lea     r8, [rsp+58h+arg_0]
0x18001475a  mov     r9d, 2
0x180014760  mov     [rsp+58h+arg_0], ax
0x180014765  mov     edx, r9d
0x180014768  jmp     short loc_180014788
0x18001476a  cmp     byte ptr [rsi+2], 2
0x18001476e  mov     rbx, rcx
0x180014771  jnz     short loc_18001478E
0x180014773  lea     rbx, [rcx+4]
0x180014777  cmp     rbx, rdi
0x18001477a  ja      short loc_1800147CF
0x18001477c  mov     edx, 4; DestinationSize
0x180014781  lea     r8, [rsi+4]; Source
0x180014785  mov     r9d, edx; SourceSize
0x180014788  call    cs:__imp_memcpy_s
0x18001478e  cmp     word ptr [rsi], 0
0x180014792  jnz     short loc_1800147BE
0x180014794  lea     r15, [rbx+2]
0x180014798  cmp     r15, rdi
0x18001479b  ja      short loc_1800147CF
0x18001479d  lea     r14, [rsi+8]
0x1800147a1  mov     rdx, rdi
0x1800147a4  sub     rdx, rbx; DestinationSize
0x1800147a7  mov     r8, r14; Source
0x1800147aa  mov     r9d, 2; SourceSize
0x1800147b0  mov     rcx, rbx; Destination
0x1800147b3  call    cs:__imp_memcpy_s
0x1800147b9  mov     rbx, r15
0x1800147bc  jmp     short loc_1800147C2
0x1800147be  lea     r14, [rsi+8]
0x1800147c2  movzx   r9d, word ptr [r14]; SourceSize
0x1800147c6  lea     rax, [r9+rbx]
0x1800147ca  cmp     rax, rdi
0x1800147cd  jbe     short loc_1800147D3
0x1800147cf  xor     al, al
0x1800147d1  jmp     short loc_1800147F3
0x1800147d3  mov     r8, [rsi+18h]; Source
0x1800147d7  sub     rdi, rbx
0x1800147da  mov     rdx, rdi; DestinationSize
0x1800147dd  mov     rcx, rbx; Destination
0x1800147e0  call    cs:__imp_memcpy_s
0x1800147e6  movzx   ecx, word ptr [r14]
0x1800147ea  mov     al, 1
0x1800147ec  add     rcx, rbx
0x1800147ef  mov     [r12], rcx
0x1800147f3  add     rsp, 28h
0x1800147f7  pop     r15
0x1800147f9  pop     r14
0x1800147fb  pop     r12
0x1800147fd  pop     rdi
0x1800147fe  pop     rsi
0x1800147ff  pop     rbx
0x180014800  retn
```
