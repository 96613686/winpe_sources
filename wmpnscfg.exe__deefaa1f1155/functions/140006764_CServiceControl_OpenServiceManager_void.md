# CServiceControl::OpenServiceManager(void)

- ea: `0x140006764`
- end: `0x140006841`
- name: `?OpenServiceManager@CServiceControl@@AEAAHXZ`
- size: `221`
- prototype: `__int64 __fastcall(CServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140006848`

## callees

- `0x1400053b4`
- `0x1400053dc`
- `0x140006764`
- `0x140006978`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x1400067c1`
- `ADVAPI32!OpenSCManagerW` at `0x1400067c1`
- `KERNEL32!GetLastError` at `0x1400067d2`
- `KERNEL32!GetLastError` at `0x1400067d2`

## pseudocode

```c
__int64 __fastcall CServiceControl::OpenServiceManager(CServiceControl *this)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  DWORD LastError; // eax
  __int64 v6; // r8

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 1;
  if ( *((_QWORD *)this + 1) )
    goto LABEL_11;
  v4 = OpenSCManagerW(0, 0, 0x20001u);
  *((_QWORD *)this + 1) = v4;
  if ( v4 )
    goto LABEL_10;
  v3 = 0;
  LastError = GetLastError();
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v6, LastError);
LABEL_10:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_d(v2[2], 64, &WPP_cb23d491edf93b904e2862226171c496_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x140006764  mov     [rsp+arg_0], rbx
0x140006769  mov     [rsp+arg_8], rsi
0x14000676e  push    rdi
0x14000676f  sub     rsp, 20h
0x140006773  mov     rdi, rcx
0x140006776  mov     rcx, cs:WPP_GLOBAL_Control
0x14000677d  lea     rsi, WPP_GLOBAL_Control
0x140006784  cmp     rcx, rsi
0x140006787  jz      short loc_1400067AB
0x140006789  test    byte ptr [rcx+1Ch], 1
0x14000678d  jz      short loc_1400067AB
0x14000678f  mov     rcx, [rcx+10h]
0x140006793  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x14000679a  mov     edx, 3Eh ; '>'
0x14000679f  call    WPP_SF_
0x1400067a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067ab  cmp     qword ptr [rdi+8], 0
0x1400067b0  mov     ebx, 1
0x1400067b5  jnz     short loc_140006806
0x1400067b7  xor     edx, edx; lpDatabaseName
0x1400067b9  mov     r8d, 20001h; dwDesiredAccess
0x1400067bf  xor     ecx, ecx; lpMachineName
0x1400067c1  call    cs:__imp_OpenSCManagerW
0x1400067c7  mov     [rdi+8], rax
0x1400067cb  test    rax, rax
0x1400067ce  jnz     short loc_1400067FF
0x1400067d0  xor     ebx, ebx
0x1400067d2  call    cs:__imp_GetLastError
0x1400067d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067df  cmp     rcx, rsi
0x1400067e2  jz      short loc_14000682F
0x1400067e4  test    byte ptr [rcx+1Ch], 2
0x1400067e8  jz      short loc_140006806
0x1400067ea  cmp     byte ptr [rcx+19h], 4
0x1400067ee  jb      short loc_140006806
0x1400067f0  mov     rcx, [rcx+10h]
0x1400067f4  lea     edx, [rbx+3Fh]
0x1400067f7  mov     r9d, eax
0x1400067fa  call    WPP_SF_D
0x1400067ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140006806  cmp     rcx, rsi
0x140006809  jz      short loc_14000682F
0x14000680b  test    byte ptr [rcx+1Ch], 1
0x14000680f  jz      short loc_14000682F
0x140006811  cmp     byte ptr [rcx+19h], 5
0x140006815  jb      short loc_14000682F
0x140006817  mov     rcx, [rcx+10h]
0x14000681b  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140006822  mov     edx, 40h ; '@'
0x140006827  mov     r9d, ebx
0x14000682a  call    WPP_SF_d
0x14000682f  mov     rsi, [rsp+28h+arg_8]
0x140006834  mov     eax, ebx
0x140006836  mov     rbx, [rsp+28h+arg_0]
0x14000683b  add     rsp, 20h
0x14000683f  pop     rdi
0x140006840  retn
```
