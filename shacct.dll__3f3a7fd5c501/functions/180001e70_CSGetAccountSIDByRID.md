# CSGetAccountSIDByRID

- ea: `0x180001e70`
- end: `0x1800020c8`
- name: `CSGetAccountSIDByRID`
- size: `600`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800126c0`
- `0x180012acc`
- `0x18001645c`

## callees

- `0x180001e70`
- `0x1800037e0`
- `0x180012f18`
- `0x180013534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002031`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180002019`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180002019`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001fef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001fc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000202b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001fc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000202b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001ffa`
- `SAMLIB!SamRidToSid` at `0x180001fe1`
- `SAMLIB!SamRidToSid` at `0x180001fe1`
- `SAMLIB!SamOpenDomain` at `0x180001f3c`
- `SAMLIB!SamOpenDomain` at `0x180001f3c`
- `SAMLIB!SamConnect` at `0x180001f1c`
- `SAMLIB!SamConnect` at `0x180001f1c`
- `SAMLIB!SamCloseHandle` at `0x180001f5a`
- `SAMLIB!SamCloseHandle` at `0x180002090`
- `SAMLIB!SamCloseHandle` at `0x180002099`
- `SAMLIB!SamCloseHandle` at `0x180001f5a`
- `SAMLIB!SamCloseHandle` at `0x180002090`
- `SAMLIB!SamCloseHandle` at `0x180002099`
- `SAMLIB!SamFreeMemory` at `0x18000204a`
- `SAMLIB!SamFreeMemory` at `0x18000204a`

## pseudocode

```c
__int64 __fastcall CSGetAccountSIDByRID(void *a1, unsigned int a2, _QWORD *a3)
{
  void *v5; // rdi
  LPVOID v7; // r12
  __int64 v8; // r14
  int v9; // eax
  int v10; // ebx
  int v11; // r15d
  int v12; // ebx
  int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  DWORD LengthSid; // r15d
  void *v18; // rax
  void *v19; // rdi
  signed int LastError; // eax
  __int64 v21; // [rsp+30h] [rbp-19h] BYREF
  _QWORD v22[4]; // [rsp+38h] [rbp-11h] BYREF
  __int128 v23; // [rsp+58h] [rbp+Fh]
  LPVOID pv; // [rsp+C0h] [rbp+77h] BYREF
  PSID pSid; // [rsp+C8h] [rbp+7Fh] BYREF

  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  v7 = 0;
  v8 = 0;
  *a3 = 0;
  pv = a1;
  if ( a1 )
  {
    v11 = 0;
  }
  else
  {
    v9 = CSGetAccountDomainSid(&pv);
    v5 = pv;
    v10 = v9;
    v11 = 1;
    if ( v9 < 0 )
    {
LABEL_18:
      CoTaskMemFree(v5);
      goto LABEL_19;
    }
  }
  v22[0] = 48;
  pv = 0;
  memset(&v22[1], 0, 24);
  v23 = 0;
  v12 = SamConnect(0, &pv, 131121, v22);
  if ( v12 < 0 )
  {
    v10 = v12 | 0x10000000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 35;
      goto LABEL_16;
    }
  }
  else
  {
    v21 = 0;
    v13 = SamOpenDomain(pv, 131973, v5, &v21);
    if ( v13 >= 0 )
    {
      v8 = v21;
      v7 = pv;
      v10 = 0;
      goto LABEL_17;
    }
    SamCloseHandle(pv);
    v10 = v13 | 0x10000000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 34;
LABEL_16:
      WPP_SF_d(v14[2], v15, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v10);
    }
  }
LABEL_17:
  if ( v11 )
    goto LABEL_18;
LABEL_19:
  if ( v10 >= 0 )
  {
    pSid = 0;
    v16 = SamRidToSid(v8, a2, &pSid);
    if ( v16 < 0 )
    {
      v10 = v16 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, a2, v10);
    }
    else
    {
      LengthSid = GetLengthSid(pSid);
      v18 = CoTaskMemAlloc(LengthSid);
      v19 = v18;
      if ( v18 )
      {
        if ( CopySid(LengthSid, v18, pSid) )
        {
          *a3 = v19;
        }
        else
        {
          CoTaskMemFree(v19);
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v10 = -2147024882;
      }
      SamFreeMemory(pSid);
    }
    SamCloseHandle(v8);
    SamCloseHandle(v7);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180001e70  push    rbp
0x180001e72  push    rsi
0x180001e73  push    rdi
0x180001e74  push    r13
0x180001e76  lea     rbp, [rsp-3Fh]
0x180001e7b  sub     rsp, 88h
0x180001e82  mov     rsi, r8
0x180001e85  mov     r13d, edx
0x180001e88  mov     rdi, rcx
0x180001e8b  test    r8, r8
0x180001e8e  jnz     short loc_180001E9A
0x180001e90  mov     eax, 80004003h
0x180001e95  jmp     loc_1800020BB
0x180001e9a  xor     eax, eax
0x180001e9c  mov     [rsp+0A0h+arg_0], rbx
0x180001ea4  mov     [rsp+0A0h+var_20], r12
0x180001eac  mov     r12d, eax
0x180001eaf  mov     [rsp+0A0h+var_28], r14
0x180001eb4  mov     r14d, eax
0x180001eb7  mov     [rsp+0A0h+var_30], r15
0x180001ebc  mov     [r8], rax
0x180001ebf  mov     [rbp+57h+pv], rcx
0x180001ec3  test    rcx, rcx
0x180001ec6  jnz     short loc_180001EE9
0x180001ec8  lea     rcx, [rbp+57h+pv]
0x180001ecc  call    CSGetAccountDomainSid
0x180001ed1  mov     rdi, [rbp+57h+pv]
0x180001ed5  mov     ebx, eax
0x180001ed7  mov     r15d, 1
0x180001edd  test    eax, eax
0x180001edf  js      loc_180001FC0
0x180001ee5  xor     eax, eax
0x180001ee7  jmp     short loc_180001EEC
0x180001ee9  mov     r15d, eax
0x180001eec  xorps   xmm0, xmm0
0x180001eef  mov     [rbp+57h+var_68], 30h ; '0'
0x180001ef7  lea     r9, [rbp+57h+var_68]
0x180001efb  mov     [rbp+57h+var_50], r12
0x180001eff  mov     r8d, 20031h
0x180001f05  mov     [rbp+57h+pv], rax
0x180001f09  lea     rdx, [rbp+57h+pv]
0x180001f0d  mov     [rbp+57h+var_60], rax
0x180001f11  xor     ecx, ecx
0x180001f13  mov     [rbp+57h+var_58], rax
0x180001f17  movdqu  [rbp+57h+var_48], xmm0
0x180001f1c  call    cs:__imp_SamConnect
0x180001f22  mov     ebx, eax
0x180001f24  test    eax, eax
0x180001f26  js      short loc_180001F84
0x180001f28  mov     rcx, [rbp+57h+pv]
0x180001f2c  lea     r9, [rbp+57h+var_70]
0x180001f30  mov     r8, rdi
0x180001f33  mov     [rbp+57h+var_70], r12
0x180001f37  mov     edx, 20385h
0x180001f3c  call    cs:__imp_SamOpenDomain
0x180001f42  mov     ebx, eax
0x180001f44  test    eax, eax
0x180001f46  js      short loc_180001F56
0x180001f48  mov     r14, [rbp+57h+var_70]
0x180001f4c  xor     eax, eax
0x180001f4e  mov     r12, [rbp+57h+pv]
0x180001f52  mov     ebx, eax
0x180001f54  jmp     short loc_180001FBB
0x180001f56  mov     rcx, [rbp+57h+pv]
0x180001f5a  call    cs:__imp_SamCloseHandle
0x180001f60  bts     ebx, 1Ch
0x180001f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f6b  lea     rax, WPP_GLOBAL_Control
0x180001f72  cmp     rcx, rax
0x180001f75  jz      short loc_180001FB9
0x180001f77  test    byte ptr [rcx+1Ch], 2
0x180001f7b  jz      short loc_180001FB9
0x180001f7d  mov     edx, 22h ; '"'
0x180001f82  jmp     short loc_180001FA6
0x180001f84  bts     ebx, 1Ch
0x180001f88  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f8f  lea     rax, WPP_GLOBAL_Control
0x180001f96  cmp     rcx, rax
0x180001f99  jz      short loc_180001FB9
0x180001f9b  test    byte ptr [rcx+1Ch], 2
0x180001f9f  jz      short loc_180001FB9
0x180001fa1  mov     edx, 23h ; '#'
0x180001fa6  mov     rcx, [rcx+10h]
0x180001faa  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180001fb1  mov     r9d, ebx
0x180001fb4  call    WPP_SF_d
0x180001fb9  xor     eax, eax
0x180001fbb  test    r15d, r15d
0x180001fbe  jz      short loc_180001FCB
0x180001fc0  mov     rcx, rdi; pv
0x180001fc3  call    cs:__imp_CoTaskMemFree
0x180001fc9  xor     eax, eax
0x180001fcb  test    ebx, ebx
0x180001fcd  js      loc_18000209F
0x180001fd3  lea     r8, [rbp+57h+pSid]
0x180001fd7  mov     [rbp+57h+pSid], rax
0x180001fdb  mov     edx, r13d
0x180001fde  mov     rcx, r14
0x180001fe1  call    cs:__imp_SamRidToSid
0x180001fe7  test    eax, eax
0x180001fe9  js      short loc_180002052
0x180001feb  mov     rcx, [rbp+57h+pSid]; pSid
0x180001fef  call    cs:__imp_GetLengthSid
0x180001ff5  mov     ecx, eax; cb
0x180001ff7  mov     r15d, eax
0x180001ffa  call    cs:__imp_CoTaskMemAlloc
0x180002000  mov     rdi, rax
0x180002003  test    rax, rax
0x180002006  jnz     short loc_18000200F
0x180002008  mov     ebx, 8007000Eh
0x18000200d  jmp     short loc_180002046
0x18000200f  mov     r8, [rbp+57h+pSid]; pSourceSid
0x180002013  mov     rdx, rdi; pDestinationSid
0x180002016  mov     ecx, r15d; nDestinationSidLength
0x180002019  call    cs:__imp_CopySid
0x18000201f  test    eax, eax
0x180002021  jz      short loc_180002028
0x180002023  mov     [rsi], rdi
0x180002026  jmp     short loc_180002046
0x180002028  mov     rcx, rdi; pv
0x18000202b  call    cs:__imp_CoTaskMemFree
0x180002031  call    cs:__imp_GetLastError
0x180002037  mov     ebx, eax
0x180002039  test    eax, eax
0x18000203b  jle     short loc_180002046
0x18000203d  movzx   ebx, ax
0x180002040  or      ebx, 80070000h
0x180002046  mov     rcx, [rbp+57h+pSid]
0x18000204a  call    cs:__imp_SamFreeMemory
0x180002050  jmp     short loc_18000208D
0x180002052  mov     ebx, eax
0x180002054  bts     ebx, 1Ch
0x180002058  mov     rcx, cs:WPP_GLOBAL_Control
0x18000205f  lea     rax, WPP_GLOBAL_Control
0x180002066  cmp     rcx, rax
0x180002069  jz      short loc_18000208D
0x18000206b  test    byte ptr [rcx+1Ch], 2
0x18000206f  jz      short loc_18000208D
0x180002071  mov     rcx, [rcx+10h]
0x180002075  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000207c  mov     edx, 44h ; 'D'
0x180002081  mov     [rsp+0A0h+var_80], ebx
0x180002085  mov     r9d, r13d
0x180002088  call    WPP_SF_dD
0x18000208d  mov     rcx, r14
0x180002090  call    cs:__imp_SamCloseHandle
0x180002096  mov     rcx, r12
0x180002099  call    cs:__imp_SamCloseHandle
0x18000209f  mov     r14, [rsp+0A0h+var_28]
0x1800020a4  mov     eax, ebx
0x1800020a6  mov     rbx, [rsp+0A0h+arg_0]
0x1800020ae  mov     r12, [rsp+0A0h+var_20]
0x1800020b6  mov     r15, [rsp+0A0h+var_30]
0x1800020bb  add     rsp, 88h
0x1800020c2  pop     r13
0x1800020c4  pop     rdi
0x1800020c5  pop     rsi
0x1800020c6  pop     rbp
0x1800020c7  retn
```
