# AllocateExpand

- ea: `0x180009748`
- end: `0x1800097d8`
- name: `AllocateExpand`
- size: `144`
- prototype: `WCHAR *()`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180005080`

## callees

- `0x180009748`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009782`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009782`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009771`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009771`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800097bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800097bc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009760`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000979d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009760`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000979d`

## string_xrefs

- `0x180009755`: `%systemroot%\system32\LogFiles\setupcln`
- `0x180009793`: `%systemroot%\system32\LogFiles\setupcln`

## pseudocode

```c
WCHAR *AllocateExpand()
{
  WCHAR *v0; // rbx
  DWORD v1; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *v3; // rax
  HANDLE v4; // rax

  v0 = 0;
  v1 = ExpandEnvironmentStringsW(L"%systemroot%\\system32\\LogFiles\\setupcln", 0, 0);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    v3 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * v1);
    v0 = v3;
    if ( v3 )
    {
      if ( !ExpandEnvironmentStringsW(L"%systemroot%\\system32\\LogFiles\\setupcln", v3, v1) || !*v0 )
      {
        v4 = GetProcessHeap();
        if ( HeapFree(v4, 0, v0) )
          return 0;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180009748  mov     [rsp+arg_0], rbx
0x18000974d  push    rdi
0x18000974e  sub     rsp, 20h
0x180009752  xor     r8d, r8d; nSize
0x180009755  lea     rcx, Src; "%systemroot%\\system32\\LogFiles\\setup"...
0x18000975c  xor     edx, edx; lpDst
0x18000975e  xor     ebx, ebx
0x180009760  call    cs:__imp_ExpandEnvironmentStringsW
0x180009766  mov     edi, eax
0x180009768  test    eax, eax
0x18000976a  jz      short loc_1800097CA
0x18000976c  mov     ebx, edi
0x18000976e  add     rbx, rbx
0x180009771  call    cs:__imp_GetProcessHeap
0x180009777  mov     r8, rbx; dwBytes
0x18000977a  mov     edx, 8; dwFlags
0x18000977f  mov     rcx, rax; hHeap
0x180009782  call    cs:__imp_HeapAlloc
0x180009788  mov     rbx, rax
0x18000978b  test    rax, rax
0x18000978e  jz      short loc_1800097CA
0x180009790  mov     r8d, edi; nSize
0x180009793  lea     rcx, Src; "%systemroot%\\system32\\LogFiles\\setup"...
0x18000979a  mov     rdx, rax; lpDst
0x18000979d  call    cs:__imp_ExpandEnvironmentStringsW
0x1800097a3  test    eax, eax
0x1800097a5  jz      short loc_1800097AE
0x1800097a7  xor     ecx, ecx
0x1800097a9  cmp     cx, [rbx]
0x1800097ac  jnz     short loc_1800097CA
0x1800097ae  call    cs:__imp_GetProcessHeap
0x1800097b4  mov     r8, rbx; lpMem
0x1800097b7  xor     edx, edx; dwFlags
0x1800097b9  mov     rcx, rax; hHeap
0x1800097bc  call    cs:__imp_HeapFree
0x1800097c2  xor     ecx, ecx
0x1800097c4  test    eax, eax
0x1800097c6  cmovnz  rbx, rcx
0x1800097ca  mov     rax, rbx
0x1800097cd  mov     rbx, [rsp+28h+arg_0]
0x1800097d2  add     rsp, 20h
0x1800097d6  pop     rdi
0x1800097d7  retn
```
