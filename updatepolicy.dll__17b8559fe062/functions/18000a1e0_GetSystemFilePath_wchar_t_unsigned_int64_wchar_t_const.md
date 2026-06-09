# GetSystemFilePath(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x18000a1e0`
- end: `0x18000a2a2`
- name: `?GetSystemFilePath@@YAJPEA_W_KPEB_W@Z`
- size: `194`
- prototype: `__int64 __fastcall(wchar_t *, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003128`

## callees

- `0x1800061b0`
- `0x180006858`
- `0x18000a1e0`
- `0x180015870`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a217`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000a217`

## pseudocode

```c
__int64 __fastcall GetSystemFilePath(wchar_t *a1, __int64 a2, const wchar_t *a3)
{
  __int64 v3; // rbx
  __int64 SystemDirectoryW; // rcx
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a1 = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(&Src + v3) );
  SystemDirectoryW = GetSystemDirectoryW(a1, 0x104u);
  if ( (unsigned __int64)(v3 + SystemDirectoryW + 1) < 0x104 )
  {
    if ( SystemDirectoryW )
    {
      a1[SystemDirectoryW] = 92;
      memmove(&a1[SystemDirectoryW + 1], &Src, 2 * v3 + 2);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x25,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safelib.cpp",
               v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safelib.cpp",
      (const char *)0x8007007ALL,
      v8);
    return 2147942522LL;
  }
}

```

## disassembly

```asm
0x18000a1e0  mov     [rsp+arg_0], rbx
0x18000a1e5  mov     [rsp+arg_8], rbp
0x18000a1ea  mov     [rsp+arg_10], rdi
0x18000a1ef  push    r14; int
0x18000a1f1  sub     rsp, 20h
0x18000a1f5  xor     ebp, ebp
0x18000a1f7  lea     r14, Src
0x18000a1fe  mov     [rcx], bp
0x18000a201  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a205  mov     rdi, rcx
0x18000a208  inc     rbx
0x18000a20b  cmp     [r14+rbx*2], bp
0x18000a210  jnz     short loc_18000A208
0x18000a212  mov     edx, 104h; uSize
0x18000a217  call    cs:__imp_GetSystemDirectoryW
0x18000a21d  mov     ecx, eax
0x18000a21f  lea     rax, [rcx+1]
0x18000a223  add     rax, rbx
0x18000a226  cmp     rax, 104h
0x18000a22c  jb      short loc_18000A250
0x18000a22e  mov     rcx, [rsp+28h]; this
0x18000a233  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000a23a  mov     ebx, 8007007Ah
0x18000a23f  mov     edx, 24h ; '$'; void *
0x18000a244  mov     r9d, ebx; char *
0x18000a247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a24c  mov     eax, ebx
0x18000a24e  jmp     short loc_18000A28C
0x18000a250  test    rcx, rcx
0x18000a253  jnz     short loc_18000A26D
0x18000a255  mov     rcx, [rsp+28h]; this
0x18000a25a  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000a261  mov     edx, 25h ; '%'; void *
0x18000a266  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a26b  jmp     short loc_18000A28C
0x18000a26d  mov     word ptr [rdi+rcx*2], 5Ch ; '\'
0x18000a273  lea     r8, ds:2[rbx*2]; Size
0x18000a27b  inc     rcx
0x18000a27e  mov     rdx, r14; Src
0x18000a281  lea     rcx, [rdi+rcx*2]; void *
0x18000a285  call    memmove
0x18000a28a  xor     eax, eax
0x18000a28c  mov     rbx, [rsp+28h+arg_0]
0x18000a291  mov     rbp, [rsp+28h+arg_8]
0x18000a296  mov     rdi, [rsp+28h+arg_10]
0x18000a29b  add     rsp, 20h
0x18000a29f  pop     r14
0x18000a2a1  retn
```
