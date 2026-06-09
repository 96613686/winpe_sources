# User::IsServiceSid(void)

- ea: `0x18002afb0`
- end: `0x18002b0f8`
- name: `?IsServiceSid@User@@QEBA_NXZ`
- size: `328`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ad84`

## callees

- `0x180008e40`
- `0x18002afb0`
- `0x18003b51c`
- `0x18004e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b03c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b03c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002afcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002afcd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002b022`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002b022`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002aff2`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002aff2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002b0d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002b0d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall User::IsServiceSid(User *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  void *v4; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v6; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  char v8; // di
  int updated; // edi
  __int64 v11; // r8
  PDWORD SidSubAuthority; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v14; // [rsp+28h] [rbp-40h]
  __int64 *v15; // [rsp+30h] [rbp-38h]
  __int64 v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h]
  int v18; // [rsp+48h] [rbp-20h]
  __int64 v19; // [rsp+4Ch] [rbp-1Ch]

  v2 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v3 = *(_QWORD *)this;
  if ( !*(_QWORD *)this || *(_BYTE *)v3 )
    goto LABEL_10;
  if ( !*(_QWORD *)(v3 + 32) )
  {
    updated = User::UpdateEntry(this);
    if ( updated < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v11, (unsigned int)updated);
      }
      v14 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v15 = &qword_180077320;
      v16 = 0;
      v17 = 0;
      v18 = updated;
      v19 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  v4 = *(void **)(*(_QWORD *)this + 32LL);
  SidIdentifierAuthority = GetSidIdentifierAuthority(v4);
  if ( !SidIdentifierAuthority )
    goto LABEL_10;
  v6 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v6 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 1280;
  if ( !v6
    && (SidSubAuthorityCount = GetSidSubAuthorityCount(v4)) != 0
    && *SidSubAuthorityCount == 6
    && (SidSubAuthority = GetSidSubAuthority(v4, 0)) != 0
    && *SidSubAuthority == 80 )
  {
    v8 = 1;
  }
  else
  {
LABEL_10:
    v8 = 0;
  }
  LeaveCriticalSection(v2);
  return v8;
}

```

## disassembly

```asm
0x18002afb0  push    rbp
0x18002afb2  push    rbx
0x18002afb3  push    rsi
0x18002afb4  push    rdi
0x18002afb5  mov     rbp, rsp
0x18002afb8  sub     rsp, 68h
0x18002afbc  mov     rsi, rcx
0x18002afbf  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002afc6  mov     [rbp+arg_0], rbx
0x18002afca  mov     rcx, rbx; lpCriticalSection
0x18002afcd  call    cs:__imp_EnterCriticalSection
0x18002afd3  nop
0x18002afd4  mov     rax, [rsi]
0x18002afd7  test    rax, rax
0x18002afda  jz      short loc_18002B036
0x18002afdc  cmp     byte ptr [rax], 0
0x18002afdf  jnz     short loc_18002B036
0x18002afe1  cmp     qword ptr [rax+20h], 0
0x18002afe6  jz      short loc_18002B04E
0x18002afe8  mov     rax, [rsi]
0x18002afeb  mov     rdi, [rax+20h]
0x18002afef  mov     rcx, rdi; pSid
0x18002aff2  call    cs:__imp_GetSidIdentifierAuthority
0x18002aff8  test    rax, rax
0x18002affb  jz      short loc_18002B036
0x18002affd  mov     dword ptr [rbp+arg_0], 0
0x18002b004  mov     word ptr [rbp+arg_0+4], 500h
0x18002b00a  mov     ecx, [rax]
0x18002b00c  sub     ecx, dword ptr [rbp+arg_0]
0x18002b00f  jnz     short loc_18002B01B
0x18002b011  movzx   ecx, word ptr [rax+4]
0x18002b015  movzx   eax, word ptr [rbp+arg_0+4]
0x18002b019  sub     ecx, eax
0x18002b01b  test    ecx, ecx
0x18002b01d  jnz     short loc_18002B036
0x18002b01f  mov     rcx, rdi; pSid
0x18002b022  call    cs:__imp_GetSidSubAuthorityCount
0x18002b028  test    rax, rax
0x18002b02b  jz      short loc_18002B036
0x18002b02d  cmp     byte ptr [rax], 6
0x18002b030  jz      loc_18002B0D2
0x18002b036  xor     dil, dil
0x18002b039  mov     rcx, rbx; lpCriticalSection
0x18002b03c  call    cs:__imp_LeaveCriticalSection
0x18002b042  mov     al, dil
0x18002b045  add     rsp, 68h
0x18002b049  pop     rdi
0x18002b04a  pop     rsi
0x18002b04b  pop     rbx
0x18002b04c  pop     rbp
0x18002b04d  retn
0x18002b04e  mov     rcx, rsi; this
0x18002b051  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002b056  mov     edi, eax
0x18002b058  test    eax, eax
0x18002b05a  jns     short loc_18002AFE8
0x18002b05c  lea     rax, WPP_GLOBAL_Control
0x18002b063  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b06a  cmp     rcx, rax
0x18002b06d  jz      short loc_18002B08C
0x18002b06f  test    byte ptr [rcx+1Ch], 80h
0x18002b073  jz      short loc_18002B08C
0x18002b075  cmp     byte ptr [rcx+19h], 2
0x18002b079  jb      short loc_18002B08C
0x18002b07b  mov     edx, 1Fh
0x18002b080  mov     r9d, edi
0x18002b083  mov     rcx, [rcx+10h]
0x18002b087  call    WPP_SF_d
0x18002b08c  mov     [rbp+var_40], 0
0x18002b090  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002b097  mov     [rbp+pExceptionObject], rax
0x18002b09b  lea     rax, qword_180077320
0x18002b0a2  mov     [rbp+var_38], rax
0x18002b0a6  mov     [rbp+var_30], 0
0x18002b0ae  mov     [rbp+var_28], 0
0x18002b0b6  mov     [rbp+var_20], edi
0x18002b0b9  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002b0c1  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002b0c8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002b0cc  call    _CxxThrowException_0
0x18002b0d2  xor     edx, edx; nSubAuthority
0x18002b0d4  mov     rcx, rdi; pSid
0x18002b0d7  call    cs:__imp_GetSidSubAuthority
0x18002b0dd  test    rax, rax
0x18002b0e0  jz      loc_18002B036
0x18002b0e6  cmp     dword ptr [rax], 50h ; 'P'
0x18002b0e9  jnz     loc_18002B036
0x18002b0ef  mov     dil, 1
0x18002b0f2  jmp     loc_18002B039
```
