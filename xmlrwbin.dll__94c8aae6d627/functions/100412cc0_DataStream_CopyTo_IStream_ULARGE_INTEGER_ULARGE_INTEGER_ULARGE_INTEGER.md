# DataStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x100412cc0`
- end: `0x100412da7`
- name: `?CopyTo@DataStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `231`
- prototype: `__int64 __usercall@<rax>(DataStream *__hidden this@<rcx>, struct IStream *@<rdx>, union _ULARGE_INTEGER@<r8>, union _ULARGE_INTEGER *@<r9>, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100412cc0`
- `0x100412db0`
- `0x100416590`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall DataStream::CopyTo(
        DataStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  DWORD LowPart; // ebx
  unsigned int v9; // edi
  _DWORD v11[9]; // [rsp+3Ch] [rbp-DCh] BYREF
  _BYTE v12[112]; // [rsp+60h] [rbp-B8h] BYREF

  LowPart = a3.LowPart;
  a4->QuadPart = 0;
  a5->QuadPart = 0;
  if ( a3.QuadPart > *((unsigned int *)this + 6) )
    LowPart = *((_DWORD *)this + 6);
  while ( LowPart )
  {
    v9 = LowPart;
    if ( LowPart > 0x64 )
      v9 = 100;
    v11[3] = v9;
    DataStream::InternalRead(this, v12, v9);
    a4->LowPart += v9;
    if ( ((unsigned int (__fastcall *)(struct IStream *, _BYTE *, _QWORD, _DWORD *))a2->lpVtbl->Write)(a2, v12, v9, v11)
      || v11[0] != v9 )
    {
      return 2147500037LL;
    }
    a5->LowPart += v9;
    LowPart -= v9;
  }
  return 0;
}

```

## disassembly

```asm
0x100412cc0  push    rbx
0x100412cc2  push    rsi
0x100412cc3  push    rdi
0x100412cc4  push    r12
0x100412cc6  push    r13
0x100412cc8  push    r14
0x100412cca  push    r15
0x100412ccc  sub     rsp, 0E0h
0x100412cd3  mov     rax, cs:__security_cookie
0x100412cda  xor     rax, rsp
0x100412cdd  mov     [rsp+118h+var_48], rax
0x100412ce5  mov     r12, r9
0x100412ce8  mov     rbx, r8
0x100412ceb  mov     r13, rdx
0x100412cee  mov     r14, rcx
0x100412cf1  mov     rax, r8
0x100412cf4  shr     rax, 20h
0x100412cf8  mov     rsi, [rsp+118h+arg_20]
0x100412d00  xor     r15d, r15d
0x100412d03  mov     [r9], r15
0x100412d06  mov     [rsi], r15
0x100412d09  test    eax, eax
0x100412d0b  jnz     short loc_100412D12
0x100412d0d  cmp     ebx, [rcx+18h]
0x100412d10  jbe     short loc_100412D15
0x100412d12  mov     ebx, [rcx+18h]
0x100412d15  mov     [rsp+118h+var_E4], ebx
0x100412d19  mov     eax, 64h ; 'd'
0x100412d1e  test    ebx, ebx
0x100412d20  jz      short loc_100412D7A
0x100412d22  mov     edi, ebx
0x100412d24  cmp     ebx, eax
0x100412d26  cmova   edi, eax
0x100412d29  mov     [rsp+118h+var_D0], edi
0x100412d2d  mov     r8d, edi; unsigned int
0x100412d30  lea     rdx, [rsp+118h+var_B8]; void *
0x100412d35  mov     rcx, r14; this
0x100412d38  call    ?InternalRead@DataStream@@AEAAXPEAXK@Z; DataStream::InternalRead(void *,ulong)
0x100412d3d  add     [r12], edi
0x100412d41  mov     rax, [r13+0]
0x100412d45  lea     r9, [rsp+118h+var_DC]
0x100412d4a  mov     r8d, edi
0x100412d4d  lea     rdx, [rsp+118h+var_B8]
0x100412d52  mov     rcx, r13
0x100412d55  mov     rax, [rax+20h]
0x100412d59  call    cs:__guard_dispatch_icall_fptr
0x100412d5f  test    eax, eax
0x100412d61  jnz     short loc_100412D73
0x100412d63  cmp     [rsp+118h+var_DC], edi
0x100412d67  jnz     short loc_100412D73
0x100412d69  add     [rsi], edi
0x100412d6b  sub     ebx, edi
0x100412d6d  mov     [rsp+118h+var_E4], ebx
0x100412d71  jmp     short loc_100412D19
0x100412d73  mov     eax, 80004005h
0x100412d78  jmp     short loc_100412D84
0x100412d7a  jmp     short loc_100412D81
0x100412d7c  mov     r15d, [rsp+118h+var_E8]
0x100412d81  mov     eax, r15d
0x100412d84  mov     rcx, [rsp+118h+var_48]
0x100412d8c  xor     rcx, rsp; StackCookie
0x100412d8f  call    __security_check_cookie
0x100412d94  add     rsp, 0E0h
0x100412d9b  pop     r15
0x100412d9d  pop     r14
0x100412d9f  pop     r13
0x100412da1  pop     r12
0x100412da3  pop     rdi
0x100412da4  pop     rsi
0x100412da5  pop     rbx
0x100412da6  retn
0x100424f20  push    rbp
0x100424f22  sub     rsp, 30h
0x100424f26  mov     rbp, rdx
0x100424f29  mov     [rbp+58h], rcx
0x100424f2d  mov     [rbp+50h], rcx
0x100424f31  mov     rax, [rbp+50h]
0x100424f35  mov     rcx, [rax]
0x100424f38  mov     [rbp+40h], rcx
0x100424f3c  mov     rax, [rbp+40h]
0x100424f40  mov     eax, [rax]
0x100424f42  cmp     eax, 0C0000005h
0x100424f47  jz      short loc_100424F79
0x100424f49  add     eax, 1FFFFFFFh
0x100424f4e  cmp     eax, 1
0x100424f51  ja      short loc_100424F69
0x100424f53  mov     rax, [rbp+40h]
0x100424f57  cmp     dword ptr [rax+18h], 1
0x100424f5b  jnz     short loc_100424F69
0x100424f5d  mov     rax, [rbp+40h]
0x100424f61  mov     ecx, [rax+20h]
0x100424f64  mov     [rbp+30h], ecx
0x100424f67  jmp     short loc_100424F70
0x100424f69  mov     dword ptr [rbp+30h], 8000FFFFh
0x100424f70  mov     dword ptr [rbp+38h], 1
0x100424f77  jmp     short loc_100424F80
0x100424f79  mov     dword ptr [rbp+38h], 0
0x100424f80  mov     eax, [rbp+38h]
0x100424f83  add     rsp, 30h
0x100424f87  pop     rbp
0x100424f88  retn
```
