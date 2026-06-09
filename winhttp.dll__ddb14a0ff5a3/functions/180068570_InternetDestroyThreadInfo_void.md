# InternetDestroyThreadInfo(void)

- ea: `0x180068570`
- end: `0x18006866d`
- name: `?InternetDestroyThreadInfo@@YAXXZ`
- size: `253`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800684bc`
- `0x180068510`

## callees

- `0x180068570`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800685aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800685aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800685de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800685de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800685f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800685f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180068595`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180068595`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180068607`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068621`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068642`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068621`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068642`

## pseudocode

```c
void __fastcall InternetDestroyThreadInfo()
{
  __int64 v0; // rbx
  _QWORD *Value; // rbx
  __int64 v2; // rdx
  _QWORD *v3; // rax
  DWORD v4; // eax
  DWORD CurrentThreadId; // eax
  __int64 v6; // [rsp+20h] [rbp-8h]
  __int64 v7; // [rsp+20h] [rbp-8h]

  if ( (BYTE1(xmmword_180107A60) & 0x20) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_d(1037, 13, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids, CurrentThreadId, v6);
  }
  v7 = v0;
  if ( InternetTlsIndex == -1 || (Value = TlsGetValue(InternetTlsIndex)) == 0 )
  {
    if ( (BYTE1(xmmword_180107A60) & 0x20) != 0 )
    {
      v4 = GetCurrentThreadId();
      WPP_SF_d(1037, 14, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids, v4, v7);
    }
  }
  else
  {
    EnterCriticalSection(&stru_180107E18);
    v2 = *Value;
    if ( *(_QWORD **)(*Value + 8LL) != Value || (v3 = (_QWORD *)Value[1], (_QWORD *)*v3 != Value) )
      __fastfail(3u);
    *v3 = v2;
    *(_QWORD *)(v2 + 8) = v3;
    --dword_180107E10;
    LeaveCriticalSection(&stru_180107E18);
    HeapFree(g_hWxProcessHeap, 0, Value);
    TlsSetValue(InternetTlsIndex, 0);
  }
}

```

## disassembly

```asm
0x180068570  sub     rsp, 28h
0x180068574  test    byte ptr cs:xmmword_180107A60+1, 20h
0x18006857b  jnz     loc_180068642
0x180068581  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x180068587  mov     [rsp+28h+var_8], rbx
0x18006858c  cmp     ecx, 0FFFFFFFFh
0x18006858f  jz      loc_180068618
0x180068595  call    cs:__imp_TlsGetValue
0x18006859b  mov     rbx, rax
0x18006859e  test    rax, rax
0x1800685a1  jz      short loc_180068618
0x1800685a3  lea     rcx, stru_180107E18; lpCriticalSection
0x1800685aa  call    cs:__imp_EnterCriticalSection
0x1800685b0  mov     rdx, [rbx]
0x1800685b3  cmp     [rdx+8], rbx
0x1800685b7  jnz     loc_180068666
0x1800685bd  mov     rax, [rbx+8]
0x1800685c1  cmp     [rax], rbx
0x1800685c4  jnz     loc_180068666
0x1800685ca  mov     [rax], rdx
0x1800685cd  lea     rcx, stru_180107E18; lpCriticalSection
0x1800685d4  mov     [rdx+8], rax
0x1800685d8  dec     cs:dword_180107E10
0x1800685de  call    cs:__imp_LeaveCriticalSection
0x1800685e4  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800685eb  mov     r8, rbx; lpMem
0x1800685ee  xor     edx, edx; dwFlags
0x1800685f0  call    cs:__imp_HeapFree
0x1800685f6  mov     ecx, cs:?InternetTlsIndex@@3KA; ulong InternetTlsIndex
0x1800685fc  xor     edx, edx
0x1800685fe  mov     rbx, [rsp+28h+var_8]
0x180068603  add     rsp, 28h
0x180068607  jmp     cs:__imp_TlsSetValue
0x18006860e  mov     rbx, [rsp+28h+var_8]
0x180068613  add     rsp, 28h
0x180068617  retn
0x180068618  test    byte ptr cs:xmmword_180107A60+1, 20h
0x18006861f  jz      short loc_18006860E
0x180068621  call    cs:__imp_GetCurrentThreadId
0x180068627  mov     edx, 0Eh
0x18006862c  lea     r8, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids
0x180068633  mov     r9d, eax
0x180068636  mov     ecx, 40Dh
0x18006863b  call    WPP_SF_d
0x180068640  jmp     short loc_18006860E
0x180068642  call    cs:__imp_GetCurrentThreadId
0x180068648  mov     edx, 0Dh
0x18006864d  lea     r8, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids
0x180068654  mov     r9d, eax
0x180068657  mov     ecx, 40Dh
0x18006865c  call    WPP_SF_d
0x180068661  jmp     loc_180068581
0x180068666  mov     ecx, 3
0x18006866b  int     29h; Win8: RtlFailFast(ecx)
```
