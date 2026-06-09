# MapLocalPathToUNC(void *,ushort const *,ushort *,ulong)

- ea: `0x18000fa10`
- end: `0x18000fc5d`
- name: `?MapLocalPathToUNC@@YAJPEAXPEBGPEAGK@Z`
- size: `589`
- prototype: `__int64 __fastcall(void *, wchar_t *String2, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800053b0`

## callees

- `0x18000b3f0`
- `0x18000b4a0`
- `0x18000cc64`
- `0x18000f7dc`
- `0x18000f83c`
- `0x18000fa10`
- `0x18000fc64`
- `0x180010320`
- `0x1800103b0`
- `0x180011000`

## pseudocode

```c
__int64 __fastcall MapLocalPathToUNC(void *a1, wchar_t *String2, unsigned __int16 *a3)
{
  unsigned int CCHSharePath; // esi
  const unsigned __int16 *v7; // r8
  unsigned int Merit; // edi
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rax
  unsigned int v14; // ebx
  int v15; // ecx
  _BYTE v17[44]; // [rsp+40h] [rbp-6B8h] BYREF
  unsigned int v18; // [rsp+6Ch] [rbp-68Ch]
  unsigned int v19; // [rsp+70h] [rbp-688h]
  __int64 v20; // [rsp+78h] [rbp-680h]
  unsigned __int16 v21[262]; // [rsp+80h] [rbp-678h] BYREF
  int v22; // [rsp+28Ch] [rbp-46Ch]
  int v23; // [rsp+290h] [rbp-468h]
  int v24; // [rsp+294h] [rbp-464h]
  unsigned __int16 v25[264]; // [rsp+2A0h] [rbp-458h] BYREF
  unsigned __int16 v26[264]; // [rsp+4B0h] [rbp-248h] BYREF

  CShareEnumerator::CShareEnumerator((CShareEnumerator *)v17);
  CCHSharePath = 0;
  CShareEnumerator::Initialize((CShareEnumerator *)v17, a1, v7);
  Merit = 204799;
  while ( 1 )
  {
    v9 = v19 + 1;
    if ( (unsigned int)v9 >= v18 )
      break;
    v22 = -1;
    v23 = 0;
    v24 = 4096;
    ++v19;
    v10 = 9 * v9;
    v11 = *(_QWORD *)(v20 + 72 * v9);
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v11 + 2 * v12) );
    if ( v12 <= 0x104 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(*(_QWORD *)(v20 + 8 * v10 + 40) + 2 * v13) );
      if ( v13 <= 0x104
        && CShareEnumerator::CoversDrivePath((CShareEnumerator *)v17, String2)
        && CShareEnumerator::GetMerit((CShareEnumerator *)v17) > Merit )
      {
        StringCchCopyW(v25, 0x105u, *(const unsigned __int16 **)(v20 + 72LL * v19));
        StringCchCopyW(v26, 0x105u, *(const unsigned __int16 **)(v20 + 72LL * v19 + 40));
        Merit = CShareEnumerator::GetMerit((CShareEnumerator *)v17);
        CCHSharePath = CShareEnumerator::QueryCCHSharePath((CShareEnumerator *)v17);
      }
    }
  }
  if ( CCHSharePath )
  {
    v15 = StringCchCopyW(a3, 0x104u, v21);
    if ( v15 >= 0 )
    {
      v15 = StringCchCatW(a3, 0x104u, L"\\");
      if ( v15 >= 0 )
      {
        v15 = StringCchCatW(a3, 0x104u, v25);
        if ( v15 >= 0 )
        {
          if ( String2[CCHSharePath] != 92 )
            v15 = StringCchCatW(a3, 0x104u, L"\\");
          if ( v15 >= 0 )
            v15 = StringCchCatW(a3, 0x104u, &String2[CCHSharePath]);
        }
      }
    }
    v14 = 0;
    if ( v15 < 0 )
      v14 = 3;
  }
  else
  {
    v14 = -2147024893;
  }
  CShareEnumerator::~CShareEnumerator((CShareEnumerator *)v17);
  return v14;
}

```

## disassembly

```asm
0x18000fa10  mov     [rsp+arg_0], rbx
0x18000fa15  push    rsi
0x18000fa16  push    rdi
0x18000fa17  push    r12
0x18000fa19  push    r14
0x18000fa1b  push    r15
0x18000fa1d  sub     rsp, 6D0h
0x18000fa24  mov     rax, cs:__security_cookie
0x18000fa2b  xor     rax, rsp
0x18000fa2e  mov     [rsp+6F8h+var_38], rax
0x18000fa36  mov     rbx, r8
0x18000fa39  mov     r14, rdx
0x18000fa3c  mov     rdi, rcx
0x18000fa3f  lea     rcx, [rsp+6F8h+var_6B8]; this
0x18000fa44  call    ??0CShareEnumerator@@QEAA@XZ; CShareEnumerator::CShareEnumerator(void)
0x18000fa49  xor     r15d, r15d
0x18000fa4c  mov     esi, r15d
0x18000fa4f  mov     rdx, rdi; void *
0x18000fa52  lea     rcx, [rsp+6F8h+var_6B8]; this
0x18000fa57  call    ?Initialize@CShareEnumerator@@QEAAXPEAXPEBG@Z; CShareEnumerator::Initialize(void *,ushort const *)
0x18000fa5c  mov     edi, 31FFFh
0x18000fa61  mov     [rsp+6F8h+var_6D0], edi
0x18000fa65  mov     r12d, 104h
0x18000fa6b  mov     eax, [rsp+6F8h+var_688]
0x18000fa6f  inc     eax
0x18000fa71  cmp     eax, [rsp+6F8h+var_68C]
0x18000fa75  jnb     loc_18000FB67
0x18000fa7b  mov     [rsp+6F8h+var_46C], 0FFFFFFFFh
0x18000fa86  mov     [rsp+6F8h+var_468], r15d
0x18000fa8e  mov     [rsp+6F8h+var_464], 1000h
0x18000fa99  mov     [rsp+6F8h+var_688], eax
0x18000fa9d  lea     rcx, [rax+rax*8]
0x18000faa1  mov     rdx, [rsp+6F8h+var_680]
0x18000faa6  mov     r8, [rdx+rcx*8]
0x18000faaa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000faae  inc     rax
0x18000fab1  cmp     [r8+rax*2], r15w
0x18000fab6  jnz     short loc_18000FAAE
0x18000fab8  cmp     rax, r12
0x18000fabb  ja      loc_18000FB62
0x18000fac1  mov     r8, [rdx+rcx*8+28h]
0x18000fac6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000faca  inc     rax
0x18000facd  cmp     [r8+rax*2], r15w
0x18000fad2  jnz     short loc_18000FACA
0x18000fad4  cmp     rax, r12
0x18000fad7  ja      loc_18000FB62
0x18000fadd  mov     rdx, r14; String2
0x18000fae0  lea     rcx, [rsp+6F8h+var_6B8]; this
0x18000fae5  call    ?CoversDrivePath@CShareEnumerator@@QEAAHPEBG@Z; CShareEnumerator::CoversDrivePath(ushort const *)
0x18000faea  test    eax, eax
0x18000faec  jz      short loc_18000FB62
0x18000faee  lea     rcx, [rsp+6F8h+var_6B8]; this
0x18000faf3  call    ?GetMerit@CShareEnumerator@@UEAAKXZ; CShareEnumerator::GetMerit(void)
0x18000faf8  cmp     eax, edi
0x18000fafa  jbe     short loc_18000FB62
0x18000fafc  mov     eax, [rsp+6F8h+var_688]
0x18000fb00  lea     rcx, [rax+rax*8]
0x18000fb04  mov     r8, [rsp+6F8h+var_680]
0x18000fb09  mov     r8, [r8+rcx*8]; unsigned __int16 *
0x18000fb0d  mov     edi, 105h
0x18000fb12  mov     edx, edi; unsigned __int64
0x18000fb14  lea     rcx, [rsp+6F8h+var_458]; unsigned __int16 *
0x18000fb1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fb21  mov     eax, [rsp+6F8h+var_688]
0x18000fb25  lea     rcx, [rax+rax*8]
0x18000fb29  mov     r8, [rsp+6F8h+var_680]
0x18000fb2e  mov     r8, [r8+rcx*8+28h]; unsigned __int16 *
0x18000fb33  mov     edx, edi; unsigned __int64
0x18000fb35  lea     rcx, [rsp+6F8h+var_248]; unsigned __int16 *
0x18000fb3d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fb42  lea     rcx, [rsp+6F8h+var_6B8]; this
0x18000fb47  call    ?GetMerit@CShareEnumerator@@UEAAKXZ; CShareEnumerator::GetMerit(void)
0x18000fb4c  mov     edi, eax
0x18000fb4e  mov     [rsp+6F8h+var_6D0], eax
0x18000fb52  lea     rcx, [rsp+6F8h+var_6B8]; this
0x18000fb57  call    ?QueryCCHSharePath@CShareEnumerator@@QEAAKXZ; CShareEnumerator::QueryCCHSharePath(void)
0x18000fb5c  mov     esi, eax
0x18000fb5e  mov     [rsp+6F8h+var_6CC], eax
0x18000fb62  jmp     loc_18000FA6B
0x18000fb67  test    esi, esi
0x18000fb69  jnz     short loc_18000FB79
0x18000fb6b  mov     ebx, 80070003h
0x18000fb70  mov     [rsp+6F8h+var_6D4], ebx
0x18000fb74  jmp     loc_18000FC29
0x18000fb79  mov     [rsp+6F8h+var_6D8], r15d
0x18000fb7e  lea     r8, [rsp+6F8h+var_678]; unsigned __int16 *
0x18000fb86  mov     rdx, r12; unsigned __int64
0x18000fb89  mov     rcx, rbx; unsigned __int16 *
0x18000fb8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fb91  mov     ecx, eax
0x18000fb93  mov     [rsp+6F8h+var_6D8], eax
0x18000fb97  test    eax, eax
0x18000fb99  js      short loc_18000FC10
0x18000fb9b  lea     r8, asc_180015BC8; "\\"
0x18000fba2  mov     rdx, r12; unsigned __int64
0x18000fba5  mov     rcx, rbx; unsigned __int16 *
0x18000fba8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fbad  mov     ecx, eax
0x18000fbaf  mov     [rsp+6F8h+var_6D8], eax
0x18000fbb3  test    eax, eax
0x18000fbb5  js      short loc_18000FC10
0x18000fbb7  lea     r8, [rsp+6F8h+var_458]; unsigned __int16 *
0x18000fbbf  mov     rdx, r12; unsigned __int64
0x18000fbc2  mov     rcx, rbx; unsigned __int16 *
0x18000fbc5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fbca  mov     ecx, eax
0x18000fbcc  mov     [rsp+6F8h+var_6D8], eax
0x18000fbd0  test    eax, eax
0x18000fbd2  js      short loc_18000FC10
0x18000fbd4  mov     eax, esi
0x18000fbd6  lea     rdi, [r14+rax*2]
0x18000fbda  cmp     word ptr [rdi], 5Ch ; '\'
0x18000fbde  jz      short loc_18000FBF8
0x18000fbe0  lea     r8, asc_180015BC8; "\\"
0x18000fbe7  mov     rdx, r12; unsigned __int64
0x18000fbea  mov     rcx, rbx; unsigned __int16 *
0x18000fbed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fbf2  mov     ecx, eax
0x18000fbf4  mov     [rsp+6F8h+var_6D8], eax
0x18000fbf8  test    ecx, ecx
0x18000fbfa  js      short loc_18000FC10
0x18000fbfc  mov     r8, rdi; unsigned __int16 *
0x18000fbff  mov     rdx, r12; unsigned __int64
0x18000fc02  mov     rcx, rbx; unsigned __int16 *
0x18000fc05  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fc0a  mov     ecx, eax
0x18000fc0c  mov     [rsp+6F8h+var_6D8], eax
0x18000fc10  mov     ebx, r15d
0x18000fc13  mov     eax, 3
0x18000fc18  test    ecx, ecx
0x18000fc1a  cmovs   ebx, eax
0x18000fc1d  mov     [rsp+6F8h+var_6D4], ebx
0x18000fc21  jmp     short loc_18000FC29
0x18000fc23  mov     ebx, eax
0x18000fc25  mov     [rsp+6F8h+var_6D4], eax
0x18000fc29  lea     rcx, [rsp+6F8h+var_6B8]; this
0x18000fc2e  call    ??1CShareEnumerator@@QEAA@XZ; CShareEnumerator::~CShareEnumerator(void)
0x18000fc33  mov     eax, ebx
0x18000fc35  mov     rcx, [rsp+6F8h+var_38]
0x18000fc3d  xor     rcx, rsp; StackCookie
0x18000fc40  call    __security_check_cookie
0x18000fc45  mov     rbx, [rsp+6F8h+arg_0]
0x18000fc4d  add     rsp, 6D0h
0x18000fc54  pop     r15
0x18000fc56  pop     r14
0x18000fc58  pop     r12
0x18000fc5a  pop     rdi
0x18000fc5b  pop     rsi
0x18000fc5c  retn
0x1800118b4  push    rbp
0x1800118b6  sub     rsp, 20h
0x1800118ba  mov     rbp, rdx
0x1800118bd  mov     eax, 1
0x1800118c2  add     rsp, 20h
0x1800118c6  pop     rbp
0x1800118c7  retn
```
