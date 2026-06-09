# RegReadConfigSettings

- ea: `0x180030dc0`
- end: `0x180031128`
- name: `RegReadConfigSettings`
- size: `872`
- prototype: `__int64 __fastcall(CRegistry *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180031130`

## callees

- `0x18000d870`
- `0x180030b90`
- `0x180030bd8`
- `0x180030d28`
- `0x180030dc0`

## string_xrefs

- `0x180030e80`: `MaxCacheIP`
- `0x1800310a9`: `AcquireIpAttempts`

## pseudocode

```c
__int64 __fastcall RegReadConfigSettings(CRegistry *this, int a2, __int64 a3)
{
  bool v6; // zf
  int v7; // eax
  int v8; // ecx
  int v9; // ecx
  BOOL v10; // eax
  int v11; // eax
  int v12; // r10d
  int v13; // r11d
  int v14; // r10d
  int v15; // r11d
  unsigned int RegString; // eax
  __int64 v17; // rcx
  int v18; // eax
  _BYTE *v19; // rax
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  unsigned __int16 *v28[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+68h] [rbp+38h] BYREF
  LPCWSTR lpSrc; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *v31; // [rsp+78h] [rbp+48h] BYREF

  LODWORD(v31) = 0;
  LODWORD(lpSrc) = 0;
  v29 = 0;
  v6 = CRegistry::ReadRegDWord(this, L"EnableVirtualIP", (unsigned int *)&lpSrc) == 0;
  v7 = 0;
  if ( v6 )
  {
    v8 = a2;
    LOBYTE(v7) = (_DWORD)lpSrc != 0;
  }
  else
  {
    v8 = 0;
  }
  *(_DWORD *)(a3 + 4) = v7;
  *(_DWORD *)a3 = v8;
  if ( CRegistry::ReadRegDWord(this, L"VirtualMode", &v29) )
  {
    v9 = 0;
    v10 = 1;
  }
  else
  {
    v9 = a2;
    v10 = v29 != 0;
  }
  *(_DWORD *)(a3 + 12) = v10;
  *(_DWORD *)(a3 + 8) = v9;
  *(_DWORD *)(a3 + 20) = 0;
  *(_DWORD *)(a3 + 16) = a2;
  if ( *(_DWORD *)(a3 + 4) )
  {
    if ( CRegistry::ReadRegDWord(this, L"VirtualizeLoopbackAdresses", (unsigned int *)&lpSrc) )
      *(_DWORD *)(a3 + 16) = 0;
    else
      *(_DWORD *)(a3 + 20) = (_DWORD)lpSrc != 0;
  }
  if ( CRegistry::ReadRegDWord(this, L"MaxCacheIP", &v29) || v29 >= 0xA )
  {
    *(_DWORD *)(a3 + 28) = 2;
    v11 = 0;
  }
  else
  {
    *(_DWORD *)(a3 + 28) = v29;
    v11 = a2;
  }
  *(_DWORD *)(a3 + 24) = v11;
  v28[0] = 0;
  LODWORD(lpSrc) = 0;
  if ( CRegistry::ReadRegString(this, L"AdapterAddress", v28, (unsigned int *)&lpSrc)
    || (unsigned int)lpSrc >> 1 >= 0x101 )
  {
    v13 = 0;
    v12 = 0;
  }
  else
  {
    StringCchCopyW((unsigned __int16 *)(a3 + 36), 0x101u, v28[0]);
    v13 = a2;
  }
  *(_DWORD *)(a3 + 552) = v12;
  *(_DWORD *)(a3 + 32) = v13;
  v28[0] = 0;
  LODWORD(lpSrc) = 0;
  if ( CRegistry::ReadRegString(this, L"VIPAdapter", v28, (unsigned int *)&lpSrc) || (unsigned int)lpSrc >> 1 >= 0x201 )
  {
    v15 = 0;
    v14 = 0;
  }
  else
  {
    StringCchCopyW((unsigned __int16 *)(a3 + 560), 0x201u, v28[0]);
    v15 = a2;
  }
  *(_DWORD *)(a3 + 1588) = v14;
  *(_DWORD *)(a3 + 556) = v15;
  lpSrc = 0;
  RegString = CRegistry::ReadRegString(this, L"IPPool", (unsigned __int16 **)&lpSrc, (unsigned int *)&v31);
  v17 = 522;
  if ( RegString || (unsigned int)v31 >= 0x20A )
  {
    v19 = (_BYTE *)(a3 + 1596);
    do
    {
      *v19++ = 0;
      --v17;
    }
    while ( v17 );
    v18 = 0;
  }
  else
  {
    LODWORD(v31) = 261;
    ExpandString(lpSrc, (LPWSTR)(a3 + 1596));
    v18 = a2;
  }
  *(_DWORD *)(a3 + 1592) = v18;
  v6 = CRegistry::ReadRegDWord(this, L"AllowPerSessionInMultiNIC", &v29) == 0;
  v20 = 0;
  if ( v6 )
  {
    v21 = a2;
    LOBYTE(v20) = v29 != 0;
  }
  else
  {
    v21 = 0;
  }
  *(_DWORD *)(a3 + 2124) = v20;
  *(_DWORD *)(a3 + 2120) = v21;
  v31 = 0;
  LODWORD(lpSrc) = 0;
  if ( !CRegistry::ReadRegString(this, L"RpcUUID", &v31, (unsigned int *)&lpSrc)
    && ((unsigned int)lpSrc & 0xFFFFFFFE) < 0x102 )
  {
    StringCchCopyW((unsigned __int16 *)(a3 + 2128), 0x81u, v31);
  }
  v6 = CRegistry::ReadRegDWord(this, L"PromptOnIPLeaseFail", &v29) == 0;
  v22 = 0;
  if ( v6 )
  {
    v23 = a2;
    LOBYTE(v22) = v29 == 1;
  }
  else
  {
    v23 = 0;
  }
  *(_DWORD *)(a3 + 2392) = v22;
  *(_DWORD *)(a3 + 2388) = v23;
  v6 = CRegistry::ReadRegDWord(this, L"ForceLogoffOnIPLeaseFail", &v29) == 0;
  v24 = 0;
  if ( v6 )
  {
    v25 = a2;
    LOBYTE(v24) = v29 == 1;
  }
  else
  {
    v25 = 0;
  }
  *(_DWORD *)(a3 + 2400) = v24;
  *(_DWORD *)(a3 + 2396) = v25;
  if ( CRegistry::ReadRegDWord(this, L"AcquireIpAttempts", &v29) || !v29 )
  {
    *(_DWORD *)(a3 + 2408) = 10;
    v26 = 0;
  }
  else
  {
    *(_DWORD *)(a3 + 2408) = v29;
    v26 = a2;
  }
  *(_DWORD *)(a3 + 2404) = v26;
  if ( CRegistry::ReadRegDWord(this, L"AcquireIpRetrySleepTime", &v29) || v29 == -1 )
  {
    *(_DWORD *)(a3 + 2416) = 1000;
    a2 = 0;
  }
  else
  {
    *(_DWORD *)(a3 + 2416) = v29;
  }
  *(_DWORD *)(a3 + 2412) = a2;
  return 0;
}

```

## disassembly

```asm
0x180030dc0  push    rbp
0x180030dc2  push    rbx
0x180030dc3  push    rsi
0x180030dc4  push    rdi
0x180030dc5  push    r14
0x180030dc7  mov     rbp, rsp
0x180030dca  sub     rsp, 30h
0x180030dce  xor     r14d, r14d
0x180030dd1  mov     rbx, r8
0x180030dd4  mov     edi, edx
0x180030dd6  mov     dword ptr [rbp+arg_18], r14d
0x180030dda  lea     r8, [rbp+lpSrc]; unsigned int *
0x180030dde  mov     dword ptr [rbp+lpSrc], r14d
0x180030de2  lea     rdx, aEnablevirtuali; "EnableVirtualIP"
0x180030de9  mov     [rbp+arg_8], r14d
0x180030ded  mov     rsi, rcx
0x180030df0  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180030df5  test    eax, eax
0x180030df7  mov     eax, r14d
0x180030dfa  jnz     short loc_180030E07
0x180030dfc  cmp     dword ptr [rbp+lpSrc], r14d
0x180030e00  mov     ecx, edi
0x180030e02  setnz   al
0x180030e05  jmp     short loc_180030E0A
0x180030e07  mov     ecx, r14d
0x180030e0a  mov     [rbx+4], eax
0x180030e0d  lea     r8, [rbp+arg_8]; unsigned int *
0x180030e11  mov     [rbx], ecx
0x180030e13  lea     rdx, aVirtualmode; "VirtualMode"
0x180030e1a  mov     rcx, rsi; this
0x180030e1d  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180030e22  test    eax, eax
0x180030e24  jnz     short loc_180030E34
0x180030e26  cmp     [rbp+arg_8], r14d
0x180030e2a  mov     eax, r14d
0x180030e2d  mov     ecx, edi
0x180030e2f  setnz   al
0x180030e32  jmp     short loc_180030E3C
0x180030e34  mov     ecx, r14d
0x180030e37  mov     eax, 1
0x180030e3c  mov     [rbx+0Ch], eax
0x180030e3f  mov     [rbx+8], ecx
0x180030e42  mov     [rbx+14h], r14d
0x180030e46  mov     [rbx+10h], edi
0x180030e49  cmp     [rbx+4], r14d
0x180030e4d  jz      short loc_180030E79
0x180030e4f  lea     r8, [rbp+lpSrc]; unsigned int *
0x180030e53  mov     rcx, rsi; this
0x180030e56  lea     rdx, aVirtualizeloop; "VirtualizeLoopbackAdresses"
0x180030e5d  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180030e62  test    eax, eax
0x180030e64  jnz     short loc_180030E75
0x180030e66  cmp     dword ptr [rbp+lpSrc], r14d
0x180030e6a  mov     eax, r14d
0x180030e6d  setnz   al
0x180030e70  mov     [rbx+14h], eax
0x180030e73  jmp     short loc_180030E79
0x180030e75  mov     [rbx+10h], r14d
0x180030e79  lea     r8, [rbp+arg_8]; unsigned int *
0x180030e7d  mov     rcx, rsi; this
0x180030e80  lea     rdx, aMaxcacheip; "MaxCacheIP"
0x180030e87  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180030e8c  test    eax, eax
0x180030e8e  jnz     short loc_180030E9F
0x180030e90  mov     eax, [rbp+arg_8]
0x180030e93  cmp     eax, 0Ah
0x180030e96  jnb     short loc_180030E9F
0x180030e98  mov     [rbx+1Ch], eax
0x180030e9b  mov     eax, edi
0x180030e9d  jmp     short loc_180030EA9
0x180030e9f  mov     dword ptr [rbx+1Ch], 2
0x180030ea6  mov     eax, r14d
0x180030ea9  mov     [rbx+18h], eax
0x180030eac  lea     r9, [rbp+lpSrc]; unsigned int *
0x180030eb0  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180030eb4  mov     [rbp+var_10], r14
0x180030eb8  lea     rdx, ValueName; "AdapterAddress"
0x180030ebf  mov     dword ptr [rbp+lpSrc], r14d
0x180030ec3  mov     rcx, rsi; this
0x180030ec6  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180030ecb  test    eax, eax
0x180030ecd  jnz     short loc_180030EF2
0x180030ecf  mov     eax, dword ptr [rbp+lpSrc]
0x180030ed2  mov     edx, 101h; unsigned __int64
0x180030ed7  shr     eax, 1
0x180030ed9  mov     r10d, eax
0x180030edc  cmp     eax, edx
0x180030ede  jnb     short loc_180030EF2
0x180030ee0  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180030ee4  lea     rcx, [rbx+24h]; unsigned __int16 *
0x180030ee8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030eed  mov     r11d, edi
0x180030ef0  jmp     short loc_180030EF8
0x180030ef2  mov     r11d, r14d
0x180030ef5  mov     r10d, r14d
0x180030ef8  mov     [rbx+228h], r10d
0x180030eff  lea     r9, [rbp+lpSrc]; unsigned int *
0x180030f03  mov     [rbx+20h], r11d
0x180030f07  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180030f0b  lea     rdx, aVipadapter; "VIPAdapter"
0x180030f12  mov     [rbp+var_10], r14
0x180030f16  mov     rcx, rsi; this
0x180030f19  mov     dword ptr [rbp+lpSrc], r14d
0x180030f1d  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180030f22  test    eax, eax
0x180030f24  jnz     short loc_180030F4C
0x180030f26  mov     eax, dword ptr [rbp+lpSrc]
0x180030f29  mov     edx, 201h; unsigned __int64
0x180030f2e  shr     eax, 1
0x180030f30  mov     r10d, eax
0x180030f33  cmp     eax, edx
0x180030f35  jnb     short loc_180030F4C
0x180030f37  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180030f3b  lea     rcx, [rbx+230h]; unsigned __int16 *
0x180030f42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030f47  mov     r11d, edi
0x180030f4a  jmp     short loc_180030F52
0x180030f4c  mov     r11d, r14d
0x180030f4f  mov     r10d, r14d
0x180030f52  mov     [rbx+634h], r10d
0x180030f59  lea     r9, [rbp+arg_18]; unsigned int *
0x180030f5d  mov     [rbx+22Ch], r11d
0x180030f64  lea     r8, [rbp+lpSrc]; unsigned __int16 **
0x180030f68  lea     rdx, aIppool; "IPPool"
0x180030f6f  mov     [rbp+lpSrc], r14
0x180030f73  mov     rcx, rsi; this
0x180030f76  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180030f7b  mov     ecx, 20Ah
0x180030f80  test    eax, eax
0x180030f82  jnz     short loc_180030FA8
0x180030f84  cmp     dword ptr [rbp+arg_18], ecx
0x180030f87  jnb     short loc_180030FA8
0x180030f89  mov     rcx, [rbp+lpSrc]; lpSrc
0x180030f8d  lea     rdx, [rbx+63Ch]; lpDst
0x180030f94  lea     r8, [rbp+arg_18]
0x180030f98  mov     dword ptr [rbp+arg_18], 105h
0x180030f9f  call    ExpandString
0x180030fa4  mov     eax, edi
0x180030fa6  jmp     short loc_180030FBE
0x180030fa8  lea     rax, [rbx+63Ch]
0x180030faf  mov     [rax], r14b
0x180030fb2  inc     rax
0x180030fb5  sub     rcx, 1
0x180030fb9  jnz     short loc_180030FAF
0x180030fbb  mov     eax, r14d
0x180030fbe  lea     r8, [rbp+arg_8]; unsigned int *
0x180030fc2  mov     [rbx+638h], eax
0x180030fc8  lea     rdx, aAllowpersessio; "AllowPerSessionInMultiNIC"
0x180030fcf  mov     rcx, rsi; this
0x180030fd2  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180030fd7  test    eax, eax
0x180030fd9  mov     eax, r14d
0x180030fdc  jnz     short loc_180030FE9
0x180030fde  cmp     [rbp+arg_8], r14d
0x180030fe2  mov     ecx, edi
0x180030fe4  setnz   al
0x180030fe7  jmp     short loc_180030FEC
0x180030fe9  mov     ecx, r14d
0x180030fec  mov     [rbx+84Ch], eax
0x180030ff2  lea     r9, [rbp+lpSrc]; unsigned int *
0x180030ff6  mov     [rbx+848h], ecx
0x180030ffc  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x180031000  mov     rcx, rsi; this
0x180031003  mov     [rbp+arg_18], r14
0x180031007  lea     rdx, aRpcuuid; "RpcUUID"
0x18003100e  mov     dword ptr [rbp+lpSrc], r14d
0x180031012  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180031017  test    eax, eax
0x180031019  jnz     short loc_18003103D
0x18003101b  mov     eax, dword ptr [rbp+lpSrc]
0x18003101e  and     eax, 0FFFFFFFEh
0x180031021  cmp     eax, 102h
0x180031026  jnb     short loc_18003103D
0x180031028  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18003102c  lea     rcx, [rbx+850h]; unsigned __int16 *
0x180031033  mov     edx, 81h; unsigned __int64
0x180031038  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003103d  lea     r8, [rbp+arg_8]; unsigned int *
0x180031041  mov     rcx, rsi; this
0x180031044  lea     rdx, aPromptonipleas; "PromptOnIPLeaseFail"
0x18003104b  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180031050  test    eax, eax
0x180031052  mov     eax, r14d
0x180031055  jnz     short loc_180031062
0x180031057  cmp     [rbp+arg_8], 1
0x18003105b  mov     ecx, edi
0x18003105d  setz    al
0x180031060  jmp     short loc_180031065
0x180031062  mov     ecx, r14d
0x180031065  mov     [rbx+958h], eax
0x18003106b  lea     r8, [rbp+arg_8]; unsigned int *
0x18003106f  mov     [rbx+954h], ecx
0x180031075  lea     rdx, aForcelogoffoni; "ForceLogoffOnIPLeaseFail"
0x18003107c  mov     rcx, rsi; this
0x18003107f  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180031084  test    eax, eax
0x180031086  mov     eax, r14d
0x180031089  jnz     short loc_180031096
0x18003108b  cmp     [rbp+arg_8], 1
0x18003108f  mov     ecx, edi
0x180031091  setz    al
0x180031094  jmp     short loc_180031099
0x180031096  mov     ecx, r14d
0x180031099  mov     [rbx+960h], eax
0x18003109f  lea     r8, [rbp+arg_8]; unsigned int *
0x1800310a3  mov     [rbx+95Ch], ecx
0x1800310a9  lea     rdx, aAcquireipattem; "AcquireIpAttempts"
0x1800310b0  mov     rcx, rsi; this
0x1800310b3  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x1800310b8  test    eax, eax
0x1800310ba  jnz     short loc_1800310CD
0x1800310bc  mov     eax, [rbp+arg_8]
0x1800310bf  test    eax, eax
0x1800310c1  jz      short loc_1800310CD
0x1800310c3  mov     [rbx+968h], eax
0x1800310c9  mov     eax, edi
0x1800310cb  jmp     short loc_1800310DA
0x1800310cd  mov     dword ptr [rbx+968h], 0Ah
0x1800310d7  mov     eax, r14d
0x1800310da  lea     r8, [rbp+arg_8]; unsigned int *
0x1800310de  mov     [rbx+964h], eax
0x1800310e4  lea     rdx, aAcquireipretry; "AcquireIpRetrySleepTime"
0x1800310eb  mov     rcx, rsi; this
0x1800310ee  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x1800310f3  test    eax, eax
0x1800310f5  jnz     short loc_180031107
0x1800310f7  mov     eax, [rbp+arg_8]
0x1800310fa  cmp     eax, 0FFFFFFFFh
0x1800310fd  jz      short loc_180031107
0x1800310ff  mov     [rbx+970h], eax
0x180031105  jmp     short loc_180031114
0x180031107  mov     dword ptr [rbx+970h], 3E8h
0x180031111  mov     edi, r14d
0x180031114  mov     [rbx+96Ch], edi
0x18003111a  xor     eax, eax
0x18003111c  add     rsp, 30h
0x180031120  pop     r14
0x180031122  pop     rdi
0x180031123  pop     rsi
0x180031124  pop     rbx
0x180031125  pop     rbp
0x180031126  retn
```
