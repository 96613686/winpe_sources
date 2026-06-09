# IniRegOpenKeyW

- ea: `0x383addfe0`
- end: `0x383ade100`
- name: `IniRegOpenKeyW`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x38387dcc0`
- `0x383adc710`

## callees

- `0x383add760`
- `0x383add980`
- `0x383added0`
- `0x383addfe0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x383ade027`
- `KERNEL32!SetLastError` at `0x383ade08e`
- `KERNEL32!SetLastError` at `0x383ade0c7`
- `KERNEL32!SetLastError` at `0x383ade027`
- `KERNEL32!SetLastError` at `0x383ade08e`
- `KERNEL32!SetLastError` at `0x383ade0c7`
- `KERNEL32!HeapFree` at `0x383ade07f`
- `KERNEL32!HeapFree` at `0x383ade0bf`
- `KERNEL32!HeapFree` at `0x383ade07f`
- `KERNEL32!HeapFree` at `0x383ade0bf`
- `KERNEL32!GetProcessHeap` at `0x383ade071`
- `KERNEL32!GetProcessHeap` at `0x383ade0b1`
- `KERNEL32!GetProcessHeap` at `0x383ade071`
- `KERNEL32!GetProcessHeap` at `0x383ade0b1`
- `ADVAPI32!RegOpenKeyW` at `0x383ade0f9`

## pseudocode

```c
LSTATUS __fastcall IniRegOpenKeyW(HKEY a1, const WCHAR *a2, HKEY *a3)
{
  const WCHAR *Path; // rax
  WCHAR *v5; // rsi
  _WORD *RawString; // rdi
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax

  if ( !dword_383B1F178 )
    return RegOpenKeyW(a1, a2, a3);
  if ( !a2 || !*a2 )
    return IniRegOpenExistingKeyW(a1, a3);
  Path = (const WCHAR *)IniRegMakePath(a1, a2);
  v5 = (WCHAR *)Path;
  if ( !Path )
  {
    SetLastError(8u);
    return 8;
  }
  RawString = (_WORD *)IniRegGetRawString(Path, 0);
  if ( RawString )
  {
    if ( *RawString != 0xFFFF || RawString[1] )
      v8 = 0;
    else
      v8 = 2;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, RawString);
    if ( !v8 )
    {
      *a3 = (HKEY)v5;
      SetLastError(0);
      return 0;
    }
  }
  else
  {
    v8 = 8;
  }
  v10 = GetProcessHeap();
  HeapFree(v10, 0, v5);
  SetLastError(v8);
  return v8;
}

```

## disassembly

```asm
0x383addfe0  push    r14
0x383addfe2  sub     rsp, 20h
0x383addfe6  cmp     cs:dword_383B1F178, 0
0x383addfed  mov     r14, r8
0x383addff0  jz      loc_383ADE0F3
0x383addff6  test    rdx, rdx
0x383addff9  jz      loc_383ADE0E5
0x383addfff  cmp     word ptr [rdx], 0
0x383ade003  jz      loc_383ADE0E5
0x383ade009  mov     [rsp+28h+arg_0], rbx
0x383ade00e  mov     [rsp+28h+arg_8], rsi
0x383ade013  call    IniRegMakePath
0x383ade018  mov     rsi, rax
0x383ade01b  test    rax, rax
0x383ade01e  jnz     short loc_383ADE040
0x383ade020  mov     ebx, 8
0x383ade025  mov     ecx, ebx; dwErrCode
0x383ade027  call    cs:__imp_SetLastError
0x383ade02d  mov     rsi, [rsp+28h+arg_8]
0x383ade032  mov     eax, ebx
0x383ade034  mov     rbx, [rsp+28h+arg_0]
0x383ade039  add     rsp, 20h
0x383ade03d  pop     r14
0x383ade03f  retn
0x383ade040  xor     edx, edx; lpKeyName
0x383ade042  mov     rcx, rax; lpAppName
0x383ade045  mov     [rsp+28h+arg_10], rdi
0x383ade04a  call    IniRegGetRawString
0x383ade04f  mov     rdi, rax
0x383ade052  test    rax, rax
0x383ade055  jz      short loc_383ADE0AC
0x383ade057  mov     eax, 0FFFFh
0x383ade05c  cmp     [rdi], ax
0x383ade05f  jnz     short loc_383ADE06F
0x383ade061  cmp     word ptr [rdi+2], 0
0x383ade066  jnz     short loc_383ADE06F
0x383ade068  mov     ebx, 2
0x383ade06d  jmp     short loc_383ADE071
0x383ade06f  xor     ebx, ebx
0x383ade071  call    cs:__imp_GetProcessHeap
0x383ade077  mov     r8, rdi; lpMem
0x383ade07a  xor     edx, edx; dwFlags
0x383ade07c  mov     rcx, rax; hHeap
0x383ade07f  call    cs:__imp_HeapFree
0x383ade085  test    ebx, ebx
0x383ade087  jnz     short loc_383ADE0B1
0x383ade089  mov     ecx, ebx; dwErrCode
0x383ade08b  mov     [r14], rsi
0x383ade08e  call    cs:__imp_SetLastError
0x383ade094  mov     rdi, [rsp+28h+arg_10]
0x383ade099  mov     rsi, [rsp+28h+arg_8]
0x383ade09e  mov     eax, ebx
0x383ade0a0  mov     rbx, [rsp+28h+arg_0]
0x383ade0a5  add     rsp, 20h
0x383ade0a9  pop     r14
0x383ade0ab  retn
0x383ade0ac  mov     ebx, 8
0x383ade0b1  call    cs:__imp_GetProcessHeap
0x383ade0b7  mov     r8, rsi; lpMem
0x383ade0ba  xor     edx, edx; dwFlags
0x383ade0bc  mov     rcx, rax; hHeap
0x383ade0bf  call    cs:__imp_HeapFree
0x383ade0c5  mov     ecx, ebx; dwErrCode
0x383ade0c7  call    cs:__imp_SetLastError
0x383ade0cd  mov     rdi, [rsp+28h+arg_10]
0x383ade0d2  mov     rsi, [rsp+28h+arg_8]
0x383ade0d7  mov     eax, ebx
0x383ade0d9  mov     rbx, [rsp+28h+arg_0]
0x383ade0de  add     rsp, 20h
0x383ade0e2  pop     r14
0x383ade0e4  retn
0x383ade0e5  mov     rdx, r8
0x383ade0e8  add     rsp, 20h
0x383ade0ec  pop     r14
0x383ade0ee  jmp     IniRegOpenExistingKeyW
0x383ade0f3  add     rsp, 20h
0x383ade0f7  pop     r14
0x383ade0f9  jmp     cs:__imp_RegOpenKeyW
```
