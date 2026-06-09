# WwanCreateWellKnownSid(WELL_KNOWN_SID_TYPE,_SID * *)

- ea: `0x1800ae038`
- end: `0x1800ae0cd`
- name: `?WwanCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAU_SID@@@Z`
- size: `149`
- prototype: `unsigned int __fastcall(enum WELL_KNOWN_SID_TYPE, struct _SID **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800adf80`

## callees

- `0x1800ae038`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae06e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae06e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0a9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ae05d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ae09f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ae05d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ae09f`

## pseudocode

```c
unsigned int __fastcall WwanCreateWellKnownSid(enum WELL_KNOWN_SID_TYPE a1, struct _SID **a2)
{
  unsigned int result; // eax
  struct _SID *v4; // rax
  struct _SID *v5; // rdi
  DWORD LastError; // ebx
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 0;
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid) )
    return 87;
  result = GetLastError();
  if ( result == 122 )
  {
    v4 = (struct _SID *)WwanMemAlloc(cbSid);
    v5 = v4;
    if ( v4 )
    {
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v4, &cbSid) )
      {
        *a2 = v5;
        return 0;
      }
      else
      {
        LastError = GetLastError();
        WwanMemFree(v5);
        return LastError;
      }
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ae038  mov     rax, rsp
0x1800ae03b  mov     [rax+10h], rbx
0x1800ae03f  mov     [rax+8], ecx
0x1800ae042  push    rdi
0x1800ae043  sub     rsp, 20h
0x1800ae047  mov     rbx, rdx
0x1800ae04a  mov     dword ptr [rax+8], 0
0x1800ae051  xor     edx, edx; DomainSid
0x1800ae053  lea     r9, [rax+8]; cbSid
0x1800ae057  xor     r8d, r8d; pSid
0x1800ae05a  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800ae05d  call    cs:__imp_CreateWellKnownSid
0x1800ae063  test    eax, eax
0x1800ae065  jz      short loc_1800AE06E
0x1800ae067  mov     eax, 57h ; 'W'
0x1800ae06c  jmp     short loc_1800AE0C2
0x1800ae06e  call    cs:__imp_GetLastError
0x1800ae074  cmp     eax, 7Ah ; 'z'
0x1800ae077  jnz     short loc_1800AE0C2
0x1800ae079  mov     ecx, [rsp+28h+cbSid]; Size
0x1800ae07d  call    WwanMemAlloc
0x1800ae082  mov     rdi, rax
0x1800ae085  test    rax, rax
0x1800ae088  jnz     short loc_1800AE092
0x1800ae08a  call    cs:__imp_GetLastError
0x1800ae090  jmp     short loc_1800AE0C2
0x1800ae092  xor     edx, edx; DomainSid
0x1800ae094  lea     r9, [rsp+28h+cbSid]; cbSid
0x1800ae099  mov     r8, rdi; pSid
0x1800ae09c  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800ae09f  call    cs:__imp_CreateWellKnownSid
0x1800ae0a5  test    eax, eax
0x1800ae0a7  jnz     short loc_1800AE0BD
0x1800ae0a9  call    cs:__imp_GetLastError
0x1800ae0af  mov     rcx, rdi
0x1800ae0b2  mov     ebx, eax
0x1800ae0b4  call    WwanMemFree
0x1800ae0b9  mov     eax, ebx
0x1800ae0bb  jmp     short loc_1800AE0C2
0x1800ae0bd  mov     [rbx], rdi
0x1800ae0c0  xor     eax, eax
0x1800ae0c2  mov     rbx, [rsp+28h+arg_8]
0x1800ae0c7  add     rsp, 20h
0x1800ae0cb  pop     rdi
0x1800ae0cc  retn
```
