# CShellPropertyThunk::ConvertDateToString(ATL::COleDateTime &,tagPROPVARIANT *)

- ea: `0x14002e710`
- end: `0x14002e7a0`
- name: `?ConvertDateToString@CShellPropertyThunk@@CAJAEAVCOleDateTime@ATL@@PEAUtagPROPVARIANT@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(struct ATL::COleDateTime *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14002e440`
- `0x140082440`

## callees

- `0x14002e710`
- `0x14002e7a8`
- `0x14002e91c`
- `0x14002e974`
- `0x14002e9cc`
- `0x14003df58`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14002e788`
- `ole32!CoTaskMemFree` at `0x14002e788`
- `ole32!CoTaskMemAlloc` at `0x14002e72c`
- `ole32!CoTaskMemAlloc` at `0x14002e72c`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::ConvertDateToString(struct ATL::COleDateTime *a1, struct tagPROPVARIANT *a2)
{
  LPVOID v4; // rax
  int Day; // edi
  int Month; // ebx
  unsigned int Year; // eax
  int v8; // ebx

  CShellPropertyThunk::AdjustTimeAndDate((bool)a1, a1);
  v4 = CoTaskMemAlloc(0x16u);
  a2->hVal.QuadPart = (LONGLONG)v4;
  if ( v4 )
  {
    Day = ATL::COleDateTime::GetDay(a1);
    Month = ATL::COleDateTime::GetMonth(a1);
    Year = ATL::COleDateTime::GetYear(a1);
    v8 = StringCchPrintfW(a2->bstrVal, 0xBu, L"%04u-%02u-%02u", Year, Month, Day);
    if ( v8 < 0 )
      CoTaskMemFree(a2->puuid);
    else
      a2->vt = 31;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002e710  push    rbx
0x14002e712  push    rbp
0x14002e713  push    rsi
0x14002e714  push    rdi
0x14002e715  sub     rsp, 38h
0x14002e719  mov     rsi, rdx
0x14002e71c  mov     rbp, rcx
0x14002e71f  mov     rdx, rcx; struct ATL::COleDateTime *
0x14002e722  call    ?AdjustTimeAndDate@CShellPropertyThunk@@CAJ_NAEAVCOleDateTime@ATL@@@Z; CShellPropertyThunk::AdjustTimeAndDate(bool,ATL::COleDateTime &)
0x14002e727  mov     ecx, 16h; cb
0x14002e72c  call    cs:__imp_CoTaskMemAlloc
0x14002e732  mov     [rsi+8], rax
0x14002e736  test    rax, rax
0x14002e739  jz      short loc_14002E790
0x14002e73b  mov     rcx, rbp; this
0x14002e73e  call    ?GetDay@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetDay(void)
0x14002e743  mov     rcx, rbp; this
0x14002e746  mov     edi, eax
0x14002e748  call    ?GetMonth@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetMonth(void)
0x14002e74d  mov     rcx, rbp; this
0x14002e750  mov     ebx, eax
0x14002e752  call    ?GetYear@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetYear(void)
0x14002e757  mov     rcx, [rsi+8]; unsigned __int16 *
0x14002e75b  lea     r8, a04u02u02u; "%04u-%02u-%02u"
0x14002e762  mov     r9d, eax
0x14002e765  mov     [rsp+58h+var_30], edi
0x14002e769  mov     edx, 0Bh; unsigned __int64
0x14002e76e  mov     [rsp+58h+var_38], ebx
0x14002e772  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002e777  mov     ebx, eax
0x14002e779  test    eax, eax
0x14002e77b  js      short loc_14002E784
0x14002e77d  mov     word ptr [rsi], 1Fh
0x14002e782  jmp     short loc_14002E795
0x14002e784  mov     rcx, [rsi+8]; pv
0x14002e788  call    cs:__imp_CoTaskMemFree
0x14002e78e  jmp     short loc_14002E795
0x14002e790  mov     ebx, 8007000Eh
0x14002e795  mov     eax, ebx
0x14002e797  add     rsp, 38h
0x14002e79b  pop     rdi
0x14002e79c  pop     rsi
0x14002e79d  pop     rbp
0x14002e79e  pop     rbx
0x14002e79f  retn
```
