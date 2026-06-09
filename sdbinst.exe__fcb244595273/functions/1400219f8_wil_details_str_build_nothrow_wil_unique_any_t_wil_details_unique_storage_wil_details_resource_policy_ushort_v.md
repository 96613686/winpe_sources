# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x1400219f8`
- end: `0x140021c61`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `617`
- prototype: `__int64 __fastcall(int *, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140021934`
- `0x14002198c`
- `0x1400281a0`
- `0x1400284c4`

## callees

- `0x140006844`
- `0x1400219f8`
- `0x14002474c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140021bc0`
- `KERNEL32!GetLastError` at `0x140021bc0`
- `KERNEL32!GetProcessHeap` at `0x140021a73`
- `KERNEL32!GetProcessHeap` at `0x140021bc8`
- `KERNEL32!GetProcessHeap` at `0x140021c17`
- `KERNEL32!GetProcessHeap` at `0x140021c34`
- `KERNEL32!GetProcessHeap` at `0x140021a73`
- `KERNEL32!GetProcessHeap` at `0x140021bc8`
- `KERNEL32!GetProcessHeap` at `0x140021c17`
- `KERNEL32!GetProcessHeap` at `0x140021c34`
- `KERNEL32!SetLastError` at `0x140021bde`
- `KERNEL32!SetLastError` at `0x140021bde`
- `KERNEL32!HeapFree` at `0x140021a81`
- `KERNEL32!HeapFree` at `0x140021bd6`
- `KERNEL32!HeapFree` at `0x140021c25`
- `KERNEL32!HeapFree` at `0x140021c42`
- `KERNEL32!HeapFree` at `0x140021a81`
- `KERNEL32!HeapFree` at `0x140021bd6`
- `KERNEL32!HeapFree` at `0x140021c25`
- `KERNEL32!HeapFree` at `0x140021c42`

## string_xrefs

- `0x140021a55`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140021bfe`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        int *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rbp
  int v8; // eax
  unsigned int v9; // ebx
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  void *v13; // rbx
  char *v14; // r8
  char *v15; // r15
  _WORD *v16; // rcx
  unsigned __int64 v17; // rdx
  signed int v18; // edi
  unsigned __int64 v19; // rax
  char *v20; // rdx
  char *v21; // r9
  __int64 v22; // r11
  char *v23; // rcx
  __int64 v24; // rax
  void *v25; // rsi
  DWORD LastError; // edi
  HANDLE v27; // rax
  HANDLE v28; // rax
  HANDLE v29; // rax
  int v30; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID lpMem; // [rsp+68h] [rbp+10h] BYREF

  v3 = a2;
  v5 = 0;
  v6 = a2;
  v7 = a2 + 16 * a3;
  if ( a2 != v7 )
  {
    do
    {
      v5 += *(_QWORD *)(v6 + 8);
      v6 += 16;
    }
    while ( v6 != v7 );
  }
  lpMem = 0;
  v8 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         &lpMem,
         0,
         v5);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      v30);
    v10 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    return v9;
  }
  v13 = lpMem;
  v14 = (char *)lpMem;
  v15 = (char *)lpMem + 2 * v5 + 2;
  if ( v3 == v7 )
  {
LABEL_35:
    if ( a1 == &v30 )
    {
      if ( v13 )
      {
        v29 = GetProcessHeap();
        HeapFree(v29, 0, v13);
      }
    }
    else
    {
      v25 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        LastError = GetLastError();
        v27 = GetProcessHeap();
        HeapFree(v27, 0, v25);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = v13;
    }
    return 0;
  }
  while ( 1 )
  {
    v16 = *(_WORD **)v3;
    if ( !*(_QWORD *)v3 )
      goto LABEL_34;
    v17 = (v15 - v14) >> 1;
    if ( !v14 )
    {
      if ( v17 )
      {
        v18 = -2147024809;
        goto LABEL_41;
      }
      goto LABEL_13;
    }
    if ( v17 > 0x7FFFFFFF )
      break;
LABEL_13:
    v19 = *(_QWORD *)(v3 + 8);
    if ( v19 < 0x7FFFFFFF )
    {
      if ( v17 )
      {
        v21 = v14;
        v22 = 0;
        do
        {
          if ( !v19 )
            break;
          if ( !*v16 )
            break;
          *(_WORD *)v21 = *v16++;
          v21 += 2;
          --v19;
          ++v22;
          --v17;
        }
        while ( v17 );
        v23 = v21 - 2;
        if ( v17 )
          v23 = v21;
        v24 = v22 - 1;
        v18 = v17 != 0 ? 0 : 0x8007007A;
        *(_WORD *)v23 = 0;
        if ( v17 )
          v24 = v22;
        v20 = &v14[2 * v24];
      }
      else
      {
        v20 = v14;
        v18 = 0;
        if ( v19 && *v16 )
        {
          if ( !v14 )
          {
            v18 = -2147024809;
            goto LABEL_42;
          }
          v18 = -2147024774;
        }
      }
      if ( v18 >= 0 || v18 == -2147024774 )
        v14 = v20;
    }
    else
    {
      v18 = -2147024809;
      if ( v17 )
        *(_WORD *)v14 = 0;
    }
    if ( v18 < 0 )
      goto LABEL_42;
LABEL_34:
    v3 += 16;
    if ( v3 == v7 )
      goto LABEL_35;
  }
  v18 = -2147024809;
LABEL_41:
  *(_WORD *)v14 = 0;
LABEL_42:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x791,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)(unsigned int)v18,
    v30);
  if ( v13 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v13);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400219f8  mov     [rsp+arg_0], rbx
0x1400219fd  mov     [rsp+arg_10], rbp
0x140021a02  push    rsi
0x140021a03  push    rdi
0x140021a04  push    r12
0x140021a06  push    r14
0x140021a08  push    r15
0x140021a0a  sub     rsp, 30h
0x140021a0e  add     r8, r8
0x140021a11  xor     r12d, r12d
0x140021a14  mov     rsi, rdx
0x140021a17  mov     r14, rcx
0x140021a1a  mov     edi, r12d
0x140021a1d  mov     rax, rdx
0x140021a20  lea     rbp, [rdx+r8*8]
0x140021a24  cmp     rdx, rbp
0x140021a27  jz      short loc_140021A36
0x140021a29  add     rdi, [rax+8]
0x140021a2d  add     rax, 10h
0x140021a31  cmp     rax, rbp
0x140021a34  jnz     short loc_140021A29
0x140021a36  mov     r8, rdi
0x140021a39  mov     [rsp+58h+lpMem], r12
0x140021a3e  xor     edx, edx
0x140021a40  lea     rcx, [rsp+58h+lpMem]
0x140021a45  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140021a4a  mov     ebx, eax
0x140021a4c  test    eax, eax
0x140021a4e  jns     short loc_140021A8E
0x140021a50  mov     rcx, [rsp+58h]; this
0x140021a55  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140021a5c  mov     r9d, eax; char *
0x140021a5f  mov     edx, 788h; void *
0x140021a64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021a69  mov     rdi, [rsp+58h+lpMem]
0x140021a6e  test    rdi, rdi
0x140021a71  jz      short loc_140021A87
0x140021a73  call    cs:__imp_GetProcessHeap
0x140021a79  mov     r8, rdi; lpMem
0x140021a7c  xor     edx, edx; dwFlags
0x140021a7e  mov     rcx, rax; hHeap
0x140021a81  call    cs:__imp_HeapFree
0x140021a87  mov     eax, ebx
0x140021a89  jmp     loc_140021C4A
0x140021a8e  mov     rbx, [rsp+58h+lpMem]
0x140021a93  mov     r8, rbx
0x140021a96  lea     r15, [rbx+2]
0x140021a9a  lea     r15, [r15+rdi*2]
0x140021a9e  cmp     rsi, rbp
0x140021aa1  jz      loc_140021BAE
0x140021aa7  mov     r9d, 8007007Ah
0x140021aad  mov     rcx, [rsi]
0x140021ab0  test    rcx, rcx
0x140021ab3  jz      loc_140021BA1
0x140021ab9  mov     rdx, r15
0x140021abc  sub     rdx, r8
0x140021abf  sar     rdx, 1
0x140021ac2  test    r8, r8
0x140021ac5  jnz     short loc_140021ADF
0x140021ac7  test    rdx, rdx
0x140021aca  jz      short loc_140021AEC
0x140021acc  mov     edi, 80070057h
0x140021ad1  test    rdx, rdx
0x140021ad4  jz      loc_140021BF9
0x140021ada  jmp     loc_140021BF5
0x140021adf  cmp     rdx, 7FFFFFFFh
0x140021ae6  ja      loc_140021BF0
0x140021aec  mov     rax, [rsi+8]
0x140021af0  cmp     rax, 7FFFFFFFh
0x140021af6  jb      short loc_140021B0F
0x140021af8  mov     edi, 80070057h
0x140021afd  test    rdx, rdx
0x140021b00  jz      loc_140021B9D
0x140021b06  mov     [r8], r12w
0x140021b0a  jmp     loc_140021B9D
0x140021b0f  test    rdx, rdx
0x140021b12  jnz     short loc_140021B33
0x140021b14  mov     rdx, r8
0x140021b17  mov     edi, r12d
0x140021b1a  test    rax, rax
0x140021b1d  jz      short loc_140021B91
0x140021b1f  cmp     [rcx], r12w
0x140021b23  jz      short loc_140021B91
0x140021b25  test    r8, r8
0x140021b28  jz      loc_140021BE9
0x140021b2e  mov     edi, r9d
0x140021b31  jmp     short loc_140021B91
0x140021b33  mov     r9, r8
0x140021b36  mov     r11, r12
0x140021b39  test    rax, rax
0x140021b3c  jz      short loc_140021B60
0x140021b3e  movzx   r10d, word ptr [rcx]
0x140021b42  test    r10w, r10w
0x140021b46  jz      short loc_140021B60
0x140021b48  mov     [r9], r10w
0x140021b4c  add     rcx, 2
0x140021b50  add     r9, 2
0x140021b54  dec     rax
0x140021b57  inc     r11
0x140021b5a  sub     rdx, 1
0x140021b5e  jnz     short loc_140021B39
0x140021b60  test    rdx, rdx
0x140021b63  lea     rcx, [r9-2]
0x140021b67  mov     rax, rdx
0x140021b6a  cmovnz  rcx, r9
0x140021b6e  neg     rax
0x140021b71  mov     r9d, 8007007Ah
0x140021b77  lea     rax, [r11-1]
0x140021b7b  sbb     edi, edi
0x140021b7d  not     edi
0x140021b7f  and     edi, r9d
0x140021b82  mov     [rcx], r12w
0x140021b86  test    rdx, rdx
0x140021b89  cmovnz  rax, r11
0x140021b8d  lea     rdx, [r8+rax*2]
0x140021b91  test    edi, edi
0x140021b93  jns     short loc_140021B9A
0x140021b95  cmp     edi, r9d
0x140021b98  jnz     short loc_140021B9D
0x140021b9a  mov     r8, rdx
0x140021b9d  test    edi, edi
0x140021b9f  js      short loc_140021BF9
0x140021ba1  add     rsi, 10h
0x140021ba5  cmp     rsi, rbp
0x140021ba8  jnz     loc_140021AAD
0x140021bae  lea     rax, [rsp+58h+var_38]
0x140021bb3  cmp     r14, rax
0x140021bb6  jz      short loc_140021C2F
0x140021bb8  mov     rsi, [r14]
0x140021bbb  test    rsi, rsi
0x140021bbe  jz      short loc_140021BE4
0x140021bc0  call    cs:__imp_GetLastError
0x140021bc6  mov     edi, eax
0x140021bc8  call    cs:__imp_GetProcessHeap
0x140021bce  mov     r8, rsi; lpMem
0x140021bd1  xor     edx, edx; dwFlags
0x140021bd3  mov     rcx, rax; hHeap
0x140021bd6  call    cs:__imp_HeapFree
0x140021bdc  mov     ecx, edi; dwErrCode
0x140021bde  call    cs:__imp_SetLastError
0x140021be4  mov     [r14], rbx
0x140021be7  jmp     short loc_140021C48
0x140021be9  mov     edi, 80070057h
0x140021bee  jmp     short loc_140021BF9
0x140021bf0  mov     edi, 80070057h
0x140021bf5  mov     [r8], r12w
0x140021bf9  mov     rcx, [rsp+58h]; this
0x140021bfe  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140021c05  mov     r9d, edi; char *
0x140021c08  mov     edx, 791h; void *
0x140021c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021c12  test    rbx, rbx
0x140021c15  jz      short loc_140021C2B
0x140021c17  call    cs:__imp_GetProcessHeap
0x140021c1d  mov     r8, rbx; lpMem
0x140021c20  xor     edx, edx; dwFlags
0x140021c22  mov     rcx, rax; hHeap
0x140021c25  call    cs:__imp_HeapFree
0x140021c2b  mov     eax, edi
0x140021c2d  jmp     short loc_140021C4A
0x140021c2f  test    rbx, rbx
0x140021c32  jz      short loc_140021C48
0x140021c34  call    cs:__imp_GetProcessHeap
0x140021c3a  mov     r8, rbx; lpMem
0x140021c3d  xor     edx, edx; dwFlags
0x140021c3f  mov     rcx, rax; hHeap
0x140021c42  call    cs:__imp_HeapFree
0x140021c48  xor     eax, eax
0x140021c4a  mov     rbx, [rsp+58h+arg_0]
0x140021c4f  mov     rbp, [rsp+58h+arg_10]
0x140021c54  add     rsp, 30h
0x140021c58  pop     r15
0x140021c5a  pop     r14
0x140021c5c  pop     r12
0x140021c5e  pop     rdi
0x140021c5f  pop     rsi
0x140021c60  retn
```
