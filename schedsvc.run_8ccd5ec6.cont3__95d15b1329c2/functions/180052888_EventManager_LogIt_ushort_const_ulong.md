# EventManager::LogIt(ushort const *,ulong)

- ea: `0x180052888`
- end: `0x18005296e`
- name: `?LogIt@EventManager@@AEAAKPEBGK@Z`
- size: `230`
- prototype: `unsigned int __fastcall(EventManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800403a4`
- `0x180047070`
- `0x180051830`
- `0x180051914`
- `0x1800519e0`
- `0x1800521cc`
- `0x1800525c0`
- `0x1800526e4`
- `0x1800527d0`

## callees

- `0x18000a460`
- `0x180052888`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `msvcrt!fflush` at `0x18005292d`
- `msvcrt!fflush` at `0x18005292d`
- `msvcrt!fclose` at `0x18005293e`
- `msvcrt!fclose` at `0x18005293e`
- `msvcrt!fputws` at `0x18005291c`
- `msvcrt!fputws` at `0x18005291c`
- `msvcrt!fopen_s` at `0x1800528c9`
- `msvcrt!fopen_s` at `0x1800528c9`

## string_xrefs

- `0x1800528bd`: `TaskScheduler.log`

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
0x180052888  mov     [rsp+arg_0], rbx
0x18005288d  push    rdi
0x18005288e  sub     rsp, 850h
0x180052895  mov     rax, cs:__security_cookie
0x18005289c  xor     rax, rsp
0x18005289f  mov     [rsp+858h+var_18], rax
0x1800528a7  mov     edi, r8d
0x1800528aa  mov     [rsp+858h+Stream], 0
0x1800528b3  mov     rbx, rdx
0x1800528b6  lea     r8, Mode; "a+"
0x1800528bd  lea     rdx, FileName; "TaskScheduler.log"
0x1800528c4  lea     rcx, [rsp+858h+Stream]; Stream
0x1800528c9  call    cs:__imp_fopen_s
0x1800528d0  nop     dword ptr [rax+rax+00h]
0x1800528d5  test    eax, eax
0x1800528d7  jnz     short loc_18005294C
0x1800528d9  xor     edx, edx; Val
0x1800528db  lea     rcx, [rsp+858h+Buffer]; void *
0x1800528e0  mov     r8d, 800h; Size
0x1800528e6  call    memset_0
0x1800528eb  mov     r9, rbx
0x1800528ee  mov     [rsp+858h+var_838], edi
0x1800528f2  lea     r8, aSD; "%s, (%d)\n"
0x1800528f9  mov     edx, 400h; unsigned __int64
0x1800528fe  lea     rcx, [rsp+858h+Buffer]; unsigned __int16 *
0x180052903  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052908  mov     rdx, [rsp+858h+Stream]; Stream
0x18005290d  lea     rcx, [rsp+858h+Buffer]; Buffer
0x180052912  xor     eax, eax
0x180052914  mov     [rsp+858h+var_1A], ax
0x18005291c  call    cs:__imp_fputws
0x180052923  nop     dword ptr [rax+rax+00h]
0x180052928  mov     rcx, [rsp+858h+Stream]; Stream
0x18005292d  call    cs:__imp_fflush
0x180052934  nop     dword ptr [rax+rax+00h]
0x180052939  mov     rcx, [rsp+858h+Stream]; Stream
0x18005293e  call    cs:__imp_fclose
0x180052945  nop     dword ptr [rax+rax+00h]
0x18005294a  xor     eax, eax
0x18005294c  mov     rcx, [rsp+858h+var_18]
0x180052954  xor     rcx, rsp; StackCookie
0x180052957  call    __security_check_cookie
0x18005295c  mov     rbx, [rsp+858h+arg_0]
0x180052964  add     rsp, 850h
0x18005296b  pop     rdi
0x18005296c  retn
```
