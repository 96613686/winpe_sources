# LOG_WRITER::AppendFormattedDate(STRU *,_SYSTEMTIME *,ushort const *,ushort const *,int)

- ea: `0x180002808`
- end: `0x180002896`
- name: `?AppendFormattedDate@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@PEBG2H@Z`
- size: `142`
- prototype: `signed int __fastcall(LOG_WRITER *this, struct STRU *, struct _SYSTEMTIME *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005458`

## callees

- `0x180002808`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002852`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180002848`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180002848`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000286e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000287d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000286e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000287d`

## pseudocode

```c
signed int __fastcall LOG_WRITER::AppendFormattedDate(
        LOG_WRITER *this,
        struct STRU *a2,
        struct _SYSTEMTIME *a3,
        const unsigned __int16 *a4)
{
  signed int result; // eax
  WCHAR DateStr[12]; // [rsp+30h] [rbp-28h] BYREF

  memset(DateStr, 0, 22);
  if ( GetDateFormatW(0x400u, 0, a3, a4, DateStr, 11) )
  {
    result = STRU::Append(a2, DateStr);
    if ( result >= 0 )
      return STRU::Append(a2, 0);
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180002808  push    rbx
0x18000280a  sub     rsp, 50h
0x18000280e  mov     rax, cs:__security_cookie
0x180002815  xor     rax, rsp
0x180002818  mov     [rsp+58h+var_10], rax
0x18000281d  xor     eax, eax
0x18000281f  mov     [rsp+58h+cchDate], 0Bh; cchDate
0x180002827  xorps   xmm0, xmm0
0x18000282a  mov     rbx, rdx
0x18000282d  movups  xmmword ptr [rsp+58h+DateStr], xmm0
0x180002832  mov     qword ptr [rsp+58h+DateStr+0Eh], rax
0x180002837  xor     edx, edx; dwFlags
0x180002839  lea     rax, [rsp+58h+DateStr]
0x18000283e  mov     ecx, 400h; Locale
0x180002843  mov     [rsp+58h+lpDateStr], rax; lpDateStr
0x180002848  call    cs:__imp_GetDateFormatW
0x18000284e  test    eax, eax
0x180002850  jnz     short loc_180002866
0x180002852  call    cs:__imp_GetLastError
0x180002858  test    eax, eax
0x18000285a  jle     short loc_180002883
0x18000285c  movzx   eax, ax
0x18000285f  or      eax, 80070000h
0x180002864  jmp     short loc_180002883
0x180002866  lea     rdx, [rsp+58h+DateStr]
0x18000286b  mov     rcx, rbx
0x18000286e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002874  test    eax, eax
0x180002876  js      short loc_180002883
0x180002878  xor     edx, edx
0x18000287a  mov     rcx, rbx
0x18000287d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002883  mov     rcx, [rsp+58h+var_10]
0x180002888  xor     rcx, rsp; StackCookie
0x18000288b  call    __security_check_cookie
0x180002890  add     rsp, 50h
0x180002894  pop     rbx
0x180002895  retn
```
