# HrCopyString(char const *,char * *)

- ea: `0x180034894`
- end: `0x18003495e`
- name: `?HrCopyString@@YAJPEBDPEAPEAD@Z`
- size: `202`
- prototype: `__int64 __fastcall(const char *, char **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180008bf0`
- `0x180014580`
- `0x180018c58`
- `0x180019fa4`

## callees

- `0x18000e350`
- `0x18002e8f0`
- `0x180034894`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800348f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800348f8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800348c6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800348c6`

## pseudocode

```c
__int64 __fastcall HrCopyString(const char *a1, char **a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rbx
  char *v6; // rax
  unsigned int v7; // ebx
  int v8; // eax

  if ( !a1 )
    return (unsigned int)-2147467261;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = v4 + 1;
  v6 = (char *)malloc(v4 + 1);
  *a2 = v6;
  if ( v6 )
  {
    v8 = StringCchCopyA(v6, v5, a1);
    v7 = v8;
    if ( v8 >= 0 )
    {
      if ( !v8 )
        return v7;
    }
    else
    {
      free(*a2);
      *a2 = 0;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids,
      (_DWORD)a1,
      v7);
  return v7;
}

```

## disassembly

```asm
0x180034894  mov     [rsp+arg_0], rbx
0x180034899  mov     [rsp+arg_8], rsi
0x18003489e  push    rdi
0x18003489f  sub     rsp, 30h
0x1800348a3  mov     rsi, rdx
0x1800348a6  mov     rdi, rcx
0x1800348a9  test    rcx, rcx
0x1800348ac  jz      loc_180034946
0x1800348b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800348b6  inc     rax
0x1800348b9  cmp     byte ptr [rcx+rax], 0
0x1800348bd  jnz     short loc_1800348B6
0x1800348bf  lea     rbx, [rax+1]
0x1800348c3  mov     rcx, rbx; Size
0x1800348c6  call    cs:__imp_malloc
0x1800348cd  nop     dword ptr [rax+rax+00h]
0x1800348d2  mov     [rsi], rax
0x1800348d5  test    rax, rax
0x1800348d8  jnz     short loc_1800348E1
0x1800348da  mov     ebx, 8007000Eh
0x1800348df  jmp     short loc_18003490F
0x1800348e1  mov     r8, rdi; char *
0x1800348e4  mov     rdx, rbx; unsigned __int64
0x1800348e7  mov     rcx, rax; char *
0x1800348ea  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800348ef  mov     ebx, eax
0x1800348f1  test    eax, eax
0x1800348f3  jns     short loc_18003490D
0x1800348f5  mov     rcx, [rsi]; Block
0x1800348f8  call    cs:__imp_free
0x1800348ff  nop     dword ptr [rax+rax+00h]
0x180034904  mov     qword ptr [rsi], 0
0x18003490b  jmp     short loc_18003490F
0x18003490d  jz      short loc_18003494B
0x18003490f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034916  lea     rax, WPP_GLOBAL_Control
0x18003491d  cmp     rcx, rax
0x180034920  jz      short loc_18003494B
0x180034922  test    byte ptr [rcx+1Ch], 1
0x180034926  jz      short loc_18003494B
0x180034928  mov     rcx, [rcx+10h]
0x18003492c  lea     r8, WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids
0x180034933  mov     edx, 1Ah
0x180034938  mov     [rsp+38h+var_18], ebx
0x18003493c  mov     r9, rdi
0x18003493f  call    WPP_SF_sd
0x180034944  jmp     short loc_18003494B
0x180034946  mov     ebx, 80004003h
0x18003494b  mov     rsi, [rsp+38h+arg_8]
0x180034950  mov     eax, ebx
0x180034952  mov     rbx, [rsp+38h+arg_0]
0x180034957  add     rsp, 30h
0x18003495b  pop     rdi
0x18003495c  retn
```
