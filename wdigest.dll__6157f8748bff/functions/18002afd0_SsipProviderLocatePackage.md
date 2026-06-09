# SsipProviderLocatePackage

- ea: `0x18002afd0`
- end: `0x18002b0f7`
- name: `SsipProviderLocatePackage`
- size: `295`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a6f8`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x18001874c`
- `0x18002afd0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002b041`
- `ntdll!RtlCompareUnicodeString` at `0x18002b041`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b0bc`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b0bc`
- `ntdll!RtlEnterCriticalSection` at `0x18002b01e`
- `ntdll!RtlEnterCriticalSection` at `0x18002b01e`

## pseudocode

```c
__int64 __fastcall SsipProviderLocatePackage(PCUNICODE_STRING String1, struct _LIST_ENTRY **a2)
{
  struct _LIST_ENTRY *i; // rbx
  unsigned int v5; // edi
  __int64 v6; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, String1);
  *a2 = 0;
  RtlEnterCriticalSection(&l_SsiCritSect);
  for ( i = l_SsiProviderList.Flink; i != &l_SsiProviderList; i = i->Flink )
  {
    if ( !RtlCompareUnicodeString(String1, (PCUNICODE_STRING)&i[1].Blink, 1u) )
    {
      v5 = 0;
      v6 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&i[1]);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v6);
      *a2 = i;
      goto LABEL_16;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
  v5 = -1073741275;
LABEL_16:
  RtlLeaveCriticalSection(&l_SsiCritSect);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18002afd0  push    rbx
0x18002afd2  push    rbp
0x18002afd3  push    rsi
0x18002afd4  push    rdi
0x18002afd5  sub     rsp, 28h
0x18002afd9  mov     rsi, rdx
0x18002afdc  mov     rdi, rcx
0x18002afdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afe6  lea     rbp, WPP_GLOBAL_Control
0x18002afed  cmp     rcx, rbp
0x18002aff0  jz      short loc_18002B010
0x18002aff2  test    byte ptr [rcx+1Ch], 80h
0x18002aff6  jz      short loc_18002B010
0x18002aff8  mov     rcx, [rcx+10h]
0x18002affc  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b003  mov     edx, 16h
0x18002b008  mov     r9, rdi
0x18002b00b  call    WPP_SF_Z
0x18002b010  lea     rcx, ?l_SsiCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002b017  mov     qword ptr [rsi], 0
0x18002b01e  call    cs:__imp_RtlEnterCriticalSection
0x18002b024  mov     rbx, cs:?l_SsiProviderList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_SsiProviderList
0x18002b02b  lea     rax, ?l_SsiProviderList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_SsiProviderList
0x18002b032  cmp     rbx, rax
0x18002b035  jz      short loc_18002B089
0x18002b037  lea     rdx, [rbx+18h]; String2
0x18002b03b  mov     r8b, 1; CaseInsensitive
0x18002b03e  mov     rcx, rdi; String1
0x18002b041  call    cs:__imp_RtlCompareUnicodeString
0x18002b047  test    eax, eax
0x18002b049  jz      short loc_18002B050
0x18002b04b  mov     rbx, [rbx]
0x18002b04e  jmp     short loc_18002B02B
0x18002b050  xor     edi, edi
0x18002b052  lea     r9d, [rdi+1]
0x18002b056  lock xadd [rbx+10h], r9d
0x18002b05c  inc     r9d
0x18002b05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b066  cmp     rcx, rbp
0x18002b069  jz      short loc_18002B084
0x18002b06b  test    byte ptr [rcx+1Ch], 4
0x18002b06f  jz      short loc_18002B084
0x18002b071  mov     rcx, [rcx+10h]
0x18002b075  lea     edx, [rdi+17h]
0x18002b078  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b07f  call    WPP_SF_d
0x18002b084  mov     [rsi], rbx
0x18002b087  jmp     short loc_18002B0B5
0x18002b089  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b090  cmp     rcx, rbp
0x18002b093  jz      short loc_18002B0B0
0x18002b095  test    byte ptr [rcx+1Ch], 2
0x18002b099  jz      short loc_18002B0B0
0x18002b09b  mov     rcx, [rcx+10h]
0x18002b09f  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b0a6  mov     edx, 18h
0x18002b0ab  call    WPP_SF_
0x18002b0b0  mov     edi, 0C0000225h
0x18002b0b5  lea     rcx, ?l_SsiCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002b0bc  call    cs:__imp_RtlLeaveCriticalSection
0x18002b0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0c9  cmp     rcx, rbp
0x18002b0cc  jz      short loc_18002B0EC
0x18002b0ce  test    byte ptr [rcx+1Ch], 80h
0x18002b0d2  jz      short loc_18002B0EC
0x18002b0d4  mov     rcx, [rcx+10h]
0x18002b0d8  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002b0df  mov     edx, 19h
0x18002b0e4  mov     r9d, edi
0x18002b0e7  call    WPP_SF_d
0x18002b0ec  mov     eax, edi
0x18002b0ee  add     rsp, 28h
0x18002b0f2  pop     rdi
0x18002b0f3  pop     rsi
0x18002b0f4  pop     rbp
0x18002b0f5  pop     rbx
0x18002b0f6  retn
```
