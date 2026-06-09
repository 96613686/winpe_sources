# HtDismantleHandleTable

- ea: `0x1800134fc`
- end: `0x1800135d3`
- name: `HtDismantleHandleTable`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015728`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x1800134fc`
- `0x18003af5c`
- `0x18003afc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800135c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800135c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001357c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001357c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001356e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001356e`

## pseudocode

```c
__int64 HtDismantleHandleTable()
{
  __int64 v0; // rcx
  unsigned int v1; // edi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  v1 = KspEnterCriticalSection(&CriticalSection);
  if ( v1 )
  {
    WppTraceIndent(v0, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids,
        (_DWORD)WPP_pszIndent,
        v1);
    }
  }
  else
  {
    v2 = g_HandleTable;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    qword_18004C050 = 0;
    qword_18004C048 = 0;
    dword_18004C058 = 0;
    g_HandleTable = 0;
    KspLeaveCriticalSection(&CriticalSection);
  }
  DeleteCriticalSection(&CriticalSection);
  return v1;
}

```

## disassembly

```asm
0x1800134fc  mov     [rsp+arg_0], rbx
0x180013501  push    rdi
0x180013502  sub     rsp, 30h
0x180013506  lea     rcx, CriticalSection
0x18001350d  call    KspEnterCriticalSection
0x180013512  mov     edi, eax
0x180013514  test    eax, eax
0x180013516  jz      short loc_180013567
0x180013518  mov     edx, 2
0x18001351d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013522  mov     rcx, cs:WPP_GLOBAL_Control
0x180013529  lea     rax, WPP_GLOBAL_Control
0x180013530  cmp     rcx, rax
0x180013533  jz      loc_1800135B9
0x180013539  test    byte ptr [rcx+1Ch], 1
0x18001353d  jz      short loc_1800135B9
0x18001353f  cmp     byte ptr [rcx+19h], 2
0x180013543  jb      short loc_1800135B9
0x180013545  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001354c  lea     r8, WPP_505bf203bb7c33930b65ec26b61baf59_Traceguids
0x180013553  mov     rcx, [rcx+10h]
0x180013557  mov     edx, 16h
0x18001355c  mov     [rsp+38h+var_18], edi
0x180013560  call    WPP_SF_sd
0x180013565  jmp     short loc_1800135B9
0x180013567  mov     rbx, cs:g_HandleTable
0x18001356e  call    cs:__imp_GetProcessHeap
0x180013574  mov     r8, rbx; lpMem
0x180013577  xor     edx, edx; dwFlags
0x180013579  mov     rcx, rax; hHeap
0x18001357c  call    cs:__imp_HeapFree
0x180013582  mov     cs:qword_18004C050, 0
0x18001358d  mov     cs:qword_18004C048, 0
0x180013598  mov     cs:dword_18004C058, 0
0x1800135a2  mov     cs:g_HandleTable, 0
0x1800135ad  lea     rcx, CriticalSection
0x1800135b4  call    KspLeaveCriticalSection
0x1800135b9  lea     rcx, CriticalSection; lpCriticalSection
0x1800135c0  call    cs:__imp_DeleteCriticalSection
0x1800135c6  mov     rbx, [rsp+38h+arg_0]
0x1800135cb  mov     eax, edi
0x1800135cd  add     rsp, 30h
0x1800135d1  pop     rdi
0x1800135d2  retn
```
