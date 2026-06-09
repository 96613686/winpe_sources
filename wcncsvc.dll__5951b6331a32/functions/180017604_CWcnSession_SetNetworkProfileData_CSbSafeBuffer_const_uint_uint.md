# CWcnSession::SetNetworkProfileData(CSbSafeBuffer const *,uint,uint)

- ea: `0x180017604`
- end: `0x180017a69`
- name: `?SetNetworkProfileData@CWcnSession@@QEAAJPEBVCSbSafeBuffer@@II@Z`
- size: `1125`
- prototype: `int(CWcnSession *__hidden this, const struct CSbSafeBuffer *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180037560`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a5ac`
- `0x180017604`
- `0x18001a57c`
- `0x18001b548`
- `0x18001b82c`
- `0x18001cdd0`
- `0x18001d1e8`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800179d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800179d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800176ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800176ed`

## string_xrefs

- `0x1800176c8`: `pSsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWcnSession::SetNetworkProfileData(
        RTL_SRWLOCK *this,
        const struct CSbSafeBuffer *a2,
        unsigned int a3,
        unsigned int a4)
{
  _QWORD *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  int v11; // ebx
  int appended; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r10
  _BYTE v18[24]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[40]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v22[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v23[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v24[24]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v25[40]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v26[24]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v27[40]; // [rsp+148h] [rbp+48h] BYREF

  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v26);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v24);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v22);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v20);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v18);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 62, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_s(v8[2], 63, WPP_a137d119f5dc35a130051116e3170526_Traceguids, "pSsid");
    v11 = -2147467261;
    goto LABEL_55;
  }
  AcquireSRWLockExclusive(this + 9);
  CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&this[10], WCN_TYPE_SSID);
  CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&this[10], WCN_TYPE_AUTHENTICATION_TYPE);
  CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&this[10], WCN_TYPE_ENCRYPTION_TYPE);
  CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&this[10], WCN_TYPE_NETWORK_INDEX);
  CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&this[10], WCN_TYPE_NETWORK_KEY_INDEX);
  appended = CWcnAttribute::SetValueFromBlob((CWcnAttribute *)v26, WCN_TYPE_SSID, a2);
  v11 = appended;
  if ( appended >= 0 )
  {
    appended = CWcnAttributeDatabase::AppendAttribute(
                 (CWcnAttributeDatabase *)&this[10],
                 (const struct CWcnAttribute *)v26);
    v11 = appended;
    if ( appended >= 0 )
    {
      appended = CWcnAttribute::SetValueFromInteger((CWcnAttribute *)v24, WCN_TYPE_AUTHENTICATION_TYPE, a3);
      v11 = appended;
      if ( appended >= 0 )
      {
        appended = CWcnAttributeDatabase::AppendAttribute(
                     (CWcnAttributeDatabase *)&this[10],
                     (const struct CWcnAttribute *)v24);
        v11 = appended;
        if ( appended >= 0 )
        {
          appended = CWcnAttribute::SetValueFromInteger((CWcnAttribute *)v22, WCN_TYPE_ENCRYPTION_TYPE, a4);
          v11 = appended;
          if ( appended >= 0 )
          {
            appended = CWcnAttributeDatabase::AppendAttribute(
                         (CWcnAttributeDatabase *)&this[10],
                         (const struct CWcnAttribute *)v22);
            v11 = appended;
            if ( appended >= 0 )
            {
              appended = CWcnAttribute::SetValueFromInteger((CWcnAttribute *)v20, WCN_TYPE_NETWORK_INDEX, 1u);
              v11 = appended;
              if ( appended >= 0 )
              {
                appended = CWcnAttributeDatabase::AppendAttribute(
                             (CWcnAttributeDatabase *)&this[10],
                             (const struct CWcnAttribute *)v20);
                v11 = appended;
                if ( appended >= 0 )
                {
                  appended = CWcnAttribute::SetValueFromInteger((CWcnAttribute *)v18, WCN_TYPE_NETWORK_KEY_INDEX, 1u);
                  v11 = appended;
                  if ( appended >= 0 )
                  {
                    appended = CWcnAttributeDatabase::AppendAttribute(
                                 (CWcnAttributeDatabase *)&this[10],
                                 (const struct CWcnAttribute *)v18);
                    v11 = appended;
                    if ( appended >= 0 )
                    {
                      LOBYTE(this[54].Ptr) = 1;
                      LOBYTE(this[185].Ptr) = 1;
                      goto LABEL_51;
                    }
                    v13 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v14 = 73;
                      goto LABEL_13;
                    }
                  }
                  else
                  {
                    v13 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v14 = 72;
                      goto LABEL_13;
                    }
                  }
                }
                else
                {
                  v13 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v14 = 71;
                    goto LABEL_13;
                  }
                }
              }
              else
              {
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v14 = 70;
                  goto LABEL_13;
                }
              }
            }
            else
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v14 = 69;
                goto LABEL_13;
              }
            }
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = 68;
              goto LABEL_13;
            }
          }
        }
        else
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 67;
            goto LABEL_13;
          }
        }
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 66;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 65;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 64;
LABEL_13:
      WPP_SF_d(v13[2], v14, WPP_a137d119f5dc35a130051116e3170526_Traceguids, (unsigned int)appended);
    }
  }
LABEL_51:
  ReleaseSRWLockExclusive(this + 9);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v11 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v15 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v16 + 16), 74, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v15, v11);
  }
LABEL_55:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v19);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v21);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v23);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v25);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v27);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017604  push    rbp
0x180017606  push    rbx
0x180017607  push    rsi
0x180017608  push    r12
0x18001760a  push    r13
0x18001760c  push    r14
0x18001760e  push    r15
0x180017610  lea     rbp, [rsp-80h]
0x180017615  sub     rsp, 180h
0x18001761c  mov     rax, cs:__security_cookie
0x180017623  xor     rax, rsp
0x180017626  mov     [rbp+0B0h+var_40], rax
0x18001762a  mov     r12d, r9d
0x18001762d  mov     r15d, r8d
0x180017630  mov     rbx, rdx
0x180017633  mov     r14, rcx
0x180017636  lea     rcx, [rbp+0B0h+var_80]; this
0x18001763a  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18001763f  nop
0x180017640  lea     rcx, [rbp+0B0h+var_C0]; this
0x180017644  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x180017649  nop
0x18001764a  lea     rcx, [rbp+0B0h+var_100]; this
0x18001764e  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x180017653  nop
0x180017654  lea     rcx, [rsp+1B0h+var_140]; this
0x180017659  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18001765e  nop
0x18001765f  lea     rcx, [rsp+1B0h+var_180]; this
0x180017664  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x180017669  nop
0x18001766a  lea     rax, WPP_GLOBAL_Control
0x180017671  mov     r10, cs:WPP_GLOBAL_Control
0x180017678  cmp     r10, rax
0x18001767b  jz      short loc_1800176B4
0x18001767d  cmp     byte ptr [r10+19h], 6
0x180017682  jb      short loc_1800176B4
0x180017684  mov     ecx, 1; int
0x180017689  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001768e  mov     edx, 3Eh ; '>'
0x180017693  mov     r9, rax
0x180017696  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001769d  mov     rcx, [r10+10h]
0x1800176a1  call    WPP_SF_s
0x1800176a6  mov     r10, cs:WPP_GLOBAL_Control
0x1800176ad  lea     rax, WPP_GLOBAL_Control
0x1800176b4  test    rbx, rbx
0x1800176b7  jnz     short loc_1800176E9
0x1800176b9  cmp     r10, rax
0x1800176bc  jz      short loc_1800176DF
0x1800176be  cmp     byte ptr [r10+19h], 2
0x1800176c3  jb      short loc_1800176DF
0x1800176c5  lea     edx, [rbx+3Fh]
0x1800176c8  lea     r9, aPssid; "pSsid"
0x1800176cf  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800176d6  mov     rcx, [r10+10h]
0x1800176da  call    WPP_SF_s
0x1800176df  mov     ebx, 80004003h
0x1800176e4  jmp     loc_180017A16
0x1800176e9  lea     rcx, [r14+48h]; SRWLock
0x1800176ed  call    cs:__imp_AcquireSRWLockExclusive
0x1800176f3  lea     rsi, [r14+50h]
0x1800176f7  mov     edx, 3Ch ; '<'; enum tagWCN_ATTRIBUTE_TYPE
0x1800176fc  mov     rcx, rsi; this
0x1800176ff  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x180017704  mov     edx, 2; enum tagWCN_ATTRIBUTE_TYPE
0x180017709  mov     rcx, rsi; this
0x18001770c  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x180017711  mov     edx, 13h; enum tagWCN_ATTRIBUTE_TYPE
0x180017716  mov     rcx, rsi; this
0x180017719  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x18001771e  mov     edx, 20h ; ' '; enum tagWCN_ATTRIBUTE_TYPE
0x180017723  mov     rcx, rsi; this
0x180017726  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x18001772b  mov     edx, 22h ; '"'; enum tagWCN_ATTRIBUTE_TYPE
0x180017730  mov     rcx, rsi; this
0x180017733  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x180017738  mov     r8, rbx; struct CSbSafeBuffer *
0x18001773b  mov     edx, 3Ch ; '<'; enum tagWCN_ATTRIBUTE_TYPE
0x180017740  lea     rcx, [rbp+0B0h+var_80]; this
0x180017744  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x180017749  mov     ebx, eax
0x18001774b  test    eax, eax
0x18001774d  jns     short loc_18001778D
0x18001774f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017756  lea     rsi, WPP_GLOBAL_Control
0x18001775d  cmp     rcx, rsi
0x180017760  jz      loc_1800179D0
0x180017766  cmp     byte ptr [rcx+19h], 2
0x18001776a  jb      loc_1800179D0
0x180017770  mov     edx, 40h ; '@'
0x180017775  mov     r9d, eax
0x180017778  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001777f  mov     rcx, [rcx+10h]
0x180017783  call    WPP_SF_d
0x180017788  jmp     loc_1800179D0
0x18001778d  lea     rdx, [rbp+0B0h+var_80]; struct CWcnAttribute *
0x180017791  mov     rcx, rsi; this
0x180017794  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x180017799  mov     ebx, eax
0x18001779b  test    eax, eax
0x18001779d  jns     short loc_1800177C7
0x18001779f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177a6  lea     rsi, WPP_GLOBAL_Control
0x1800177ad  cmp     rcx, rsi
0x1800177b0  jz      loc_1800179D0
0x1800177b6  cmp     byte ptr [rcx+19h], 2
0x1800177ba  jb      loc_1800179D0
0x1800177c0  mov     edx, 41h ; 'A'
0x1800177c5  jmp     short loc_180017775
0x1800177c7  mov     r8d, r15d; unsigned int
0x1800177ca  mov     edx, 2; enum tagWCN_ATTRIBUTE_TYPE
0x1800177cf  lea     rcx, [rbp+0B0h+var_C0]; this
0x1800177d3  call    ?SetValueFromInteger@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@I@Z; CWcnAttribute::SetValueFromInteger(tagWCN_ATTRIBUTE_TYPE,uint)
0x1800177d8  mov     ebx, eax
0x1800177da  test    eax, eax
0x1800177dc  jns     short loc_180017809
0x1800177de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177e5  lea     rsi, WPP_GLOBAL_Control
0x1800177ec  cmp     rcx, rsi
0x1800177ef  jz      loc_1800179D0
0x1800177f5  cmp     byte ptr [rcx+19h], 2
0x1800177f9  jb      loc_1800179D0
0x1800177ff  mov     edx, 42h ; 'B'
0x180017804  jmp     loc_180017775
0x180017809  lea     rdx, [rbp+0B0h+var_C0]; struct CWcnAttribute *
0x18001780d  mov     rcx, rsi; this
0x180017810  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x180017815  mov     ebx, eax
0x180017817  test    eax, eax
0x180017819  jns     short loc_180017846
0x18001781b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017822  lea     rsi, WPP_GLOBAL_Control
0x180017829  cmp     rcx, rsi
0x18001782c  jz      loc_1800179D0
0x180017832  cmp     byte ptr [rcx+19h], 2
0x180017836  jb      loc_1800179D0
0x18001783c  mov     edx, 43h ; 'C'
0x180017841  jmp     loc_180017775
0x180017846  mov     r8d, r12d; unsigned int
0x180017849  mov     edx, 13h; enum tagWCN_ATTRIBUTE_TYPE
0x18001784e  lea     rcx, [rbp+0B0h+var_100]; this
0x180017852  call    ?SetValueFromInteger@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@I@Z; CWcnAttribute::SetValueFromInteger(tagWCN_ATTRIBUTE_TYPE,uint)
0x180017857  mov     ebx, eax
0x180017859  test    eax, eax
0x18001785b  jns     short loc_180017888
0x18001785d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017864  lea     rsi, WPP_GLOBAL_Control
0x18001786b  cmp     rcx, rsi
0x18001786e  jz      loc_1800179D0
0x180017874  cmp     byte ptr [rcx+19h], 2
0x180017878  jb      loc_1800179D0
0x18001787e  mov     edx, 44h ; 'D'
0x180017883  jmp     loc_180017775
0x180017888  lea     rdx, [rbp+0B0h+var_100]; struct CWcnAttribute *
0x18001788c  mov     rcx, rsi; this
0x18001788f  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x180017894  mov     ebx, eax
0x180017896  test    eax, eax
0x180017898  jns     short loc_1800178C5
0x18001789a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178a1  lea     rsi, WPP_GLOBAL_Control
0x1800178a8  cmp     rcx, rsi
0x1800178ab  jz      loc_1800179D0
0x1800178b1  cmp     byte ptr [rcx+19h], 2
0x1800178b5  jb      loc_1800179D0
0x1800178bb  mov     edx, 45h ; 'E'
0x1800178c0  jmp     loc_180017775
0x1800178c5  mov     r15d, 1
0x1800178cb  mov     r8d, r15d; unsigned int
0x1800178ce  lea     edx, [r15+1Fh]; enum tagWCN_ATTRIBUTE_TYPE
0x1800178d2  lea     rcx, [rsp+1B0h+var_140]; this
0x1800178d7  call    ?SetValueFromInteger@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@I@Z; CWcnAttribute::SetValueFromInteger(tagWCN_ATTRIBUTE_TYPE,uint)
0x1800178dc  mov     ebx, eax
0x1800178de  test    eax, eax
0x1800178e0  jns     short loc_18001790C
0x1800178e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178e9  lea     rsi, WPP_GLOBAL_Control
0x1800178f0  cmp     rcx, rsi
0x1800178f3  jz      loc_1800179D0
0x1800178f9  cmp     byte ptr [rcx+19h], 2
0x1800178fd  jb      loc_1800179D0
0x180017903  lea     edx, [r15+45h]
0x180017907  jmp     loc_180017775
0x18001790c  lea     rdx, [rsp+1B0h+var_140]; struct CWcnAttribute *
0x180017911  mov     rcx, rsi; this
0x180017914  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x180017919  mov     ebx, eax
0x18001791b  test    eax, eax
0x18001791d  jns     short loc_18001794A
0x18001791f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017926  lea     rsi, WPP_GLOBAL_Control
0x18001792d  cmp     rcx, rsi
0x180017930  jz      loc_1800179D0
0x180017936  cmp     byte ptr [rcx+19h], 2
0x18001793a  jb      loc_1800179D0
0x180017940  mov     edx, 47h ; 'G'
0x180017945  jmp     loc_180017775
0x18001794a  mov     r8d, r15d; unsigned int
0x18001794d  mov     edx, 22h ; '"'; enum tagWCN_ATTRIBUTE_TYPE
0x180017952  lea     rcx, [rsp+1B0h+var_180]; this
0x180017957  call    ?SetValueFromInteger@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@I@Z; CWcnAttribute::SetValueFromInteger(tagWCN_ATTRIBUTE_TYPE,uint)
0x18001795c  mov     ebx, eax
0x18001795e  test    eax, eax
0x180017960  jns     short loc_180017985
0x180017962  mov     rcx, cs:WPP_GLOBAL_Control
0x180017969  lea     rsi, WPP_GLOBAL_Control
0x180017970  cmp     rcx, rsi
0x180017973  jz      short loc_1800179D0
0x180017975  cmp     byte ptr [rcx+19h], 2
0x180017979  jb      short loc_1800179D0
0x18001797b  mov     edx, 48h ; 'H'
0x180017980  jmp     loc_180017775
0x180017985  lea     rdx, [rsp+1B0h+var_180]; struct CWcnAttribute *
0x18001798a  mov     rcx, rsi; this
0x18001798d  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x180017992  mov     ebx, eax
0x180017994  test    eax, eax
0x180017996  jns     short loc_1800179BB
0x180017998  mov     rcx, cs:WPP_GLOBAL_Control
0x18001799f  lea     rsi, WPP_GLOBAL_Control
0x1800179a6  cmp     rcx, rsi
0x1800179a9  jz      short loc_1800179D0
0x1800179ab  cmp     byte ptr [rcx+19h], 2
0x1800179af  jb      short loc_1800179D0
0x1800179b1  mov     edx, 49h ; 'I'
0x1800179b6  jmp     loc_180017775
0x1800179bb  mov     [r14+1B0h], r15b
0x1800179c2  mov     [r14+5C8h], r15b
0x1800179c9  lea     rsi, WPP_GLOBAL_Control
0x1800179d0  lea     rcx, [r14+48h]; SRWLock
0x1800179d4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800179da  mov     r10, cs:WPP_GLOBAL_Control
0x1800179e1  cmp     r10, rsi
0x1800179e4  jz      short loc_180017A16
0x1800179e6  test    ebx, ebx
0x1800179e8  js      short loc_1800179F1
0x1800179ea  cmp     byte ptr [r10+19h], 6
0x1800179ef  jb      short loc_180017A16
0x1800179f1  or      ecx, 0FFFFFFFFh; int
0x1800179f4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800179f9  mov     edx, 4Ah ; 'J'
0x1800179fe  mov     [rsp+1B0h+var_190], ebx
0x180017a02  mov     r9, rax
0x180017a05  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180017a0c  mov     rcx, [r10+10h]
0x180017a10  call    WPP_SF_sd
0x180017a15  nop
0x180017a16  lea     rcx, [rsp+1B0h+var_168]; this
0x180017a1b  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180017a20  nop
0x180017a21  lea     rcx, [rbp+0B0h+var_128]; this
0x180017a25  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180017a2a  nop
0x180017a2b  lea     rcx, [rbp+0B0h+var_E8]; this
0x180017a2f  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180017a34  nop
0x180017a35  lea     rcx, [rbp+0B0h+var_A8]; this
0x180017a39  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180017a3e  nop
0x180017a3f  lea     rcx, [rbp+0B0h+var_68]; this
0x180017a43  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180017a48  mov     eax, ebx
0x180017a4a  mov     rcx, [rbp+0B0h+var_40]
0x180017a4e  xor     rcx, rsp; StackCookie
0x180017a51  call    __security_check_cookie
0x180017a56  add     rsp, 180h
0x180017a5d  pop     r15
0x180017a5f  pop     r14
0x180017a61  pop     r13
0x180017a63  pop     r12
0x180017a65  pop     rsi
0x180017a66  pop     rbx
0x180017a67  pop     rbp
0x180017a68  retn
```
