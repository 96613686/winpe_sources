# InternetGetThreadInfo(void)

- ea: `0x1800339d0`
- end: `0x180033a69`
- name: `?InternetGetThreadInfo@@YAPEAU_INTERNET_THREAD_INFO@@XZ`
- size: `153`
- prototype: `struct _INTERNET_THREAD_INFO *(void)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180015bd0`
- `0x180015d30`
- `0x180032c78`
- `0x180033960`
- `0x180038e30`
- `0x180039160`
- `0x18003caf0`
- `0x18007f428`
- `0x180095148`

## callees

- `0x1800339d0`
- `0x1800809a8`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800339ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800339ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800339fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800339fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339da`

## pseudocode

```c
struct _INTERNET_THREAD_INFO *InternetGetThreadInfo(void)
{
  DWORD LastError; // edi
  struct _INTERNET_THREAD_INFO *ThreadInfo; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v4; // [rsp+20h] [rbp-8h]

  LastError = GetLastError();
  if ( InternetTlsIndex == -1 || (ThreadInfo = (struct _INTERNET_THREAD_INFO *)TlsGetValue(InternetTlsIndex)) == 0 )
  {
    if ( (BYTE1(xmmword_180107A60) & 0x20) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(1037, 15, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids, CurrentThreadId, v4);
    }
    ThreadInfo = InternetCreateThreadInfo();
    if ( !ThreadInfo && (BYTE1(xmmword_180107A60) & 0x20) != 0 )
      WPP_SF_(1037, 16, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids);
  }
  SetLastError(LastError);
  return ThreadInfo;
}

```

## disassembly

```asm
0x1800339d0  mov     [rsp+arg_0], rbx
0x1800339d5  push    rdi
0x1800339d6  sub     rsp, 20h
0x1800339da  call    cs:__imp_GetLastError
0x1800339e0  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x1800339e6  mov     edi, eax
0x1800339e8  cmp     ecx, 0FFFFFFFFh
0x1800339eb  jz      short loc_180033A11
0x1800339ed  call    cs:__imp_TlsGetValue
0x1800339f3  mov     rbx, rax
0x1800339f6  test    rax, rax
0x1800339f9  jz      short loc_180033A11
0x1800339fb  mov     ecx, edi; dwErrCode
0x1800339fd  call    cs:__imp_SetLastError
0x180033a03  mov     rax, rbx
0x180033a06  mov     rbx, [rsp+28h+arg_0]
0x180033a0b  add     rsp, 20h
0x180033a0f  pop     rdi
0x180033a10  retn
0x180033a11  test    byte ptr cs:xmmword_180107A60+1, 20h
0x180033a18  jnz     short loc_180033A48
0x180033a1a  call    ?InternetCreateThreadInfo@@YAPEAU_INTERNET_THREAD_INFO@@XZ; InternetCreateThreadInfo(void)
0x180033a1f  mov     rbx, rax
0x180033a22  test    rax, rax
0x180033a25  jnz     short loc_1800339FB
0x180033a27  test    byte ptr cs:xmmword_180107A60+1, 20h
0x180033a2e  jz      short loc_1800339FB
0x180033a30  mov     edx, 10h
0x180033a35  lea     r8, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids
0x180033a3c  mov     ecx, 40Dh
0x180033a41  call    WPP_SF_
0x180033a46  jmp     short loc_1800339FB
0x180033a48  call    cs:__imp_GetCurrentThreadId
0x180033a4e  mov     edx, 0Fh
0x180033a53  lea     r8, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids
0x180033a5a  mov     r9d, eax
0x180033a5d  mov     ecx, 40Dh
0x180033a62  call    WPP_SF_d
0x180033a67  jmp     short loc_180033A1A
```
