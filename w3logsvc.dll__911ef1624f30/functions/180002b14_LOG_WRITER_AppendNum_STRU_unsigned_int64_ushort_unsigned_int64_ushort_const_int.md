# LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)

- ea: `0x180002b14`
- end: `0x180002ba0`
- name: `?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z`
- size: `140`
- prototype: `int __fastcall(LOG_WRITER *this, struct STRU *, unsigned __int64, unsigned __int16 *, size_t BufferCount, const unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002704`
- `0x180002f48`
- `0x180003718`
- `0x180004878`
- `0x180004f24`
- `0x180005458`

## callees

- `0x180002b14`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180002b35`
- `msvcrt!_ui64tow_s` at `0x180002b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b5e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002b78`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002b8f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002b78`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002b8f`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002b56`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002b56`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendNum(
        LOG_WRITER *this,
        struct STRU *a2,
        unsigned __int64 a3,
        unsigned __int16 *a4,
        size_t BufferCount,
        const unsigned __int16 *a6,
        int a7)
{
  int result; // eax

  if ( _ui64tow_s(a3, a4, BufferCount, 10) )
  {
    if ( a7 )
    {
      return STRU::Append(a2, L"- ", 2u);
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    result = STRU::Append(a2, a4);
    if ( result >= 0 && a6 )
      return STRU::Append(a2, a6);
  }
  return result;
}

```

## disassembly

```asm
0x180002b14  mov     [rsp+arg_0], rbx
0x180002b19  push    rdi
0x180002b1a  sub     rsp, 20h
0x180002b1e  mov     rdi, r9
0x180002b21  mov     rcx, r8; Value
0x180002b24  mov     r8, [rsp+28h+BufferCount]; BufferCount
0x180002b29  mov     rbx, rdx
0x180002b2c  mov     rdx, rdi; Buffer
0x180002b2f  mov     r9d, 0Ah; Radix
0x180002b35  call    cs:__imp__ui64tow_s
0x180002b3b  test    eax, eax
0x180002b3d  jz      short loc_180002B72
0x180002b3f  cmp     [rsp+28h+arg_30], 0
0x180002b44  jz      short loc_180002B5E
0x180002b46  mov     r8d, 2
0x180002b4c  lea     rdx, asc_180012130; "- "
0x180002b53  mov     rcx, rbx
0x180002b56  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002b5c  jmp     short loc_180002B95
0x180002b5e  call    cs:__imp_GetLastError
0x180002b64  test    eax, eax
0x180002b66  jle     short loc_180002B95
0x180002b68  movzx   eax, ax
0x180002b6b  or      eax, 80070000h
0x180002b70  jmp     short loc_180002B95
0x180002b72  mov     rdx, rdi
0x180002b75  mov     rcx, rbx
0x180002b78  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002b7e  test    eax, eax
0x180002b80  js      short loc_180002B95
0x180002b82  mov     rdx, [rsp+28h+arg_28]
0x180002b87  test    rdx, rdx
0x180002b8a  jz      short loc_180002B95
0x180002b8c  mov     rcx, rbx
0x180002b8f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002b95  mov     rbx, [rsp+28h+arg_0]
0x180002b9a  add     rsp, 20h
0x180002b9e  pop     rdi
0x180002b9f  retn
```
