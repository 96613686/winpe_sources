# SoundBeep(void)

- ea: `0x180019230`
- end: `0x1800192f0`
- name: `?SoundBeep@@YAHXZ`
- size: `192`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800027a0`

## callees

- `0x18000b6d4`
- `0x180019230`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!Beep` at `0x1800192a7`
- `api-ms-win-core-util-l1-1-0!Beep` at `0x1800192a7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180019249`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180019249`

## pseudocode

```c
BOOL SoundBeep(void)
{
  int v0; // eax
  int pvParam; // [rsp+30h] [rbp+8h] BYREF

  pvParam = 0;
  if ( SystemParametersInfoW(1u, 0, &pvParam, 0) )
  {
    v0 = pvParam;
  }
  else
  {
    v0 = 1;
    pvParam = 1;
  }
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids);
    }
    return Beep(0x1B8u, 0x7Du);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180019230  sub     rsp, 28h
0x180019234  xor     edx, edx; uiParam
0x180019236  mov     [rsp+28h+pvParam], 0
0x18001923e  xor     r9d, r9d; fWinIni
0x180019241  lea     r8, [rsp+28h+pvParam]; pvParam
0x180019246  lea     ecx, [rdx+1]; uiAction
0x180019249  call    cs:__imp_SystemParametersInfoW
0x18001924f  test    eax, eax
0x180019251  jnz     short loc_18001925E
0x180019253  mov     eax, 1
0x180019258  mov     [rsp+28h+pvParam], eax
0x18001925c  jmp     short loc_180019262
0x18001925e  mov     eax, [rsp+28h+pvParam]
0x180019262  test    eax, eax
0x180019264  jz      short loc_1800192AF
0x180019266  mov     rcx, cs:WPP_GLOBAL_Control
0x18001926d  lea     rax, WPP_GLOBAL_Control
0x180019274  cmp     rcx, rax
0x180019277  jz      short loc_18001929D
0x180019279  test    dword ptr [rcx+1Ch], 400000h
0x180019280  jz      short loc_18001929D
0x180019282  cmp     byte ptr [rcx+19h], 5
0x180019286  jb      short loc_18001929D
0x180019288  mov     rcx, [rcx+10h]
0x18001928c  lea     r8, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids
0x180019293  mov     edx, 20h ; ' '
0x180019298  call    WPP_SF_
0x18001929d  mov     edx, 7Dh ; '}'; dwDuration
0x1800192a2  mov     ecx, 1B8h; dwFreq
0x1800192a7  call    cs:__imp_Beep
0x1800192ad  jmp     short loc_1800192EB
0x1800192af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192b6  lea     rax, WPP_GLOBAL_Control
0x1800192bd  cmp     rcx, rax
0x1800192c0  jz      short loc_1800192E6
0x1800192c2  test    dword ptr [rcx+1Ch], 400000h
0x1800192c9  jz      short loc_1800192E6
0x1800192cb  cmp     byte ptr [rcx+19h], 5
0x1800192cf  jb      short loc_1800192E6
0x1800192d1  mov     rcx, [rcx+10h]
0x1800192d5  lea     r8, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids
0x1800192dc  mov     edx, 21h ; '!'
0x1800192e1  call    WPP_SF_
0x1800192e6  mov     eax, 1
0x1800192eb  add     rsp, 28h
0x1800192ef  retn
```
