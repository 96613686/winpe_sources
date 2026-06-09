# EventManager::LogIt(ushort const *,ulong)

- ea: `0x1800207e8`
- end: `0x1800208b5`
- name: `?LogIt@EventManager@@AEAAKPEBGK@Z`
- size: `205`
- prototype: `unsigned int __fastcall(EventManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `16`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800046c0`
- `0x180004c6c`
- `0x180006490`
- `0x180008030`
- `0x18000a03c`
- `0x18001f05c`
- `0x18001f374`
- `0x18001f468`
- `0x18001f560`
- `0x18001f600`
- `0x18001f764`
- `0x180020144`
- `0x180021060`
- `0x1800255e0`
- `0x180030b18`
- `0x180036d30`

## callees

- `0x1800207e8`
- `0x180036e44`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `msvcrt!fflush` at `0x180020881`
- `msvcrt!fflush` at `0x180020881`
- `msvcrt!fclose` at `0x18002088c`
- `msvcrt!fclose` at `0x18002088c`
- `msvcrt!fputws` at `0x180020876`
- `msvcrt!fputws` at `0x180020876`
- `msvcrt!fopen_s` at `0x180020829`
- `msvcrt!fopen_s` at `0x180020829`

## string_xrefs

- `0x18002081d`: `TaskScheduler.log`

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
0x1800207e8  mov     [rsp+arg_0], rbx
0x1800207ed  push    rdi
0x1800207ee  sub     rsp, 850h
0x1800207f5  mov     rax, cs:__security_cookie
0x1800207fc  xor     rax, rsp
0x1800207ff  mov     [rsp+858h+var_18], rax
0x180020807  mov     edi, r8d
0x18002080a  mov     [rsp+858h+Stream], 0
0x180020813  mov     rbx, rdx
0x180020816  lea     r8, Mode; "a+"
0x18002081d  lea     rdx, FileName; "TaskScheduler.log"
0x180020824  lea     rcx, [rsp+858h+Stream]; Stream
0x180020829  call    cs:__imp_fopen_s
0x18002082f  test    eax, eax
0x180020831  jnz     short loc_180020894
0x180020833  xor     edx, edx; Val
0x180020835  lea     rcx, [rsp+858h+Buffer]; void *
0x18002083a  mov     r8d, 800h; Size
0x180020840  call    memset_0
0x180020845  mov     r9, rbx
0x180020848  mov     [rsp+858h+var_838], edi
0x18002084c  lea     r8, aSD; "%s, (%d)\n"
0x180020853  mov     edx, 400h; unsigned __int64
0x180020858  lea     rcx, [rsp+858h+Buffer]; unsigned __int16 *
0x18002085d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020862  mov     rdx, [rsp+858h+Stream]; Stream
0x180020867  lea     rcx, [rsp+858h+Buffer]; Buffer
0x18002086c  xor     eax, eax
0x18002086e  mov     [rsp+858h+var_1A], ax
0x180020876  call    cs:__imp_fputws
0x18002087c  mov     rcx, [rsp+858h+Stream]; Stream
0x180020881  call    cs:__imp_fflush
0x180020887  mov     rcx, [rsp+858h+Stream]; Stream
0x18002088c  call    cs:__imp_fclose
0x180020892  xor     eax, eax
0x180020894  mov     rcx, [rsp+858h+var_18]
0x18002089c  xor     rcx, rsp; StackCookie
0x18002089f  call    __security_check_cookie
0x1800208a4  mov     rbx, [rsp+858h+arg_0]
0x1800208ac  add     rsp, 850h
0x1800208b3  pop     rdi
0x1800208b4  retn
```
