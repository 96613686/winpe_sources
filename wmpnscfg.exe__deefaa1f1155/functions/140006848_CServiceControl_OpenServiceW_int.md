# CServiceControl::OpenServiceW(int)

- ea: `0x140006848`
- end: `0x140006972`
- name: `?OpenServiceW@CServiceControl@@AEAAHH@Z`
- size: `298`
- prototype: `__int64 __fastcall(CServiceControl *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1400065cc`

## callees

- `0x1400053b4`
- `0x1400053dc`
- `0x140006764`
- `0x140006848`
- `0x140006978`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x1400068f2`
- `ADVAPI32!OpenServiceW` at `0x1400068f2`
- `KERNEL32!GetLastError` at `0x140006903`
- `KERNEL32!GetLastError` at `0x140006903`

## pseudocode

```c
__int64 __fastcall CServiceControl::OpenServiceW(CServiceControl *this)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // eax
  SC_HANDLE v5; // rax
  DWORD LastError; // eax
  __int64 v7; // r8

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 1;
  if ( *((_QWORD *)this + 2) )
    goto LABEL_16;
  v4 = CServiceControl::OpenServiceManager(this);
  v3 = v4;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_cb23d491edf93b904e2862226171c496_Traceguids, v4);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v3 != 1 )
    goto LABEL_16;
  v5 = OpenServiceW(*((SC_HANDLE *)this + 1), *(LPCWSTR *)this, 0x115u);
  *((_QWORD *)this + 2) = v5;
  if ( v5 )
    goto LABEL_15;
  v3 = 0;
  LastError = GetLastError();
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v7, LastError);
LABEL_15:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_16:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_d(v2[2], 58, &WPP_cb23d491edf93b904e2862226171c496_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x140006848  mov     [rsp+arg_0], rbx
0x14000684d  mov     [rsp+arg_8], rbp
0x140006852  push    rdi
0x140006853  sub     rsp, 20h
0x140006857  mov     rdi, rcx
0x14000685a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006861  lea     rbp, WPP_GLOBAL_Control
0x140006868  cmp     rcx, rbp
0x14000686b  jz      short loc_14000688F
0x14000686d  test    byte ptr [rcx+1Ch], 1
0x140006871  jz      short loc_14000688F
0x140006873  mov     rcx, [rcx+10h]
0x140006877  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x14000687e  mov     edx, 37h ; '7'
0x140006883  call    WPP_SF_
0x140006888  mov     rcx, cs:WPP_GLOBAL_Control
0x14000688f  cmp     qword ptr [rdi+10h], 0
0x140006894  mov     ebx, 1
0x140006899  jnz     loc_140006937
0x14000689f  mov     rcx, rdi; this
0x1400068a2  call    ?OpenServiceManager@CServiceControl@@AEAAHXZ; CServiceControl::OpenServiceManager(void)
0x1400068a7  mov     ebx, eax
0x1400068a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068b0  cmp     rcx, rbp
0x1400068b3  jz      short loc_1400068E0
0x1400068b5  test    byte ptr [rcx+1Ch], 2
0x1400068b9  jz      short loc_1400068E0
0x1400068bb  cmp     byte ptr [rcx+19h], 4
0x1400068bf  jb      short loc_1400068E0
0x1400068c1  mov     rcx, [rcx+10h]
0x1400068c5  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x1400068cc  mov     edx, 38h ; '8'
0x1400068d1  mov     r9d, eax
0x1400068d4  call    WPP_SF_d
0x1400068d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068e0  cmp     ebx, 1
0x1400068e3  jnz     short loc_140006937
0x1400068e5  mov     rdx, [rdi]; lpServiceName
0x1400068e8  mov     r8d, 115h; dwDesiredAccess
0x1400068ee  mov     rcx, [rdi+8]; hSCManager
0x1400068f2  call    cs:__imp_OpenServiceW
0x1400068f8  mov     [rdi+10h], rax
0x1400068fc  test    rax, rax
0x1400068ff  jnz     short loc_140006930
0x140006901  xor     ebx, ebx
0x140006903  call    cs:__imp_GetLastError
0x140006909  mov     rcx, cs:WPP_GLOBAL_Control
0x140006910  cmp     rcx, rbp
0x140006913  jz      short loc_140006960
0x140006915  test    byte ptr [rcx+1Ch], 2
0x140006919  jz      short loc_140006937
0x14000691b  cmp     byte ptr [rcx+19h], 4
0x14000691f  jb      short loc_140006937
0x140006921  mov     rcx, [rcx+10h]
0x140006925  lea     edx, [rbx+39h]
0x140006928  mov     r9d, eax
0x14000692b  call    WPP_SF_D
0x140006930  mov     rcx, cs:WPP_GLOBAL_Control
0x140006937  cmp     rcx, rbp
0x14000693a  jz      short loc_140006960
0x14000693c  test    byte ptr [rcx+1Ch], 1
0x140006940  jz      short loc_140006960
0x140006942  cmp     byte ptr [rcx+19h], 5
0x140006946  jb      short loc_140006960
0x140006948  mov     rcx, [rcx+10h]
0x14000694c  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140006953  mov     edx, 3Ah ; ':'
0x140006958  mov     r9d, ebx
0x14000695b  call    WPP_SF_d
0x140006960  mov     rbp, [rsp+28h+arg_8]
0x140006965  mov     eax, ebx
0x140006967  mov     rbx, [rsp+28h+arg_0]
0x14000696c  add     rsp, 20h
0x140006970  pop     rdi
0x140006971  retn
```
