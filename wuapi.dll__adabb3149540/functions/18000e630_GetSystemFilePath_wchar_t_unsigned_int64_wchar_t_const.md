# GetSystemFilePath(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x18000e630`
- end: `0x18000e6f2`
- name: `?GetSystemFilePath@@YAJPEA_W_KPEB_W@Z`
- size: `194`
- prototype: `__int64 __fastcall(wchar_t *, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007308`

## callees

- `0x180003760`
- `0x180003784`
- `0x18000e630`
- `0x180015e40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000e667`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000e667`

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
0x18000e630  mov     [rsp+arg_0], rbx
0x18000e635  mov     [rsp+arg_8], rbp
0x18000e63a  mov     [rsp+arg_10], rdi
0x18000e63f  push    r14; int
0x18000e641  sub     rsp, 20h
0x18000e645  xor     ebp, ebp
0x18000e647  lea     r14, Src
0x18000e64e  mov     [rcx], bp
0x18000e651  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e655  mov     rdi, rcx
0x18000e658  inc     rbx
0x18000e65b  cmp     [r14+rbx*2], bp
0x18000e660  jnz     short loc_18000E658
0x18000e662  mov     edx, 104h; uSize
0x18000e667  call    cs:__imp_GetSystemDirectoryW
0x18000e66d  mov     ecx, eax
0x18000e66f  lea     rax, [rcx+1]
0x18000e673  add     rax, rbx
0x18000e676  cmp     rax, 104h
0x18000e67c  jb      short loc_18000E6A0
0x18000e67e  mov     rcx, [rsp+28h]; this
0x18000e683  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000e68a  mov     ebx, 8007007Ah
0x18000e68f  mov     edx, 24h ; '$'; void *
0x18000e694  mov     r9d, ebx; char *
0x18000e697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e69c  mov     eax, ebx
0x18000e69e  jmp     short loc_18000E6DC
0x18000e6a0  test    rcx, rcx
0x18000e6a3  jnz     short loc_18000E6BD
0x18000e6a5  mov     rcx, [rsp+28h]; this
0x18000e6aa  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000e6b1  mov     edx, 25h ; '%'; void *
0x18000e6b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e6bb  jmp     short loc_18000E6DC
0x18000e6bd  mov     word ptr [rdi+rcx*2], 5Ch ; '\'
0x18000e6c3  lea     r8, ds:2[rbx*2]; Size
0x18000e6cb  inc     rcx
0x18000e6ce  mov     rdx, r14; Src
0x18000e6d1  lea     rcx, [rdi+rcx*2]; void *
0x18000e6d5  call    memmove
0x18000e6da  xor     eax, eax
0x18000e6dc  mov     rbx, [rsp+28h+arg_0]
0x18000e6e1  mov     rbp, [rsp+28h+arg_8]
0x18000e6e6  mov     rdi, [rsp+28h+arg_10]
0x18000e6eb  add     rsp, 20h
0x18000e6ef  pop     r14
0x18000e6f1  retn
```
