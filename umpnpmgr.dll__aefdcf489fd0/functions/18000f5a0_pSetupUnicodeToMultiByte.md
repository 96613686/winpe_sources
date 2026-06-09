# pSetupUnicodeToMultiByte

- ea: `0x18000f5a0`
- end: `0x18000f641`
- name: `pSetupUnicodeToMultiByte`
- size: `161`
- prototype: `CHAR *__fastcall(LPCWCH lpWideCharStr)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000fc1c`
- `0x1800177e0`

## callees

- `0x18000f5a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f5fe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f5fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f614`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f614`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000f628`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000f628`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f5d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f5d1`

## pseudocode

```c
CHAR *__fastcall pSetupUnicodeToMultiByte(LPCWCH lpWideCharStr)
{
  __int64 v2; // rax
  int v4; // esi
  CHAR *lpMultiByteStr; // rdi
  unsigned int v6; // eax
  LPVOID v8; // rax

  v2 = -1;
  while ( lpWideCharStr[++v2] != 0 )
    ;
  v4 = v2 + 1;
  lpMultiByteStr = (CHAR *)HeapAlloc(hHeap, 0, (unsigned int)(2 * (v2 + 1)));
  if ( !lpMultiByteStr )
    return 0;
  v6 = WideCharToMultiByte(0, 0, lpWideCharStr, v4, lpMultiByteStr, 2 * v4, 0, 0);
  if ( !v6 )
  {
    HeapFree(hHeap, 0, lpMultiByteStr);
    return 0;
  }
  v8 = HeapReAlloc(hHeap, 0, lpMultiByteStr, v6);
  if ( v8 )
    return (CHAR *)v8;
  return lpMultiByteStr;
}

```

## disassembly

```asm
0x18000f5a0  push    rbx
0x18000f5a2  push    rbp
0x18000f5a3  push    rsi
0x18000f5a4  push    rdi
0x18000f5a5  sub     rsp, 48h
0x18000f5a9  mov     rbx, rcx
0x18000f5ac  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f5b3  cmp     word ptr [rcx+rax*2+2], 0
0x18000f5b9  lea     rax, [rax+1]
0x18000f5bd  jnz     short loc_18000F5B3
0x18000f5bf  mov     rcx, cs:hHeap; hHeap
0x18000f5c6  lea     esi, [rax+1]
0x18000f5c9  lea     ebp, [rsi+rsi]
0x18000f5cc  xor     edx, edx; dwFlags
0x18000f5ce  mov     r8d, ebp; dwBytes
0x18000f5d1  call    cs:__imp_HeapAlloc
0x18000f5d7  mov     rdi, rax
0x18000f5da  test    rax, rax
0x18000f5dd  jz      short loc_18000F61A
0x18000f5df  xor     eax, eax
0x18000f5e1  mov     r9d, esi; cchWideChar
0x18000f5e4  mov     [rsp+68h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18000f5e9  mov     r8, rbx; lpWideCharStr
0x18000f5ec  mov     [rsp+68h+lpDefaultChar], rax; lpDefaultChar
0x18000f5f1  xor     edx, edx; dwFlags
0x18000f5f3  mov     [rsp+68h+cbMultiByte], ebp; cbMultiByte
0x18000f5f7  xor     ecx, ecx; CodePage
0x18000f5f9  mov     [rsp+68h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000f5fe  call    cs:__imp_WideCharToMultiByte
0x18000f604  mov     rcx, cs:hHeap; hHeap
0x18000f60b  xor     edx, edx; dwFlags
0x18000f60d  mov     r8, rdi; lpMem
0x18000f610  test    eax, eax
0x18000f612  jnz     short loc_18000F625
0x18000f614  call    cs:__imp_HeapFree
0x18000f61a  xor     eax, eax
0x18000f61c  add     rsp, 48h
0x18000f620  pop     rdi
0x18000f621  pop     rsi
0x18000f622  pop     rbp
0x18000f623  pop     rbx
0x18000f624  retn
0x18000f625  mov     r9d, eax; dwBytes
0x18000f628  call    cs:__imp_HeapReAlloc
0x18000f62e  test    rax, rax
0x18000f631  cmovnz  rdi, rax
0x18000f635  mov     rax, rdi
0x18000f638  add     rsp, 48h
0x18000f63c  pop     rdi
0x18000f63d  pop     rsi
0x18000f63e  pop     rbp
0x18000f63f  pop     rbx
0x18000f640  retn
```
