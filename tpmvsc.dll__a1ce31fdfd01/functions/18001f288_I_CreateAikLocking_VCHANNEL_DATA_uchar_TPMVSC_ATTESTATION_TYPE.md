# I_CreateAikLocking(VCHANNEL_DATA *,uchar,TPMVSC_ATTESTATION_TYPE)

- ea: `0x18001f288`
- end: `0x18001f423`
- name: `?I_CreateAikLocking@@YAKPEAUVCHANNEL_DATA@@EW4TPMVSC_ATTESTATION_TYPE@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(RTL_SRWLOCK **, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016954`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18001ce10`
- `0x18001e070`
- `0x18001f288`
- `0x180023a38`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f33f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f33f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f323`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f323`

## string_xrefs

- `0x18001f2c3`: `I_CreateAikLocking`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_CreateAikLocking(RTL_SRWLOCK **a1, __int64 a2, int a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  RTL_SRWLOCK **v5; // rax
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // edi
  int v11; // [rsp+38h] [rbp-49h] BYREF
  int v12; // [rsp+3Ch] [rbp-45h] BYREF
  RTL_SRWLOCK **v13; // [rsp+40h] [rbp-41h] BYREF
  _QWORD *v14; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v15[5]; // [rsp+50h] [rbp-31h] BYREF
  _QWORD v16[8]; // [rsp+78h] [rbp-9h] BYREF
  char v17[24]; // [rsp+B8h] [rbp+37h] BYREF
  int v18; // [rsp+F8h] [rbp+77h] BYREF

  v18 = a3;
  v13 = a1;
  v11 = 0;
  v12 = 0;
  strcpy(v17, "I_CreateAikLocking");
  v15[0] = v17;
  v15[1] = &v12;
  v15[2] = &v11;
  lambda_a1409a84bbe01405fb965e20b27d848b_::operator()(v15);
  v12 = 1;
  v14 = v15;
  v5 = v13;
  if ( !v13 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3);
    v5 = v13;
  }
  v6 = *v5 + 7;
  AcquireSRWLockExclusive(v6);
  v15[3] = v6;
  if ( v18 )
  {
    if ( (unsigned int)(v18 - 1) <= 1 )
    {
      v16[0] = off_180038310;
      v16[1] = &v13;
      v16[2] = &v18;
      v16[7] = v16;
      v9 = I_StoreAik(v13, v7, v16);
      v11 = v9;
    }
    else
    {
      WppTraceIndent(v8, 2);
      v9 = 87;
      v11 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          87,
          (__int64)"Invalid attestation type");
        v9 = v11;
      }
    }
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
  }
  else
  {
    v11 = 0;
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
    v9 = 0;
  }
  WppTraceUnwinder__lambda_a1409a84bbe01405fb965e20b27d848b____::_WppTraceUnwinder__lambda_a1409a84bbe01405fb965e20b27d848b____(&v14);
  return v9;
}

```

## disassembly

```asm
0x18001f288  mov     rax, rsp
0x18001f28b  mov     [rax+10h], rbx
0x18001f28f  mov     [rax+20h], rdi
0x18001f293  mov     [rax+18h], r8d
0x18001f297  push    rbp
0x18001f298  lea     rbp, [rax-5Fh]
0x18001f29c  sub     rsp, 0D0h
0x18001f2a3  mov     rax, cs:__security_cookie
0x18001f2aa  xor     rax, rsp
0x18001f2ad  mov     [rbp+57h+var_8], rax
0x18001f2b1  mov     [rbp+57h+var_98], rcx
0x18001f2b5  mov     [rbp+57h+var_A0], 0
0x18001f2bc  mov     [rbp+57h+var_9C], 0
0x18001f2c3  movups  xmm0, xmmword ptr cs:aICreateaiklock; "I_CreateAikLocking"
0x18001f2ca  movups  xmmword ptr [rbp+57h+var_20], xmm0
0x18001f2ce  mov     eax, dword ptr cs:aICreateaiklock+0Fh; "ing"
0x18001f2d4  mov     dword ptr [rbp+57h+var_20+0Fh], eax
0x18001f2d7  lea     rax, [rbp+57h+var_20]
0x18001f2db  mov     [rbp+57h+var_88], rax
0x18001f2df  lea     rax, [rbp+57h+var_9C]
0x18001f2e3  mov     [rbp+57h+var_80], rax
0x18001f2e7  lea     rax, [rbp+57h+var_A0]
0x18001f2eb  mov     [rbp+57h+var_78], rax
0x18001f2ef  lea     rcx, [rbp+57h+var_88]
0x18001f2f3  call    _lambda_a1409a84bbe01405fb965e20b27d848b___operator__
0x18001f2f8  mov     [rbp+57h+var_9C], 1
0x18001f2ff  lea     rax, [rbp+57h+var_88]
0x18001f303  mov     [rbp+57h+var_90], rax
0x18001f307  mov     rax, [rbp+57h+var_98]
0x18001f30b  test    rax, rax
0x18001f30e  jnz     short loc_18001F319
0x18001f310  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f315  mov     rax, [rbp+57h+var_98]
0x18001f319  mov     rbx, [rax]
0x18001f31c  add     rbx, 38h ; '8'
0x18001f320  mov     rcx, rbx; SRWLock
0x18001f323  call    cs:__imp_AcquireSRWLockExclusive
0x18001f329  mov     [rbp+57h+var_70], rbx
0x18001f32d  mov     eax, [rbp+57h+arg_10]
0x18001f330  test    eax, eax
0x18001f332  jnz     short loc_18001F34C
0x18001f334  mov     [rbp+57h+var_A0], eax
0x18001f337  test    rbx, rbx
0x18001f33a  jz      short loc_18001F345
0x18001f33c  mov     rcx, rbx; SRWLock
0x18001f33f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f345  xor     edi, edi
0x18001f347  jmp     loc_18001F3F7
0x18001f34c  dec     eax
0x18001f34e  cmp     eax, 1
0x18001f351  jbe     short loc_18001F3B3
0x18001f353  mov     edx, 2
0x18001f358  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f35d  mov     edi, 57h ; 'W'
0x18001f362  mov     [rbp+57h+var_A0], edi
0x18001f365  lea     rax, WPP_GLOBAL_Control
0x18001f36c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f373  cmp     rcx, rax
0x18001f376  jz      short loc_18001F3E8
0x18001f378  test    byte ptr [rcx+1Ch], 1
0x18001f37c  jz      short loc_18001F3E8
0x18001f37e  cmp     byte ptr [rcx+19h], 2
0x18001f382  jb      short loc_18001F3E8
0x18001f384  lea     edx, [rdi+12h]
0x18001f387  lea     rax, aInvalidAttesta; "Invalid attestation type"
0x18001f38e  mov     [rsp+0D0h+var_A8], rax
0x18001f393  mov     dword ptr [rsp+0D0h+var_B0], edi
0x18001f397  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f39e  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001f3a5  mov     rcx, [rcx+10h]
0x18001f3a9  call    WPP_SF_sDs
0x18001f3ae  mov     edi, [rbp+57h+var_A0]
0x18001f3b1  jmp     short loc_18001F3E8
0x18001f3b3  lea     rax, off_180038310
0x18001f3ba  mov     [rbp+57h+var_60], rax
0x18001f3be  lea     rax, [rbp+57h+var_98]
0x18001f3c2  mov     [rbp+57h+var_58], rax
0x18001f3c6  lea     rax, [rbp+57h+arg_10]
0x18001f3ca  mov     [rbp+57h+var_50], rax
0x18001f3ce  lea     rax, [rbp+57h+var_60]
0x18001f3d2  mov     [rbp+57h+var_28], rax
0x18001f3d6  lea     r8, [rbp+57h+var_60]
0x18001f3da  mov     rcx, [rbp+57h+var_98]
0x18001f3de  call    I_StoreAik
0x18001f3e3  mov     edi, eax
0x18001f3e5  mov     [rbp+57h+var_A0], eax
0x18001f3e8  test    rbx, rbx
0x18001f3eb  jz      short loc_18001F3F7
0x18001f3ed  mov     rcx, rbx; SRWLock
0x18001f3f0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f3f6  nop
0x18001f3f7  lea     rcx, [rbp+57h+var_90]
0x18001f3fb  call    WppTraceUnwinder__lambda_a1409a84bbe01405fb965e20b27d848b_______WppTraceUnwinder__lambda_a1409a84bbe01405fb965e20b27d848b____
0x18001f400  mov     eax, edi
0x18001f402  mov     rcx, [rbp+57h+var_8]
0x18001f406  xor     rcx, rsp; StackCookie
0x18001f409  call    __security_check_cookie
0x18001f40e  lea     r11, [rsp+0D0h+var_s0]
0x18001f416  mov     rbx, [r11+18h]
0x18001f41a  mov     rdi, [r11+28h]
0x18001f41e  mov     rsp, r11
0x18001f421  pop     rbp
0x18001f422  retn
```
