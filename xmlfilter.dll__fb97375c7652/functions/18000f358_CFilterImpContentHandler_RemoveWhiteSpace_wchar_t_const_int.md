# CFilterImpContentHandler::RemoveWhiteSpace(wchar_t const * &,int &)

- ea: `0x18000f358`
- end: `0x18000f415`
- name: `?RemoveWhiteSpace@CFilterImpContentHandler@@IEAAXAEAPEB_WAEAH@Z`
- size: `189`
- prototype: `void __fastcall(CFilterImpContentHandler *__hidden this, const wchar_t **, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f540`

## callees

- `0x18000f358`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000f382`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000f3d6`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000f382`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000f3d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFilterImpContentHandler::RemoveWhiteSpace(CFilterImpContentHandler *this, const wchar_t **a2, int *a3)
{
  const wchar_t *v3; // rbx
  const wchar_t *v6; // rbp
  const wchar_t *v7; // rcx
  __int64 v8; // rbx
  char *v9; // rbx

  v3 = *a2;
  v6 = &(*a2)[*a3];
  while ( v3 < v6 && (*v3 == 10 || *v3 == 13 || (unsigned int)_o_iswspace(*v3)) )
    ++v3;
  v7 = *a2;
  v8 = v3 - *a2;
  if ( (_DWORD)v8 )
  {
    *a3 -= v8 - 1;
    *a2 += (int)v8 - 1;
    v7 = *a2;
  }
  if ( *a3 )
  {
    v9 = (char *)&v7[*a3 - 1];
    if ( v9 >= (char *)v7 )
    {
      do
      {
        if ( *(_WORD *)v9 != 10 && *(_WORD *)v9 != 13 && !(unsigned int)_o_iswspace(*(unsigned __int16 *)v9) )
          break;
        v9 -= 2;
      }
      while ( v9 >= (char *)*a2 );
    }
    if ( v9 + 2 < (char *)&(*a2)[*a3 - 2] )
      *a3 = (v9 - (char *)*a2 + 2) >> 1;
  }
}

```

## disassembly

```asm
0x18000f358  push    rbx
0x18000f35a  push    rbp
0x18000f35b  push    rsi
0x18000f35c  push    rdi
0x18000f35d  sub     rsp, 28h
0x18000f361  mov     rbx, [rdx]
0x18000f364  mov     rsi, r8
0x18000f367  movsxd  rax, dword ptr [r8]
0x18000f36a  mov     rdi, rdx
0x18000f36d  lea     rbp, [rbx+rax*2]
0x18000f371  jmp     short loc_18000F390
0x18000f373  cmp     word ptr [rbx], 0Ah
0x18000f377  jz      short loc_18000F38C
0x18000f379  cmp     word ptr [rbx], 0Dh
0x18000f37d  jz      short loc_18000F38C
0x18000f37f  movzx   ecx, word ptr [rbx]
0x18000f382  call    cs:__imp__o_iswspace
0x18000f388  test    eax, eax
0x18000f38a  jz      short loc_18000F395
0x18000f38c  add     rbx, 2
0x18000f390  cmp     rbx, rbp
0x18000f393  jb      short loc_18000F373
0x18000f395  mov     rcx, [rdi]
0x18000f398  sub     rbx, rcx
0x18000f39b  sar     rbx, 1
0x18000f39e  test    ebx, ebx
0x18000f3a0  jz      short loc_18000F3B3
0x18000f3a2  lea     eax, [rbx-1]
0x18000f3a5  sub     [rsi], eax
0x18000f3a7  movsxd  rcx, eax
0x18000f3aa  add     rcx, rcx
0x18000f3ad  add     [rdi], rcx
0x18000f3b0  mov     rcx, [rdi]
0x18000f3b3  cmp     dword ptr [rsi], 0
0x18000f3b6  jz      short loc_18000F40C
0x18000f3b8  movsxd  rbx, dword ptr [rsi]
0x18000f3bb  dec     rbx
0x18000f3be  lea     rbx, [rcx+rbx*2]
0x18000f3c2  cmp     rbx, rcx
0x18000f3c5  jb      short loc_18000F3E9
0x18000f3c7  cmp     word ptr [rbx], 0Ah
0x18000f3cb  jz      short loc_18000F3E0
0x18000f3cd  cmp     word ptr [rbx], 0Dh
0x18000f3d1  jz      short loc_18000F3E0
0x18000f3d3  movzx   ecx, word ptr [rbx]
0x18000f3d6  call    cs:__imp__o_iswspace
0x18000f3dc  test    eax, eax
0x18000f3de  jz      short loc_18000F3E9
0x18000f3e0  sub     rbx, 2
0x18000f3e4  cmp     rbx, [rdi]
0x18000f3e7  jnb     short loc_18000F3C7
0x18000f3e9  movsxd  rax, dword ptr [rsi]
0x18000f3ec  mov     rdx, [rdi]
0x18000f3ef  add     rax, 0FFFFFFFFFFFFFFFEh
0x18000f3f3  lea     rcx, [rdx+rax*2]
0x18000f3f7  lea     rax, [rbx+2]
0x18000f3fb  cmp     rax, rcx
0x18000f3fe  jnb     short loc_18000F40C
0x18000f400  sub     rbx, rdx
0x18000f403  add     rbx, 2
0x18000f407  sar     rbx, 1
0x18000f40a  mov     [rsi], ebx
0x18000f40c  add     rsp, 28h
0x18000f410  pop     rdi
0x18000f411  pop     rsi
0x18000f412  pop     rbp
0x18000f413  pop     rbx
0x18000f414  retn
```
