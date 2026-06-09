# EventManager::LogIt(ushort const *,ulong)

- ea: `0x18004ff54`
- end: `0x180050021`
- name: `?LogIt@EventManager@@AEAAKPEBGK@Z`
- size: `205`
- prototype: `unsigned int __fastcall(EventManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18003e8f8`
- `0x18004510c`
- `0x18004f008`
- `0x18004f0dc`
- `0x18004f190`
- `0x18004f90c`
- `0x18004fccc`
- `0x18004fdcc`
- `0x18004fea8`

## callees

- `0x180015740`
- `0x18004ff54`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!fflush` at `0x18004ffed`
- `msvcrt!fflush` at `0x18004ffed`
- `msvcrt!fclose` at `0x18004fff8`
- `msvcrt!fclose` at `0x18004fff8`
- `msvcrt!fputws` at `0x18004ffe2`
- `msvcrt!fputws` at `0x18004ffe2`
- `msvcrt!fopen_s` at `0x18004ff95`
- `msvcrt!fopen_s` at `0x18004ff95`

## string_xrefs

- `0x18004ff89`: `TaskScheduler.log`

## pseudocode

```c
errno_t __fastcall EventManager::LogIt(EventManager *this, const unsigned __int16 *a2, int a3)
{
  errno_t result; // eax
  int v6; // [rsp+20h] [rbp-838h]
  FILE *Stream; // [rsp+30h] [rbp-828h] BYREF
  wchar_t Buffer[1024]; // [rsp+40h] [rbp-818h] BYREF

  Stream = 0;
  result = fopen_s(&Stream, "TaskScheduler.log", "a+");
  if ( !result )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    v6 = a3;
    StringCchPrintfW(Buffer, 0x400u, L"%s, (%d)\n", a2, v6);
    Buffer[1023] = 0;
    fputws(Buffer, Stream);
    fflush(Stream);
    fclose(Stream);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004ff54  mov     [rsp+arg_0], rbx
0x18004ff59  push    rdi
0x18004ff5a  sub     rsp, 850h
0x18004ff61  mov     rax, cs:__security_cookie
0x18004ff68  xor     rax, rsp
0x18004ff6b  mov     [rsp+858h+var_18], rax
0x18004ff73  mov     edi, r8d
0x18004ff76  mov     [rsp+858h+Stream], 0
0x18004ff7f  mov     rbx, rdx
0x18004ff82  lea     r8, Mode; "a+"
0x18004ff89  lea     rdx, FileName; "TaskScheduler.log"
0x18004ff90  lea     rcx, [rsp+858h+Stream]; Stream
0x18004ff95  call    cs:__imp_fopen_s
0x18004ff9b  test    eax, eax
0x18004ff9d  jnz     short loc_180050000
0x18004ff9f  xor     edx, edx; Val
0x18004ffa1  lea     rcx, [rsp+858h+Buffer]; void *
0x18004ffa6  mov     r8d, 800h; Size
0x18004ffac  call    memset_0
0x18004ffb1  mov     r9, rbx
0x18004ffb4  mov     [rsp+858h+var_838], edi
0x18004ffb8  lea     r8, aSD; "%s, (%d)\n"
0x18004ffbf  mov     edx, 400h; unsigned __int64
0x18004ffc4  lea     rcx, [rsp+858h+Buffer]; unsigned __int16 *
0x18004ffc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ffce  mov     rdx, [rsp+858h+Stream]; Stream
0x18004ffd3  lea     rcx, [rsp+858h+Buffer]; Buffer
0x18004ffd8  xor     eax, eax
0x18004ffda  mov     [rsp+858h+var_1A], ax
0x18004ffe2  call    cs:__imp_fputws
0x18004ffe8  mov     rcx, [rsp+858h+Stream]; Stream
0x18004ffed  call    cs:__imp_fflush
0x18004fff3  mov     rcx, [rsp+858h+Stream]; Stream
0x18004fff8  call    cs:__imp_fclose
0x18004fffe  xor     eax, eax
0x180050000  mov     rcx, [rsp+858h+var_18]
0x180050008  xor     rcx, rsp; StackCookie
0x18005000b  call    __security_check_cookie
0x180050010  mov     rbx, [rsp+858h+arg_0]
0x180050018  add     rsp, 850h
0x18005001f  pop     rdi
0x180050020  retn
```
