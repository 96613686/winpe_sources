# I_CreateKeyLocking(VCHANNEL_DATA *,uchar,uchar,uchar)

- ea: `0x18001f558`
- end: `0x18001f77d`
- name: `?I_CreateKeyLocking@@YAKPEAUVCHANNEL_DATA@@EEE@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct VCHANNEL_DATA *, char, char, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002d830`

## callees

- `0x180001ec0`
- `0x18000a110`
- `0x18000bc48`
- `0x18000c124`
- `0x18000c198`
- `0x18001ccf8`
- `0x18001d8e4`
- `0x18001f558`
- `0x180023e54`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f740`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f750`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f740`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f750`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f698`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f698`

## string_xrefs

- `0x18001f70b`: `Unable to create asymmetric key`
- `0x18001f597`: `I_CreateKeyLocking`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall I_CreateKeyLocking(struct VCHANNEL_DATA *a1, char a2, char a3, char a4)
{
  __int64 v5; // rdx
  struct VCHANNEL_DATA *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  char v9; // al
  int v10; // r9d
  RTL_SRWLOCK *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // edi
  unsigned int v16; // [rsp+30h] [rbp-69h] BYREF
  int v17; // [rsp+34h] [rbp-65h] BYREF
  struct VCHANNEL_DATA *v18; // [rsp+38h] [rbp-61h] BYREF
  _QWORD *v19; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v20[5]; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v21[8]; // [rsp+70h] [rbp-29h] BYREF
  char v22[24]; // [rsp+B0h] [rbp+17h] BYREF
  char v23; // [rsp+110h] [rbp+77h] BYREF
  char v24; // [rsp+118h] [rbp+7Fh] BYREF

  v24 = a4;
  v23 = a3;
  v18 = a1;
  v16 = 0;
  v17 = 0;
  strcpy(v22, "I_CreateKeyLocking");
  v20[0] = v22;
  v20[1] = &v17;
  v20[2] = &v16;
  lambda_3a7db05ab8ed5421c8037679721c0087_::operator()(v20);
  v17 = 1;
  v19 = v20;
  v6 = v18;
  if ( !v18 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v5);
    v6 = v18;
  }
  if ( !(unsigned int)I_IsRoleAuthenticated(v6, 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( (unsigned __int8)(a2 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( (unsigned __int8)((v23 & 0xF) - 6) > 3u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  LOBYTE(v8) = v24;
  v9 = v24 & 1;
  if ( (v24 & 6) == 0 )
    v9 = 1;
  if ( v9 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( (unsigned __int8)((v23 & 0xF) - 6) > 3u )
  {
    WppTraceIndent(v8, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          102,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          v10,
          87);
    }
    __fastfail(0x57u);
  }
  v11 = (RTL_SRWLOCK *)(*(_QWORD *)v18 + 56LL);
  AcquireSRWLockExclusive(v11);
  v20[3] = v11;
  v21[0] = off_180038340;
  v21[1] = &v18;
  v21[2] = &v23;
  v21[3] = &v24;
  v21[7] = v21;
  LOBYTE(v12) = a2;
  v16 = I_StoreAsymKey(v18, v12, v21);
  if ( v16 )
  {
    WppTraceIndent(v13, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v16,
        (__int64)"Unable to create asymmetric key");
    }
    v14 = v16;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
  }
  else
  {
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v14 = 0;
  }
  WppTraceUnwinder__lambda_3a7db05ab8ed5421c8037679721c0087____::_WppTraceUnwinder__lambda_3a7db05ab8ed5421c8037679721c0087____(&v19);
  return v14;
}

```

## disassembly

```asm
0x18001f558  mov     [rsp-8+arg_18], r9b
0x18001f55d  mov     [rsp-8+arg_10], r8b
0x18001f562  push    rbp
0x18001f563  push    rbx
0x18001f564  push    rsi
0x18001f565  push    rdi
0x18001f566  push    r15
0x18001f568  lea     rbp, [rsp-37h]
0x18001f56d  sub     rsp, 0D0h
0x18001f574  mov     rax, cs:__security_cookie
0x18001f57b  xor     rax, rsp
0x18001f57e  mov     [rbp+57h+var_28], rax
0x18001f582  mov     dil, dl
0x18001f585  mov     [rbp+57h+var_B8], rcx
0x18001f589  mov     [rbp+57h+var_C0], 0
0x18001f590  mov     [rbp+57h+var_BC], 0
0x18001f597  movups  xmm0, xmmword ptr cs:aICreatekeylock; "I_CreateKeyLocking"
0x18001f59e  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18001f5a2  mov     eax, dword ptr cs:aICreatekeylock+0Fh; "ing"
0x18001f5a8  mov     dword ptr [rbp+57h+var_40+0Fh], eax
0x18001f5ab  lea     rax, [rbp+57h+var_40]
0x18001f5af  mov     [rbp+57h+var_A8], rax
0x18001f5b3  lea     rax, [rbp+57h+var_BC]
0x18001f5b7  mov     [rbp+57h+var_A0], rax
0x18001f5bb  lea     rax, [rbp+57h+var_C0]
0x18001f5bf  mov     [rbp+57h+var_98], rax
0x18001f5c3  lea     rcx, [rbp+57h+var_A8]
0x18001f5c7  call    _lambda_3a7db05ab8ed5421c8037679721c0087___operator__
0x18001f5cc  mov     esi, 1
0x18001f5d1  mov     [rbp+57h+var_BC], esi
0x18001f5d4  lea     rax, [rbp+57h+var_A8]
0x18001f5d8  mov     [rbp+57h+var_B0], rax
0x18001f5dc  mov     rcx, [rbp+57h+var_B8]
0x18001f5e0  test    rcx, rcx
0x18001f5e3  jnz     short loc_18001F5EE
0x18001f5e5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f5ea  mov     rcx, [rbp+57h+var_B8]
0x18001f5ee  mov     edx, esi
0x18001f5f0  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x18001f5f5  test    eax, eax
0x18001f5f7  jnz     short loc_18001F5FE
0x18001f5f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f5fe  lea     eax, [rdi-80h]
0x18001f601  cmp     al, 20h ; ' '
0x18001f603  jbe     short loc_18001F60A
0x18001f605  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f60a  mov     al, [rbp+57h+arg_10]
0x18001f60d  and     al, 0Fh
0x18001f60f  mov     bl, 6
0x18001f611  sub     al, bl
0x18001f613  cmp     al, 3
0x18001f615  jbe     short loc_18001F61C
0x18001f617  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f61c  mov     al, [rbp+57h+arg_18]
0x18001f61f  mov     cl, al
0x18001f621  and     al, sil
0x18001f624  movzx   eax, al
0x18001f627  test    bl, cl
0x18001f629  cmovz   eax, esi
0x18001f62c  test    al, al
0x18001f62e  jz      short loc_18001F635
0x18001f630  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f635  mov     al, [rbp+57h+arg_10]
0x18001f638  and     al, 0Fh
0x18001f63a  sub     al, bl
0x18001f63c  lea     r15, WPP_GLOBAL_Control
0x18001f643  cmp     al, 3
0x18001f645  jbe     short loc_18001F68A
0x18001f647  mov     edx, 2
0x18001f64c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f651  mov     ebx, 57h ; 'W'
0x18001f656  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f65d  cmp     rcx, r15
0x18001f660  jz      short loc_18001F685
0x18001f662  test    [rcx+1Ch], sil
0x18001f666  jz      short loc_18001F685
0x18001f668  cmp     [rcx+19h], sil
0x18001f66c  jb      short loc_18001F685
0x18001f66e  lea     edx, [rbx+0Fh]
0x18001f671  mov     [rsp+0F0h+var_D0], ebx
0x18001f675  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001f67c  mov     rcx, [rcx+10h]
0x18001f680  call    WPP_SF_sD
0x18001f685  mov     rcx, rbx
0x18001f688  int     29h; Win8: RtlFailFast(ecx)
0x18001f68a  mov     rax, [rbp+57h+var_B8]
0x18001f68e  mov     rbx, [rax]
0x18001f691  add     rbx, 38h ; '8'
0x18001f695  mov     rcx, rbx; SRWLock
0x18001f698  call    cs:__imp_AcquireSRWLockExclusive
0x18001f69e  mov     [rbp+57h+var_90], rbx
0x18001f6a2  lea     rax, off_180038340
0x18001f6a9  mov     [rbp+57h+var_80], rax
0x18001f6ad  lea     rax, [rbp+57h+var_B8]
0x18001f6b1  mov     [rbp+57h+var_78], rax
0x18001f6b5  lea     rax, [rbp+57h+arg_10]
0x18001f6b9  mov     [rbp+57h+var_70], rax
0x18001f6bd  lea     rax, [rbp+57h+arg_18]
0x18001f6c1  mov     [rbp+57h+var_68], rax
0x18001f6c5  lea     rax, [rbp+57h+var_80]
0x18001f6c9  mov     [rbp+57h+var_48], rax
0x18001f6cd  lea     r8, [rbp+57h+var_80]
0x18001f6d1  mov     dl, dil
0x18001f6d4  mov     rcx, [rbp+57h+var_B8]
0x18001f6d8  call    I_StoreAsymKey
0x18001f6dd  mov     [rbp+57h+var_C0], eax
0x18001f6e0  test    eax, eax
0x18001f6e2  jz      short loc_18001F748
0x18001f6e4  mov     edx, 2
0x18001f6e9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6f5  cmp     rcx, r15
0x18001f6f8  jz      short loc_18001F735
0x18001f6fa  test    [rcx+1Ch], sil
0x18001f6fe  jz      short loc_18001F735
0x18001f700  cmp     byte ptr [rcx+19h], 2
0x18001f704  jb      short loc_18001F735
0x18001f706  mov     edx, 67h ; 'g'
0x18001f70b  lea     rax, aUnableToCreate_15; "Unable to create asymmetric key"
0x18001f712  mov     [rsp+0F0h+var_C8], rax
0x18001f717  mov     eax, [rbp+57h+var_C0]
0x18001f71a  mov     [rsp+0F0h+var_D0], eax
0x18001f71e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f725  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001f72c  mov     rcx, [rcx+10h]
0x18001f730  call    WPP_SF_sDs
0x18001f735  mov     edi, [rbp+57h+var_C0]
0x18001f738  test    rbx, rbx
0x18001f73b  jz      short loc_18001F758
0x18001f73d  mov     rcx, rbx; SRWLock
0x18001f740  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f746  jmp     short loc_18001F758
0x18001f748  test    rbx, rbx
0x18001f74b  jz      short loc_18001F756
0x18001f74d  mov     rcx, rbx; SRWLock
0x18001f750  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f756  xor     edi, edi
0x18001f758  lea     rcx, [rbp+57h+var_B0]
0x18001f75c  call    WppTraceUnwinder__lambda_3a7db05ab8ed5421c8037679721c0087_______WppTraceUnwinder__lambda_3a7db05ab8ed5421c8037679721c0087____
0x18001f761  mov     eax, edi
0x18001f763  mov     rcx, [rbp+57h+var_28]
0x18001f767  xor     rcx, rsp; StackCookie
0x18001f76a  call    __security_check_cookie
0x18001f76f  add     rsp, 0D0h
0x18001f776  pop     r15
0x18001f778  pop     rdi
0x18001f779  pop     rsi
0x18001f77a  pop     rbx
0x18001f77b  pop     rbp
0x18001f77c  retn
```
