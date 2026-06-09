# CBioTraceLogging::GetIdentityFromSid(ushort const *,_WINBIO_IDENTITY *)

- ea: `0x1800806d4`
- end: `0x18008076f`
- name: `?GetIdentityFromSid@CBioTraceLogging@@CAJPEBGPEAU_WINBIO_IDENTITY@@@Z`
- size: `155`
- prototype: `static int(const unsigned __int16 *, struct _WINBIO_IDENTITY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180080448`
- `0x18008053c`

## callees

- `0x18005388c`
- `0x180056358`
- `0x1800806d4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180080742`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180080742`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180080758`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180080758`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180080712`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180080712`

## string_xrefs

- `0x1800806e7`: `onecore\ds\security\biometrics\service\server\biotracelogging.cpp`
- `0x180080726`: `onecore\ds\security\biometrics\service\server\biotracelogging.cpp`

## pseudocode

```c
__int64 __fastcall CBioTraceLogging::GetIdentityFromSid(const unsigned __int16 *a1, struct _WINBIO_IDENTITY *a2)
{
  __int64 result; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
      (const char *)0x80004003LL,
      v6);
    return 2147500035LL;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(a1, &Sid) )
  {
    v5 = 1220;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
             v4);
  }
  if ( !CopySid(0x44u, a2->Value.AccountSid.Data, Sid) )
  {
    v5 = 1221;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
             v4);
  }
  a2->Value.Null = GetLengthSid(Sid);
  result = 0;
  a2->Type = 3;
  return result;
}

```

## disassembly

```asm
0x1800806d4  push    rbx; int
0x1800806d6  sub     rsp, 20h
0x1800806da  mov     rbx, rdx
0x1800806dd  test    rdx, rdx
0x1800806e0  jnz     short loc_180080704
0x1800806e2  mov     rcx, [rsp+28h]; this
0x1800806e7  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\biometrics\\serv"...
0x1800806ee  mov     ebx, 80004003h
0x1800806f3  mov     edx, 4C2h; void *
0x1800806f8  mov     r9d, ebx; char *
0x1800806fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080700  mov     eax, ebx
0x180080702  jmp     short loc_180080769
0x180080704  lea     rdx, [rsp+28h+Sid]; Sid
0x180080709  mov     [rsp+28h+Sid], 0
0x180080712  call    cs:__imp_ConvertStringSidToSidW
0x180080718  test    eax, eax
0x18008071a  jnz     short loc_180080734
0x18008071c  mov     edx, 4C4h; void *
0x180080721  mov     rcx, [rsp+28h]; this
0x180080726  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\biometrics\\serv"...
0x18008072d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180080732  jmp     short loc_180080769
0x180080734  mov     r8, [rsp+28h+Sid]; pSourceSid
0x180080739  lea     rdx, [rbx+8]; pDestinationSid
0x18008073d  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180080742  call    cs:__imp_CopySid
0x180080748  test    eax, eax
0x18008074a  jnz     short loc_180080753
0x18008074c  mov     edx, 4C5h
0x180080751  jmp     short loc_180080721
0x180080753  mov     rcx, [rsp+28h+Sid]; pSid
0x180080758  call    cs:__imp_GetLengthSid
0x18008075e  mov     [rbx+4], eax
0x180080761  xor     eax, eax
0x180080763  mov     dword ptr [rbx], 3
0x180080769  add     rsp, 20h
0x18008076d  pop     rbx
0x18008076e  retn
```
