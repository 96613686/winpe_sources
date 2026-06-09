# BuildKeyNameString(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180012a94`
- end: `0x180012ee0`
- name: `?BuildKeyNameString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `1100`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180002e10`
- `0x1800086b0`
- `0x18000b91c`
- `0x18000ba94`
- `0x1800116a0`
- `0x180012a94`
- `0x180013838`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180012ac6`
- `wbemcomn!GetMemLogObject` at `0x180012b35`
- `wbemcomn!GetMemLogObject` at `0x180012ba8`
- `wbemcomn!GetMemLogObject` at `0x180012c36`
- `wbemcomn!GetMemLogObject` at `0x180012cae`
- `wbemcomn!GetMemLogObject` at `0x180012d0b`
- `wbemcomn!GetMemLogObject` at `0x180012d77`
- `wbemcomn!GetMemLogObject` at `0x180012dd6`
- `wbemcomn!GetMemLogObject` at `0x180012e31`
- `wbemcomn!GetMemLogObject` at `0x180012e78`
- `wbemcomn!GetMemLogObject` at `0x180012ac6`
- `wbemcomn!GetMemLogObject` at `0x180012b35`
- `wbemcomn!GetMemLogObject` at `0x180012ba8`
- `wbemcomn!GetMemLogObject` at `0x180012c36`
- `wbemcomn!GetMemLogObject` at `0x180012cae`
- `wbemcomn!GetMemLogObject` at `0x180012d0b`
- `wbemcomn!GetMemLogObject` at `0x180012d77`
- `wbemcomn!GetMemLogObject` at `0x180012dd6`
- `wbemcomn!GetMemLogObject` at `0x180012e31`
- `wbemcomn!GetMemLogObject` at `0x180012e78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012ad6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012b40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012bb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012c41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012cb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012d16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012d82`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012de1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012e3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012e88`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012ad6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012b40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012bb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012c41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012cb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012d16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012d82`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012de1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012e3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012e88`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180012b99`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180012b99`

## pseudocode

```c
__int64 __fastcall BuildKeyNameString(HKEY a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v7; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  CMemoryLog *v12; // rax
  unsigned __int64 v13; // rbx
  __int64 v14; // rdx
  CMemoryLog *v15; // rax
  int v16; // edi
  CMemoryLog *v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  __int64 v27; // r8
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  CMemoryLog *v31; // rax
  _BYTE v32[24]; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp+30h] BYREF

  v34 = 0;
  *a3 = 0;
  if ( !a2 )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v7;
    }
    v10 = 11;
    v11 = 2147749896LL;
    goto LABEL_6;
  }
  v7 = StringCchLengthW(a2, 0x100u, &v34);
  if ( (v7 & 0x80000000) != 0 )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v7);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v7;
    }
    v10 = 12;
    v11 = v7;
    goto LABEL_6;
  }
  v13 = v34 + 14;
  v33 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v34 + 14, 2u));
  if ( v33 )
  {
    MakeGuard<void (*)(unsigned short *),RefHolder<unsigned short *>>(v32, v14, &v33);
    *v33 = 0;
    if ( a1 == HKEY_CLASSES_ROOT )
    {
      v16 = StringCchCopyW(v33, v13, L"CLASSES_ROOT");
      if ( v16 < 0 )
      {
        v17 = GetMemLogObject();
        CMemoryLog::Write(v17, v16);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v20 = 14;
LABEL_23:
        WPP_SF_D(v19[2], v20, v18, (unsigned int)v16);
LABEL_24:
        ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v32);
        return (unsigned int)v16;
      }
    }
    else if ( a1 == HKEY_CURRENT_USER )
    {
      v16 = StringCchCopyW(v33, v13, L"CURRENT_USER");
      if ( v16 < 0 )
      {
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, v16);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v20 = 15;
        goto LABEL_23;
      }
    }
    else if ( a1 == HKEY_LOCAL_MACHINE )
    {
      v16 = StringCchCopyW(v33, v13, L"MACHINE");
      if ( v16 < 0 )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, v16);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v20 = 16;
        goto LABEL_23;
      }
    }
    else
    {
      if ( a1 != HKEY_USERS )
      {
        v31 = GetMemLogObject();
        v7 = -2147217400;
        CMemoryLog::Write(v31, -2147217400);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 18;
        v30 = 2147749896LL;
        goto LABEL_58;
      }
      v16 = StringCchCopyW(v33, v13, L"USERS");
      if ( v16 < 0 )
      {
        v24 = GetMemLogObject();
        CMemoryLog::Write(v24, v16);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v20 = 17;
        goto LABEL_23;
      }
    }
    v16 = StringCchCatW(v33, v13, L"\\");
    if ( v16 < 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, v16);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v20 = 19;
      goto LABEL_23;
    }
    v7 = StringCchCatW(v33, v13, a2);
    if ( (v7 & 0x80000000) == 0 )
    {
      v32[0] = 1;
      *a3 = v33;
LABEL_59:
      ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v32);
      return v7;
    }
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, v7);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v29 = 20;
    v30 = v7;
LABEL_58:
    WPP_SF_D(v28[2], v29, v27, v30);
    goto LABEL_59;
  }
  v15 = GetMemLogObject();
  v7 = -2147217402;
  CMemoryLog::Write(v15, -2147217402);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return v7;
  }
  v10 = 13;
  v11 = 2147749894LL;
LABEL_6:
  WPP_SF_D(v9[2], v10, v8, v11);
  return v7;
}

```

## disassembly

```asm
0x180012a94  mov     [rsp-18h+arg_0], rbx
0x180012a99  mov     [rsp-18h+arg_18], rsi
0x180012a9e  push    rbp
0x180012a9f  push    rdi
0x180012aa0  push    r14
0x180012aa2  mov     rbp, rsp
0x180012aa5  sub     rsp, 40h
0x180012aa9  mov     r14, r8
0x180012aac  mov     rsi, rdx
0x180012aaf  mov     rdi, rcx
0x180012ab2  mov     [rbp+arg_10], 0
0x180012aba  mov     qword ptr [r8], 0
0x180012ac1  test    rdx, rdx
0x180012ac4  jnz     short loc_180012B1E
0x180012ac6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012acc  mov     ebx, 80041008h
0x180012ad1  mov     edx, ebx
0x180012ad3  mov     rcx, rax
0x180012ad6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012adc  lea     rax, WPP_GLOBAL_Control
0x180012ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012aea  cmp     rcx, rax
0x180012aed  jz      loc_180012ECB
0x180012af3  test    byte ptr [rcx+1Ch], 4
0x180012af7  jz      loc_180012ECB
0x180012afd  cmp     byte ptr [rcx+19h], 2
0x180012b01  jb      loc_180012ECB
0x180012b07  lea     edx, [rsi+0Bh]
0x180012b0a  mov     r9d, 80041008h
0x180012b10  mov     rcx, [rcx+10h]
0x180012b14  call    WPP_SF_D
0x180012b19  jmp     loc_180012ECB
0x180012b1e  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x180012b22  mov     edx, 100h; unsigned __int64
0x180012b27  mov     rcx, rsi; unsigned __int16 *
0x180012b2a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180012b2f  mov     ebx, eax
0x180012b31  test    eax, eax
0x180012b33  jns     short loc_180012B7B
0x180012b35  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012b3b  mov     edx, ebx
0x180012b3d  mov     rcx, rax
0x180012b40  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012b46  lea     rax, WPP_GLOBAL_Control
0x180012b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b54  cmp     rcx, rax
0x180012b57  jz      loc_180012ECB
0x180012b5d  test    byte ptr [rcx+1Ch], 4
0x180012b61  jz      loc_180012ECB
0x180012b67  cmp     byte ptr [rcx+19h], 2
0x180012b6b  jb      loc_180012ECB
0x180012b71  mov     edx, 0Ch
0x180012b76  mov     r9d, ebx
0x180012b79  jmp     short loc_180012B10
0x180012b7b  mov     rbx, [rbp+arg_10]
0x180012b7f  add     rbx, 0Eh
0x180012b83  mov     eax, 2
0x180012b88  mul     rbx
0x180012b8b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012b92  cmovb   rax, rcx
0x180012b96  mov     rcx, rax
0x180012b99  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180012b9f  mov     [rbp+arg_8], rax
0x180012ba3  test    rax, rax
0x180012ba6  jnz     short loc_180012BF9
0x180012ba8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012bae  mov     ebx, 80041006h
0x180012bb3  mov     edx, ebx
0x180012bb5  mov     rcx, rax
0x180012bb8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012bbe  lea     rax, WPP_GLOBAL_Control
0x180012bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bcc  cmp     rcx, rax
0x180012bcf  jz      loc_180012ECB
0x180012bd5  test    byte ptr [rcx+1Ch], 4
0x180012bd9  jz      loc_180012ECB
0x180012bdf  cmp     byte ptr [rcx+19h], 2
0x180012be3  jb      loc_180012ECB
0x180012be9  mov     edx, 0Dh
0x180012bee  mov     r9d, 80041006h
0x180012bf4  jmp     loc_180012B10
0x180012bf9  lea     r8, [rbp+arg_8]
0x180012bfd  lea     rcx, [rbp+var_18]
0x180012c01  call    ??$MakeGuard@P6AXPEAG@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@P6AXPEAG@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(ushort *),RefHolder<ushort *>>(void (*)(ushort *),RefHolder<ushort *>)
0x180012c06  nop
0x180012c07  xor     ecx, ecx
0x180012c09  mov     rax, [rbp+arg_8]
0x180012c0d  mov     [rax], cx
0x180012c10  cmp     rdi, 0FFFFFFFF80000000h
0x180012c17  jnz     short loc_180012C88
0x180012c19  lea     r8, aClassesRoot; "CLASSES_ROOT"
0x180012c20  mov     rdx, rbx; unsigned __int64
0x180012c23  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180012c27  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012c2c  mov     edi, eax
0x180012c2e  test    eax, eax
0x180012c30  jns     loc_180012DBD
0x180012c36  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012c3c  mov     edx, edi
0x180012c3e  mov     rcx, rax
0x180012c41  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012c47  lea     rax, WPP_GLOBAL_Control
0x180012c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c55  cmp     rcx, rax
0x180012c58  jz      short loc_180012C78
0x180012c5a  test    byte ptr [rcx+1Ch], 4
0x180012c5e  jz      short loc_180012C78
0x180012c60  cmp     byte ptr [rcx+19h], 2
0x180012c64  jb      short loc_180012C78
0x180012c66  mov     edx, 0Eh
0x180012c6b  mov     r9d, edi
0x180012c6e  mov     rcx, [rcx+10h]
0x180012c72  call    WPP_SF_D
0x180012c77  nop
0x180012c78  lea     rcx, [rbp+var_18]
0x180012c7c  call    ??1?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>::~ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>(void)
0x180012c81  mov     eax, edi
0x180012c83  jmp     loc_180012ECD
0x180012c88  cmp     rdi, 0FFFFFFFF80000001h
0x180012c8f  jnz     short loc_180012CE5
0x180012c91  lea     r8, aCurrentUser; "CURRENT_USER"
0x180012c98  mov     rdx, rbx; unsigned __int64
0x180012c9b  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180012c9f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012ca4  mov     edi, eax
0x180012ca6  test    eax, eax
0x180012ca8  jns     loc_180012DBD
0x180012cae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012cb4  mov     edx, edi
0x180012cb6  mov     rcx, rax
0x180012cb9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012cbf  lea     rax, WPP_GLOBAL_Control
0x180012cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ccd  cmp     rcx, rax
0x180012cd0  jz      short loc_180012C78
0x180012cd2  test    byte ptr [rcx+1Ch], 4
0x180012cd6  jz      short loc_180012C78
0x180012cd8  cmp     byte ptr [rcx+19h], 2
0x180012cdc  jb      short loc_180012C78
0x180012cde  mov     edx, 0Fh
0x180012ce3  jmp     short loc_180012C6B
0x180012ce5  cmp     rdi, 0FFFFFFFF80000002h
0x180012cec  jnz     short loc_180012D51
0x180012cee  lea     r8, aMachine; "MACHINE"
0x180012cf5  mov     rdx, rbx; unsigned __int64
0x180012cf8  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180012cfc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012d01  mov     edi, eax
0x180012d03  test    eax, eax
0x180012d05  jns     loc_180012DBD
0x180012d0b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012d11  mov     edx, edi
0x180012d13  mov     rcx, rax
0x180012d16  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012d1c  lea     rax, WPP_GLOBAL_Control
0x180012d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d2a  cmp     rcx, rax
0x180012d2d  jz      loc_180012C78
0x180012d33  test    byte ptr [rcx+1Ch], 4
0x180012d37  jz      loc_180012C78
0x180012d3d  cmp     byte ptr [rcx+19h], 2
0x180012d41  jb      loc_180012C78
0x180012d47  mov     edx, 10h
0x180012d4c  jmp     loc_180012C6B
0x180012d51  cmp     rdi, 0FFFFFFFF80000003h
0x180012d58  jnz     loc_180012E78
0x180012d5e  lea     r8, aUsers; "USERS"
0x180012d65  mov     rdx, rbx; unsigned __int64
0x180012d68  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180012d6c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012d71  mov     edi, eax
0x180012d73  test    eax, eax
0x180012d75  jns     short loc_180012DBD
0x180012d77  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012d7d  mov     edx, edi
0x180012d7f  mov     rcx, rax
0x180012d82  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012d88  lea     rax, WPP_GLOBAL_Control
0x180012d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d96  cmp     rcx, rax
0x180012d99  jz      loc_180012C78
0x180012d9f  test    byte ptr [rcx+1Ch], 4
0x180012da3  jz      loc_180012C78
0x180012da9  cmp     byte ptr [rcx+19h], 2
0x180012dad  jb      loc_180012C78
0x180012db3  mov     edx, 11h
0x180012db8  jmp     loc_180012C6B
0x180012dbd  lea     r8, asc_180019B2C; "\\"
0x180012dc4  mov     rdx, rbx; unsigned __int64
0x180012dc7  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180012dcb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012dd0  mov     edi, eax
0x180012dd2  test    eax, eax
0x180012dd4  jns     short loc_180012E1C
0x180012dd6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012ddc  mov     edx, edi
0x180012dde  mov     rcx, rax
0x180012de1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012de7  lea     rax, WPP_GLOBAL_Control
0x180012dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180012df5  cmp     rcx, rax
0x180012df8  jz      loc_180012C78
0x180012dfe  test    byte ptr [rcx+1Ch], 4
0x180012e02  jz      loc_180012C78
0x180012e08  cmp     byte ptr [rcx+19h], 2
0x180012e0c  jb      loc_180012C78
0x180012e12  mov     edx, 13h
0x180012e17  jmp     loc_180012C6B
0x180012e1c  mov     r8, rsi; unsigned __int16 *
0x180012e1f  mov     rdx, rbx; unsigned __int64
0x180012e22  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180012e26  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012e2b  mov     ebx, eax
0x180012e2d  test    eax, eax
0x180012e2f  jns     short loc_180012E6B
0x180012e31  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012e37  mov     edx, ebx
0x180012e39  mov     rcx, rax
0x180012e3c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012e42  lea     rax, WPP_GLOBAL_Control
0x180012e49  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e50  cmp     rcx, rax
0x180012e53  jz      short loc_180012EC2
0x180012e55  test    byte ptr [rcx+1Ch], 4
0x180012e59  jz      short loc_180012EC2
0x180012e5b  cmp     byte ptr [rcx+19h], 2
0x180012e5f  jb      short loc_180012EC2
0x180012e61  mov     edx, 14h
0x180012e66  mov     r9d, ebx
0x180012e69  jmp     short loc_180012EB8
0x180012e6b  mov     [rbp+var_18], 1
0x180012e6f  mov     rax, [rbp+arg_8]
0x180012e73  mov     [r14], rax
0x180012e76  jmp     short loc_180012EC2
0x180012e78  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180012e7e  mov     ebx, 80041008h
0x180012e83  mov     edx, ebx
0x180012e85  mov     rcx, rax
0x180012e88  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180012e8e  lea     rax, WPP_GLOBAL_Control
0x180012e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e9c  cmp     rcx, rax
0x180012e9f  jz      short loc_180012EC2
0x180012ea1  test    byte ptr [rcx+1Ch], 4
0x180012ea5  jz      short loc_180012EC2
0x180012ea7  cmp     byte ptr [rcx+19h], 2
0x180012eab  jb      short loc_180012EC2
0x180012ead  mov     edx, 12h
0x180012eb2  mov     r9d, 80041008h
0x180012eb8  mov     rcx, [rcx+10h]
0x180012ebc  call    WPP_SF_D
0x180012ec1  nop
0x180012ec2  lea     rcx, [rbp+var_18]
0x180012ec6  call    ??1?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>::~ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>(void)
0x180012ecb  mov     eax, ebx
0x180012ecd  mov     rbx, [rsp+40h+arg_0]
0x180012ed2  mov     rsi, [rsp+40h+arg_18]
0x180012ed7  add     rsp, 40h
0x180012edb  pop     r14
0x180012edd  pop     rdi
0x180012ede  pop     rbp
0x180012edf  retn
```
