# TVarString<16>::SetMinimalSize(unsigned __int64)

- ea: `0x18000c188`
- end: `0x18000c2ac`
- name: `?SetMinimalSize@?$TVarString@$0BA@@@QEAAX_K@Z`
- size: `292`
- prototype: `void __fastcall(_QWORD *, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000596c`
- `0x18000ee44`
- `0x18000f7e0`
- `0x18000fb0c`

## callees

- `0x180003f50`
- `0x18000c188`
- `0x18000c7ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c1d7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c1d7`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18000c1bf`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18000c1bf`

## string_xrefs

- `0x18000c273`: `onecoreuap\base\appmodel\search\filters\xml\varstr.h`
- `0x18000c297`: `onecoreuap\base\appmodel\search\filters\xml\varstr.h`

## pseudocode

```c
void __fastcall TVarString<16>::SetMinimalSize(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rdi
  _WORD *v4; // rsi
  _WORD *v5; // rcx
  __int64 v6; // rax
  _WORD *v7; // rax
  _WORD *v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rax
  _WORD *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = a2 + 1;
  if ( (unsigned __int64)(a2 + 1) > *a1 )
  {
    v4 = a1 + 2;
    v5 = (_WORD *)a1[7];
    if ( v5 == v4 )
    {
      v7 = malloc(2 * v2 + 2);
      a1[7] = v7;
      v8 = v7;
      if ( !v7 )
      {
        v13 = wil::verify_hresult<long>(2147942414LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\varstr.h",
          (const char *)v13,
          v14);
      }
      v9 = v2 + 1;
      if ( v2 != -1 )
      {
        if ( v9 > 0x7FFFFFFF || (v10 = *a1 + 1LL, v10 > 0x7FFFFFFE) )
        {
          *v8 = 0;
        }
        else
        {
          do
          {
            if ( !v10 )
              break;
            if ( !*v4 )
              break;
            *v8++ = *v4++;
            --v10;
            --v9;
          }
          while ( v9 );
          v11 = v8 - 1;
          if ( v9 )
            v11 = v8;
          *v11 = 0;
        }
      }
      *(_WORD *)(a1[7] + 2LL * *a1) = 0;
    }
    else
    {
      v6 = _o_realloc(v5, 2 * v2 + 2);
      if ( !v6 )
      {
        v12 = wil::verify_hresult<long>(2147942414LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\varstr.h",
          (const char *)v12,
          v14);
      }
      a1[7] = v6;
    }
    *a1 = v2;
  }
}

```

## disassembly

```asm
0x18000c188  mov     [rsp+arg_0], rbx
0x18000c18d  mov     [rsp+arg_8], rsi
0x18000c192  push    rdi; int
0x18000c193  sub     rsp, 20h
0x18000c197  lea     rdi, [rdx+1]
0x18000c19b  mov     rbx, rcx
0x18000c19e  cmp     rdi, [rcx]
0x18000c1a1  jbe     loc_18000C254
0x18000c1a7  lea     rsi, [rcx+10h]
0x18000c1ab  mov     rcx, [rcx+38h]
0x18000c1af  lea     rax, ds:2[rdi*2]
0x18000c1b7  cmp     rcx, rsi
0x18000c1ba  jz      short loc_18000C1D4
0x18000c1bc  mov     rdx, rax
0x18000c1bf  call    cs:__imp__o_realloc
0x18000c1c5  test    rax, rax
0x18000c1c8  jz      loc_18000C264
0x18000c1ce  mov     [rbx+38h], rax
0x18000c1d2  jmp     short loc_18000C251
0x18000c1d4  mov     rcx, rax; Size
0x18000c1d7  call    cs:__imp_malloc
0x18000c1dd  xor     edx, edx
0x18000c1df  mov     [rbx+38h], rax
0x18000c1e3  mov     rcx, rax
0x18000c1e6  test    rax, rax
0x18000c1e9  jz      loc_18000C288
0x18000c1ef  lea     r8, [rdi+1]
0x18000c1f3  test    r8, r8
0x18000c1f6  jz      short loc_18000C246
0x18000c1f8  cmp     r8, 7FFFFFFFh
0x18000c1ff  ja      short loc_18000C243
0x18000c201  mov     rax, [rbx]
0x18000c204  inc     rax
0x18000c207  cmp     rax, 7FFFFFFEh
0x18000c20d  ja      short loc_18000C243
0x18000c20f  test    rax, rax
0x18000c212  jz      short loc_18000C233
0x18000c214  movzx   r9d, word ptr [rsi]
0x18000c218  test    r9w, r9w
0x18000c21c  jz      short loc_18000C233
0x18000c21e  mov     [rcx], r9w
0x18000c222  add     rsi, 2
0x18000c226  add     rcx, 2
0x18000c22a  dec     rax
0x18000c22d  sub     r8, 1
0x18000c231  jnz     short loc_18000C20F
0x18000c233  test    r8, r8
0x18000c236  lea     rax, [rcx-2]
0x18000c23a  cmovnz  rax, rcx
0x18000c23e  mov     [rax], dx
0x18000c241  jmp     short loc_18000C246
0x18000c243  mov     [rcx], dx
0x18000c246  mov     rcx, [rbx]
0x18000c249  mov     rax, [rbx+38h]
0x18000c24d  mov     [rax+rcx*2], dx
0x18000c251  mov     [rbx], rdi
0x18000c254  mov     rbx, [rsp+28h+arg_0]
0x18000c259  mov     rsi, [rsp+28h+arg_8]
0x18000c25e  add     rsp, 20h
0x18000c262  pop     rdi
0x18000c263  retn
0x18000c264  mov     ecx, 8007000Eh
0x18000c269  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c26e  mov     rcx, [rsp+28h]; this
0x18000c273  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000c27a  mov     r9d, eax; char *
0x18000c27d  mov     edx, 0C9h; void *
0x18000c282  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c288  mov     ecx, 8007000Eh
0x18000c28d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c292  mov     rcx, [rsp+28h]; this
0x18000c297  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000c29e  mov     r9d, eax; char *
0x18000c2a1  mov     edx, 0DCh; void *
0x18000c2a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
