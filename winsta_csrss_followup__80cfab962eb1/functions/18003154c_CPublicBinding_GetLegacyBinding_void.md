# CPublicBinding::GetLegacyBinding(void)

- ea: `0x18003154c`
- end: `0x180031599`
- name: `?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `77`
- prototype: `void *__fastcall(CPublicBinding *__hidden this)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x1800150d0`
- `0x18002e008`
- `0x18002e1ec`
- `0x18002e448`
- `0x18002e584`
- `0x18002e830`
- `0x18002eaac`
- `0x18002ecbc`
- `0x18002ede0`
- `0x18002f0a0`
- `0x18002f324`
- `0x18002f460`
- `0x18002f6c8`
- `0x18002f884`
- `0x18002f9e0`
- `0x18002fae8`
- `0x18002fbf4`

## callees

- `0x180005b40`
- `0x18002eeec`
- `0x18003154c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003156e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003156e`

## string_xrefs

- `0x18003157a`: `Legacy_WinStationOpenServerW return 0xd`

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
0x18003154c  push    rbx
0x18003154e  sub     rsp, 20h
0x180031552  cmp     qword ptr [rcx+20h], 0
0x180031557  mov     rbx, rcx
0x18003155a  jnz     short loc_18003158E
0x18003155c  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180031560  call    ?Legacy_WinStationOpenServerW@@YAPEAXPEAX@Z; Legacy_WinStationOpenServerW(void *)
0x180031565  mov     [rbx+20h], rax
0x180031569  test    rax, rax
0x18003156c  jnz     short loc_18003158E
0x18003156e  call    cs:__imp_GetLastError
0x180031575  nop     dword ptr [rax+rax+00h]
0x18003157a  lea     rdx, aLegacyWinstati; "Legacy_WinStationOpenServerW return 0xd"
0x180031581  mov     ecx, 8; int
0x180031586  mov     r8d, eax
0x180031589  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003158e  mov     rax, [rbx+20h]
0x180031592  add     rsp, 20h
0x180031596  pop     rbx
0x180031597  retn
```
