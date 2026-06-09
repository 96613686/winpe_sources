# CRpcImpersonateClient::IsDefender(void)

- ea: `0x18001c780`
- end: `0x18001c84f`
- name: `?IsDefender@CRpcImpersonateClient@@QEAAHXZ`
- size: `207`
- prototype: `__int64 __fastcall(CRpcImpersonateClient *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005308`
- `0x180025520`
- `0x1800337d0`

## callees

- `0x180008e48`
- `0x18001c780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c80f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c80f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c7c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c7c6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001c7b7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001c7b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c7a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c7a1`

## pseudocode

```c
__int64 __fastcall CRpcImpersonateClient::IsDefender(CRpcImpersonateClient *this)
{
  DWORD v2; // eax
  DWORD LastError; // eax
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  int v5; // [rsp+34h] [rbp+Ch]
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  v5 = HIDWORD(this);
  IsMember = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-1913148863-3492339771-4165695881-2087618961-4109116736", &Sid) )
  {
    if ( !CheckTokenMembership(0, Sid, &IsMember) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, LastError);
      }
      IsMember = 0;
    }
    LocalFree(Sid);
  }
  else
  {
    v2 = GetLastError();
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v2);
    }
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18001c780  mov     qword ptr [rsp+IsMember], rcx
0x18001c785  push    rbx
0x18001c786  sub     rsp, 20h
0x18001c78a  xor     ebx, ebx
0x18001c78c  lea     rdx, [rsp+28h+Sid]; Sid
0x18001c791  lea     rcx, StringSid; "S-1-5-80-1913148863-3492339771-41656958"...
0x18001c798  mov     [rsp+28h+IsMember], ebx
0x18001c79c  mov     [rsp+28h+Sid], rbx
0x18001c7a1  call    cs:__imp_ConvertStringSidToSidW
0x18001c7a7  test    eax, eax
0x18001c7a9  jz      short loc_18001C7D6
0x18001c7ab  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18001c7b0  lea     r8, [rsp+28h+IsMember]; IsMember
0x18001c7b5  xor     ecx, ecx; TokenHandle
0x18001c7b7  call    cs:__imp_CheckTokenMembership
0x18001c7bd  test    eax, eax
0x18001c7bf  jz      short loc_18001C80F
0x18001c7c1  mov     rcx, [rsp+28h+Sid]; hMem
0x18001c7c6  call    cs:__imp_LocalFree
0x18001c7cc  mov     eax, [rsp+28h+IsMember]
0x18001c7d0  add     rsp, 20h
0x18001c7d4  pop     rbx
0x18001c7d5  retn
0x18001c7d6  call    cs:__imp_GetLastError
0x18001c7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7e3  lea     rdx, WPP_GLOBAL_Control
0x18001c7ea  cmp     rcx, rdx
0x18001c7ed  jz      short loc_18001C7CC
0x18001c7ef  test    byte ptr [rcx+1Ch], 1
0x18001c7f3  jz      short loc_18001C7CC
0x18001c7f5  mov     rcx, [rcx+10h]
0x18001c7f9  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001c800  mov     edx, 1Eh
0x18001c805  mov     r9d, eax
0x18001c808  call    WPP_SF_d
0x18001c80d  jmp     short loc_18001C7CC
0x18001c80f  call    cs:__imp_GetLastError
0x18001c815  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c81c  lea     rdx, WPP_GLOBAL_Control
0x18001c823  cmp     rcx, rdx
0x18001c826  jz      short loc_18001C846
0x18001c828  test    byte ptr [rcx+1Ch], 1
0x18001c82c  jz      short loc_18001C846
0x18001c82e  mov     rcx, [rcx+10h]
0x18001c832  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001c839  mov     edx, 1Dh
0x18001c83e  mov     r9d, eax
0x18001c841  call    WPP_SF_d
0x18001c846  mov     [rsp+28h+IsMember], ebx
0x18001c84a  jmp     loc_18001C7C1
```
