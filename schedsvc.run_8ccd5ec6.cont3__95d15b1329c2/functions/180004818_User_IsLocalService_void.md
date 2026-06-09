# User::IsLocalService(void)

- ea: `0x180004818`
- end: `0x180004954`
- name: `?IsLocalService@User@@QEBA_NXZ`
- size: `316`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180003310`
- `0x180006a10`
- `0x180006a74`
- `0x180006ac0`
- `0x180053394`

## callees

- `0x180004818`
- `0x180056954`
- `0x18005a2bc`
- `0x18006acbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000491f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000491f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004933`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004839`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004839`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180004909`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180004909`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall User::IsLocalService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  int updated; // edi
  bool v5; // di
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v8; // [rsp+28h] [rbp-40h]
  const unsigned __int16 *v9; // [rsp+30h] [rbp-38h]
  __int64 v10; // [rsp+38h] [rbp-30h]
  __int64 v11; // [rsp+40h] [rbp-28h]
  int v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+4Ch] [rbp-1Ch]

  v2 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v3 = *(_QWORD *)this;
  if ( !*(_QWORD *)this || *(_BYTE *)v3 )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    if ( !*(_QWORD *)(v3 + 32) )
    {
      updated = User::UpdateEntry(this);
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
            (unsigned int)updated);
        }
        v8 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v9 = &qword_1800A8718;
        v10 = 0;
        v11 = 0;
        v12 = updated;
        v13 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
    }
    v5 = IsWellKnownSid(*(PSID *)(*(_QWORD *)this + 32LL), WinLocalServiceSid);
    LeaveCriticalSection(v2);
    return v5;
  }
}

```

## disassembly

```asm
0x180004818  mov     [rsp+arg_8], rbx
0x18000481d  mov     [rsp+arg_10], rsi
0x180004822  push    rdi
0x180004823  sub     rsp, 60h
0x180004827  mov     rsi, rcx
0x18000482a  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180004831  mov     [rsp+68h+arg_0], rbx
0x180004836  mov     rcx, rbx; lpCriticalSection
0x180004839  call    cs:__imp_EnterCriticalSection
0x180004840  nop     dword ptr [rax+rax+00h]
0x180004845  nop
0x180004846  mov     rax, [rsi]
0x180004849  test    rax, rax
0x18000484c  jz      loc_180004930
0x180004852  cmp     byte ptr [rax], 0
0x180004855  jnz     loc_180004930
0x18000485b  cmp     qword ptr [rax+20h], 0
0x180004860  jnz     loc_1800048FD
0x180004866  mov     rcx, rsi; this
0x180004869  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18000486e  mov     edi, eax
0x180004870  test    eax, eax
0x180004872  jns     loc_1800048FD
0x180004878  lea     rax, WPP_GLOBAL_Control
0x18000487f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004886  cmp     rcx, rax
0x180004889  jz      short loc_1800048AF
0x18000488b  test    byte ptr [rcx+1Ch], 80h
0x18000488f  jz      short loc_1800048AF
0x180004891  cmp     byte ptr [rcx+19h], 2
0x180004895  jb      short loc_1800048AF
0x180004897  mov     edx, 1Dh
0x18000489c  mov     r9d, edi
0x18000489f  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800048a6  mov     rcx, [rcx+10h]
0x1800048aa  call    WPP_SF_d
0x1800048af  mov     [rsp+68h+var_40], 0
0x1800048b4  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800048bb  mov     [rsp+68h+pExceptionObject], rax
0x1800048c0  lea     rax, qword_1800A8718
0x1800048c7  mov     [rsp+68h+var_38], rax
0x1800048cc  mov     [rsp+68h+var_30], 0
0x1800048d5  mov     [rsp+68h+var_28], 0
0x1800048de  mov     [rsp+68h+var_20], edi
0x1800048e2  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x1800048eb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800048f2  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800048f7  call    _CxxThrowException_0
0x1800048fd  mov     rax, [rsi]
0x180004900  mov     edx, 17h; WellKnownSidType
0x180004905  mov     rcx, [rax+20h]; pSid
0x180004909  call    cs:__imp_IsWellKnownSid
0x180004910  nop     dword ptr [rax+rax+00h]
0x180004915  nop
0x180004916  test    eax, eax
0x180004918  setnz   dil
0x18000491c  mov     rcx, rbx; lpCriticalSection
0x18000491f  call    cs:__imp_LeaveCriticalSection
0x180004926  nop     dword ptr [rax+rax+00h]
0x18000492b  mov     al, dil
0x18000492e  jmp     short loc_180004941
0x180004930  mov     rcx, rbx; lpCriticalSection
0x180004933  call    cs:__imp_LeaveCriticalSection
0x18000493a  nop     dword ptr [rax+rax+00h]
0x18000493f  xor     al, al
0x180004941  lea     r11, [rsp+68h+var_8]
0x180004946  mov     rbx, [r11+18h]
0x18000494a  mov     rsi, [r11+20h]
0x18000494e  mov     rsp, r11
0x180004951  pop     rdi
0x180004952  retn
```
