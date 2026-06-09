# SessionLogoffCallback

- ea: `0x1800030c0`
- end: `0x180003149`
- name: `SessionLogoffCallback`
- size: `137`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fd0`

## callees

- `0x180002d80`
- `0x1800030c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003131`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003131`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x180003104`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x180003104`

## pseudocode

```c
__int64 __fastcall SessionLogoffCallback(int a1)
{
  __int128 *i; // rbx
  HANDLE *v3; // rdx
  int v5; // [rsp+38h] [rbp+10h] BYREF

  EnterCriticalSection(&csForProcessCount);
LABEL_2:
  for ( i = (__int128 *)xmmword_1800096E0; i != &xmmword_1800096E0; i = *(__int128 **)i )
  {
    v3 = (HANDLE *)(i - 3);
    if ( *((_DWORD *)i - 4) == a1 )
    {
      if ( !*v3 )
      {
        v5 = 0;
        SecondaryLogonCleanupJob(0, (__int64)v3, &v5);
        if ( !v5 )
          goto LABEL_2;
        break;
      }
      TerminateJobObject(*v3, 0);
    }
  }
  LeaveCriticalSection(&csForProcessCount);
  return 0;
}

```

## disassembly

```asm
0x1800030c0  mov     [rsp+arg_0], rbx
0x1800030c5  mov     [rsp+arg_10], rsi
0x1800030ca  push    rdi
0x1800030cb  sub     rsp, 20h
0x1800030cf  mov     edi, ecx
0x1800030d1  lea     rcx, csForProcessCount; lpCriticalSection
0x1800030d8  call    cs:__imp_EnterCriticalSection
0x1800030de  lea     rsi, xmmword_1800096E0
0x1800030e5  mov     rbx, qword ptr cs:xmmword_1800096E0
0x1800030ec  cmp     rbx, rsi
0x1800030ef  jz      short loc_18000312A
0x1800030f1  cmp     [rbx-10h], edi
0x1800030f4  lea     rdx, [rbx-30h]
0x1800030f8  jnz     short loc_18000310A
0x1800030fa  mov     rcx, [rdx]; hJob
0x1800030fd  test    rcx, rcx
0x180003100  jz      short loc_18000310F
0x180003102  xor     edx, edx; uExitCode
0x180003104  call    cs:__imp_TerminateJobObject
0x18000310a  mov     rbx, [rbx]
0x18000310d  jmp     short loc_1800030EC
0x18000310f  lea     r8, [rsp+28h+arg_8]
0x180003114  mov     [rsp+28h+arg_8], 0
0x18000311c  xor     ecx, ecx
0x18000311e  call    SecondaryLogonCleanupJob
0x180003123  cmp     [rsp+28h+arg_8], 0
0x180003128  jz      short loc_1800030E5
0x18000312a  lea     rcx, csForProcessCount; lpCriticalSection
0x180003131  call    cs:__imp_LeaveCriticalSection
0x180003137  mov     rbx, [rsp+28h+arg_0]
0x18000313c  xor     eax, eax
0x18000313e  mov     rsi, [rsp+28h+arg_10]
0x180003143  add     rsp, 20h
0x180003147  pop     rdi
0x180003148  retn
```
