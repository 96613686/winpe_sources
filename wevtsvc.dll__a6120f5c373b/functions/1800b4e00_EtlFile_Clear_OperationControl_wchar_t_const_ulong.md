# EtlFile::Clear(OperationControl *,wchar_t const *,ulong)

- ea: `0x1800b4e00`
- end: `0x1800b5106`
- name: `?Clear@EtlFile@@UEAAXPEAVOperationControl@@PEB_WK@Z`
- size: `774`
- prototype: `void __fastcall(EtlFile *this, struct OperationControl *, const wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180017e94`
- `0x1800613d8`
- `0x180092008`
- `0x180098c50`
- `0x1800b4e00`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b4f34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b4f34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b50e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b50e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b502f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b502f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b4f57`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b5025`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b4f57`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b5025`

## pseudocode

```c
void __fastcall EtlFile::Clear(EtlFile *this, struct OperationControl *a2, const wchar_t *a3)
{
  __int64 v5; // r12
  DWORD LastError; // ebx
  DWORD v7; // r15d
  __int64 v8; // r13
  PVOID *v9; // rcx
  __int128 pExceptionObject; // [rsp+38h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h]
  int v12; // [rsp+50h] [rbp-10h]
  int v13; // [rsp+54h] [rbp-Ch]
  int v14; // [rsp+58h] [rbp-8h]
  DWORD GrantedAccess; // [rsp+90h] [rbp+30h] BYREF

  v5 = 0;
  GrantedAccess = 0;
  if ( !EvtCheckAccess(*((PSECURITY_DESCRIPTOR *)this + 76), 4u, &GrantedAccess, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 5);
    }
    pExceptionObject = 0;
    v11 = 0;
    v12 = 5;
    v13 = -1;
    v14 = 104;
    throw (EvtException *)&pExceptionObject;
  }
  if ( a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, 50);
    }
    pExceptionObject = 0;
    v11 = 0;
    v12 = 50;
    v13 = -1;
    v14 = 109;
    throw (EvtException *)&pExceptionObject;
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 84);
  if ( FileExists(*((const wchar_t **)this + 2)) )
  {
    if ( !DeleteFileW(*((LPCWSTR *)this + 2)) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, LastError);
      }
      pExceptionObject = 0;
      v11 = 0;
      v12 = LastError;
      v13 = -1;
      v14 = 118;
      throw (EvtException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids,
        *((_QWORD *)this + 2));
    }
  }
  v7 = 0;
  do
  {
    v8 = 32 * v5;
    if ( !FileExists(*((const wchar_t **)this + 4 * v5 + 6)) )
      goto LABEL_34;
    if ( !DeleteFileW(*(LPCWSTR *)((char *)this + v8 + 48)) )
    {
      v7 = GetLastError();
LABEL_34:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids,
        *(_QWORD *)((char *)this + v8 + 48));
      goto LABEL_34;
    }
LABEL_35:
    ++v5;
  }
  while ( v5 != 16 );
  if ( v7 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_d(v9[2], 20, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids, v7);
    pExceptionObject = 0;
    v11 = 0;
    v12 = v7;
    v13 = -1;
    v14 = 143;
    throw (EvtException *)&pExceptionObject;
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this + 84);
}

```

## disassembly

```asm
0x1800b4e00  mov     [rsp-28h+arg_8], rbx
0x1800b4e05  mov     [rsp-28h+arg_10], rsi
0x1800b4e0a  push    rbp
0x1800b4e0b  push    r12
0x1800b4e0d  push    r13
0x1800b4e0f  push    r14
0x1800b4e11  push    r15
0x1800b4e13  mov     rbp, rsp
0x1800b4e16  sub     rsp, 60h
0x1800b4e1a  mov     rbx, r8
0x1800b4e1d  mov     r14, rcx
0x1800b4e20  xor     r12d, r12d
0x1800b4e23  mov     [rbp+GrantedAccess], r12d
0x1800b4e27  mov     [rsp+60h+var_40], r12b; bool
0x1800b4e2c  xor     r9d, r9d; bool
0x1800b4e2f  lea     r8, [rbp+GrantedAccess]; GrantedAccess
0x1800b4e33  lea     edx, [r12+4]; DesiredAccess
0x1800b4e38  mov     rcx, [rcx+260h]; SecurityDescriptor
0x1800b4e3f  call    ?EvtCheckAccess@@YA_NPEAXKAEAK_N2@Z; EvtCheckAccess(void *,ulong,ulong &,bool,bool)
0x1800b4e44  test    al, al
0x1800b4e46  jnz     short loc_1800B4EB6
0x1800b4e48  lea     rsi, WPP_GLOBAL_Control
0x1800b4e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4e56  cmp     rcx, rsi
0x1800b4e59  jz      short loc_1800B4E84
0x1800b4e5b  test    dword ptr [rcx+1Ch], 200h
0x1800b4e62  jz      short loc_1800B4E84
0x1800b4e64  cmp     byte ptr [rcx+19h], 2
0x1800b4e68  jb      short loc_1800B4E84
0x1800b4e6a  lea     edx, [r12+0Fh]
0x1800b4e6f  lea     r9d, [r12+5]
0x1800b4e74  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800b4e7b  mov     rcx, [rcx+10h]
0x1800b4e7f  call    WPP_SF_d
0x1800b4e84  xorps   xmm0, xmm0
0x1800b4e87  movdqu  [rbp+pExceptionObject], xmm0
0x1800b4e8c  mov     [rbp+var_18], r12
0x1800b4e90  mov     [rbp+var_10], 5
0x1800b4e97  mov     [rbp+var_C], 0FFFFFFFFh
0x1800b4e9e  mov     [rbp+var_8], 68h ; 'h'
0x1800b4ea5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b4eac  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b4eb0  call    _CxxThrowException_0
0x1800b4eb6  test    rbx, rbx
0x1800b4eb9  jz      short loc_1800B4F26
0x1800b4ebb  lea     rsi, WPP_GLOBAL_Control
0x1800b4ec2  mov     ebx, 32h ; '2'
0x1800b4ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4ece  cmp     rcx, rsi
0x1800b4ed1  jz      short loc_1800B4EF8
0x1800b4ed3  test    dword ptr [rcx+1Ch], 200h
0x1800b4eda  jz      short loc_1800B4EF8
0x1800b4edc  cmp     byte ptr [rcx+19h], 2
0x1800b4ee0  jb      short loc_1800B4EF8
0x1800b4ee2  lea     edx, [rbx-22h]
0x1800b4ee5  mov     r9d, ebx
0x1800b4ee8  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800b4eef  mov     rcx, [rcx+10h]
0x1800b4ef3  call    WPP_SF_d
0x1800b4ef8  xorps   xmm0, xmm0
0x1800b4efb  movdqu  [rbp+pExceptionObject], xmm0
0x1800b4f00  mov     [rbp+var_18], r12
0x1800b4f04  mov     [rbp+var_10], ebx
0x1800b4f07  mov     [rbp+var_C], 0FFFFFFFFh
0x1800b4f0e  mov     [rbp+var_8], 6Dh ; 'm'
0x1800b4f15  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b4f1c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b4f20  call    _CxxThrowException_0
0x1800b4f26  lea     rbx, [r14+2A0h]
0x1800b4f2d  mov     [rbp+var_30], rbx
0x1800b4f31  mov     rcx, rbx; SRWLock
0x1800b4f34  call    cs:__imp_AcquireSRWLockExclusive
0x1800b4f3a  nop
0x1800b4f3b  mov     rcx, [r14+10h]; wchar_t *
0x1800b4f3f  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x1800b4f44  lea     rsi, WPP_GLOBAL_Control
0x1800b4f4b  test    al, al
0x1800b4f4d  jz      loc_1800B5008
0x1800b4f53  mov     rcx, [r14+10h]; lpFileName
0x1800b4f57  call    cs:__imp_DeleteFileW
0x1800b4f5d  test    eax, eax
0x1800b4f5f  jnz     short loc_1800B4FD4
0x1800b4f61  call    cs:__imp_GetLastError
0x1800b4f67  mov     ebx, eax
0x1800b4f69  mov     eax, 507h
0x1800b4f6e  test    ebx, ebx
0x1800b4f70  cmovz   ebx, eax
0x1800b4f73  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4f7a  cmp     rcx, rsi
0x1800b4f7d  jz      short loc_1800B4FA6
0x1800b4f7f  test    dword ptr [rcx+1Ch], 200h
0x1800b4f86  jz      short loc_1800B4FA6
0x1800b4f88  cmp     byte ptr [rcx+19h], 2
0x1800b4f8c  jb      short loc_1800B4FA6
0x1800b4f8e  mov     edx, 11h
0x1800b4f93  mov     r9d, ebx
0x1800b4f96  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800b4f9d  mov     rcx, [rcx+10h]
0x1800b4fa1  call    WPP_SF_d
0x1800b4fa6  xorps   xmm0, xmm0
0x1800b4fa9  movdqu  [rbp+pExceptionObject], xmm0
0x1800b4fae  mov     [rbp+var_18], r12
0x1800b4fb2  mov     [rbp+var_10], ebx
0x1800b4fb5  mov     [rbp+var_C], 0FFFFFFFFh
0x1800b4fbc  mov     [rbp+var_8], 76h ; 'v'
0x1800b4fc3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b4fca  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b4fce  call    _CxxThrowException_0
0x1800b4fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4fdb  cmp     rcx, rsi
0x1800b4fde  jz      short loc_1800B5008
0x1800b4fe0  test    dword ptr [rcx+1Ch], 200h
0x1800b4fe7  jz      short loc_1800B5008
0x1800b4fe9  cmp     byte ptr [rcx+19h], 5
0x1800b4fed  jb      short loc_1800B5008
0x1800b4fef  mov     edx, 12h
0x1800b4ff4  mov     r9, [r14+10h]
0x1800b4ff8  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800b4fff  mov     rcx, [rcx+10h]
0x1800b5003  call    WPP_SF_S
0x1800b5008  mov     r15d, r12d
0x1800b500b  mov     r13, r12
0x1800b500e  shl     r13, 5
0x1800b5012  mov     rcx, [r14+r13+30h]; wchar_t *
0x1800b5017  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x1800b501c  test    al, al
0x1800b501e  jz      short loc_1800B506F
0x1800b5020  mov     rcx, [r14+r13+30h]; lpFileName
0x1800b5025  call    cs:__imp_DeleteFileW
0x1800b502b  test    eax, eax
0x1800b502d  jnz     short loc_1800B503A
0x1800b502f  call    cs:__imp_GetLastError
0x1800b5035  mov     r15d, eax
0x1800b5038  jmp     short loc_1800B506F
0x1800b503a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5041  cmp     rcx, rsi
0x1800b5044  jz      short loc_1800B5076
0x1800b5046  test    dword ptr [rcx+1Ch], 200h
0x1800b504d  jz      short loc_1800B5076
0x1800b504f  cmp     byte ptr [rcx+19h], 5
0x1800b5053  jb      short loc_1800B5076
0x1800b5055  mov     edx, 13h
0x1800b505a  mov     r9, [r14+r13+30h]
0x1800b505f  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800b5066  mov     rcx, [rcx+10h]
0x1800b506a  call    WPP_SF_S
0x1800b506f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5076  inc     r12
0x1800b5079  cmp     r12, 10h
0x1800b507d  jnz     short loc_1800B500B
0x1800b507f  test    r15d, r15d
0x1800b5082  jz      short loc_1800B50E3
0x1800b5084  cmp     rcx, rsi
0x1800b5087  jz      short loc_1800B50B0
0x1800b5089  test    dword ptr [rcx+1Ch], 200h
0x1800b5090  jz      short loc_1800B50B0
0x1800b5092  cmp     byte ptr [rcx+19h], 2
0x1800b5096  jb      short loc_1800B50B0
0x1800b5098  lea     edx, [r12+4]
0x1800b509d  mov     r9d, r15d
0x1800b50a0  lea     r8, WPP_df2db0e57fcf329b720e46088dc10b5a_Traceguids
0x1800b50a7  mov     rcx, [rcx+10h]
0x1800b50ab  call    WPP_SF_d
0x1800b50b0  xorps   xmm0, xmm0
0x1800b50b3  movdqu  [rbp+pExceptionObject], xmm0
0x1800b50b8  mov     [rbp+var_18], 0
0x1800b50c0  mov     [rbp+var_10], r15d
0x1800b50c4  mov     [rbp+var_C], 0FFFFFFFFh
0x1800b50cb  mov     [rbp+var_8], 8Fh
0x1800b50d2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b50d9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b50dd  call    _CxxThrowException_0
0x1800b50e3  mov     rcx, rbx; SRWLock
0x1800b50e6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b50ec  lea     r11, [rsp+60h+var_s0]
0x1800b50f1  mov     rbx, [r11+38h]
0x1800b50f5  mov     rsi, [r11+40h]
0x1800b50f9  mov     rsp, r11
0x1800b50fc  pop     r15
0x1800b50fe  pop     r14
0x1800b5100  pop     r13
0x1800b5102  pop     r12
0x1800b5104  pop     rbp
0x1800b5105  retn
```
