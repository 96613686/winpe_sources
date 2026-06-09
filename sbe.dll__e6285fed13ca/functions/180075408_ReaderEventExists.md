# ReaderEventExists

- ea: `0x180075408`
- end: `0x18007549c`
- name: `ReaderEventExists`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800754a4`

## callees

- `0x180001c00`
- `0x180073b48`
- `0x180075408`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180075460`
- `KERNEL32!CloseHandle` at `0x180075460`
- `KERNEL32!GetLastError` at `0x180075468`
- `KERNEL32!GetLastError` at `0x180075468`
- `KERNEL32!OpenEventW` at `0x18007544c`
- `KERNEL32!OpenEventW` at `0x18007544c`

## pseudocode

```c
__int64 __fastcall ReaderEventExists(GUID *a1, _DWORD *a2)
{
  int ReaderIdEventName; // edi
  HANDLE v4; // rax
  WCHAR Name[264]; // [rsp+20h] [rbp-228h] BYREF

  *a2 = 1;
  ReaderIdEventName = CreateReaderIdEventName(a1);
  if ( ReaderIdEventName >= 0 )
  {
    v4 = OpenEventW(0x100000u, 0, Name);
    if ( v4 )
    {
      *a2 = 1;
      CloseHandle(v4);
    }
    else if ( GetLastError() == 2 )
    {
      *a2 = 0;
    }
  }
  return (unsigned int)ReaderIdEventName;
}

```

## disassembly

```asm
0x180075408  mov     [rsp+arg_10], rbx
0x18007540d  push    rdi
0x18007540e  sub     rsp, 240h
0x180075415  mov     rax, cs:__security_cookie
0x18007541c  xor     rax, rsp
0x18007541f  mov     [rsp+248h+var_18], rax
0x180075427  lea     r8, [rsp+248h+Name]
0x18007542c  mov     dword ptr [rdx], 1
0x180075432  mov     rbx, rdx
0x180075435  call    CreateReaderIdEventName
0x18007543a  mov     edi, eax
0x18007543c  test    eax, eax
0x18007543e  js      short loc_180075479
0x180075440  lea     r8, [rsp+248h+Name]; lpName
0x180075445  xor     edx, edx; bInheritHandle
0x180075447  mov     ecx, 100000h; dwDesiredAccess
0x18007544c  call    cs:__imp_OpenEventW
0x180075452  test    rax, rax
0x180075455  jz      short loc_180075468
0x180075457  mov     rcx, rax; hObject
0x18007545a  mov     dword ptr [rbx], 1
0x180075460  call    cs:__imp_CloseHandle
0x180075466  jmp     short loc_180075479
0x180075468  call    cs:__imp_GetLastError
0x18007546e  cmp     eax, 2
0x180075471  jnz     short loc_180075479
0x180075473  mov     dword ptr [rbx], 0
0x180075479  mov     eax, edi
0x18007547b  mov     rcx, [rsp+248h+var_18]
0x180075483  xor     rcx, rsp; StackCookie
0x180075486  call    __security_check_cookie
0x18007548b  mov     rbx, [rsp+248h+arg_10]
0x180075493  add     rsp, 240h
0x18007549a  pop     rdi
0x18007549b  retn
```
