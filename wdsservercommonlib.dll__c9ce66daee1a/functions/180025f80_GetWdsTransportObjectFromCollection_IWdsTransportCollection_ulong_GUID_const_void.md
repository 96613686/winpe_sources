# GetWdsTransportObjectFromCollection(IWdsTransportCollection *,ulong,_GUID const &,void * *)

- ea: `0x180025f80`
- end: `0x1800260c2`
- name: `?GetWdsTransportObjectFromCollection@@YAJPEAUIWdsTransportCollection@@KAEBU_GUID@@PEAPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct IWdsTransportCollection *, unsigned int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063c4`
- `0x180025f80`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180026049`
- `KERNEL32!SetLastError` at `0x180026073`
- `KERNEL32!SetLastError` at `0x180026049`
- `KERNEL32!SetLastError` at `0x180026073`
- `KERNEL32!GetLastError` at `0x180025fbf`
- `KERNEL32!GetLastError` at `0x18002600e`
- `KERNEL32!GetLastError` at `0x180026055`
- `KERNEL32!GetLastError` at `0x180025fbf`
- `KERNEL32!GetLastError` at `0x18002600e`
- `KERNEL32!GetLastError` at `0x180026055`

## string_xrefs

- `0x180025fdb`: `onecore\base\eco\wds\wdslib\common\src\wdstptmgmtutil.cpp`
- `0x180026027`: `onecore\base\eco\wds\wdslib\common\src\wdstptmgmtutil.cpp`

## pseudocode

```c
__int64 __fastcall GetWdsTransportObjectFromCollection(
        struct IWdsTransportCollection *a1,
        __int64 a2,
        const struct _GUID *a3,
        void **a4)
{
  struct IWdsTransportCollectionVtbl *lpVtbl; // rax
  int v7; // edi
  DWORD LastError; // ebx
  DWORD v9; // ebx
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  v11 = 0;
  v7 = ((__int64 (__fastcall *)(struct IWdsTransportCollection *, __int64, __int64 *))lpVtbl->get_Item)(a1, a2, &v11);
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdstptmgmtutil.cpp",
      70,
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdstptmgmtutil.cpp",
      70,
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
0x180025f80  mov     r11, rsp
0x180025f83  mov     [r11+10h], rbx
0x180025f87  mov     [r11+18h], rsi
0x180025f8b  push    rdi
0x180025f8c  sub     rsp, 40h
0x180025f90  mov     rax, [rcx]
0x180025f93  mov     rsi, r8
0x180025f96  and     qword ptr [r11+8], 0
0x180025f9b  lea     r8, [r11+8]
0x180025f9f  mov     rbx, r9
0x180025fa2  mov     rax, [rax+40h]
0x180025fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fab  mov     edi, eax
0x180025fad  test    eax, eax
0x180025faf  jns     loc_180026081
0x180025fb5  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025fbd  jz      short loc_180026004
0x180025fbf  call    cs:__imp_GetLastError
0x180025fc6  nop     dword ptr [rax+rax+00h]
0x180025fcb  lea     r9, dword_1800331C4
0x180025fd2  mov     [rsp+48h+var_20], edi
0x180025fd6  mov     [rsp+48h+var_28], r9
0x180025fdb  lea     r8, aOnecoreBaseEco_8; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025fe2  mov     ebx, eax
0x180025fe4  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180025feb  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025ff2  mov     r9d, 46h ; 'F'
0x180025ff8  mov     ecx, 80000h
0x180025ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026002  jmp     short loc_180026047
0x180026004  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002600c  jz      short loc_180026055
0x18002600e  call    cs:__imp_GetLastError
0x180026015  nop     dword ptr [rax+rax+00h]
0x18002601a  lea     r9, dword_1800331C4
0x180026021  mov     dword ptr [rsp+48h+var_28], edi
0x180026025  mov     ebx, eax
0x180026027  lea     rdx, aOnecoreBaseEco_8; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002602e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180026035  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002603c  mov     r8d, 46h ; 'F'
0x180026042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026047  mov     ecx, ebx; dwErrCode
0x180026049  call    cs:__imp_SetLastError
0x180026050  nop     dword ptr [rax+rax+00h]
0x180026055  call    cs:__imp_GetLastError
0x18002605c  nop     dword ptr [rax+rax+00h]
0x180026061  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180026068  mov     ebx, eax
0x18002606a  jz      short loc_180026071
0x18002606c  call    ElTraceErrorInfo
0x180026071  mov     ecx, ebx; dwErrCode
0x180026073  call    cs:__imp_SetLastError
0x18002607a  nop     dword ptr [rax+rax+00h]
0x18002607f  jmp     short loc_180026099
0x180026081  mov     rcx, [rsp+48h+arg_0]
0x180026086  mov     r8, rbx
0x180026089  mov     rdx, rsi
0x18002608c  mov     rax, [rcx]
0x18002608f  mov     rax, [rax]
0x180026092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026097  mov     edi, eax
0x180026099  mov     rcx, [rsp+48h+arg_0]
0x18002609e  test    rcx, rcx
0x1800260a1  jz      short loc_1800260AF
0x1800260a3  mov     rax, [rcx]
0x1800260a6  mov     rax, [rax+10h]
0x1800260aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260af  mov     rbx, [rsp+48h+arg_8]
0x1800260b4  mov     eax, edi
0x1800260b6  mov     rsi, [rsp+48h+arg_10]
0x1800260bb  add     rsp, 40h
0x1800260bf  pop     rdi
0x1800260c0  retn
```
