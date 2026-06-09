# InitSecurity

- ea: `0x1402dedb8`
- end: `0x1402df075`
- name: `InitSecurity`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402dd0ac`

## callees

- `0x1400411c0`
- `0x140043810`
- `0x140044c10`
- `0x140045220`
- `0x1402dedb8`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1402dedc1`
- `ntoskrnl!SeExports` at `0x1402dee29`
- `ntoskrnl!SeExports` at `0x1402dee61`
- `ntoskrnl!SeExports` at `0x1402deea2`
- `ntoskrnl!SeExports` at `0x1402deeee`
- `ntoskrnl!SeExports` at `0x1402def29`
- `ntoskrnl!SeExports` at `0x1402def6a`
- `ntoskrnl!RtlLengthSid` at `0x1402dedd5`
- `ntoskrnl!RtlLengthSid` at `0x1402dedd5`
- `ntoskrnl!RtlCopySid` at `0x1402dee1d`
- `ntoskrnl!RtlCopySid` at `0x1402dee1d`
- `WIN32K!W32GetUserSessionState` at `0x1402defbc`
- `WIN32K!W32GetUserSessionState` at `0x1402defd7`
- `WIN32K!W32GetUserSessionState` at `0x1402defe3`
- `WIN32K!W32GetUserSessionState` at `0x1402df056`
- `WIN32K!W32GetUserSessionState` at `0x1402defbc`
- `WIN32K!W32GetUserSessionState` at `0x1402defd7`
- `WIN32K!W32GetUserSessionState` at `0x1402defe3`
- `WIN32K!W32GetUserSessionState` at `0x1402df056`

## pseudocode

```c
_BOOL8 InitSecurity()
{
  PSID SeWorldSid; // rsi
  ULONG v1; // ebp
  unsigned __int64 v2; // rcx
  char *v3; // rax
  void *v4; // rbx
  void *v5; // rax
  void *v6; // rdi
  void *v7; // rax
  void *v8; // rax
  void *v9; // rcx
  void *v11; // rax
  void *v12; // rax
  void *v13; // rax
  void *v14; // rsi
  struct _ACL *SecurityDescriptor; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  _DWORD *UserSessionState; // rax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rcx
  ULONG AceListLength; // [rsp+60h] [rbp+8h] BYREF

  SeWorldSid = SeExports->SeWorldSid;
  v1 = RtlLengthSid(SeWorldSid);
  v3 = (char *)Win32AllocPoolWithQuotaZInitImpl(v2, v1 + 8, 0x65737355u);
  v4 = v3;
  if ( !v3 )
    return 0;
  *((_WORD *)v3 + 1) = v1 + 8;
  AceListLength = v1 + 8;
  *(_WORD *)v3 = 3584;
  *((_DWORD *)v3 + 1) = 983935;
  RtlCopySid(v1, v3 + 8, SeWorldSid);
  v5 = (void *)AllocAce(v4, 0, 14, 983935, SeExports->SeRestrictedSid, &AceListLength);
  v6 = v5;
  if ( !v5 )
    goto LABEL_5;
  v7 = (void *)AllocAce(v5, 0, 9, 0x10000000, SeExports->SeWorldSid, &AceListLength);
  v4 = v7;
  if ( !v7 )
    goto LABEL_11;
  v8 = (void *)AllocAce(v7, 0, 9, 0x10000000, SeExports->SeRestrictedSid, &AceListLength);
  v6 = v8;
  if ( !v8 )
  {
LABEL_5:
    v9 = v4;
LABEL_6:
    GreDeleteFastMutex(v9);
    return 0;
  }
  v11 = (void *)AllocAce(v8, 0, 0, 5, SeExports->SeAliasAdminsSid, &AceListLength);
  v4 = v11;
  if ( !v11 )
    goto LABEL_11;
  v12 = (void *)AllocAce(v11, 0, 0, 2, SeExports->SeWorldSid, &AceListLength);
  v6 = v12;
  if ( !v12 )
    goto LABEL_5;
  v13 = (void *)AllocAce(v12, 0, 0, 2, SeExports->SeRestrictedSid, &AceListLength);
  v14 = v13;
  if ( !v13 )
  {
LABEL_11:
    v9 = v6;
    goto LABEL_6;
  }
  SecurityDescriptor = CreateSecurityDescriptor(v13, AceListLength, 0);
  *(_QWORD *)(W32GetUserSessionState(v17, v16, v18) + 63304) = SecurityDescriptor;
  GreDeleteFastMutex(v14);
  W32GetUserSessionState(v20, v19, v21);
  UserSessionState = (_DWORD *)W32GetUserSessionState(v23, v22, v24);
  v26 = 0;
  v27 = 0;
  do
  {
    UserSessionState[v27 + 10598] = 0x20000;
    UserSessionState[v27 + 10599] = 0x20000;
    v27 += 4;
    v28 = 2 * (v26 + 2);
    ++v26;
    UserSessionState[2 * v28 + 10592] = 0x20000;
    UserSessionState[v27 + 10597] = 2031616;
  }
  while ( v26 != 24 );
  UserSessionState[10606] = 131079;
  UserSessionState[10607] = 135160;
  UserSessionState[10608] = 0x20000;
  UserSessionState[10609] = 2035711;
  return *(_QWORD *)(W32GetUserSessionState(v28, v27 * 4, 24) + 63304) != 0;
}

```

## disassembly

```asm
0x1402dedb8  push    rbx
0x1402dedba  push    rbp
0x1402dedbb  push    rsi
0x1402dedbc  push    rdi
0x1402dedbd  sub     rsp, 38h
0x1402dedc1  mov     rax, cs:__imp_SeExports
0x1402dedc8  mov     rcx, [rax]
0x1402dedcb  mov     rsi, [rcx+0C0h]
0x1402dedd2  mov     rcx, rsi; Sid
0x1402dedd5  call    cs:__imp_RtlLengthSid
0x1402deddc  nop     dword ptr [rax+rax+00h]
0x1402dede1  mov     r8d, 65737355h; unsigned int
0x1402dede7  mov     ebp, eax
0x1402dede9  lea     edi, [rax+8]
0x1402dedec  mov     edx, edi; unsigned __int64
0x1402dedee  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1402dedf3  mov     rbx, rax
0x1402dedf6  test    rax, rax
0x1402dedf9  jz      loc_1402DEEE2
0x1402dedff  mov     [rax+2], di
0x1402dee03  lea     rdx, [rax+8]; DestinationSid
0x1402dee07  mov     [rsp+58h+AceListLength], edi
0x1402dee0b  mov     r8, rsi; SourceSid
0x1402dee0e  mov     edi, 0F037Fh
0x1402dee13  mov     word ptr [rax], 0E00h
0x1402dee18  mov     ecx, ebp; DestinationSidLength
0x1402dee1a  mov     [rax+4], edi
0x1402dee1d  call    cs:__imp_RtlCopySid
0x1402dee24  nop     dword ptr [rax+rax+00h]
0x1402dee29  mov     rax, cs:__imp_SeExports
0x1402dee30  lea     rcx, [rsp+58h+AceListLength]
0x1402dee35  mov     [rsp+58h+var_30], rcx; __int64
0x1402dee3a  mov     r9d, edi
0x1402dee3d  mov     r8b, 0Eh
0x1402dee40  xor     edx, edx
0x1402dee42  mov     rcx, rbx; Buffer
0x1402dee45  mov     rax, [rax]
0x1402dee48  mov     rax, [rax+158h]
0x1402dee4f  mov     [rsp+58h+Sid], rax; Sid
0x1402dee54  call    AllocAce
0x1402dee59  mov     rdi, rax
0x1402dee5c  test    rax, rax
0x1402dee5f  jz      short loc_1402DEEDA
0x1402dee61  mov     rax, cs:__imp_SeExports
0x1402dee68  lea     rcx, [rsp+58h+AceListLength]
0x1402dee6d  mov     [rsp+58h+var_30], rcx; __int64
0x1402dee72  mov     esi, 10000000h
0x1402dee77  mov     r9d, esi
0x1402dee7a  mov     r8b, 9
0x1402dee7d  xor     edx, edx
0x1402dee7f  mov     rcx, rdi; Buffer
0x1402dee82  mov     rax, [rax]
0x1402dee85  mov     rax, [rax+0C0h]
0x1402dee8c  mov     [rsp+58h+Sid], rax; Sid
0x1402dee91  call    AllocAce
0x1402dee96  mov     rbx, rax
0x1402dee99  test    rax, rax
0x1402dee9c  jz      loc_1402DEFA2
0x1402deea2  mov     rax, cs:__imp_SeExports
0x1402deea9  lea     rcx, [rsp+58h+AceListLength]
0x1402deeae  mov     [rsp+58h+var_30], rcx; __int64
0x1402deeb3  mov     r9d, esi
0x1402deeb6  mov     r8b, 9
0x1402deeb9  xor     edx, edx
0x1402deebb  mov     rcx, rbx; Buffer
0x1402deebe  mov     rax, [rax]
0x1402deec1  mov     rax, [rax+158h]
0x1402deec8  mov     [rsp+58h+Sid], rax; Sid
0x1402deecd  call    AllocAce
0x1402deed2  mov     rdi, rax
0x1402deed5  test    rax, rax
0x1402deed8  jnz     short loc_1402DEEEE
0x1402deeda  mov     rcx, rbx; Buffer
0x1402deedd  call    GreDeleteFastMutex
0x1402deee2  xor     eax, eax
0x1402deee4  add     rsp, 38h
0x1402deee8  pop     rdi
0x1402deee9  pop     rsi
0x1402deeea  pop     rbp
0x1402deeeb  pop     rbx
0x1402deeec  retn
0x1402deeee  mov     rax, cs:__imp_SeExports
0x1402deef5  lea     rcx, [rsp+58h+AceListLength]
0x1402deefa  mov     [rsp+58h+var_30], rcx; __int64
0x1402deeff  mov     r9d, 5
0x1402def05  xor     r8d, r8d
0x1402def08  xor     edx, edx
0x1402def0a  mov     rcx, rdi; Buffer
0x1402def0d  mov     rax, [rax]
0x1402def10  mov     rax, [rax+110h]
0x1402def17  mov     [rsp+58h+Sid], rax; Sid
0x1402def1c  call    AllocAce
0x1402def21  mov     rbx, rax
0x1402def24  test    rax, rax
0x1402def27  jz      short loc_1402DEFA2
0x1402def29  mov     rax, cs:__imp_SeExports
0x1402def30  lea     rcx, [rsp+58h+AceListLength]
0x1402def35  mov     [rsp+58h+var_30], rcx; __int64
0x1402def3a  mov     esi, 2
0x1402def3f  mov     r9d, esi
0x1402def42  xor     r8d, r8d
0x1402def45  xor     edx, edx
0x1402def47  mov     rcx, rbx; Buffer
0x1402def4a  mov     rax, [rax]
0x1402def4d  mov     rax, [rax+0C0h]
0x1402def54  mov     [rsp+58h+Sid], rax; Sid
0x1402def59  call    AllocAce
0x1402def5e  mov     rdi, rax
0x1402def61  test    rax, rax
0x1402def64  jz      loc_1402DEEDA
0x1402def6a  mov     rax, cs:__imp_SeExports
0x1402def71  lea     rcx, [rsp+58h+AceListLength]
0x1402def76  mov     [rsp+58h+var_30], rcx; __int64
0x1402def7b  mov     r9d, esi
0x1402def7e  xor     r8d, r8d
0x1402def81  xor     edx, edx
0x1402def83  mov     rcx, rdi; Buffer
0x1402def86  mov     rax, [rax]
0x1402def89  mov     rax, [rax+158h]
0x1402def90  mov     [rsp+58h+Sid], rax; Sid
0x1402def95  call    AllocAce
0x1402def9a  mov     rsi, rax
0x1402def9d  test    rax, rax
0x1402defa0  jnz     short loc_1402DEFAA
0x1402defa2  mov     rcx, rdi
0x1402defa5  jmp     loc_1402DEEDD
0x1402defaa  mov     edx, [rsp+58h+AceListLength]; AceListLength
0x1402defae  xor     r8d, r8d; DaclDefaulted
0x1402defb1  mov     rcx, rsi; AceList
0x1402defb4  call    CreateSecurityDescriptor
0x1402defb9  mov     rbx, rax
0x1402defbc  call    cs:__imp_W32GetUserSessionState
0x1402defc3  nop     dword ptr [rax+rax+00h]
0x1402defc8  mov     rcx, rsi; Buffer
0x1402defcb  mov     [rax+0F748h], rbx
0x1402defd2  call    GreDeleteFastMutex
0x1402defd7  call    cs:__imp_W32GetUserSessionState
0x1402defde  nop     dword ptr [rax+rax+00h]
0x1402defe3  call    cs:__imp_W32GetUserSessionState
0x1402defea  nop     dword ptr [rax+rax+00h]
0x1402defef  xor     r8d, r8d
0x1402deff2  mov     r9d, 20000h
0x1402deff8  xor     edx, edx
0x1402deffa  mov     [rax+rdx+0A598h], r9d
0x1402df002  lea     rcx, [r8+2]
0x1402df006  mov     [rax+rdx+0A59Ch], r9d
0x1402df00e  lea     rdx, [rdx+10h]
0x1402df012  add     rcx, rcx
0x1402df015  inc     r8
0x1402df018  mov     [rax+rcx*8+0A580h], r9d
0x1402df020  mov     dword ptr [rax+rdx+0A594h], 1F0000h
0x1402df02b  cmp     r8, 18h
0x1402df02f  jnz     short loc_1402DEFFA
0x1402df031  mov     dword ptr [rax+0A5B8h], 20007h
0x1402df03b  mov     dword ptr [rax+0A5BCh], 20FF8h
0x1402df045  mov     [rax+0A5C0h], r9d
0x1402df04c  mov     dword ptr [rax+0A5C4h], 1F0FFFh
0x1402df056  call    cs:__imp_W32GetUserSessionState
0x1402df05d  nop     dword ptr [rax+rax+00h]
0x1402df062  xor     ecx, ecx
0x1402df064  cmp     [rax+0F748h], rcx
0x1402df06b  setnz   cl
0x1402df06e  mov     eax, ecx
0x1402df070  jmp     loc_1402DEEE4
```
