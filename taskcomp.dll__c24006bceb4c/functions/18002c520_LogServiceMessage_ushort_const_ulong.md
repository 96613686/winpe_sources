# LogServiceMessage(ushort const *,ulong)

- ea: `0x18002c520`
- end: `0x18002c5cb`
- name: `?LogServiceMessage@@YAXPEBGK@Z`
- size: `171`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180011d44`
- `0x18002c49c`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x18002c520`
- `0x18002cd24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c558`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c558`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c5b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c5b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c57b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c57b`

## string_xrefs

- `0x18002c585`: `"Task Scheduler Service" ** ERROR **\n`

## pseudocode

```c
void __fastcall LogServiceMessage(const unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v3; // eax
  unsigned __int64 v4; // rsi
  WCHAR *v5; // rax
  unsigned __int16 *v6; // rbx

  if ( ghLog )
  {
    v3 = 20480;
    if ( a2 <= 0x5000 )
      v3 = a2;
    v4 = ((unsigned __int64)v3 >> 1) + 65;
    v5 = (WCHAR *)LocalAlloc(0x40u, 2 * v4);
    v6 = v5;
    if ( v5 )
    {
      if ( !LoadStringW(g_hInstance, 0x470u, v5, 64) )
        StringCchCopyW(v6, v4, L"\"Task Scheduler Service\" ** ERROR **\n");
      if ( a1 )
        StringCchCatW(v6, v4, a1);
      WriteLog(v6);
      LocalFree(v6);
    }
  }
}

```

## disassembly

```asm
0x18002c520  mov     [rsp+arg_0], rbx
0x18002c525  mov     [rsp+arg_8], rsi
0x18002c52a  push    rdi
0x18002c52b  sub     rsp, 20h
0x18002c52f  cmp     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x18002c537  mov     rdi, rcx
0x18002c53a  jz      short loc_18002C5BB
0x18002c53c  mov     eax, 5000h
0x18002c541  mov     ecx, 40h ; '@'; uFlags
0x18002c546  cmp     edx, eax
0x18002c548  cmovbe  eax, edx
0x18002c54b  mov     esi, eax
0x18002c54d  shr     rsi, 1
0x18002c550  add     rsi, 41h ; 'A'
0x18002c554  lea     rdx, [rsi+rsi]; uBytes
0x18002c558  call    cs:__imp_LocalAlloc
0x18002c55e  mov     rbx, rax
0x18002c561  test    rax, rax
0x18002c564  jz      short loc_18002C5BB
0x18002c566  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002c56d  mov     r9d, 40h ; '@'; cchBufferMax
0x18002c573  mov     r8, rax; lpBuffer
0x18002c576  mov     edx, 470h; uID
0x18002c57b  call    cs:__imp_LoadStringW
0x18002c581  test    eax, eax
0x18002c583  jnz     short loc_18002C597
0x18002c585  lea     r8, aTaskSchedulerS_0; "\"Task Scheduler Service\" ** ERROR **"...
0x18002c58c  mov     rdx, rsi; unsigned __int64
0x18002c58f  mov     rcx, rbx; unsigned __int16 *
0x18002c592  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c597  test    rdi, rdi
0x18002c59a  jz      short loc_18002C5AA
0x18002c59c  mov     r8, rdi; unsigned __int16 *
0x18002c59f  mov     rdx, rsi; unsigned __int64
0x18002c5a2  mov     rcx, rbx; unsigned __int16 *
0x18002c5a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c5aa  mov     rcx, rbx; lpBuffer
0x18002c5ad  call    ?WriteLog@@YAXPEAG@Z; WriteLog(ushort *)
0x18002c5b2  mov     rcx, rbx; hMem
0x18002c5b5  call    cs:__imp_LocalFree
0x18002c5bb  mov     rbx, [rsp+28h+arg_0]
0x18002c5c0  mov     rsi, [rsp+28h+arg_8]
0x18002c5c5  add     rsp, 20h
0x18002c5c9  pop     rdi
0x18002c5ca  retn
```
