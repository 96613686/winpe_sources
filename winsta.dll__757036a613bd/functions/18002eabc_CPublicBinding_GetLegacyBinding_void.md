# CPublicBinding::GetLegacyBinding(void)

- ea: `0x18002eabc`
- end: `0x18002eb02`
- name: `?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `70`
- prototype: `void *__fastcall(CPublicBinding *__hidden this)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x1800140f4`
- `0x18002bdd8`
- `0x18002bf90`
- `0x18002c1c0`
- `0x18002c2e0`
- `0x18002c550`
- `0x18002c79c`
- `0x18002c96c`
- `0x18002ca70`
- `0x18002cd00`
- `0x18002cf4c`
- `0x18002d06c`
- `0x18002d2a0`
- `0x18002d438`
- `0x18002d57c`
- `0x18002d668`
- `0x18002d754`

## callees

- `0x180007890`
- `0x18002cb5c`
- `0x18002eabc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eade`

## string_xrefs

- `0x18002eae4`: `Legacy_WinStationOpenServerW return 0xd`

## pseudocode

```c
unsigned __int16 *__fastcall CPublicBinding::GetLegacyBinding(unsigned __int16 **this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  DWORD LastError; // eax

  if ( !this[4] )
  {
    v3 = Legacy_WinStationOpenServerW(this[5], a2);
    this[4] = (unsigned __int16 *)v3;
    if ( !v3 )
    {
      LastError = GetLastError();
      _DbgPrintMessage(8, "Legacy_WinStationOpenServerW return 0xd", LastError);
    }
  }
  return this[4];
}

```

## disassembly

```asm
0x18002eabc  push    rbx
0x18002eabe  sub     rsp, 20h
0x18002eac2  cmp     qword ptr [rcx+20h], 0
0x18002eac7  mov     rbx, rcx
0x18002eaca  jnz     short loc_18002EAF8
0x18002eacc  mov     rcx, [rcx+28h]; unsigned __int16 *
0x18002ead0  call    ?Legacy_WinStationOpenServerW@@YAPEAXPEAX@Z; Legacy_WinStationOpenServerW(void *)
0x18002ead5  mov     [rbx+20h], rax
0x18002ead9  test    rax, rax
0x18002eadc  jnz     short loc_18002EAF8
0x18002eade  call    cs:__imp_GetLastError
0x18002eae4  lea     rdx, aLegacyWinstati; "Legacy_WinStationOpenServerW return 0xd"
0x18002eaeb  mov     ecx, 8; int
0x18002eaf0  mov     r8d, eax
0x18002eaf3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002eaf8  mov     rax, [rbx+20h]
0x18002eafc  add     rsp, 20h
0x18002eb00  pop     rbx
0x18002eb01  retn
```
