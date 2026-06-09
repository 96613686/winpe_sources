# GetWdsTransportObjectFromCollection(IWdsTransportCollection *,ulong,_GUID const &,void * *)

- ea: `0x1800270a0`
- end: `0x1800271e2`
- name: `?GetWdsTransportObjectFromCollection@@YAJPEAUIWdsTransportCollection@@KAEBU_GUID@@PEAPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct IWdsTransportCollection *, unsigned int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006ea4`
- `0x1800270a0`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180027169`
- `KERNEL32!SetLastError` at `0x180027193`
- `KERNEL32!SetLastError` at `0x180027169`
- `KERNEL32!SetLastError` at `0x180027193`
- `KERNEL32!GetLastError` at `0x1800270df`
- `KERNEL32!GetLastError` at `0x18002712e`
- `KERNEL32!GetLastError` at `0x180027175`
- `KERNEL32!GetLastError` at `0x1800270df`
- `KERNEL32!GetLastError` at `0x18002712e`
- `KERNEL32!GetLastError` at `0x180027175`

## string_xrefs

- `0x1800270fb`: `onecore\base\eco\wds\wdslib\common\src\wdstptmgmtutil.cpp`
- `0x180027147`: `onecore\base\eco\wds\wdslib\common\src\wdstptmgmtutil.cpp`

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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdstptmgmtutil.cpp",
      70,
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
0x1800270a0  mov     r11, rsp
0x1800270a3  mov     [r11+10h], rbx
0x1800270a7  mov     [r11+18h], rsi
0x1800270ab  push    rdi
0x1800270ac  sub     rsp, 40h
0x1800270b0  mov     rax, [rcx]
0x1800270b3  mov     rsi, r8
0x1800270b6  and     qword ptr [r11+8], 0
0x1800270bb  lea     r8, [r11+8]
0x1800270bf  mov     rbx, r9
0x1800270c2  mov     rax, [rax+40h]
0x1800270c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270cb  mov     edi, eax
0x1800270cd  test    eax, eax
0x1800270cf  jns     loc_1800271A1
0x1800270d5  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800270dd  jz      short loc_180027124
0x1800270df  call    cs:__imp_GetLastError
0x1800270e6  nop     dword ptr [rax+rax+00h]
0x1800270eb  lea     r9, dword_18003572C
0x1800270f2  mov     [rsp+48h+var_20], edi
0x1800270f6  mov     [rsp+48h+var_28], r9
0x1800270fb  lea     r8, aOnecoreBaseEco_8; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180027102  mov     ebx, eax
0x180027104  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002710b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180027112  mov     r9d, 46h ; 'F'
0x180027118  mov     ecx, 80000h
0x18002711d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027122  jmp     short loc_180027167
0x180027124  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002712c  jz      short loc_180027175
0x18002712e  call    cs:__imp_GetLastError
0x180027135  nop     dword ptr [rax+rax+00h]
0x18002713a  lea     r9, dword_18003572C
0x180027141  mov     dword ptr [rsp+48h+var_28], edi
0x180027145  mov     ebx, eax
0x180027147  lea     rdx, aOnecoreBaseEco_8; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002714e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027155  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002715c  mov     r8d, 46h ; 'F'
0x180027162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027167  mov     ecx, ebx; dwErrCode
0x180027169  call    cs:__imp_SetLastError
0x180027170  nop     dword ptr [rax+rax+00h]
0x180027175  call    cs:__imp_GetLastError
0x18002717c  nop     dword ptr [rax+rax+00h]
0x180027181  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180027188  mov     ebx, eax
0x18002718a  jz      short loc_180027191
0x18002718c  call    ElTraceErrorInfo
0x180027191  mov     ecx, ebx; dwErrCode
0x180027193  call    cs:__imp_SetLastError
0x18002719a  nop     dword ptr [rax+rax+00h]
0x18002719f  jmp     short loc_1800271B9
0x1800271a1  mov     rcx, [rsp+48h+arg_0]
0x1800271a6  mov     r8, rbx
0x1800271a9  mov     rdx, rsi
0x1800271ac  mov     rax, [rcx]
0x1800271af  mov     rax, [rax]
0x1800271b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271b7  mov     edi, eax
0x1800271b9  mov     rcx, [rsp+48h+arg_0]
0x1800271be  test    rcx, rcx
0x1800271c1  jz      short loc_1800271CF
0x1800271c3  mov     rax, [rcx]
0x1800271c6  mov     rax, [rax+10h]
0x1800271ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271cf  mov     rbx, [rsp+48h+arg_8]
0x1800271d4  mov     eax, edi
0x1800271d6  mov     rsi, [rsp+48h+arg_10]
0x1800271db  add     rsp, 40h
0x1800271df  pop     rdi
0x1800271e0  retn
```
