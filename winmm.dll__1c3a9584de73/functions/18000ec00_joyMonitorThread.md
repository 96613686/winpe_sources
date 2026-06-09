# joyMonitorThread

- ea: `0x18000ec00`
- end: `0x18000ece4`
- name: `joyMonitorThread`
- size: `228`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000e5b4`
- `0x18000e658`
- `0x18000ec00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ecb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ecb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ecc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ecc2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ec20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ec20`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000ec3c`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000ec3c`

## pseudocode

```c
__int64 __fastcall joyMonitorThread(PVOID Parameter)
{
  DWORD v1; // eax
  int v2; // esi
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 result; // rax

  while ( 1 )
  {
    if ( !g_hEventWinmm )
    {
LABEL_4:
      SleepEx(0xEA60u, 0);
      goto LABEL_5;
    }
    v1 = WaitForSingleObject(g_hEventWinmm, 0xEA60u);
    if ( !v1 )
      break;
    if ( v1 != 258 )
      goto LABEL_4;
LABEL_5:
    v2 = 0;
    v3 = 0;
    do
    {
      v4 = qword_180026280[v3];
      if ( !v4 )
        goto LABEL_14;
      EnterCriticalSection(&joyCritSec);
      if ( *(_DWORD *)(v4 + 48) )
      {
        if ( *(_DWORD *)(v4 + 48) != 1 )
        {
          joyClose((unsigned int)v3);
          goto LABEL_13;
        }
        *(_DWORD *)(v4 + 48) = 2;
      }
      else
      {
        *(_DWORD *)(v4 + 48) = 1;
      }
      v2 = 1;
LABEL_13:
      LeaveCriticalSection(&joyCritSec);
LABEL_14:
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < 0x10 );
    if ( !v2 )
    {
      EnterCriticalSection(&joyCritSec);
      joyCloseAll();
      LeaveCriticalSection(&joyCritSec);
      break;
    }
  }
  result = 0;
  dword_180025BA0 = 0;
  return result;
}

```

## disassembly

```asm
0x18000ec00  mov     [rsp+arg_0], rbx
0x18000ec05  mov     [rsp+arg_8], rsi
0x18000ec0a  push    rdi
0x18000ec0b  sub     rsp, 20h
0x18000ec0f  mov     rcx, cs:g_hEventWinmm; hHandle
0x18000ec16  test    rcx, rcx
0x18000ec19  jz      short loc_18000EC35
0x18000ec1b  mov     edx, 0EA60h; dwMilliseconds
0x18000ec20  call    cs:__imp_WaitForSingleObject
0x18000ec26  test    eax, eax
0x18000ec28  jz      loc_18000ECC8
0x18000ec2e  cmp     eax, 102h
0x18000ec33  jz      short loc_18000EC42
0x18000ec35  xor     edx, edx; bAlertable
0x18000ec37  mov     ecx, 0EA60h; dwMilliseconds
0x18000ec3c  call    cs:__imp_SleepEx
0x18000ec42  xor     esi, esi
0x18000ec44  xor     ebx, ebx
0x18000ec46  lea     rdi, qword_180026280
0x18000ec4d  mov     rdi, [rdi+rbx*8]
0x18000ec51  test    rdi, rdi
0x18000ec54  jz      short loc_18000EC9A
0x18000ec56  lea     rcx, joyCritSec; lpCriticalSection
0x18000ec5d  call    cs:__imp_EnterCriticalSection
0x18000ec63  cmp     dword ptr [rdi+30h], 0
0x18000ec67  jnz     short loc_18000EC72
0x18000ec69  mov     dword ptr [rdi+30h], 1
0x18000ec70  jmp     short loc_18000EC7F
0x18000ec72  cmp     dword ptr [rdi+30h], 1
0x18000ec76  jnz     short loc_18000EC86
0x18000ec78  mov     dword ptr [rdi+30h], 2
0x18000ec7f  mov     esi, 1
0x18000ec84  jmp     short loc_18000EC8D
0x18000ec86  mov     ecx, ebx
0x18000ec88  call    joyClose
0x18000ec8d  lea     rcx, joyCritSec; lpCriticalSection
0x18000ec94  call    cs:__imp_LeaveCriticalSection
0x18000ec9a  inc     ebx
0x18000ec9c  cmp     ebx, 10h
0x18000ec9f  jb      short loc_18000EC46
0x18000eca1  test    esi, esi
0x18000eca3  jnz     loc_18000EC0F
0x18000eca9  lea     rcx, joyCritSec; lpCriticalSection
0x18000ecb0  call    cs:__imp_EnterCriticalSection
0x18000ecb6  call    joyCloseAll
0x18000ecbb  lea     rcx, joyCritSec; lpCriticalSection
0x18000ecc2  call    cs:__imp_LeaveCriticalSection
0x18000ecc8  mov     rbx, [rsp+28h+arg_0]
0x18000eccd  xor     eax, eax
0x18000eccf  mov     rsi, [rsp+28h+arg_8]
0x18000ecd4  mov     cs:dword_180025BA0, 0
0x18000ecde  add     rsp, 20h
0x18000ece2  pop     rdi
0x18000ece3  retn
```
