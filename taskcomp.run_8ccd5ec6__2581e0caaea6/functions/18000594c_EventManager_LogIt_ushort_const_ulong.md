# EventManager::LogIt(ushort const *,ulong)

- ea: `0x18000594c`
- end: `0x180005a32`
- name: `?LogIt@EventManager@@AEAAKPEBGK@Z`
- size: `230`
- prototype: `unsigned int __fastcall(EventManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005650`
- `0x18000571c`
- `0x1800057a0`
- `0x180005894`
- `0x180005a38`
- `0x180011958`

## callees

- `0x18000594c`
- `0x180006314`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `msvcrt!fputws` at `0x1800059e0`
- `msvcrt!fputws` at `0x1800059e0`
- `msvcrt!fopen_s` at `0x18000598d`
- `msvcrt!fopen_s` at `0x18000598d`
- `msvcrt!fflush` at `0x1800059f1`
- `msvcrt!fflush` at `0x1800059f1`
- `msvcrt!fclose` at `0x180005a02`
- `msvcrt!fclose` at `0x180005a02`

## string_xrefs

- `0x180005981`: `TaskScheduler.log`

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
0x18000594c  mov     [rsp+arg_0], rbx
0x180005951  push    rdi
0x180005952  sub     rsp, 850h
0x180005959  mov     rax, cs:__security_cookie
0x180005960  xor     rax, rsp
0x180005963  mov     [rsp+858h+var_18], rax
0x18000596b  mov     edi, r8d
0x18000596e  mov     [rsp+858h+Stream], 0
0x180005977  mov     rbx, rdx
0x18000597a  lea     r8, Mode; "a+"
0x180005981  lea     rdx, FileName; "TaskScheduler.log"
0x180005988  lea     rcx, [rsp+858h+Stream]; Stream
0x18000598d  call    cs:__imp_fopen_s
0x180005994  nop     dword ptr [rax+rax+00h]
0x180005999  test    eax, eax
0x18000599b  jnz     short loc_180005A10
0x18000599d  xor     edx, edx; Val
0x18000599f  lea     rcx, [rsp+858h+Buffer]; void *
0x1800059a4  mov     r8d, 800h; Size
0x1800059aa  call    memset_0
0x1800059af  mov     r9, rbx
0x1800059b2  mov     [rsp+858h+var_838], edi
0x1800059b6  lea     r8, aSD; "%s, (%d)\n"
0x1800059bd  mov     edx, 400h; unsigned __int64
0x1800059c2  lea     rcx, [rsp+858h+Buffer]; unsigned __int16 *
0x1800059c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800059cc  mov     rdx, [rsp+858h+Stream]; Stream
0x1800059d1  lea     rcx, [rsp+858h+Buffer]; Buffer
0x1800059d6  xor     eax, eax
0x1800059d8  mov     [rsp+858h+var_1A], ax
0x1800059e0  call    cs:__imp_fputws
0x1800059e7  nop     dword ptr [rax+rax+00h]
0x1800059ec  mov     rcx, [rsp+858h+Stream]; Stream
0x1800059f1  call    cs:__imp_fflush
0x1800059f8  nop     dword ptr [rax+rax+00h]
0x1800059fd  mov     rcx, [rsp+858h+Stream]; Stream
0x180005a02  call    cs:__imp_fclose
0x180005a09  nop     dword ptr [rax+rax+00h]
0x180005a0e  xor     eax, eax
0x180005a10  mov     rcx, [rsp+858h+var_18]
0x180005a18  xor     rcx, rsp; StackCookie
0x180005a1b  call    __security_check_cookie
0x180005a20  mov     rbx, [rsp+858h+arg_0]
0x180005a28  add     rsp, 850h
0x180005a2f  pop     rdi
0x180005a30  retn
```
