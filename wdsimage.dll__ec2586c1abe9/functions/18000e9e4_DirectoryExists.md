# DirectoryExists

- ea: `0x18000e9e4`
- end: `0x18000eab8`
- name: `DirectoryExists`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800071b0`
- `0x18000eb44`

## callees

- `0x18000e9e4`
- `0x18000efbc`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18000ea20`
- `KERNEL32!GetFileAttributesW` at `0x18000ea20`
- `KERNEL32!GetProcessHeap` at `0x18000ea5d`
- `KERNEL32!GetProcessHeap` at `0x18000ea5d`
- `KERNEL32!HeapFree` at `0x18000ea71`
- `KERNEL32!HeapFree` at `0x18000ea71`
- `KERNEL32!GetLastError` at `0x18000ea3c`
- `KERNEL32!GetLastError` at `0x18000ea3c`
- `KERNEL32!SetLastError` at `0x18000ea7f`
- `KERNEL32!SetLastError` at `0x18000ea94`
- `KERNEL32!SetLastError` at `0x18000ea7f`
- `KERNEL32!SetLastError` at `0x18000ea94`

## pseudocode

```c
__int64 __fastcall DirectoryExists(const wchar_t *a1)
{
  unsigned int v1; // ebx
  char *v2; // rax
  char *v3; // rbp
  DWORD v4; // edi
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  HANDLE ProcessHeap; // rax

  v1 = 0;
  if ( a1 && *a1 )
  {
    v2 = PrepareUnicodePathEx(a1, 0);
    v3 = v2;
    if ( v2 )
    {
      v4 = 0;
      FileAttributesW = GetFileAttributesW((LPCWSTR)v2);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError )
        {
          if ( LastError == 2 )
            v4 = 3;
        }
        else
        {
          v4 = 267;
        }
      }
      else
      {
        v1 = 1;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      SetLastError(v4);
    }
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
0x18000e9e4  mov     [rsp+arg_0], rbx
0x18000e9e9  mov     [rsp+arg_8], rbp
0x18000e9ee  mov     [rsp+arg_10], rsi
0x18000e9f3  push    rdi
0x18000e9f4  sub     rsp, 20h
0x18000e9f8  xor     ebx, ebx
0x18000e9fa  test    rcx, rcx
0x18000e9fd  jz      loc_18000EA8F
0x18000ea03  cmp     bx, [rcx]
0x18000ea06  jz      loc_18000EA8F
0x18000ea0c  xor     edx, edx
0x18000ea0e  call    PrepareUnicodePathEx
0x18000ea13  mov     rbp, rax
0x18000ea16  test    rax, rax
0x18000ea19  jz      short loc_18000EA8B
0x18000ea1b  mov     rcx, rax; lpFileName
0x18000ea1e  mov     edi, ebx
0x18000ea20  call    cs:__imp_GetFileAttributesW
0x18000ea27  nop     dword ptr [rax+rax+00h]
0x18000ea2c  cmp     eax, 0FFFFFFFFh
0x18000ea2f  jz      short loc_18000EA3C
0x18000ea31  test    al, 10h
0x18000ea33  jz      short loc_18000EA3C
0x18000ea35  mov     ebx, 1
0x18000ea3a  jmp     short loc_18000EA5D
0x18000ea3c  call    cs:__imp_GetLastError
0x18000ea43  nop     dword ptr [rax+rax+00h]
0x18000ea48  mov     edi, eax
0x18000ea4a  test    eax, eax
0x18000ea4c  jnz     short loc_18000EA55
0x18000ea4e  mov     edi, 10Bh
0x18000ea53  jmp     short loc_18000EA5D
0x18000ea55  cmp     eax, 2
0x18000ea58  jnz     short loc_18000EA5D
0x18000ea5a  lea     edi, [rax+1]
0x18000ea5d  call    cs:__imp_GetProcessHeap
0x18000ea64  nop     dword ptr [rax+rax+00h]
0x18000ea69  mov     r8, rbp; lpMem
0x18000ea6c  xor     edx, edx; dwFlags
0x18000ea6e  mov     rcx, rax; hHeap
0x18000ea71  call    cs:__imp_HeapFree
0x18000ea78  nop     dword ptr [rax+rax+00h]
0x18000ea7d  mov     ecx, edi; dwErrCode
0x18000ea7f  call    cs:__imp_SetLastError
0x18000ea86  nop     dword ptr [rax+rax+00h]
0x18000ea8b  mov     eax, ebx
0x18000ea8d  jmp     short loc_18000EAA2
0x18000ea8f  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ea94  call    cs:__imp_SetLastError
0x18000ea9b  nop     dword ptr [rax+rax+00h]
0x18000eaa0  xor     eax, eax
0x18000eaa2  mov     rbx, [rsp+28h+arg_0]
0x18000eaa7  mov     rbp, [rsp+28h+arg_8]
0x18000eaac  mov     rsi, [rsp+28h+arg_10]
0x18000eab1  add     rsp, 20h
0x18000eab5  pop     rdi
0x18000eab6  retn
```
