# User::IsNetworkService(void)

- ea: `0x18001a808`
- end: `0x18001a91f`
- name: `?IsNetworkService@User@@QEBA_NXZ`
- size: `279`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a928`
- `0x18001ad80`

## callees

- `0x18000878c`
- `0x18000c760`
- `0x18001a808`
- `0x18001aacc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a82b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a82b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a8f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a905`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a8f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a905`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a8e7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a8e7`

## pseudocode

```c
bool __fastcall User::IsNetworkService(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // edi
  bool v4; // di
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v7; // [rsp+28h] [rbp-38h]
  char *v8; // [rsp+30h] [rbp-30h]
  __int64 v9; // [rsp+38h] [rbp-28h]
  __int64 v10; // [rsp+40h] [rbp-20h]
  int v11; // [rsp+48h] [rbp-18h]
  __int64 v12; // [rsp+4Ch] [rbp-14h]
  PSID pSid; // [rsp+70h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v14; // [rsp+78h] [rbp+18h]

  v2 = User::s_cs;
  v14 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this || **(_BYTE **)this )
  {
    LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    pSid = 0;
    v3 = User::LookupSid(this, &pSid);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids,
          (unsigned int)v3);
      }
      v7 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v8 = byte_1800505F8;
      v9 = 0;
      v10 = 0;
      v11 = v3;
      v12 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v4 = IsWellKnownSid(pSid, WinNetworkServiceSid);
    LeaveCriticalSection(v2);
    return v4;
  }
}

```

## disassembly

```asm
0x18001a808  mov     [rsp-8+arg_10], rbx
0x18001a80d  mov     [rsp-8+arg_18], rdi
0x18001a812  push    rbp
0x18001a813  mov     rbp, rsp
0x18001a816  sub     rsp, 60h
0x18001a81a  mov     rdi, rcx
0x18001a81d  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001a824  mov     [rbp+arg_8], rbx
0x18001a828  mov     rcx, rbx; lpCriticalSection
0x18001a82b  call    cs:__imp_EnterCriticalSection
0x18001a831  nop
0x18001a832  mov     rax, [rdi]
0x18001a835  test    rax, rax
0x18001a838  jz      loc_18001A902
0x18001a83e  cmp     byte ptr [rax], 0
0x18001a841  jnz     loc_18001A902
0x18001a847  mov     [rbp+pSid], 0
0x18001a84f  lea     rdx, [rbp+pSid]; void **
0x18001a853  mov     rcx, rdi; this
0x18001a856  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18001a85b  mov     edi, eax
0x18001a85d  test    eax, eax
0x18001a85f  jns     short loc_18001A8DE
0x18001a861  lea     rax, WPP_GLOBAL_Control
0x18001a868  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a86f  cmp     rcx, rax
0x18001a872  jz      short loc_18001A898
0x18001a874  test    byte ptr [rcx+1Ch], 80h
0x18001a878  jz      short loc_18001A898
0x18001a87a  cmp     byte ptr [rcx+19h], 2
0x18001a87e  jb      short loc_18001A898
0x18001a880  mov     edx, 1Eh
0x18001a885  mov     r9d, edi
0x18001a888  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001a88f  mov     rcx, [rcx+10h]
0x18001a893  call    WPP_SF_d
0x18001a898  mov     [rbp+var_38], 0
0x18001a89c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001a8a3  mov     [rbp+pExceptionObject], rax
0x18001a8a7  lea     rax, byte_1800505F8
0x18001a8ae  mov     [rbp+var_30], rax
0x18001a8b2  mov     [rbp+var_28], 0
0x18001a8ba  mov     [rbp+var_20], 0
0x18001a8c2  mov     [rbp+var_18], edi
0x18001a8c5  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001a8cd  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001a8d4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a8d8  call    _CxxThrowException_0
0x18001a8de  mov     edx, 18h; WellKnownSidType
0x18001a8e3  mov     rcx, [rbp+pSid]; pSid
0x18001a8e7  call    cs:__imp_IsWellKnownSid
0x18001a8ed  nop
0x18001a8ee  test    eax, eax
0x18001a8f0  setnz   dil
0x18001a8f4  mov     rcx, rbx; lpCriticalSection
0x18001a8f7  call    cs:__imp_LeaveCriticalSection
0x18001a8fd  mov     al, dil
0x18001a900  jmp     short loc_18001A90D
0x18001a902  mov     rcx, rbx; lpCriticalSection
0x18001a905  call    cs:__imp_LeaveCriticalSection
0x18001a90b  xor     al, al
0x18001a90d  lea     r11, [rsp+60h+var_s0]
0x18001a912  mov     rbx, [r11+20h]
0x18001a916  mov     rdi, [r11+28h]
0x18001a91a  mov     rsp, r11
0x18001a91d  pop     rbp
0x18001a91e  retn
```
