# UtilGetParentDirectory(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18000f5e0`
- end: `0x18000f6df`
- name: `?UtilGetParentDirectory@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18000e0a0`

## callees

- `0x18000cb10`
- `0x18000f5e0`
- `0x180011648`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18000f654`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18000f654`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18000f699`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18000f699`

## string_xrefs

- `0x18000f602`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x18000f66a`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
__int64 __fastcall UtilGetParentDirectory(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 result; // rax
  unsigned __int64 v6; // rbx
  __int64 v7; // r8
  HRESULT v8; // esi
  __int64 v9; // rdx
  PWSTR v10; // rcx
  WCHAR *v11; // rcx
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 6164;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)v3,
      v12);
    return v3;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, a1) )
  {
    v3 = -2147024882;
    v4 = 6168;
    goto LABEL_3;
  }
  v8 = PathCchRemoveBackslash(*(PWSTR *)a2, ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) + 1);
  if ( v8 < 0 )
  {
    v9 = 6176;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)(unsigned int)v8,
      v12);
    return (unsigned int)v8;
  }
  if ( (unsigned int)v8 > 1 )
    return 2147500037LL;
  v8 = PathCchRemoveFileSpec(*(PWSTR *)a2, ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) + 1);
  if ( v8 < 0 )
  {
    v9 = 6181;
    goto LABEL_10;
  }
  v10 = *(PWSTR *)a2;
  do
    ++v6;
  while ( v10[v6] );
  if ( v6 > (__int64)(*(_QWORD *)(a2 + 8) - (_QWORD)v10) >> 1 )
    __int2c();
  v11 = &v10[v6];
  result = 0;
  *(_QWORD *)(a2 + 8) = v11;
  *v11 = 0;
  return result;
}

```

## disassembly

```asm
0x18000f5e0  push    rbx
0x18000f5e2  push    rbp
0x18000f5e3  push    rsi
0x18000f5e4  push    rdi
0x18000f5e5  sub     rsp, 28h
0x18000f5e9  xor     ebp, ebp
0x18000f5eb  mov     rdi, rdx
0x18000f5ee  test    rcx, rcx
0x18000f5f1  jnz     short loc_18000F618
0x18000f5f3  mov     ebx, 80070057h
0x18000f5f8  mov     edx, 1814h; void *
0x18000f5fd  mov     rcx, [rsp+48h]; this
0x18000f602  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18000f609  mov     r9d, ebx; char *
0x18000f60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f611  mov     eax, ebx
0x18000f613  jmp     loc_18000F6D6
0x18000f618  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f61c  mov     r8, rbx
0x18000f61f  inc     r8
0x18000f622  cmp     [rcx+r8*2], bp
0x18000f627  jnz     short loc_18000F61F
0x18000f629  mov     rdx, rcx
0x18000f62c  mov     rcx, rdi
0x18000f62f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000f634  test    al, al
0x18000f636  jnz     short loc_18000F644
0x18000f638  mov     ebx, 8007000Eh
0x18000f63d  mov     edx, 1818h
0x18000f642  jmp     short loc_18000F5FD
0x18000f644  mov     rdx, [rdi+8]
0x18000f648  sub     rdx, [rdi]
0x18000f64b  mov     rcx, [rdi]; pszPath
0x18000f64e  sar     rdx, 1
0x18000f651  inc     rdx; cchPath
0x18000f654  call    cs:__imp_PathCchRemoveBackslash
0x18000f65a  mov     esi, eax
0x18000f65c  test    eax, eax
0x18000f65e  jns     short loc_18000F67D
0x18000f660  mov     edx, 1820h; void *
0x18000f665  mov     rcx, [rsp+48h]; this
0x18000f66a  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x18000f671  mov     r9d, esi; char *
0x18000f674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f679  mov     eax, esi
0x18000f67b  jmp     short loc_18000F6D6
0x18000f67d  cmp     esi, 1
0x18000f680  jbe     short loc_18000F689
0x18000f682  mov     eax, 80004005h
0x18000f687  jmp     short loc_18000F6D6
0x18000f689  mov     rdx, [rdi+8]
0x18000f68d  sub     rdx, [rdi]
0x18000f690  mov     rcx, [rdi]; pszPath
0x18000f693  sar     rdx, 1
0x18000f696  inc     rdx; cchPath
0x18000f699  call    cs:__imp_PathCchRemoveFileSpec
0x18000f69f  mov     esi, eax
0x18000f6a1  test    eax, eax
0x18000f6a3  jns     short loc_18000F6AC
0x18000f6a5  mov     edx, 1825h
0x18000f6aa  jmp     short loc_18000F665
0x18000f6ac  mov     rcx, [rdi]
0x18000f6af  inc     rbx
0x18000f6b2  cmp     [rcx+rbx*2], bp
0x18000f6b6  jnz     short loc_18000F6AF
0x18000f6b8  mov     rax, [rdi+8]
0x18000f6bc  sub     rax, rcx
0x18000f6bf  sar     rax, 1
0x18000f6c2  cmp     rbx, rax
0x18000f6c5  jbe     short loc_18000F6C9
0x18000f6c7  int     2Ch; Windows NT - assertion failure
0x18000f6c9  lea     rcx, [rcx+rbx*2]
0x18000f6cd  xor     eax, eax
0x18000f6cf  mov     [rdi+8], rcx
0x18000f6d3  mov     [rcx], bp
0x18000f6d6  add     rsp, 28h
0x18000f6da  pop     rdi
0x18000f6db  pop     rsi
0x18000f6dc  pop     rbp
0x18000f6dd  pop     rbx
0x18000f6de  retn
```
