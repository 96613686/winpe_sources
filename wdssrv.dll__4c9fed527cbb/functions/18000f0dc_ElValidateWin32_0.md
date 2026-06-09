# ElValidateWin32_0

- ea: `0x18000f0dc`
- end: `0x18000f1a5`
- name: `ElValidateWin32_0`
- size: `201`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008214`
- `0x180008c58`
- `0x1800096a4`
- `0x180009da4`
- `0x18000aa50`
- `0x18000ac40`
- `0x18000b1ec`
- `0x18000c3b4`
- `0x18000cc30`
- `0x18000d380`
- `0x18000e310`
- `0x18000e360`
- `0x18000e988`

## callees

- `0x18000f0dc`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f186`
- `KERNEL32!SetLastError` at `0x18000f186`
- `KERNEL32!GetLastError` at `0x18000f102`
- `KERNEL32!GetLastError` at `0x18000f14e`
- `KERNEL32!GetLastError` at `0x18000f102`
- `KERNEL32!GetLastError` at `0x18000f14e`

## string_xrefs

- `0x18000f11e`: `base\eco\wds\wdssrv\server\src\wdsservice.cpp`
- `0x18000f167`: `base\eco\wds\wdssrv\server\src\wdsservice.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_0(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\wdsservice.cpp",
        a4,
        &dword_18001F974,
        a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\wdsservice.cpp",
        a4,
        &dword_18001F974,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000f0dc  mov     [rsp+arg_0], rbx
0x18000f0e1  mov     [rsp+arg_8], rsi
0x18000f0e6  push    rdi
0x18000f0e7  sub     rsp, 40h
0x18000f0eb  mov     esi, r9d
0x18000f0ee  mov     edi, ecx
0x18000f0f0  test    ecx, ecx
0x18000f0f2  jz      loc_18000F192
0x18000f0f8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000f100  jz      short loc_18000F144
0x18000f102  call    cs:__imp_GetLastError
0x18000f109  nop     dword ptr [rax+rax+00h]
0x18000f10e  lea     r9, dword_18001F974
0x18000f115  mov     [rsp+48h+var_20], edi
0x18000f119  mov     [rsp+48h+var_28], r9
0x18000f11e  lea     r8, aBaseEcoWdsWdss_14; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18000f125  mov     ebx, eax
0x18000f127  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000f12e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000f135  mov     r9d, esi
0x18000f138  mov     ecx, 80000h
0x18000f13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f142  jmp     short loc_18000F184
0x18000f144  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000f14c  jz      short loc_18000F192
0x18000f14e  call    cs:__imp_GetLastError
0x18000f155  nop     dword ptr [rax+rax+00h]
0x18000f15a  lea     r9, dword_18001F974
0x18000f161  mov     dword ptr [rsp+48h+var_28], edi
0x18000f165  mov     ebx, eax
0x18000f167  lea     rdx, aBaseEcoWdsWdss_14; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18000f16e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000f175  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000f17c  mov     r8d, esi
0x18000f17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f184  mov     ecx, ebx; dwErrCode
0x18000f186  call    cs:__imp_SetLastError
0x18000f18d  nop     dword ptr [rax+rax+00h]
0x18000f192  mov     rbx, [rsp+48h+arg_0]
0x18000f197  mov     eax, edi
0x18000f199  mov     rsi, [rsp+48h+arg_8]
0x18000f19e  add     rsp, 40h
0x18000f1a2  pop     rdi
0x18000f1a3  retn
```
