# InitSecurity

- ea: `0x1402dcdb8`
- end: `0x1402dd075`
- name: `InitSecurity`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402db0ac`

## callees

- `0x14004a0d0`
- `0x14004c720`
- `0x14004d9d0`
- `0x14004dfe0`
- `0x1402dcdb8`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1402dcdc1`
- `ntoskrnl!SeExports` at `0x1402dce29`
- `ntoskrnl!SeExports` at `0x1402dce61`
- `ntoskrnl!SeExports` at `0x1402dcea2`
- `ntoskrnl!SeExports` at `0x1402dceee`
- `ntoskrnl!SeExports` at `0x1402dcf29`
- `ntoskrnl!SeExports` at `0x1402dcf6a`
- `ntoskrnl!RtlLengthSid` at `0x1402dcdd5`
- `ntoskrnl!RtlLengthSid` at `0x1402dcdd5`
- `ntoskrnl!RtlCopySid` at `0x1402dce1d`
- `ntoskrnl!RtlCopySid` at `0x1402dce1d`
- `WIN32K!W32GetUserSessionState` at `0x1402dcfbc`
- `WIN32K!W32GetUserSessionState` at `0x1402dcfd7`
- `WIN32K!W32GetUserSessionState` at `0x1402dcfe3`
- `WIN32K!W32GetUserSessionState` at `0x1402dd056`
- `WIN32K!W32GetUserSessionState` at `0x1402dcfbc`
- `WIN32K!W32GetUserSessionState` at `0x1402dcfd7`
- `WIN32K!W32GetUserSessionState` at `0x1402dcfe3`
- `WIN32K!W32GetUserSessionState` at `0x1402dd056`

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
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _DWORD *UserSessionState; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
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
  *(_QWORD *)(W32GetUserSessionState(v16) + 63304) = SecurityDescriptor;
  GreDeleteFastMutex(v14);
  W32GetUserSessionState(v17);
  UserSessionState = (_DWORD *)W32GetUserSessionState(v18);
  v20 = 0;
  v21 = 0;
  do
  {
    UserSessionState[v21 + 10598] = 0x20000;
    UserSessionState[v21 + 10599] = 0x20000;
    v21 += 4;
    v22 = 2 * (v20 + 2);
    ++v20;
    UserSessionState[2 * v22 + 10592] = 0x20000;
    UserSessionState[v21 + 10597] = 2031616;
  }
  while ( v20 != 24 );
  UserSessionState[10606] = 131079;
  UserSessionState[10607] = 135160;
  UserSessionState[10608] = 0x20000;
  UserSessionState[10609] = 2035711;
  return *(_QWORD *)(W32GetUserSessionState(v22) + 63304) != 0;
}

```

## disassembly

```asm
0x1402dcdb8  push    rbx
0x1402dcdba  push    rbp
0x1402dcdbb  push    rsi
0x1402dcdbc  push    rdi
0x1402dcdbd  sub     rsp, 38h
0x1402dcdc1  mov     rax, cs:__imp_SeExports
0x1402dcdc8  mov     rcx, [rax]
0x1402dcdcb  mov     rsi, [rcx+0C0h]
0x1402dcdd2  mov     rcx, rsi; Sid
0x1402dcdd5  call    cs:__imp_RtlLengthSid
0x1402dcddc  nop     dword ptr [rax+rax+00h]
0x1402dcde1  mov     r8d, 65737355h; unsigned int
0x1402dcde7  mov     ebp, eax
0x1402dcde9  lea     edi, [rax+8]
0x1402dcdec  mov     edx, edi; unsigned __int64
0x1402dcdee  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1402dcdf3  mov     rbx, rax
0x1402dcdf6  test    rax, rax
0x1402dcdf9  jz      loc_1402DCEE2
0x1402dcdff  mov     [rax+2], di
0x1402dce03  lea     rdx, [rax+8]; DestinationSid
0x1402dce07  mov     [rsp+58h+AceListLength], edi
0x1402dce0b  mov     r8, rsi; SourceSid
0x1402dce0e  mov     edi, 0F037Fh
0x1402dce13  mov     word ptr [rax], 0E00h
0x1402dce18  mov     ecx, ebp; DestinationSidLength
0x1402dce1a  mov     [rax+4], edi
0x1402dce1d  call    cs:__imp_RtlCopySid
0x1402dce24  nop     dword ptr [rax+rax+00h]
0x1402dce29  mov     rax, cs:__imp_SeExports
0x1402dce30  lea     rcx, [rsp+58h+AceListLength]
0x1402dce35  mov     [rsp+58h+var_30], rcx; __int64
0x1402dce3a  mov     r9d, edi
0x1402dce3d  mov     r8b, 0Eh
0x1402dce40  xor     edx, edx
0x1402dce42  mov     rcx, rbx; Buffer
0x1402dce45  mov     rax, [rax]
0x1402dce48  mov     rax, [rax+158h]
0x1402dce4f  mov     [rsp+58h+Sid], rax; Sid
0x1402dce54  call    AllocAce
0x1402dce59  mov     rdi, rax
0x1402dce5c  test    rax, rax
0x1402dce5f  jz      short loc_1402DCEDA
0x1402dce61  mov     rax, cs:__imp_SeExports
0x1402dce68  lea     rcx, [rsp+58h+AceListLength]
0x1402dce6d  mov     [rsp+58h+var_30], rcx; __int64
0x1402dce72  mov     esi, 10000000h
0x1402dce77  mov     r9d, esi
0x1402dce7a  mov     r8b, 9
0x1402dce7d  xor     edx, edx
0x1402dce7f  mov     rcx, rdi; Buffer
0x1402dce82  mov     rax, [rax]
0x1402dce85  mov     rax, [rax+0C0h]
0x1402dce8c  mov     [rsp+58h+Sid], rax; Sid
0x1402dce91  call    AllocAce
0x1402dce96  mov     rbx, rax
0x1402dce99  test    rax, rax
0x1402dce9c  jz      loc_1402DCFA2
0x1402dcea2  mov     rax, cs:__imp_SeExports
0x1402dcea9  lea     rcx, [rsp+58h+AceListLength]
0x1402dceae  mov     [rsp+58h+var_30], rcx; __int64
0x1402dceb3  mov     r9d, esi
0x1402dceb6  mov     r8b, 9
0x1402dceb9  xor     edx, edx
0x1402dcebb  mov     rcx, rbx; Buffer
0x1402dcebe  mov     rax, [rax]
0x1402dcec1  mov     rax, [rax+158h]
0x1402dcec8  mov     [rsp+58h+Sid], rax; Sid
0x1402dcecd  call    AllocAce
0x1402dced2  mov     rdi, rax
0x1402dced5  test    rax, rax
0x1402dced8  jnz     short loc_1402DCEEE
0x1402dceda  mov     rcx, rbx; Buffer
0x1402dcedd  call    GreDeleteFastMutex
0x1402dcee2  xor     eax, eax
0x1402dcee4  add     rsp, 38h
0x1402dcee8  pop     rdi
0x1402dcee9  pop     rsi
0x1402dceea  pop     rbp
0x1402dceeb  pop     rbx
0x1402dceec  retn
0x1402dceee  mov     rax, cs:__imp_SeExports
0x1402dcef5  lea     rcx, [rsp+58h+AceListLength]
0x1402dcefa  mov     [rsp+58h+var_30], rcx; __int64
0x1402dceff  mov     r9d, 5
0x1402dcf05  xor     r8d, r8d
0x1402dcf08  xor     edx, edx
0x1402dcf0a  mov     rcx, rdi; Buffer
0x1402dcf0d  mov     rax, [rax]
0x1402dcf10  mov     rax, [rax+110h]
0x1402dcf17  mov     [rsp+58h+Sid], rax; Sid
0x1402dcf1c  call    AllocAce
0x1402dcf21  mov     rbx, rax
0x1402dcf24  test    rax, rax
0x1402dcf27  jz      short loc_1402DCFA2
0x1402dcf29  mov     rax, cs:__imp_SeExports
0x1402dcf30  lea     rcx, [rsp+58h+AceListLength]
0x1402dcf35  mov     [rsp+58h+var_30], rcx; __int64
0x1402dcf3a  mov     esi, 2
0x1402dcf3f  mov     r9d, esi
0x1402dcf42  xor     r8d, r8d
0x1402dcf45  xor     edx, edx
0x1402dcf47  mov     rcx, rbx; Buffer
0x1402dcf4a  mov     rax, [rax]
0x1402dcf4d  mov     rax, [rax+0C0h]
0x1402dcf54  mov     [rsp+58h+Sid], rax; Sid
0x1402dcf59  call    AllocAce
0x1402dcf5e  mov     rdi, rax
0x1402dcf61  test    rax, rax
0x1402dcf64  jz      loc_1402DCEDA
0x1402dcf6a  mov     rax, cs:__imp_SeExports
0x1402dcf71  lea     rcx, [rsp+58h+AceListLength]
0x1402dcf76  mov     [rsp+58h+var_30], rcx; __int64
0x1402dcf7b  mov     r9d, esi
0x1402dcf7e  xor     r8d, r8d
0x1402dcf81  xor     edx, edx
0x1402dcf83  mov     rcx, rdi; Buffer
0x1402dcf86  mov     rax, [rax]
0x1402dcf89  mov     rax, [rax+158h]
0x1402dcf90  mov     [rsp+58h+Sid], rax; Sid
0x1402dcf95  call    AllocAce
0x1402dcf9a  mov     rsi, rax
0x1402dcf9d  test    rax, rax
0x1402dcfa0  jnz     short loc_1402DCFAA
0x1402dcfa2  mov     rcx, rdi
0x1402dcfa5  jmp     loc_1402DCEDD
0x1402dcfaa  mov     edx, [rsp+58h+AceListLength]; AceListLength
0x1402dcfae  xor     r8d, r8d; DaclDefaulted
0x1402dcfb1  mov     rcx, rsi; AceList
0x1402dcfb4  call    CreateSecurityDescriptor
0x1402dcfb9  mov     rbx, rax
0x1402dcfbc  call    cs:__imp_W32GetUserSessionState
0x1402dcfc3  nop     dword ptr [rax+rax+00h]
0x1402dcfc8  mov     rcx, rsi; Buffer
0x1402dcfcb  mov     [rax+0F748h], rbx
0x1402dcfd2  call    GreDeleteFastMutex
0x1402dcfd7  call    cs:__imp_W32GetUserSessionState
0x1402dcfde  nop     dword ptr [rax+rax+00h]
0x1402dcfe3  call    cs:__imp_W32GetUserSessionState
0x1402dcfea  nop     dword ptr [rax+rax+00h]
0x1402dcfef  xor     r8d, r8d
0x1402dcff2  mov     r9d, 20000h
0x1402dcff8  xor     edx, edx
0x1402dcffa  mov     [rax+rdx+0A598h], r9d
0x1402dd002  lea     rcx, [r8+2]
0x1402dd006  mov     [rax+rdx+0A59Ch], r9d
0x1402dd00e  lea     rdx, [rdx+10h]
0x1402dd012  add     rcx, rcx
0x1402dd015  inc     r8
0x1402dd018  mov     [rax+rcx*8+0A580h], r9d
0x1402dd020  mov     dword ptr [rax+rdx+0A594h], 1F0000h
0x1402dd02b  cmp     r8, 18h
0x1402dd02f  jnz     short loc_1402DCFFA
0x1402dd031  mov     dword ptr [rax+0A5B8h], 20007h
0x1402dd03b  mov     dword ptr [rax+0A5BCh], 20FF8h
0x1402dd045  mov     [rax+0A5C0h], r9d
0x1402dd04c  mov     dword ptr [rax+0A5C4h], 1F0FFFh
0x1402dd056  call    cs:__imp_W32GetUserSessionState
0x1402dd05d  nop     dword ptr [rax+rax+00h]
0x1402dd062  xor     ecx, ecx
0x1402dd064  cmp     [rax+0F748h], rcx
0x1402dd06b  setnz   cl
0x1402dd06e  mov     eax, ecx
0x1402dd070  jmp     loc_1402DCEE4
```
