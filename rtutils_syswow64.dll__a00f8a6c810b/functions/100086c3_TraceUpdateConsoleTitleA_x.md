# TraceUpdateConsoleTitleA(x)

- ea: `0x100086c3`
- end: `0x10008726`
- name: `_TraceUpdateConsoleTitleA@4`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x10009977`
- `0x10009eb2`

## callees

- `0x10003c20`
- `0x10005d00`
- `0x100086c3`

## import_xrefs

- `api-ms-win-core-console-l2-2-0!SetConsoleTitleA` at `0x10008712`
- `api-ms-win-core-console-l2-2-0!SetConsoleTitleA` at `0x10008712`

## pseudocode

```c
HRESULT __thiscall TraceUpdateConsoleTitleA(_BYTE *this)
{
  const char *v1; // eax
  HRESULT result; // eax
  char pszDest[260]; // [esp+0h] [ebp-108h] BYREF

  v1 = "%s [Tracing Active]";
  if ( (this[32] & 1) != 0 )
    v1 = "%s [Tracing Inactive]";
  result = StringCchPrintfA(pszDest, 0x104u, v1, this + 40);
  if ( result < 0 )
    return (unsigned __int16)result;
  SetConsoleTitleA(pszDest);
  return 0;
}

```

## disassembly

```asm
0x100086c3  mov     edi, edi
0x100086c5  push    ebp
0x100086c6  mov     ebp, esp
0x100086c8  sub     esp, 108h
0x100086ce  mov     eax, ___security_cookie
0x100086d3  xor     eax, ebp
0x100086d5  mov     [ebp+var_4], eax
0x100086d8  test    byte ptr [ecx+20h], 1
0x100086dc  lea     eax, [ecx+28h]
0x100086df  push    eax
0x100086e0  mov     ecx, offset aSTracingInacti; "%s [Tracing Inactive]"
0x100086e5  mov     eax, offset aSTracingActive; "%s [Tracing Active]"
0x100086ea  cmovnz  eax, ecx
0x100086ed  push    eax; pszFormat
0x100086ee  lea     eax, [ebp+pszDest]
0x100086f4  push    104h; cchDest
0x100086f9  push    eax; pszDest
0x100086fa  call    _StringCchPrintfA
0x100086ff  add     esp, 10h
0x10008702  test    eax, eax
0x10008704  jns     short loc_1000870B
0x10008706  movzx   eax, ax
0x10008709  jmp     short loc_1000871A
0x1000870b  lea     eax, [ebp+pszDest]
0x10008711  push    eax; lpConsoleTitle
0x10008712  call    ds:__imp__SetConsoleTitleA@4; SetConsoleTitleA(x)
0x10008718  xor     eax, eax
0x1000871a  mov     ecx, [ebp+var_4]
0x1000871d  xor     ecx, ebp; StackCookie
0x1000871f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10008724  leave
0x10008725  retn
```
