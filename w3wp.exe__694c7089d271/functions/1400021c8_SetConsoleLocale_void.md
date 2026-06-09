# SetConsoleLocale(void)

- ea: `0x1400021c8`
- end: `0x1400022bd`
- name: `?SetConsoleLocale@@YAXXZ`
- size: `245`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002a40`
- `0x140003b4c`

## callees

- `0x1400021c8`
- `0x140003cc0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140002268`
- `msvcrt!swprintf_s` at `0x140002268`
- `msvcrt!_wsetlocale` at `0x1400021f4`
- `msvcrt!_wsetlocale` at `0x14000220c`
- `msvcrt!_wsetlocale` at `0x140002224`
- `msvcrt!_wsetlocale` at `0x14000223c`
- `msvcrt!_wsetlocale` at `0x14000227e`
- `msvcrt!_wsetlocale` at `0x1400021f4`
- `msvcrt!_wsetlocale` at `0x14000220c`
- `msvcrt!_wsetlocale` at `0x140002224`
- `msvcrt!_wsetlocale` at `0x14000223c`
- `msvcrt!_wsetlocale` at `0x14000227e`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x140002248`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x140002248`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x140002294`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x140002294`

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
0x1400021c8  sub     rsp, 48h
0x1400021cc  mov     rax, cs:__security_cookie
0x1400021d3  xor     rax, rsp
0x1400021d6  mov     [rsp+48h+var_10], rax
0x1400021db  cmp     cs:dword_140008E68, 0
0x1400021e2  jnz     loc_1400022AA
0x1400021e8  lea     rdx, aOcp; ".OCP"
0x1400021ef  mov     ecx, 1; Category
0x1400021f4  call    cs:__imp__wsetlocale
0x1400021fb  nop     dword ptr [rax+rax+00h]
0x140002200  lea     rdx, aOcp; ".OCP"
0x140002207  mov     ecx, 3; Category
0x14000220c  call    cs:__imp__wsetlocale
0x140002213  nop     dword ptr [rax+rax+00h]
0x140002218  lea     rdx, aOcp; ".OCP"
0x14000221f  mov     ecx, 4; Category
0x140002224  call    cs:__imp__wsetlocale
0x14000222b  nop     dword ptr [rax+rax+00h]
0x140002230  lea     rdx, aOcp; ".OCP"
0x140002237  mov     ecx, 5; Category
0x14000223c  call    cs:__imp__wsetlocale
0x140002243  nop     dword ptr [rax+rax+00h]
0x140002248  call    cs:__imp_GetConsoleOutputCP
0x14000224f  nop     dword ptr [rax+rax+00h]
0x140002254  lea     r8, aD; ".%d"
0x14000225b  mov     edx, 0Ch; BufferCount
0x140002260  mov     r9d, eax
0x140002263  lea     rcx, [rsp+48h+Buffer]; Buffer
0x140002268  call    cs:__imp_swprintf_s
0x14000226f  nop     dword ptr [rax+rax+00h]
0x140002274  lea     rdx, [rsp+48h+Buffer]; Locale
0x140002279  mov     ecx, 2; Category
0x14000227e  call    cs:__imp__wsetlocale
0x140002285  nop     dword ptr [rax+rax+00h]
0x14000228a  xor     r8d, r8d; pulNumLanguages
0x14000228d  xor     edx, edx; pwszLanguagesBuffer
0x14000228f  mov     ecx, 100h; dwFlags
0x140002294  call    cs:__imp_SetThreadPreferredUILanguages
0x14000229b  nop     dword ptr [rax+rax+00h]
0x1400022a0  mov     cs:dword_140008E68, 1
0x1400022aa  mov     rcx, [rsp+48h+var_10]
0x1400022af  xor     rcx, rsp; StackCookie
0x1400022b2  call    __security_check_cookie
0x1400022b7  add     rsp, 48h
0x1400022bb  retn
```
