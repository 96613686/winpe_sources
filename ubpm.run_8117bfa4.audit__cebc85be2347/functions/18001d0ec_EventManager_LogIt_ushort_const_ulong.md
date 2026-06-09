# EventManager::LogIt(ushort const *,ulong)

- ea: `0x18001d0ec`
- end: `0x18001d1d2`
- name: `?LogIt@EventManager@@AEAAKPEBGK@Z`
- size: `230`
- prototype: `unsigned int __fastcall(EventManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `15`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005614`
- `0x180006e20`
- `0x18000a9ac`
- `0x18000ad48`
- `0x18001b618`
- `0x18001b98c`
- `0x18001ba8c`
- `0x18001bb54`
- `0x18001bcdc`
- `0x18001c87c`
- `0x18001cbe0`
- `0x18001da20`
- `0x180026e7c`
- `0x180032d90`
- `0x18003937c`

## callees

- `0x18001d0ec`
- `0x1800394b4`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `msvcrt!fflush` at `0x18001d191`
- `msvcrt!fflush` at `0x18001d191`
- `msvcrt!fclose` at `0x18001d1a2`
- `msvcrt!fclose` at `0x18001d1a2`
- `msvcrt!fputws` at `0x18001d180`
- `msvcrt!fputws` at `0x18001d180`
- `msvcrt!fopen_s` at `0x18001d12d`
- `msvcrt!fopen_s` at `0x18001d12d`

## string_xrefs

- `0x18001d121`: `TaskScheduler.log`

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
0x18001d0ec  mov     [rsp+arg_0], rbx
0x18001d0f1  push    rdi
0x18001d0f2  sub     rsp, 850h
0x18001d0f9  mov     rax, cs:__security_cookie
0x18001d100  xor     rax, rsp
0x18001d103  mov     [rsp+858h+var_18], rax
0x18001d10b  mov     edi, r8d
0x18001d10e  mov     [rsp+858h+Stream], 0
0x18001d117  mov     rbx, rdx
0x18001d11a  lea     r8, Mode; "a+"
0x18001d121  lea     rdx, FileName; "TaskScheduler.log"
0x18001d128  lea     rcx, [rsp+858h+Stream]; Stream
0x18001d12d  call    cs:__imp_fopen_s
0x18001d134  nop     dword ptr [rax+rax+00h]
0x18001d139  test    eax, eax
0x18001d13b  jnz     short loc_18001D1B0
0x18001d13d  xor     edx, edx; Val
0x18001d13f  lea     rcx, [rsp+858h+Buffer]; void *
0x18001d144  mov     r8d, 800h; Size
0x18001d14a  call    memset_0
0x18001d14f  mov     r9, rbx
0x18001d152  mov     [rsp+858h+var_838], edi
0x18001d156  lea     r8, aSD; "%s, (%d)\n"
0x18001d15d  mov     edx, 400h; unsigned __int64
0x18001d162  lea     rcx, [rsp+858h+Buffer]; unsigned __int16 *
0x18001d167  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d16c  mov     rdx, [rsp+858h+Stream]; Stream
0x18001d171  lea     rcx, [rsp+858h+Buffer]; Buffer
0x18001d176  xor     eax, eax
0x18001d178  mov     [rsp+858h+var_1A], ax
0x18001d180  call    cs:__imp_fputws
0x18001d187  nop     dword ptr [rax+rax+00h]
0x18001d18c  mov     rcx, [rsp+858h+Stream]; Stream
0x18001d191  call    cs:__imp_fflush
0x18001d198  nop     dword ptr [rax+rax+00h]
0x18001d19d  mov     rcx, [rsp+858h+Stream]; Stream
0x18001d1a2  call    cs:__imp_fclose
0x18001d1a9  nop     dword ptr [rax+rax+00h]
0x18001d1ae  xor     eax, eax
0x18001d1b0  mov     rcx, [rsp+858h+var_18]
0x18001d1b8  xor     rcx, rsp; StackCookie
0x18001d1bb  call    __security_check_cookie
0x18001d1c0  mov     rbx, [rsp+858h+arg_0]
0x18001d1c8  add     rsp, 850h
0x18001d1cf  pop     rdi
0x18001d1d0  retn
```
