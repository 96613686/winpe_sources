# ClientDestroyContext(void *)

- ea: `0x18000be60`
- end: `0x18000bf6d`
- name: `?ClientDestroyContext@@YAXPEAX@Z`
- size: `269`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005d50`

## callees

- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x18000be60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bec6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bec6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bed9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bed9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bea2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bea2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000beb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000beb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000bf23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000bf23`

## pseudocode

```c
void __fastcall ClientDestroyContext(char *lpMem)
{
  union DOT11_OUI_HEADER *v2; // rcx
  struct _TP_CLEANUP_GROUP *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rax
  HANDLE ProcessHeap; // rax
  __int64 v7; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    v3 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)lpMem + 37);
    if ( v3 )
      CloseThreadpoolCleanupGroup(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 168));
    v4 = (void *)*((_QWORD *)lpMem + 26);
    if ( v4 )
      CloseHandle(v4);
    v5 = *((_QWORD *)lpMem + 20);
    if ( v5 )
    {
      v7 = *(_QWORD *)(v5 + 32);
      if ( v7 )
        FreeWLMem(v7);
      FreeWLMem(*((_QWORD *)lpMem + 20));
    }
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
      HeapFree(ProcessHeap, 0, lpMem);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v2 + 105) >= 4u
    && (*((_BYTE *)v2 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v2 + 12), 46, WPP_797f1b088bb039a5f91226960c081484_Traceguids, 0);
  }
}

```

## disassembly

```asm
0x18000be60  mov     [rsp+arg_0], rbx
0x18000be65  push    rdi
0x18000be66  sub     rsp, 20h
0x18000be6a  mov     rbx, rcx
0x18000be6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be74  lea     rdi, WPP_GLOBAL_Control
0x18000be7b  cmp     rcx, rdi
0x18000be7e  jz      short loc_18000BE86
0x18000be80  cmp     byte ptr [rcx+69h], 4
0x18000be84  jnb     short loc_18000BEFC
0x18000be86  test    rbx, rbx
0x18000be89  jz      short loc_18000BEE6
0x18000be8b  mov     rcx, [rbx+128h]; ptpcg
0x18000be92  test    rcx, rcx
0x18000be95  jnz     loc_18000BF23
0x18000be9b  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x18000bea2  call    cs:__imp_DeleteCriticalSection
0x18000bea8  mov     rcx, [rbx+0D0h]; hObject
0x18000beaf  test    rcx, rcx
0x18000beb2  jz      short loc_18000BEBA
0x18000beb4  call    cs:__imp_CloseHandle
0x18000beba  mov     rax, [rbx+0A0h]
0x18000bec1  test    rax, rax
0x18000bec4  jnz     short loc_18000BF2E
0x18000bec6  call    cs:__imp_GetProcessHeap
0x18000becc  test    rax, rax
0x18000becf  jz      short loc_18000BEDF
0x18000bed1  mov     r8, rbx; lpMem
0x18000bed4  xor     edx, edx; dwFlags
0x18000bed6  mov     rcx, rax; hHeap
0x18000bed9  call    cs:__imp_HeapFree
0x18000bedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bee6  cmp     rcx, rdi
0x18000bee9  jz      short loc_18000BEF1
0x18000beeb  cmp     byte ptr [rcx+69h], 4
0x18000beef  jnb     short loc_18000BF4D
0x18000bef1  mov     rbx, [rsp+28h+arg_0]
0x18000bef6  add     rsp, 20h
0x18000befa  pop     rdi
0x18000befb  retn
0x18000befc  test    byte ptr [rcx+6Ch], 2
0x18000bf00  jz      short loc_18000BE86
0x18000bf02  mov     rcx, [rcx+60h]
0x18000bf06  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000bf0d  mov     edx, 2Dh ; '-'
0x18000bf12  call    WPP_SF_
0x18000bf17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf1e  jmp     loc_18000BE86
0x18000bf23  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000bf29  jmp     loc_18000BE9B
0x18000bf2e  mov     rcx, [rax+20h]
0x18000bf32  test    rcx, rcx
0x18000bf35  jz      short loc_18000BF3C
0x18000bf37  call    FreeWLMem
0x18000bf3c  mov     rcx, [rbx+0A0h]
0x18000bf43  call    FreeWLMem
0x18000bf48  jmp     loc_18000BEC6
0x18000bf4d  test    byte ptr [rcx+6Ch], 2
0x18000bf51  jz      short loc_18000BEF1
0x18000bf53  mov     rcx, [rcx+60h]
0x18000bf57  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000bf5e  mov     edx, 2Eh ; '.'
0x18000bf63  xor     r9d, r9d
0x18000bf66  call    WPP_SF_d
0x18000bf6b  jmp     short loc_18000BEF1
```
