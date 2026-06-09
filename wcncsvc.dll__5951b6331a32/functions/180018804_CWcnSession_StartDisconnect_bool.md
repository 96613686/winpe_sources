# CWcnSession::StartDisconnect(bool)

- ea: `0x180018804`
- end: `0x180018a6d`
- name: `?StartDisconnect@CWcnSession@@QEAAX_N@Z`
- size: `617`
- prototype: `void __fastcall(CWcnSession *__hidden this, bool)`
- caller_count: `16`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e5e0`
- `0x180014c64`
- `0x1800157bc`
- `0x180017054`
- `0x180019580`
- `0x18002642c`
- `0x1800361d0`
- `0x1800362c0`
- `0x1800471a0`
- `0x180047a10`
- `0x180047f8c`
- `0x18004a420`
- `0x18004be80`
- `0x18004cd4c`
- `0x18004f4f0`
- `0x180056adc`

## callees

- `0x180004fb8`
- `0x180005088`
- `0x180018804`
- `0x180019808`
- `0x180053004`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018874`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018882`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018874`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018882`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800189ef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800189ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800188d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001896c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800188d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001896c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800188ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800188ad`

## pseudocode

```c
void __fastcall CWcnSession::StartDisconnect(CWcnSession *this, char a2)
{
  bool v4; // di
  const char *Indent; // rax
  __int64 v6; // r10
  __int64 v7; // r8
  __int64 *v8; // rdx
  int v9; // r9d
  _BYTE *v10; // r10
  const char *v11; // rax
  __int64 v12; // r10
  DWORD v13; // eax
  char v14; // di
  unsigned int v15; // eax
  __int64 v16; // r10
  char v17; // r11
  int v18; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-40h] BYREF
  char *v20; // [rsp+48h] [rbp-30h]
  __int64 v21; // [rsp+50h] [rbp-28h]
  int *v22; // [rsp+58h] [rbp-20h]
  __int64 v23; // [rsp+60h] [rbp-18h]

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 32, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
  if ( *((_DWORD *)this + 56) == 2 || *((_DWORD *)this + 56) == 1 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 29), 0, 0, 0);
    v4 = *((_QWORD *)this + 25) != 0;
    *((_DWORD *)this + 56) = 3;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
  if ( v4 )
  {
    if ( *((_DWORD *)this + 5) == 2 || *((int *)this + 6) >= 0 )
    {
      if ( (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 1) == 0 )
        goto LABEL_15;
      v9 = 2;
      v20 = (char *)this + 1576;
      v8 = SessionEndSuccess;
    }
    else
    {
      if ( (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 2) == 0 )
        goto LABEL_15;
      v18 = *((_DWORD *)this + 6);
      v8 = SessionEndFailure;
      v23 = 4;
      v20 = (char *)this + 1576;
      v9 = 3;
      v22 = &v18;
    }
    v21 = 16;
    McGenEventWrite_EtwEventWriteTransfer(WCN_ETW_EVENT_GUID_Context, (__int64)v8, v7, v9, (__int64)v19);
  }
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  if ( v4 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 25) + 24LL))(*((_QWORD *)this + 25));
  if ( a2 )
  {
    while ( *((_DWORD *)this + 56) )
    {
      v13 = WaitForSingleObjectEx(*((HANDLE *)this + 33), 0xFFFFFFFF, 0);
      v14 = v13;
      if ( v13 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = (unsigned int)GetIndent(0);
          WPP_SF_sld(
            *(_QWORD *)(v16 + 16),
            33,
            (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids,
            v15,
            v14,
            v17);
          break;
        }
        goto LABEL_19;
      }
    }
  }
  v10 = WPP_GLOBAL_Control;
LABEL_19:
  if ( v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 6u )
  {
    v11 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 34, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v11);
  }
}

```

## disassembly

```asm
0x180018804  push    rbp
0x180018806  push    rbx
0x180018807  push    rsi
0x180018808  push    rdi
0x180018809  push    r13
0x18001880b  push    r14
0x18001880d  mov     rbp, rsp
0x180018810  sub     rsp, 78h
0x180018814  mov     rax, cs:__security_cookie
0x18001881b  xor     rax, rsp
0x18001881e  mov     [rbp+var_10], rax
0x180018822  mov     r14b, dl
0x180018825  mov     rbx, rcx
0x180018828  xor     dil, dil
0x18001882b  mov     r10, cs:WPP_GLOBAL_Control
0x180018832  lea     rax, WPP_GLOBAL_Control
0x180018839  mov     r13d, 1
0x18001883f  cmp     r10, rax
0x180018842  jz      short loc_18001886A
0x180018844  cmp     byte ptr [r10+19h], 6
0x180018849  jb      short loc_18001886A
0x18001884b  mov     ecx, r13d; int
0x18001884e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018853  mov     rcx, [r10+10h]
0x180018857  lea     edx, [r13+1Fh]
0x18001885b  mov     r9, rax
0x18001885e  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018865  call    WPP_SF_s
0x18001886a  lea     rsi, [rbx+600h]
0x180018871  mov     rcx, rsi; lpCriticalSection
0x180018874  call    cs:__imp_EnterCriticalSection
0x18001887a  mov     rcx, [rbx+20h]
0x18001887e  add     rcx, 10h; lpCriticalSection
0x180018882  call    cs:__imp_EnterCriticalSection
0x180018888  mov     eax, [rbx+0E0h]
0x18001888e  cmp     eax, 2
0x180018891  jz      short loc_18001889E
0x180018893  mov     eax, [rbx+0E0h]
0x180018899  cmp     eax, r13d
0x18001889c  jnz     short loc_1800188CD
0x18001889e  mov     rcx, [rbx+0E8h]; pti
0x1800188a5  xor     r9d, r9d; msWindowLength
0x1800188a8  xor     r8d, r8d; msPeriod
0x1800188ab  xor     edx, edx; pftDueTime
0x1800188ad  call    cs:__imp_SetThreadpoolTimer
0x1800188b3  cmp     qword ptr [rbx+0C8h], 0
0x1800188bb  movzx   edi, dil
0x1800188bf  cmovnz  edi, r13d
0x1800188c3  mov     dword ptr [rbx+0E0h], 3
0x1800188cd  mov     rcx, [rbx+20h]
0x1800188d1  add     rcx, 10h; lpCriticalSection
0x1800188d5  call    cs:__imp_LeaveCriticalSection
0x1800188db  test    dil, dil
0x1800188de  jz      loc_180018969
0x1800188e4  cmp     dword ptr [rbx+14h], 2
0x1800188e8  jz      short loc_18001892B
0x1800188ea  mov     eax, [rbx+18h]
0x1800188ed  test    eax, eax
0x1800188ef  jns     short loc_18001892B
0x1800188f1  test    byte ptr cs:Microsoft_Windows_WCN_Config_RegistrarEnableBits, 2
0x1800188f8  jz      short loc_180018969
0x1800188fa  mov     [rbp+var_48], eax
0x1800188fd  lea     rdx, SessionEndFailure
0x180018904  lea     rax, [rbx+628h]
0x18001890b  mov     [rbp+var_18], 4
0x180018913  mov     [rbp+var_30], rax
0x180018917  mov     r9d, 3
0x18001891d  lea     rax, [rbp+var_48]
0x180018921  mov     [rbp+var_20], rax
0x180018925  lea     rax, [rbp+var_40]
0x180018929  jmp     short loc_180018950
0x18001892b  test    byte ptr cs:Microsoft_Windows_WCN_Config_RegistrarEnableBits, r13b
0x180018932  jz      short loc_180018969
0x180018934  lea     rax, [rbx+628h]
0x18001893b  mov     r9d, 2
0x180018941  mov     [rbp+var_30], rax
0x180018945  lea     rdx, SessionEndSuccess
0x18001894c  lea     rax, [rbp+var_40]
0x180018950  lea     rcx, WCN_ETW_EVENT_GUID_Context
0x180018957  mov     [rsp+78h+var_58], rax
0x18001895c  mov     [rbp+var_28], 10h
0x180018964  call    McGenEventWrite_EtwEventWriteTransfer
0x180018969  mov     rcx, rsi; lpCriticalSection
0x18001896c  call    cs:__imp_LeaveCriticalSection
0x180018972  test    dil, dil
0x180018975  jz      short loc_18001898A
0x180018977  mov     rcx, [rbx+0C8h]
0x18001897e  mov     rax, [rcx]
0x180018981  mov     rax, [rax+18h]
0x180018985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001898a  test    r14b, r14b
0x18001898d  jnz     short loc_1800189FB
0x18001898f  lea     rsi, WPP_GLOBAL_Control
0x180018996  mov     r10, cs:WPP_GLOBAL_Control
0x18001899d  cmp     r10, rsi
0x1800189a0  jz      short loc_1800189C9
0x1800189a2  cmp     byte ptr [r10+19h], 6
0x1800189a7  jb      short loc_1800189C9
0x1800189a9  or      ecx, 0FFFFFFFFh; int
0x1800189ac  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800189b1  mov     rcx, [r10+10h]
0x1800189b5  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800189bc  mov     edx, 22h ; '"'
0x1800189c1  mov     r9, rax
0x1800189c4  call    WPP_SF_s
0x1800189c9  mov     rcx, [rbp+var_10]
0x1800189cd  xor     rcx, rsp; StackCookie
0x1800189d0  call    __security_check_cookie
0x1800189d5  add     rsp, 78h
0x1800189d9  pop     r14
0x1800189db  pop     r13
0x1800189dd  pop     rdi
0x1800189de  pop     rsi
0x1800189df  pop     rbx
0x1800189e0  pop     rbp
0x1800189e1  retn
0x1800189e2  mov     rcx, [rbx+108h]; hHandle
0x1800189e9  xor     r8d, r8d; bAlertable
0x1800189ec  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800189ef  call    cs:__imp_WaitForSingleObjectEx
0x1800189f5  mov     edi, eax
0x1800189f7  test    eax, eax
0x1800189f9  jnz     short loc_180018A07
0x1800189fb  mov     eax, [rbx+0E0h]
0x180018a01  test    eax, eax
0x180018a03  jnz     short loc_1800189E2
0x180018a05  jmp     short loc_18001898F
0x180018a07  mov     r10, cs:WPP_GLOBAL_Control
0x180018a0e  lea     rsi, WPP_GLOBAL_Control
0x180018a15  cmp     r10, rsi
0x180018a18  jz      short loc_1800189C9
0x180018a1a  cmp     byte ptr [r10+19h], 2
0x180018a1f  jb      loc_18001899D
0x180018a25  mov     r11d, [rbx+10h]
0x180018a29  test    r11d, r11d
0x180018a2c  jle     short loc_180018A39
0x180018a2e  movzx   r11d, r11w
0x180018a32  or      r11d, 80070000h
0x180018a39  xor     ecx, ecx; int
0x180018a3b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180018a40  mov     rcx, [r10+10h]
0x180018a44  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180018a4b  or      r11d, 80000000h
0x180018a52  mov     edx, 21h ; '!'
0x180018a57  mov     [rsp+78h+var_50], r11d
0x180018a5c  mov     r9, rax
0x180018a5f  mov     dword ptr [rsp+78h+var_58], edi
0x180018a63  call    WPP_SF_sld
0x180018a68  jmp     loc_180018996
```
