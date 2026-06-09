# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x140002970`
- end: `0x140002b31`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `449`
- prototype: `ATL::CSid *(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *, UCHAR, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022d0`

## callees

- `0x140002970`
- `0x140007298`
- `0x1400072bc`
- `0x140007468`
- `0x14000a2d0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140002ab6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140002ab6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002ac5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002ac5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002adf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002adf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140002a9b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140002a9b`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x140002a63`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x140002a63`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x140002a43`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x140002a43`

## pseudocode

```c
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, ...)
{
  va_list v5; // rbp
  DWORD i; // ebx
  DWORD v7; // edi
  DWORD LengthSid; // eax
  int Error; // eax
  _BYTE Sid[80]; // [rsp+30h] [rbp-88h] BYREF
  va_list va; // [rsp+D8h] [rbp+20h] BYREF

  va_start(va, a3);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  *((_QWORD *)this + 11) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 12) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 13) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 14) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !a3 || GetSidLengthRequired(a3) > 0x44 )
    goto LABEL_10;
  if ( !InitializeSid(Sid, a2, a3) )
    ATL::AtlThrowLastWin32();
  va_copy(v5, va);
  for ( i = 0; i < a3; *GetSidSubAuthority(Sid, i++) = v7 )
  {
    v5 += 8;
    v7 = *((_DWORD *)v5 - 2);
  }
  if ( !IsValidSid(Sid) || (LengthSid = GetLengthSid(Sid), LengthSid > 0x44) )
LABEL_10:
    ATL::PrivateAtlThrow(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, Sid) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::PrivateAtlThrow(Error);
  }
  *((_DWORD *)this + 20) = 8;
  return this;
}

```

## disassembly

```asm
0x140002970  mov     [rsp+arg_10], r8b
0x140002975  mov     [rsp+arg_18], r9
0x14000297a  push    rbx
0x14000297b  push    rbp
0x14000297c  push    rsi
0x14000297d  push    rdi
0x14000297e  sub     rsp, 98h
0x140002985  mov     rax, cs:__security_cookie
0x14000298c  xor     rax, rsp
0x14000298f  mov     [rsp+0B8h+var_38], rax
0x140002997  mov     rbx, rdx
0x14000299a  mov     rsi, rcx
0x14000299d  mov     [rsp+0B8h+var_98], rcx
0x1400029a2  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x1400029a9  mov     [rcx], rax
0x1400029ac  mov     byte ptr [rcx+4Ch], 0
0x1400029b0  mov     dword ptr [rcx+50h], 7
0x1400029b7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400029be  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400029c5  mov     rax, [rax+18h]
0x1400029c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029ce  add     rax, 18h
0x1400029d2  mov     [rsi+58h], rax
0x1400029d6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400029dd  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400029e4  mov     rax, [rax+18h]
0x1400029e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029ed  add     rax, 18h
0x1400029f1  mov     [rsi+60h], rax
0x1400029f5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400029fc  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140002a03  mov     rax, [rax+18h]
0x140002a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a0c  add     rax, 18h
0x140002a10  mov     [rsi+68h], rax
0x140002a14  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140002a1b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140002a22  mov     rax, [rax+18h]
0x140002a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a2b  add     rax, 18h
0x140002a2f  mov     [rsi+70h], rax
0x140002a33  movzx   ecx, [rsp+0B8h+arg_10]; nSubAuthorityCount
0x140002a3b  test    cl, cl
0x140002a3d  jz      loc_140002B0F
0x140002a43  call    cs:__imp_GetSidLengthRequired
0x140002a49  cmp     eax, 44h ; 'D'
0x140002a4c  ja      loc_140002B0F
0x140002a52  movzx   r8d, [rsp+0B8h+arg_10]; nSubAuthorityCount
0x140002a5b  mov     rdx, rbx; pIdentifierAuthority
0x140002a5e  lea     rcx, [rsp+0B8h+Sid]; Sid
0x140002a63  call    cs:__imp_InitializeSid
0x140002a69  test    eax, eax
0x140002a6b  jz      loc_140002B1A
0x140002a71  mov     [rsp+0B8h+var_90], 0
0x140002a7a  lea     rbp, [rsp+0B8h+arg_18]
0x140002a82  xor     ebx, ebx
0x140002a84  cmp     [rsp+0B8h+arg_10], bl
0x140002a8b  jbe     short loc_140002AB1
0x140002a8d  lea     rbp, [rbp+8]
0x140002a91  mov     edi, [rbp-8]
0x140002a94  mov     edx, ebx; nSubAuthority
0x140002a96  lea     rcx, [rsp+0B8h+Sid]; pSid
0x140002a9b  call    cs:__imp_GetSidSubAuthority
0x140002aa1  mov     [rax], edi
0x140002aa3  inc     ebx
0x140002aa5  movzx   eax, [rsp+0B8h+arg_10]
0x140002aad  cmp     ebx, eax
0x140002aaf  jb      short loc_140002A8D
0x140002ab1  lea     rcx, [rsp+0B8h+Sid]; pSid
0x140002ab6  call    cs:__imp_IsValidSid
0x140002abc  test    eax, eax
0x140002abe  jz      short loc_140002B0F
0x140002ac0  lea     rcx, [rsp+0B8h+Sid]; pSid
0x140002ac5  call    cs:__imp_GetLengthSid
0x140002acb  cmp     eax, 44h ; 'D'
0x140002ace  ja      short loc_140002B0F
0x140002ad0  mov     byte ptr [rsi+4Ch], 1
0x140002ad4  lea     rdx, [rsi+8]; pDestinationSid
0x140002ad8  lea     r8, [rsp+0B8h+Sid]; pSourceSid
0x140002add  mov     ecx, eax; nDestinationSidLength
0x140002adf  call    cs:__imp_CopySid
0x140002ae5  test    eax, eax
0x140002ae7  jz      short loc_140002B20
0x140002ae9  mov     dword ptr [rsi+50h], 8
0x140002af0  mov     rax, rsi
0x140002af3  mov     rcx, [rsp+0B8h+var_38]
0x140002afb  xor     rcx, rsp; StackCookie
0x140002afe  call    __security_check_cookie
0x140002b03  add     rsp, 98h
0x140002b0a  pop     rdi
0x140002b0b  pop     rsi
0x140002b0c  pop     rbp
0x140002b0d  pop     rbx
0x140002b0e  retn
0x140002b0f  mov     ecx, 80070057h; int
0x140002b14  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140002b1a  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140002b20  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140002b25  mov     byte ptr [rsi+4Ch], 0
0x140002b29  mov     ecx, eax; int
0x140002b2b  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
