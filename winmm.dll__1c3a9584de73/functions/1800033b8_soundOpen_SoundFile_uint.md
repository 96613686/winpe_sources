# soundOpen(_SoundFile *,uint)

- ea: `0x1800033b8`
- end: `0x18000367e`
- name: `?soundOpen@@YAHPEAU_SoundFile@@I@Z`
- size: `710`
- prototype: `__int64 __fastcall(struct _SoundFile *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003124`

## callees

- `0x18000304c`
- `0x1800033b8`
- `0x18000b6d4`

## import_xrefs

- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180003505`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180003505`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800033eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800033eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003629`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003629`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a96c`
- `api-ms-win-mm-mme-l1-1-0!waveOutWrite` at `0x1800034b7`
- `api-ms-win-mm-mme-l1-1-0!waveOutWrite` at `0x1800034b7`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x180003454`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x180003454`
- `api-ms-win-mm-mme-l1-1-0!waveOutPrepareHeader` at `0x180003474`
- `api-ms-win-mm-mme-l1-1-0!waveOutPrepareHeader` at `0x180003474`

## pseudocode

```c
__int64 __fastcall soundOpen(struct _SoundFile *a1, int a2)
{
  unsigned int v4; // esi
  DWORD fdwOpen; // eax
  LPWAVEHDR v6; // rdx
  MMRESULT v7; // ebx
  unsigned __int64 v8; // rax
  unsigned int v9; // ecx
  int v10; // eax
  bool v11; // sf
  unsigned int v12; // eax
  LPCWSTR v13; // rcx
  __int64 v14; // rdx

  if ( a1 )
  {
    v4 = 0;
    if ( !hWaveOut )
    {
      EnterCriticalSection(&WavHdrCritSec);
      lpWavHdr = (LPWAVEHDR)((char *)a1 + 4);
      if ( a1 == (struct _SoundFile *)-4LL )
      {
LABEL_39:
        LeaveCriticalSection(&WavHdrCritSec);
        return v4;
      }
      fdwOpen = 2;
      if ( hwndNotify )
        fdwOpen = 65538;
      if ( (a2 & 0x200000) != 0 )
        fdwOpen |= 0x20u;
      if ( (a2 & 0x100000) != 0 )
        fdwOpen |= 0x100u;
      if ( waveOutOpen(&hWaveOut, 0xFFFFFFFF, *(LPCWAVEFORMATEX *)((char *)a1 + 20), (DWORD_PTR)hwndNotify, 0, fdwOpen) )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids);
        }
        hWaveOut = 0;
        lpWavHdr = 0;
        goto LABEL_39;
      }
      if ( waveOutPrepareHeader(hWaveOut, lpWavHdr, 0x30u) )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v14 = 17;
      }
      else
      {
        v6 = lpWavHdr;
        if ( (a2 & 9) == 9 )
        {
          lpWavHdr->dwLoops = -1;
          v6->dwFlags |= 0xCu;
        }
        else
        {
          lpWavHdr->dwLoops = 0;
          v6->dwFlags &= 0xFFFFFFF3;
          v6->dwFlags |= 0x2000u;
        }
        v6->dwFlags &= ~1u;
        v7 = waveOutWrite(hWaveOut, v6, 0x30u);
        v8 = 2000 * (unsigned __int64)lpWavHdr->dwBufferLength / *(unsigned int *)(lpWavHdr->dwUser + 8);
        v9 = v8;
        if ( v8 > 0xFFFFFFFF )
        {
          timeDelta = -1;
          v10 = -2147024362;
          v9 = -1;
        }
        else
        {
          timeDelta = v8;
          v10 = 0;
        }
        v11 = v10 < 0;
        v12 = 0x7FFFFFFF;
        if ( v11 )
        {
          timeDelta = 0x7FFFFFFF;
          v9 = 0x7FFFFFFF;
        }
        if ( v9 < 0x7FFFFFFF )
          v12 = v9;
        timeDelta = v12;
        timeStart = timeGetTime();
        if ( !v7 )
        {
          v4 = 1;
          goto LABEL_39;
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_24:
          soundClose();
          goto LABEL_39;
        }
        v14 = 18;
      }
      WPP_SF_(*((_QWORD *)v13 + 2), v14, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids);
      goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800033b8  mov     [rsp+arg_0], rbx
0x1800033bd  mov     [rsp+arg_8], rsi
0x1800033c2  push    rdi
0x1800033c3  sub     rsp, 40h
0x1800033c7  mov     ebx, edx
0x1800033c9  mov     rdi, rcx
0x1800033cc  test    rcx, rcx
0x1800033cf  jz      loc_180003641
0x1800033d5  xor     esi, esi
0x1800033d7  cmp     cs:?hWaveOut@@3PEAUHWAVEOUT__@@EA, rsi; HWAVEOUT__ * hWaveOut
0x1800033de  jnz     loc_180003645
0x1800033e4  lea     rcx, WavHdrCritSec; lpCriticalSection
0x1800033eb  call    cs:__imp_EnterCriticalSection
0x1800033f1  lea     r8, [rdi+4]
0x1800033f5  mov     cs:lpWavHdr, r8
0x1800033fc  test    r8, r8
0x1800033ff  jz      loc_180003622
0x180003405  lea     eax, [rsi+2]
0x180003408  mov     ecx, 10002h
0x18000340d  mov     r9, cs:hwndNotify; dwCallback
0x180003414  test    r9, r9
0x180003417  cmovnz  eax, ecx
0x18000341a  mov     [rsp+48h+var_18], eax
0x18000341e  bt      ebx, 15h
0x180003422  jnb     short loc_18000342B
0x180003424  or      eax, 20h
0x180003427  mov     [rsp+48h+var_18], eax
0x18000342b  bt      ebx, 14h
0x18000342f  jb      loc_18000354D
0x180003435  mov     [rsp+48h+fdwOpen], eax; fdwOpen
0x180003439  mov     [rsp+48h+dwInstance], 0; dwInstance
0x180003442  mov     r8, [r8+10h]; pwfx
0x180003446  mov     edi, 0FFFFFFFFh
0x18000344b  mov     edx, edi; uDeviceID
0x18000344d  lea     rcx, ?hWaveOut@@3PEAUHWAVEOUT__@@EA; phwo
0x180003454  call    cs:__imp_waveOutOpen
0x18000345a  test    eax, eax
0x18000345c  jnz     loc_18000355A
0x180003462  lea     r8d, [rax+30h]; cbwh
0x180003466  mov     rdx, cs:lpWavHdr; pwh
0x18000346d  mov     rcx, cs:?hWaveOut@@3PEAUHWAVEOUT__@@EA; hwo
0x180003474  call    cs:__imp_waveOutPrepareHeader
0x18000347a  test    eax, eax
0x18000347c  jnz     loc_180003530
0x180003482  and     ebx, 9
0x180003485  mov     rdx, cs:lpWavHdr; pwh
0x18000348c  cmp     bl, 9
0x18000348f  jz      loc_1800035D9
0x180003495  mov     [rdx+1Ch], eax
0x180003498  and     dword ptr [rdx+18h], 0FFFFFFF3h
0x18000349c  mov     eax, [rdx+18h]
0x18000349f  bts     eax, 0Dh
0x1800034a3  mov     [rdx+18h], eax
0x1800034a6  and     dword ptr [rdx+18h], 0FFFFFFFEh
0x1800034aa  mov     r8d, 30h ; '0'; cbwh
0x1800034b0  mov     rcx, cs:?hWaveOut@@3PEAUHWAVEOUT__@@EA; hwo
0x1800034b7  call    cs:__imp_waveOutWrite
0x1800034bd  mov     ebx, eax
0x1800034bf  mov     rdx, cs:lpWavHdr
0x1800034c6  mov     ecx, [rdx+8]
0x1800034c9  imul    rax, rcx, 7D0h
0x1800034d0  mov     rcx, [rdx+10h]
0x1800034d4  mov     r8d, [rcx+8]
0x1800034d8  xor     edx, edx
0x1800034da  div     r8
0x1800034dd  mov     rcx, rax
0x1800034e0  cmp     rax, rdi
0x1800034e3  ja      short loc_180003521
0x1800034e5  mov     cs:?timeDelta@@3KA, eax; ulong timeDelta
0x1800034eb  xor     eax, eax
0x1800034ed  test    eax, eax
0x1800034ef  mov     eax, 7FFFFFFFh
0x1800034f4  js      loc_1800035E5
0x1800034fa  cmp     ecx, eax
0x1800034fc  cmovb   eax, ecx
0x1800034ff  mov     cs:?timeDelta@@3KA, eax; ulong timeDelta
0x180003505  call    cs:__imp_timeGetTime
0x18000350b  mov     cs:?timeStart@@3KA, eax; ulong timeStart
0x180003511  test    ebx, ebx
0x180003513  jnz     loc_1800035F2
0x180003519  lea     esi, [rbx+1]
0x18000351c  jmp     loc_180003622
0x180003521  mov     cs:?timeDelta@@3KA, edi; ulong timeDelta
0x180003527  mov     eax, 80070216h
0x18000352c  mov     ecx, edi
0x18000352e  jmp     short loc_1800034ED
0x180003530  lea     rax, WPP_GLOBAL_Control
0x180003537  mov     rcx, cs:WPP_GLOBAL_Control
0x18000353e  cmp     rcx, rax
0x180003541  jnz     short loc_1800035A9
0x180003543  call    ?soundClose@@YAHXZ; soundClose(void)
0x180003548  jmp     loc_180003622
0x18000354d  bts     eax, 8
0x180003551  mov     [rsp+48h+var_18], eax
0x180003555  jmp     loc_180003435
0x18000355a  lea     rax, WPP_GLOBAL_Control
0x180003561  mov     rcx, cs:WPP_GLOBAL_Control
0x180003568  cmp     rcx, rax
0x18000356b  jz      short loc_180003591
0x18000356d  test    dword ptr [rcx+1Ch], 400000h
0x180003574  jz      short loc_180003591
0x180003576  cmp     byte ptr [rcx+19h], 2
0x18000357a  jb      short loc_180003591
0x18000357c  mov     edx, 10h
0x180003581  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180003588  mov     rcx, [rcx+10h]
0x18000358c  call    WPP_SF_
0x180003591  mov     cs:?hWaveOut@@3PEAUHWAVEOUT__@@EA, 0; HWAVEOUT__ * hWaveOut
0x18000359c  mov     cs:lpWavHdr, 0
0x1800035a7  jmp     short loc_180003622
0x1800035a9  test    dword ptr [rcx+1Ch], 400000h
0x1800035b0  jz      short loc_180003543
0x1800035b2  cmp     byte ptr [rcx+19h], 2
0x1800035b6  jb      short loc_180003543
0x1800035b8  mov     edx, 11h
0x1800035bd  jmp     short loc_1800035C4
0x1800035bf  mov     edx, 12h
0x1800035c4  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x1800035cb  mov     rcx, [rcx+10h]
0x1800035cf  call    WPP_SF_
0x1800035d4  jmp     loc_180003543
0x1800035d9  mov     [rdx+1Ch], edi
0x1800035dc  or      dword ptr [rdx+18h], 0Ch
0x1800035e0  jmp     loc_1800034A6
0x1800035e5  mov     cs:?timeDelta@@3KA, eax; ulong timeDelta
0x1800035eb  mov     ecx, eax
0x1800035ed  jmp     loc_1800034FA
0x1800035f2  lea     rax, WPP_GLOBAL_Control
0x1800035f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003600  cmp     rcx, rax
0x180003603  jz      loc_180003543
0x180003609  test    dword ptr [rcx+1Ch], 400000h
0x180003610  jz      loc_180003543
0x180003616  cmp     byte ptr [rcx+19h], 2
0x18000361a  jb      loc_180003543
0x180003620  jmp     short loc_1800035BF
0x180003622  lea     rcx, WavHdrCritSec; lpCriticalSection
0x180003629  call    cs:__imp_LeaveCriticalSection
0x18000362f  mov     eax, esi
0x180003631  mov     rbx, [rsp+48h+arg_0]
0x180003636  mov     rsi, [rsp+48h+arg_8]
0x18000363b  add     rsp, 40h
0x18000363f  pop     rdi
0x180003640  retn
0x180003641  xor     eax, eax
0x180003643  jmp     short loc_180003631
0x180003645  lea     rax, WPP_GLOBAL_Control
0x18000364c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003653  cmp     rcx, rax
0x180003656  jz      short loc_180003641
0x180003658  test    dword ptr [rcx+1Ch], 400000h
0x18000365f  jz      short loc_180003641
0x180003661  cmp     byte ptr [rcx+19h], 2
0x180003665  jb      short loc_180003641
0x180003667  mov     edx, 0Fh
0x18000366c  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180003673  mov     rcx, [rcx+10h]
0x180003677  call    WPP_SF_
0x18000367c  jmp     short loc_180003641
0x18001a957  push    rbp
0x18001a959  sub     rsp, 30h
0x18001a95d  mov     rbp, rdx
0x18001a960  lea     rcx, WavHdrCritSec
0x18001a967  add     rsp, 30h
0x18001a96b  pop     rbp
0x18001a96c  jmp     cs:__imp_LeaveCriticalSection
```
