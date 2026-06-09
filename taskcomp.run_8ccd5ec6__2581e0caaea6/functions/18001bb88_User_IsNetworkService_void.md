# User::IsNetworkService(void)

- ea: `0x18001bb88`
- end: `0x18001bcba`
- name: `?IsNetworkService@User@@QEBA_NXZ`
- size: `306`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001bcc0`
- `0x18001c21c`

## callees

- `0x180008c4c`
- `0x18000cf80`
- `0x180018534`
- `0x18001bb88`
- `0x18001be88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc99`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001bc6f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001bc6f`

## pseudocode

```c
bool __fastcall User::IsNetworkService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  User *v3; // rcx
  int v4; // edi
  bool v5; // di
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v8; // [rsp+28h] [rbp-38h]
  char *v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+38h] [rbp-28h]
  __int64 v11; // [rsp+40h] [rbp-20h]
  int v12; // [rsp+48h] [rbp-18h]
  __int64 v13; // [rsp+4Ch] [rbp-14h]
  PSID pSid; // [rsp+70h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v15; // [rsp+78h] [rbp+18h]

  v2 = User::s_cs;
  v15 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this || User::IsAlias(this) )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    pSid = 0;
    v4 = User::LookupSid(v3, &pSid);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
          (unsigned int)v4);
      }
      v8 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v9 = byte_180052608;
      v10 = 0;
      v11 = 0;
      v12 = v4;
      v13 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v5 = IsWellKnownSid(pSid, WinNetworkServiceSid);
    LeaveCriticalSection(v2);
    return v5;
  }
}

```

## disassembly

```asm
0x18001bb88  mov     [rsp-8+arg_10], rbx
0x18001bb8d  mov     [rsp-8+arg_18], rdi
0x18001bb92  push    rbp
0x18001bb93  mov     rbp, rsp
0x18001bb96  sub     rsp, 60h
0x18001bb9a  mov     rdi, rcx
0x18001bb9d  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001bba4  mov     [rbp+arg_8], rbx
0x18001bba8  mov     rcx, rbx; lpCriticalSection
0x18001bbab  call    cs:__imp_EnterCriticalSection
0x18001bbb2  nop     dword ptr [rax+rax+00h]
0x18001bbb7  nop
0x18001bbb8  cmp     qword ptr [rdi], 0
0x18001bbbc  jz      loc_18001BC96
0x18001bbc2  mov     rcx, rdi; this
0x18001bbc5  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x18001bbca  test    al, al
0x18001bbcc  jnz     loc_18001BC96
0x18001bbd2  mov     [rbp+pSid], 0
0x18001bbda  lea     rdx, [rbp+pSid]; void **
0x18001bbde  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18001bbe3  mov     edi, eax
0x18001bbe5  test    eax, eax
0x18001bbe7  jns     short loc_18001BC66
0x18001bbe9  lea     rax, WPP_GLOBAL_Control
0x18001bbf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbf7  cmp     rcx, rax
0x18001bbfa  jz      short loc_18001BC20
0x18001bbfc  test    byte ptr [rcx+1Ch], 80h
0x18001bc00  jz      short loc_18001BC20
0x18001bc02  cmp     byte ptr [rcx+19h], 2
0x18001bc06  jb      short loc_18001BC20
0x18001bc08  mov     edx, 1Eh
0x18001bc0d  mov     r9d, edi
0x18001bc10  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001bc17  mov     rcx, [rcx+10h]
0x18001bc1b  call    WPP_SF_d
0x18001bc20  mov     [rbp+var_38], 0
0x18001bc24  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001bc2b  mov     [rbp+pExceptionObject], rax
0x18001bc2f  lea     rax, byte_180052608
0x18001bc36  mov     [rbp+var_30], rax
0x18001bc3a  mov     [rbp+var_28], 0
0x18001bc42  mov     [rbp+var_20], 0
0x18001bc4a  mov     [rbp+var_18], edi
0x18001bc4d  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001bc55  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001bc5c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001bc60  call    _CxxThrowException_0
0x18001bc66  mov     edx, 18h; WellKnownSidType
0x18001bc6b  mov     rcx, [rbp+pSid]; pSid
0x18001bc6f  call    cs:__imp_IsWellKnownSid
0x18001bc76  nop     dword ptr [rax+rax+00h]
0x18001bc7b  nop
0x18001bc7c  test    eax, eax
0x18001bc7e  setnz   dil
0x18001bc82  mov     rcx, rbx; lpCriticalSection
0x18001bc85  call    cs:__imp_LeaveCriticalSection
0x18001bc8c  nop     dword ptr [rax+rax+00h]
0x18001bc91  mov     al, dil
0x18001bc94  jmp     short loc_18001BCA7
0x18001bc96  mov     rcx, rbx; lpCriticalSection
0x18001bc99  call    cs:__imp_LeaveCriticalSection
0x18001bca0  nop     dword ptr [rax+rax+00h]
0x18001bca5  xor     al, al
0x18001bca7  lea     r11, [rsp+60h+var_s0]
0x18001bcac  mov     rbx, [r11+20h]
0x18001bcb0  mov     rdi, [r11+28h]
0x18001bcb4  mov     rsp, r11
0x18001bcb7  pop     rbp
0x18001bcb8  retn
```
