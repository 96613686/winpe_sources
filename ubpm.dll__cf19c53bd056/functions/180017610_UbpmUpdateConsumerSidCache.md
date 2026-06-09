# UbpmUpdateConsumerSidCache

- ea: `0x180017610`
- end: `0x1800179c4`
- name: `UbpmUpdateConsumerSidCache`
- size: `948`
- prototype: `__int64 __fastcall(PCWSTR SourceString, const WCHAR *, DWORD, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800174d0`
- `0x180018ef0`

## callees

- `0x18000f9a0`
- `0x180017610`
- `0x180019d90`
- `0x18001e9f4`
- `0x180034ec4`
- `0x18003d580`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800179b9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800179b9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180017826`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180017826`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180017794`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800177c7`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180017794`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800177c7`
- `ntdll!RtlInitUnicodeString` at `0x180017691`
- `ntdll!RtlInitUnicodeString` at `0x18001769e`
- `ntdll!RtlInitUnicodeString` at `0x180017774`
- `ntdll!RtlInitUnicodeString` at `0x180017781`
- `ntdll!RtlInitUnicodeString` at `0x18001783b`
- `ntdll!RtlInitUnicodeString` at `0x180017691`
- `ntdll!RtlInitUnicodeString` at `0x18001769e`
- `ntdll!RtlInitUnicodeString` at `0x180017774`
- `ntdll!RtlInitUnicodeString` at `0x180017781`
- `ntdll!RtlInitUnicodeString` at `0x18001783b`
- `ntdll!RtlNtStatusToDosError` at `0x180017876`
- `ntdll!RtlNtStatusToDosError` at `0x1800178e3`
- `ntdll!RtlNtStatusToDosError` at `0x180017929`
- `ntdll!RtlNtStatusToDosError` at `0x180017876`
- `ntdll!RtlNtStatusToDosError` at `0x1800178e3`
- `ntdll!RtlNtStatusToDosError` at `0x180017929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017919`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x1800176b2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x1800176b2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180017702`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180017702`

## string_xrefs

- `0x180017981`: `removed from`

## pseudocode

```c
__int64 __fastcall UbpmUpdateConsumerSidCache(PCWSTR SourceString, const WCHAR *a2, DWORD a3, int a4)
{
  const wchar_t *v6; // rsi
  unsigned int v8; // edi
  NTSTATUS v9; // eax
  int v10; // r8d
  char v11; // r14
  int v12; // ecx
  int v13; // r9d
  DWORD LastError; // ebx
  NTSTATUS v16; // eax
  void *v17; // rax
  NTSTATUS v18; // eax
  char v19; // al
  int v20; // edx
  _QWORD *v21; // rax
  const wchar_t *v22; // rax
  SIZE_T Size; // [rsp+60h] [rbp-39h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp-31h] BYREF
  PSID pSid; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString[3]; // [rsp+78h] [rbp-21h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  memset(DestinationString, 0, sizeof(DestinationString));
  Buffer = 0;
  LODWORD(Size) = 0;
  pSid = 0;
  v6 = a2;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !SourceString || a3 - 80 > 0x1F )
  {
    LastError = 87;
    goto LABEL_12;
  }
  if ( !a4 )
  {
    RtlInitUnicodeString(&DestinationString[1], a2);
    RtlInitUnicodeString(DestinationString, SourceString);
    v8 = a4 + 1;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, a3, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      LastError = GetLastError();
      goto LABEL_12;
    }
    RtlInitUnicodeString(DestinationString, SourceString);
    *(_QWORD *)&DestinationString[2].Length = pSid;
    goto LABEL_25;
  }
  RtlInitUnicodeString(&DestinationString[1], a2);
  RtlInitUnicodeString(DestinationString, SourceString);
  v16 = RtlCreateVirtualAccountSid(&DestinationString[1], a3, 0, &Size);
  if ( v16 == -1073741789 )
  {
    v17 = UbpmAlloc((unsigned int)Size);
    *(_QWORD *)&DestinationString[2].Length = v17;
    if ( v17 )
    {
      v18 = RtlCreateVirtualAccountSid(&DestinationString[1], a3, v17, &Size);
      if ( v18 >= 0 )
      {
LABEL_25:
        v8 = 0;
LABEL_5:
        v9 = LsaLookupManageSidNameMapping(v8, DestinationString, &Buffer);
        v11 = v9;
        if ( v9 < 0 )
        {
          LastError = RtlNtStatusToDosError(v9);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
              v6 != 0 ? (unsigned int)v6 : 0,
              v11);
        }
        else
        {
          if ( v8 )
          {
            if ( v8 == 1 )
            {
              v13 = *(_DWORD *)Buffer;
              LastError = *(_DWORD *)Buffer != 0 ? 0xD : 0;
            }
            else
            {
              LastError = 87;
              v13 = 87;
            }
          }
          else
          {
            v12 = 0;
            v13 = *(_DWORD *)Buffer;
            if ( *(_DWORD *)Buffer )
              v12 = 13;
            LastError = v12;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v22 = L"added to";
            if ( !a4 )
              v22 = L"removed from";
            if ( !v6 )
              v6 = L"NULL";
            WPP_SF_dSS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              v10,
              v13,
              (__int64)v6,
              (__int64)v22);
          }
        }
        goto LABEL_12;
      }
      LastError = RtlNtStatusToDosError(v18);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v20 = 66;
    }
    else
    {
      LastError = GetLastError();
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v20 = 65;
    }
    WPP_SF_Sd(v21[2], v20, (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids, (_DWORD)v6, LastError);
    goto LABEL_12;
  }
  LastError = 13;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v19 = RtlNtStatusToDosError(v16);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
      (_DWORD)v6,
      v19);
  }
LABEL_12:
  if ( Buffer )
    LsaLookupFreeMemory(Buffer);
  if ( *(PSID *)&DestinationString[2].Length != pSid )
    UBPM_MIDL_user_free(*(_QWORD *)&DestinationString[2].Length);
  if ( pSid )
    FreeSid(pSid);
  return LastError;
}

```

## disassembly

```asm
0x180017610  push    rbp
0x180017612  push    rbx
0x180017613  push    rsi
0x180017614  push    rdi
0x180017615  push    r12
0x180017617  push    r14
0x180017619  push    r15
0x18001761b  lea     rbp, [rsp-27h]
0x180017620  sub     rsp, 0C0h
0x180017627  mov     rax, cs:__security_cookie
0x18001762e  xor     rax, rsp
0x180017631  mov     [rbp+57h+var_40], rax
0x180017635  xor     r12d, r12d
0x180017638  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001763e  mov     [rbp+57h+DestinationString.Length], r12w
0x180017643  xorps   xmm0, xmm0
0x180017646  mov     [rbp+57h+Buffer], r12
0x18001764a  mov     r15d, r9d
0x18001764d  mov     dword ptr [rbp+57h+Size], r12d
0x180017651  mov     ebx, r8d
0x180017654  mov     [rbp+57h+var_80], r12
0x180017658  mov     rsi, rdx
0x18001765b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x18001765f  mov     r14, rcx
0x180017662  movups  xmmword ptr [rbp+57h+var_68+2], xmm0
0x180017666  movups  xmmword ptr [rbp+57h+var_68+10h], xmm0
0x18001766a  movups  xmmword ptr [rbp+57h+DestinationString.MaximumLength], xmm0
0x18001766e  test    rcx, rcx
0x180017671  jz      loc_1800177DD
0x180017677  lea     eax, [r8-50h]
0x18001767b  cmp     eax, 1Fh
0x18001767e  ja      loc_1800177DD
0x180017684  test    r9d, r9d
0x180017687  jnz     loc_180017767
0x18001768d  lea     rcx, [rbp+57h+var_68]; DestinationString
0x180017691  call    cs:__imp_RtlInitUnicodeString
0x180017697  mov     rdx, r14; SourceString
0x18001769a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001769e  call    cs:__imp_RtlInitUnicodeString
0x1800176a4  lea     edi, [r15+1]
0x1800176a8  lea     r8, [rbp+57h+Buffer]
0x1800176ac  mov     ecx, edi
0x1800176ae  lea     rdx, [rbp+57h+DestinationString]
0x1800176b2  call    cs:__imp_LsaLookupManageSidNameMapping
0x1800176b8  mov     r14d, eax
0x1800176bb  test    eax, eax
0x1800176bd  js      loc_180017926
0x1800176c3  test    edi, edi
0x1800176c5  jnz     short loc_18001773F
0x1800176c7  mov     rax, [rbp+57h+Buffer]
0x1800176cb  lea     ebx, [rdi+0Dh]
0x1800176ce  mov     ecx, r12d
0x1800176d1  mov     r9d, [rax]
0x1800176d4  test    r9d, r9d
0x1800176d7  cmovnz  ecx, ebx
0x1800176da  mov     ebx, ecx
0x1800176dc  mov     rdx, cs:WPP_GLOBAL_Control
0x1800176e3  lea     rcx, WPP_GLOBAL_Control
0x1800176ea  cmp     rdx, rcx
0x1800176ed  jz      short loc_1800176F9
0x1800176ef  test    byte ptr [rdx+1Ch], 4
0x1800176f3  jnz     loc_18001797E
0x1800176f9  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800176fd  test    rcx, rcx
0x180017700  jz      short loc_180017708
0x180017702  call    cs:__imp_LsaLookupFreeMemory
0x180017708  mov     rcx, qword ptr [rbp+57h+var_68+10h]
0x18001770c  cmp     rcx, [rbp+57h+var_80]
0x180017710  jnz     short loc_180017760
0x180017712  mov     rcx, [rbp+57h+var_80]; pSid
0x180017716  test    rcx, rcx
0x180017719  jnz     loc_1800179B9
0x18001771f  mov     eax, ebx
0x180017721  mov     rcx, [rbp+57h+var_40]
0x180017725  xor     rcx, rsp; StackCookie
0x180017728  call    __security_check_cookie
0x18001772d  add     rsp, 0C0h
0x180017734  pop     r15
0x180017736  pop     r14
0x180017738  pop     r12
0x18001773a  pop     rdi
0x18001773b  pop     rsi
0x18001773c  pop     rbx
0x18001773d  pop     rbp
0x18001773e  retn
0x18001773f  cmp     edi, 1
0x180017742  jnz     loc_1800177E7
0x180017748  mov     rax, [rbp+57h+Buffer]
0x18001774c  lea     ebx, [rdi+0Ch]
0x18001774f  mov     r9d, [rax]
0x180017752  mov     eax, r9d
0x180017755  neg     eax
0x180017757  sbb     ecx, ecx
0x180017759  and     ebx, ecx
0x18001775b  jmp     loc_1800176DC
0x180017760  call    UBPM_MIDL_user_free
0x180017765  jmp     short loc_180017712
0x180017767  test    rsi, rsi
0x18001776a  jz      loc_1800177F4
0x180017770  lea     rcx, [rbp+57h+var_68]; DestinationString
0x180017774  call    cs:__imp_RtlInitUnicodeString
0x18001777a  mov     rdx, r14; SourceString
0x18001777d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180017781  call    cs:__imp_RtlInitUnicodeString
0x180017787  lea     r9, [rbp+57h+Size]
0x18001778b  xor     r8d, r8d
0x18001778e  mov     edx, ebx
0x180017790  lea     rcx, [rbp+57h+var_68]
0x180017794  call    cs:__imp_RtlCreateVirtualAccountSid
0x18001779a  cmp     eax, 0C0000023h
0x18001779f  jnz     loc_18001784B
0x1800177a5  mov     ecx, dword ptr [rbp+57h+Size]; Size
0x1800177a8  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800177ad  mov     qword ptr [rbp+57h+var_68+10h], rax
0x1800177b1  test    rax, rax
0x1800177b4  jz      loc_1800178B1
0x1800177ba  lea     r9, [rbp+57h+Size]
0x1800177be  mov     r8, rax
0x1800177c1  mov     edx, ebx
0x1800177c3  lea     rcx, [rbp+57h+var_68]
0x1800177c7  call    cs:__imp_RtlCreateVirtualAccountSid
0x1800177cd  test    eax, eax
0x1800177cf  js      loc_1800178E1
0x1800177d5  mov     edi, r12d
0x1800177d8  jmp     loc_1800176A8
0x1800177dd  mov     ebx, 57h ; 'W'
0x1800177e2  jmp     loc_1800176F9
0x1800177e7  mov     ebx, 57h ; 'W'
0x1800177ec  mov     r9d, ebx
0x1800177ef  jmp     loc_1800176DC
0x1800177f4  lea     rax, [rbp+57h+var_80]
0x1800177f8  xor     r9d, r9d; nSubAuthority1
0x1800177fb  mov     [rsp+0F0h+pSid], rax; pSid
0x180017800  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180017804  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x180017809  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x18001780e  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x180017813  lea     edx, [r9+1]; nSubAuthorityCount
0x180017817  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x18001781c  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x180017821  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x180017826  call    cs:__imp_AllocateAndInitializeSid
0x18001782c  test    eax, eax
0x18001782e  jz      loc_180017919
0x180017834  mov     rdx, r14; SourceString
0x180017837  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001783b  call    cs:__imp_RtlInitUnicodeString
0x180017841  mov     rax, [rbp+57h+var_80]
0x180017845  mov     qword ptr [rbp+57h+var_68+10h], rax
0x180017849  jmp     short loc_1800177D5
0x18001784b  mov     ebx, 0Dh
0x180017850  mov     rdx, cs:WPP_GLOBAL_Control
0x180017857  lea     rcx, WPP_GLOBAL_Control
0x18001785e  cmp     rdx, rcx
0x180017861  jz      loc_1800176F9
0x180017867  lea     edi, [rbx-0Ch]
0x18001786a  test    [rdx+1Ch], dil
0x18001786e  jz      loc_1800176F9
0x180017874  mov     ecx, eax; Status
0x180017876  call    cs:__imp_RtlNtStatusToDosError
0x18001787c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017883  lea     edx, [rbx+33h]
0x180017886  mov     [rsp+0F0h+nSubAuthority2], eax
0x18001788a  mov     rcx, [rcx+10h]
0x18001788e  jmp     short loc_18001789D
0x180017890  mov     edx, 41h ; 'A'
0x180017895  mov     rcx, [rax+10h]
0x180017899  mov     [rsp+0F0h+nSubAuthority2], ebx
0x18001789d  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x1800178a4  mov     r9, rsi
0x1800178a7  call    WPP_SF_Sd
0x1800178ac  jmp     loc_1800176F9
0x1800178b1  call    cs:__imp_GetLastError
0x1800178b7  mov     ebx, eax
0x1800178b9  mov     rax, cs:WPP_GLOBAL_Control
0x1800178c0  lea     rcx, WPP_GLOBAL_Control
0x1800178c7  cmp     rax, rcx
0x1800178ca  jz      loc_1800176F9
0x1800178d0  mov     edi, 1
0x1800178d5  test    [rax+1Ch], dil
0x1800178d9  jz      loc_1800176F9
0x1800178df  jmp     short loc_180017890
0x1800178e1  mov     ecx, eax; Status
0x1800178e3  call    cs:__imp_RtlNtStatusToDosError
0x1800178e9  mov     ebx, eax
0x1800178eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800178f2  lea     rcx, WPP_GLOBAL_Control
0x1800178f9  cmp     rax, rcx
0x1800178fc  jz      loc_1800176F9
0x180017902  mov     edi, 1
0x180017907  test    [rax+1Ch], dil
0x18001790b  jz      loc_1800176F9
0x180017911  lea     edx, [rdi+41h]
0x180017914  jmp     loc_180017895
0x180017919  call    cs:__imp_GetLastError
0x18001791f  mov     ebx, eax
0x180017921  jmp     loc_1800176F9
0x180017926  mov     ecx, r14d; Status
0x180017929  call    cs:__imp_RtlNtStatusToDosError
0x18001792f  mov     ebx, eax
0x180017931  mov     r10, cs:WPP_GLOBAL_Control
0x180017938  lea     rcx, WPP_GLOBAL_Control
0x18001793f  cmp     r10, rcx
0x180017942  jz      loc_1800176F9
0x180017948  test    byte ptr [r10+1Ch], 2
0x18001794d  jz      loc_1800176F9
0x180017953  mov     rcx, [r10+10h]
0x180017957  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x18001795e  mov     rax, rsi
0x180017961  mov     [rsp+0F0h+nSubAuthority2], r14d
0x180017966  neg     rax
0x180017969  mov     edx, 43h ; 'C'
0x18001796e  sbb     r9, r9
0x180017971  and     r9, rsi
0x180017974  call    WPP_SF_SL
0x180017979  jmp     loc_1800176F9
0x18001797e  test    r15d, r15d
0x180017981  lea     rcx, aRemovedFrom; "removed from"
0x180017988  lea     rax, aAddedTo; "added to"
0x18001798f  cmovz   rax, rcx
0x180017993  test    rsi, rsi
0x180017996  lea     rcx, aNull_0; "NULL"
0x18001799d  mov     qword ptr [rsp+0F0h+nSubAuthority3], rax
0x1800179a2  cmovz   rsi, rcx
0x1800179a6  mov     rcx, [rdx+10h]
0x1800179aa  mov     qword ptr [rsp+0F0h+nSubAuthority2], rsi
0x1800179af  call    WPP_SF_dSS
0x1800179b4  jmp     loc_1800176F9
0x1800179b9  call    cs:__imp_FreeSid
0x1800179bf  jmp     loc_18001771F
```
