# SpQueryPackageInfo(CSslUserContext *,void *)

- ea: `0x18006f7a4`
- end: `0x18006f8af`
- name: `?SpQueryPackageInfo@@YAJPEAUCSslUserContext@@PEAX@Z`
- size: `267`
- prototype: `__int64 __fastcall(struct CSslUserContext *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026d30`

## callees

- `0x180057c8c`
- `0x18005a148`
- `0x18006f7a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f818`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f818`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f7eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f7ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f7eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f7ff`

## string_xrefs

- `0x18006f7f1`: `Schannel Security Package`
- `0x18006f887`: `Schannel Security Package`

## pseudocode

```c
__int64 __fastcall SpQueryPackageInfo(struct CSslUserContext *a1, void *a2)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rsi
  _WORD *v5; // rax

  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c87a45a788bd3ab9f142d4514d1f809e_Traceguids);
  v3 = (unsigned int)(2 * lstrlenW(L"Schannel") + 2);
  v4 = (unsigned int)(2 * lstrlenW(L"Schannel Security Package") + 2);
  v5 = LocalAlloc(0x40u, v3 + v4 + 32);
  *(_QWORD *)a2 = v5;
  if ( !v5 )
    return 3221225626LL;
  v5[2] = 1;
  *(_WORD *)(*(_QWORD *)a2 + 6LL) = 14;
  **(_DWORD **)a2 = 4261811;
  *(_DWORD *)(*(_QWORD *)a2 + 8LL) = 24576;
  *(_QWORD *)(*(_QWORD *)a2 + 16LL) = *(_QWORD *)a2 + 32LL;
  *(_QWORD *)(*(_QWORD *)a2 + 24LL) = v3 + *(_QWORD *)(*(_QWORD *)a2 + 16LL);
  wcscpy_s(*(wchar_t **)(*(_QWORD *)a2 + 16LL), v3 >> 1, L"Schannel");
  wcscpy_s(*(wchar_t **)(*(_QWORD *)a2 + 24LL), v4 >> 1, L"Schannel Security Package");
  return 0;
}

```

## disassembly

```asm
0x18006f7a4  mov     [rsp+arg_0], rbx
0x18006f7a9  mov     [rsp+arg_8], rsi
0x18006f7ae  push    rdi
0x18006f7af  sub     rsp, 20h
0x18006f7b3  mov     rbx, rdx
0x18006f7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f7bd  lea     rax, WPP_GLOBAL_Control
0x18006f7c4  cmp     rcx, rax
0x18006f7c7  jz      short loc_18006F7E4
0x18006f7c9  test    byte ptr [rcx+1Ch], 4
0x18006f7cd  jz      short loc_18006F7E4
0x18006f7cf  mov     rcx, [rcx+10h]
0x18006f7d3  lea     r8, WPP_c87a45a788bd3ab9f142d4514d1f809e_Traceguids
0x18006f7da  mov     edx, 11h
0x18006f7df  call    WPP_SF_
0x18006f7e4  lea     rcx, aSchannel_0; "Schannel"
0x18006f7eb  call    cs:__imp_lstrlenW
0x18006f7f1  lea     rcx, aSchannelSecuri; "Schannel Security Package"
0x18006f7f8  lea     edi, ds:2[rax*2]
0x18006f7ff  call    cs:__imp_lstrlenW
0x18006f805  mov     ecx, 40h ; '@'; uFlags
0x18006f80a  lea     esi, ds:2[rax*2]
0x18006f811  lea     rdx, [rsi+20h]
0x18006f815  add     rdx, rdi; uBytes
0x18006f818  call    cs:__imp_LocalAlloc
0x18006f81e  mov     [rbx], rax
0x18006f821  test    rax, rax
0x18006f824  jnz     short loc_18006F82D
0x18006f826  mov     eax, 0C000009Ah
0x18006f82b  jmp     short loc_18006F89F
0x18006f82d  mov     ecx, 1
0x18006f832  lea     r8, aSchannel_0; "Schannel"
0x18006f839  mov     [rax+4], cx
0x18006f83d  mov     rax, [rbx]
0x18006f840  mov     word ptr [rax+6], 0Eh
0x18006f846  mov     rax, [rbx]
0x18006f849  mov     dword ptr [rax], 4107B3h
0x18006f84f  mov     rax, [rbx]
0x18006f852  mov     dword ptr [rax+8], 6000h
0x18006f859  mov     rcx, [rbx]
0x18006f85c  lea     rax, [rcx+20h]
0x18006f860  mov     [rcx+10h], rax
0x18006f864  mov     r9, [rbx]
0x18006f867  mov     rcx, [r9+10h]
0x18006f86b  add     rcx, rdi
0x18006f86e  shr     rdi, 1
0x18006f871  mov     [r9+18h], rcx
0x18006f875  mov     rdx, rdi; SizeInWords
0x18006f878  mov     rcx, [rbx]
0x18006f87b  mov     rcx, [rcx+10h]; Destination
0x18006f87f  call    wcscpy_s
0x18006f884  mov     rcx, [rbx]
0x18006f887  lea     r8, aSchannelSecuri; "Schannel Security Package"
0x18006f88e  shr     rsi, 1
0x18006f891  mov     rdx, rsi; SizeInWords
0x18006f894  mov     rcx, [rcx+18h]; Destination
0x18006f898  call    wcscpy_s
0x18006f89d  xor     eax, eax
0x18006f89f  mov     rbx, [rsp+28h+arg_0]
0x18006f8a4  mov     rsi, [rsp+28h+arg_8]
0x18006f8a9  add     rsp, 20h
0x18006f8ad  pop     rdi
0x18006f8ae  retn
```
