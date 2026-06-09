# StartListeningThread(void)

- ea: `0x180015460`
- end: `0x180015610`
- name: `?StartListeningThread@@YAJXZ`
- size: `432`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015020`
- `0x1800301f8`

## callees

- `0x180015370`
- `0x180015460`
- `0x180018138`
- `0x18001d9a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800154ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800154ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001557c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001557c`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800154e4`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18001553e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800154e4`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18001553e`

## string_xrefs

- `0x180015602`: `StartListeningThread completed!\n`

## pseudocode

```c
__int64 StartListeningThread(void)
{
  unsigned int v0; // ecx
  HLOCAL v1; // rax
  _NtpProvState *v2; // rcx
  __int64 v3; // rax
  _NtpProvState *v4; // r9
  unsigned int i; // ebx
  __int64 v6; // rax
  __int64 v7; // rdx
  signed int LastError; // eax
  signed int v10; // ebx

  if ( *((_QWORD *)g_pnpstate + 13) )
    return 2147943647LL;
  v0 = *((_DWORD *)g_pnpstate + 18) + 2;
  if ( *((_DWORD *)g_pnpstate + 18) >= 0xFFFFFFFE )
    return 2147942934LL;
  if ( !is_mul_ok(8u, v0) )
    return 2147942934LL;
  v1 = LocalAlloc(0x40u, 8LL * v0);
  v2 = g_pnpstate;
  *((_QWORD *)g_pnpstate + 13) = v1;
  if ( !v1 )
    return 2147942414LL;
  v3 = RegisterWaitForSingleObjectEx(*((_QWORD *)v2 + 11), HandleListeningThreadStopEvent, 0, 0xFFFFFFFFLL, 8);
  v4 = g_pnpstate;
  **((_QWORD **)g_pnpstate + 13) = v3;
  if ( **((_QWORD **)v4 + 13) )
  {
    for ( i = 1; i < *((_DWORD *)v4 + 18) + 1; ++i )
    {
      v6 = RegisterWaitForSingleObjectEx(
             *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 8) + 8LL * (i - 1)) + 144LL),
             HandleListeningThreadDataAvail,
             i - 1,
             0xFFFFFFFFLL,
             0);
      v4 = g_pnpstate;
      v7 = 8LL * i;
      *(_QWORD *)(v7 + *((_QWORD *)g_pnpstate + 13)) = v6;
      if ( !*(_QWORD *)(v7 + *((_QWORD *)v4 + 13)) )
        goto LABEL_11;
    }
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"StartListeningThread completed!\n");
    return 0;
  }
  else
  {
LABEL_11:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 < 0 )
      StopListeningThread();
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180015460  sub     rsp, 38h
0x180015464  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001546b  cmp     qword ptr [rax+68h], 0
0x180015470  jnz     loc_1800155F4
0x180015476  mov     ecx, [rax+48h]
0x180015479  add     ecx, 2
0x18001547c  cmp     ecx, 2
0x18001547f  jb      loc_180015571
0x180015485  mov     [rsp+38h+arg_8], rbx
0x18001548a  mov     ebx, 8
0x18001548f  mov     eax, ecx
0x180015491  mul     rbx
0x180015494  mov     [rsp+38h+var_8], rdi
0x180015499  xor     edi, edi
0x18001549b  test    rdx, rdx
0x18001549e  jnz     loc_1800155DF
0x1800154a4  mov     rdx, rax; uBytes
0x1800154a7  mov     ecx, 40h ; '@'; uFlags
0x1800154ac  call    cs:__imp_LocalAlloc
0x1800154b3  nop     dword ptr [rax+rax+00h]
0x1800154b8  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800154bf  mov     [rcx+68h], rax
0x1800154c3  test    rax, rax
0x1800154c6  jz      loc_1800155CA
0x1800154cc  mov     rcx, [rcx+58h]
0x1800154d0  lea     rdx, ?HandleListeningThreadStopEvent@@YAXPEAXE@Z; HandleListeningThreadStopEvent(void *,uchar)
0x1800154d7  mov     r9d, 0FFFFFFFFh
0x1800154dd  mov     [rsp+38h+var_18], ebx
0x1800154e1  xor     r8d, r8d
0x1800154e4  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800154eb  nop     dword ptr [rax+rax+00h]
0x1800154f0  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800154f7  mov     rcx, [r9+68h]
0x1800154fb  mov     [rcx], rax
0x1800154fe  mov     rax, [r9+68h]
0x180015502  cmp     [rax], rdi
0x180015505  jz      short loc_18001557C
0x180015507  mov     ebx, 1
0x18001550c  mov     eax, [r9+48h]
0x180015510  inc     eax
0x180015512  cmp     ebx, eax
0x180015514  jnb     loc_1800155AD
0x18001551a  mov     rax, [r9+40h]
0x18001551e  lea     r8d, [rbx-1]
0x180015522  mov     r9d, 0FFFFFFFFh
0x180015528  mov     [rsp+38h+var_18], edi
0x18001552c  lea     rdx, ?HandleListeningThreadDataAvail@@YAXPEAXE@Z; HandleListeningThreadDataAvail(void *,uchar)
0x180015533  mov     rcx, [rax+r8*8]
0x180015537  mov     rcx, [rcx+90h]
0x18001553e  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180015545  nop     dword ptr [rax+rax+00h]
0x18001554a  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180015551  mov     ecx, ebx
0x180015553  lea     rdx, ds:0[rcx*8]
0x18001555b  mov     rcx, [r9+68h]
0x18001555f  mov     [rdx+rcx], rax
0x180015563  mov     rax, [r9+68h]
0x180015567  cmp     [rdx+rax], rdi
0x18001556b  jz      short loc_18001557C
0x18001556d  inc     ebx
0x18001556f  jmp     short loc_18001550C
0x180015571  mov     eax, 80070216h
0x180015576  add     rsp, 38h
0x18001557a  retn
0x18001557c  call    cs:__imp_GetLastError
0x180015583  nop     dword ptr [rax+rax+00h]
0x180015588  mov     ebx, eax
0x18001558a  test    eax, eax
0x18001558c  jle     short loc_180015597
0x18001558e  movzx   ebx, ax
0x180015591  or      ebx, 80070000h
0x180015597  test    ebx, ebx
0x180015599  js      short loc_1800155FB
0x18001559b  mov     rdi, [rsp+38h+var_8]
0x1800155a0  mov     eax, ebx
0x1800155a2  mov     rbx, [rsp+38h+arg_8]
0x1800155a7  add     rsp, 38h
0x1800155ab  retn
0x1800155ad  xor     ecx, ecx
0x1800155af  call    FileLogAllowEntry
0x1800155b4  test    al, al
0x1800155b6  jnz     short loc_180015602
0x1800155b8  mov     rbx, [rsp+38h+arg_8]
0x1800155bd  mov     eax, edi
0x1800155bf  mov     rdi, [rsp+38h+var_8]
0x1800155c4  add     rsp, 38h
0x1800155c8  retn
0x1800155ca  mov     rbx, [rsp+38h+arg_8]
0x1800155cf  mov     eax, 8007000Eh
0x1800155d4  mov     rdi, [rsp+38h+var_8]
0x1800155d9  add     rsp, 38h
0x1800155dd  retn
0x1800155df  mov     rbx, [rsp+38h+arg_8]
0x1800155e4  mov     eax, 80070216h
0x1800155e9  mov     rdi, [rsp+38h+var_8]
0x1800155ee  add     rsp, 38h
0x1800155f2  retn
0x1800155f4  mov     eax, 800704DFh
0x1800155f9  jmp     short loc_1800155A7
0x1800155fb  call    ?StopListeningThread@@YAJXZ; StopListeningThread(void)
0x180015600  jmp     short loc_18001559B
0x180015602  lea     rcx, aStartlistening; "StartListeningThread completed!\n"
0x180015609  call    FileLogAdd
0x18001560e  jmp     short loc_1800155B8
```
