# InitSecurity

- ea: `0x1402dce78`
- end: `0x1402dd135`
- name: `InitSecurity`
- size: `701`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402db0ac`

## callees

- `0x14007b930`
- `0x14007df80`
- `0x14007f230`
- `0x14007f840`
- `0x1402dce78`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1402dce81`
- `ntoskrnl!SeExports` at `0x1402dcee9`
- `ntoskrnl!SeExports` at `0x1402dcf21`
- `ntoskrnl!SeExports` at `0x1402dcf62`
- `ntoskrnl!SeExports` at `0x1402dcfae`
- `ntoskrnl!SeExports` at `0x1402dcfe9`
- `ntoskrnl!SeExports` at `0x1402dd02a`
- `ntoskrnl!RtlLengthSid` at `0x1402dce95`
- `ntoskrnl!RtlLengthSid` at `0x1402dce95`
- `ntoskrnl!RtlCopySid` at `0x1402dcedd`
- `ntoskrnl!RtlCopySid` at `0x1402dcedd`
- `WIN32K!W32GetUserSessionState` at `0x1402dd07c`
- `WIN32K!W32GetUserSessionState` at `0x1402dd097`
- `WIN32K!W32GetUserSessionState` at `0x1402dd0a3`
- `WIN32K!W32GetUserSessionState` at `0x1402dd116`
- `WIN32K!W32GetUserSessionState` at `0x1402dd07c`
- `WIN32K!W32GetUserSessionState` at `0x1402dd097`
- `WIN32K!W32GetUserSessionState` at `0x1402dd0a3`
- `WIN32K!W32GetUserSessionState` at `0x1402dd116`

## pseudocode

```c
_BOOL8 InitSecurity()
{
  PSID SeWorldSid; // rsi
  ULONG v1; // ebp
  __int64 v2; // rcx
  __int64 v3; // rax
  void *v4; // rbx
  _DWORD *v5; // rax
  __int64 v6; // rdx
  _DWORD *v7; // rdi
  void *v8; // rax
  _DWORD *v9; // rax
  _DWORD *v10; // rcx
  void *v12; // rax
  _DWORD *v13; // rax
  _DWORD *v14; // rax
  _DWORD *v15; // rsi
  struct _ACL *SecurityDescriptor; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  _DWORD *UserSessionState; // rax
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  ULONG AceListLength; // [rsp+60h] [rbp+8h] BYREF

  SeWorldSid = SeExports->SeWorldSid;
  v1 = RtlLengthSid(SeWorldSid);
  v3 = Win32AllocPoolWithQuotaZInitImpl(v2, v1 + 8, 0x65737355u);
  v4 = (void *)v3;
  if ( !v3 )
    return 0;
  *(_WORD *)(v3 + 2) = v1 + 8;
  AceListLength = v1 + 8;
  *(_WORD *)v3 = 3584;
  *(_DWORD *)(v3 + 4) = 983935;
  RtlCopySid(v1, (PSID)(v3 + 8), SeWorldSid);
  v5 = (_DWORD *)AllocAce(v4, 0, 14, 983935, SeExports->SeRestrictedSid, &AceListLength);
  v7 = v5;
  if ( !v5 )
    goto LABEL_5;
  v8 = (void *)AllocAce(v5, 0, 9, 0x10000000, SeExports->SeWorldSid, &AceListLength);
  v4 = v8;
  if ( !v8 )
    goto LABEL_11;
  v9 = (_DWORD *)AllocAce(v8, 0, 9, 0x10000000, SeExports->SeRestrictedSid, &AceListLength);
  v7 = v9;
  if ( !v9 )
  {
LABEL_5:
    v10 = v4;
LABEL_6:
    GreDeleteFastMutex(v10, v6);
    return 0;
  }
  v12 = (void *)AllocAce(v9, 0, 0, 5, SeExports->SeAliasAdminsSid, &AceListLength);
  v4 = v12;
  if ( !v12 )
    goto LABEL_11;
  v13 = (_DWORD *)AllocAce(v12, 0, 0, 2, SeExports->SeWorldSid, &AceListLength);
  v7 = v13;
  if ( !v13 )
    goto LABEL_5;
  v14 = (_DWORD *)AllocAce(v13, 0, 0, 2, SeExports->SeRestrictedSid, &AceListLength);
  v15 = v14;
  if ( !v14 )
  {
LABEL_11:
    v10 = v7;
    goto LABEL_6;
  }
  SecurityDescriptor = CreateSecurityDescriptor(v14, AceListLength, 0);
  *(_QWORD *)(W32GetUserSessionState(v18, v17) + 63304) = SecurityDescriptor;
  GreDeleteFastMutex(v15, v19);
  W32GetUserSessionState(v21, v20);
  UserSessionState = (_DWORD *)W32GetUserSessionState(v23, v22);
  v25 = 0;
  v26 = 0;
  do
  {
    UserSessionState[v26 + 10598] = 0x20000;
    UserSessionState[v26 + 10599] = 0x20000;
    v26 += 4;
    v27 = 2 * (v25 + 2);
    ++v25;
    UserSessionState[2 * v27 + 10592] = 0x20000;
    UserSessionState[v26 + 10597] = 2031616;
  }
  while ( v25 != 24 );
  UserSessionState[10606] = 131079;
  UserSessionState[10607] = 135160;
  UserSessionState[10608] = 0x20000;
  UserSessionState[10609] = 2035711;
  return *(_QWORD *)(W32GetUserSessionState(v27, v26 * 4) + 63304) != 0;
}

```

## disassembly

```asm
0x1402dce78  push    rbx
0x1402dce7a  push    rbp
0x1402dce7b  push    rsi
0x1402dce7c  push    rdi
0x1402dce7d  sub     rsp, 38h
0x1402dce81  mov     rax, cs:__imp_SeExports
0x1402dce88  mov     rcx, [rax]
0x1402dce8b  mov     rsi, [rcx+0C0h]
0x1402dce92  mov     rcx, rsi; Sid
0x1402dce95  call    cs:__imp_RtlLengthSid
0x1402dce9c  nop     dword ptr [rax+rax+00h]
0x1402dcea1  mov     r8d, 65737355h; unsigned int
0x1402dcea7  mov     ebp, eax
0x1402dcea9  lea     edi, [rax+8]
0x1402dceac  mov     edx, edi; unsigned __int64
0x1402dceae  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1402dceb3  mov     rbx, rax
0x1402dceb6  test    rax, rax
0x1402dceb9  jz      loc_1402DCFA2
0x1402dcebf  mov     [rax+2], di
0x1402dcec3  lea     rdx, [rax+8]; DestinationSid
0x1402dcec7  mov     [rsp+58h+AceListLength], edi
0x1402dcecb  mov     r8, rsi; SourceSid
0x1402dcece  mov     edi, 0F037Fh
0x1402dced3  mov     word ptr [rax], 0E00h
0x1402dced8  mov     ecx, ebp; DestinationSidLength
0x1402dceda  mov     [rax+4], edi
0x1402dcedd  call    cs:__imp_RtlCopySid
0x1402dcee4  nop     dword ptr [rax+rax+00h]
0x1402dcee9  mov     rax, cs:__imp_SeExports
0x1402dcef0  lea     rcx, [rsp+58h+AceListLength]
0x1402dcef5  mov     [rsp+58h+var_30], rcx; __int64
0x1402dcefa  mov     r9d, edi
0x1402dcefd  mov     r8b, 0Eh
0x1402dcf00  xor     edx, edx
0x1402dcf02  mov     rcx, rbx; Buffer
0x1402dcf05  mov     rax, [rax]
0x1402dcf08  mov     rax, [rax+158h]
0x1402dcf0f  mov     [rsp+58h+Sid], rax; Sid
0x1402dcf14  call    AllocAce
0x1402dcf19  mov     rdi, rax
0x1402dcf1c  test    rax, rax
0x1402dcf1f  jz      short loc_1402DCF9A
0x1402dcf21  mov     rax, cs:__imp_SeExports
0x1402dcf28  lea     rcx, [rsp+58h+AceListLength]
0x1402dcf2d  mov     [rsp+58h+var_30], rcx; __int64
0x1402dcf32  mov     esi, 10000000h
0x1402dcf37  mov     r9d, esi
0x1402dcf3a  mov     r8b, 9
0x1402dcf3d  xor     edx, edx
0x1402dcf3f  mov     rcx, rdi; Buffer
0x1402dcf42  mov     rax, [rax]
0x1402dcf45  mov     rax, [rax+0C0h]
0x1402dcf4c  mov     [rsp+58h+Sid], rax; Sid
0x1402dcf51  call    AllocAce
0x1402dcf56  mov     rbx, rax
0x1402dcf59  test    rax, rax
0x1402dcf5c  jz      loc_1402DD062
0x1402dcf62  mov     rax, cs:__imp_SeExports
0x1402dcf69  lea     rcx, [rsp+58h+AceListLength]
0x1402dcf6e  mov     [rsp+58h+var_30], rcx; __int64
0x1402dcf73  mov     r9d, esi
0x1402dcf76  mov     r8b, 9
0x1402dcf79  xor     edx, edx
0x1402dcf7b  mov     rcx, rbx; Buffer
0x1402dcf7e  mov     rax, [rax]
0x1402dcf81  mov     rax, [rax+158h]
0x1402dcf88  mov     [rsp+58h+Sid], rax; Sid
0x1402dcf8d  call    AllocAce
0x1402dcf92  mov     rdi, rax
0x1402dcf95  test    rax, rax
0x1402dcf98  jnz     short loc_1402DCFAE
0x1402dcf9a  mov     rcx, rbx; Buffer
0x1402dcf9d  call    GreDeleteFastMutex
0x1402dcfa2  xor     eax, eax
0x1402dcfa4  add     rsp, 38h
0x1402dcfa8  pop     rdi
0x1402dcfa9  pop     rsi
0x1402dcfaa  pop     rbp
0x1402dcfab  pop     rbx
0x1402dcfac  retn
0x1402dcfae  mov     rax, cs:__imp_SeExports
0x1402dcfb5  lea     rcx, [rsp+58h+AceListLength]
0x1402dcfba  mov     [rsp+58h+var_30], rcx; __int64
0x1402dcfbf  mov     r9d, 5
0x1402dcfc5  xor     r8d, r8d
0x1402dcfc8  xor     edx, edx
0x1402dcfca  mov     rcx, rdi; Buffer
0x1402dcfcd  mov     rax, [rax]
0x1402dcfd0  mov     rax, [rax+110h]
0x1402dcfd7  mov     [rsp+58h+Sid], rax; Sid
0x1402dcfdc  call    AllocAce
0x1402dcfe1  mov     rbx, rax
0x1402dcfe4  test    rax, rax
0x1402dcfe7  jz      short loc_1402DD062
0x1402dcfe9  mov     rax, cs:__imp_SeExports
0x1402dcff0  lea     rcx, [rsp+58h+AceListLength]
0x1402dcff5  mov     [rsp+58h+var_30], rcx; __int64
0x1402dcffa  mov     esi, 2
0x1402dcfff  mov     r9d, esi
0x1402dd002  xor     r8d, r8d
0x1402dd005  xor     edx, edx
0x1402dd007  mov     rcx, rbx; Buffer
0x1402dd00a  mov     rax, [rax]
0x1402dd00d  mov     rax, [rax+0C0h]
0x1402dd014  mov     [rsp+58h+Sid], rax; Sid
0x1402dd019  call    AllocAce
0x1402dd01e  mov     rdi, rax
0x1402dd021  test    rax, rax
0x1402dd024  jz      loc_1402DCF9A
0x1402dd02a  mov     rax, cs:__imp_SeExports
0x1402dd031  lea     rcx, [rsp+58h+AceListLength]
0x1402dd036  mov     [rsp+58h+var_30], rcx; __int64
0x1402dd03b  mov     r9d, esi
0x1402dd03e  xor     r8d, r8d
0x1402dd041  xor     edx, edx
0x1402dd043  mov     rcx, rdi; Buffer
0x1402dd046  mov     rax, [rax]
0x1402dd049  mov     rax, [rax+158h]
0x1402dd050  mov     [rsp+58h+Sid], rax; Sid
0x1402dd055  call    AllocAce
0x1402dd05a  mov     rsi, rax
0x1402dd05d  test    rax, rax
0x1402dd060  jnz     short loc_1402DD06A
0x1402dd062  mov     rcx, rdi
0x1402dd065  jmp     loc_1402DCF9D
0x1402dd06a  mov     edx, [rsp+58h+AceListLength]; AceListLength
0x1402dd06e  xor     r8d, r8d; DaclDefaulted
0x1402dd071  mov     rcx, rsi; AceList
0x1402dd074  call    CreateSecurityDescriptor
0x1402dd079  mov     rbx, rax
0x1402dd07c  call    cs:__imp_W32GetUserSessionState
0x1402dd083  nop     dword ptr [rax+rax+00h]
0x1402dd088  mov     rcx, rsi; Buffer
0x1402dd08b  mov     [rax+0F748h], rbx
0x1402dd092  call    GreDeleteFastMutex
0x1402dd097  call    cs:__imp_W32GetUserSessionState
0x1402dd09e  nop     dword ptr [rax+rax+00h]
0x1402dd0a3  call    cs:__imp_W32GetUserSessionState
0x1402dd0aa  nop     dword ptr [rax+rax+00h]
0x1402dd0af  xor     r8d, r8d
0x1402dd0b2  mov     r9d, 20000h
0x1402dd0b8  xor     edx, edx
0x1402dd0ba  mov     [rax+rdx+0A598h], r9d
0x1402dd0c2  lea     rcx, [r8+2]
0x1402dd0c6  mov     [rax+rdx+0A59Ch], r9d
0x1402dd0ce  lea     rdx, [rdx+10h]
0x1402dd0d2  add     rcx, rcx
0x1402dd0d5  inc     r8
0x1402dd0d8  mov     [rax+rcx*8+0A580h], r9d
0x1402dd0e0  mov     dword ptr [rax+rdx+0A594h], 1F0000h
0x1402dd0eb  cmp     r8, 18h
0x1402dd0ef  jnz     short loc_1402DD0BA
0x1402dd0f1  mov     dword ptr [rax+0A5B8h], 20007h
0x1402dd0fb  mov     dword ptr [rax+0A5BCh], 20FF8h
0x1402dd105  mov     [rax+0A5C0h], r9d
0x1402dd10c  mov     dword ptr [rax+0A5C4h], 1F0FFFh
0x1402dd116  call    cs:__imp_W32GetUserSessionState
0x1402dd11d  nop     dword ptr [rax+rax+00h]
0x1402dd122  xor     ecx, ecx
0x1402dd124  cmp     [rax+0F748h], rcx
0x1402dd12b  setnz   cl
0x1402dd12e  mov     eax, ecx
0x1402dd130  jmp     loc_1402DCFA4
```
