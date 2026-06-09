# HrCopyString(char const *,char * *)

- ea: `0x180031f84`
- end: `0x180032041`
- name: `?HrCopyString@@YAJPEBDPEAPEAD@Z`
- size: `189`
- prototype: `__int64 __fastcall(const char *, char **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000770c`
- `0x1800097f0`
- `0x180014ec4`
- `0x180016838`

## callees

- `0x18000d030`
- `0x18002c90c`
- `0x180031f84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031fe2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031fe2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031fb6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031fb6`

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
0x180031f84  mov     [rsp+arg_0], rbx
0x180031f89  mov     [rsp+arg_8], rsi
0x180031f8e  push    rdi
0x180031f8f  sub     rsp, 30h
0x180031f93  mov     rsi, rdx
0x180031f96  mov     rdi, rcx
0x180031f99  test    rcx, rcx
0x180031f9c  jz      loc_18003202A
0x180031fa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031fa6  inc     rax
0x180031fa9  cmp     byte ptr [rcx+rax], 0
0x180031fad  jnz     short loc_180031FA6
0x180031faf  lea     rbx, [rax+1]
0x180031fb3  mov     rcx, rbx; Size
0x180031fb6  call    cs:__imp_malloc
0x180031fbc  mov     [rsi], rax
0x180031fbf  test    rax, rax
0x180031fc2  jnz     short loc_180031FCB
0x180031fc4  mov     ebx, 8007000Eh
0x180031fc9  jmp     short loc_180031FF3
0x180031fcb  mov     r8, rdi; char *
0x180031fce  mov     rdx, rbx; unsigned __int64
0x180031fd1  mov     rcx, rax; char *
0x180031fd4  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180031fd9  mov     ebx, eax
0x180031fdb  test    eax, eax
0x180031fdd  jns     short loc_180031FF1
0x180031fdf  mov     rcx, [rsi]; Block
0x180031fe2  call    cs:__imp_free
0x180031fe8  mov     qword ptr [rsi], 0
0x180031fef  jmp     short loc_180031FF3
0x180031ff1  jz      short loc_18003202F
0x180031ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ffa  lea     rax, WPP_GLOBAL_Control
0x180032001  cmp     rcx, rax
0x180032004  jz      short loc_18003202F
0x180032006  test    byte ptr [rcx+1Ch], 1
0x18003200a  jz      short loc_18003202F
0x18003200c  mov     rcx, [rcx+10h]
0x180032010  lea     r8, WPP_2a93b8cd1ba13cd6c891d054980ab5f0_Traceguids
0x180032017  mov     edx, 1Ah
0x18003201c  mov     [rsp+38h+var_18], ebx
0x180032020  mov     r9, rdi
0x180032023  call    WPP_SF_sd
0x180032028  jmp     short loc_18003202F
0x18003202a  mov     ebx, 80004003h
0x18003202f  mov     rsi, [rsp+38h+arg_8]
0x180032034  mov     eax, ebx
0x180032036  mov     rbx, [rsp+38h+arg_0]
0x18003203b  add     rsp, 30h
0x18003203f  pop     rdi
0x180032040  retn
```
