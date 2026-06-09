# CWcnSession::PrepareOutgoingMessage(ulong)

- ea: `0x180017054`
- end: `0x18001741d`
- name: `?PrepareOutgoingMessage@CWcnSession@@QEAAJK@Z`
- size: `969`
- prototype: `__int64 __fastcall(CWcnSession *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800157bc`
- `0x180015b84`
- `0x1800471a0`
- `0x18004a7a8`
- `0x18004be80`
- `0x18004f8f8`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180015280`
- `0x180017054`
- `0x180018804`
- `0x180019808`
- `0x180053004`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800170c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800170c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800173b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800173b0`
- `RPCRT4!UuidCreate` at `0x18001711f`
- `RPCRT4!UuidCreate` at `0x18001711f`

## pseudocode

```c
__int64 __fastcall CWcnSession::PrepareOutgoingMessage(CWcnSession *this, unsigned int a2)
{
  char v4; // r14
  const char *Indent; // rax
  __int64 v6; // r10
  __int64 v7; // r8
  char v8; // al
  _QWORD *v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  const char *v15; // rax
  __int64 v16; // r10
  unsigned int v17; // eax
  __int64 v18; // r10
  char v19; // r11
  bool v20; // zf
  __int64 *v21; // rax
  __int64 v22; // rdx
  const char *v23; // rax
  __int64 v24; // r10
  __int16 v26; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v27[16]; // [rsp+40h] [rbp-29h] BYREF
  char *v28; // [rsp+50h] [rbp-19h]
  __int64 v29; // [rsp+58h] [rbp-11h]
  char *v30; // [rsp+60h] [rbp-9h]
  __int64 v31; // [rsp+68h] [rbp-1h]
  __int16 *v32; // [rsp+70h] [rbp+7h]
  __int64 v33; // [rsp+78h] [rbp+Fh]
  __int64 v34; // [rsp+80h] [rbp+17h]
  int v35; // [rsp+88h] [rbp+1Fh]
  int v36; // [rsp+8Ch] [rbp+23h]

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 121, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
  }
  WaitForSingleObject(*((HANDLE *)this + 32), 0xFFFFFFFF);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  v8 = *((_BYTE *)this + 437);
  if ( v8 || *((_BYTE *)this + 438) )
  {
    v12 = 0;
    if ( v8 && *((_BYTE *)this + 448) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v15 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v16 + 16), 124, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v15);
      }
      goto LABEL_42;
    }
    ++*((_DWORD *)this + 114);
    goto LABEL_25;
  }
  v9 = (_QWORD *)*((_QWORD *)this + 41);
  if ( v9 )
    v9[1] = *v9;
  *((_BYTE *)this + 320) = 1;
  *((_QWORD *)this + 37) = (char *)this + 304;
  UuidCreate((UUID *)this + 21);
  v10 = *((_QWORD *)this + 27);
  *((_DWORD *)this + 69) = 3;
  *((_DWORD *)this + 68) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10) )
  {
    v11 = CWcnSession::AdjustProtocolVersion(this);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 122;
LABEL_13:
        WPP_SF_d(v13[2], v14, WPP_a137d119f5dc35a130051116e3170526_Traceguids, (unsigned int)v11);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 27) + 8LL))(*((_QWORD *)this + 27), a2);
  v12 = v11;
  if ( v11 >= 0 )
  {
    *((_QWORD *)this + 37) = 0;
    *((_DWORD *)this + 110) = 0;
LABEL_25:
    if ( *((_DWORD *)this + 110) >= 0x1Eu )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = (unsigned int)GetIndent(0);
        WPP_SF_sd(*(_QWORD *)(v18 + 16), 125, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v17, v19);
      }
      v20 = *((_DWORD *)this + 6) == -2147467259;
      *((_DWORD *)this + 69) = 3;
      if ( v20 )
        *((_DWORD *)this + 6) = -2147176436;
    }
    if ( *((_DWORD *)this + 69) <= 1u )
    {
      if ( (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 1) != 0 )
      {
        v21 = (__int64 *)*((_QWORD *)this + 41);
        v22 = *v21;
        if ( v21 )
          LOWORD(v21) = v21[1] - v22;
        v26 = (__int16)v21;
        v28 = (char *)this + 1576;
        v30 = (char *)this + 336;
        v32 = &v26;
        v34 = v22;
        v35 = (unsigned __int16)v21;
        v29 = 16;
        v31 = 16;
        v33 = 2;
        v36 = 0;
        McGenEventWrite_EtwEventWriteTransfer(WCN_ETW_EVENT_GUID_Context, (__int64)SessionSend, v7, 5, (__int64)v27);
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 25) + 8LL))(
              *((_QWORD *)this + 25),
              *((unsigned int *)this + 70),
              *((unsigned int *)this + 69),
              (char *)this + 304);
      v12 = v11;
      if ( v11 >= 0 )
      {
        ++*((_DWORD *)this + 110);
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 126;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v4 = 1;
    }
    goto LABEL_42;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 123;
    goto LABEL_13;
  }
LABEL_42:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  if ( v4 )
    CWcnSession::StartDisconnect(this, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v23 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v24 + 16), 127, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v23);
  }
  return v12;
}

```

## disassembly

```asm
0x180017054  mov     [rsp-8+arg_10], rbx
0x180017059  push    rbp
0x18001705a  push    rsi
0x18001705b  push    rdi
0x18001705c  push    r14
0x18001705e  push    r15
0x180017060  lea     rbp, [rsp-37h]
0x180017065  sub     rsp, 0A0h
0x18001706c  mov     rax, cs:__security_cookie
0x180017073  xor     rax, rsp
0x180017076  mov     [rbp+57h+var_30], rax
0x18001707a  mov     esi, edx
0x18001707c  mov     rbx, rcx
0x18001707f  xor     r14b, r14b
0x180017082  mov     r10, cs:WPP_GLOBAL_Control
0x180017089  lea     rax, WPP_GLOBAL_Control
0x180017090  cmp     r10, rax
0x180017093  jz      short loc_1800170BE
0x180017095  cmp     byte ptr [r10+19h], 6
0x18001709a  jb      short loc_1800170BE
0x18001709c  mov     ecx, 1; int
0x1800170a1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800170a6  mov     rcx, [r10+10h]
0x1800170aa  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800170b1  mov     edx, 79h ; 'y'
0x1800170b6  mov     r9, rax
0x1800170b9  call    WPP_SF_s
0x1800170be  mov     rcx, [rbx+100h]; hHandle
0x1800170c5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800170c8  call    cs:__imp_WaitForSingleObject
0x1800170ce  lea     r15, [rbx+600h]
0x1800170d5  mov     rcx, r15; lpCriticalSection
0x1800170d8  call    cs:__imp_EnterCriticalSection
0x1800170de  mov     al, [rbx+1B5h]
0x1800170e4  test    al, al
0x1800170e6  jnz     loc_1800171F6
0x1800170ec  cmp     [rbx+1B6h], r14b
0x1800170f3  jnz     loc_1800171F6
0x1800170f9  lea     rdx, [rbx+130h]
0x180017100  mov     rcx, [rdx+18h]
0x180017104  test    rcx, rcx
0x180017107  jz      short loc_180017110
0x180017109  mov     rax, [rcx]
0x18001710c  mov     [rcx+8], rax
0x180017110  mov     byte ptr [rdx+10h], 1
0x180017114  lea     rcx, [rdx+20h]; Uuid
0x180017118  mov     [rbx+128h], rdx
0x18001711f  call    cs:__imp_UuidCreate
0x180017125  mov     rcx, [rbx+0D8h]
0x18001712c  mov     dword ptr [rbx+114h], 3
0x180017136  mov     dword ptr [rbx+110h], 1
0x180017140  mov     rax, [rcx]
0x180017143  mov     rax, [rax+10h]
0x180017147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001714c  test    al, al
0x18001714e  jz      short loc_18001719C
0x180017150  mov     rcx, rbx; this
0x180017153  call    ?AdjustProtocolVersion@CWcnSession@@AEAAJXZ; CWcnSession::AdjustProtocolVersion(void)
0x180017158  mov     edi, eax
0x18001715a  test    eax, eax
0x18001715c  jns     short loc_18001719C
0x18001715e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017165  lea     rsi, WPP_GLOBAL_Control
0x18001716c  cmp     rcx, rsi
0x18001716f  jz      loc_1800173AD
0x180017175  cmp     byte ptr [rcx+19h], 2
0x180017179  jb      loc_1800173AD
0x18001717f  mov     edx, 7Ah ; 'z'
0x180017184  mov     rcx, [rcx+10h]
0x180017188  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001718f  mov     r9d, eax
0x180017192  call    WPP_SF_d
0x180017197  jmp     loc_1800173AD
0x18001719c  mov     rcx, [rbx+0D8h]
0x1800171a3  mov     edx, esi
0x1800171a5  mov     rax, [rcx]
0x1800171a8  mov     rax, [rax+8]
0x1800171ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b1  mov     edi, eax
0x1800171b3  test    eax, eax
0x1800171b5  jns     short loc_1800171DF
0x1800171b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171be  lea     rsi, WPP_GLOBAL_Control
0x1800171c5  cmp     rcx, rsi
0x1800171c8  jz      loc_1800173AD
0x1800171ce  cmp     byte ptr [rcx+19h], 2
0x1800171d2  jb      loc_1800173AD
0x1800171d8  mov     edx, 7Bh ; '{'
0x1800171dd  jmp     short loc_180017184
0x1800171df  mov     qword ptr [rbx+128h], 0
0x1800171ea  mov     dword ptr [rbx+1B8h], 0
0x1800171f4  jmp     short loc_18001724F
0x1800171f6  xor     edi, edi
0x1800171f8  test    al, al
0x1800171fa  jz      short loc_180017249
0x1800171fc  cmp     [rbx+1C0h], dil
0x180017203  jz      short loc_180017249
0x180017205  mov     r10, cs:WPP_GLOBAL_Control
0x18001720c  lea     rsi, WPP_GLOBAL_Control
0x180017213  cmp     r10, rsi
0x180017216  jz      loc_1800173AD
0x18001721c  cmp     byte ptr [r10+19h], 4
0x180017221  jb      loc_1800173AD
0x180017227  xor     ecx, ecx; int
0x180017229  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001722e  mov     rcx, [r10+10h]
0x180017232  lea     edx, [rdi+7Ch]
0x180017235  mov     r9, rax
0x180017238  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001723f  call    WPP_SF_s
0x180017244  jmp     loc_1800173AD
0x180017249  inc     dword ptr [rbx+1C8h]
0x18001724f  mov     r11d, [rbx+1B8h]
0x180017256  cmp     r11d, 1Eh
0x18001725a  jb      short loc_1800172B6
0x18001725c  mov     r10, cs:WPP_GLOBAL_Control
0x180017263  lea     rsi, WPP_GLOBAL_Control
0x18001726a  cmp     r10, rsi
0x18001726d  jz      short loc_18001729A
0x18001726f  cmp     byte ptr [r10+19h], 2
0x180017274  jb      short loc_18001729A
0x180017276  xor     ecx, ecx; int
0x180017278  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001727d  mov     rcx, [r10+10h]
0x180017281  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180017288  mov     edx, 7Dh ; '}'
0x18001728d  mov     dword ptr [rsp+0C0h+var_A0], r11d
0x180017292  mov     r9, rax
0x180017295  call    WPP_SF_sd
0x18001729a  cmp     dword ptr [rbx+18h], 80004005h
0x1800172a1  mov     dword ptr [rbx+114h], 3
0x1800172ab  jnz     short loc_1800172BD
0x1800172ad  mov     dword ptr [rbx+18h], 8004B00Ch
0x1800172b4  jmp     short loc_1800172BD
0x1800172b6  lea     rsi, WPP_GLOBAL_Control
0x1800172bd  cmp     dword ptr [rbx+114h], 1
0x1800172c4  jbe     short loc_1800172CE
0x1800172c6  mov     r14b, 1
0x1800172c9  jmp     loc_1800173AD
0x1800172ce  test    byte ptr cs:Microsoft_Windows_WCN_Config_RegistrarEnableBits, 1
0x1800172d5  jz      loc_18001735E
0x1800172db  mov     rax, [rbx+148h]
0x1800172e2  mov     rdx, [rax]
0x1800172e5  test    rax, rax
0x1800172e8  jz      short loc_1800172F1
0x1800172ea  mov     rax, [rax+8]
0x1800172ee  sub     rax, rdx
0x1800172f1  movzx   ecx, ax
0x1800172f4  mov     r9d, 5
0x1800172fa  lea     rax, [rbx+628h]
0x180017301  mov     [rbp+57h+var_90], cx
0x180017305  mov     [rbp+57h+var_70], rax
0x180017309  lea     rax, [rbx+150h]
0x180017310  mov     [rbp+57h+var_60], rax
0x180017314  lea     rax, [rbp+57h+var_90]
0x180017318  mov     [rbp+57h+var_50], rax
0x18001731c  lea     rax, [rbp+57h+var_80]
0x180017320  mov     [rbp+57h+var_40], rdx
0x180017324  lea     rdx, SessionSend
0x18001732b  mov     [rbp+57h+var_38], ecx
0x18001732e  lea     rcx, WCN_ETW_EVENT_GUID_Context
0x180017335  mov     [rsp+0C0h+var_A0], rax
0x18001733a  mov     [rbp+57h+var_68], 10h
0x180017342  mov     [rbp+57h+var_58], 10h
0x18001734a  mov     [rbp+57h+var_48], 2
0x180017352  mov     [rbp+57h+var_34], 0
0x180017359  call    McGenEventWrite_EtwEventWriteTransfer
0x18001735e  mov     rcx, [rbx+0C8h]
0x180017365  lea     r9, [rbx+130h]
0x18001736c  mov     r8d, [rbx+114h]
0x180017373  mov     edx, [rbx+118h]
0x180017379  mov     rax, [rcx]
0x18001737c  mov     rax, [rax+8]
0x180017380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017385  mov     edi, eax
0x180017387  test    eax, eax
0x180017389  jns     short loc_1800173A7
0x18001738b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017392  cmp     rcx, rsi
0x180017395  jz      short loc_1800173AD
0x180017397  cmp     byte ptr [rcx+19h], 2
0x18001739b  jb      short loc_1800173AD
0x18001739d  mov     edx, 7Eh ; '~'
0x1800173a2  jmp     loc_180017184
0x1800173a7  inc     dword ptr [rbx+1B8h]
0x1800173ad  mov     rcx, r15; lpCriticalSection
0x1800173b0  call    cs:__imp_LeaveCriticalSection
0x1800173b6  test    r14b, r14b
0x1800173b9  jz      short loc_1800173C5
0x1800173bb  xor     edx, edx; bool
0x1800173bd  mov     rcx, rbx; this
0x1800173c0  call    ?StartDisconnect@CWcnSession@@QEAAX_N@Z; CWcnSession::StartDisconnect(bool)
0x1800173c5  mov     r10, cs:WPP_GLOBAL_Control
0x1800173cc  cmp     r10, rsi
0x1800173cf  jz      short loc_1800173F8
0x1800173d1  cmp     byte ptr [r10+19h], 6
0x1800173d6  jb      short loc_1800173F8
0x1800173d8  or      ecx, 0FFFFFFFFh; int
0x1800173db  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800173e0  mov     rcx, [r10+10h]
0x1800173e4  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800173eb  mov     edx, 7Fh
0x1800173f0  mov     r9, rax
0x1800173f3  call    WPP_SF_s
0x1800173f8  mov     eax, edi
0x1800173fa  mov     rcx, [rbp+57h+var_30]
0x1800173fe  xor     rcx, rsp; StackCookie
0x180017401  call    __security_check_cookie
0x180017406  mov     rbx, [rsp+0C0h+arg_10]
0x18001740e  add     rsp, 0A0h
0x180017415  pop     r15
0x180017417  pop     r14
0x180017419  pop     rdi
0x18001741a  pop     rsi
0x18001741b  pop     rbp
0x18001741c  retn
```
