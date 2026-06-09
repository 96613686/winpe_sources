# WdsGetCurrentDirectory

- ea: `0x18001ba60`
- end: `0x18001bb81`
- name: `WdsGetCurrentDirectory`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000179c`
- `0x18001a28c`
- `0x18001ba60`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x18001ba8d`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001bb0f`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001ba8d`
- `KERNEL32!GetCurrentDirectoryW` at `0x18001bb0f`
- `KERNEL32!GetLastError` at `0x18001ba9f`
- `KERNEL32!GetLastError` at `0x18001bb1f`
- `KERNEL32!GetLastError` at `0x18001ba9f`
- `KERNEL32!GetLastError` at `0x18001bb1f`

## pseudocode

```c
__int64 __fastcall WdsGetCurrentDirectory(WCHAR **a1)
{
  signed int v1; // ebx
  DWORD CurrentDirectoryW; // eax
  unsigned __int64 v4; // rdi
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  unsigned __int64 v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  DWORD v12; // eax
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax

  v1 = 0;
  if ( a1 )
  {
    CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
    v4 = CurrentDirectoryW;
    if ( CurrentDirectoryW )
    {
      v9 = 2LL * CurrentDirectoryW;
      if ( !is_mul_ok(v4, 2u) )
        v9 = -1;
      v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v10;
      if ( v10 )
      {
        v12 = GetCurrentDirectoryW(v4, v10);
        if ( v12 )
        {
          if ( v12 <= (unsigned int)v4 )
          {
            *a1 = v11;
            return (unsigned int)v1;
          }
          v1 = -2147024809;
        }
        else
        {
          LastError = GetLastError();
          v16 = ElValidateWin32_8(LastError, v14, v15, 2802);
          v1 = v16;
          if ( v16 > 0 )
            v1 = (unsigned __int16)v16 | 0x80070000;
          if ( v1 >= 0 )
            v1 = -2147467259;
        }
        operator delete(v11);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v5 = GetLastError();
      v8 = ElValidateWin32_8(v5, v6, v7, 2784);
      v1 = v8;
      if ( v8 > 0 )
        v1 = (unsigned __int16)v8 | 0x80070000;
      if ( v1 >= 0 )
        return (unsigned int)-2147467259;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001ba60  mov     [rsp+arg_0], rbx
0x18001ba65  mov     [rsp+arg_8], rsi
0x18001ba6a  mov     [rsp+arg_10], rdi
0x18001ba6f  push    r14
0x18001ba71  sub     rsp, 20h
0x18001ba75  xor     ebx, ebx
0x18001ba77  mov     r14, rcx
0x18001ba7a  test    rcx, rcx
0x18001ba7d  jnz     short loc_18001BA89
0x18001ba7f  mov     ebx, 80070057h
0x18001ba84  jmp     loc_18001BB68
0x18001ba89  xor     edx, edx; lpBuffer
0x18001ba8b  xor     ecx, ecx; nBufferLength
0x18001ba8d  call    cs:__imp_GetCurrentDirectoryW
0x18001ba94  nop     dword ptr [rax+rax+00h]
0x18001ba99  mov     edi, eax
0x18001ba9b  test    eax, eax
0x18001ba9d  jnz     short loc_18001BAD9
0x18001ba9f  call    cs:__imp_GetLastError
0x18001baa6  nop     dword ptr [rax+rax+00h]
0x18001baab  mov     ecx, eax
0x18001baad  mov     r9d, 0AE0h
0x18001bab3  call    ElValidateWin32_8
0x18001bab8  mov     ebx, eax
0x18001baba  test    eax, eax
0x18001babc  jle     short loc_18001BAC7
0x18001babe  movzx   ebx, ax
0x18001bac1  or      ebx, 80070000h
0x18001bac7  test    ebx, ebx
0x18001bac9  js      loc_18001BB68
0x18001bacf  mov     ebx, 80004005h
0x18001bad4  jmp     loc_18001BB68
0x18001bad9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bae0  mov     eax, 2
0x18001bae5  mul     rdi
0x18001bae8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001baef  cmovo   rax, rcx
0x18001baf3  mov     rcx, rax; unsigned __int64
0x18001baf6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bafb  mov     rsi, rax
0x18001bafe  test    rax, rax
0x18001bb01  jnz     short loc_18001BB0A
0x18001bb03  mov     ebx, 8007000Eh
0x18001bb08  jmp     short loc_18001BB68
0x18001bb0a  mov     rdx, rsi; lpBuffer
0x18001bb0d  mov     ecx, edi; nBufferLength
0x18001bb0f  call    cs:__imp_GetCurrentDirectoryW
0x18001bb16  nop     dword ptr [rax+rax+00h]
0x18001bb1b  test    eax, eax
0x18001bb1d  jnz     short loc_18001BB52
0x18001bb1f  call    cs:__imp_GetLastError
0x18001bb26  nop     dword ptr [rax+rax+00h]
0x18001bb2b  mov     ecx, eax
0x18001bb2d  mov     r9d, 0AF2h
0x18001bb33  call    ElValidateWin32_8
0x18001bb38  mov     ebx, eax
0x18001bb3a  test    eax, eax
0x18001bb3c  jle     short loc_18001BB47
0x18001bb3e  movzx   ebx, ax
0x18001bb41  or      ebx, 80070000h
0x18001bb47  test    ebx, ebx
0x18001bb49  js      short loc_18001BB5B
0x18001bb4b  mov     ebx, 80004005h
0x18001bb50  jmp     short loc_18001BB5B
0x18001bb52  cmp     eax, edi
0x18001bb54  jbe     short loc_18001BB65
0x18001bb56  mov     ebx, 80070057h
0x18001bb5b  mov     rcx, rsi; lpMem
0x18001bb5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bb63  jmp     short loc_18001BB68
0x18001bb65  mov     [r14], rsi
0x18001bb68  mov     rsi, [rsp+28h+arg_8]
0x18001bb6d  mov     eax, ebx
0x18001bb6f  mov     rbx, [rsp+28h+arg_0]
0x18001bb74  mov     rdi, [rsp+28h+arg_10]
0x18001bb79  add     rsp, 20h
0x18001bb7d  pop     r14
0x18001bb7f  retn
```
