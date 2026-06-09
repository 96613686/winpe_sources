# ElValidateWin32

- ea: `0x180003944`
- end: `0x180003a12`
- name: `ElValidateWin32`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `48`
- callee_count: `2`
- tags: ``

## callers

- `0x180002108`
- `0x180002990`
- `0x180002ab0`
- `0x180002c24`
- `0x180003340`
- `0x180003380`
- `0x1800034b8`
- `0x180003680`
- `0x180003a18`
- `0x180004120`
- `0x1800042f0`
- `0x180004818`
- `0x1800049b4`
- `0x180005600`
- `0x180005c70`
- `0x180005df0`
- `0x180006090`
- `0x18000d380`
- `0x18000fd54`
- `0x18000fedc`
- `0x18001010c`
- `0x18001038c`
- `0x18001040c`
- `0x180010640`
- `0x180011bb0`
- `0x180011ce0`
- `0x180012084`
- `0x1800124ac`
- `0x180012790`
- `0x180013638`
- `0x1800183b0`
- `0x1800184d0`
- `0x1800186f0`
- `0x180018b08`
- `0x180018cdc`
- `0x180019340`
- `0x180019434`
- `0x180019498`
- `0x180019668`
- `0x1800197b0`
- `0x180019a44`
- `0x180019c3c`
- `0x180019d14`
- `0x180019ea4`
- `0x180019f2c`
- `0x180019fb0`
- `0x18001a008`
- `0x18001a474`

## callees

- `0x180003944`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800039ee`
- `KERNEL32!SetLastError` at `0x1800039ee`
- `KERNEL32!GetLastError` at `0x180003972`
- `KERNEL32!GetLastError` at `0x1800039ba`
- `KERNEL32!GetLastError` at `0x180003972`
- `KERNEL32!GetLastError` at `0x1800039ba`

## pseudocode

```c
__int64 __fastcall ElValidateWin32(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &dword_18001F974, a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &dword_18001F974, a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180003944  mov     [rsp+arg_0], rbx
0x180003949  mov     [rsp+arg_8], rbp
0x18000394e  mov     [rsp+arg_10], rsi
0x180003953  push    rdi
0x180003954  sub     rsp, 40h
0x180003958  mov     esi, r9d
0x18000395b  mov     rbp, r8
0x18000395e  mov     edi, ecx
0x180003960  test    ecx, ecx
0x180003962  jz      loc_1800039FA
0x180003968  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180003970  jz      short loc_1800039B0
0x180003972  call    cs:__imp_GetLastError
0x180003979  nop     dword ptr [rax+rax+00h]
0x18000397e  lea     r9, dword_18001F974
0x180003985  mov     [rsp+48h+var_20], edi
0x180003989  mov     [rsp+48h+var_28], r9
0x18000398e  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180003995  mov     ebx, eax
0x180003997  mov     r9d, esi
0x18000399a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800039a1  mov     r8, rbp
0x1800039a4  mov     ecx, 80000h
0x1800039a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ae  jmp     short loc_1800039EC
0x1800039b0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800039b8  jz      short loc_1800039FA
0x1800039ba  call    cs:__imp_GetLastError
0x1800039c1  nop     dword ptr [rax+rax+00h]
0x1800039c6  lea     r9, dword_18001F974
0x1800039cd  mov     dword ptr [rsp+48h+var_28], edi
0x1800039d1  mov     ebx, eax
0x1800039d3  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800039da  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800039e1  mov     r8d, esi
0x1800039e4  mov     rdx, rbp
0x1800039e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ec  mov     ecx, ebx; dwErrCode
0x1800039ee  call    cs:__imp_SetLastError
0x1800039f5  nop     dword ptr [rax+rax+00h]
0x1800039fa  mov     rbx, [rsp+48h+arg_0]
0x1800039ff  mov     eax, edi
0x180003a01  mov     rbp, [rsp+48h+arg_8]
0x180003a06  mov     rsi, [rsp+48h+arg_10]
0x180003a0b  add     rsp, 40h
0x180003a0f  pop     rdi
0x180003a10  retn
```
