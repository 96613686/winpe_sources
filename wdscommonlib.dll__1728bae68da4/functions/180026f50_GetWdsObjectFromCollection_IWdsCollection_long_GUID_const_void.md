# GetWdsObjectFromCollection(IWdsCollection *,long,_GUID const &,void * *)

- ea: `0x180026f50`
- end: `0x180027092`
- name: `?GetWdsObjectFromCollection@@YAJPEAUIWdsCollection@@JAEBU_GUID@@PEAPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct IWdsCollection *, int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006ea4`
- `0x180026f50`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180027019`
- `KERNEL32!SetLastError` at `0x180027043`
- `KERNEL32!SetLastError` at `0x180027019`
- `KERNEL32!SetLastError` at `0x180027043`
- `KERNEL32!GetLastError` at `0x180026f8f`
- `KERNEL32!GetLastError` at `0x180026fde`
- `KERNEL32!GetLastError` at `0x180027025`
- `KERNEL32!GetLastError` at `0x180026f8f`
- `KERNEL32!GetLastError` at `0x180026fde`
- `KERNEL32!GetLastError` at `0x180027025`

## string_xrefs

- `0x180026fab`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`
- `0x180026ff7`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`

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
      &dword_18003572C,
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
      &dword_18003572C,
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
0x180026f50  mov     r11, rsp
0x180026f53  mov     [r11+10h], rbx
0x180026f57  mov     [r11+18h], rsi
0x180026f5b  push    rdi
0x180026f5c  sub     rsp, 40h
0x180026f60  mov     rax, [rcx]
0x180026f63  mov     rsi, r8
0x180026f66  and     qword ptr [r11+8], 0
0x180026f6b  lea     r8, [r11+8]
0x180026f6f  mov     rbx, r9
0x180026f72  mov     rax, [rax+40h]
0x180026f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f7b  mov     edi, eax
0x180026f7d  test    eax, eax
0x180026f7f  jns     loc_180027051
0x180026f85  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180026f8d  jz      short loc_180026FD4
0x180026f8f  call    cs:__imp_GetLastError
0x180026f96  nop     dword ptr [rax+rax+00h]
0x180026f9b  lea     r9, dword_18003572C
0x180026fa2  mov     [rsp+48h+var_20], edi
0x180026fa6  mov     [rsp+48h+var_28], r9
0x180026fab  lea     r8, aOnecoreBaseEco_12; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180026fb2  mov     ebx, eax
0x180026fb4  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180026fbb  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180026fc2  mov     r9d, 261h
0x180026fc8  mov     ecx, 80000h
0x180026fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fd2  jmp     short loc_180027017
0x180026fd4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180026fdc  jz      short loc_180027025
0x180026fde  call    cs:__imp_GetLastError
0x180026fe5  nop     dword ptr [rax+rax+00h]
0x180026fea  lea     r9, dword_18003572C
0x180026ff1  mov     dword ptr [rsp+48h+var_28], edi
0x180026ff5  mov     ebx, eax
0x180026ff7  lea     rdx, aOnecoreBaseEco_12; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180026ffe  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027005  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002700c  mov     r8d, 261h
0x180027012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027017  mov     ecx, ebx; dwErrCode
0x180027019  call    cs:__imp_SetLastError
0x180027020  nop     dword ptr [rax+rax+00h]
0x180027025  call    cs:__imp_GetLastError
0x18002702c  nop     dword ptr [rax+rax+00h]
0x180027031  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180027038  mov     ebx, eax
0x18002703a  jz      short loc_180027041
0x18002703c  call    ElTraceErrorInfo
0x180027041  mov     ecx, ebx; dwErrCode
0x180027043  call    cs:__imp_SetLastError
0x18002704a  nop     dword ptr [rax+rax+00h]
0x18002704f  jmp     short loc_180027069
0x180027051  mov     rcx, [rsp+48h+arg_0]
0x180027056  mov     r8, rbx
0x180027059  mov     rdx, rsi
0x18002705c  mov     rax, [rcx]
0x18002705f  mov     rax, [rax]
0x180027062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027067  mov     edi, eax
0x180027069  mov     rcx, [rsp+48h+arg_0]
0x18002706e  test    rcx, rcx
0x180027071  jz      short loc_18002707F
0x180027073  mov     rax, [rcx]
0x180027076  mov     rax, [rax+10h]
0x18002707a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002707f  mov     rbx, [rsp+48h+arg_8]
0x180027084  mov     eax, edi
0x180027086  mov     rsi, [rsp+48h+arg_10]
0x18002708b  add     rsp, 40h
0x18002708f  pop     rdi
0x180027090  retn
```
