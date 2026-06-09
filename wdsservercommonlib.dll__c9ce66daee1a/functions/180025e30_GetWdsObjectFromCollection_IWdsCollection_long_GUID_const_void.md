# GetWdsObjectFromCollection(IWdsCollection *,long,_GUID const &,void * *)

- ea: `0x180025e30`
- end: `0x180025f72`
- name: `?GetWdsObjectFromCollection@@YAJPEAUIWdsCollection@@JAEBU_GUID@@PEAPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct IWdsCollection *, int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063c4`
- `0x180025e30`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180025ef9`
- `KERNEL32!SetLastError` at `0x180025f23`
- `KERNEL32!SetLastError` at `0x180025ef9`
- `KERNEL32!SetLastError` at `0x180025f23`
- `KERNEL32!GetLastError` at `0x180025e6f`
- `KERNEL32!GetLastError` at `0x180025ebe`
- `KERNEL32!GetLastError` at `0x180025f05`
- `KERNEL32!GetLastError` at `0x180025e6f`
- `KERNEL32!GetLastError` at `0x180025ebe`
- `KERNEL32!GetLastError` at `0x180025f05`

## string_xrefs

- `0x180025e8b`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`
- `0x180025ed7`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`

## pseudocode

```c
__int64 __fastcall GetWdsObjectFromCollection(struct IWdsCollection *a1, __int64 a2, const struct _GUID *a3, void **a4)
{
  __int64 v4; // rax
  int v7; // edi
  DWORD LastError; // ebx
  DWORD v9; // ebx
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_QWORD *)a1;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IWdsCollection *, __int64, __int64 *))(v4 + 64))(a1, a2, &v11);
  if ( v7 >= 0 )
  {
    v7 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v11)(v11, a3, a4);
    goto LABEL_11;
  }
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsmgmtutil.cpp",
      609,
      &dword_1800331C4,
      v7);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsmgmtutil.cpp",
      609,
      &dword_1800331C4,
      v7);
    goto LABEL_6;
  }
LABEL_7:
  v9 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v9);
LABEL_11:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180025e30  mov     r11, rsp
0x180025e33  mov     [r11+10h], rbx
0x180025e37  mov     [r11+18h], rsi
0x180025e3b  push    rdi
0x180025e3c  sub     rsp, 40h
0x180025e40  mov     rax, [rcx]
0x180025e43  mov     rsi, r8
0x180025e46  and     qword ptr [r11+8], 0
0x180025e4b  lea     r8, [r11+8]
0x180025e4f  mov     rbx, r9
0x180025e52  mov     rax, [rax+40h]
0x180025e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e5b  mov     edi, eax
0x180025e5d  test    eax, eax
0x180025e5f  jns     loc_180025F31
0x180025e65  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025e6d  jz      short loc_180025EB4
0x180025e6f  call    cs:__imp_GetLastError
0x180025e76  nop     dword ptr [rax+rax+00h]
0x180025e7b  lea     r9, dword_1800331C4
0x180025e82  mov     [rsp+48h+var_20], edi
0x180025e86  mov     [rsp+48h+var_28], r9
0x180025e8b  lea     r8, aOnecoreBaseEco_13; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025e92  mov     ebx, eax
0x180025e94  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180025e9b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025ea2  mov     r9d, 261h
0x180025ea8  mov     ecx, 80000h
0x180025ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eb2  jmp     short loc_180025EF7
0x180025eb4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025ebc  jz      short loc_180025F05
0x180025ebe  call    cs:__imp_GetLastError
0x180025ec5  nop     dword ptr [rax+rax+00h]
0x180025eca  lea     r9, dword_1800331C4
0x180025ed1  mov     dword ptr [rsp+48h+var_28], edi
0x180025ed5  mov     ebx, eax
0x180025ed7  lea     rdx, aOnecoreBaseEco_13; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025ede  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025ee5  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180025eec  mov     r8d, 261h
0x180025ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ef7  mov     ecx, ebx; dwErrCode
0x180025ef9  call    cs:__imp_SetLastError
0x180025f00  nop     dword ptr [rax+rax+00h]
0x180025f05  call    cs:__imp_GetLastError
0x180025f0c  nop     dword ptr [rax+rax+00h]
0x180025f11  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180025f18  mov     ebx, eax
0x180025f1a  jz      short loc_180025F21
0x180025f1c  call    ElTraceErrorInfo
0x180025f21  mov     ecx, ebx; dwErrCode
0x180025f23  call    cs:__imp_SetLastError
0x180025f2a  nop     dword ptr [rax+rax+00h]
0x180025f2f  jmp     short loc_180025F49
0x180025f31  mov     rcx, [rsp+48h+arg_0]
0x180025f36  mov     r8, rbx
0x180025f39  mov     rdx, rsi
0x180025f3c  mov     rax, [rcx]
0x180025f3f  mov     rax, [rax]
0x180025f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f47  mov     edi, eax
0x180025f49  mov     rcx, [rsp+48h+arg_0]
0x180025f4e  test    rcx, rcx
0x180025f51  jz      short loc_180025F5F
0x180025f53  mov     rax, [rcx]
0x180025f56  mov     rax, [rax+10h]
0x180025f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f5f  mov     rbx, [rsp+48h+arg_8]
0x180025f64  mov     eax, edi
0x180025f66  mov     rsi, [rsp+48h+arg_10]
0x180025f6b  add     rsp, 40h
0x180025f6f  pop     rdi
0x180025f70  retn
```
