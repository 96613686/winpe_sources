# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000f188`
- end: `0x18000f26e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae64`
- `0x18000dcdc`
- `0x18000e888`
- `0x18000ed20`
- `0x18000fdc0`

## callees

- `0x18000f188`
- `0x180010e4c`

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
0x18000f188  mov     rax, rsp
0x18000f18b  mov     [rax+10h], rbx
0x18000f18f  mov     [rax+18h], rbp
0x18000f193  push    rsi
0x18000f194  push    rdi
0x18000f195  push    r12
0x18000f197  push    r14
0x18000f199  push    r15
0x18000f19b  sub     rsp, 20h
0x18000f19f  xor     r15d, r15d
0x18000f1a2  mov     rsi, r8
0x18000f1a5  cmp     byte ptr [rcx+2], 1
0x18000f1a9  mov     r12, rdx
0x18000f1ac  mov     r8, [rdx]; Source
0x18000f1af  mov     rdi, rcx
0x18000f1b2  jnz     short loc_18000F1E6
0x18000f1b4  lea     rbx, [r8+2]
0x18000f1b8  cmp     rbx, rsi
0x18000f1bb  ja      loc_18000F249
0x18000f1c1  lea     ebp, [r15+2]
0x18000f1c5  mov     [rcx+10h], r8
0x18000f1c9  mov     r9d, ebp; SourceSize
0x18000f1cc  mov     [rax+8], r15w
0x18000f1d1  mov     edx, ebp; DestinationSize
0x18000f1d3  lea     rcx, [rax+8]; Destination
0x18000f1d7  call    memcpy_s
0x18000f1dc  movzx   eax, [rsp+48h+arg_0]
0x18000f1e1  mov     [rdi+4], eax
0x18000f1e4  jmp     short loc_18000F210
0x18000f1e6  mov     ebp, 2
0x18000f1eb  mov     rbx, r8
0x18000f1ee  cmp     [rcx+2], bpl
0x18000f1f2  jnz     short loc_18000F210
0x18000f1f4  lea     rbx, [r8+4]
0x18000f1f8  cmp     rbx, rsi
0x18000f1fb  ja      short loc_18000F249
0x18000f1fd  lea     edx, [rbp+2]; DestinationSize
0x18000f200  mov     [rcx+10h], r8
0x18000f204  mov     r9d, edx; SourceSize
0x18000f207  add     rcx, 4; Destination
0x18000f20b  call    memcpy_s
0x18000f210  movzx   eax, word ptr [rdi]
0x18000f213  lea     r14, [rdi+8]
0x18000f217  mov     [r14], ax
0x18000f21b  test    ax, ax
0x18000f21e  jnz     short loc_18000F23D
0x18000f220  lea     r15, [rbx+2]
0x18000f224  cmp     r15, rsi
0x18000f227  ja      short loc_18000F249
0x18000f229  mov     r9, rbp; SourceSize
0x18000f22c  mov     r8, rbx; Source
0x18000f22f  mov     rdx, rbp; DestinationSize
0x18000f232  mov     rcx, r14; Destination
0x18000f235  call    memcpy_s
0x18000f23a  mov     rbx, r15
0x18000f23d  movzx   ecx, word ptr [r14]
0x18000f241  add     rcx, rbx
0x18000f244  cmp     rcx, rsi
0x18000f247  jbe     short loc_18000F24D
0x18000f249  xor     al, al
0x18000f24b  jmp     short loc_18000F257
0x18000f24d  mov     [rdi+18h], rbx
0x18000f251  mov     al, 1
0x18000f253  mov     [r12], rcx
0x18000f257  mov     rbx, [rsp+48h+arg_8]
0x18000f25c  mov     rbp, [rsp+48h+arg_10]
0x18000f261  add     rsp, 20h
0x18000f265  pop     r15
0x18000f267  pop     r14
0x18000f269  pop     r12
0x18000f26b  pop     rdi
0x18000f26c  pop     rsi
0x18000f26d  retn
```
