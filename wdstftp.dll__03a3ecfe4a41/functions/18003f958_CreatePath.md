# CreatePath

- ea: `0x18003f958`
- end: `0x18003fb8d`
- name: `CreatePath`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180018c90`

## callees

- `0x18003d150`
- `0x18003dd2c`
- `0x18003f704`
- `0x18003f958`
- `0x1800401d0`
- `0x1800607d4`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18003fa52`
- `KERNEL32!CreateDirectoryW` at `0x18003facf`
- `KERNEL32!CreateDirectoryW` at `0x18003fa52`
- `KERNEL32!CreateDirectoryW` at `0x18003facf`
- `KERNEL32!HeapFree` at `0x18003fa0f`
- `KERNEL32!HeapFree` at `0x18003fb3d`
- `KERNEL32!HeapFree` at `0x18003fa0f`
- `KERNEL32!HeapFree` at `0x18003fb3d`
- `KERNEL32!GetLastError` at `0x18003fae0`
- `KERNEL32!GetLastError` at `0x18003fafc`
- `KERNEL32!GetLastError` at `0x18003fb4b`
- `KERNEL32!GetLastError` at `0x18003fae0`
- `KERNEL32!GetLastError` at `0x18003fafc`
- `KERNEL32!GetLastError` at `0x18003fb4b`
- `KERNEL32!SetLastError` at `0x18003faa1`
- `KERNEL32!SetLastError` at `0x18003fb5b`
- `KERNEL32!SetLastError` at `0x18003fb70`
- `KERNEL32!SetLastError` at `0x18003faa1`
- `KERNEL32!SetLastError` at `0x18003fb5b`
- `KERNEL32!SetLastError` at `0x18003fb70`
- `KERNEL32!GetProcessHeap` at `0x18003f9fb`
- `KERNEL32!GetProcessHeap` at `0x18003fb29`
- `KERNEL32!GetProcessHeap` at `0x18003f9fb`
- `KERNEL32!GetProcessHeap` at `0x18003fb29`

## string_xrefs

- `0x18003faec`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x18003fb08`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall CreatePath(unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // ebp
  int v4; // r12d
  wchar_t *v5; // rax
  WCHAR *v6; // rsi
  int v7; // eax
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  __int64 v10; // rdi
  DWORD v11; // eax
  const wchar_t *v12; // r8
  HANDLE ProcessHeap; // rax

  v1 = 0;
  LastError = 0;
  v4 = 1;
  if ( a1 && *a1 )
  {
    v5 = (wchar_t *)PrepareUnicodePath(a1);
    v6 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      goto LABEL_24;
    }
    v7 = ParseUncPath(v5);
    if ( v7 < 0 )
    {
      v4 = 0;
      SetLastError((unsigned __int16)v7);
      v10 = 0;
    }
    else
    {
      v10 = 0;
      if ( ((unsigned __int16)(MEMORY[0] - 97) <= 0x19u || (unsigned __int16)(MEMORY[0] - 65) <= 0x19u)
        && MEMORY[2] == 6029370 )
      {
        v10 = 8;
      }
    }
    if ( v4 == 1 )
    {
      while ( 1 )
      {
        v8 = wcschr_0((const wchar_t *)v10, 0x5Cu);
        v9 = v8;
        if ( !v8 )
          break;
        *v8 = 0;
        if ( !(unsigned int)DirectoryExists(v6) )
          CreateDirectoryW(v6, 0);
        *v9 = 92;
        v10 = (__int64)(v9 + 1);
      }
      if ( (unsigned int)DirectoryExists(v6) == 1 || CreateDirectoryW(v6, 0) )
      {
        v1 = 1;
LABEL_22:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
LABEL_24:
        SetLastError(LastError);
        return v1;
      }
      v11 = GetLastError();
      v12 = L"CreatePath: Unable to create [%s]; GLE = 0x%x";
    }
    else
    {
      v11 = GetLastError();
      v12 = L"CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x";
    }
    LastError = v11;
    LibLog(&g_WdsLibLog, 50331648, v12, a1, v11);
    goto LABEL_22;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18003f958  push    rbx
0x18003f95a  push    rbp
0x18003f95b  push    rsi
0x18003f95c  push    rdi
0x18003f95d  push    r12
0x18003f95f  push    r14
0x18003f961  push    r15
0x18003f963  sub     rsp, 30h
0x18003f967  xor     ebx, ebx
0x18003f969  mov     r14, rcx
0x18003f96c  mov     [rsp+68h+arg_8], rbx
0x18003f971  mov     ebp, ebx
0x18003f973  lea     r12d, [rbx+1]
0x18003f977  test    rcx, rcx
0x18003f97a  jz      loc_18003FB6B
0x18003f980  cmp     bx, [rcx]
0x18003f983  jz      loc_18003FB6B
0x18003f989  lea     rdx, [rsp+68h+arg_8]
0x18003f98e  call    PrepareUnicodePath
0x18003f993  mov     rsi, rax
0x18003f996  test    rax, rax
0x18003f999  jz      loc_18003FB4B
0x18003f99f  lea     r8, [rsp+68h+lpMem]
0x18003f9a7  mov     [rsp+68h+lpMem], rbx
0x18003f9af  lea     rdx, [rsp+68h+arg_0]
0x18003f9b4  mov     [rsp+68h+arg_0], ebx
0x18003f9b8  mov     rcx, rax; String1
0x18003f9bb  call    ParseUncPath
0x18003f9c0  lea     r15d, [rbx+5Ch]
0x18003f9c4  test    eax, eax
0x18003f9c6  js      loc_18003FA9B
0x18003f9cc  cmp     [rsp+68h+arg_0], r12d
0x18003f9d1  jnz     loc_18003FA68
0x18003f9d7  mov     r15, [rsp+68h+lpMem]
0x18003f9df  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003f9e3  inc     rcx
0x18003f9e6  cmp     [r15+rcx*2], bx
0x18003f9eb  jnz     short loc_18003F9E3
0x18003f9ed  mov     rax, [rsp+68h+arg_8]
0x18003f9f2  lea     rdi, [rax+rcx*2]
0x18003f9f6  test    r15, r15
0x18003f9f9  jz      short loc_18003FA1B
0x18003f9fb  call    cs:__imp_GetProcessHeap
0x18003fa02  nop     dword ptr [rax+rax+00h]
0x18003fa07  mov     r8, r15; lpMem
0x18003fa0a  xor     edx, edx; dwFlags
0x18003fa0c  mov     rcx, rax; hHeap
0x18003fa0f  call    cs:__imp_HeapFree
0x18003fa16  nop     dword ptr [rax+rax+00h]
0x18003fa1b  mov     r15d, 5Ch ; '\'
0x18003fa21  cmp     r12d, 1
0x18003fa25  jnz     loc_18003FAFC
0x18003fa2b  mov     edx, r15d; Ch
0x18003fa2e  mov     rcx, rdi; Str
0x18003fa31  call    wcschr_0
0x18003fa36  mov     rdi, rax
0x18003fa39  test    rax, rax
0x18003fa3c  jz      short loc_18003FAB7
0x18003fa3e  mov     rcx, rsi
0x18003fa41  mov     [rax], bx
0x18003fa44  call    DirectoryExists
0x18003fa49  test    eax, eax
0x18003fa4b  jnz     short loc_18003FA5E
0x18003fa4d  xor     edx, edx; lpSecurityAttributes
0x18003fa4f  mov     rcx, rsi; lpPathName
0x18003fa52  call    cs:__imp_CreateDirectoryW
0x18003fa59  nop     dword ptr [rax+rax+00h]
0x18003fa5e  mov     [rdi], r15w
0x18003fa62  add     rdi, 2
0x18003fa66  jmp     short loc_18003FA2B
0x18003fa68  mov     rdi, [rsp+68h+arg_8]
0x18003fa6d  movzx   ecx, word ptr [rdi]
0x18003fa70  lea     eax, [rcx-61h]
0x18003fa73  cmp     ax, 19h
0x18003fa77  jbe     short loc_18003FA83
0x18003fa79  sub     cx, 41h ; 'A'
0x18003fa7d  cmp     cx, 19h
0x18003fa81  ja      short loc_18003FA21
0x18003fa83  mov     eax, 3Ah ; ':'
0x18003fa88  cmp     ax, [rdi+2]
0x18003fa8c  jnz     short loc_18003FA21
0x18003fa8e  cmp     r15w, [rdi+4]
0x18003fa93  jnz     short loc_18003FA21
0x18003fa95  add     rdi, 8
0x18003fa99  jmp     short loc_18003FA21
0x18003fa9b  movzx   ecx, ax; dwErrCode
0x18003fa9e  mov     r12d, ebx
0x18003faa1  call    cs:__imp_SetLastError
0x18003faa8  nop     dword ptr [rax+rax+00h]
0x18003faad  mov     rdi, [rsp+68h+arg_8]
0x18003fab2  jmp     loc_18003FA21
0x18003fab7  cmp     r12d, 1
0x18003fabb  jnz     short loc_18003FAFC
0x18003fabd  mov     rcx, rsi
0x18003fac0  call    DirectoryExists
0x18003fac5  cmp     eax, r12d
0x18003fac8  jz      short loc_18003FAF5
0x18003faca  xor     edx, edx; lpSecurityAttributes
0x18003facc  mov     rcx, rsi; lpPathName
0x18003facf  call    cs:__imp_CreateDirectoryW
0x18003fad6  nop     dword ptr [rax+rax+00h]
0x18003fadb  cmp     eax, r12d
0x18003fade  jz      short loc_18003FAF5
0x18003fae0  call    cs:__imp_GetLastError
0x18003fae7  nop     dword ptr [rax+rax+00h]
0x18003faec  lea     r8, aCreatepathUnab; "CreatePath: Unable to create [%s]; GLE "...
0x18003faf3  jmp     short loc_18003FB0F
0x18003faf5  mov     ebx, 1
0x18003fafa  jmp     short loc_18003FB29
0x18003fafc  call    cs:__imp_GetLastError
0x18003fb03  nop     dword ptr [rax+rax+00h]
0x18003fb08  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to create parent dir"...
0x18003fb0f  mov     r9, r14
0x18003fb12  mov     [rsp+68h+var_48], eax
0x18003fb16  mov     edx, 3000000h
0x18003fb1b  lea     rcx, g_WdsLibLog
0x18003fb22  mov     ebp, eax
0x18003fb24  call    LibLog
0x18003fb29  call    cs:__imp_GetProcessHeap
0x18003fb30  nop     dword ptr [rax+rax+00h]
0x18003fb35  mov     r8, rsi; lpMem
0x18003fb38  xor     edx, edx; dwFlags
0x18003fb3a  mov     rcx, rax; hHeap
0x18003fb3d  call    cs:__imp_HeapFree
0x18003fb44  nop     dword ptr [rax+rax+00h]
0x18003fb49  jmp     short loc_18003FB59
0x18003fb4b  call    cs:__imp_GetLastError
0x18003fb52  nop     dword ptr [rax+rax+00h]
0x18003fb57  mov     ebp, eax
0x18003fb59  mov     ecx, ebp; dwErrCode
0x18003fb5b  call    cs:__imp_SetLastError
0x18003fb62  nop     dword ptr [rax+rax+00h]
0x18003fb67  mov     eax, ebx
0x18003fb69  jmp     short loc_18003FB7E
0x18003fb6b  mov     ecx, 57h ; 'W'; dwErrCode
0x18003fb70  call    cs:__imp_SetLastError
0x18003fb77  nop     dword ptr [rax+rax+00h]
0x18003fb7c  xor     eax, eax
0x18003fb7e  add     rsp, 30h
0x18003fb82  pop     r15
0x18003fb84  pop     r14
0x18003fb86  pop     r12
0x18003fb88  pop     rdi
0x18003fb89  pop     rsi
0x18003fb8a  pop     rbp
0x18003fb8b  pop     rbx
0x18003fb8c  retn
```
