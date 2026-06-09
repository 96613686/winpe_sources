# CIdentitySecurity::CIdentitySecurity(bool)

- ea: `0x180023160`
- end: `0x1800234f4`
- name: `??0CIdentitySecurity@@QEAA@_N@Z`
- size: `916`
- prototype: `CIdentitySecurity *__fastcall(CIdentitySecurity *this, char)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ab30`
- `0x180014120`
- `0x18001c4fc`
- `0x18001cb10`
- `0x18001cd60`
- `0x18001d19c`
- `0x180023160`
- `0x18002ca74`
- `0x18002ee7c`
- `0x1800307ec`
- `0x1800442d3`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023210`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023299`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002324f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002324f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023265`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023265`
- `ntdll!RtlLengthSid` at `0x1800231f0`
- `ntdll!RtlLengthSid` at `0x1800231f0`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800232fa`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800232fa`

## string_xrefs

- `0x180023257`: `CopySid`
- `0x1800233e3`: `COMException()`
- `0x1800234bd`: `ComException()`

## pseudocode

```c
CIdentitySecurity *__fastcall CIdentitySecurity::CIdentitySecurity(CIdentitySecurity *this, char a2)
{
  void *v3; // r14
  ULONG v4; // eax
  size_t v5; // r15
  void *v6; // rax
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax
  void *v9; // rdi
  int SidFromThreadOrProcess; // r15d
  void *v11; // rbx
  signed int v13; // eax
  char v14; // [rsp+20h] [rbp-39h] BYREF
  void *ppInterface; // [rsp+28h] [rbp-31h] BYREF
  void *v16; // [rsp+30h] [rbp-29h] BYREF
  DWORD LastError; // [rsp+38h] [rbp-21h]
  int v18; // [rsp+3Ch] [rbp-1Dh]
  void **pExceptionObject; // [rsp+40h] [rbp-19h] BYREF
  signed int v20; // [rsp+48h] [rbp-11h]
  CIdentitySecurity *v21; // [rsp+50h] [rbp-9h]
  void *v22; // [rsp+58h] [rbp-1h]
  _DWORD Sid[4]; // [rsp+60h] [rbp+7h] BYREF

  v21 = this;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 6;
  *((_DWORD *)this + 3) = 8;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 6;
  *((_DWORD *)this + 7) = 8;
  *((_BYTE *)this + 32) = a2;
  Sid[0] = 257;
  Sid[1] = 83886080;
  Sid[2] = 18;
  v3 = 0;
  v16 = 0;
  LastError = 0;
  v18 = 8;
  if ( !(unsigned int)DLIsValidSid(Sid) )
  {
    LastError = 13;
    goto LABEL_13;
  }
  v4 = RtlLengthSid(Sid);
  v5 = v4;
  if ( !hHeap )
  {
    v16 = 0;
LABEL_6:
    LastError = 14;
    goto LABEL_13;
  }
  v6 = HeapAlloc(hHeap, 0, v4);
  v3 = v6;
  v16 = v6;
  if ( !v6 )
    goto LABEL_6;
  memset_0(v6, 0, v5);
  ProcAddress = (FARPROC)qword_180070338;
  if ( qword_180070338 )
    goto LABEL_11;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "CopySid");
    qword_180070338 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_12;
LABEL_11:
    if ( ((unsigned int (__fastcall *)(_QWORD, void *, _DWORD *))ProcAddress)((unsigned int)v5, v3, Sid) )
      goto LABEL_13;
    goto LABEL_12;
  }
  SetLastError(SecurityDll);
LABEL_12:
  CMUILocale::_Free(v3);
  v3 = 0;
  v16 = 0;
  LastError = GetLastError();
  v18 = 8;
LABEL_13:
  CNtSid::operator=((char *)this + 16, &v16);
  if ( *((_DWORD *)this + 6) )
  {
    if ( *((_DWORD *)this + 6) != 14 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids,
          "COMException()");
      }
      v13 = *((_DWORD *)this + 6);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      pExceptionObject = &ComException::`vftable';
      v20 = v13;
      throw (ComException *)&pExceptionObject;
    }
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&v14;
  }
  if ( NtCurrentTeb()->IsImpersonating || (ppInterface = 0, CoGetCallContext(&IID_IServerSecurity, &ppInterface)) )
  {
    SidFromThreadOrProcess = CIdentitySecurity::GetSidFromThreadOrProcess(this, this);
  }
  else
  {
    v9 = ppInterface;
    v22 = ppInterface;
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
    {
      SidFromThreadOrProcess = CIdentitySecurity::GetSidFromThreadOrProcess(this, this);
    }
    else
    {
      SidFromThreadOrProcess = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      if ( SidFromThreadOrProcess < 0 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
        goto LABEL_39;
      }
      v11 = ppInterface;
      pExceptionObject = (void **)ppInterface;
      SidFromThreadOrProcess = CIdentitySecurity::GetSidFromThreadOrProcess(this, this);
       IServerSecurity::`vcall'{40,{flat}}(v11);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( SidFromThreadOrProcess < 0 )
  {
LABEL_39:
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids,
        "ComException()");
    }
    pExceptionObject = &ComException::`vftable';
    v20 = SidFromThreadOrProcess;
    throw (ComException *)&pExceptionObject;
  }
  CMUILocale::_Free(v3);
  return this;
}

```

## disassembly

```asm
0x180023160  push    rbp
0x180023162  push    rbx
0x180023163  push    rsi
0x180023164  push    rdi
0x180023165  push    r14
0x180023167  push    r15
0x180023169  lea     rbp, [rsp-2Fh]
0x18002316e  sub     rsp, 88h
0x180023175  mov     rax, cs:__security_cookie
0x18002317c  xor     rax, rsp
0x18002317f  mov     [rbp+57h+var_40], rax
0x180023183  mov     rsi, rcx
0x180023186  mov     [rbp+57h+var_60], rcx
0x18002318a  mov     qword ptr [rcx], 0
0x180023191  mov     eax, 6
0x180023196  mov     [rcx+8], eax
0x180023199  lea     ecx, [rax+2]
0x18002319c  mov     [rsi+0Ch], ecx
0x18002319f  mov     qword ptr [rsi+10h], 0
0x1800231a7  mov     [rsi+18h], eax
0x1800231aa  mov     [rsi+1Ch], ecx
0x1800231ad  mov     [rsi+20h], dl
0x1800231b0  mov     [rbp+57h+Sid], 101h
0x1800231b7  mov     [rbp+57h+var_4C], 5000000h
0x1800231be  mov     [rbp+57h+var_48], 12h
0x1800231c5  xor     r14d, r14d
0x1800231c8  mov     [rbp+57h+var_80], r14
0x1800231cc  mov     [rbp+57h+var_78], r14d
0x1800231d0  mov     [rbp+57h+var_74], ecx
0x1800231d3  lea     rcx, [rbp+57h+Sid]; void *
0x1800231d7  call    ?DLIsValidSid@@YAHPEAX@Z; DLIsValidSid(void *)
0x1800231dc  test    eax, eax
0x1800231de  jnz     short loc_1800231EC
0x1800231e0  mov     [rbp+57h+var_78], 0Dh
0x1800231e7  jmp     loc_1800232A9
0x1800231ec  lea     rcx, [rbp+57h+Sid]; Sid
0x1800231f0  call    cs:__imp_RtlLengthSid
0x1800231f6  mov     r15d, eax
0x1800231f9  mov     rcx, cs:hHeap; hHeap
0x180023200  test    rcx, rcx
0x180023203  jnz     short loc_18002320B
0x180023205  mov     [rbp+57h+var_80], r14
0x180023209  jmp     short loc_180023222
0x18002320b  mov     r8, r15; dwBytes
0x18002320e  xor     edx, edx; dwFlags
0x180023210  call    cs:__imp_HeapAlloc
0x180023216  mov     r14, rax
0x180023219  mov     [rbp+57h+var_80], rax
0x18002321d  test    rax, rax
0x180023220  jnz     short loc_18002322B
0x180023222  mov     [rbp+57h+var_78], 0Eh
0x180023229  jmp     short loc_1800232A9
0x18002322b  mov     r8, r15; Size
0x18002322e  xor     edx, edx; Val
0x180023230  mov     rcx, r14; void *
0x180023233  call    memset_0
0x180023238  mov     rax, cs:qword_180070338
0x18002323f  test    rax, rax
0x180023242  jnz     short loc_180023277
0x180023244  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180023249  test    eax, eax
0x18002324b  jz      short loc_180023257
0x18002324d  mov     ecx, eax; dwErrCode
0x18002324f  call    cs:__imp_SetLastError
0x180023255  jmp     short loc_18002328A
0x180023257  lea     rdx, aCopysid; "CopySid"
0x18002325e  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180023265  call    cs:__imp_GetProcAddress
0x18002326b  mov     cs:qword_180070338, rax
0x180023272  test    rax, rax
0x180023275  jz      short loc_18002328A
0x180023277  lea     r8, [rbp+57h+Sid]
0x18002327b  mov     rdx, r14
0x18002327e  mov     ecx, r15d
0x180023281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023286  test    eax, eax
0x180023288  jnz     short loc_1800232A9
0x18002328a  mov     rcx, r14; void *
0x18002328d  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180023292  xor     r14d, r14d
0x180023295  mov     [rbp+57h+var_80], r14
0x180023299  call    cs:__imp_GetLastError
0x18002329f  mov     [rbp+57h+var_78], eax
0x1800232a2  mov     [rbp+57h+var_74], 8
0x1800232a9  lea     rdx, [rbp+57h+var_80]
0x1800232ad  lea     rcx, [rsi+10h]
0x1800232b1  call    ??4CNtSid@@QEAAAEAV0@AEBV0@@Z; CNtSid::operator=(CNtSid const &)
0x1800232b6  cmp     dword ptr [rsi+18h], 0
0x1800232ba  jz      short loc_1800232D7
0x1800232bc  mov     edx, 0FFFFFFFEh; int
0x1800232c1  lea     rcx, qword_18006A9C0; this
0x1800232c8  cmp     dword ptr [rsi+18h], 0Eh
0x1800232cc  jz      loc_180023428
0x1800232d2  jmp     loc_1800233B9
0x1800232d7  mov     eax, gs:179Ch
0x1800232df  test    eax, eax
0x1800232e1  jnz     loc_18002337A
0x1800232e7  mov     [rbp+57h+ppInterface], 0
0x1800232ef  lea     rdx, [rbp+57h+ppInterface]; ppInterface
0x1800232f3  lea     rcx, IID_IServerSecurity; riid
0x1800232fa  call    cs:__imp_CoGetCallContext
0x180023300  test    eax, eax
0x180023302  jnz     short loc_18002337A
0x180023304  mov     rdi, [rbp+57h+ppInterface]
0x180023308  mov     [rbp+57h+var_58], rdi
0x18002330c  mov     rcx, [rbp+57h+ppInterface]
0x180023310  mov     rax, [rcx]
0x180023313  mov     rax, [rax+30h]
0x180023317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002331c  test    eax, eax
0x18002331e  jz      short loc_18002333F
0x180023320  mov     rdx, rsi; struct CNtSid *
0x180023323  mov     rcx, rsi; this
0x180023326  call    ?GetSidFromThreadOrProcess@CIdentitySecurity@@AEAAJAEAVCNtSid@@@Z; CIdentitySecurity::GetSidFromThreadOrProcess(CNtSid &)
0x18002332b  mov     r15d, eax
0x18002332e  mov     rax, [rdi]
0x180023331  mov     rcx, rdi
0x180023334  mov     rax, [rax+10h]
0x180023338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002333d  jmp     short loc_180023388
0x18002333f  mov     rcx, [rbp+57h+ppInterface]
0x180023343  mov     rax, [rcx]
0x180023346  mov     rax, [rax+20h]
0x18002334a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002334f  mov     r15d, eax
0x180023352  test    eax, eax
0x180023354  js      loc_180023479
0x18002335a  mov     rbx, [rbp+57h+ppInterface]
0x18002335e  mov     [rbp+57h+pExceptionObject], rbx
0x180023362  mov     rdx, rsi; struct CNtSid *
0x180023365  mov     rcx, rsi; this
0x180023368  call    ?GetSidFromThreadOrProcess@CIdentitySecurity@@AEAAJAEAVCNtSid@@@Z; CIdentitySecurity::GetSidFromThreadOrProcess(CNtSid &)
0x18002336d  mov     r15d, eax
0x180023370  mov     rcx, rbx
0x180023373  call    ??_9IServerSecurity@@$BCI@AA; [thunk]: IServerSecurity::`vcall'{40,{flat}}
0x180023378  jmp     short loc_18002332E
0x18002337a  mov     rdx, rsi; struct CNtSid *
0x18002337d  mov     rcx, rsi; this
0x180023380  call    ?GetSidFromThreadOrProcess@CIdentitySecurity@@AEAAJAEAVCNtSid@@@Z; CIdentitySecurity::GetSidFromThreadOrProcess(CNtSid &)
0x180023385  mov     r15d, eax
0x180023388  test    r15d, r15d
0x18002338b  js      loc_180023488
0x180023391  mov     rcx, r14; void *
0x180023394  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180023399  nop
0x18002339a  mov     rax, rsi
0x18002339d  mov     rcx, [rbp+57h+var_40]
0x1800233a1  xor     rcx, rsp; StackCookie
0x1800233a4  call    __security_check_cookie
0x1800233a9  add     rsp, 88h
0x1800233b0  pop     r15
0x1800233b2  pop     r14
0x1800233b4  pop     rdi
0x1800233b5  pop     rsi
0x1800233b6  pop     rbx
0x1800233b7  pop     rbp
0x1800233b8  retn
0x1800233b9  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800233be  nop
0x1800233bf  lea     rax, WPP_GLOBAL_Control
0x1800233c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233cd  cmp     rcx, rax
0x1800233d0  jz      short loc_1800233FA
0x1800233d2  test    byte ptr [rcx+1Ch], 1
0x1800233d6  jz      short loc_1800233FA
0x1800233d8  cmp     byte ptr [rcx+19h], 2
0x1800233dc  jb      short loc_1800233FA
0x1800233de  mov     edx, 18h
0x1800233e3  lea     r9, aComexception; "COMException()"
0x1800233ea  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x1800233f1  mov     rcx, [rcx+10h]
0x1800233f5  call    WPP_SF_s
0x1800233fa  mov     eax, [rsi+18h]
0x1800233fd  test    eax, eax
0x1800233ff  jle     short loc_180023409
0x180023401  movzx   eax, ax
0x180023404  or      eax, 80070000h
0x180023409  lea     rcx, ??_7ComException@@6B@; const ComException::`vftable'
0x180023410  mov     [rbp+57h+pExceptionObject], rcx
0x180023414  mov     [rbp+57h+var_68], eax
0x180023417  lea     rdx, _TI2?AVComException@@; pThrowInfo
0x18002341e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023422  call    _CxxThrowException_0
0x180023428  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002342d  lea     rax, WPP_GLOBAL_Control
0x180023434  mov     rcx, cs:WPP_GLOBAL_Control
0x18002343b  cmp     rcx, rax
0x18002343e  jz      short loc_180023468
0x180023440  test    byte ptr [rcx+1Ch], 1
0x180023444  jz      short loc_180023468
0x180023446  cmp     byte ptr [rcx+19h], 2
0x18002344a  jb      short loc_180023468
0x18002344c  mov     edx, 17h
0x180023451  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180023458  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x18002345f  mov     rcx, [rcx+10h]
0x180023463  call    WPP_SF_s
0x180023468  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18002346f  lea     rcx, [rbp+57h+var_90]; pExceptionObject
0x180023473  call    _CxxThrowException_0
0x180023479  mov     rax, [rdi]
0x18002347c  mov     rcx, rdi
0x18002347f  mov     rax, [rax+10h]
0x180023483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023488  mov     edx, 0FFFFFFFEh; int
0x18002348d  lea     rcx, qword_18006A9C0; this
0x180023494  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023499  lea     rax, WPP_GLOBAL_Control
0x1800234a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234a7  cmp     rcx, rax
0x1800234aa  jz      short loc_1800234D4
0x1800234ac  test    byte ptr [rcx+1Ch], 1
0x1800234b0  jz      short loc_1800234D4
0x1800234b2  cmp     byte ptr [rcx+19h], 2
0x1800234b6  jb      short loc_1800234D4
0x1800234b8  mov     edx, 19h
0x1800234bd  lea     r9, aComexception_0; "ComException()"
0x1800234c4  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x1800234cb  mov     rcx, [rcx+10h]
0x1800234cf  call    WPP_SF_s
0x1800234d4  lea     rcx, ??_7ComException@@6B@; const ComException::`vftable'
0x1800234db  mov     [rbp+57h+pExceptionObject], rcx
0x1800234df  mov     [rbp+57h+var_68], r15d
0x1800234e3  lea     rdx, _TI2?AVComException@@; pThrowInfo
0x1800234ea  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800234ee  call    _CxxThrowException_0
```
