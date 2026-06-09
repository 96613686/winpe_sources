# InternetDestroyThreadInfo

- ea: `0x1800d3c78`
- end: `0x1800d3d81`
- name: `InternetDestroyThreadInfo`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800d3734`
- `0x1800d39b4`

## callees

- `0x1800d3c78`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d3ce1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d3ce1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d3cb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d3cb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d3cfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d3d6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d3cfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d3d6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3d1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3d41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3d1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3d41`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d3c91`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d3c91`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800d3d0f`

## pseudocode

```c
int InternetDestroyThreadInfo()
{
  _QWORD *Value; // rax
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  _QWORD *v3; // rax
  void *v4; // r8
  DWORD v5; // eax
  DWORD CurrentThreadId; // eax

  if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_d(1037, 20, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, CurrentThreadId);
  }
  Value = TlsGetValue(InternetTlsIndex);
  v1 = Value;
  if ( Value )
  {
    EnterCriticalSection(&stru_180266E38);
    v2 = *v1;
    if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v3 = (_QWORD *)v1[1], (_QWORD *)*v3 != v1) )
      __fastfail(3u);
    *v3 = v2;
    *(_QWORD *)(v2 + 8) = v3;
    --dword_180266E30;
    LeaveCriticalSection(&stru_180266E38);
    v4 = (void *)v1[3];
    if ( v4 )
    {
      HeapFree(g_hWxProcessHeap, 0, v4);
      v1[3] = 0;
    }
    HeapFree(g_hWxProcessHeap, 0, v1);
    LODWORD(Value) = TlsSetValue(InternetTlsIndex, 0);
  }
  else if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
  {
    v5 = GetCurrentThreadId();
    LODWORD(Value) = WPP_SF_d(1037, 21, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, v5);
  }
  return (int)Value;
}

```

## disassembly

```asm
0x1800d3c78  push    rbx
0x1800d3c7a  sub     rsp, 20h
0x1800d3c7e  test    byte ptr cs:xmmword_180266B60+1, 20h
0x1800d3c85  jnz     loc_1800D3D41
0x1800d3c8b  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x1800d3c91  call    cs:__imp_TlsGetValue
0x1800d3c97  mov     rbx, rax
0x1800d3c9a  test    rax, rax
0x1800d3c9d  jnz     short loc_1800D3CAE
0x1800d3c9f  test    byte ptr cs:xmmword_180266B60+1, 20h
0x1800d3ca6  jnz     short loc_1800D3D1D
0x1800d3ca8  add     rsp, 20h
0x1800d3cac  pop     rbx
0x1800d3cad  retn
0x1800d3cae  lea     rcx, stru_180266E38; lpCriticalSection
0x1800d3cb5  call    cs:__imp_EnterCriticalSection
0x1800d3cbb  mov     rcx, [rbx]
0x1800d3cbe  cmp     [rcx+8], rbx
0x1800d3cc2  jnz     short loc_1800D3D16
0x1800d3cc4  mov     rax, [rbx+8]
0x1800d3cc8  cmp     [rax], rbx
0x1800d3ccb  jnz     short loc_1800D3D16
0x1800d3ccd  mov     [rax], rcx
0x1800d3cd0  mov     [rcx+8], rax
0x1800d3cd4  lea     rcx, stru_180266E38; lpCriticalSection
0x1800d3cdb  dec     cs:dword_180266E30
0x1800d3ce1  call    cs:__imp_LeaveCriticalSection
0x1800d3ce7  mov     r8, [rbx+18h]; lpMem
0x1800d3ceb  test    r8, r8
0x1800d3cee  jnz     short loc_1800D3D65
0x1800d3cf0  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800d3cf7  mov     r8, rbx; lpMem
0x1800d3cfa  xor     edx, edx; dwFlags
0x1800d3cfc  call    cs:__imp_HeapFree
0x1800d3d02  mov     ecx, cs:?InternetTlsIndex@@3KA; ulong InternetTlsIndex
0x1800d3d08  xor     edx, edx
0x1800d3d0a  add     rsp, 20h
0x1800d3d0e  pop     rbx
0x1800d3d0f  jmp     cs:__imp_TlsSetValue
0x1800d3d16  mov     ecx, 3
0x1800d3d1b  int     29h; Win8: RtlFailFast(ecx)
0x1800d3d1d  call    cs:__imp_GetCurrentThreadId
0x1800d3d23  mov     edx, 15h
0x1800d3d28  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x1800d3d2f  mov     r9d, eax
0x1800d3d32  mov     ecx, 40Dh
0x1800d3d37  add     rsp, 20h
0x1800d3d3b  pop     rbx
0x1800d3d3c  jmp     WPP_SF_d
0x1800d3d41  call    cs:__imp_GetCurrentThreadId
0x1800d3d47  mov     edx, 14h
0x1800d3d4c  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x1800d3d53  mov     r9d, eax
0x1800d3d56  mov     ecx, 40Dh
0x1800d3d5b  call    WPP_SF_d
0x1800d3d60  jmp     loc_1800D3C8B
0x1800d3d65  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800d3d6c  xor     edx, edx; dwFlags
0x1800d3d6e  call    cs:__imp_HeapFree
0x1800d3d74  mov     qword ptr [rbx+18h], 0
0x1800d3d7c  jmp     loc_1800D3CF0
```
