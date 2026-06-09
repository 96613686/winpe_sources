# waveInSetCurrentConsoleVoiceComId(uint,ulong)

- ea: `0x18000b584`
- end: `0x18000b73d`
- name: `?waveInSetCurrentConsoleVoiceComId@@YAIIK@Z`
- size: `441`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008834`

## callees

- `0x180004534`
- `0x180007640`
- `0x180007d70`
- `0x18000a4f0`
- `0x18000b584`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b67b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b67b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6bd`

## pseudocode

```c
__int64 __fastcall waveInSetCurrentConsoleVoiceComId(unsigned int a1, char a2)
{
  unsigned int v2; // edi
  struct HWAVEOUT__ *v5; // rbx
  unsigned int v6; // ebp

  v2 = 0;
  if ( gpstrWiConsoleVoiceComStringId )
    HeapFree(hHeap, 0, gpstrWiConsoleVoiceComStringId);
  gpstrWiConsoleVoiceComStringId = 0;
  if ( !wTotalWaveInDevs )
    goto LABEL_19;
  if ( a1 == -1 )
    WaveMapperInit();
  EnterCriticalSection(&NumDevsCritSec);
  v5 = *(struct HWAVEOUT__ **)&waveindrvZ.unused;
  v2 = 2;
  if ( a1 == -1 )
  {
    v6 = 0;
    while ( v5 != &waveindrvZ )
    {
      if ( ((_BYTE)v5[28] & 2) != 0 )
        goto LABEL_28;
      v5 = *(struct HWAVEOUT__ **)v5;
    }
  }
  else
  {
    v6 = a1;
    if ( *(struct HWAVEOUT__ **)&waveindrvZ.unused != &waveindrvZ )
    {
      do
      {
        if ( ((_BYTE)v5[28] & 2) == 0 )
        {
          if ( *((_DWORD *)v5 + 22) > v6 )
            break;
          v6 -= *((_DWORD *)v5 + 22);
        }
        v5 = *(struct HWAVEOUT__ **)v5;
      }
      while ( v5 != &waveindrvZ );
      if ( v5 != &waveindrvZ )
      {
LABEL_28:
        _InterlockedIncrement((volatile signed __int32 *)v5 + 23);
        v2 = 0;
        goto LABEL_12;
      }
    }
  }
  v5 = 0;
  v6 = 0;
LABEL_12:
  LeaveCriticalSection(&NumDevsCritSec);
  if ( !v2 )
  {
    v2 = StringId_Create((struct _MMDRV *)v5, v6, &gpstrWiConsoleVoiceComStringId, 0);
    if ( !v2
      && !gfDisablePreferredDeviceReordering
      && (NtCurrentPeb()->AppCompatFlagsUser.QuadPart & 0x200000000LL) != 0
      && a1 )
    {
      EnterCriticalSection(&NumDevsCritSec);
      **((_QWORD **)v5 + 1) = *(_QWORD *)v5;
      *(_QWORD *)(*(_QWORD *)v5 + 8LL) = *((_QWORD *)v5 + 1);
      *(_QWORD *)v5 = *(_QWORD *)&waveindrvZ.unused;
      *((_QWORD *)v5 + 1) = &waveindrvZ;
      *(_QWORD *)(*(_QWORD *)&waveindrvZ.unused + 8LL) = v5;
      *(_QWORD *)&waveindrvZ.unused = v5;
      LeaveCriticalSection(&NumDevsCritSec);
    }
    mregDecUsagePtr((struct _MMDRV *)v5);
    if ( !v2 )
    {
LABEL_19:
      gfUsePreferredWaveOnly = a2 & 1;
      if ( WaveMapperInitialized )
        waveInMessage((HWAVEIN)0xFFFFFFFFLL, 0x2001u, 0, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000b584  push    rbx
0x18000b586  push    rbp
0x18000b587  push    rsi
0x18000b588  push    rdi
0x18000b589  push    r13
0x18000b58b  push    r14
0x18000b58d  push    r15
0x18000b58f  sub     rsp, 20h
0x18000b593  mov     r8, cs:?gpstrWiConsoleVoiceComStringId@@3PEAGEA; lpMem
0x18000b59a  xor     edi, edi
0x18000b59c  mov     r15d, edx
0x18000b59f  mov     r14d, ecx
0x18000b5a2  test    r8, r8
0x18000b5a5  jz      short loc_18000B5B6
0x18000b5a7  mov     rcx, cs:hHeap; hHeap
0x18000b5ae  xor     edx, edx; dwFlags
0x18000b5b0  call    cs:__imp_HeapFree
0x18000b5b6  cmp     cs:wTotalWaveInDevs, edi
0x18000b5bc  mov     r13d, 0FFFFFFFFh
0x18000b5c2  mov     cs:?gpstrWiConsoleVoiceComStringId@@3PEAGEA, rdi; ushort * gpstrWiConsoleVoiceComStringId
0x18000b5c9  jz      loc_18000B6CF
0x18000b5cf  cmp     r14d, r13d
0x18000b5d2  jnz     short loc_18000B5D9
0x18000b5d4  call    WaveMapperInit
0x18000b5d9  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000b5e0  call    cs:__imp_EnterCriticalSection
0x18000b5e6  mov     rbx, qword ptr cs:waveindrvZ.unused
0x18000b5ed  mov     edi, 2
0x18000b5f2  lea     rsi, waveindrvZ
0x18000b5f9  cmp     r14d, r13d
0x18000b5fc  jnz     loc_18000B707
0x18000b602  xor     ebp, ebp
0x18000b604  jmp     short loc_18000B613
0x18000b606  test    [rbx+70h], dil
0x18000b60a  jnz     loc_18000B732
0x18000b610  mov     rbx, [rbx]
0x18000b613  cmp     rbx, rsi
0x18000b616  jnz     short loc_18000B606
0x18000b618  xor     ebx, ebx
0x18000b61a  xor     ebp, ebp
0x18000b61c  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000b623  call    cs:__imp_LeaveCriticalSection
0x18000b629  test    edi, edi
0x18000b62b  jnz     loc_18000B6F6
0x18000b631  xor     r9d, r9d; unsigned int *
0x18000b634  lea     r8, ?gpstrWiConsoleVoiceComStringId@@3PEAGEA; unsigned __int16 **
0x18000b63b  mov     edx, ebp; unsigned int
0x18000b63d  mov     rcx, rbx; struct _MMDRV *
0x18000b640  call    ?StringId_Create@@YAIPEAU_MMDRV@@IPEAPEAGPEAK@Z; StringId_Create(_MMDRV *,uint,ushort * *,ulong *)
0x18000b645  mov     edi, eax
0x18000b647  test    eax, eax
0x18000b649  jnz     short loc_18000B6C3
0x18000b64b  cmp     cs:gfDisablePreferredDeviceReordering, eax
0x18000b651  jnz     short loc_18000B6C3
0x18000b653  mov     rax, gs:60h
0x18000b65c  mov     rcx, 200000000h
0x18000b666  test    [rax+2D0h], rcx
0x18000b66d  jz      short loc_18000B6C3
0x18000b66f  test    r14d, r14d
0x18000b672  jz      short loc_18000B6C3
0x18000b674  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000b67b  call    cs:__imp_EnterCriticalSection
0x18000b681  mov     rdx, [rbx+8]
0x18000b685  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000b68c  mov     rax, [rbx]
0x18000b68f  mov     [rdx], rax
0x18000b692  mov     rax, [rbx+8]
0x18000b696  mov     rdx, [rbx]
0x18000b699  mov     [rdx+8], rax
0x18000b69d  mov     rax, qword ptr cs:waveindrvZ.unused
0x18000b6a4  mov     [rbx], rax
0x18000b6a7  mov     [rbx+8], rsi
0x18000b6ab  mov     rax, qword ptr cs:waveindrvZ.unused
0x18000b6b2  mov     [rax+8], rbx
0x18000b6b6  mov     qword ptr cs:waveindrvZ.unused, rbx
0x18000b6bd  call    cs:__imp_LeaveCriticalSection
0x18000b6c3  mov     rcx, rbx; struct _MMDRV *
0x18000b6c6  call    mregDecUsagePtr
0x18000b6cb  test    edi, edi
0x18000b6cd  jnz     short loc_18000B6F6
0x18000b6cf  and     r15d, 1
0x18000b6d3  cmp     cs:WaveMapperInitialized, 0
0x18000b6da  mov     cs:?gfUsePreferredWaveOnly@@3HA, r15d; int gfUsePreferredWaveOnly
0x18000b6e1  jz      short loc_18000B6F6
0x18000b6e3  xor     r9d, r9d; dw2
0x18000b6e6  xor     r8d, r8d; dw1
0x18000b6e9  mov     edx, 2001h; uMsg
0x18000b6ee  mov     rcx, r13; hwi
0x18000b6f1  call    waveInMessage
0x18000b6f6  mov     eax, edi
0x18000b6f8  add     rsp, 20h
0x18000b6fc  pop     r15
0x18000b6fe  pop     r14
0x18000b700  pop     r13
0x18000b702  pop     rdi
0x18000b703  pop     rsi
0x18000b704  pop     rbp
0x18000b705  pop     rbx
0x18000b706  retn
0x18000b707  mov     ebp, r14d
0x18000b70a  cmp     rbx, rsi
0x18000b70d  jz      loc_18000B618
0x18000b713  test    [rbx+70h], dil
0x18000b717  jnz     short loc_18000B721
0x18000b719  cmp     [rbx+58h], ebp
0x18000b71c  ja      short loc_18000B729
0x18000b71e  sub     ebp, [rbx+58h]
0x18000b721  mov     rbx, [rbx]
0x18000b724  cmp     rbx, rsi
0x18000b727  jnz     short loc_18000B713
0x18000b729  cmp     rbx, rsi
0x18000b72c  jz      loc_18000B618
0x18000b732  lock inc dword ptr [rbx+5Ch]
0x18000b736  xor     edi, edi
0x18000b738  jmp     loc_18000B61C
```
