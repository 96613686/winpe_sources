# mciRegisterCommandTable(void *,uint *,uint,void *)

- ea: `0x1800126c0`
- end: `0x1800127a3`
- name: `?mciRegisterCommandTable@@YAIPEAXPEAII0@Z`
- size: `227`
- prototype: `unsigned int(void *, unsigned int *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012f30`

## callees

- `0x18000b6d4`
- `0x1800126c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012790`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012758`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012758`

## pseudocode

```c
__int64 __fastcall mciRegisterCommandTable(__int64 a1, unsigned int *a2, int a3, __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdx

  EnterCriticalSection(&mciCritSec);
  v8 = 0;
  if ( number_of_command_tables )
  {
    do
    {
      if ( !command_tables[5 * v8] )
        break;
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < number_of_command_tables );
    if ( (unsigned int)v8 < number_of_command_tables )
      goto LABEL_12;
  }
  if ( number_of_command_tables != 20 )
  {
    LODWORD(v8) = number_of_command_tables++;
LABEL_12:
    v9 = 5LL * (unsigned int)v8;
    LODWORD(command_tables[v9 + 2]) = a3;
    command_tables[v9] = a1;
    command_tables[v9 + 3] = (__int64)a2;
    command_tables[v9 + 1] = a4;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      number_of_command_tables - 9,
      WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids);
  }
  HeapFree(hHeap, 0, a2);
  LODWORD(v8) = -1;
LABEL_13:
  LeaveCriticalSection(&mciCritSec);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800126c0  push    rbx
0x1800126c2  push    rbp
0x1800126c3  push    rsi
0x1800126c4  push    rdi
0x1800126c5  push    r14
0x1800126c7  sub     rsp, 20h
0x1800126cb  mov     r14, rcx
0x1800126ce  mov     rsi, r9
0x1800126d1  lea     rcx, mciCritSec; lpCriticalSection
0x1800126d8  mov     ebp, r8d
0x1800126db  mov     rdi, rdx
0x1800126de  call    cs:__imp_EnterCriticalSection
0x1800126e4  mov     r10d, cs:?number_of_command_tables@@3IA; uint number_of_command_tables
0x1800126eb  lea     r8, command_tables
0x1800126f2  xor     ebx, ebx
0x1800126f4  test    r10d, r10d
0x1800126f7  jz      short loc_180012710
0x1800126f9  lea     rcx, [rbx+rbx*4]
0x1800126fd  cmp     qword ptr [r8+rcx*8], 0
0x180012702  jz      short loc_18001270B
0x180012704  inc     ebx
0x180012706  cmp     ebx, r10d
0x180012709  jb      short loc_1800126F9
0x18001270b  cmp     ebx, r10d
0x18001270e  jb      short loc_180012770
0x180012710  cmp     r10d, 14h
0x180012714  jnz     short loc_180012763
0x180012716  mov     rcx, cs:WPP_GLOBAL_Control
0x18001271d  lea     rax, WPP_GLOBAL_Control
0x180012724  cmp     rcx, rax
0x180012727  jz      short loc_18001274C
0x180012729  test    dword ptr [rcx+1Ch], 400000h
0x180012730  jz      short loc_18001274C
0x180012732  cmp     byte ptr [rcx+19h], 1
0x180012736  jb      short loc_18001274C
0x180012738  mov     rcx, [rcx+10h]
0x18001273c  lea     edx, [r10-9]
0x180012740  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012747  call    WPP_SF_
0x18001274c  mov     rcx, cs:hHeap; hHeap
0x180012753  mov     r8, rdi; lpMem
0x180012756  xor     edx, edx; dwFlags
0x180012758  call    cs:__imp_HeapFree
0x18001275e  or      ebx, 0FFFFFFFFh
0x180012761  jmp     short loc_180012789
0x180012763  lea     eax, [r10+1]
0x180012767  mov     ebx, r10d
0x18001276a  mov     cs:?number_of_command_tables@@3IA, eax; uint number_of_command_tables
0x180012770  mov     eax, ebx
0x180012772  lea     rdx, [rax+rax*4]
0x180012776  mov     [r8+rdx*8+10h], ebp
0x18001277b  mov     [r8+rdx*8], r14
0x18001277f  mov     [r8+rdx*8+18h], rdi
0x180012784  mov     [r8+rdx*8+8], rsi
0x180012789  lea     rcx, mciCritSec; lpCriticalSection
0x180012790  call    cs:__imp_LeaveCriticalSection
0x180012796  mov     eax, ebx
0x180012798  add     rsp, 20h
0x18001279c  pop     r14
0x18001279e  pop     rdi
0x18001279f  pop     rsi
0x1800127a0  pop     rbp
0x1800127a1  pop     rbx
0x1800127a2  retn
```
