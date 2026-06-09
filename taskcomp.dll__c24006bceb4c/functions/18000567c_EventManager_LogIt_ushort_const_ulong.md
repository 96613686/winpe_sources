# EventManager::LogIt(ushort const *,ulong)

- ea: `0x18000567c`
- end: `0x180005749`
- name: `?LogIt@EventManager@@AEAAKPEBGK@Z`
- size: `205`
- prototype: `unsigned int __fastcall(EventManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800053b8`
- `0x180005474`
- `0x1800054ec`
- `0x1800055d0`
- `0x180005750`
- `0x180010efc`

## callees

- `0x18000567c`
- `0x180005f7c`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!fputws` at `0x18000570a`
- `msvcrt!fputws` at `0x18000570a`
- `msvcrt!fopen_s` at `0x1800056bd`
- `msvcrt!fopen_s` at `0x1800056bd`
- `msvcrt!fflush` at `0x180005715`
- `msvcrt!fflush` at `0x180005715`
- `msvcrt!fclose` at `0x180005720`
- `msvcrt!fclose` at `0x180005720`

## string_xrefs

- `0x1800056b1`: `TaskScheduler.log`

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
0x18000567c  mov     [rsp+arg_0], rbx
0x180005681  push    rdi
0x180005682  sub     rsp, 850h
0x180005689  mov     rax, cs:__security_cookie
0x180005690  xor     rax, rsp
0x180005693  mov     [rsp+858h+var_18], rax
0x18000569b  mov     edi, r8d
0x18000569e  mov     [rsp+858h+Stream], 0
0x1800056a7  mov     rbx, rdx
0x1800056aa  lea     r8, Mode; "a+"
0x1800056b1  lea     rdx, FileName; "TaskScheduler.log"
0x1800056b8  lea     rcx, [rsp+858h+Stream]; Stream
0x1800056bd  call    cs:__imp_fopen_s
0x1800056c3  test    eax, eax
0x1800056c5  jnz     short loc_180005728
0x1800056c7  xor     edx, edx; Val
0x1800056c9  lea     rcx, [rsp+858h+Buffer]; void *
0x1800056ce  mov     r8d, 800h; Size
0x1800056d4  call    memset_0
0x1800056d9  mov     r9, rbx
0x1800056dc  mov     [rsp+858h+var_838], edi
0x1800056e0  lea     r8, aSD; "%s, (%d)\n"
0x1800056e7  mov     edx, 400h; unsigned __int64
0x1800056ec  lea     rcx, [rsp+858h+Buffer]; unsigned __int16 *
0x1800056f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800056f6  mov     rdx, [rsp+858h+Stream]; Stream
0x1800056fb  lea     rcx, [rsp+858h+Buffer]; Buffer
0x180005700  xor     eax, eax
0x180005702  mov     [rsp+858h+var_1A], ax
0x18000570a  call    cs:__imp_fputws
0x180005710  mov     rcx, [rsp+858h+Stream]; Stream
0x180005715  call    cs:__imp_fflush
0x18000571b  mov     rcx, [rsp+858h+Stream]; Stream
0x180005720  call    cs:__imp_fclose
0x180005726  xor     eax, eax
0x180005728  mov     rcx, [rsp+858h+var_18]
0x180005730  xor     rcx, rsp; StackCookie
0x180005733  call    __security_check_cookie
0x180005738  mov     rbx, [rsp+858h+arg_0]
0x180005740  add     rsp, 850h
0x180005747  pop     rdi
0x180005748  retn
```
