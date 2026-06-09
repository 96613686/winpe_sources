# CreateTransRecord

- ea: `0x14001bc90`
- end: `0x14001bd3a`
- name: `CreateTransRecord`
- size: `170`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001d818`

## callees

- `0x14001bc90`
- `0x1400400d6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001bce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001bce6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001bcf6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001bcf6`
- `ntdll!RtlEnterCriticalSection` at `0x14001bc9f`
- `ntdll!RtlEnterCriticalSection` at `0x14001bc9f`
- `ntdll!RtlLeaveCriticalSection` at `0x14001bcdb`
- `ntdll!RtlLeaveCriticalSection` at `0x14001bcdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001bd07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001bd07`

## pseudocode

```c
_QWORD *CreateTransRecord()
{
  _QWORD *v0; // rbx
  _QWORD *v1; // rax
  _QWORD *v2; // rcx
  LPVOID *v3; // rdx
  HANDLE ProcessHeap; // rax

  v0 = 0;
  RtlEnterCriticalSection(&TLCritSect);
  v1 = qword_140082248;
  if ( qword_140082248 != &qword_140082248 )
  {
    v2 = *(_QWORD **)qword_140082248;
    if ( *(LPVOID *)(*(_QWORD *)qword_140082248 + 8LL) != qword_140082248
      || (v3 = (LPVOID *)*((_QWORD *)qword_140082248 + 1), *v3 != qword_140082248) )
    {
      __fastfail(3u);
    }
    *v3 = v2;
    v0 = v1;
    v2[1] = v3;
  }
  RtlLeaveCriticalSection(&TLCritSect);
  if ( v0 || (ProcessHeap = GetProcessHeap(), (v0 = HeapAlloc(ProcessHeap, 8u, 0x48u)) != 0) )
  {
    memset_0(v0, 0, 0x48u);
    v0[3] = v0 + 2;
    v0[2] = v0 + 2;
    return v0;
  }
  else
  {
    SetLastError(0xEu);
    return 0;
  }
}

```

## disassembly

```asm
0x14001bc90  push    rbx
0x14001bc92  sub     rsp, 20h
0x14001bc96  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001bc9d  xor     ebx, ebx
0x14001bc9f  call    cs:__imp_RtlEnterCriticalSection
0x14001bca5  mov     rax, cs:qword_140082248
0x14001bcac  lea     rcx, qword_140082248
0x14001bcb3  cmp     rax, rcx
0x14001bcb6  jz      short loc_14001BCD4
0x14001bcb8  mov     rcx, [rax]
0x14001bcbb  cmp     [rcx+8], rax
0x14001bcbf  jnz     short loc_14001BD11
0x14001bcc1  mov     rdx, [rax+8]
0x14001bcc5  cmp     [rdx], rax
0x14001bcc8  jnz     short loc_14001BD11
0x14001bcca  mov     [rdx], rcx
0x14001bccd  mov     rbx, rax
0x14001bcd0  mov     [rcx+8], rdx
0x14001bcd4  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001bcdb  call    cs:__imp_RtlLeaveCriticalSection
0x14001bce1  test    rbx, rbx
0x14001bce4  jnz     short loc_14001BD18
0x14001bce6  call    cs:__imp_GetProcessHeap
0x14001bcec  mov     rcx, rax; hHeap
0x14001bcef  lea     edx, [rbx+8]; dwFlags
0x14001bcf2  lea     r8d, [rbx+48h]; dwBytes
0x14001bcf6  call    cs:__imp_HeapAlloc
0x14001bcfc  mov     rbx, rax
0x14001bcff  test    rax, rax
0x14001bd02  jnz     short loc_14001BD18
0x14001bd04  lea     ecx, [rax+0Eh]; dwErrCode
0x14001bd07  call    cs:__imp_SetLastError
0x14001bd0d  xor     eax, eax
0x14001bd0f  jmp     short loc_14001BD34
0x14001bd11  mov     ecx, 3
0x14001bd16  int     29h; Win8: RtlFailFast(ecx)
0x14001bd18  xor     edx, edx; Val
0x14001bd1a  mov     rcx, rbx; void *
0x14001bd1d  lea     r8d, [rdx+48h]; Size
0x14001bd21  call    memset_0
0x14001bd26  lea     rax, [rbx+10h]
0x14001bd2a  mov     [rax+8], rax
0x14001bd2e  mov     [rax], rax
0x14001bd31  mov     rax, rbx
0x14001bd34  add     rsp, 20h
0x14001bd38  pop     rbx
0x14001bd39  retn
```
