# LogServiceMessage(ushort const *,ulong)

- ea: `0x18002e304`
- end: `0x18002e3c6`
- name: `?LogServiceMessage@@YAXPEBGK@Z`
- size: `194`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012858`
- `0x18002e274`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x18002e304`
- `0x18002ebd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e340`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e340`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e3a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e3a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e369`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e369`

## string_xrefs

- `0x18002e379`: `"Task Scheduler Service" ** ERROR **\n`

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
0x18002e304  mov     [rsp+arg_0], rbx
0x18002e309  mov     [rsp+arg_8], rsi
0x18002e30e  push    rdi
0x18002e30f  sub     rsp, 20h
0x18002e313  cmp     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x18002e31b  mov     rdi, rcx
0x18002e31e  jz      loc_18002E3B5
0x18002e324  mov     eax, 5000h
0x18002e329  mov     ecx, 40h ; '@'; uFlags
0x18002e32e  cmp     edx, eax
0x18002e330  cmovbe  eax, edx
0x18002e333  mov     esi, eax
0x18002e335  shr     rsi, 1
0x18002e338  add     rsi, 41h ; 'A'
0x18002e33c  lea     rdx, [rsi+rsi]; uBytes
0x18002e340  call    cs:__imp_LocalAlloc
0x18002e347  nop     dword ptr [rax+rax+00h]
0x18002e34c  mov     rbx, rax
0x18002e34f  test    rax, rax
0x18002e352  jz      short loc_18002E3B5
0x18002e354  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002e35b  mov     r9d, 40h ; '@'; cchBufferMax
0x18002e361  mov     r8, rax; lpBuffer
0x18002e364  mov     edx, 470h; uID
0x18002e369  call    cs:__imp_LoadStringW
0x18002e370  nop     dword ptr [rax+rax+00h]
0x18002e375  test    eax, eax
0x18002e377  jnz     short loc_18002E38B
0x18002e379  lea     r8, aTaskSchedulerS_0; "\"Task Scheduler Service\" ** ERROR **"...
0x18002e380  mov     rdx, rsi; unsigned __int64
0x18002e383  mov     rcx, rbx; unsigned __int16 *
0x18002e386  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e38b  test    rdi, rdi
0x18002e38e  jz      short loc_18002E39E
0x18002e390  mov     r8, rdi; unsigned __int16 *
0x18002e393  mov     rdx, rsi; unsigned __int64
0x18002e396  mov     rcx, rbx; unsigned __int16 *
0x18002e399  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e39e  mov     rcx, rbx; lpBuffer
0x18002e3a1  call    ?WriteLog@@YAXPEAG@Z; WriteLog(ushort *)
0x18002e3a6  mov     rcx, rbx; hMem
0x18002e3a9  call    cs:__imp_LocalFree
0x18002e3b0  nop     dword ptr [rax+rax+00h]
0x18002e3b5  mov     rbx, [rsp+28h+arg_0]
0x18002e3ba  mov     rsi, [rsp+28h+arg_8]
0x18002e3bf  add     rsp, 20h
0x18002e3c3  pop     rdi
0x18002e3c4  retn
```
