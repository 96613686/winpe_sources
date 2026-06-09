# DuiStringFindAndReplace(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ushort *,uint)

- ea: `0x18001a8c0`
- end: `0x18001ab3b`
- name: `?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAGI@Z`
- size: `635`
- prototype: `__int64 __fastcall(unsigned __int64 *Src, __int64, int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180019da0`
- `0x18001ab44`

## callees

- `0x180001e26`
- `0x180001e32`
- `0x18001661c`
- `0x180016634`
- `0x18001a8c0`
- `0x18001af34`
- `0x18001b324`
- `0x18001b4b8`
- `0x18001bf40`

## import_xrefs

- `msvcrt!_itow` at `0x18001a924`
- `msvcrt!_itow` at `0x18001a924`

## pseudocode

```c
__int64 __fastcall DuiStringFindAndReplace(unsigned __int64 *Src, __int64 a2, int a3)
{
  unsigned __int64 *v4; // rbx
  __int64 result; // rax
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 *v18; // r12
  unsigned __int64 v19; // rbp
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  wchar_t Buffer[8]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v23; // [rsp+40h] [rbp-58h]
  __int64 v24; // [rsp+50h] [rbp-48h]

  *(_OWORD *)Buffer = 0;
  v24 = 0;
  v4 = Src;
  v23 = 0;
  result = std::wstring::find(Src, L"%1");
  v6 = -1;
  v7 = result;
  if ( result == -1 )
    return result;
  _itow(a3, Buffer, 10);
  if ( Buffer[0] )
  {
    do
      ++v6;
    while ( Buffer[v6] );
  }
  else
  {
    v6 = 0;
  }
  v8 = v4[3];
  if ( v8 < 8 )
    v9 = (unsigned __int64)v4;
  else
    v9 = *v4;
  if ( (unsigned __int64)Buffer < v9 )
  {
    v11 = v4[2];
  }
  else
  {
    if ( v8 < 8 )
      v10 = (unsigned __int64)v4;
    else
      v10 = *v4;
    v11 = v4[2];
    if ( v10 + 2 * v11 > (unsigned __int64)Buffer )
    {
      if ( v8 < 8 )
        v12 = (unsigned __int64)v4;
      else
        v12 = *v4;
      return std::wstring::replace(v4, (__int64)((__int64)Buffer - v12) >> 1, v6);
    }
  }
  if ( v11 < v7 )
    std::wstring::_Xran();
  v13 = 2;
  if ( v11 - v7 < 2 )
    v13 = v11 - v7;
  result = ~v6;
  v14 = v11 - v13;
  if ( ~v6 <= v14 )
    std::wstring::_Xlen();
  v15 = v14 - v7;
  if ( v6 < v13 )
  {
    if ( v8 < 8 )
    {
      v16 = (unsigned __int64)v4;
      v17 = (unsigned __int64)v4;
    }
    else
    {
      v16 = *v4;
      v17 = *v4;
    }
    if ( v15 )
      result = (__int64)memmove_0((void *)(v16 + 2 * (v6 + v7)), (const void *)(v17 + 2 * (v13 + v7)), 2 * v15);
  }
  if ( v6 || v13 )
  {
    v18 = v4 + 2;
    result = 0x7FFFFFFFFFFFFFFELL;
    v19 = v6 + v4[2] - v13;
    if ( v19 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( v4[3] < v19 )
    {
      result = std::wstring::_Copy(v4);
      if ( !v19 )
        return result;
      goto LABEL_33;
    }
    if ( v19 )
    {
LABEL_33:
      if ( v13 < v6 )
      {
        if ( v4[3] < 8 )
        {
          v20 = (unsigned __int64)v4;
          v21 = (unsigned __int64)v4;
        }
        else
        {
          v20 = *v4;
          v21 = *v4;
        }
        if ( v15 )
          memmove_0((void *)(v20 + 2 * (v6 + v7)), (const void *)(v21 + 2 * (v13 + v7)), 2 * v15);
      }
      if ( v4[3] < 8 )
        result = (__int64)v4;
      else
        result = *v4;
      if ( v6 )
        result = (__int64)memcpy_0((void *)(result + 2 * v7), Buffer, 2 * v6);
      if ( v4[3] >= 8 )
        v4 = (unsigned __int64 *)*v4;
      *v18 = v19;
      *((_WORD *)v4 + v19) = 0;
      return result;
    }
    if ( v4[3] >= 8 )
      v4 = (unsigned __int64 *)*v4;
    *v18 = 0;
    *(_WORD *)v4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a8c0  mov     [rsp+arg_8], rbx
0x18001a8c5  push    rbp
0x18001a8c6  push    rsi
0x18001a8c7  push    rdi
0x18001a8c8  push    r12
0x18001a8ca  push    r13
0x18001a8cc  push    r14
0x18001a8ce  push    r15
0x18001a8d0  sub     rsp, 60h
0x18001a8d4  mov     rax, cs:__security_cookie
0x18001a8db  xor     rax, rsp
0x18001a8de  mov     [rsp+98h+var_40], rax
0x18001a8e3  xorps   xmm0, xmm0
0x18001a8e6  lea     rdx, a1; "%1"
0x18001a8ed  xor     eax, eax
0x18001a8ef  mov     esi, r8d
0x18001a8f2  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x18001a8f7  mov     [rsp+98h+var_48], rax
0x18001a8fc  mov     rbx, rcx
0x18001a8ff  movups  [rsp+98h+var_58], xmm0
0x18001a904  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find(ushort const *,unsigned __int64)
0x18001a909  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001a90d  mov     r15, rax
0x18001a910  cmp     rax, rdi
0x18001a913  jz      loc_18001AB04
0x18001a919  lea     r8d, [rdi+0Bh]; Radix
0x18001a91d  mov     ecx, esi; Value
0x18001a91f  lea     rdx, [rsp+98h+Buffer]; Buffer
0x18001a924  call    cs:__imp__itow
0x18001a92a  xor     r13d, r13d
0x18001a92d  cmp     [rsp+98h+Buffer], r13w
0x18001a933  jnz     short loc_18001A93A
0x18001a935  mov     edi, r13d
0x18001a938  jmp     short loc_18001A949
0x18001a93a  lea     rax, [rsp+98h+Buffer]
0x18001a93f  inc     rdi
0x18001a942  cmp     [rax+rdi*2], r13w
0x18001a947  jnz     short loc_18001A93F
0x18001a949  mov     rcx, [rbx+18h]
0x18001a94d  cmp     rcx, 8
0x18001a951  jb      short loc_18001A958
0x18001a953  mov     rax, [rbx]
0x18001a956  jmp     short loc_18001A95B
0x18001a958  mov     rax, rbx
0x18001a95b  lea     rdx, [rsp+98h+Buffer]
0x18001a960  cmp     rdx, rax
0x18001a963  jb      short loc_18001A9C1
0x18001a965  cmp     rcx, 8
0x18001a969  jb      short loc_18001A970
0x18001a96b  mov     rax, [rbx]
0x18001a96e  jmp     short loc_18001A973
0x18001a970  mov     rax, rbx
0x18001a973  mov     rsi, [rbx+10h]
0x18001a977  lea     rdx, [rsp+98h+Buffer]
0x18001a97c  lea     rax, [rax+rsi*2]
0x18001a980  cmp     rax, rdx
0x18001a983  jbe     short loc_18001A9C5
0x18001a985  cmp     rcx, 8
0x18001a989  jb      short loc_18001A990
0x18001a98b  mov     rcx, [rbx]
0x18001a98e  jmp     short loc_18001A993
0x18001a990  mov     rcx, rbx
0x18001a993  lea     rax, [rsp+98h+Buffer]
0x18001a998  mov     [rsp+98h+var_70], rdi; __int64
0x18001a99d  sub     rax, rcx
0x18001a9a0  mov     r9, rbx
0x18001a9a3  sar     rax, 1
0x18001a9a6  mov     r8d, 2
0x18001a9ac  mov     rdx, r15
0x18001a9af  mov     [rsp+98h+var_78], rax; __int64
0x18001a9b4  mov     rcx, rbx; Src
0x18001a9b7  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18001a9bc  jmp     loc_18001AB04
0x18001a9c1  mov     rsi, [rbx+10h]
0x18001a9c5  cmp     rsi, r15
0x18001a9c8  jb      loc_18001AB29
0x18001a9ce  mov     rax, rsi
0x18001a9d1  mov     r14d, 2
0x18001a9d7  sub     rax, r15
0x18001a9da  cmp     rax, r14
0x18001a9dd  cmovb   r14, rax
0x18001a9e1  mov     rax, rdi
0x18001a9e4  not     rax
0x18001a9e7  sub     rsi, r14
0x18001a9ea  cmp     rax, rsi
0x18001a9ed  jbe     loc_18001AB2F
0x18001a9f3  sub     rsi, r15
0x18001a9f6  cmp     rdi, r14
0x18001a9f9  jnb     short loc_18001AA2D
0x18001a9fb  cmp     rcx, 8
0x18001a9ff  jb      short loc_18001AA09
0x18001aa01  mov     rcx, [rbx]
0x18001aa04  mov     rdx, rcx
0x18001aa07  jmp     short loc_18001AA0F
0x18001aa09  mov     rcx, rbx
0x18001aa0c  mov     rdx, rbx
0x18001aa0f  test    rsi, rsi
0x18001aa12  jz      short loc_18001AA2D
0x18001aa14  lea     rax, [r14+r15]
0x18001aa18  lea     rdx, [rdx+rax*2]; Src
0x18001aa1c  lea     rax, [rdi+r15]
0x18001aa20  lea     rcx, [rcx+rax*2]; void *
0x18001aa24  lea     r8, [rsi+rsi]; Size
0x18001aa28  call    memmove_0
0x18001aa2d  test    rdi, rdi
0x18001aa30  jnz     short loc_18001AA3B
0x18001aa32  test    r14, r14
0x18001aa35  jz      loc_18001AB04
0x18001aa3b  lea     r12, [rbx+10h]
0x18001aa3f  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001aa49  mov     rbp, [r12]
0x18001aa4d  sub     rbp, r14
0x18001aa50  add     rbp, rdi
0x18001aa53  cmp     rbp, rax
0x18001aa56  ja      loc_18001AB35
0x18001aa5c  cmp     [rbx+18h], rbp
0x18001aa60  jnb     short loc_18001AA8E
0x18001aa62  mov     r8, [r12]
0x18001aa66  mov     rdx, rbp
0x18001aa69  mov     rcx, rbx; Src
0x18001aa6c  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001aa71  test    rbp, rbp
0x18001aa74  jz      loc_18001AB04
0x18001aa7a  cmp     r14, rdi
0x18001aa7d  jnb     short loc_18001AACB
0x18001aa7f  cmp     qword ptr [rbx+18h], 8
0x18001aa84  jb      short loc_18001AAA7
0x18001aa86  mov     rcx, [rbx]
0x18001aa89  mov     rdx, rcx
0x18001aa8c  jmp     short loc_18001AAAD
0x18001aa8e  test    rbp, rbp
0x18001aa91  jnz     short loc_18001AA7A
0x18001aa93  cmp     qword ptr [rbx+18h], 8
0x18001aa98  jb      short loc_18001AA9D
0x18001aa9a  mov     rbx, [rbx]
0x18001aa9d  mov     [r12], r13
0x18001aaa1  mov     [rbx], r13w
0x18001aaa5  jmp     short loc_18001AB04
0x18001aaa7  mov     rcx, rbx
0x18001aaaa  mov     rdx, rbx
0x18001aaad  test    rsi, rsi
0x18001aab0  jz      short loc_18001AACB
0x18001aab2  lea     rax, [r14+r15]
0x18001aab6  lea     rdx, [rdx+rax*2]; Src
0x18001aaba  lea     rax, [rdi+r15]
0x18001aabe  lea     rcx, [rcx+rax*2]; void *
0x18001aac2  lea     r8, [rsi+rsi]; Size
0x18001aac6  call    memmove_0
0x18001aacb  cmp     qword ptr [rbx+18h], 8
0x18001aad0  jb      short loc_18001AAD7
0x18001aad2  mov     rax, [rbx]
0x18001aad5  jmp     short loc_18001AADA
0x18001aad7  mov     rax, rbx
0x18001aada  test    rdi, rdi
0x18001aadd  jz      short loc_18001AAF1
0x18001aadf  lea     r8, [rdi+rdi]; Size
0x18001aae3  lea     rcx, [rax+r15*2]; void *
0x18001aae7  lea     rdx, [rsp+98h+Buffer]; Src
0x18001aaec  call    memcpy_0
0x18001aaf1  cmp     qword ptr [rbx+18h], 8
0x18001aaf6  jb      short loc_18001AAFB
0x18001aaf8  mov     rbx, [rbx]
0x18001aafb  mov     [r12], rbp
0x18001aaff  mov     [rbx+rbp*2], r13w
0x18001ab04  mov     rcx, [rsp+98h+var_40]
0x18001ab09  xor     rcx, rsp; StackCookie
0x18001ab0c  call    __security_check_cookie
0x18001ab11  mov     rbx, [rsp+98h+arg_8]
0x18001ab19  add     rsp, 60h
0x18001ab1d  pop     r15
0x18001ab1f  pop     r14
0x18001ab21  pop     r13
0x18001ab23  pop     r12
0x18001ab25  pop     rdi
0x18001ab26  pop     rsi
0x18001ab27  pop     rbp
0x18001ab28  retn
0x18001ab29  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18001ab2f  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18001ab35  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
