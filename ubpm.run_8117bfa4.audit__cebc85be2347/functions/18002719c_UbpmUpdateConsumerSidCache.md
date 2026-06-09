# UbpmUpdateConsumerSidCache

- ea: `0x18002719c`
- end: `0x1800275b4`
- name: `UbpmUpdateConsumerSidCache`
- size: `1048`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ec90`
- `0x18002702c`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18001af64`
- `0x18002719c`
- `0x1800373c0`
- `0x18003ffc4`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800275a3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800275a3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800273e3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800273e3`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180027345`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18002737e`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180027345`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18002737e`
- `ntdll!RtlInitUnicodeString` at `0x18002721d`
- `ntdll!RtlInitUnicodeString` at `0x180027230`
- `ntdll!RtlInitUnicodeString` at `0x180027319`
- `ntdll!RtlInitUnicodeString` at `0x18002732c`
- `ntdll!RtlInitUnicodeString` at `0x1800273fe`
- `ntdll!RtlInitUnicodeString` at `0x18002721d`
- `ntdll!RtlInitUnicodeString` at `0x180027230`
- `ntdll!RtlInitUnicodeString` at `0x180027319`
- `ntdll!RtlInitUnicodeString` at `0x18002732c`
- `ntdll!RtlInitUnicodeString` at `0x1800273fe`
- `ntdll!RtlNtStatusToDosError` at `0x180027442`
- `ntdll!RtlNtStatusToDosError` at `0x1800274bb`
- `ntdll!RtlNtStatusToDosError` at `0x18002750d`
- `ntdll!RtlNtStatusToDosError` at `0x180027442`
- `ntdll!RtlNtStatusToDosError` at `0x1800274bb`
- `ntdll!RtlNtStatusToDosError` at `0x18002750d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800274f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800274f7`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x18002724a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupManageSidNameMapping` at `0x18002724a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800272a0`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800272a0`

## string_xrefs

- `0x18002756b`: `removed from`

## pseudocode

```c
__int64 __fastcall UbpmUpdateConsumerSidCache(PCWSTR SourceString, const WCHAR *a2, __int64 a3, __int64 a4)
{
  int v4; // r15d
  unsigned int v5; // ebx
  const wchar_t *v6; // rsi
  unsigned int v8; // edi
  NTSTATUS v9; // eax
  char v10; // r14
  int v11; // ecx
  DWORD LastError; // ebx
  NTSTATUS v14; // eax
  void *v15; // rax
  NTSTATUS v16; // eax
  char v17; // al
  int v18; // edx
  _QWORD *v19; // rax
  const wchar_t *v20; // rax
  SIZE_T Size; // [rsp+60h] [rbp-39h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp-31h] BYREF
  PSID pSid; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString[3]; // [rsp+78h] [rbp-21h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  memset(DestinationString, 0, sizeof(DestinationString));
  Buffer = 0;
  v4 = a4;
  LODWORD(Size) = 0;
  v5 = a3;
  pSid = 0;
  v6 = a2;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !SourceString || (unsigned int)(a3 - 80) > 0x1F )
  {
    LastError = 87;
    goto LABEL_12;
  }
  if ( !(_DWORD)a4 )
  {
    RtlInitUnicodeString(&DestinationString[1], a2);
    RtlInitUnicodeString(DestinationString, SourceString);
    v8 = v4 + 1;
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
  v14 = RtlCreateVirtualAccountSid(&DestinationString[1], v5, 0, &Size);
  if ( v14 == -1073741789 )
  {
    v15 = UbpmAlloc((unsigned int)Size);
    *(_QWORD *)&DestinationString[2].Length = v15;
    if ( v15 )
    {
      v16 = RtlCreateVirtualAccountSid(&DestinationString[1], v5, v15, &Size);
      if ( v16 >= 0 )
      {
LABEL_25:
        v8 = 0;
LABEL_5:
        v9 = LsaLookupManageSidNameMapping(v8, DestinationString, &Buffer);
        v10 = v9;
        if ( v9 < 0 )
        {
          LastError = RtlNtStatusToDosError(v9);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
              v6 != 0 ? (unsigned int)v6 : 0,
              v10);
        }
        else
        {
          if ( v8 )
          {
            if ( v8 == 1 )
            {
              a4 = *(unsigned int *)Buffer;
              LastError = *(_DWORD *)Buffer != 0 ? 0xD : 0;
            }
            else
            {
              LastError = 87;
              a4 = 87;
            }
          }
          else
          {
            v11 = 0;
            a4 = *(unsigned int *)Buffer;
            if ( (_DWORD)a4 )
              v11 = 13;
            LastError = v11;
          }
          a2 = (const WCHAR *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v20 = L"added to";
            if ( !v4 )
              v20 = L"removed from";
            if ( !v6 )
              v6 = L"NULL";
            WPP_SF_dSS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              a3,
              a4,
              (__int64)v6,
              (__int64)v20);
          }
        }
        goto LABEL_12;
      }
      LastError = RtlNtStatusToDosError(v16);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v18 = 66;
    }
    else
    {
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v18 = 65;
    }
    WPP_SF_Sd(v19[2], v18, (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids, (_DWORD)v6, LastError);
    goto LABEL_12;
  }
  LastError = 13;
  a2 = (const WCHAR *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = RtlNtStatusToDosError(v14);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
      (_DWORD)v6,
      v17);
  }
LABEL_12:
  if ( Buffer )
    LsaLookupFreeMemory(Buffer);
  if ( *(PSID *)&DestinationString[2].Length != pSid )
    UBPM_MIDL_user_free(*(_QWORD *)&DestinationString[2].Length, a2, a3, a4);
  if ( pSid )
    FreeSid(pSid);
  return LastError;
}

```

## disassembly

```asm
0x18002719c  push    rbp
0x18002719e  push    rbx
0x18002719f  push    rsi
0x1800271a0  push    rdi
0x1800271a1  push    r12
0x1800271a3  push    r14
0x1800271a5  push    r15
0x1800271a7  lea     rbp, [rsp-27h]
0x1800271ac  sub     rsp, 0C0h
0x1800271b3  mov     rax, cs:__security_cookie
0x1800271ba  xor     rax, rsp
0x1800271bd  mov     [rbp+57h+var_40], rax
0x1800271c1  xor     r12d, r12d
0x1800271c4  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800271ca  mov     [rbp+57h+DestinationString.Length], r12w
0x1800271cf  xorps   xmm0, xmm0
0x1800271d2  mov     [rbp+57h+Buffer], r12
0x1800271d6  mov     r15d, r9d
0x1800271d9  mov     dword ptr [rbp+57h+Size], r12d
0x1800271dd  mov     ebx, r8d
0x1800271e0  mov     [rbp+57h+var_80], r12
0x1800271e4  mov     rsi, rdx
0x1800271e7  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1800271eb  mov     r14, rcx
0x1800271ee  movups  xmmword ptr [rbp+57h+var_68+2], xmm0
0x1800271f2  movups  xmmword ptr [rbp+57h+var_68+10h], xmm0
0x1800271f6  movups  xmmword ptr [rbp+57h+DestinationString.MaximumLength], xmm0
0x1800271fa  test    rcx, rcx
0x1800271fd  jz      loc_18002739A
0x180027203  lea     eax, [r8-50h]
0x180027207  cmp     eax, 1Fh
0x18002720a  ja      loc_18002739A
0x180027210  test    r9d, r9d
0x180027213  jnz     loc_18002730C
0x180027219  lea     rcx, [rbp+57h+var_68]; DestinationString
0x18002721d  call    cs:__imp_RtlInitUnicodeString
0x180027224  nop     dword ptr [rax+rax+00h]
0x180027229  mov     rdx, r14; SourceString
0x18002722c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180027230  call    cs:__imp_RtlInitUnicodeString
0x180027237  nop     dword ptr [rax+rax+00h]
0x18002723c  lea     edi, [r15+1]
0x180027240  lea     r8, [rbp+57h+Buffer]
0x180027244  mov     ecx, edi
0x180027246  lea     rdx, [rbp+57h+DestinationString]
0x18002724a  call    cs:__imp_LsaLookupManageSidNameMapping
0x180027251  nop     dword ptr [rax+rax+00h]
0x180027256  mov     r14d, eax
0x180027259  test    eax, eax
0x18002725b  js      loc_18002750A
0x180027261  test    edi, edi
0x180027263  jnz     short loc_1800272E4
0x180027265  mov     rax, [rbp+57h+Buffer]
0x180027269  lea     ebx, [rdi+0Dh]
0x18002726c  mov     ecx, r12d
0x18002726f  mov     r9d, [rax]
0x180027272  test    r9d, r9d
0x180027275  cmovnz  ecx, ebx
0x180027278  mov     ebx, ecx
0x18002727a  mov     rdx, cs:WPP_GLOBAL_Control
0x180027281  lea     rcx, WPP_GLOBAL_Control
0x180027288  cmp     rdx, rcx
0x18002728b  jz      short loc_180027297
0x18002728d  test    byte ptr [rdx+1Ch], 4
0x180027291  jnz     loc_180027568
0x180027297  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18002729b  test    rcx, rcx
0x18002729e  jz      short loc_1800272AC
0x1800272a0  call    cs:__imp_LsaLookupFreeMemory
0x1800272a7  nop     dword ptr [rax+rax+00h]
0x1800272ac  mov     rcx, qword ptr [rbp+57h+var_68+10h]
0x1800272b0  cmp     rcx, [rbp+57h+var_80]
0x1800272b4  jnz     short loc_180027305
0x1800272b6  mov     rcx, [rbp+57h+var_80]; pSid
0x1800272ba  test    rcx, rcx
0x1800272bd  jnz     loc_1800275A3
0x1800272c3  mov     eax, ebx
0x1800272c5  mov     rcx, [rbp+57h+var_40]
0x1800272c9  xor     rcx, rsp; StackCookie
0x1800272cc  call    __security_check_cookie
0x1800272d1  add     rsp, 0C0h
0x1800272d8  pop     r15
0x1800272da  pop     r14
0x1800272dc  pop     r12
0x1800272de  pop     rdi
0x1800272df  pop     rsi
0x1800272e0  pop     rbx
0x1800272e1  pop     rbp
0x1800272e2  retn
0x1800272e4  cmp     edi, 1
0x1800272e7  jnz     loc_1800273A4
0x1800272ed  mov     rax, [rbp+57h+Buffer]
0x1800272f1  lea     ebx, [rdi+0Ch]
0x1800272f4  mov     r9d, [rax]
0x1800272f7  mov     eax, r9d
0x1800272fa  neg     eax
0x1800272fc  sbb     ecx, ecx
0x1800272fe  and     ebx, ecx
0x180027300  jmp     loc_18002727A
0x180027305  call    UBPM_MIDL_user_free
0x18002730a  jmp     short loc_1800272B6
0x18002730c  test    rsi, rsi
0x18002730f  jz      loc_1800273B1
0x180027315  lea     rcx, [rbp+57h+var_68]; DestinationString
0x180027319  call    cs:__imp_RtlInitUnicodeString
0x180027320  nop     dword ptr [rax+rax+00h]
0x180027325  mov     rdx, r14; SourceString
0x180027328  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002732c  call    cs:__imp_RtlInitUnicodeString
0x180027333  nop     dword ptr [rax+rax+00h]
0x180027338  lea     r9, [rbp+57h+Size]
0x18002733c  xor     r8d, r8d
0x18002733f  mov     edx, ebx
0x180027341  lea     rcx, [rbp+57h+var_68]
0x180027345  call    cs:__imp_RtlCreateVirtualAccountSid
0x18002734c  nop     dword ptr [rax+rax+00h]
0x180027351  cmp     eax, 0C0000023h
0x180027356  jnz     loc_180027417
0x18002735c  mov     ecx, dword ptr [rbp+57h+Size]; Size
0x18002735f  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180027364  mov     qword ptr [rbp+57h+var_68+10h], rax
0x180027368  test    rax, rax
0x18002736b  jz      loc_180027483
0x180027371  lea     r9, [rbp+57h+Size]
0x180027375  mov     r8, rax
0x180027378  mov     edx, ebx
0x18002737a  lea     rcx, [rbp+57h+var_68]
0x18002737e  call    cs:__imp_RtlCreateVirtualAccountSid
0x180027385  nop     dword ptr [rax+rax+00h]
0x18002738a  test    eax, eax
0x18002738c  js      loc_1800274B9
0x180027392  mov     edi, r12d
0x180027395  jmp     loc_180027240
0x18002739a  mov     ebx, 57h ; 'W'
0x18002739f  jmp     loc_180027297
0x1800273a4  mov     ebx, 57h ; 'W'
0x1800273a9  mov     r9d, ebx
0x1800273ac  jmp     loc_18002727A
0x1800273b1  lea     rax, [rbp+57h+var_80]
0x1800273b5  xor     r9d, r9d; nSubAuthority1
0x1800273b8  mov     [rsp+0F0h+pSid], rax; pSid
0x1800273bd  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800273c1  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x1800273c6  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x1800273cb  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x1800273d0  lea     edx, [r9+1]; nSubAuthorityCount
0x1800273d4  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x1800273d9  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x1800273de  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x1800273e3  call    cs:__imp_AllocateAndInitializeSid
0x1800273ea  nop     dword ptr [rax+rax+00h]
0x1800273ef  test    eax, eax
0x1800273f1  jz      loc_1800274F7
0x1800273f7  mov     rdx, r14; SourceString
0x1800273fa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800273fe  call    cs:__imp_RtlInitUnicodeString
0x180027405  nop     dword ptr [rax+rax+00h]
0x18002740a  mov     rax, [rbp+57h+var_80]
0x18002740e  mov     qword ptr [rbp+57h+var_68+10h], rax
0x180027412  jmp     loc_180027392
0x180027417  mov     ebx, 0Dh
0x18002741c  mov     rdx, cs:WPP_GLOBAL_Control
0x180027423  lea     rcx, WPP_GLOBAL_Control
0x18002742a  cmp     rdx, rcx
0x18002742d  jz      loc_180027297
0x180027433  lea     edi, [rbx-0Ch]
0x180027436  test    [rdx+1Ch], dil
0x18002743a  jz      loc_180027297
0x180027440  mov     ecx, eax; Status
0x180027442  call    cs:__imp_RtlNtStatusToDosError
0x180027449  nop     dword ptr [rax+rax+00h]
0x18002744e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027455  lea     edx, [rbx+33h]
0x180027458  mov     [rsp+0F0h+nSubAuthority2], eax
0x18002745c  mov     rcx, [rcx+10h]
0x180027460  jmp     short loc_18002746F
0x180027462  mov     edx, 41h ; 'A'
0x180027467  mov     rcx, [rax+10h]
0x18002746b  mov     [rsp+0F0h+nSubAuthority2], ebx
0x18002746f  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180027476  mov     r9, rsi
0x180027479  call    WPP_SF_Sd
0x18002747e  jmp     loc_180027297
0x180027483  call    cs:__imp_GetLastError
0x18002748a  nop     dword ptr [rax+rax+00h]
0x18002748f  mov     ebx, eax
0x180027491  mov     rax, cs:WPP_GLOBAL_Control
0x180027498  lea     rcx, WPP_GLOBAL_Control
0x18002749f  cmp     rax, rcx
0x1800274a2  jz      loc_180027297
0x1800274a8  mov     edi, 1
0x1800274ad  test    [rax+1Ch], dil
0x1800274b1  jz      loc_180027297
0x1800274b7  jmp     short loc_180027462
0x1800274b9  mov     ecx, eax; Status
0x1800274bb  call    cs:__imp_RtlNtStatusToDosError
0x1800274c2  nop     dword ptr [rax+rax+00h]
0x1800274c7  mov     ebx, eax
0x1800274c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800274d0  lea     rcx, WPP_GLOBAL_Control
0x1800274d7  cmp     rax, rcx
0x1800274da  jz      loc_180027297
0x1800274e0  mov     edi, 1
0x1800274e5  test    [rax+1Ch], dil
0x1800274e9  jz      loc_180027297
0x1800274ef  lea     edx, [rdi+41h]
0x1800274f2  jmp     loc_180027467
0x1800274f7  call    cs:__imp_GetLastError
0x1800274fe  nop     dword ptr [rax+rax+00h]
0x180027503  mov     ebx, eax
0x180027505  jmp     loc_180027297
0x18002750a  mov     ecx, r14d; Status
0x18002750d  call    cs:__imp_RtlNtStatusToDosError
0x180027514  nop     dword ptr [rax+rax+00h]
0x180027519  mov     ebx, eax
0x18002751b  mov     r10, cs:WPP_GLOBAL_Control
0x180027522  lea     rcx, WPP_GLOBAL_Control
0x180027529  cmp     r10, rcx
0x18002752c  jz      loc_180027297
0x180027532  test    byte ptr [r10+1Ch], 2
0x180027537  jz      loc_180027297
0x18002753d  mov     rcx, [r10+10h]
0x180027541  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180027548  mov     rax, rsi
0x18002754b  mov     [rsp+0F0h+nSubAuthority2], r14d
0x180027550  neg     rax
0x180027553  mov     edx, 43h ; 'C'
0x180027558  sbb     r9, r9
0x18002755b  and     r9, rsi
0x18002755e  call    WPP_SF_SL
0x180027563  jmp     loc_180027297
0x180027568  test    r15d, r15d
0x18002756b  lea     rcx, aRemovedFrom; "removed from"
0x180027572  lea     rax, aAddedTo; "added to"
0x180027579  cmovz   rax, rcx
0x18002757d  test    rsi, rsi
0x180027580  lea     rcx, aNull_0; "NULL"
0x180027587  mov     qword ptr [rsp+0F0h+nSubAuthority3], rax
0x18002758c  cmovz   rsi, rcx
0x180027590  mov     rcx, [rdx+10h]
0x180027594  mov     qword ptr [rsp+0F0h+nSubAuthority2], rsi
0x180027599  call    WPP_SF_dSS
0x18002759e  jmp     loc_180027297
0x1800275a3  call    cs:__imp_FreeSid
0x1800275aa  nop     dword ptr [rax+rax+00h]
0x1800275af  jmp     loc_1800272C3
```
