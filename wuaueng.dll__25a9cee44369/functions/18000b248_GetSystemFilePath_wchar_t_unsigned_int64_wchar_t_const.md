# GetSystemFilePath(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x18000b248`
- end: `0x18000b30a`
- name: `?GetSystemFilePath@@YAJPEA_W_KPEB_W@Z`
- size: `194`
- prototype: `__int64 __fastcall(wchar_t *, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005524`

## callees

- `0x180003760`
- `0x180003784`
- `0x18000b248`
- `0x180015df0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b27f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b27f`

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
0x18000b248  mov     [rsp+arg_0], rbx
0x18000b24d  mov     [rsp+arg_8], rbp
0x18000b252  mov     [rsp+arg_10], rdi
0x18000b257  push    r14; int
0x18000b259  sub     rsp, 20h
0x18000b25d  xor     ebp, ebp
0x18000b25f  lea     r14, Src
0x18000b266  mov     [rcx], bp
0x18000b269  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000b26d  mov     rdi, rcx
0x18000b270  inc     rbx
0x18000b273  cmp     [r14+rbx*2], bp
0x18000b278  jnz     short loc_18000B270
0x18000b27a  mov     edx, 104h; uSize
0x18000b27f  call    cs:__imp_GetSystemDirectoryW
0x18000b285  mov     ecx, eax
0x18000b287  lea     rax, [rcx+1]
0x18000b28b  add     rax, rbx
0x18000b28e  cmp     rax, 104h
0x18000b294  jb      short loc_18000B2B8
0x18000b296  mov     rcx, [rsp+28h]; this
0x18000b29b  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000b2a2  mov     ebx, 8007007Ah
0x18000b2a7  mov     edx, 24h ; '$'; void *
0x18000b2ac  mov     r9d, ebx; char *
0x18000b2af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2b4  mov     eax, ebx
0x18000b2b6  jmp     short loc_18000B2F4
0x18000b2b8  test    rcx, rcx
0x18000b2bb  jnz     short loc_18000B2D5
0x18000b2bd  mov     rcx, [rsp+28h]; this
0x18000b2c2  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000b2c9  mov     edx, 25h ; '%'; void *
0x18000b2ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b2d3  jmp     short loc_18000B2F4
0x18000b2d5  mov     word ptr [rdi+rcx*2], 5Ch ; '\'
0x18000b2db  lea     r8, ds:2[rbx*2]; Size
0x18000b2e3  inc     rcx
0x18000b2e6  mov     rdx, r14; Src
0x18000b2e9  lea     rcx, [rdi+rcx*2]; void *
0x18000b2ed  call    memmove
0x18000b2f2  xor     eax, eax
0x18000b2f4  mov     rbx, [rsp+28h+arg_0]
0x18000b2f9  mov     rbp, [rsp+28h+arg_8]
0x18000b2fe  mov     rdi, [rsp+28h+arg_10]
0x18000b303  add     rsp, 20h
0x18000b307  pop     r14
0x18000b309  retn
```
