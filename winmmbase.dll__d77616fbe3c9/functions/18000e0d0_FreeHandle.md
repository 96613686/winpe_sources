# FreeHandle

- ea: `0x18000e0d0`
- end: `0x18000e1ac`
- name: `FreeHandle`
- size: `220`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048e0`
- `0x180005030`
- `0x18000a960`
- `0x18000e000`
- `0x180011c1c`
- `0x180011e60`
- `0x180011f20`
- `0x180012180`
- `0x180017b20`
- `0x180017d30`
- `0x180018a10`
- `0x180018e40`
- `0x180019330`
- `0x180019920`
- `0x18001a3c0`
- `0x18001d590`

## callees

- `0x18000e0d0`
- `0x180012d08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e150`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e150`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e0ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e115`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e0ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e135`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e15d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e135`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e15d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e13e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e13e`

## pseudocode

```c
void __fastcall FreeHandle(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  unsigned __int64 *i; // rcx

  if ( a1 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)(a1 - 80);
    EnterCriticalSection(&HandleListCritSec);
    for ( i = &pHandleList; *i; i = (unsigned __int64 *)*i )
    {
      if ( (struct _RTL_CRITICAL_SECTION *)*i == v1 )
      {
        *i = (unsigned __int64)v1->DebugInfo;
        EnterCriticalSection(v1 + 1);
        *(_QWORD *)&v1->LockCount = 0;
        v1->OwningThread = 0;
        v1->DebugInfo = 0;
        LeaveCriticalSection(v1 + 1);
        DeleteCriticalSection(v1 + 1);
        HeapFree(hHeap, 0, v1);
        goto LABEL_6;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
    }
LABEL_6:
    LeaveCriticalSection(&HandleListCritSec);
  }
}

```

## disassembly

```asm
0x18000e0d0  test    rcx, rcx
0x18000e0d3  jz      locret_18000E16D
0x18000e0d9  mov     [rsp+arg_0], rbx
0x18000e0de  push    rdi
0x18000e0df  sub     rsp, 20h
0x18000e0e3  lea     rdi, [rcx-50h]
0x18000e0e7  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000e0ee  call    cs:__imp_EnterCriticalSection
0x18000e0f4  lea     rcx, pHandleList
0x18000e0fb  mov     rax, [rcx]
0x18000e0fe  test    rax, rax
0x18000e101  jz      short loc_18000E173
0x18000e103  cmp     rax, rdi
0x18000e106  jnz     short loc_18000E16E
0x18000e108  mov     rax, [rdi]
0x18000e10b  lea     rbx, [rdi+28h]
0x18000e10f  mov     [rcx], rax
0x18000e112  mov     rcx, rbx; lpCriticalSection
0x18000e115  call    cs:__imp_EnterCriticalSection
0x18000e11b  mov     rcx, rbx; lpCriticalSection
0x18000e11e  mov     qword ptr [rdi+8], 0
0x18000e126  mov     qword ptr [rdi+10h], 0
0x18000e12e  mov     qword ptr [rdi], 0
0x18000e135  call    cs:__imp_LeaveCriticalSection
0x18000e13b  mov     rcx, rbx; lpCriticalSection
0x18000e13e  call    cs:__imp_DeleteCriticalSection
0x18000e144  mov     rcx, cs:hHeap; hHeap
0x18000e14b  mov     r8, rdi; lpMem
0x18000e14e  xor     edx, edx; dwFlags
0x18000e150  call    cs:__imp_HeapFree
0x18000e156  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000e15d  call    cs:__imp_LeaveCriticalSection
0x18000e163  mov     rbx, [rsp+28h+arg_0]
0x18000e168  add     rsp, 20h
0x18000e16c  pop     rdi
0x18000e16d  retn
0x18000e16e  mov     rcx, rax
0x18000e171  jmp     short loc_18000E0FB
0x18000e173  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e17a  lea     rax, WPP_GLOBAL_Control
0x18000e181  cmp     rcx, rax
0x18000e184  jz      short loc_18000E156
0x18000e186  test    dword ptr [rcx+1Ch], 400000h
0x18000e18d  jz      short loc_18000E156
0x18000e18f  cmp     byte ptr [rcx+19h], 1
0x18000e193  jb      short loc_18000E156
0x18000e195  mov     rcx, [rcx+10h]
0x18000e199  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x18000e1a0  mov     edx, 0Bh
0x18000e1a5  call    WPP_SF_
0x18000e1aa  jmp     short loc_18000E156
```
