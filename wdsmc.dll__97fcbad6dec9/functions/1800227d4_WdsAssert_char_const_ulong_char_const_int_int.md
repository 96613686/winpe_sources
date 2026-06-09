# WdsAssert(char const *,ulong,char const *,int,int)

- ea: `0x1800227d4`
- end: `0x180022866`
- name: `?WdsAssert@@YAXPEBDK0HH@Z`
- size: `146`
- prototype: `void __fastcall(const char *, unsigned int, const char *, int, int)`
- caller_count: `65`
- callee_count: `4`
- tags: ``

## callers

- `0x180002810`
- `0x1800033d8`
- `0x18000433c`
- `0x18000480c`
- `0x180005098`
- `0x180005a4c`
- `0x180005f18`
- `0x180008610`
- `0x180008738`
- `0x180008c50`
- `0x180008d38`
- `0x180008dcc`
- `0x180009ab8`
- `0x180009e84`
- `0x18000c6c0`
- `0x18000cd20`
- `0x18000d060`
- `0x18000d978`
- `0x18000de34`
- `0x18000e1e0`
- `0x18000f130`
- `0x18000f480`
- `0x1800109f0`
- `0x180011160`
- `0x180011220`
- `0x180011610`
- `0x18001198c`
- `0x180011bbc`
- `0x180011ff0`
- `0x180012a60`
- `0x180012c98`
- `0x1800132cc`
- `0x1800142b0`
- `0x1800148b4`
- `0x1800150c0`
- `0x180015620`
- `0x180016e70`
- `0x180017254`
- `0x180017f40`
- `0x180018060`
- `0x180018120`
- `0x180018488`
- `0x180018f20`
- `0x1800194ac`
- `0x180019628`
- `0x1800196b4`
- `0x1800197e0`
- `0x180019874`
- `0x180019a3c`
- `0x180019c90`

## callees

- `0x1800227d4`
- `0x18002286c`
- `0x180026670`
- `0x180026d46`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x180022845`
- `KERNEL32!OutputDebugStringA` at `0x180022845`

## pseudocode

```c
void __fastcall WdsAssert(const char *a1, int a2, const char *a3, __int64 a4, int a5)
{
  CHAR OutputString[256]; // [rsp+40h] [rbp-128h] BYREF

  if ( !a5 )
  {
    memset_0(OutputString, 0, sizeof(OutputString));
    StringCchPrintfA(OutputString, 0x100u, "%s[%s:%u] %s\n", "RETAIL ASSERT", a1, a2, a3);
    OutputDebugStringA(OutputString);
  }
}

```

## disassembly

```asm
0x1800227d4  push    rbx
0x1800227d6  push    rsi
0x1800227d7  push    rdi
0x1800227d8  sub     rsp, 150h
0x1800227df  mov     rax, cs:__security_cookie
0x1800227e6  xor     rax, rsp
0x1800227e9  mov     [rsp+168h+var_28], rax
0x1800227f1  cmp     [rsp+168h+arg_20], 0
0x1800227f9  mov     rsi, r8
0x1800227fc  mov     edi, edx
0x1800227fe  mov     rbx, rcx
0x180022801  jnz     short loc_18002284B
0x180022803  xor     edx, edx; Val
0x180022805  lea     rcx, [rsp+168h+OutputString]; void *
0x18002280a  mov     r8d, 100h; Size
0x180022810  call    memset_0
0x180022815  mov     [rsp+168h+var_138], rsi
0x18002281a  lea     r9, aRetailAssert; "RETAIL ASSERT"
0x180022821  mov     [rsp+168h+var_140], edi
0x180022825  lea     r8, aSSUS; "%s[%s:%u] %s\n"
0x18002282c  mov     edx, 100h; unsigned __int64
0x180022831  mov     [rsp+168h+var_148], rbx
0x180022836  lea     rcx, [rsp+168h+OutputString]; Buffer
0x18002283b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180022840  lea     rcx, [rsp+168h+OutputString]; lpOutputString
0x180022845  call    cs:__imp_OutputDebugStringA
0x18002284b  mov     rcx, [rsp+168h+var_28]
0x180022853  xor     rcx, rsp; StackCookie
0x180022856  call    __security_check_cookie
0x18002285b  add     rsp, 150h
0x180022862  pop     rdi
0x180022863  pop     rsi
0x180022864  pop     rbx
0x180022865  retn
```
