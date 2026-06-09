# WaveMapperInit

- ea: `0x180004534`
- end: `0x180004607`
- name: `WaveMapperInit`
- size: `211`
- prototype: `__int64(void)`
- caller_count: `13`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001378`
- `0x180004480`
- `0x1800048e0`
- `0x180005030`
- `0x180007b00`
- `0x1800093a0`
- `0x180009820`
- `0x180009a8c`
- `0x18000a0d8`
- `0x18000a27c`
- `0x18000a790`
- `0x18000b584`
- `0x18000b8f4`

## callees

- `0x180001f30`
- `0x18000296c`
- `0x180004534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004552`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004568`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004568`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000457f`

## pseudocode

```c
void WaveMapperInit()
{
  HDRVR v0; // rax
  UINT v1; // edi
  HDRVR v2; // rbx
  UINT v3; // eax
  BOOL v4; // eax

  EnterCriticalSection(&NumDevsCritSec);
  EnterCriticalSection(&MapperInitCritSec);
  if ( !WaveMapperInitialized && wTotalWaveOutDevs + wTotalWaveInDevs )
  {
    v0 = (HDRVR)mmDrvOpen(wszWaveMapper);
    v4 = 0;
    if ( v0 )
    {
      v1 = mmDrvInstall(v0, wszWaveMapper, 0, 0xC002u);
      v2 = (HDRVR)mmDrvOpen(wszWaveMapper);
      v3 = mmDrvInstall(v2, wszWaveMapper, 0, 0xC001u);
      if ( v2 )
      {
        if ( v1 && v3 )
          v4 = 1;
      }
    }
    WaveMapperInitialized |= v4;
  }
  LeaveCriticalSection(&MapperInitCritSec);
  LeaveCriticalSection(&NumDevsCritSec);
}

```

## disassembly

```asm
0x180004534  mov     [rsp+arg_0], rbx
0x180004539  push    rdi
0x18000453a  sub     rsp, 20h
0x18000453e  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180004545  call    cs:__imp_EnterCriticalSection
0x18000454b  lea     rcx, ?MapperInitCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004552  call    cs:__imp_EnterCriticalSection
0x180004558  cmp     cs:WaveMapperInitialized, 0
0x18000455f  jz      short loc_180004586
0x180004561  lea     rcx, ?MapperInitCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004568  call    cs:__imp_LeaveCriticalSection
0x18000456e  lea     rcx, NumDevsCritSec
0x180004575  mov     rbx, [rsp+28h+arg_0]
0x18000457a  add     rsp, 20h
0x18000457e  pop     rdi
0x18000457f  jmp     cs:__imp_LeaveCriticalSection
0x180004586  mov     ecx, cs:wTotalWaveInDevs
0x18000458c  add     ecx, cs:wTotalWaveOutDevs
0x180004592  jz      short loc_180004561
0x180004594  lea     rcx, wszWaveMapper; "wavemapper"
0x18000459b  call    ?mmDrvOpen@@YAPEAUHDRVR__@@PEBG@Z; mmDrvOpen(ushort const *)
0x1800045a0  test    rax, rax
0x1800045a3  jz      short loc_1800045EB
0x1800045a5  mov     r9d, 0C002h; wFlags
0x1800045ab  lea     rdx, wszWaveMapper; "wavemapper"
0x1800045b2  xor     r8d, r8d; drvMessage
0x1800045b5  mov     rcx, rax; hDriver
0x1800045b8  call    mmDrvInstall
0x1800045bd  lea     rcx, wszWaveMapper; "wavemapper"
0x1800045c4  mov     edi, eax
0x1800045c6  call    ?mmDrvOpen@@YAPEAUHDRVR__@@PEBG@Z; mmDrvOpen(ushort const *)
0x1800045cb  mov     r9d, 0C001h; wFlags
0x1800045d1  lea     rdx, wszWaveMapper; "wavemapper"
0x1800045d8  xor     r8d, r8d; drvMessage
0x1800045db  mov     rcx, rax; hDriver
0x1800045de  mov     rbx, rax
0x1800045e1  call    mmDrvInstall
0x1800045e6  test    rbx, rbx
0x1800045e9  jnz     short loc_1800045F8
0x1800045eb  xor     eax, eax
0x1800045ed  or      cs:WaveMapperInitialized, eax
0x1800045f3  jmp     loc_180004561
0x1800045f8  test    edi, edi
0x1800045fa  jz      short loc_1800045EB
0x1800045fc  test    eax, eax
0x1800045fe  jz      short loc_1800045EB
0x180004600  mov     eax, 1
0x180004605  jmp     short loc_1800045ED
```
