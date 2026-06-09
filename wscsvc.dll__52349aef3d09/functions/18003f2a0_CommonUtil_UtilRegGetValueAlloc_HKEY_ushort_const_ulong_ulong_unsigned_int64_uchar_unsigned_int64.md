# CommonUtil::UtilRegGetValueAlloc(HKEY__ *,ushort const *,ulong,ulong *,unsigned __int64 *,uchar * *,unsigned __int64)

- ea: `0x18003f2a0`
- end: `0x18003f469`
- name: `?UtilRegGetValueAlloc@CommonUtil@@YAJPEAUHKEY__@@PEBGKPEAKPEA_KPEAPEAE_K@Z`
- size: `457`
- prototype: `__int64 __usercall@<rax>(CommonUtil *__hidden this@<rcx>, HKEY@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int *, unsigned __int64 *, unsigned __int8 **, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003a040`

## callees

- `0x180029e74`
- `0x18002a762`
- `0x18003ee60`
- `0x18003ee98`
- `0x18003f254`
- `0x18003f2a0`
- `0x18003fc30`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValueAlloc(
        CommonUtil *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int64 *a6)
{
  unsigned int Value; // eax
  __int64 v9; // rcx
  int v10; // r8d
  size_t v11; // rbx
  size_t v12; // rdx
  __int64 result; // rax
  void *v14; // rbx
  HKEY v15; // rdx
  int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // edi
  void *v21; // [rsp+28h] [rbp-D8h]
  void *v22; // [rsp+28h] [rbp-D8h]
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 Src[34]; // [rsp+40h] [rbp-C0h] BYREF

  Size = 260;
  Value = CommonUtil::UtilRegGetValue(this, a2, a4, (unsigned int *)&Size, Src, v21);
  if ( (unsigned __int8)CommonUtil::IsTypeMismatch(v9, *(unsigned int *)a4, Value) )
    return 2147944029LL;
  if ( v10 < 0 )
  {
    result = 0;
    if ( v10 != -2147024662 )
      result = (unsigned int)v10;
    if ( (_DWORD)result == -2147024894 )
    {
      return 2147942402LL;
    }
    else if ( (int)result >= 0 )
    {
      v14 = 0;
      Block = 0;
      while ( 1 )
      {
        if ( v14 )
        {
          operator delete(v14);
          Block = 0;
        }
        v16 = CommonUtil::MpNewBuffer<unsigned char>(&Block, Size);
        if ( v16 < 0 )
          break;
        v14 = Block;
        v17 = CommonUtil::UtilRegGetValue(this, v15, a4, (unsigned int *)&Size, (unsigned __int64 *)Block, v22);
        if ( (unsigned __int8)CommonUtil::IsTypeMismatch(v18, *(unsigned int *)a4, v17) )
        {
          if ( v14 )
            operator delete(v14);
          return 2147944029LL;
        }
        if ( v19 >= 0 )
        {
          *(_QWORD *)a5 = Size;
          *a6 = (unsigned __int64)v14;
          return 0;
        }
        v20 = 0;
        if ( v19 != -2147024662 )
          v20 = v19;
        if ( v20 == -2147024894 )
        {
          if ( v14 )
            operator delete(v14);
          return 2147942402LL;
        }
        if ( v20 < 0 )
        {
          if ( v14 )
            operator delete(v14);
          return (unsigned int)v20;
        }
      }
      if ( Block )
        operator delete(Block);
      return (unsigned int)v16;
    }
  }
  else
  {
    v11 = Size;
    v12 = Size;
    *(_QWORD *)a5 = Size;
    result = CommonUtil::MpNewBuffer<unsigned char>(a6, v12);
    if ( (int)result >= 0 )
    {
      memmove_0((void *)*a6, Src, v11);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003f2a0  mov     [rsp-8+arg_8], rbx
0x18003f2a5  mov     [rsp-8+arg_10], rsi
0x18003f2aa  push    rbp
0x18003f2ab  push    rdi
0x18003f2ac  push    r12
0x18003f2ae  push    r14
0x18003f2b0  push    r15
0x18003f2b2  lea     rbp, [rsp-60h]
0x18003f2b7  sub     rsp, 160h
0x18003f2be  mov     rax, cs:__security_cookie
0x18003f2c5  xor     rax, rsp
0x18003f2c8  mov     [rbp+80h+var_30], rax
0x18003f2cc  mov     r14, [rbp+80h+arg_20]
0x18003f2d3  lea     rax, [rsp+180h+Src]
0x18003f2d8  mov     rsi, [rbp+80h+arg_28]
0x18003f2df  mov     r15, r9
0x18003f2e2  mov     r8, r15; unsigned __int16 *
0x18003f2e5  mov     [rsp+180h+Size], 104h
0x18003f2ee  lea     r9, [rsp+180h+Size]; unsigned int *
0x18003f2f3  mov     [rsp+180h+var_160], rax; unsigned __int64 *
0x18003f2f8  mov     r12, rcx
0x18003f2fb  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x18003f300  mov     edx, [r15]
0x18003f303  mov     r8d, eax
0x18003f306  call    CommonUtil__IsTypeMismatch
0x18003f30b  test    al, al
0x18003f30d  jnz     loc_18003F429
0x18003f313  test    r8d, r8d
0x18003f316  js      short loc_18003F34A
0x18003f318  mov     rbx, [rsp+180h+Size]
0x18003f31d  mov     rcx, rsi
0x18003f320  mov     rdx, rbx
0x18003f323  mov     [r14], rbx
0x18003f326  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x18003f32b  test    eax, eax
0x18003f32d  js      loc_18003F42E
0x18003f333  mov     rcx, [rsi]; void *
0x18003f336  lea     rdx, [rsp+180h+Src]; Src
0x18003f33b  mov     r8, rbx; Size
0x18003f33e  call    memmove_0
0x18003f343  xor     eax, eax
0x18003f345  jmp     loc_18003F42E
0x18003f34a  xor     eax, eax
0x18003f34c  cmp     r8d, 800700EAh
0x18003f353  cmovnz  eax, r8d
0x18003f357  cmp     eax, 80070002h
0x18003f35c  jz      loc_18003F405
0x18003f362  test    eax, eax
0x18003f364  js      loc_18003F42E
0x18003f36a  xor     ebx, ebx
0x18003f36c  mov     [rsp+180h+Block], rbx
0x18003f371  test    rbx, rbx
0x18003f374  jz      short loc_18003F387
0x18003f376  mov     rcx, rbx; Block
0x18003f379  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f37e  mov     [rsp+180h+Block], 0
0x18003f387  mov     rdx, [rsp+180h+Size]
0x18003f38c  lea     rcx, [rsp+180h+Block]
0x18003f391  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x18003f396  mov     ebx, eax
0x18003f398  test    eax, eax
0x18003f39a  js      loc_18003F456
0x18003f3a0  mov     rbx, [rsp+180h+Block]
0x18003f3a5  lea     r9, [rsp+180h+Size]; unsigned int *
0x18003f3aa  mov     r8, r15; unsigned __int16 *
0x18003f3ad  mov     [rsp+180h+var_160], rbx; unsigned __int64 *
0x18003f3b2  mov     rcx, r12; this
0x18003f3b5  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x18003f3ba  mov     edx, [r15]
0x18003f3bd  mov     r8d, eax
0x18003f3c0  call    CommonUtil__IsTypeMismatch
0x18003f3c5  test    al, al
0x18003f3c7  jnz     short loc_18003F41C
0x18003f3c9  test    r8d, r8d
0x18003f3cc  jns     short loc_18003F40C
0x18003f3ce  xor     edi, edi
0x18003f3d0  cmp     r8d, 800700EAh
0x18003f3d7  cmovnz  edi, r8d
0x18003f3db  cmp     edi, 80070002h
0x18003f3e1  jz      short loc_18003F3F8
0x18003f3e3  test    edi, edi
0x18003f3e5  jns     short loc_18003F371
0x18003f3e7  test    rbx, rbx
0x18003f3ea  jz      short loc_18003F3F4
0x18003f3ec  mov     rcx, rbx; Block
0x18003f3ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f3f4  mov     eax, edi
0x18003f3f6  jmp     short loc_18003F42E
0x18003f3f8  test    rbx, rbx
0x18003f3fb  jz      short loc_18003F405
0x18003f3fd  mov     rcx, rbx; Block
0x18003f400  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f405  mov     eax, 80070002h
0x18003f40a  jmp     short loc_18003F42E
0x18003f40c  mov     rax, [rsp+180h+Size]
0x18003f411  mov     [r14], rax
0x18003f414  mov     [rsi], rbx
0x18003f417  jmp     loc_18003F343
0x18003f41c  test    rbx, rbx
0x18003f41f  jz      short loc_18003F429
0x18003f421  mov     rcx, rbx; Block
0x18003f424  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f429  mov     eax, 8007065Dh
0x18003f42e  mov     rcx, [rbp+80h+var_30]
0x18003f432  xor     rcx, rsp; StackCookie
0x18003f435  call    __security_check_cookie
0x18003f43a  lea     r11, [rsp+180h+var_20]
0x18003f442  mov     rbx, [r11+38h]
0x18003f446  mov     rsi, [r11+40h]
0x18003f44a  mov     rsp, r11
0x18003f44d  pop     r15
0x18003f44f  pop     r14
0x18003f451  pop     r12
0x18003f453  pop     rdi
0x18003f454  pop     rbp
0x18003f455  retn
0x18003f456  mov     rcx, [rsp+180h+Block]; Block
0x18003f45b  test    rcx, rcx
0x18003f45e  jz      short loc_18003F465
0x18003f460  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f465  mov     eax, ebx
0x18003f467  jmp     short loc_18003F42E
```
