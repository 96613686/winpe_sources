# pSetupCreateTextLogSectionW

- ea: `0x18000fc1c`
- end: `0x18000fcc5`
- name: `pSetupCreateTextLogSectionW`
- size: `169`
- prototype: `_BOOL8 __fastcall(const WCHAR *, __int64, const WCHAR *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800056d0`
- `0x1800126cc`
- `0x180014a84`

## callees

- `0x18000f5a0`
- `0x18000fc1c`
- `0x1800177e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fcb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fcb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcaa`

## pseudocode

```c
_BOOL8 __fastcall pSetupCreateTextLogSectionW(const WCHAR *a1, __int64 a2, const WCHAR *a3, unsigned __int64 *a4)
{
  BOOL TextLogSectionA; // ebp
  char *v5; // rsi
  DWORD LastError; // ebx
  CHAR *v9; // rdi

  TextLogSectionA = 0;
  v5 = 0;
  if ( !a1 || (v5 = (char *)pSetupUnicodeToMultiByte(a1)) != 0 )
  {
    v9 = 0;
    if ( !a3 || (v9 = (CHAR *)pSetupUnicodeToMultiByte(a3)) != 0 )
    {
      LastError = 0;
      TextLogSectionA = pSetupCreateTextLogSectionA(v5, a2, v9, a4);
      if ( !TextLogSectionA )
        LastError = GetLastError();
    }
    else
    {
      LastError = 8;
    }
    if ( v5 )
      HeapFree(hHeap, 0, v5);
    if ( v9 )
      HeapFree(hHeap, 0, v9);
  }
  else
  {
    LastError = 8;
  }
  SetLastError(LastError);
  return TextLogSectionA;
}

```

## disassembly

```asm
0x18000fc1c  push    rbx
0x18000fc1e  push    rbp
0x18000fc1f  push    rsi
0x18000fc20  push    rdi
0x18000fc21  push    r14
0x18000fc23  sub     rsp, 20h
0x18000fc27  xor     ebp, ebp
0x18000fc29  xor     esi, esi
0x18000fc2b  mov     r14, r9
0x18000fc2e  mov     rbx, r8
0x18000fc31  test    rcx, rcx
0x18000fc34  jz      short loc_18000FC48
0x18000fc36  call    pSetupUnicodeToMultiByte
0x18000fc3b  mov     rsi, rax
0x18000fc3e  test    rax, rax
0x18000fc41  jnz     short loc_18000FC48
0x18000fc43  lea     ebx, [rbp+8]
0x18000fc46  jmp     short loc_18000FCB0
0x18000fc48  xor     edi, edi
0x18000fc4a  test    rbx, rbx
0x18000fc4d  jz      short loc_18000FC64
0x18000fc4f  mov     rcx, rbx; lpWideCharStr
0x18000fc52  call    pSetupUnicodeToMultiByte
0x18000fc57  mov     rdi, rax
0x18000fc5a  test    rax, rax
0x18000fc5d  jnz     short loc_18000FC64
0x18000fc5f  lea     ebx, [rax+8]
0x18000fc62  jmp     short loc_18000FC82
0x18000fc64  mov     r9, r14
0x18000fc67  mov     r8, rdi
0x18000fc6a  mov     rcx, rsi
0x18000fc6d  xor     ebx, ebx
0x18000fc6f  call    pSetupCreateTextLogSectionA
0x18000fc74  mov     ebp, eax
0x18000fc76  test    eax, eax
0x18000fc78  jnz     short loc_18000FC82
0x18000fc7a  call    cs:__imp_GetLastError
0x18000fc80  mov     ebx, eax
0x18000fc82  test    rsi, rsi
0x18000fc85  jz      short loc_18000FC99
0x18000fc87  mov     rcx, cs:hHeap; hHeap
0x18000fc8e  mov     r8, rsi; lpMem
0x18000fc91  xor     edx, edx; dwFlags
0x18000fc93  call    cs:__imp_HeapFree
0x18000fc99  test    rdi, rdi
0x18000fc9c  jz      short loc_18000FCB0
0x18000fc9e  mov     rcx, cs:hHeap; hHeap
0x18000fca5  mov     r8, rdi; lpMem
0x18000fca8  xor     edx, edx; dwFlags
0x18000fcaa  call    cs:__imp_HeapFree
0x18000fcb0  mov     ecx, ebx; dwErrCode
0x18000fcb2  call    cs:__imp_SetLastError
0x18000fcb8  mov     eax, ebp
0x18000fcba  add     rsp, 20h
0x18000fcbe  pop     r14
0x18000fcc0  pop     rdi
0x18000fcc1  pop     rsi
0x18000fcc2  pop     rbp
0x18000fcc3  pop     rbx
0x18000fcc4  retn
```
