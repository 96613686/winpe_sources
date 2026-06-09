# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x1800228e8`
- end: `0x180022ad0`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800227f0`

## callees

- `0x1800228e8`
- `0x1800291d4`
- `0x18002aa24`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180022aa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180022aa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022989`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        __int64 a1,
        ULONGLONG a2)
{
  _WORD *v2; // r15
  __int64 v4; // rcx
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rsi
  ULONGLONG v7; // r9
  HRESULT v8; // ebx
  _WORD *v10; // rax
  _WORD *v11; // rdx
  unsigned __int64 v12; // rax
  _WORD *v13; // rcx
  __int64 v14; // r9
  ULONGLONG v15; // r14
  LPVOID v16; // rax
  ULONGLONG pullResult; // [rsp+20h] [rbp-38h] BYREF

  v2 = (_WORD *)a2;
  if ( !a2 )
  {
    v8 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    return (unsigned int)v8;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    return (unsigned int)-2147024362;
  v7 = *(_QWORD *)(a1 + 16);
  if ( v7 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v4;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v4) );
      }
      else
      {
        v4 = 0;
      }
      *(_QWORD *)(a1 + 8) = v4;
    }
    else
    {
      v4 = *(_QWORD *)(a1 + 8);
    }
    v7 = (v4 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v7;
  }
  if ( v7 )
  {
    v8 = 0;
    if ( v6 > v7 )
    {
      pullResult = 0;
      v8 = ULongLongMult(v7, a2, &pullResult);
      if ( v8 >= 0 )
      {
        v15 = pullResult;
        if ( pullResult - v14 > 0x800 )
          v15 = v14 + 2048;
        if ( v6 > v15 )
          v15 = v5 + 1;
        v16 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v15);
        if ( !v16 )
          return (unsigned int)-2147024882;
        *(_QWORD *)(a1 + 16) = v15;
        *(_QWORD *)a1 = v16;
        goto LABEL_13;
      }
    }
LABEL_12:
    if ( v8 < 0 )
      return (unsigned int)v8;
    goto LABEL_13;
  }
  if ( !is_mul_ok(v6, 2u) )
    return (unsigned int)-2147024362;
  v10 = CoTaskMemAlloc(2 * v6);
  if ( !v10 )
  {
    v8 = -2147024882;
    goto LABEL_12;
  }
  *(_QWORD *)(a1 + 16) = v6;
  v8 = 0;
  *(_QWORD *)a1 = v10;
  *v10 = 0;
LABEL_13:
  if ( v5 != -1 )
  {
    v11 = *(_WORD **)a1;
    if ( v5 > 0x7FFFFFFE || v6 > 0x7FFFFFFF )
    {
      *v11 = 0;
    }
    else
    {
      v12 = v5;
      do
      {
        if ( !v12 )
          break;
        if ( !*v2 )
          break;
        *v11++ = *v2++;
        --v12;
        --v6;
      }
      while ( v6 );
      v13 = v11 - 1;
      if ( v6 )
        v13 = v11;
      *v13 = 0;
    }
  }
  *(_QWORD *)(a1 + 8) = v5;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800228e8  mov     [rsp+arg_10], rbx
0x1800228ed  mov     [rsp+arg_18], rbp
0x1800228f2  push    rsi
0x1800228f3  push    rdi
0x1800228f4  push    r12
0x1800228f6  push    r14
0x1800228f8  push    r15
0x1800228fa  sub     rsp, 30h
0x1800228fe  mov     rax, cs:__security_cookie
0x180022905  xor     rax, rsp
0x180022908  mov     [rsp+58h+var_30], rax
0x18002290d  xor     r12d, r12d
0x180022910  mov     r15, rdx
0x180022913  mov     rdi, rcx
0x180022916  test    rdx, rdx
0x180022919  jz      loc_180022AC3
0x18002291f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180022923  mov     rbp, rcx
0x180022926  inc     rbp
0x180022929  cmp     [rdx+rbp*2], r12w
0x18002292e  jnz     short loc_180022926
0x180022930  lea     rsi, [rbp+1]
0x180022934  cmp     rsi, rbp
0x180022937  jb      short loc_18002295B
0x180022939  mov     r9, [rdi+10h]
0x18002293d  cmp     r9, rcx
0x180022940  jz      loc_180022A09
0x180022946  test    r9, r9
0x180022949  jnz     loc_180022A52
0x18002294f  lea     eax, [r9+2]
0x180022953  mul     rsi
0x180022956  test    rdx, rdx
0x180022959  jz      short loc_180022986
0x18002295b  mov     ebx, 80070216h
0x180022960  mov     eax, ebx
0x180022962  mov     rcx, [rsp+58h+var_30]
0x180022967  xor     rcx, rsp; StackCookie
0x18002296a  call    __security_check_cookie
0x18002296f  mov     rbx, [rsp+58h+arg_10]
0x180022974  mov     rbp, [rsp+58h+arg_18]
0x180022979  add     rsp, 30h
0x18002297d  pop     r15
0x18002297f  pop     r14
0x180022981  pop     r12
0x180022983  pop     rdi
0x180022984  pop     rsi
0x180022985  retn
0x180022986  mov     rcx, rax; cb
0x180022989  call    cs:__imp_CoTaskMemAlloc
0x18002298f  test    rax, rax
0x180022992  jz      loc_180022A48
0x180022998  mov     [rdi+10h], rsi
0x18002299c  mov     ebx, r12d
0x18002299f  mov     [rdi], rax
0x1800229a2  mov     [rax], r12w
0x1800229a6  jmp     short loc_1800229AC
0x1800229a8  test    ebx, ebx
0x1800229aa  js      short loc_180022960
0x1800229ac  test    rsi, rsi
0x1800229af  jz      short loc_1800229FA
0x1800229b1  mov     rdx, [rdi]
0x1800229b4  cmp     rbp, 7FFFFFFEh
0x1800229bb  ja      short loc_180022A03
0x1800229bd  cmp     rsi, 7FFFFFFFh
0x1800229c4  ja      short loc_180022A03
0x1800229c6  mov     rax, rbp
0x1800229c9  test    rax, rax
0x1800229cc  jz      short loc_1800229EB
0x1800229ce  movzx   ecx, word ptr [r15]
0x1800229d2  test    cx, cx
0x1800229d5  jz      short loc_1800229EB
0x1800229d7  mov     [rdx], cx
0x1800229da  add     r15, 2
0x1800229de  add     rdx, 2; ullMultiplier
0x1800229e2  dec     rax
0x1800229e5  sub     rsi, 1
0x1800229e9  jnz     short loc_1800229C9
0x1800229eb  test    rsi, rsi
0x1800229ee  lea     rcx, [rdx-2]
0x1800229f2  cmovnz  rcx, rdx
0x1800229f6  mov     [rcx], r12w
0x1800229fa  mov     [rdi+8], rbp
0x1800229fe  jmp     loc_180022960
0x180022a03  mov     [rdx], r12w
0x180022a07  jmp     short loc_1800229FA
0x180022a09  cmp     [rdi+8], rcx
0x180022a0d  jnz     short loc_180022A2C
0x180022a0f  mov     rax, [rdi]
0x180022a12  test    rax, rax
0x180022a15  jnz     short loc_180022A1C
0x180022a17  mov     rcx, r12
0x180022a1a  jmp     short loc_180022A26
0x180022a1c  inc     rcx
0x180022a1f  cmp     [rax+rcx*2], r12w
0x180022a24  jnz     short loc_180022A1C
0x180022a26  mov     [rdi+8], rcx
0x180022a2a  jmp     short loc_180022A30
0x180022a2c  mov     rcx, [rdi+8]
0x180022a30  mov     rax, [rdi]
0x180022a33  inc     rcx
0x180022a36  neg     rax
0x180022a39  sbb     r9, r9
0x180022a3c  and     r9, rcx
0x180022a3f  mov     [rdi+10h], r9
0x180022a43  jmp     loc_180022946
0x180022a48  mov     ebx, 8007000Eh
0x180022a4d  jmp     loc_1800229A8
0x180022a52  mov     ebx, r12d
0x180022a55  cmp     rsi, r9
0x180022a58  jbe     loc_1800229A8
0x180022a5e  lea     r8, [rsp+58h+pullResult]; pullResult
0x180022a63  mov     [rsp+58h+pullResult], r12
0x180022a68  mov     rcx, r9; ullMultiplicand
0x180022a6b  call    ULongLongMult
0x180022a70  mov     ebx, eax
0x180022a72  test    eax, eax
0x180022a74  js      loc_1800229A8
0x180022a7a  mov     r14, [rsp+58h+pullResult]
0x180022a7f  mov     rax, r14
0x180022a82  sub     rax, r9
0x180022a85  cmp     rax, 800h
0x180022a8b  jbe     short loc_180022A94
0x180022a8d  lea     r14, [r9+800h]
0x180022a94  mov     rcx, [rdi]; pv
0x180022a97  cmp     rsi, r14
0x180022a9a  cmova   r14, rsi
0x180022a9e  lea     rdx, [r14+r14]; cb
0x180022aa2  call    cs:__imp_CoTaskMemRealloc
0x180022aa8  test    rax, rax
0x180022aab  jz      short loc_180022AB9
0x180022aad  mov     [rdi+10h], r14
0x180022ab1  mov     [rdi], rax
0x180022ab4  jmp     loc_1800229AC
0x180022ab9  mov     ebx, 8007000Eh
0x180022abe  jmp     loc_180022960
0x180022ac3  mov     ebx, r12d
0x180022ac6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180022acb  jmp     loc_180022960
```
