# GetUserNameAndSid(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x140006d7c`
- end: `0x140006fe0`
- name: `?GetUserNameAndSid@@YAHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `612`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005658`

## callees

- `0x1400014f0`
- `0x140003004`
- `0x140003bf8`
- `0x14000491c`
- `0x1400053b4`
- `0x1400053dc`
- `0x140006b4c`
- `0x140006bd0`
- `0x140006c7c`
- `0x140006d7c`
- `0x140006fe8`
- `0x1400073b4`

## import_xrefs

- `SspiCli!GetUserNameExW` at `0x140006e16`
- `SspiCli!GetUserNameExW` at `0x140006e16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUserNameAndSid(_QWORD *a1, LPWSTR *a2)
{
  BOOLEAN UserName; // al
  unsigned int v5; // edi
  LPWSTR v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rax
  const unsigned __int16 *v9; // r8
  unsigned __int8 Account; // al
  _QWORD *v11; // rcx
  const unsigned __int16 *v12; // rax
  ULONG nSize[4]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v15[128]; // [rsp+30h] [rbp-B8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids);
  }
  nSize[0] = 0x7FFF;
  if ( ((*((_DWORD *)*a2 - 3) - 0x7FFF) | (1 - *((_DWORD *)*a2 - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, 0x7FFF);
  UserName = GetUserNameExW(NameSamCompatible, *a2, nSize);
  v5 = UserName;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, UserName);
  }
  v6 = *a2;
  v7 = -1;
  if ( *a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v6[v8] );
    if ( (int)v8 < 0 )
LABEL_40:
      ATL::AtlThrowImpl(-2147024809);
  }
  else
  {
    LODWORD(v8) = 0;
  }
  if ( (int)v8 > *((_DWORD *)v6 - 3) )
    goto LABEL_40;
  *((_DWORD *)v6 - 4) = v8;
  (*a2)[(unsigned int)v8] = 0;
  ATL::CSid::CSid((ATL::CSid *)v15);
  if ( v5 != 1 )
  {
LABEL_26:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, *a2, nSize[0]);
  }
  Account = ATL::CSid::LoadAccount((ATL::CSid *)v15, *a2, v9);
  v5 = Account;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, Account);
    goto LABEL_26;
  }
LABEL_27:
  if ( v5 != 1 )
  {
LABEL_35:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      WPP_SF_d(v11[2], 23, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v5);
    goto LABEL_39;
  }
  v12 = ATL::CSid::Sid((ATL::CSid *)v15);
  if ( v12 )
  {
    do
      ++v7;
    while ( v12[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v12, (unsigned int)v7);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, *a1, nSize[0]);
      v11 = WPP_GLOBAL_Control;
    }
    goto LABEL_35;
  }
LABEL_39:
  ATL::CSid::~CSid((ATL::CSid *)v15);
  return v5;
}

```

## disassembly

```asm
0x140006d7c  mov     [rsp+arg_10], rbx
0x140006d81  push    rbp
0x140006d82  push    rsi
0x140006d83  push    rdi
0x140006d84  push    r12
0x140006d86  push    r14
0x140006d88  sub     rsp, 0C0h
0x140006d8f  mov     rax, cs:__security_cookie
0x140006d96  xor     rax, rsp
0x140006d99  mov     [rsp+0E8h+var_38], rax
0x140006da1  mov     rbx, rdx
0x140006da4  mov     r14, rcx
0x140006da7  lea     rsi, WPP_GLOBAL_Control
0x140006dae  lea     r12, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x140006db5  mov     rcx, cs:WPP_GLOBAL_Control
0x140006dbc  cmp     rcx, rsi
0x140006dbf  jz      short loc_140006DDE
0x140006dc1  test    byte ptr [rcx+1Ch], 1
0x140006dc5  jz      short loc_140006DDE
0x140006dc7  cmp     byte ptr [rcx+19h], 5
0x140006dcb  jb      short loc_140006DDE
0x140006dcd  mov     edx, 12h
0x140006dd2  mov     r8, r12
0x140006dd5  mov     rcx, [rcx+10h]
0x140006dd9  call    WPP_SF_
0x140006dde  mov     r8d, 7FFFh
0x140006de4  mov     [rsp+0E8h+nSize], r8d
0x140006de9  mov     rax, [rbx]
0x140006dec  mov     edx, 1
0x140006df1  sub     edx, [rax-8]
0x140006df4  mov     ecx, [rax-0Ch]
0x140006df7  sub     ecx, r8d
0x140006dfa  or      edx, ecx
0x140006dfc  jge     short loc_140006E09
0x140006dfe  mov     edx, r8d
0x140006e01  mov     rcx, rbx
0x140006e04  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140006e09  lea     r8, [rsp+0E8h+nSize]; nSize
0x140006e0e  mov     rdx, [rbx]; lpNameBuffer
0x140006e11  mov     ecx, 2; NameFormat
0x140006e16  call    cs:__imp_GetUserNameExW
0x140006e1c  movzx   edi, al
0x140006e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e26  cmp     rcx, rsi
0x140006e29  jz      short loc_140006E4B
0x140006e2b  test    byte ptr [rcx+1Ch], 2
0x140006e2f  jz      short loc_140006E4B
0x140006e31  cmp     byte ptr [rcx+19h], 4
0x140006e35  jb      short loc_140006E4B
0x140006e37  mov     edx, 13h
0x140006e3c  mov     r9d, edi
0x140006e3f  mov     r8, r12
0x140006e42  mov     rcx, [rcx+10h]
0x140006e46  call    WPP_SF_d
0x140006e4b  mov     rcx, [rbx]
0x140006e4e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006e52  xor     ebp, ebp
0x140006e54  test    rcx, rcx
0x140006e57  jnz     short loc_140006E5D
0x140006e59  mov     eax, ebp
0x140006e5b  jmp     short loc_140006E71
0x140006e5d  mov     rax, rsi
0x140006e60  inc     rax
0x140006e63  cmp     [rcx+rax*2], bp
0x140006e67  jnz     short loc_140006E60
0x140006e69  test    eax, eax
0x140006e6b  js      loc_140006FD5
0x140006e71  cmp     eax, [rcx-0Ch]
0x140006e74  jg      loc_140006FD5
0x140006e7a  mov     [rcx-10h], eax
0x140006e7d  mov     edx, eax
0x140006e7f  mov     rcx, [rbx]
0x140006e82  mov     [rcx+rdx*2], bp
0x140006e86  lea     rcx, [rsp+0E8h+var_B8]; this
0x140006e8b  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x140006e90  nop
0x140006e91  cmp     edi, 1
0x140006e94  jnz     short loc_140006F0C
0x140006e96  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e9d  lea     rax, WPP_GLOBAL_Control
0x140006ea4  cmp     rcx, rax
0x140006ea7  jz      short loc_140006EC7
0x140006ea9  test    byte ptr [rcx+1Ch], 2
0x140006ead  jz      short loc_140006EC7
0x140006eaf  cmp     byte ptr [rcx+19h], 4
0x140006eb3  jb      short loc_140006EC7
0x140006eb5  lea     edx, [rdi+13h]
0x140006eb8  mov     r9, [rbx]
0x140006ebb  mov     r8, r12
0x140006ebe  mov     rcx, [rcx+10h]
0x140006ec2  call    WPP_SF_S
0x140006ec7  mov     rdx, [rbx]; unsigned __int16 *
0x140006eca  lea     rcx, [rsp+0E8h+var_B8]; this
0x140006ecf  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z; ATL::CSid::LoadAccount(ushort const *,ushort const *)
0x140006ed4  movzx   edi, al
0x140006ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ede  lea     rbx, WPP_GLOBAL_Control
0x140006ee5  cmp     rcx, rbx
0x140006ee8  jz      short loc_140006F1A
0x140006eea  test    byte ptr [rcx+1Ch], 2
0x140006eee  jz      short loc_140006F1A
0x140006ef0  cmp     byte ptr [rcx+19h], 4
0x140006ef4  jb      short loc_140006F1A
0x140006ef6  mov     edx, 15h
0x140006efb  mov     r9d, edi
0x140006efe  mov     r8, r12
0x140006f01  mov     rcx, [rcx+10h]
0x140006f05  call    WPP_SF_d
0x140006f0a  jmp     short loc_140006F13
0x140006f0c  lea     rbx, WPP_GLOBAL_Control
0x140006f13  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f1a  cmp     edi, 1
0x140006f1d  jnz     short loc_140006F7C
0x140006f1f  lea     rcx, [rsp+0E8h+var_B8]; this
0x140006f24  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x140006f29  test    rax, rax
0x140006f2c  jnz     short loc_140006F32
0x140006f2e  mov     esi, ebp
0x140006f30  jmp     short loc_140006F3B
0x140006f32  inc     rsi
0x140006f35  cmp     [rax+rsi*2], bp
0x140006f39  jnz     short loc_140006F32
0x140006f3b  mov     r8d, esi
0x140006f3e  mov     rdx, rax
0x140006f41  mov     rcx, r14
0x140006f44  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140006f49  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f50  cmp     rcx, rbx
0x140006f53  jz      short loc_140006FA2
0x140006f55  test    byte ptr [rcx+1Ch], 2
0x140006f59  jz      short loc_140006F7C
0x140006f5b  cmp     byte ptr [rcx+19h], 4
0x140006f5f  jb      short loc_140006F7C
0x140006f61  mov     edx, 16h
0x140006f66  mov     r9, [r14]
0x140006f69  mov     r8, r12
0x140006f6c  mov     rcx, [rcx+10h]
0x140006f70  call    WPP_SF_S
0x140006f75  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f7c  cmp     rcx, rbx
0x140006f7f  jz      short loc_140006FA2
0x140006f81  test    byte ptr [rcx+1Ch], 1
0x140006f85  jz      short loc_140006FA2
0x140006f87  cmp     byte ptr [rcx+19h], 5
0x140006f8b  jb      short loc_140006FA2
0x140006f8d  mov     edx, 17h
0x140006f92  mov     r9d, edi
0x140006f95  mov     r8, r12
0x140006f98  mov     rcx, [rcx+10h]
0x140006f9c  call    WPP_SF_d
0x140006fa1  nop
0x140006fa2  lea     rcx, [rsp+0E8h+var_B8]; this
0x140006fa7  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140006fac  mov     eax, edi
0x140006fae  mov     rcx, [rsp+0E8h+var_38]
0x140006fb6  xor     rcx, rsp; StackCookie
0x140006fb9  call    __security_check_cookie
0x140006fbe  mov     rbx, [rsp+0E8h+arg_10]
0x140006fc6  add     rsp, 0C0h
0x140006fcd  pop     r14
0x140006fcf  pop     r12
0x140006fd1  pop     rdi
0x140006fd2  pop     rsi
0x140006fd3  pop     rbp
0x140006fd4  retn
0x140006fd5  mov     ecx, 80070057h; int
0x140006fda  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
