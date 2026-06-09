# CSettings::ComputeConsent(bool)

- ea: `0x14000560c`
- end: `0x1400058e3`
- name: `?ComputeConsent@CSettings@@AEBA?AW4_CONSENT_SETTING@@_N@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400084f4`

## callees

- `0x14000162c`
- `0x140003200`
- `0x14000560c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140005668`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140005726`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400057bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140005668`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140005726`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1400057bd`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140005736`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x140005736`

## pseudocode

```c
__int64 __fastcall CSettings::ComputeConsent(__int64 a1, char a2)
{
  unsigned int v3; // ebx
  int v4; // esi
  int v6; // r14d
  int v7; // edi
  int WerTelemetryMode; // r15d
  int v9; // ecx
  int v10; // [rsp+30h] [rbp-99h] BYREF
  int v11; // [rsp+34h] [rbp-95h] BYREF
  int v12; // [rsp+38h] [rbp-91h] BYREF
  int v13; // [rsp+3Ch] [rbp-8Dh] BYREF
  unsigned int v14; // [rsp+40h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-79h] BYREF
  unsigned int *v16; // [rsp+70h] [rbp-59h]
  __int64 v17; // [rsp+78h] [rbp-51h]
  int *v18; // [rsp+80h] [rbp-49h]
  __int64 v19; // [rsp+88h] [rbp-41h]
  int *v20; // [rsp+90h] [rbp-39h]
  __int64 v21; // [rsp+98h] [rbp-31h]
  int *v22; // [rsp+A0h] [rbp-29h]
  __int64 v23; // [rsp+A8h] [rbp-21h]
  int *v24; // [rsp+B0h] [rbp-19h]
  __int64 v25; // [rsp+B8h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+C0h] [rbp-9h] BYREF

  v3 = 1;
  if ( !byte_14002C8C8 )
    goto LABEL_6;
  if ( !dword_14002C8CC )
  {
    v4 = *(_DWORD *)String;
    goto LABEL_7;
  }
  if ( dword_14002C8CC == 1 )
    v4 = wcstol(String, 0, 10);
  else
LABEL_6:
    v4 = dword_14002C928;
LABEL_7:
  if ( dword_14002DB78 == 3 )
    return 0;
  if ( dword_14002DB78 == 4 )
    return v3;
  if ( dword_14002DB78 != 2 )
  {
    v6 = v4;
    if ( !byte_14002C860 )
      goto LABEL_21;
    if ( !dword_14002C864 )
    {
      v7 = *(_DWORD *)qword_14002C868;
      goto LABEL_22;
    }
    if ( dword_14002C864 == 1 )
      v7 = wcstol(qword_14002C868, 0, 10);
    else
LABEL_21:
      v7 = dword_14002C8C0;
LABEL_22:
    WerTelemetryMode = TelGetWerTelemetryMode();
    if ( (unsigned int)(v7 - 1) <= 3 )
    {
      if ( v7 != 1 )
        goto LABEL_27;
    }
    else
    {
      v7 = 1;
    }
    if ( WerTelemetryMode >= 1 )
      v7 = 2;
LABEL_27:
    if ( WerTelemetryMode )
    {
      if ( WerTelemetryMode == 1 )
      {
        if ( v7 >= 3 )
          v7 = 2;
      }
      else if ( WerTelemetryMode == 2 && v7 >= 4 )
      {
        v7 = 3;
      }
    }
    else
    {
      v7 = 1;
    }
    if ( !byte_14002C930 )
    {
      v9 = 1;
LABEL_37:
      v3 = v7;
LABEL_49:
      if ( a2
        && (unsigned int)dword_14002C000 > 4
        && (qword_14002C010 & 2) != 0
        && (qword_14002C018 & 2) == qword_14002C018 )
      {
        v12 = v9;
        v24 = &v10;
        v25 = 4;
        v22 = &v11;
        v23 = 4;
        v20 = &v12;
        v21 = 4;
        v18 = &v13;
        v16 = &v14;
        v19 = 4;
        v17 = 4;
        v10 = v6;
        v11 = WerTelemetryMode;
        v13 = v7;
        v14 = v3;
        tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, byte_140025CDC, 0, 0, 7u, &v15);
      }
      return v3;
    }
    if ( dword_14002C934 )
    {
      if ( dword_14002C934 == 1 )
        v9 = wcstol(qword_14002C938, 0, 10);
      else
        v9 = dword_14002C990;
    }
    else
    {
      v9 = *(_DWORD *)qword_14002C938;
    }
    if ( v9 >= 5 )
      v9 = 1;
    if ( byte_14002C860 )
    {
      if ( v4 < 2 )
      {
        if ( v4 )
        {
          if ( v4 != 1 )
            goto LABEL_49;
          goto LABEL_37;
        }
      }
      else
      {
        v6 = 0;
      }
    }
    v3 = v9;
    goto LABEL_49;
  }
  if ( (unsigned int)dword_14002C000 > 4 && (qword_14002C010 & 2) != 0 && (qword_14002C018 & 2) == qword_14002C018 )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, byte_140025CA8, 0, 0, 2u, &v26);
  return 4;
}

```

## disassembly

```asm
0x14000560c  push    rbp
0x14000560e  push    rbx
0x14000560f  push    rsi
0x140005610  push    rdi
0x140005611  push    r12
0x140005613  push    r14
0x140005615  push    r15
0x140005617  lea     rbp, [rsp-27h]
0x14000561c  sub     rsp, 0F0h
0x140005623  mov     rax, cs:__security_cookie
0x14000562a  xor     rax, rsp
0x14000562d  mov     [rbp+57h+var_40], rax
0x140005631  cmp     cs:byte_14002C8C8, 0
0x140005638  mov     r12b, dl
0x14000563b  mov     ebx, 1
0x140005640  jz      short loc_140005672
0x140005642  mov     eax, cs:dword_14002C8CC
0x140005648  test    eax, eax
0x14000564a  jnz     short loc_140005657
0x14000564c  mov     rax, cs:String
0x140005653  mov     esi, [rax]
0x140005655  jmp     short loc_140005678
0x140005657  cmp     eax, ebx
0x140005659  jnz     short loc_140005672
0x14000565b  mov     rcx, cs:String; String
0x140005662  xor     edx, edx; EndPtr
0x140005664  lea     r8d, [rdx+0Ah]; Radix
0x140005668  call    cs:__imp_wcstol
0x14000566e  mov     esi, eax
0x140005670  jmp     short loc_140005678
0x140005672  mov     esi, cs:dword_14002C928
0x140005678  mov     eax, cs:dword_14002DB78
0x14000567e  cmp     eax, 3
0x140005681  jnz     short loc_14000568A
0x140005683  xor     eax, eax
0x140005685  jmp     loc_1400058B0
0x14000568a  cmp     eax, 4
0x14000568d  jz      loc_1400058AE
0x140005693  mov     edx, 2
0x140005698  cmp     eax, edx
0x14000569a  jnz     short loc_1400056F4
0x14000569c  mov     eax, cs:dword_14002C000
0x1400056a2  cmp     eax, 4
0x1400056a5  jbe     short loc_1400056EA
0x1400056a7  mov     rcx, cs:qword_14002C018
0x1400056ae  mov     rax, cs:qword_14002C010
0x1400056b5  test    dl, al
0x1400056b7  jz      short loc_1400056EA
0x1400056b9  mov     rax, rcx
0x1400056bc  and     rax, rdx
0x1400056bf  cmp     rax, rcx
0x1400056c2  jnz     short loc_1400056EA
0x1400056c4  lea     rax, [rbp+57h+var_60]
0x1400056c8  xor     r9d, r9d
0x1400056cb  mov     [rsp+120h+var_F8], rax
0x1400056d0  lea     rcx, dword_14002C000
0x1400056d7  mov     [rsp+120h+var_100], edx
0x1400056db  xor     r8d, r8d
0x1400056de  lea     rdx, byte_140025CA8
0x1400056e5  call    _tlgWriteTransfer_EventWriteTransfer
0x1400056ea  mov     eax, 4
0x1400056ef  jmp     loc_1400058B0
0x1400056f4  cmp     cs:byte_14002C860, 0
0x1400056fb  mov     r14d, esi
0x1400056fe  jz      short loc_140005730
0x140005700  mov     eax, cs:dword_14002C864
0x140005706  test    eax, eax
0x140005708  jnz     short loc_140005715
0x14000570a  mov     rax, cs:qword_14002C868
0x140005711  mov     edi, [rax]
0x140005713  jmp     short loc_140005736
0x140005715  cmp     eax, ebx
0x140005717  jnz     short loc_140005730
0x140005719  mov     rcx, cs:qword_14002C868; String
0x140005720  xor     edx, edx; EndPtr
0x140005722  lea     r8d, [rdx+0Ah]; Radix
0x140005726  call    cs:__imp_wcstol
0x14000572c  mov     edi, eax
0x14000572e  jmp     short loc_140005736
0x140005730  mov     edi, cs:dword_14002C8C0
0x140005736  call    cs:__imp_TelGetWerTelemetryMode
0x14000573c  lea     ecx, [rdi-1]
0x14000573f  mov     r15d, eax
0x140005742  cmp     ecx, 3
0x140005745  jbe     short loc_14000574B
0x140005747  mov     edi, ebx
0x140005749  jmp     short loc_14000574F
0x14000574b  cmp     edi, ebx
0x14000574d  jnz     short loc_14000575C
0x14000574f  cmp     r15d, ebx
0x140005752  mov     edx, 2
0x140005757  cmovge  edi, edx
0x14000575a  jmp     short loc_140005761
0x14000575c  mov     edx, 2
0x140005761  mov     ecx, r15d
0x140005764  test    r15d, r15d
0x140005767  jz      short loc_140005786
0x140005769  sub     ecx, ebx
0x14000576b  jz      short loc_14000577D
0x14000576d  cmp     ecx, ebx
0x14000576f  jnz     short loc_140005788
0x140005771  cmp     edi, 4
0x140005774  jl      short loc_140005788
0x140005776  mov     edi, 3
0x14000577b  jmp     short loc_140005788
0x14000577d  cmp     edi, 3
0x140005780  jl      short loc_140005788
0x140005782  mov     edi, edx
0x140005784  jmp     short loc_140005788
0x140005786  mov     edi, ebx
0x140005788  cmp     cs:byte_14002C930, 0
0x14000578f  jnz     short loc_140005797
0x140005791  mov     ecx, ebx
0x140005793  mov     ebx, edi
0x140005795  jmp     short loc_1400057EA
0x140005797  mov     eax, cs:dword_14002C934
0x14000579d  test    eax, eax
0x14000579f  jnz     short loc_1400057AC
0x1400057a1  mov     rax, cs:qword_14002C938
0x1400057a8  mov     ecx, [rax]
0x1400057aa  jmp     short loc_1400057CD
0x1400057ac  cmp     eax, ebx
0x1400057ae  jnz     short loc_1400057C7
0x1400057b0  mov     rcx, cs:qword_14002C938; String
0x1400057b7  xor     edx, edx; EndPtr
0x1400057b9  lea     r8d, [rdx+0Ah]; Radix
0x1400057bd  call    cs:__imp_wcstol
0x1400057c3  mov     ecx, eax
0x1400057c5  jmp     short loc_1400057CD
0x1400057c7  mov     ecx, cs:dword_14002C990
0x1400057cd  cmp     ecx, 5
0x1400057d0  cmovge  ecx, ebx
0x1400057d3  cmp     cs:byte_14002C860, 0
0x1400057da  jz      short loc_1400057E8
0x1400057dc  cmp     esi, 2
0x1400057df  jl      loc_1400058CE
0x1400057e5  xor     r14d, r14d
0x1400057e8  mov     ebx, ecx
0x1400057ea  test    r12b, r12b
0x1400057ed  jz      loc_1400058AE
0x1400057f3  mov     eax, cs:dword_14002C000
0x1400057f9  mov     r8d, 4
0x1400057ff  cmp     eax, r8d
0x140005802  jbe     loc_1400058AE
0x140005808  mov     rdx, cs:qword_14002C018
0x14000580f  mov     rax, cs:qword_14002C010
0x140005816  test    al, 2
0x140005818  jz      loc_1400058AE
0x14000581e  mov     rax, rdx
0x140005821  and     eax, 2
0x140005824  cmp     rax, rdx
0x140005827  jnz     loc_1400058AE
0x14000582d  lea     rax, [rsp+120h+var_F0]
0x140005832  mov     [rsp+120h+var_E8], ecx
0x140005836  mov     [rbp+57h+var_70], rax
0x14000583a  lea     rdx, byte_140025CDC
0x140005841  lea     rax, [rsp+120h+var_EC]
0x140005846  mov     [rbp+57h+var_68], r8
0x14000584a  mov     [rbp+57h+var_80], rax
0x14000584e  lea     rcx, dword_14002C000
0x140005855  lea     rax, [rsp+120h+var_E8]
0x14000585a  mov     [rbp+57h+var_78], r8
0x14000585e  mov     [rbp+57h+var_90], rax
0x140005862  xor     r9d, r9d
0x140005865  lea     rax, [rsp+120h+var_E4]
0x14000586a  mov     [rbp+57h+var_88], r8
0x14000586e  mov     [rbp+57h+var_A0], rax
0x140005872  lea     rax, [rsp+120h+var_E0]
0x140005877  mov     [rbp+57h+var_B0], rax
0x14000587b  lea     rax, [rbp+57h+var_D0]
0x14000587f  mov     [rbp+57h+var_98], r8
0x140005883  mov     [rbp+57h+var_A8], r8
0x140005887  xor     r8d, r8d
0x14000588a  mov     [rsp+120h+var_F8], rax
0x14000588f  mov     [rsp+120h+var_100], 7
0x140005897  mov     [rsp+120h+var_F0], r14d
0x14000589c  mov     [rsp+120h+var_EC], r15d
0x1400058a1  mov     [rsp+120h+var_E4], edi
0x1400058a5  mov     [rsp+120h+var_E0], ebx
0x1400058a9  call    _tlgWriteTransfer_EventWriteTransfer
0x1400058ae  mov     eax, ebx
0x1400058b0  mov     rcx, [rbp+57h+var_40]
0x1400058b4  xor     rcx, rsp; StackCookie
0x1400058b7  call    __security_check_cookie
0x1400058bc  add     rsp, 0F0h
0x1400058c3  pop     r15
0x1400058c5  pop     r14
0x1400058c7  pop     r12
0x1400058c9  pop     rdi
0x1400058ca  pop     rsi
0x1400058cb  pop     rbx
0x1400058cc  pop     rbp
0x1400058cd  retn
0x1400058ce  test    esi, esi
0x1400058d0  jz      loc_1400057E8
0x1400058d6  cmp     esi, ebx
0x1400058d8  jnz     loc_1400057EA
0x1400058de  jmp     loc_140005793
```
