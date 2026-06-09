# PrintMessage(uint,...)

- ea: `0x14003694c`
- end: `0x140036a59`
- name: `?PrintMessage@@YAXIZZ`
- size: `269`
- prototype: `void(UINT, ...)`
- caller_count: `58`
- callee_count: `3`
- tags: ``

## callers

- `0x1400309c0`
- `0x140030ac0`
- `0x140030bf8`
- `0x14003123c`
- `0x1400313c4`
- `0x1400314c8`
- `0x1400315c8`
- `0x1400318f0`
- `0x140031c54`
- `0x140031d28`
- `0x140031dfc`
- `0x140031ec8`
- `0x140031fb8`
- `0x140032230`
- `0x14003290c`
- `0x140032dcc`
- `0x140033254`
- `0x140033414`
- `0x14003357c`
- `0x14003364c`
- `0x140033810`
- `0x1400338f8`
- `0x1400339c8`
- `0x140033bac`
- `0x140033ec4`
- `0x14003406c`
- `0x14003413c`
- `0x140034230`
- `0x140034318`
- `0x1400343e8`
- `0x14003451c`
- `0x1400347c4`
- `0x140034898`
- `0x14003496c`
- `0x140034a38`
- `0x140034b0c`
- `0x140034bd8`
- `0x140034cc8`
- `0x140034dc4`
- `0x14003506c`
- `0x140035300`
- `0x140035658`
- `0x140035db4`
- `0x140035f48`
- `0x140036114`
- `0x140036258`
- `0x140036a60`
- `0x140036b34`
- `0x140036ce0`
- `0x140037050`

## callees

- `0x14003694c`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400369f7`
- `msvcrt!_vsnwprintf` at `0x1400369f7`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1400369d2`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1400369d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400369a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400369a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400369bc`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400369bc`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140036a38`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x140036a38`

## pseudocode

```c
void PrintMessage(UINT a1, ...)
{
  char *StdHandle; // rax
  void *v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // r8
  DWORD NumberOfCharsWritten; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t v6[1024]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Buffer[1024]; // [rsp+848h] [rbp+740h] BYREF
  va_list Args; // [rsp+1090h] [rbp+F88h] BYREF

  va_start(Args, a1);
  NumberOfCharsWritten = LoadStringW(0, a1, Buffer, 1024);
  if ( NumberOfCharsWritten )
  {
    StdHandle = (char *)GetStdHandle(0xFFFFFFF5);
    v2 = StdHandle;
    if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL && (GetFileType(StdHandle) & 0xFFFF7FFF) == 2 )
    {
      v3 = _vsnwprintf(v6, 0x3FFu, Buffer, Args);
      if ( v3 < 0x400 )
      {
        if ( v3 == 1023 )
          v6[1023] = 0;
        v4 = -1;
        do
          ++v4;
        while ( v6[v4] );
        NumberOfCharsWritten = v4;
        WriteConsoleW(v2, v6, v4, &NumberOfCharsWritten, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x14003694c  mov     rax, rsp
0x14003694f  mov     [rax+8], ecx
0x140036952  mov     [rax+10h], rdx
0x140036956  mov     [rax+18h], r8
0x14003695a  mov     [rax+20h], r9
0x14003695e  push    rbp
0x14003695f  push    rbx
0x140036960  push    rsi
0x140036961  push    rdi
0x140036962  lea     rbp, [rax-0F78h]
0x140036969  mov     eax, 1058h
0x14003696e  call    _alloca_probe
0x140036973  sub     rsp, rax
0x140036976  mov     rax, cs:__security_cookie
0x14003697d  xor     rax, rsp
0x140036980  mov     [rbp+0F70h+var_30], rax
0x140036987  mov     edx, ecx; uID
0x140036989  lea     r8, [rbp+0F70h+Buffer]; lpBuffer
0x140036990  xor     edi, edi
0x140036992  lea     rsi, [rbp+0F70h+Args]
0x140036999  xor     ecx, ecx; hInstance
0x14003699b  mov     [rsp+1070h+NumberOfCharsWritten], edi
0x14003699f  mov     r9d, 400h; cchBufferMax
0x1400369a5  call    cs:__imp_LoadStringW
0x1400369ab  mov     [rsp+1070h+NumberOfCharsWritten], eax
0x1400369af  test    eax, eax
0x1400369b1  jz      loc_140036A3E
0x1400369b7  mov     ecx, 0FFFFFFF5h; nStdHandle
0x1400369bc  call    cs:__imp_GetStdHandle
0x1400369c2  mov     rbx, rax
0x1400369c5  lea     rcx, [rax-1]
0x1400369c9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400369cd  ja      short loc_140036A3E
0x1400369cf  mov     rcx, rax; hFile
0x1400369d2  call    cs:__imp_GetFileType
0x1400369d8  btr     eax, 0Fh
0x1400369dc  cmp     eax, 2
0x1400369df  jnz     short loc_140036A3E
0x1400369e1  mov     r9, rsi; Args
0x1400369e4  lea     r8, [rbp+0F70h+Buffer]; Format
0x1400369eb  mov     esi, 3FFh
0x1400369f0  lea     rcx, [rsp+1070h+var_1030]; Buffer
0x1400369f5  mov     edx, esi; BufferCount
0x1400369f7  call    cs:__imp__vsnwprintf
0x1400369fd  test    eax, eax
0x1400369ff  js      short loc_140036A3E
0x140036a01  cmp     eax, esi
0x140036a03  ja      short loc_140036A3E
0x140036a05  jnz     short loc_140036A0E
0x140036a07  mov     [rbp+0F70h+var_832], di
0x140036a0e  lea     rax, [rsp+1070h+var_1030]
0x140036a13  or      r8, 0FFFFFFFFFFFFFFFFh
0x140036a17  inc     r8; nNumberOfCharsToWrite
0x140036a1a  cmp     [rax+r8*2], di
0x140036a1f  jnz     short loc_140036A17
0x140036a21  lea     r9, [rsp+1070h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x140036a26  mov     [rsp+1070h+NumberOfCharsWritten], r8d
0x140036a2b  lea     rdx, [rsp+1070h+var_1030]; lpBuffer
0x140036a30  mov     [rsp+20h], rdi; lpReserved
0x140036a35  mov     rcx, rbx; hConsoleOutput
0x140036a38  call    cs:__imp_WriteConsoleW
0x140036a3e  mov     rcx, [rbp+0F70h+var_30]
0x140036a45  xor     rcx, rsp; StackCookie
0x140036a48  call    __security_check_cookie
0x140036a4d  add     rsp, 1058h
0x140036a54  pop     rdi
0x140036a55  pop     rsi
0x140036a56  pop     rbx
0x140036a57  pop     rbp
0x140036a58  retn
```
