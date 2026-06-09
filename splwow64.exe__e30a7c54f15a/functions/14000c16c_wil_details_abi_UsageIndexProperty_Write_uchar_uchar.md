# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000c16c`
- end: `0x14000c254`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ac84`

## callees

- `0x1400027fe`
- `0x140006388`
- `0x14000c16c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c1cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000c1cf`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x14000c16c  push    rbx
0x14000c16e  push    rbp
0x14000c16f  push    rsi
0x14000c170  push    rdi
0x14000c171  push    r14
0x14000c173  push    r15
0x14000c175  sub     rsp, 28h
0x14000c179  mov     al, [rcx+2]
0x14000c17c  xor     ebp, ebp
0x14000c17e  mov     r9, [rdx]
0x14000c181  mov     rdi, r8
0x14000c184  mov     r15, rdx
0x14000c187  mov     rsi, rcx
0x14000c18a  cmp     al, 1
0x14000c18c  jnz     short loc_14000C1AA
0x14000c18e  lea     rbx, [r9+2]
0x14000c192  cmp     rbx, r8
0x14000c195  ja      loc_14000C225
0x14000c19b  test    r9, r9
0x14000c19e  jz      short loc_14000C1CF
0x14000c1a0  movzx   eax, word ptr [rcx+4]
0x14000c1a4  mov     [r9], ax
0x14000c1a8  jmp     short loc_14000C1E5
0x14000c1aa  cmp     al, 2
0x14000c1ac  jnz     short loc_14000C1E2
0x14000c1ae  lea     rbx, [r9+4]
0x14000c1b2  cmp     rbx, rdi
0x14000c1b5  ja      short loc_14000C225
0x14000c1b7  test    r9, r9
0x14000c1ba  jz      short loc_14000C1CF
0x14000c1bc  lea     rax, [rcx+4]
0x14000c1c0  test    rax, rax
0x14000c1c3  jz      short loc_14000C1CC
0x14000c1c5  mov     eax, [rax]
0x14000c1c7  mov     [r9], eax
0x14000c1ca  jmp     short loc_14000C1E5
0x14000c1cc  mov     [r9], eax
0x14000c1cf  call    cs:__imp__o__errno
0x14000c1d5  mov     dword ptr [rax], 16h
0x14000c1db  call    _invalid_parameter_noinfo
0x14000c1e0  jmp     short loc_14000C1E5
0x14000c1e2  mov     rbx, r9
0x14000c1e5  cmp     [rsi], bp
0x14000c1e8  jnz     short loc_14000C213
0x14000c1ea  lea     r14, [rbx+2]
0x14000c1ee  cmp     r14, rdi
0x14000c1f1  ja      short loc_14000C225
0x14000c1f3  lea     rbp, [rsi+8]
0x14000c1f7  mov     rdx, rdi
0x14000c1fa  sub     rdx, rbx; DestinationSize
0x14000c1fd  mov     r8, rbp; Source
0x14000c200  mov     r9d, 2; SourceSize
0x14000c206  mov     rcx, rbx; Destination
0x14000c209  call    memcpy_s
0x14000c20e  mov     rbx, r14
0x14000c211  jmp     short loc_14000C217
0x14000c213  lea     rbp, [rsi+8]
0x14000c217  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000c21c  lea     rax, [r9+rbx]
0x14000c220  cmp     rax, rdi
0x14000c223  jbe     short loc_14000C229
0x14000c225  xor     al, al
0x14000c227  jmp     short loc_14000C247
0x14000c229  mov     r8, [rsi+18h]; Source
0x14000c22d  sub     rdi, rbx
0x14000c230  mov     rdx, rdi; DestinationSize
0x14000c233  mov     rcx, rbx; Destination
0x14000c236  call    memcpy_s
0x14000c23b  movzx   ecx, word ptr [rbp+0]
0x14000c23f  mov     al, 1
0x14000c241  add     rcx, rbx
0x14000c244  mov     [r15], rcx
0x14000c247  add     rsp, 28h
0x14000c24b  pop     r15
0x14000c24d  pop     r14
0x14000c24f  pop     rdi
0x14000c250  pop     rsi
0x14000c251  pop     rbp
0x14000c252  pop     rbx
0x14000c253  retn
```
