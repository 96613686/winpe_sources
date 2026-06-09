# _DbgpDeleteTraceControl(_DBG_TRACE_CONTROL_BLOCK *)

- ea: `0x180035fc8`
- end: `0x1800360a6`
- name: `?_DbgpDeleteTraceControl@@YAXPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z`
- size: `222`
- prototype: `void __fastcall(struct _DBG_TRACE_CONTROL_BLOCK *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180035d38`
- `0x180036874`
- `0x1800369dc`

## callees

- `0x180013304`
- `0x180035fc8`
- `0x1800366ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036072`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036072`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036004`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036021`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036021`
- `ntdll!RtlFreeHeap` at `0x18003609a`
- `ntdll!RtlFreeHeap` at `0x18003609a`
- `ntdll!RtlFreeUnicodeString` at `0x18003605b`
- `ntdll!RtlFreeUnicodeString` at `0x180036065`
- `ntdll!RtlFreeUnicodeString` at `0x18003605b`
- `ntdll!RtlFreeUnicodeString` at `0x180036065`
- `ntdll!EtwUnregisterTraceGuids` at `0x180036046`
- `ntdll!EtwUnregisterTraceGuids` at `0x180036046`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180035fe7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180035fe7`

## pseudocode

```c
void __fastcall _DbgpDeleteTraceControl(struct _DBG_TRACE_CONTROL_BLOCK *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  HKEY v4; // rcx

  if ( a1 )
  {
    v2 = (void *)*((_QWORD *)a1 + 20);
    if ( v2 )
    {
      UnregisterWaitEx(v2, 0);
      *((_QWORD *)a1 + 20) = 0;
    }
    v3 = (void *)*((_QWORD *)a1 + 19);
    if ( v3 )
    {
      CloseHandle(v3);
      *((_QWORD *)a1 + 19) = 0;
    }
    v4 = (HKEY)*((_QWORD *)a1 + 21);
    if ( v4 )
    {
      RegCloseKey(v4);
      *((_QWORD *)a1 + 21) = 0;
    }
    _DbgpStopTracing(a1);
    if ( *((_QWORD *)a1 + 16) )
    {
      EtwUnregisterTraceGuids();
      *((_QWORD *)a1 + 16) = 0;
    }
    RtlFreeUnicodeString((PUNICODE_STRING)((char *)a1 + 56));
    RtlFreeUnicodeString((PUNICODE_STRING)((char *)a1 + 40));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 192));
    memset_0(a1, 0, 0xF0u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
  }
}

```

## disassembly

```asm
0x180035fc8  test    rcx, rcx
0x180035fcb  jz      locret_1800360A5
0x180035fd1  push    rbx
0x180035fd2  sub     rsp, 20h
0x180035fd6  mov     rbx, rcx
0x180035fd9  mov     rcx, [rcx+0A0h]; WaitHandle
0x180035fe0  test    rcx, rcx
0x180035fe3  jz      short loc_180035FF8
0x180035fe5  xor     edx, edx; CompletionEvent
0x180035fe7  call    cs:__imp_UnregisterWaitEx
0x180035fed  mov     qword ptr [rbx+0A0h], 0
0x180035ff8  mov     rcx, [rbx+98h]; hObject
0x180035fff  test    rcx, rcx
0x180036002  jz      short loc_180036015
0x180036004  call    cs:__imp_CloseHandle
0x18003600a  mov     qword ptr [rbx+98h], 0
0x180036015  mov     rcx, [rbx+0A8h]; hKey
0x18003601c  test    rcx, rcx
0x18003601f  jz      short loc_180036032
0x180036021  call    cs:__imp_RegCloseKey
0x180036027  mov     qword ptr [rbx+0A8h], 0
0x180036032  mov     rcx, rbx; struct _DBG_TRACE_CONTROL_BLOCK *
0x180036035  call    ?_DbgpStopTracing@@YAXPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z; _DbgpStopTracing(_DBG_TRACE_CONTROL_BLOCK *)
0x18003603a  mov     rcx, [rbx+80h]
0x180036041  test    rcx, rcx
0x180036044  jz      short loc_180036057
0x180036046  call    cs:__imp_EtwUnregisterTraceGuids
0x18003604c  mov     qword ptr [rbx+80h], 0
0x180036057  lea     rcx, [rbx+38h]; UnicodeString
0x18003605b  call    cs:__imp_RtlFreeUnicodeString
0x180036061  lea     rcx, [rbx+28h]; UnicodeString
0x180036065  call    cs:__imp_RtlFreeUnicodeString
0x18003606b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180036072  call    cs:__imp_DeleteCriticalSection
0x180036078  xor     edx, edx; Val
0x18003607a  mov     r8d, 0F0h; Size
0x180036080  mov     rcx, rbx; void *
0x180036083  call    memset_0
0x180036088  mov     rcx, gs:60h
0x180036091  mov     r8, rbx; P
0x180036094  xor     edx, edx; Flags
0x180036096  mov     rcx, [rcx+30h]; HeapHandle
0x18003609a  call    cs:__imp_RtlFreeHeap
0x1800360a0  add     rsp, 20h
0x1800360a4  pop     rbx
0x1800360a5  retn
```
