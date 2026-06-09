# ProfNotifEventLog::Push(long,CEventLog::eFmt)

- ea: `0x18000890c`
- end: `0x180008a2f`
- name: `?Push@ProfNotifEventLog@@QEAAJJW4eFmt@CEventLog@@@Z`
- size: `291`
- prototype: `int __high(int, enum CEventLog::eFmt)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180008510`
- `0x180008648`
- `0x1800087a8`

## callees

- `0x180001770`
- `0x1800021f4`
- `0x180003714`
- `0x180003be0`
- `0x18000890c`
- `0x18000c234`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000896e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000896e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008978`

## pseudocode

```c
__int64 __fastcall ProfNotifEventLog::Push(__int64 a1, DWORD a2, int a3)
{
  signed int LastError; // eax
  signed int v7; // ebx
  wchar_t *v8; // rdi
  void *v9; // rdx
  const wchar_t *v10; // r8
  wchar_t *lpBuffer; // [rsp+40h] [rbp-78h] BYREF
  wchar_t v13[40]; // [rsp+50h] [rbp-68h] BYREF

  if ( a3 == 2 )
  {
    lpBuffer = 0;
    if ( FormatMessageW(0x1100u, 0, a2, 0, (LPWSTR)&lpBuffer, 1u, 0) )
    {
      v8 = 0;
      if ( lpBuffer )
        v8 = lpBuffer;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = 0;
      if ( v7 < 0 )
        return (unsigned int)v7;
    }
    v7 = CEventLog::CStrArray::Append((CEventLog::CStrArray *)(a1 + 8), v8);
    ProfNotif_HeapFree(v8, v9);
    return (unsigned int)v7;
  }
  memset_0(v13, 0, sizeof(v13));
  v10 = L"%d";
  if ( a3 )
    v10 = L"0x%08X";
  v7 = StringCchPrintfW(v13, 0x28u, v10, a2);
  if ( v7 >= 0 )
    return (unsigned int)CEventLog::CStrArray::Append((CEventLog::CStrArray *)(a1 + 8), v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000890c  mov     r11, rsp
0x18000890f  mov     [r11+18h], rbx
0x180008913  mov     [r11+20h], rsi
0x180008917  push    rdi
0x180008918  sub     rsp, 0B0h
0x18000891f  mov     rax, cs:__security_cookie
0x180008926  xor     rax, rsp
0x180008929  mov     [rsp+0B8h+var_18], rax
0x180008931  mov     ebx, r8d
0x180008934  mov     edi, edx
0x180008936  mov     rsi, rcx
0x180008939  cmp     r8d, 2
0x18000893d  jnz     short loc_1800089BC
0x18000893f  mov     [rsp+0B8h+Arguments], 0; Arguments
0x180008948  lea     rax, [r11-78h]
0x18000894c  mov     r8d, edx; dwMessageId
0x18000894f  mov     [rsp+0B8h+nSize], 1; nSize
0x180008957  xor     edx, edx; lpSource
0x180008959  mov     [rsp+0B8h+lpBuffer], rax; lpBuffer
0x18000895e  xor     r9d, r9d; dwLanguageId
0x180008961  mov     qword ptr [r11-78h], 0
0x180008969  mov     ecx, 1100h; dwFlags
0x18000896e  call    cs:__imp_FormatMessageW
0x180008974  test    eax, eax
0x180008976  jnz     short loc_180008995
0x180008978  call    cs:__imp_GetLastError
0x18000897e  mov     ebx, eax
0x180008980  test    eax, eax
0x180008982  jle     short loc_18000898D
0x180008984  movzx   ebx, ax
0x180008987  or      ebx, 80070000h
0x18000898d  xor     edi, edi
0x18000898f  test    ebx, ebx
0x180008991  jns     short loc_1800089A4
0x180008993  jmp     short loc_180008A08
0x180008995  mov     rax, [rsp+0B8h+var_78]
0x18000899a  xor     edi, edi
0x18000899c  test    rax, rax
0x18000899f  jz      short loc_1800089A4
0x1800089a1  mov     rdi, rax
0x1800089a4  lea     rcx, [rsi+8]; this
0x1800089a8  mov     rdx, rdi; wchar_t *
0x1800089ab  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x1800089b0  mov     rcx, rdi; lpMem
0x1800089b3  mov     ebx, eax
0x1800089b5  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x1800089ba  jmp     short loc_180008A08
0x1800089bc  xor     edx, edx; Val
0x1800089be  lea     rcx, [rsp+0B8h+var_68]; void *
0x1800089c3  lea     r8d, [rdx+50h]; Size
0x1800089c7  call    memset_0
0x1800089cc  lea     rax, a0x08x; "0x%08X"
0x1800089d3  test    ebx, ebx
0x1800089d5  lea     r8, aD; "%d"
0x1800089dc  mov     r9d, edi
0x1800089df  cmovnz  r8, rax; wchar_t *
0x1800089e3  lea     rcx, [rsp+0B8h+var_68]; wchar_t *
0x1800089e8  mov     edx, 28h ; '('; unsigned __int64
0x1800089ed  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800089f2  mov     ebx, eax
0x1800089f4  test    eax, eax
0x1800089f6  js      short loc_180008A08
0x1800089f8  lea     rcx, [rsi+8]; this
0x1800089fc  lea     rdx, [rsp+0B8h+var_68]; wchar_t *
0x180008a01  call    ?Append@CStrArray@CEventLog@@QEAAJPEB_W@Z; CEventLog::CStrArray::Append(wchar_t const *)
0x180008a06  mov     ebx, eax
0x180008a08  mov     eax, ebx
0x180008a0a  mov     rcx, [rsp+0B8h+var_18]
0x180008a12  xor     rcx, rsp; StackCookie
0x180008a15  call    __security_check_cookie
0x180008a1a  lea     r11, [rsp+0B8h+var_8]
0x180008a22  mov     rbx, [r11+20h]
0x180008a26  mov     rsi, [r11+28h]
0x180008a2a  mov     rsp, r11
0x180008a2d  pop     rdi
0x180008a2e  retn
```
