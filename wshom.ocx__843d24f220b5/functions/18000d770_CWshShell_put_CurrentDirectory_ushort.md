# CWshShell::put_CurrentDirectory(ushort *)

- ea: `0x18000d770`
- end: `0x18000d845`
- name: `?put_CurrentDirectory@CWshShell@@UEAAJPEAG@Z`
- size: `213`
- prototype: `int(CWshShell *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800059f8`
- `0x180006124`
- `0x18000d770`
- `0x180010250`

## import_xrefs

- `KERNEL32!SetCurrentDirectoryW` at `0x18000d7ae`
- `KERNEL32!SetCurrentDirectoryW` at `0x18000d7ae`
- `KERNEL32!SetCurrentDirectoryA` at `0x18000d7fc`
- `KERNEL32!SetCurrentDirectoryA` at `0x18000d7fc`
- `KERNEL32!GetLastError` at `0x18000d7b8`
- `KERNEL32!GetLastError` at `0x18000d806`
- `KERNEL32!GetLastError` at `0x18000d7b8`
- `KERNEL32!GetLastError` at `0x18000d806`

## pseudocode

```c
__int64 __fastcall CWshShell::put_CurrentDirectory(CWshShell *this, unsigned __int16 *a2)
{
  signed int v2; // ebx
  signed int LastError; // eax
  signed int v4; // eax
  LPCSTR lpPathName; // [rsp+30h] [rbp-228h] BYREF
  void *Block; // [rsp+38h] [rbp-220h] BYREF
  char v8[512]; // [rsp+40h] [rbp-218h] BYREF

  lpPathName = 0;
  Block = 0;
  if ( Global::g_fWindowsNT )
  {
    v2 = 0;
    if ( !SetCurrentDirectoryW(a2) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v2 = PWSZToPSZ(a2, v8, 512, (char **)&Block, (char **)&lpPathName);
    if ( v2 >= 0 && !SetCurrentDirectoryA(lpPathName) )
    {
      v4 = GetLastError();
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
    }
    if ( Block )
      operator delete(Block);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d770  push    rbx
0x18000d772  sub     rsp, 250h
0x18000d779  mov     rax, cs:__security_cookie
0x18000d780  xor     rax, rsp
0x18000d783  mov     [rsp+258h+var_18], rax
0x18000d78b  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000d792  mov     rax, rdx
0x18000d795  mov     [rsp+258h+lpPathName], 0
0x18000d79e  mov     [rsp+258h+Block], 0
0x18000d7a7  jz      short loc_18000D7CF
0x18000d7a9  mov     rcx, rdx; lpPathName
0x18000d7ac  xor     ebx, ebx
0x18000d7ae  call    cs:__imp_SetCurrentDirectoryW
0x18000d7b4  test    eax, eax
0x18000d7b6  jnz     short loc_18000D82A
0x18000d7b8  call    cs:__imp_GetLastError
0x18000d7be  mov     ebx, eax
0x18000d7c0  test    eax, eax
0x18000d7c2  jle     short loc_18000D82A
0x18000d7c4  movzx   ebx, ax
0x18000d7c7  or      ebx, 80070000h
0x18000d7cd  jmp     short loc_18000D82A
0x18000d7cf  lea     rcx, [rsp+258h+lpPathName]
0x18000d7d4  mov     r8d, 200h; int
0x18000d7da  mov     [rsp+258h+var_238], rcx; char **
0x18000d7df  lea     r9, [rsp+258h+Block]; char **
0x18000d7e4  mov     rcx, rax; lpWideCharStr
0x18000d7e7  lea     rdx, [rsp+258h+var_218]; char *
0x18000d7ec  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x18000d7f1  mov     ebx, eax
0x18000d7f3  test    eax, eax
0x18000d7f5  js      short loc_18000D81B
0x18000d7f7  mov     rcx, [rsp+258h+lpPathName]; lpPathName
0x18000d7fc  call    cs:__imp_SetCurrentDirectoryA
0x18000d802  test    eax, eax
0x18000d804  jnz     short loc_18000D81B
0x18000d806  call    cs:__imp_GetLastError
0x18000d80c  mov     ebx, eax
0x18000d80e  test    eax, eax
0x18000d810  jle     short loc_18000D81B
0x18000d812  movzx   ebx, ax
0x18000d815  or      ebx, 80070000h
0x18000d81b  mov     rcx, [rsp+258h+Block]; Block
0x18000d820  test    rcx, rcx
0x18000d823  jz      short loc_18000D82A
0x18000d825  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d82a  mov     eax, ebx
0x18000d82c  mov     rcx, [rsp+258h+var_18]
0x18000d834  xor     rcx, rsp; StackCookie
0x18000d837  call    __security_check_cookie
0x18000d83c  add     rsp, 250h
0x18000d843  pop     rbx
0x18000d844  retn
```
