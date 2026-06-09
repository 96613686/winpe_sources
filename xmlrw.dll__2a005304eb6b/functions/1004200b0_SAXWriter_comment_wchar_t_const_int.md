# SAXWriter::comment(wchar_t const *,int)

- ea: `0x1004200b0`
- end: `0x10042016e`
- name: `?comment@SAXWriter@@UEAAJPEB_WH@Z`
- size: `190`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1004200b0`
- `0x1004245e0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::comment(SAXWriter *this, const wchar_t *a2, unsigned int a3)
{
  unsigned int v6; // ebx

  v6 = 0;
  if ( a2 )
  {
    if ( *((_DWORD *)this + 11) == 1 )
    {
      *((_DWORD *)this + 11) = 5;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 3) + 40LL))((char *)this - 24, 5);
      if ( v6 )
        return v6;
    }
    (*(void (__fastcall **)(char *, const wchar_t *, _QWORD))(*((_QWORD *)this - 3) + 176LL))((char *)this - 24, a2, a3);
    if ( *((_BYTE *)this + 193) && *((_BYTE *)this + 48) )
      *((_DWORD *)this + 11) = 8;
    else
      *((_DWORD *)this + 11) = 1;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x1004200b0  mov     [rsp+arg_0], rbx
0x1004200b5  mov     [rsp+arg_8], rsi
0x1004200ba  mov     [rsp+arg_10], rdi
0x1004200bf  push    r14
0x1004200c1  sub     rsp, 50h
0x1004200c5  mov     r14d, r8d
0x1004200c8  mov     rsi, rdx
0x1004200cb  mov     rdi, rcx
0x1004200ce  xor     ebx, ebx
0x1004200d0  mov     [rsp+58h+var_34], ebx
0x1004200d4  test    rdx, rdx
0x1004200d7  jnz     short loc_1004200E4
0x1004200d9  mov     ebx, 80070057h
0x1004200de  mov     [rsp+58h+var_34], ebx
0x1004200e2  jmp     short loc_100420156
0x1004200e4  cmp     dword ptr [rcx+2Ch], 1
0x1004200e8  jnz     short loc_1004200F3
0x1004200ea  mov     dword ptr [rcx+2Ch], 5
0x1004200f1  jmp     short loc_100420113
0x1004200f3  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1004200f7  mov     rax, [rcx]
0x1004200fa  mov     edx, 5
0x1004200ff  mov     rax, [rax+28h]
0x100420103  call    cs:__guard_dispatch_icall_fptr
0x100420109  mov     ebx, eax
0x10042010b  mov     [rsp+58h+var_34], eax
0x10042010f  test    eax, eax
0x100420111  jnz     short loc_100420156
0x100420113  lea     rcx, [rdi-18h]
0x100420117  mov     rax, [rcx]
0x10042011a  mov     r8d, r14d
0x10042011d  mov     rdx, rsi
0x100420120  mov     rax, [rax+0B0h]
0x100420127  call    cs:__guard_dispatch_icall_fptr
0x10042012d  cmp     byte ptr [rdi+0C1h], 0
0x100420134  jz      short loc_100420145
0x100420136  cmp     byte ptr [rdi+30h], 0
0x10042013a  jz      short loc_100420145
0x10042013c  mov     dword ptr [rdi+2Ch], 8
0x100420143  jmp     short loc_10042014C
0x100420145  mov     dword ptr [rdi+2Ch], 1
0x10042014c  jmp     short loc_100420156
0x10042014e  mov     ebx, [rsp+58h+var_38]
0x100420152  mov     [rsp+58h+var_34], ebx
0x100420156  mov     eax, ebx
0x100420158  mov     rbx, [rsp+58h+arg_0]
0x10042015d  mov     rsi, [rsp+58h+arg_8]
0x100420162  mov     rdi, [rsp+58h+arg_10]
0x100420167  add     rsp, 50h
0x10042016b  pop     r14
0x10042016d  retn
0x10043a380  push    rbp
0x10043a382  sub     rsp, 20h
0x10043a386  mov     rbp, rdx
0x10043a389  mov     [rbp+40h], rcx
0x10043a38d  mov     [rbp+38h], rcx
0x10043a391  mov     rax, [rbp+38h]
0x10043a395  mov     rcx, [rax]
0x10043a398  mov     [rbp+30h], rcx
0x10043a39c  mov     rax, [rbp+30h]
0x10043a3a0  mov     eax, [rax]
0x10043a3a2  cmp     eax, 0C0000005h
0x10043a3a7  jz      short loc_10043A3D9
0x10043a3a9  add     eax, 1FFFFFFFh
0x10043a3ae  cmp     eax, 1
0x10043a3b1  ja      short loc_10043A3C9
0x10043a3b3  mov     rax, [rbp+30h]
0x10043a3b7  cmp     dword ptr [rax+18h], 1
0x10043a3bb  jnz     short loc_10043A3C9
0x10043a3bd  mov     rax, [rbp+30h]
0x10043a3c1  mov     ecx, [rax+20h]
0x10043a3c4  mov     [rbp+20h], ecx
0x10043a3c7  jmp     short loc_10043A3D0
0x10043a3c9  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a3d0  mov     dword ptr [rbp+28h], 1
0x10043a3d7  jmp     short loc_10043A3E0
0x10043a3d9  mov     dword ptr [rbp+28h], 0
0x10043a3e0  mov     eax, [rbp+28h]
0x10043a3e3  add     rsp, 20h
0x10043a3e7  pop     rbp
0x10043a3e8  retn
```
