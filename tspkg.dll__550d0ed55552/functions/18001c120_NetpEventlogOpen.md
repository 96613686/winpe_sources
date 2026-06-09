# NetpEventlogOpen

- ea: `0x18001c120`
- end: `0x18001c1b4`
- name: `NetpEventlogOpen`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b810`

## callees

- `0x18000c174`
- `0x18001c120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001c169`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001c169`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c153`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1a2`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *NetpEventlogOpen()
{
  __int64 v0; // rax
  rsize_t v1; // rsi
  struct _RTL_CRITICAL_SECTION *result; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdi

  v0 = -1;
  do
    ++v0;
  while ( TSGlobalEventSourceName[v0] );
  v1 = v0 + 1;
  result = (struct _RTL_CRITICAL_SECTION *)LocalAlloc(0, 2 * (v0 + 1) + 72);
  v3 = result;
  if ( result )
  {
    InitializeCriticalSection(result);
    *(_QWORD *)&v3[1].LockCount = v3 + 1;
    v3[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v3[1];
    LODWORD(v3[1].OwningThread) = 3600000;
    wcscpy_s((wchar_t *)&v3[1].SpinCount, v1, TSGlobalEventSourceName);
    v3[1].LockSemaphore = &v3[1].SpinCount;
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18001c120  mov     [rsp+hMem], rcx
0x18001c125  push    rbx
0x18001c126  push    rsi
0x18001c127  push    rdi
0x18001c128  push    r14
0x18001c12a  sub     rsp, 28h
0x18001c12e  lea     r14, ?TSGlobalEventSourceName@@3PAGA; "LsaSrv"
0x18001c135  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c139  xor     ebx, ebx
0x18001c13b  inc     rax
0x18001c13e  cmp     [r14+rax*2], bx
0x18001c143  jnz     short loc_18001C13B
0x18001c145  lea     rsi, [rax+1]
0x18001c149  lea     rdx, ds:48h[rsi*2]; uBytes
0x18001c151  xor     ecx, ecx; uFlags
0x18001c153  call    cs:__imp_LocalAlloc
0x18001c159  mov     rdi, rax
0x18001c15c  mov     [rsp+48h+hMem], rax
0x18001c161  test    rax, rax
0x18001c164  jz      short loc_18001C1AA
0x18001c166  mov     rcx, rdi; lpCriticalSection
0x18001c169  call    cs:__imp_InitializeCriticalSection
0x18001c16f  nop
0x18001c170  lea     rax, [rdi+28h]
0x18001c174  mov     [rax+8], rax
0x18001c178  mov     [rax], rax
0x18001c17b  mov     dword ptr [rdi+38h], 36EE80h
0x18001c182  lea     rbx, [rdi+48h]
0x18001c186  mov     r8, r14; Source
0x18001c189  mov     rdx, rsi; SizeInWords
0x18001c18c  mov     rcx, rbx; Destination
0x18001c18f  call    wcscpy_s
0x18001c194  mov     [rdi+40h], rbx
0x18001c198  mov     rax, rdi
0x18001c19b  jmp     short loc_18001C1AA
0x18001c19d  mov     rcx, [rsp+48h+hMem]; hMem
0x18001c1a2  call    cs:__imp_LocalFree
0x18001c1a8  xor     eax, eax
0x18001c1aa  add     rsp, 28h
0x18001c1ae  pop     r14
0x18001c1b0  pop     rdi
0x18001c1b1  pop     rsi
0x18001c1b2  pop     rbx
0x18001c1b3  retn
```
