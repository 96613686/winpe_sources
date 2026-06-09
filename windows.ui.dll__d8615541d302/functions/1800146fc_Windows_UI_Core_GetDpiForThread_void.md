# Windows::UI::Core::GetDpiForThread(void)

- ea: `0x1800146fc`
- end: `0x18001474d`
- name: `?GetDpiForThread@Core@UI@Windows@@YAMXZ`
- size: `81`
- prototype: `float __fastcall(Windows::UI::Core *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180013830`
- `0x180013f70`
- `0x180096258`
- `0x180097110`

## callees

- `0x1800146fc`
- `0x18006040c`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014736`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180014736`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x180014712`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x180014712`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x180014709`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x180014709`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x180014725`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x180014725`

## pseudocode

```c
float __fastcall Windows::UI::Core::GetDpiForThread(Windows::UI::Core *this)
{
  __int64 ThreadDpiAwarenessContext; // rax
  int DpiForSystem; // eax

  if ( !(unsigned __int8)IsTextInputClientWrapperCreatePresent(this) )
    return 0.0;
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  if ( (unsigned int)GetAwarenessFromDpiAwarenessContext(ThreadDpiAwarenessContext) == 2 )
    return 0.0;
  DpiForSystem = GetDpiForSystem();
  return (float)MulDiv(DpiForSystem, 100, 96) / 100.0;
}

```

## disassembly

```asm
0x1800146fc  sub     rsp, 28h
0x180014700  call    IsTextInputClientWrapperCreatePresent
0x180014705  test    al, al
0x180014707  jz      short loc_18001471D
0x180014709  call    cs:__imp_GetThreadDpiAwarenessContext
0x18001470f  mov     rcx, rax
0x180014712  call    cs:__imp_GetAwarenessFromDpiAwarenessContext
0x180014718  cmp     eax, 2
0x18001471b  jnz     short loc_180014725
0x18001471d  xorps   xmm0, xmm0
0x180014720  add     rsp, 28h
0x180014724  retn
0x180014725  call    cs:__imp_GetDpiForSystem
0x18001472b  mov     edx, 64h ; 'd'; nNumerator
0x180014730  mov     ecx, eax; nNumber
0x180014732  lea     r8d, [rdx-4]; nDenominator
0x180014736  call    cs:__imp_MulDiv
0x18001473c  movd    xmm0, eax
0x180014740  cvtdq2ps xmm0, xmm0
0x180014743  divss   xmm0, cs:__real@42c80000
0x18001474b  jmp     short loc_180014720
```
