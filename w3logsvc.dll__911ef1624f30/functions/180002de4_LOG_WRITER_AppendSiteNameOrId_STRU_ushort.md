# LOG_WRITER::AppendSiteNameOrId(STRU *,ushort *)

- ea: `0x180002de4`
- end: `0x180002eb1`
- name: `?AppendSiteNameOrId@LOG_WRITER@@AEAAJPEAVSTRU@@PEAG@Z`
- size: `205`
- prototype: `errno_t __fastcall(LOG_WRITER *this, struct STRU *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003718`

## callees

- `0x180002d38`
- `0x180002de4`

## import_xrefs

- `msvcrt!_itow_s` at `0x180002e13`
- `msvcrt!_itow_s` at `0x180002e13`
- `msvcrt!_wcsupr_s` at `0x180002e75`
- `msvcrt!_wcsupr_s` at `0x180002e75`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e3c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e4c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e60`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e3c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e4c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e60`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002e2d`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002e2d`

## pseudocode

```c
errno_t __fastcall LOG_WRITER::AppendSiteNameOrId(LOG_WRITER *this, struct STRU *a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  errno_t result; // eax
  unsigned int v7; // edi
  wchar_t *v8; // rsi
  LOG_WRITER *v9; // rcx
  unsigned __int16 v10; // [rsp+20h] [rbp-18h]

  v3 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)(v3 + 8) == 1 )
  {
    if ( _itow_s(*(_DWORD *)(v3 + 32), a3, 0xCu, 10) )
    {
      return STRU::Append(a2, L"- ", 2u);
    }
    else
    {
      result = STRU::Append(a2, L"W3SVC");
      if ( result >= 0 )
      {
        result = STRU::Append(a2, a3);
        if ( result >= 0 )
          return STRU::Append(a2, L" ");
      }
    }
  }
  else
  {
    v7 = *(_DWORD *)(v3 + 96);
    v8 = *(wchar_t **)(v3 + 80);
    result = _wcsupr_s(v8, v7 + 1);
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      return LOG_WRITER::AppendSanitizedStringOrHyphen(v9, a2, v8, v7, v10, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002de4  mov     [rsp+arg_0], rbx
0x180002de9  mov     [rsp+arg_8], rsi
0x180002dee  push    rdi
0x180002def  sub     rsp, 30h
0x180002df3  mov     rax, [rcx+8]
0x180002df7  mov     rdi, r8
0x180002dfa  mov     rbx, rdx
0x180002dfd  cmp     dword ptr [rax+8], 1
0x180002e01  jnz     short loc_180002E68
0x180002e03  mov     ecx, [rax+20h]; Value
0x180002e06  mov     r9d, 0Ah; Radix
0x180002e0c  mov     rdx, rdi; Buffer
0x180002e0f  lea     r8d, [r9+2]; BufferCount
0x180002e13  call    cs:__imp__itow_s
0x180002e19  mov     rcx, rbx
0x180002e1c  test    eax, eax
0x180002e1e  jz      short loc_180002E35
0x180002e20  mov     r8d, 2
0x180002e26  lea     rdx, asc_180012130; "- "
0x180002e2d  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002e33  jmp     short loc_180002EA1
0x180002e35  lea     rdx, aW3svc; "W3SVC"
0x180002e3c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002e42  test    eax, eax
0x180002e44  js      short loc_180002EA1
0x180002e46  mov     rdx, rdi
0x180002e49  mov     rcx, rbx
0x180002e4c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002e52  test    eax, eax
0x180002e54  js      short loc_180002EA1
0x180002e56  lea     rdx, asc_180012138; " "
0x180002e5d  mov     rcx, rbx
0x180002e60  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002e66  jmp     short loc_180002EA1
0x180002e68  mov     edi, [rax+60h]
0x180002e6b  mov     rsi, [rax+50h]
0x180002e6f  mov     rcx, rsi; String
0x180002e72  lea     edx, [rdi+1]; Size
0x180002e75  call    cs:__imp__wcsupr_s
0x180002e7b  test    eax, eax
0x180002e7d  jz      short loc_180002E8B
0x180002e7f  jle     short loc_180002EA1
0x180002e81  movzx   eax, ax
0x180002e84  or      eax, 80070000h
0x180002e89  jmp     short loc_180002EA1
0x180002e8b  mov     r9d, edi; unsigned int
0x180002e8e  mov     [rsp+38h+var_10], 1; int
0x180002e96  mov     r8, rsi; unsigned __int16 *
0x180002e99  mov     rdx, rbx; struct STRU *
0x180002e9c  call    ?AppendSanitizedStringOrHyphen@LOG_WRITER@@AEAAJPEAVSTRU@@PEAGKGH@Z; LOG_WRITER::AppendSanitizedStringOrHyphen(STRU *,ushort *,ulong,ushort,int)
0x180002ea1  mov     rbx, [rsp+38h+arg_0]
0x180002ea6  mov     rsi, [rsp+38h+arg_8]
0x180002eab  add     rsp, 30h
0x180002eaf  pop     rdi
0x180002eb0  retn
```
