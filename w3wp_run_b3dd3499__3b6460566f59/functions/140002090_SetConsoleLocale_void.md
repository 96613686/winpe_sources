# SetConsoleLocale(void)

- ea: `0x140002090`
- end: `0x140002154`
- name: `?SetConsoleLocale@@YAXXZ`
- size: `196`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400027b0`
- `0x14000377c`

## callees

- `0x140002090`
- `0x1400038e0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140002112`
- `msvcrt!swprintf_s` at `0x140002112`
- `msvcrt!_wsetlocale` at `0x1400020bc`
- `msvcrt!_wsetlocale` at `0x1400020ce`
- `msvcrt!_wsetlocale` at `0x1400020e0`
- `msvcrt!_wsetlocale` at `0x1400020f2`
- `msvcrt!_wsetlocale` at `0x140002122`
- `msvcrt!_wsetlocale` at `0x1400020bc`
- `msvcrt!_wsetlocale` at `0x1400020ce`
- `msvcrt!_wsetlocale` at `0x1400020e0`
- `msvcrt!_wsetlocale` at `0x1400020f2`
- `msvcrt!_wsetlocale` at `0x140002122`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x1400020f8`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x1400020f8`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x140002132`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x140002132`

## pseudocode

```c
void SetConsoleLocale(void)
{
  UINT ConsoleOutputCP; // eax
  wchar_t Buffer[12]; // [rsp+20h] [rbp-28h] BYREF

  if ( !dword_140008E68 )
  {
    _wsetlocale(1, L".OCP");
    _wsetlocale(3, L".OCP");
    _wsetlocale(4, L".OCP");
    _wsetlocale(5, L".OCP");
    ConsoleOutputCP = GetConsoleOutputCP();
    swprintf_s(Buffer, 0xCu, L".%d", ConsoleOutputCP);
    _wsetlocale(2, Buffer);
    SetThreadPreferredUILanguages(0x100u, 0, 0);
    dword_140008E68 = 1;
  }
}

```

## disassembly

```asm
0x140002090  sub     rsp, 48h
0x140002094  mov     rax, cs:__security_cookie
0x14000209b  xor     rax, rsp
0x14000209e  mov     [rsp+48h+var_10], rax
0x1400020a3  cmp     cs:dword_140008E68, 0
0x1400020aa  jnz     loc_140002142
0x1400020b0  lea     rdx, aOcp; ".OCP"
0x1400020b7  mov     ecx, 1; Category
0x1400020bc  call    cs:__imp__wsetlocale
0x1400020c2  lea     rdx, aOcp; ".OCP"
0x1400020c9  mov     ecx, 3; Category
0x1400020ce  call    cs:__imp__wsetlocale
0x1400020d4  lea     rdx, aOcp; ".OCP"
0x1400020db  mov     ecx, 4; Category
0x1400020e0  call    cs:__imp__wsetlocale
0x1400020e6  lea     rdx, aOcp; ".OCP"
0x1400020ed  mov     ecx, 5; Category
0x1400020f2  call    cs:__imp__wsetlocale
0x1400020f8  call    cs:__imp_GetConsoleOutputCP
0x1400020fe  lea     r8, aD; ".%d"
0x140002105  mov     edx, 0Ch; BufferCount
0x14000210a  mov     r9d, eax
0x14000210d  lea     rcx, [rsp+48h+Buffer]; Buffer
0x140002112  call    cs:__imp_swprintf_s
0x140002118  lea     rdx, [rsp+48h+Buffer]; Locale
0x14000211d  mov     ecx, 2; Category
0x140002122  call    cs:__imp__wsetlocale
0x140002128  xor     r8d, r8d; pulNumLanguages
0x14000212b  xor     edx, edx; pwszLanguagesBuffer
0x14000212d  mov     ecx, 100h; dwFlags
0x140002132  call    cs:__imp_SetThreadPreferredUILanguages
0x140002138  mov     cs:dword_140008E68, 1
0x140002142  mov     rcx, [rsp+48h+var_10]
0x140002147  xor     rcx, rsp; StackCookie
0x14000214a  call    __security_check_cookie
0x14000214f  add     rsp, 48h
0x140002153  retn
```
