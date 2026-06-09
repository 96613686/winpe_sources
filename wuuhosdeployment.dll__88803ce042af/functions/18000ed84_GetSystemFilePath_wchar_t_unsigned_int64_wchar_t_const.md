# GetSystemFilePath(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x18000ed84`
- end: `0x18000ee44`
- name: `?GetSystemFilePath@@YAJPEA_W_KPEB_W@Z`
- size: `192`
- prototype: `int(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a094`
- `0x18003b800`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000ed84`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000edb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000edb9`

## pseudocode

```c
__int64 __fastcall GetSystemFilePath(wchar_t *a1, __int64 a2, const wchar_t *a3)
{
  __int64 v4; // rbx
  __int64 SystemDirectoryW; // rcx
  const char *v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a1 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a3[v4] );
  SystemDirectoryW = GetSystemDirectoryW(a1, 0x104u);
  if ( (unsigned __int64)(v4 + SystemDirectoryW + 1) < 0x104 )
  {
    if ( SystemDirectoryW )
    {
      a1[SystemDirectoryW] = 92;
      memmove(&a1[SystemDirectoryW + 1], a3, 2 * v4 + 2);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x25,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safelib.cpp",
               v7);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safelib.cpp",
      (const char *)0x8007007ALL,
      v9);
    return 2147942522LL;
  }
}

```

## disassembly

```asm
0x18000ed84  mov     [rsp+arg_0], rbx
0x18000ed89  mov     [rsp+arg_8], rsi
0x18000ed8e  mov     [rsp+arg_10], rdi
0x18000ed93  push    r14; int
0x18000ed95  sub     rsp, 20h
0x18000ed99  xor     r14d, r14d
0x18000ed9c  mov     rsi, r8
0x18000ed9f  mov     [rcx], r14w
0x18000eda3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000eda7  mov     rdi, rcx
0x18000edaa  inc     rbx
0x18000edad  cmp     [r8+rbx*2], r14w
0x18000edb2  jnz     short loc_18000EDAA
0x18000edb4  mov     edx, 104h; uSize
0x18000edb9  call    cs:__imp_GetSystemDirectoryW
0x18000edbf  mov     ecx, eax
0x18000edc1  lea     rax, [rcx+1]
0x18000edc5  add     rax, rbx
0x18000edc8  cmp     rax, 104h
0x18000edce  jb      short loc_18000EDF2
0x18000edd0  mov     rcx, [rsp+28h]; this
0x18000edd5  lea     r8, aCW1SSrcClientL_9; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000eddc  mov     ebx, 8007007Ah
0x18000ede1  mov     edx, 24h ; '$'; void *
0x18000ede6  mov     r9d, ebx; char *
0x18000ede9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000edee  mov     eax, ebx
0x18000edf0  jmp     short loc_18000EE2E
0x18000edf2  test    rcx, rcx
0x18000edf5  jnz     short loc_18000EE0F
0x18000edf7  mov     rcx, [rsp+28h]; this
0x18000edfc  lea     r8, aCW1SSrcClientL_9; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000ee03  mov     edx, 25h ; '%'; void *
0x18000ee08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ee0d  jmp     short loc_18000EE2E
0x18000ee0f  mov     word ptr [rdi+rcx*2], 5Ch ; '\'
0x18000ee15  lea     r8, ds:2[rbx*2]; Size
0x18000ee1d  inc     rcx
0x18000ee20  mov     rdx, rsi; Src
0x18000ee23  lea     rcx, [rdi+rcx*2]; void *
0x18000ee27  call    memmove
0x18000ee2c  xor     eax, eax
0x18000ee2e  mov     rbx, [rsp+28h+arg_0]
0x18000ee33  mov     rsi, [rsp+28h+arg_8]
0x18000ee38  mov     rdi, [rsp+28h+arg_10]
0x18000ee3d  add     rsp, 20h
0x18000ee41  pop     r14
0x18000ee43  retn
```
