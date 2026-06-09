# waveOutSetCurrentConsoleVoiceComId(uint,ulong)

- ea: `0x18000a27c`
- end: `0x18000a4ea`
- name: `?waveOutSetCurrentConsoleVoiceComId@@YAIIK@Z`
- size: `622`
- prototype: `unsigned int __fastcall(HMIXEROBJ hmxobj, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008834`

## callees

- `0x180004534`
- `0x180007d70`
- `0x180008530`
- `0x18000a27c`
- `0x18000a4f0`
- `0x18000df74`
- `0x180010220`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a2e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a3a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a40a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a2e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a3a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a40a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a323`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a454`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a323`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a454`

## pseudocode

```c
__int64 __fastcall waveOutSetCurrentConsoleVoiceComId(HMIXEROBJ hmxobj, char a2)
{
  unsigned int v2; // ebx
  HMIXEROBJ v3; // r14
  __int64 v5; // rdi
  unsigned int v6; // ebp
  MMRESULT ID; // eax
  unsigned int v8; // ebx
  struct _MMDRV *v9; // rbx
  __int64 puMxId; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  v3 = (HMIXEROBJ)(unsigned int)hmxobj;
  if ( gpstrWoConsoleVoiceComStringId )
    HeapFree(hHeap, 0, gpstrWoConsoleVoiceComStringId);
  gpstrWoConsoleVoiceComStringId = 0;
  if ( !wTotalWaveOutDevs )
    goto LABEL_25;
  LODWORD(puMxId) = 0;
  if ( (_DWORD)v3 == -1 )
    WaveMapperInit();
  EnterCriticalSection(&NumDevsCritSec);
  v5 = waveoutdrvZ;
  v2 = 2;
  if ( (_DWORD)v3 == -1 )
  {
    v6 = 0;
    while ( (__int64 *)v5 != &waveoutdrvZ )
    {
      if ( (*(_BYTE *)(v5 + 112) & 2) != 0 )
        goto LABEL_34;
      v5 = *(_QWORD *)v5;
    }
  }
  else
  {
    v6 = (unsigned int)v3;
    if ( (__int64 *)waveoutdrvZ != &waveoutdrvZ )
    {
      do
      {
        if ( (*(_BYTE *)(v5 + 112) & 2) == 0 )
        {
          if ( *(_DWORD *)(v5 + 88) > v6 )
            break;
          v6 -= *(_DWORD *)(v5 + 88);
        }
        v5 = *(_QWORD *)v5;
      }
      while ( (__int64 *)v5 != &waveoutdrvZ );
      if ( (__int64 *)v5 != &waveoutdrvZ )
      {
LABEL_34:
        _InterlockedIncrement((volatile signed __int32 *)(v5 + 92));
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
    v2 = StringId_Create((struct _MMDRV *)v5, v6, &gpstrWoConsoleVoiceComStringId, 0);
    if ( !v2 )
    {
      if ( !gfDisablePreferredDeviceReordering && (NtCurrentPeb()->AppCompatFlagsUser.QuadPart & 0x200000000LL) != 0 )
      {
        ID = mixerGetID(v3, (UINT *)&puMxId, 0x10000000u);
        v8 = puMxId;
        if ( ID )
          v8 = 0;
        if ( (_DWORD)v3 )
        {
          EnterCriticalSection(&NumDevsCritSec);
          **(_QWORD **)(v5 + 8) = *(_QWORD *)v5;
          *(_QWORD *)(*(_QWORD *)v5 + 8LL) = *(_QWORD *)(v5 + 8);
          *(_QWORD *)v5 = waveoutdrvZ;
          *(_QWORD *)(v5 + 8) = &waveoutdrvZ;
          *(_QWORD *)(waveoutdrvZ + 8) = v5;
          waveoutdrvZ = v5;
          LeaveCriticalSection(&NumDevsCritSec);
        }
        if ( v8 )
        {
          puMxId = 0;
          if ( !(unsigned int)mixerReferenceDriverById(v8, &puMxId, 0) )
          {
            EnterCriticalSection(&NumDevsCritSec);
            v9 = (struct _MMDRV *)puMxId;
            **(_QWORD **)(puMxId + 8) = *(_QWORD *)puMxId;
            *(_QWORD *)(*(_QWORD *)v9 + 8LL) = *((_QWORD *)v9 + 1);
            *(_QWORD *)v9 = mixerdrvZ;
            *((_QWORD *)v9 + 1) = &mixerdrvZ;
            *((_QWORD *)mixerdrvZ + 1) = v9;
            mixerdrvZ = v9;
            LeaveCriticalSection(&NumDevsCritSec);
            mregDecUsagePtr(v9);
          }
        }
      }
      v2 = 0;
    }
    mregDecUsagePtr((struct _MMDRV *)v5);
    if ( !v2 )
    {
LABEL_25:
      gfUsePreferredWaveOnly = a2 & 1;
      if ( WaveMapperInitialized )
        waveOutMessage((HWAVEOUT)0xFFFFFFFFLL, 0x2001u, 0, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000a27c  mov     [rsp+arg_0], rbx
0x18000a281  mov     [rsp+arg_8], rbp
0x18000a286  push    rsi
0x18000a287  push    rdi
0x18000a288  push    r13
0x18000a28a  push    r14
0x18000a28c  push    r15
0x18000a28e  sub     rsp, 20h
0x18000a292  mov     r8, cs:?gpstrWoConsoleVoiceComStringId@@3PEAGEA; lpMem
0x18000a299  xor     ebx, ebx
0x18000a29b  mov     r14d, ecx
0x18000a29e  mov     r15d, edx
0x18000a2a1  test    r8, r8
0x18000a2a4  jz      short loc_18000A2B5
0x18000a2a6  mov     rcx, cs:hHeap; hHeap
0x18000a2ad  xor     edx, edx; dwFlags
0x18000a2af  call    cs:__imp_HeapFree
0x18000a2b5  cmp     cs:wTotalWaveOutDevs, ebx
0x18000a2bb  mov     edi, 0FFFFFFFFh
0x18000a2c0  mov     cs:?gpstrWoConsoleVoiceComStringId@@3PEAGEA, rbx; ushort * gpstrWoConsoleVoiceComStringId
0x18000a2c7  jz      loc_18000A475
0x18000a2cd  mov     dword ptr [rsp+48h+puMxId], ebx
0x18000a2d1  cmp     r14d, edi
0x18000a2d4  jnz     short loc_18000A2DB
0x18000a2d6  call    WaveMapperInit
0x18000a2db  lea     r13, NumDevsCritSec
0x18000a2e2  mov     rcx, r13; lpCriticalSection
0x18000a2e5  call    cs:__imp_EnterCriticalSection
0x18000a2eb  cmp     r14d, edi
0x18000a2ee  lea     rsi, waveoutdrvZ
0x18000a2f5  mov     rdi, cs:waveoutdrvZ
0x18000a2fc  mov     ebx, 2
0x18000a301  jnz     loc_18000A4B5
0x18000a307  xor     ebp, ebp
0x18000a309  jmp     short loc_18000A317
0x18000a30b  test    [rdi+70h], bl
0x18000a30e  jnz     loc_18000A4DF
0x18000a314  mov     rdi, [rdi]
0x18000a317  cmp     rdi, rsi
0x18000a31a  jnz     short loc_18000A30B
0x18000a31c  xor     edi, edi
0x18000a31e  xor     ebp, ebp
0x18000a320  mov     rcx, r13; lpCriticalSection
0x18000a323  call    cs:__imp_LeaveCriticalSection
0x18000a329  test    ebx, ebx
0x18000a32b  jnz     loc_18000A49C
0x18000a331  xor     r9d, r9d; unsigned int *
0x18000a334  lea     r8, ?gpstrWoConsoleVoiceComStringId@@3PEAGEA; unsigned __int16 **
0x18000a33b  mov     edx, ebp; unsigned int
0x18000a33d  mov     rcx, rdi; struct _MMDRV *
0x18000a340  call    ?StringId_Create@@YAIPEAU_MMDRV@@IPEAPEAGPEAK@Z; StringId_Create(_MMDRV *,uint,ushort * *,ulong *)
0x18000a345  mov     ebx, eax
0x18000a347  test    eax, eax
0x18000a349  jnz     loc_18000A464
0x18000a34f  cmp     cs:gfDisablePreferredDeviceReordering, eax
0x18000a355  jnz     loc_18000A462
0x18000a35b  mov     rax, gs:60h
0x18000a364  mov     rcx, 200000000h
0x18000a36e  test    [rax+2D0h], rcx
0x18000a375  jz      loc_18000A462
0x18000a37b  mov     rcx, r14; hmxobj
0x18000a37e  lea     rdx, [rsp+48h+puMxId]; puMxId
0x18000a383  mov     r8d, 10000000h; fdwId
0x18000a389  call    mixerGetID
0x18000a38e  mov     ebx, dword ptr [rsp+48h+puMxId]
0x18000a392  mov     ecx, eax
0x18000a394  xor     eax, eax
0x18000a396  test    ecx, ecx
0x18000a398  cmovnz  ebx, eax
0x18000a39b  test    r14d, r14d
0x18000a39e  jz      short loc_18000A3E7
0x18000a3a0  mov     rcx, r13; lpCriticalSection
0x18000a3a3  call    cs:__imp_EnterCriticalSection
0x18000a3a9  mov     rcx, [rdi+8]
0x18000a3ad  mov     rax, [rdi]
0x18000a3b0  mov     [rcx], rax
0x18000a3b3  mov     rcx, [rdi]
0x18000a3b6  mov     rax, [rdi+8]
0x18000a3ba  mov     [rcx+8], rax
0x18000a3be  mov     rcx, r13; lpCriticalSection
0x18000a3c1  mov     rax, cs:waveoutdrvZ
0x18000a3c8  mov     [rdi], rax
0x18000a3cb  mov     [rdi+8], rsi
0x18000a3cf  mov     rax, cs:waveoutdrvZ
0x18000a3d6  mov     [rax+8], rdi
0x18000a3da  mov     cs:waveoutdrvZ, rdi
0x18000a3e1  call    cs:__imp_LeaveCriticalSection
0x18000a3e7  test    ebx, ebx
0x18000a3e9  jz      short loc_18000A462
0x18000a3eb  xor     r8d, r8d
0x18000a3ee  mov     [rsp+48h+puMxId], 0
0x18000a3f7  lea     rdx, [rsp+48h+puMxId]
0x18000a3fc  mov     ecx, ebx
0x18000a3fe  call    mixerReferenceDriverById
0x18000a403  test    eax, eax
0x18000a405  jnz     short loc_18000A462
0x18000a407  mov     rcx, r13; lpCriticalSection
0x18000a40a  call    cs:__imp_EnterCriticalSection
0x18000a410  mov     rbx, [rsp+48h+puMxId]
0x18000a415  mov     rcx, r13; lpCriticalSection
0x18000a418  mov     rdx, [rbx+8]
0x18000a41c  mov     rax, [rbx]
0x18000a41f  mov     [rdx], rax
0x18000a422  mov     rax, [rbx+8]
0x18000a426  mov     rdx, [rbx]
0x18000a429  mov     [rdx+8], rax
0x18000a42d  mov     rax, cs:mixerdrvZ
0x18000a434  mov     [rbx], rax
0x18000a437  lea     rax, mixerdrvZ
0x18000a43e  mov     [rbx+8], rax
0x18000a442  mov     rax, cs:mixerdrvZ
0x18000a449  mov     [rax+8], rbx
0x18000a44d  mov     cs:mixerdrvZ, rbx
0x18000a454  call    cs:__imp_LeaveCriticalSection
0x18000a45a  mov     rcx, rbx; struct _MMDRV *
0x18000a45d  call    mregDecUsagePtr
0x18000a462  xor     ebx, ebx
0x18000a464  mov     rcx, rdi; struct _MMDRV *
0x18000a467  call    mregDecUsagePtr
0x18000a46c  test    ebx, ebx
0x18000a46e  jnz     short loc_18000A49C
0x18000a470  mov     edi, 0FFFFFFFFh
0x18000a475  and     r15d, 1
0x18000a479  cmp     cs:WaveMapperInitialized, 0
0x18000a480  mov     cs:?gfUsePreferredWaveOnly@@3HA, r15d; int gfUsePreferredWaveOnly
0x18000a487  jz      short loc_18000A49C
0x18000a489  xor     r9d, r9d; dw2
0x18000a48c  xor     r8d, r8d; dw1
0x18000a48f  mov     edx, 2001h; uMsg
0x18000a494  mov     rcx, rdi; hwo
0x18000a497  call    waveOutMessage
0x18000a49c  mov     rbp, [rsp+48h+arg_8]
0x18000a4a1  mov     eax, ebx
0x18000a4a3  mov     rbx, [rsp+48h+arg_0]
0x18000a4a8  add     rsp, 20h
0x18000a4ac  pop     r15
0x18000a4ae  pop     r14
0x18000a4b0  pop     r13
0x18000a4b2  pop     rdi
0x18000a4b3  pop     rsi
0x18000a4b4  retn
0x18000a4b5  mov     ebp, r14d
0x18000a4b8  cmp     rdi, rsi
0x18000a4bb  jz      loc_18000A31C
0x18000a4c1  test    [rdi+70h], bl
0x18000a4c4  jnz     short loc_18000A4CE
0x18000a4c6  cmp     [rdi+58h], ebp
0x18000a4c9  ja      short loc_18000A4D6
0x18000a4cb  sub     ebp, [rdi+58h]
0x18000a4ce  mov     rdi, [rdi]
0x18000a4d1  cmp     rdi, rsi
0x18000a4d4  jnz     short loc_18000A4C1
0x18000a4d6  cmp     rdi, rsi
0x18000a4d9  jz      loc_18000A31C
0x18000a4df  lock inc dword ptr [rdi+5Ch]
0x18000a4e3  xor     ebx, ebx
0x18000a4e5  jmp     loc_18000A320
```
