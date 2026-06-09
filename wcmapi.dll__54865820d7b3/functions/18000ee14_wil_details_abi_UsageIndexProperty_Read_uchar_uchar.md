# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000ee14`
- end: `0x18000ef17`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `259`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cf28`
- `0x18000dccc`
- `0x18000e170`
- `0x18000f4e8`
- `0x180010110`

## callees

- `0x180008a90`
- `0x18000aaf4`
- `0x18000ee14`

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
  unsigned __int16 v11; // [rsp+20h] [rbp-38h] BYREF

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
0x18000ee14  mov     r11, rsp
0x18000ee17  mov     [r11+18h], rbx
0x18000ee1b  mov     [r11+20h], rbp
0x18000ee1f  push    rsi
0x18000ee20  push    rdi
0x18000ee21  push    r12
0x18000ee23  push    r14
0x18000ee25  push    r15
0x18000ee27  sub     rsp, 30h
0x18000ee2b  mov     rax, cs:__security_cookie
0x18000ee32  xor     rax, rsp
0x18000ee35  mov     [rsp+58h+var_30], rax
0x18000ee3a  xor     r15d, r15d
0x18000ee3d  mov     rsi, r8
0x18000ee40  cmp     byte ptr [rcx+2], 1
0x18000ee44  mov     r12, rdx
0x18000ee47  mov     r8, [rdx]; Source
0x18000ee4a  mov     rdi, rcx
0x18000ee4d  jnz     short loc_18000EE81
0x18000ee4f  lea     rbx, [r8+2]
0x18000ee53  cmp     rbx, rsi
0x18000ee56  ja      loc_18000EEE4
0x18000ee5c  lea     ebp, [r15+2]
0x18000ee60  mov     [rcx+10h], r8
0x18000ee64  mov     r9d, ebp; SourceSize
0x18000ee67  mov     [r11-38h], r15w
0x18000ee6c  mov     edx, ebp; DestinationSize
0x18000ee6e  lea     rcx, [r11-38h]; Destination
0x18000ee72  call    memcpy_s
0x18000ee77  movzx   eax, [rsp+58h+var_38]
0x18000ee7c  mov     [rdi+4], eax
0x18000ee7f  jmp     short loc_18000EEAB
0x18000ee81  mov     ebp, 2
0x18000ee86  mov     rbx, r8
0x18000ee89  cmp     [rcx+2], bpl
0x18000ee8d  jnz     short loc_18000EEAB
0x18000ee8f  lea     rbx, [r8+4]
0x18000ee93  cmp     rbx, rsi
0x18000ee96  ja      short loc_18000EEE4
0x18000ee98  lea     edx, [rbp+2]; DestinationSize
0x18000ee9b  mov     [rcx+10h], r8
0x18000ee9f  mov     r9d, edx; SourceSize
0x18000eea2  add     rcx, 4; Destination
0x18000eea6  call    memcpy_s
0x18000eeab  movzx   eax, word ptr [rdi]
0x18000eeae  lea     r14, [rdi+8]
0x18000eeb2  mov     [r14], ax
0x18000eeb6  test    ax, ax
0x18000eeb9  jnz     short loc_18000EED8
0x18000eebb  lea     r15, [rbx+2]
0x18000eebf  cmp     r15, rsi
0x18000eec2  ja      short loc_18000EEE4
0x18000eec4  mov     r9, rbp; SourceSize
0x18000eec7  mov     r8, rbx; Source
0x18000eeca  mov     rdx, rbp; DestinationSize
0x18000eecd  mov     rcx, r14; Destination
0x18000eed0  call    memcpy_s
0x18000eed5  mov     rbx, r15
0x18000eed8  movzx   ecx, word ptr [r14]
0x18000eedc  add     rcx, rbx
0x18000eedf  cmp     rcx, rsi
0x18000eee2  jbe     short loc_18000EEE8
0x18000eee4  xor     al, al
0x18000eee6  jmp     short loc_18000EEF2
0x18000eee8  mov     [rdi+18h], rbx
0x18000eeec  mov     al, 1
0x18000eeee  mov     [r12], rcx
0x18000eef2  mov     rcx, [rsp+58h+var_30]
0x18000eef7  xor     rcx, rsp; StackCookie
0x18000eefa  call    __security_check_cookie
0x18000eeff  mov     rbx, [rsp+58h+arg_10]
0x18000ef04  mov     rbp, [rsp+58h+arg_18]
0x18000ef09  add     rsp, 30h
0x18000ef0d  pop     r15
0x18000ef0f  pop     r14
0x18000ef11  pop     r12
0x18000ef13  pop     rdi
0x18000ef14  pop     rsi
0x18000ef15  retn
```
