# EvtOpenSession

- ea: `0x18001f170`
- end: `0x18001f353`
- name: `EvtOpenSession`
- size: `483`
- prototype: `EVT_HANDLE __stdcall(EVT_LOGIN_CLASS LoginClass, PVOID Login, DWORD Timeout, DWORD Flags)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180006aec`
- `0x180007010`
- `0x18001f170`
- `0x180021d1c`
- `0x180023548`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f313`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f313`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
EVT_HANDLE __stdcall EvtOpenSession(EVT_LOGIN_CLASS LoginClass, PVOID Login, DWORD Timeout, DWORD Flags)
{
  Session *v8; // rsi
  __int64 v9; // rcx
  Session *v10; // rcx
  DWORD v11; // ecx
  void *v12; // r14
  Session *v14; // [rsp+20h] [rbp-A8h] BYREF
  struct _EVT_RPC_LOGIN *v15; // [rsp+28h] [rbp-A0h] BYREF
  unsigned __int64 v16; // [rsp+30h] [rbp-98h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-90h] BYREF
  __int64 v18; // [rsp+48h] [rbp-80h]
  int v19; // [rsp+50h] [rbp-78h]
  int v20; // [rsp+54h] [rbp-74h]
  int v21; // [rsp+58h] [rbp-70h]
  __int128 v22; // [rsp+60h] [rbp-68h] BYREF
  __int64 v23; // [rsp+70h] [rbp-58h]
  int v24; // [rsp+78h] [rbp-50h]
  int v25; // [rsp+7Ch] [rbp-4Ch]
  int v26; // [rsp+80h] [rbp-48h]

  v8 = 0;
  v14 = 0;
  LastErrInfo::Reset(*(LastErrInfo **)&LoginClass);
  if ( LoginClass != EvtRpcLogin || !Login || Flags )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    v22 = 0;
    v23 = 0;
    v24 = 87;
    v25 = -1;
    v26 = 199;
    throw (EvtException *)&v22;
  }
  if ( Timeout )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 50);
    }
    pExceptionObject = 0;
    v18 = 0;
    v19 = 50;
    v20 = -1;
    v21 = 204;
    throw (EvtException *)&pExceptionObject;
  }
  v15 = (struct _EVT_RPC_LOGIN *)Login;
  v16 = 0;
  v10 = HandleTable::Emplace<Session,_EVT_RPC_LOGIN *>(v9, &v16, &v15);
  if ( v10 )
  {
    *((_QWORD *)v10 + 2) = v16;
    _InterlockedAdd((volatile signed __int32 *)v10 + 2, 1u);
    _InterlockedAdd((volatile signed __int32 *)v10 + 6, 1u);
    v8 = v10;
    v14 = v10;
    v15 = 0;
    EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v15);
    v11 = 0;
  }
  else
  {
    v11 = 14;
  }
  SetLastError(v11);
  if ( v8 )
  {
    v12 = (void *)*((_QWORD *)v8 + 2);
    v14 = 0;
    *((_BYTE *)v8 + 29) = 1;
  }
  else
  {
    v12 = 0;
  }
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v14);
  return v12;
}

```

## disassembly

```asm
0x18001f170  push    rsi
0x18001f172  push    rdi
0x18001f173  push    r12
0x18001f175  push    r13
0x18001f177  push    r14
0x18001f179  push    r15
0x18001f17b  sub     rsp, 98h
0x18001f182  mov     r13d, r9d
0x18001f185  mov     r12d, r8d
0x18001f188  mov     r14, rdx
0x18001f18b  mov     r15d, ecx
0x18001f18e  xor     esi, esi
0x18001f190  mov     [rsp+0C8h+var_A8], rsi
0x18001f195  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18001f19a  lea     edi, [rsi+1]
0x18001f19d  cmp     r15d, edi
0x18001f1a0  jnz     loc_18001F28B
0x18001f1a6  test    r14, r14
0x18001f1a9  jz      loc_18001F28B
0x18001f1af  test    r13d, r13d
0x18001f1b2  jnz     loc_18001F28B
0x18001f1b8  test    r12d, r12d
0x18001f1bb  jz      short loc_18001F22E
0x18001f1bd  lea     rax, WPP_GLOBAL_Control
0x18001f1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1cb  cmp     rcx, rax
0x18001f1ce  jz      short loc_18001F1F3
0x18001f1d0  test    [rcx+1Ch], dil
0x18001f1d4  jz      short loc_18001F1F3
0x18001f1d6  cmp     byte ptr [rcx+19h], 2
0x18001f1da  jb      short loc_18001F1F3
0x18001f1dc  lea     edx, [rsi+13h]
0x18001f1df  lea     r9d, [rsi+32h]
0x18001f1e3  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001f1ea  mov     rcx, [rcx+10h]
0x18001f1ee  call    WPP_SF_D
0x18001f1f3  xorps   xmm0, xmm0
0x18001f1f6  movdqu  [rsp+0C8h+pExceptionObject], xmm0
0x18001f1fc  mov     [rsp+0C8h+var_80], 0
0x18001f205  mov     [rsp+0C8h+var_78], 32h ; '2'
0x18001f20d  mov     [rsp+0C8h+var_74], 0FFFFFFFFh
0x18001f215  mov     [rsp+0C8h+var_70], 0CCh
0x18001f21d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f224  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18001f229  call    _CxxThrowException_0
0x18001f22e  mov     [rsp+0C8h+var_A0], r14
0x18001f233  mov     [rsp+0C8h+var_98], 0
0x18001f23c  lea     r8, [rsp+0C8h+var_A0]
0x18001f241  lea     rdx, [rsp+0C8h+var_98]
0x18001f246  call    ??$Emplace@VSession@@PEAU_EVT_RPC_LOGIN@@@HandleTable@@QEAAPEAVSession@@AEAPEAX$$QEAPEAU_EVT_RPC_LOGIN@@@Z; HandleTable::Emplace<Session,_EVT_RPC_LOGIN *>(void * &,_EVT_RPC_LOGIN * &&)
0x18001f24b  mov     rcx, rax
0x18001f24e  test    rax, rax
0x18001f251  jnz     short loc_18001F258
0x18001f253  lea     ecx, [rax+0Eh]
0x18001f256  jmp     short loc_18001F286
0x18001f258  mov     rax, [rsp+0C8h+var_98]
0x18001f25d  mov     [rcx+10h], rax
0x18001f261  lock add [rcx+8], edi
0x18001f265  lock add [rcx+18h], edi
0x18001f269  mov     rsi, rcx
0x18001f26c  mov     [rsp+0C8h+var_A8], rcx
0x18001f271  mov     [rsp+0C8h+var_A0], 0
0x18001f27a  lea     rcx, [rsp+0C8h+var_A0]; this
0x18001f27f  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001f284  xor     ecx, ecx
0x18001f286  jmp     loc_18001F313
0x18001f28b  lea     rax, WPP_GLOBAL_Control
0x18001f292  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f299  cmp     rcx, rax
0x18001f29c  jz      short loc_18001F2C3
0x18001f29e  test    [rcx+1Ch], dil
0x18001f2a2  jz      short loc_18001F2C3
0x18001f2a4  cmp     byte ptr [rcx+19h], 2
0x18001f2a8  jb      short loc_18001F2C3
0x18001f2aa  mov     edx, 12h
0x18001f2af  lea     r9d, [rdx+45h]
0x18001f2b3  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001f2ba  mov     rcx, [rcx+10h]
0x18001f2be  call    WPP_SF_D
0x18001f2c3  xorps   xmm0, xmm0
0x18001f2c6  movdqu  [rsp+0C8h+var_68], xmm0
0x18001f2cc  mov     [rsp+0C8h+var_58], 0
0x18001f2d5  mov     [rsp+0C8h+var_50], 57h ; 'W'
0x18001f2dd  mov     [rsp+0C8h+var_4C], 0FFFFFFFFh
0x18001f2e5  mov     [rsp+0C8h+var_48], 0C7h
0x18001f2f0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f2f7  lea     rcx, [rsp+0C8h+var_68]; pExceptionObject
0x18001f2fc  call    _CxxThrowException_0
0x18001f302  mov     edi, 1
0x18001f307  mov     ecx, [rsp+0C8h+dwErrCode]; dwErrCode
0x18001f30e  mov     rsi, [rsp+0C8h+var_A8]
0x18001f313  call    cs:__imp_SetLastError
0x18001f319  test    rsi, rsi
0x18001f31c  jz      short loc_18001F331
0x18001f31e  mov     r14, [rsi+10h]
0x18001f322  mov     [rsp+0C8h+var_A8], 0
0x18001f32b  xchg    dil, [rsi+1Dh]
0x18001f32f  jmp     short loc_18001F334
0x18001f331  xor     r14d, r14d
0x18001f334  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001f339  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001f33e  mov     rax, r14
0x18001f341  add     rsp, 98h
0x18001f348  pop     r15
0x18001f34a  pop     r14
0x18001f34c  pop     r13
0x18001f34e  pop     r12
0x18001f350  pop     rdi
0x18001f351  pop     rsi
0x18001f352  retn
```
