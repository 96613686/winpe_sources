# WdsAssert(char const *,ulong,char const *,int,int)

- ea: `0x180012f34`
- end: `0x180012fc6`
- name: `?WdsAssert@@YAXPEBDK0HH@Z`
- size: `146`
- prototype: `void __fastcall(const char *, unsigned int, const char *, int, int)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180002268`
- `0x1800026ac`
- `0x18000294c`
- `0x1800042f4`
- `0x1800051e8`
- `0x180007310`
- `0x180013048`
- `0x18001319c`
- `0x180013254`
- `0x180013314`
- `0x1800133ec`
- `0x1800134f4`

## callees

- `0x180012f34`
- `0x180012fcc`
- `0x180015660`
- `0x180015c9d`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x180012fa5`
- `KERNEL32!OutputDebugStringA` at `0x180012fa5`

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
0x180012f34  push    rbx
0x180012f36  push    rsi
0x180012f37  push    rdi
0x180012f38  sub     rsp, 150h
0x180012f3f  mov     rax, cs:__security_cookie
0x180012f46  xor     rax, rsp
0x180012f49  mov     [rsp+168h+var_28], rax
0x180012f51  cmp     [rsp+168h+arg_20], 0
0x180012f59  mov     rsi, r8
0x180012f5c  mov     edi, edx
0x180012f5e  mov     rbx, rcx
0x180012f61  jnz     short loc_180012FAB
0x180012f63  xor     edx, edx; Val
0x180012f65  lea     rcx, [rsp+168h+OutputString]; void *
0x180012f6a  mov     r8d, 100h; Size
0x180012f70  call    memset_0
0x180012f75  mov     [rsp+168h+var_138], rsi
0x180012f7a  lea     r9, aRetailAssert; "RETAIL ASSERT"
0x180012f81  mov     [rsp+168h+var_140], edi
0x180012f85  lea     r8, aSSUS; "%s[%s:%u] %s\n"
0x180012f8c  mov     edx, 100h; unsigned __int64
0x180012f91  mov     [rsp+168h+var_148], rbx
0x180012f96  lea     rcx, [rsp+168h+OutputString]; Buffer
0x180012f9b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180012fa0  lea     rcx, [rsp+168h+OutputString]; lpOutputString
0x180012fa5  call    cs:__imp_OutputDebugStringA
0x180012fab  mov     rcx, [rsp+168h+var_28]
0x180012fb3  xor     rcx, rsp; StackCookie
0x180012fb6  call    __security_check_cookie
0x180012fbb  add     rsp, 150h
0x180012fc2  pop     rdi
0x180012fc3  pop     rsi
0x180012fc4  pop     rbx
0x180012fc5  retn
```
