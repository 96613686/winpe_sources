# CWshShell::get_CurrentDirectory(ushort * *)

- ea: `0x18000d6a0`
- end: `0x18000d762`
- name: `?get_CurrentDirectory@CWshShell@@UEAAJPEAPEAG@Z`
- size: `194`
- prototype: `int(CWshShell *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800060e4`
- `0x180006124`
- `0x180009b40`
- `0x18000d6a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000d6fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d6fa`
- `KERNEL32!GetCurrentDirectoryW` at `0x18000d6ba`
- `KERNEL32!GetCurrentDirectoryW` at `0x18000d6ed`
- `KERNEL32!GetCurrentDirectoryW` at `0x18000d6ba`
- `KERNEL32!GetCurrentDirectoryW` at `0x18000d6ed`
- `KERNEL32!GetCurrentDirectoryA` at `0x18000d705`
- `KERNEL32!GetCurrentDirectoryA` at `0x18000d723`
- `KERNEL32!GetCurrentDirectoryA` at `0x18000d705`
- `KERNEL32!GetCurrentDirectoryA` at `0x18000d723`
- `KERNEL32!GetLastError` at `0x18000d72d`
- `KERNEL32!GetLastError` at `0x18000d72d`

## pseudocode

```c
__int64 __fastcall CWshShell::get_CurrentDirectory(CWshShell *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  signed int CurrentDirectoryW; // ebp
  WCHAR *v5; // rax
  CHAR *v6; // rdi
  signed int CurrentDirectoryA; // ebp
  CHAR *v8; // rax
  signed int LastError; // eax

  v3 = 0;
  if ( !Global::g_fWindowsNT )
  {
    CurrentDirectoryA = GetCurrentDirectoryA(0, 0);
    v8 = (CHAR *)operator new(CurrentDirectoryA);
    v6 = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    if ( GetCurrentDirectoryA(CurrentDirectoryA, v8) )
    {
      PSZToBSTR(v6, a2);
      goto LABEL_11;
    }
LABEL_8:
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_11;
  }
  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  v5 = (WCHAR *)operator new(saturated_mul(CurrentDirectoryW, 2u));
  v6 = (CHAR *)v5;
  if ( v5 )
  {
    if ( GetCurrentDirectoryW(CurrentDirectoryW, v5) )
    {
      *a2 = SysAllocString((const OLECHAR *)v6);
LABEL_11:
      operator delete(v6);
      return v3;
    }
    goto LABEL_8;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18000d6a0  push    rbx
0x18000d6a2  push    rbp
0x18000d6a3  push    rsi
0x18000d6a4  push    rdi
0x18000d6a5  sub     rsp, 28h
0x18000d6a9  mov     rsi, rdx
0x18000d6ac  xor     ebx, ebx
0x18000d6ae  xor     edx, edx; lpBuffer
0x18000d6b0  xor     ecx, ecx; nBufferLength
0x18000d6b2  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x18000d6b8  jz      short loc_18000D705
0x18000d6ba  call    cs:__imp_GetCurrentDirectoryW
0x18000d6c0  movsxd  rbp, eax
0x18000d6c3  lea     rcx, [rbx-1]
0x18000d6c7  lea     eax, [rbx+2]
0x18000d6ca  mul     rbp
0x18000d6cd  cmovb   rax, rcx
0x18000d6d1  mov     rcx, rax; Size
0x18000d6d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d6d9  mov     rdi, rax
0x18000d6dc  test    rax, rax
0x18000d6df  jnz     short loc_18000D6E8
0x18000d6e1  mov     ebx, 8007000Eh
0x18000d6e6  jmp     short loc_18000D757
0x18000d6e8  mov     rdx, rdi; lpBuffer
0x18000d6eb  mov     ecx, ebp; nBufferLength
0x18000d6ed  call    cs:__imp_GetCurrentDirectoryW
0x18000d6f3  test    eax, eax
0x18000d6f5  jz      short loc_18000D72D
0x18000d6f7  mov     rcx, rdi; psz
0x18000d6fa  call    cs:__imp_SysAllocString
0x18000d700  mov     [rsi], rax
0x18000d703  jmp     short loc_18000D74F
0x18000d705  call    cs:__imp_GetCurrentDirectoryA
0x18000d70b  movsxd  rbp, eax
0x18000d70e  mov     rcx, rbp; Size
0x18000d711  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d716  mov     rdi, rax
0x18000d719  test    rax, rax
0x18000d71c  jz      short loc_18000D6E1
0x18000d71e  mov     rdx, rax; lpBuffer
0x18000d721  mov     ecx, ebp; nBufferLength
0x18000d723  call    cs:__imp_GetCurrentDirectoryA
0x18000d729  test    eax, eax
0x18000d72b  jnz     short loc_18000D744
0x18000d72d  call    cs:__imp_GetLastError
0x18000d733  mov     ebx, eax
0x18000d735  test    eax, eax
0x18000d737  jle     short loc_18000D74F
0x18000d739  movzx   ebx, ax
0x18000d73c  or      ebx, 80070000h
0x18000d742  jmp     short loc_18000D74F
0x18000d744  mov     rdx, rsi; unsigned __int16 **
0x18000d747  mov     rcx, rdi; lpMultiByteStr
0x18000d74a  call    ?PSZToBSTR@@YAJPEBDPEAPEAG@Z; PSZToBSTR(char const *,ushort * *)
0x18000d74f  mov     rcx, rdi; Block
0x18000d752  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d757  mov     eax, ebx
0x18000d759  add     rsp, 28h
0x18000d75d  pop     rdi
0x18000d75e  pop     rsi
0x18000d75f  pop     rbp
0x18000d760  pop     rbx
0x18000d761  retn
```
