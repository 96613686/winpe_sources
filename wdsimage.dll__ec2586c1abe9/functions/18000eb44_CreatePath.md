# CreatePath

- ea: `0x18000eb44`
- end: `0x18000eca2`
- name: `CreatePath`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c148`

## callees

- `0x1800015e3`
- `0x18000e9e4`
- `0x18000eac0`
- `0x18000eb44`
- `0x18000efbc`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18000ebc9`
- `KERNEL32!CreateDirectoryW` at `0x18000ebee`
- `KERNEL32!CreateDirectoryW` at `0x18000ebc9`
- `KERNEL32!CreateDirectoryW` at `0x18000ebee`
- `KERNEL32!GetProcessHeap` at `0x18000ec33`
- `KERNEL32!GetProcessHeap` at `0x18000ec33`
- `KERNEL32!HeapFree` at `0x18000ec47`
- `KERNEL32!HeapFree` at `0x18000ec47`
- `KERNEL32!GetLastError` at `0x18000ebff`
- `KERNEL32!GetLastError` at `0x18000ec55`
- `KERNEL32!GetLastError` at `0x18000ebff`
- `KERNEL32!GetLastError` at `0x18000ec55`
- `KERNEL32!SetLastError` at `0x18000ec65`
- `KERNEL32!SetLastError` at `0x18000ec7a`
- `KERNEL32!SetLastError` at `0x18000ec65`
- `KERNEL32!SetLastError` at `0x18000ec7a`

## string_xrefs

- `0x18000ec0e`: `CreatePath: Unable to create [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall CreatePath(_WORD *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // ebp
  WCHAR *v4; // rdi
  const wchar_t *v5; // rcx
  wchar_t *v6; // rax
  wchar_t *v7; // r14
  HANDLE ProcessHeap; // rax
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  v10 = 0;
  LastError = 0;
  if ( a1 && *a1 )
  {
    v4 = (WCHAR *)PrepareUnicodePathEx(a1, &v10);
    if ( v4 )
    {
      v5 = (const wchar_t *)(v10 + 2);
      if ( !v10 )
        v5 = v4;
      while ( 1 )
      {
        v6 = wcschr_0(v5, 0x5Cu);
        v7 = v6;
        if ( !v6 )
          break;
        *v6 = 0;
        if ( !(unsigned int)DirectoryExists(v4) )
          CreateDirectoryW(v4, 0);
        *v7 = 92;
        v5 = v7 + 1;
      }
      if ( (unsigned int)DirectoryExists(v4) == 1 || CreateDirectoryW(v4, 0) )
      {
        v1 = 1;
      }
      else
      {
        LastError = GetLastError();
        LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Unable to create [%s]; GLE = 0x%x", a1, LastError);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    else
    {
      LastError = GetLastError();
    }
    SetLastError(LastError);
    return v1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000eb44  mov     rax, rsp
0x18000eb47  mov     [rax+10h], rbx
0x18000eb4b  mov     [rax+18h], rbp
0x18000eb4f  mov     [rax+20h], rsi
0x18000eb53  push    rdi
0x18000eb54  push    r14
0x18000eb56  push    r15
0x18000eb58  sub     rsp, 30h
0x18000eb5c  xor     ebx, ebx
0x18000eb5e  mov     rsi, rcx
0x18000eb61  mov     [rax+8], rbx
0x18000eb65  mov     ebp, ebx
0x18000eb67  test    rcx, rcx
0x18000eb6a  jz      loc_18000EC75
0x18000eb70  cmp     bx, [rcx]
0x18000eb73  jz      loc_18000EC75
0x18000eb79  lea     rdx, [rax+8]
0x18000eb7d  call    PrepareUnicodePathEx
0x18000eb82  mov     rdi, rax
0x18000eb85  test    rax, rax
0x18000eb88  jz      loc_18000EC55
0x18000eb8e  mov     rax, [rsp+48h+arg_0]
0x18000eb93  lea     rcx, [rax+2]
0x18000eb97  test    rax, rax
0x18000eb9a  jnz     short loc_18000EB9F
0x18000eb9c  mov     rcx, rdi; Str
0x18000eb9f  mov     r15d, 5Ch ; '\'
0x18000eba5  mov     edx, r15d; Ch
0x18000eba8  call    wcschr_0
0x18000ebad  mov     r14, rax
0x18000ebb0  mov     rcx, rdi
0x18000ebb3  test    rax, rax
0x18000ebb6  jz      short loc_18000EBDF
0x18000ebb8  mov     [rax], bx
0x18000ebbb  call    DirectoryExists
0x18000ebc0  test    eax, eax
0x18000ebc2  jnz     short loc_18000EBD5
0x18000ebc4  xor     edx, edx; lpSecurityAttributes
0x18000ebc6  mov     rcx, rdi; lpPathName
0x18000ebc9  call    cs:__imp_CreateDirectoryW
0x18000ebd0  nop     dword ptr [rax+rax+00h]
0x18000ebd5  mov     [r14], r15w
0x18000ebd9  lea     rcx, [r14+2]
0x18000ebdd  jmp     short loc_18000EBA5
0x18000ebdf  call    DirectoryExists
0x18000ebe4  cmp     eax, 1
0x18000ebe7  jz      short loc_18000EC2E
0x18000ebe9  xor     edx, edx; lpSecurityAttributes
0x18000ebeb  mov     rcx, rdi; lpPathName
0x18000ebee  call    cs:__imp_CreateDirectoryW
0x18000ebf5  nop     dword ptr [rax+rax+00h]
0x18000ebfa  cmp     eax, 1
0x18000ebfd  jz      short loc_18000EC2E
0x18000ebff  call    cs:__imp_GetLastError
0x18000ec06  nop     dword ptr [rax+rax+00h]
0x18000ec0b  mov     r9, rsi
0x18000ec0e  lea     r8, aCreatepathUnab; "CreatePath: Unable to create [%s]; GLE "...
0x18000ec15  lea     rcx, g_WdsLibLog
0x18000ec1c  mov     [rsp+48h+var_28], eax
0x18000ec20  mov     edx, 3000000h
0x18000ec25  mov     ebp, eax
0x18000ec27  call    LibLog
0x18000ec2c  jmp     short loc_18000EC33
0x18000ec2e  mov     ebx, 1
0x18000ec33  call    cs:__imp_GetProcessHeap
0x18000ec3a  nop     dword ptr [rax+rax+00h]
0x18000ec3f  mov     r8, rdi; lpMem
0x18000ec42  xor     edx, edx; dwFlags
0x18000ec44  mov     rcx, rax; hHeap
0x18000ec47  call    cs:__imp_HeapFree
0x18000ec4e  nop     dword ptr [rax+rax+00h]
0x18000ec53  jmp     short loc_18000EC63
0x18000ec55  call    cs:__imp_GetLastError
0x18000ec5c  nop     dword ptr [rax+rax+00h]
0x18000ec61  mov     ebp, eax
0x18000ec63  mov     ecx, ebp; dwErrCode
0x18000ec65  call    cs:__imp_SetLastError
0x18000ec6c  nop     dword ptr [rax+rax+00h]
0x18000ec71  mov     eax, ebx
0x18000ec73  jmp     short loc_18000EC88
0x18000ec75  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ec7a  call    cs:__imp_SetLastError
0x18000ec81  nop     dword ptr [rax+rax+00h]
0x18000ec86  xor     eax, eax
0x18000ec88  mov     rbx, [rsp+48h+arg_8]
0x18000ec8d  mov     rbp, [rsp+48h+arg_10]
0x18000ec92  mov     rsi, [rsp+48h+arg_18]
0x18000ec97  add     rsp, 30h
0x18000ec9b  pop     r15
0x18000ec9d  pop     r14
0x18000ec9f  pop     rdi
0x18000eca0  retn
```
