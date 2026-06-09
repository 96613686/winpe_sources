# wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x180026f8c`
- end: `0x180027011`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180027fd0`
- `0x1800339f8`
- `0x180033d40`

## callees

- `0x1800267f8`
- `0x180026f8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026fd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026fd5`

## string_xrefs

- `0x180026fba`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HLOCAL *__fastcall wil::make_unique_hlocal_nothrow<unsigned short [0]>(
        HLOCAL *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12CE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  *a1 = LocalAlloc(0, 2 * a2);
  v6 = *a1;
  if ( *a1 )
  {
    v7 = &v6[v5];
    while ( v6 != v7 )
      *v6++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180026f8c  mov     [rsp+arg_8], rbx
0x180026f91  mov     [rsp+arg_0], rcx
0x180026f96  push    rdi
0x180026f97  sub     rsp, 30h
0x180026f9b  mov     rbx, rcx
0x180026f9e  mov     [rsp+38h+var_18], 0
0x180026fa6  mov     rcx, [rsp+38h]; this
0x180026fab  mov     rax, 7FFFFFFFFFFFFFFFh
0x180026fb5  cmp     rdx, rax
0x180026fb8  jbe     short loc_180026FCC
0x180026fba  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026fc1  mov     edx, 12CEh; void *
0x180026fc6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180026fcc  lea     rdi, [rdx+rdx]
0x180026fd0  mov     rdx, rdi; uBytes
0x180026fd3  xor     ecx, ecx; uFlags
0x180026fd5  call    cs:__imp_LocalAlloc
0x180026fdb  mov     [rbx], rax
0x180026fde  mov     [rsp+38h+var_18], 1
0x180026fe6  mov     rax, [rbx]
0x180026fe9  test    rax, rax
0x180026fec  jz      short loc_180027002
0x180026fee  lea     rcx, [rax+rdi]
0x180026ff2  jmp     short loc_180026FFD
0x180026ff4  xor     edx, edx
0x180026ff6  mov     [rax], dx
0x180026ff9  add     rax, 2
0x180026ffd  cmp     rax, rcx
0x180027000  jnz     short loc_180026FF4
0x180027002  mov     rax, rbx
0x180027005  mov     rbx, [rsp+38h+arg_8]
0x18002700a  add     rsp, 30h
0x18002700e  pop     rdi
0x18002700f  retn
```
