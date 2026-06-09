# InternetCreateThreadInfo(void)

- ea: `0x1800809a8`
- end: `0x180080a62`
- name: `?InternetCreateThreadInfo@@YAPEAU_INTERNET_THREAD_INFO@@XZ`
- size: `186`
- prototype: `struct _INTERNET_THREAD_INFO *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013f60`
- `0x1800339d0`

## callees

- `0x1800809a8`
- `0x180080a68`
- `0x1800cf008`
- `0x1800d14a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800809be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800809be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080a58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080a58`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800809ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800809ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800809d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800809d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a31`

## pseudocode

```c
struct _INTERNET_THREAD_INFO *InternetCreateThreadInfo(void)
{
  _QWORD *v0; // rax
  __int64 v1; // rbx
  DWORD CurrentThreadId; // eax
  DWORD v3; // ecx
  struct SERIALIZED_LIST *v4; // rcx
  int v6; // edx
  int v7; // ecx
  int v8; // r8d

  v0 = HeapAlloc(g_hWxProcessHeap, 8u, 0x20u);
  v1 = (__int64)v0;
  if ( v0 )
  {
    v0[1] = v0;
    *v0 = v0;
    CurrentThreadId = GetCurrentThreadId();
    v3 = InternetTlsIndex;
    *(_DWORD *)(v1 + 20) = CurrentThreadId;
    *(_DWORD *)(v1 + 16) = 1685219412;
    if ( TlsSetValue(v3, (LPVOID)v1) )
    {
      InsertAtHeadOfSerializedList(v4, (struct _LIST_ENTRY *)v1);
    }
    else
    {
      if ( (BYTE1(xmmword_180107A60) & 0x20) != 0 )
      {
        GetLastError();
        WPP_SF_dqd(v7, v6, v8, InternetTlsIndex, v1);
      }
      HeapFree(g_hWxProcessHeap, 0, (LPVOID)v1);
      return 0;
    }
  }
  else if ( (BYTE1(xmmword_180107A60) & 0x20) != 0 )
  {
    WPP_SF_(1037, 11, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids);
  }
  return (struct _INTERNET_THREAD_INFO *)v1;
}

```

## disassembly

```asm
0x1800809a8  push    rbx
0x1800809aa  sub     rsp, 30h
0x1800809ae  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800809b5  mov     edx, 8; dwFlags
0x1800809ba  lea     r8d, [rdx+18h]; dwBytes
0x1800809be  call    cs:__imp_HeapAlloc
0x1800809c4  mov     rbx, rax
0x1800809c7  test    rax, rax
0x1800809ca  jz      short loc_180080A07
0x1800809cc  mov     [rax+8], rax
0x1800809d0  mov     [rax], rax
0x1800809d3  call    cs:__imp_GetCurrentThreadId
0x1800809d9  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x1800809df  mov     rdx, rbx; lpTlsValue
0x1800809e2  mov     [rbx+14h], eax
0x1800809e5  mov     dword ptr [rbx+10h], 64726854h
0x1800809ec  call    cs:__imp_TlsSetValue
0x1800809f2  test    eax, eax
0x1800809f4  jz      short loc_180080A28
0x1800809f6  mov     rdx, rbx; struct _LIST_ENTRY *
0x1800809f9  call    ?InsertAtHeadOfSerializedList@@YAXPEAVSERIALIZED_LIST@@PEAU_LIST_ENTRY@@@Z; InsertAtHeadOfSerializedList(SERIALIZED_LIST *,_LIST_ENTRY *)
0x1800809fe  mov     rax, rbx
0x180080a01  add     rsp, 30h
0x180080a05  pop     rbx
0x180080a06  retn
0x180080a07  test    byte ptr cs:xmmword_180107A60+1, 20h
0x180080a0e  jz      short loc_1800809FE
0x180080a10  mov     edx, 0Bh
0x180080a15  lea     r8, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids
0x180080a1c  mov     ecx, 40Dh
0x180080a21  call    WPP_SF_
0x180080a26  jmp     short loc_1800809FE
0x180080a28  test    byte ptr cs:xmmword_180107A60+1, 20h
0x180080a2f  jz      short loc_180080A4C
0x180080a31  call    cs:__imp_GetLastError
0x180080a37  mov     r9d, cs:?InternetTlsIndex@@3KA; ulong InternetTlsIndex
0x180080a3e  mov     [rsp+38h+var_10], eax
0x180080a42  mov     [rsp+38h+var_18], rbx
0x180080a47  call    WPP_SF_dqd
0x180080a4c  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180080a53  mov     r8, rbx; lpMem
0x180080a56  xor     edx, edx; dwFlags
0x180080a58  call    cs:__imp_HeapFree
0x180080a5e  xor     ebx, ebx
0x180080a60  jmp     short loc_1800809FE
```
