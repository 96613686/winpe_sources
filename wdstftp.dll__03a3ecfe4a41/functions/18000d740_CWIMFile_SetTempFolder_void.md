# CWIMFile::SetTempFolder(void)

- ea: `0x18000d740`
- end: `0x18000d844`
- name: `?SetTempFolder@CWIMFile@@AEAAKXZ`
- size: `260`
- prototype: `unsigned int __fastcall(CWIMFile *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c9c4`

## callees

- `0x18000a960`
- `0x18000d740`
- `0x18000e2e4`
- `0x18003ce78`
- `0x180060808`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d770`
- `KERNEL32!GetLastError` at `0x18000d7df`
- `KERNEL32!GetLastError` at `0x18000d802`
- `KERNEL32!GetLastError` at `0x18000d770`
- `KERNEL32!GetLastError` at `0x18000d7df`
- `KERNEL32!GetLastError` at `0x18000d802`
- `KERNEL32!GetTempPathW` at `0x18000d75e`
- `KERNEL32!GetTempPathW` at `0x18000d7cf`
- `KERNEL32!GetTempPathW` at `0x18000d75e`
- `KERNEL32!GetTempPathW` at `0x18000d7cf`

## pseudocode

```c
__int64 __fastcall CWIMFile::SetTempFolder(CWIMFile *this)
{
  unsigned int v2; // ebx
  DWORD TempPathW; // edi
  DWORD v4; // eax
  const char *v5; // rdx
  DWORD v6; // edi
  unsigned __int64 v7; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rsi
  DWORD LastError; // eax
  const char *v11; // rdx
  unsigned int v12; // r9d

  v2 = 0;
  TempPathW = GetTempPathW(0, 0);
  if ( TempPathW )
  {
    v6 = TempPathW + 1;
    v7 = 2LL * v6;
    if ( !is_mul_ok(v6, 2u) )
      v7 = -1;
    v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
      return 8;
    if ( GetTempPathW(v6, v8) )
    {
      if ( (unsigned int)WIMSetTemporaryPath(*(_QWORD *)this, v9) )
      {
LABEL_12:
        operator delete(v9);
        return v2;
      }
      LastError = GetLastError();
      v12 = 203;
    }
    else
    {
      LastError = GetLastError();
      v12 = 197;
    }
    v2 = ElValidateWin32(LastError, v11, "base\\eco\\wds\\wdslib\\wim\\wdswimfile.cpp", v12);
    goto LABEL_12;
  }
  v4 = GetLastError();
  return ElValidateWin32(v4, v5, "base\\eco\\wds\\wdslib\\wim\\wdswimfile.cpp", 0xB7u);
}

```

## disassembly

```asm
0x18000d740  mov     [rsp+arg_0], rbx
0x18000d745  mov     [rsp+arg_8], rsi
0x18000d74a  mov     [rsp+arg_10], rdi
0x18000d74f  push    r14
0x18000d751  sub     rsp, 20h
0x18000d755  mov     r14, rcx
0x18000d758  xor     edx, edx; lpBuffer
0x18000d75a  xor     ecx, ecx; nBufferLength
0x18000d75c  xor     ebx, ebx
0x18000d75e  call    cs:__imp_GetTempPathW
0x18000d765  nop     dword ptr [rax+rax+00h]
0x18000d76a  mov     edi, eax
0x18000d76c  test    eax, eax
0x18000d76e  jnz     short loc_18000D797
0x18000d770  call    cs:__imp_GetLastError
0x18000d777  nop     dword ptr [rax+rax+00h]
0x18000d77c  mov     r9d, 0B7h; unsigned int
0x18000d782  lea     r8, aBaseEcoWdsWdsl_0; "base\\eco\\wds\\wdslib\\wim\\wdswimfile"...
0x18000d789  mov     ecx, eax; unsigned int
0x18000d78b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d790  mov     ebx, eax
0x18000d792  jmp     loc_18000D82C
0x18000d797  inc     edi
0x18000d799  mov     eax, 2
0x18000d79e  mov     ecx, edi
0x18000d7a0  mul     rcx
0x18000d7a3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d7aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d7b1  cmovo   rax, rcx
0x18000d7b5  mov     rcx, rax; unsigned __int64
0x18000d7b8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d7bd  mov     rsi, rax
0x18000d7c0  test    rax, rax
0x18000d7c3  jnz     short loc_18000D7CA
0x18000d7c5  lea     ebx, [rax+8]
0x18000d7c8  jmp     short loc_18000D82C
0x18000d7ca  mov     rdx, rsi; lpBuffer
0x18000d7cd  mov     ecx, edi; nBufferLength
0x18000d7cf  call    cs:__imp_GetTempPathW
0x18000d7d6  nop     dword ptr [rax+rax+00h]
0x18000d7db  test    eax, eax
0x18000d7dd  jnz     short loc_18000D7F3
0x18000d7df  call    cs:__imp_GetLastError
0x18000d7e6  nop     dword ptr [rax+rax+00h]
0x18000d7eb  mov     r9d, 0C5h
0x18000d7f1  jmp     short loc_18000D814
0x18000d7f3  mov     rcx, [r14]
0x18000d7f6  mov     rdx, rsi
0x18000d7f9  call    WIMSetTemporaryPath
0x18000d7fe  test    eax, eax
0x18000d800  jnz     short loc_18000D824
0x18000d802  call    cs:__imp_GetLastError
0x18000d809  nop     dword ptr [rax+rax+00h]
0x18000d80e  mov     r9d, 0CBh; unsigned int
0x18000d814  lea     r8, aBaseEcoWdsWdsl_0; "base\\eco\\wds\\wdslib\\wim\\wdswimfile"...
0x18000d81b  mov     ecx, eax; unsigned int
0x18000d81d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d822  mov     ebx, eax
0x18000d824  mov     rcx, rsi; void *
0x18000d827  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d82c  mov     rsi, [rsp+28h+arg_8]
0x18000d831  mov     eax, ebx
0x18000d833  mov     rbx, [rsp+28h+arg_0]
0x18000d838  mov     rdi, [rsp+28h+arg_10]
0x18000d83d  add     rsp, 20h
0x18000d841  pop     r14
0x18000d843  retn
```
