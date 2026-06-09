# CShellPropertyThunk::ConvertDateTimeToString(ATL::COleDateTime &,tagPROPVARIANT *)

- ea: `0x140080e9c`
- end: `0x140080f69`
- name: `?ConvertDateTimeToString@CShellPropertyThunk@@CAJAEAVCOleDateTime@ATL@@PEAUtagPROPVARIANT@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(struct ATL::COleDateTime *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140082440`

## callees

- `0x14002e7a8`
- `0x14002e91c`
- `0x14002e974`
- `0x14002e9cc`
- `0x14003df58`
- `0x140080e9c`
- `0x140081c20`
- `0x140081d74`
- `0x140081e1c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140080f4b`
- `ole32!CoTaskMemFree` at `0x140080f4b`
- `ole32!CoTaskMemAlloc` at `0x140080ebe`
- `ole32!CoTaskMemAlloc` at `0x140080ebe`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::ConvertDateTimeToString(
        struct ATL::COleDateTime *a1,
        struct tagPROPVARIANT *a2)
{
  LPVOID v4; // rax
  int Second; // r14d
  int Minute; // ebp
  int Hour; // esi
  int Day; // edi
  int Month; // ebx
  unsigned int Year; // eax
  int v11; // ebx

  CShellPropertyThunk::AdjustTimeAndDate((bool)a1, a1);
  v4 = CoTaskMemAlloc(0x28u);
  a2->hVal.QuadPart = (LONGLONG)v4;
  if ( v4 )
  {
    Second = ATL::COleDateTime::GetSecond(a1);
    Minute = ATL::COleDateTime::GetMinute(a1);
    Hour = ATL::COleDateTime::GetHour(a1);
    Day = ATL::COleDateTime::GetDay(a1);
    Month = ATL::COleDateTime::GetMonth(a1);
    Year = ATL::COleDateTime::GetYear(a1);
    v11 = StringCchPrintfW(a2->bstrVal, 0x14u, L"%04u-%02u-%02uT%02u:%02u:%02u", Year, Month, Day, Hour, Minute, Second);
    if ( v11 < 0 )
      CoTaskMemFree(a2->puuid);
    else
      a2->vt = 31;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140080e9c  push    rbx
0x140080e9e  push    rbp
0x140080e9f  push    rsi
0x140080ea0  push    rdi
0x140080ea1  push    r12
0x140080ea3  push    r14
0x140080ea5  push    r15
0x140080ea7  sub     rsp, 50h
0x140080eab  mov     r15, rdx
0x140080eae  mov     r12, rcx
0x140080eb1  mov     rdx, rcx; struct ATL::COleDateTime *
0x140080eb4  call    ?AdjustTimeAndDate@CShellPropertyThunk@@CAJ_NAEAVCOleDateTime@ATL@@@Z; CShellPropertyThunk::AdjustTimeAndDate(bool,ATL::COleDateTime &)
0x140080eb9  mov     ecx, 28h ; '('; cb
0x140080ebe  call    cs:__imp_CoTaskMemAlloc
0x140080ec4  mov     [r15+8], rax
0x140080ec8  test    rax, rax
0x140080ecb  jz      loc_140080F53
0x140080ed1  mov     rcx, r12; this
0x140080ed4  call    ?GetSecond@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetSecond(void)
0x140080ed9  mov     rcx, r12; this
0x140080edc  mov     r14d, eax
0x140080edf  call    ?GetMinute@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetMinute(void)
0x140080ee4  mov     rcx, r12; this
0x140080ee7  mov     ebp, eax
0x140080ee9  call    ?GetHour@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetHour(void)
0x140080eee  mov     rcx, r12; this
0x140080ef1  mov     esi, eax
0x140080ef3  call    ?GetDay@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetDay(void)
0x140080ef8  mov     rcx, r12; this
0x140080efb  mov     edi, eax
0x140080efd  call    ?GetMonth@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetMonth(void)
0x140080f02  mov     rcx, r12; this
0x140080f05  mov     ebx, eax
0x140080f07  call    ?GetYear@COleDateTime@ATL@@QEBAHXZ; ATL::COleDateTime::GetYear(void)
0x140080f0c  mov     rcx, [r15+8]; unsigned __int16 *
0x140080f10  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u"
0x140080f17  mov     [rsp+88h+var_48], r14d
0x140080f1c  mov     r9d, eax
0x140080f1f  mov     [rsp+88h+var_50], ebp
0x140080f23  mov     edx, 14h; unsigned __int64
0x140080f28  mov     [rsp+88h+var_58], esi
0x140080f2c  mov     [rsp+88h+var_60], edi
0x140080f30  mov     [rsp+88h+var_68], ebx
0x140080f34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140080f39  mov     ebx, eax
0x140080f3b  test    eax, eax
0x140080f3d  js      short loc_140080F47
0x140080f3f  mov     word ptr [r15], 1Fh
0x140080f45  jmp     short loc_140080F58
0x140080f47  mov     rcx, [r15+8]; pv
0x140080f4b  call    cs:__imp_CoTaskMemFree
0x140080f51  jmp     short loc_140080F58
0x140080f53  mov     ebx, 8007000Eh
0x140080f58  mov     eax, ebx
0x140080f5a  add     rsp, 50h
0x140080f5e  pop     r15
0x140080f60  pop     r14
0x140080f62  pop     r12
0x140080f64  pop     rdi
0x140080f65  pop     rsi
0x140080f66  pop     rbp
0x140080f67  pop     rbx
0x140080f68  retn
```
