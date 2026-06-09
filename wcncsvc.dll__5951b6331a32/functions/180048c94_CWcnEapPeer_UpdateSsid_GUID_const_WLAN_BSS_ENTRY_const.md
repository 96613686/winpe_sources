# CWcnEapPeer::UpdateSsid(_GUID const *,_WLAN_BSS_ENTRY const *)

- ea: `0x180048c94`
- end: `0x180048ffe`
- name: `?UpdateSsid@CWcnEapPeer@@QEAAJPEBU_GUID@@PEBU_WLAN_BSS_ENTRY@@@Z`
- size: `874`
- prototype: `__int64 __fastcall(CWcnEapPeer *__hidden this, const struct _GUID *, const struct _WLAN_BSS_ENTRY *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800460f4`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a6d4`
- `0x18000c7f8`
- `0x18001a57c`
- `0x18001b548`
- `0x18001cdd0`
- `0x18001d1e8`
- `0x180048c94`
- `0x180053004`
- `0x180056de6`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048f30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048f3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048f30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048f3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048dab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048dab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWcnEapPeer::UpdateSsid(CWcnEapPeer *this, const struct _GUID *a2, const struct _WLAN_BSS_ENTRY *a3)
{
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  int v9; // ebx
  RTL_SRWLOCK *v10; // r15
  int appended; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // r10
  _BYTE v17[32]; // [rsp+30h] [rbp-A9h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v19[24]; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v20[40]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v21[24]; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v22[40]; // [rsp+C8h] [rbp-11h] BYREF

  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v18);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v21);
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v17);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v19);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 12, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_s(v6[2], 13, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids, "pBssEntry");
    v9 = -2147467261;
    goto LABEL_44;
  }
  *(struct _GUID *)((char *)this + 72) = *a2;
  if ( a3->dot11Ssid.uSSIDLength != *((_DWORD *)this + 8)
    || (v9 = 0, memcmp_0(a3->dot11Ssid.ucSSID, (char *)this + 36, a3->dot11Ssid.uSSIDLength)) )
  {
    v10 = (RTL_SRWLOCK *)*((_QWORD *)this + 2);
    *((_DWORD *)this + 6) = *(_DWORD *)a3->dot11Bssid;
    *((_WORD *)this + 14) = *(_WORD *)&a3->dot11Bssid[4];
    AcquireSRWLockExclusive(v10 + 21);
    appended = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v18, a3->dot11Ssid.ucSSID, a3->dot11Ssid.uSSIDLength);
    v9 = appended;
    if ( appended >= 0 )
    {
      appended = CWcnAttribute::SetValueFromBlob(
                   (CWcnAttribute *)v21,
                   WCN_TYPE_CURRENT_SSID,
                   (const struct CSbSafeBuffer *)v18);
      v9 = appended;
      if ( appended >= 0 )
      {
        appended = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v17, (const unsigned __int8 *)this + 24, 6u);
        v9 = appended;
        if ( appended >= 0 )
        {
          appended = CWcnAttribute::SetValueFromBlob(
                       (CWcnAttribute *)v19,
                       WCN_TYPE_BSSID,
                       (const struct CSbSafeBuffer *)v17);
          v9 = appended;
          if ( appended >= 0 )
          {
            CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&v10[22], WCN_TYPE_CURRENT_SSID);
            CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&v10[22], WCN_TYPE_BSSID);
            appended = CWcnAttributeDatabase::AppendAttribute(
                         (CWcnAttributeDatabase *)&v10[22],
                         (const struct CWcnAttribute *)v21);
            v9 = appended;
            if ( appended >= 0 )
            {
              appended = CWcnAttributeDatabase::AppendAttribute(
                           (CWcnAttributeDatabase *)&v10[22],
                           (const struct CWcnAttribute *)v19);
              v9 = appended;
              if ( appended >= 0 )
              {
                ReleaseSRWLockExclusive(v10 + 21);
                *((_OWORD *)this + 2) = *(_OWORD *)&a3->dot11Ssid.uSSIDLength;
                *((_OWORD *)this + 3) = *(_OWORD *)&a3->dot11Ssid.ucSSID[12];
                *((_DWORD *)this + 16) = *(_DWORD *)&a3->dot11Ssid.ucSSID[28];
                if ( *((_BYTE *)this + 68) )
                  CWcnIdentity::SetDataIsStale((CWcnIdentity *)&v10[17]);
                *((_BYTE *)this + 68) = 1;
                goto LABEL_40;
              }
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_36;
              v13 = 19;
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_36;
              v13 = 18;
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_36;
            v13 = 17;
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_36;
          v13 = 16;
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_36;
        v13 = 15;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_36;
      v13 = 14;
    }
    WPP_SF_d(v12[2], v13, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids, (unsigned int)appended);
LABEL_36:
    ReleaseSRWLockExclusive(v10 + 21);
  }
LABEL_40:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v9 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v14 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v15 + 16), 20, (unsigned int)WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids, v14, v9);
  }
LABEL_44:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v20);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v17);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v22);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180048c94  mov     [rsp-8+arg_8], rbx
0x180048c99  push    rbp
0x180048c9a  push    rsi
0x180048c9b  push    rdi
0x180048c9c  push    r12
0x180048c9e  push    r13
0x180048ca0  push    r14
0x180048ca2  push    r15
0x180048ca4  lea     rbp, [rsp-27h]
0x180048ca9  sub     rsp, 100h
0x180048cb0  mov     rax, cs:__security_cookie
0x180048cb7  xor     rax, rsp
0x180048cba  mov     [rbp+57h+var_40], rax
0x180048cbe  mov     rsi, r8
0x180048cc1  mov     rbx, rdx
0x180048cc4  mov     rdi, rcx
0x180048cc7  lea     rcx, [rsp+130h+var_E0]; this
0x180048ccc  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x180048cd1  nop
0x180048cd2  lea     rcx, [rbp+57h+var_80]; this
0x180048cd6  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x180048cdb  nop
0x180048cdc  lea     rcx, [rsp+130h+var_100]; this
0x180048ce1  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x180048ce6  nop
0x180048ce7  lea     rcx, [rbp+57h+var_C0]; this
0x180048ceb  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x180048cf0  nop
0x180048cf1  lea     r13, WPP_GLOBAL_Control
0x180048cf8  mov     r10, cs:WPP_GLOBAL_Control
0x180048cff  cmp     r10, r13
0x180048d02  jz      short loc_180048D34
0x180048d04  cmp     byte ptr [r10+19h], 6
0x180048d09  jb      short loc_180048D34
0x180048d0b  mov     ecx, 1; int
0x180048d10  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180048d15  mov     edx, 0Ch
0x180048d1a  mov     r9, rax
0x180048d1d  lea     r8, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids
0x180048d24  mov     rcx, [r10+10h]
0x180048d28  call    WPP_SF_s
0x180048d2d  mov     r10, cs:WPP_GLOBAL_Control
0x180048d34  test    rsi, rsi
0x180048d37  jnz     short loc_180048D69
0x180048d39  cmp     r10, r13
0x180048d3c  jz      short loc_180048D5F
0x180048d3e  cmp     byte ptr [r10+19h], 2
0x180048d43  jb      short loc_180048D5F
0x180048d45  lea     edx, [rsi+0Dh]
0x180048d48  lea     r9, aPbssentry; "pBssEntry"
0x180048d4f  lea     r8, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids
0x180048d56  mov     rcx, [r10+10h]
0x180048d5a  call    WPP_SF_s
0x180048d5f  mov     ebx, 80004003h
0x180048d64  jmp     loc_180048FAC
0x180048d69  movups  xmm0, xmmword ptr [rbx]
0x180048d6c  movdqu  xmmword ptr [rdi+48h], xmm0
0x180048d71  mov     eax, [rsi]
0x180048d73  cmp     eax, [rdi+20h]
0x180048d76  jnz     short loc_180048D92
0x180048d78  xor     ebx, ebx
0x180048d7a  mov     r8d, eax; Size
0x180048d7d  lea     rdx, [rdi+24h]; Buf2
0x180048d81  lea     rcx, [rsi+4]; Buf1
0x180048d85  call    memcmp_0
0x180048d8a  test    eax, eax
0x180048d8c  jz      loc_180048F70
0x180048d92  mov     r15, [rdi+10h]
0x180048d96  mov     eax, [rsi+28h]
0x180048d99  mov     [rdi+18h], eax
0x180048d9c  movzx   eax, word ptr [rsi+2Ch]
0x180048da0  mov     [rdi+1Ch], ax
0x180048da4  lea     rcx, [r15+0A8h]; SRWLock
0x180048dab  call    cs:__imp_AcquireSRWLockExclusive
0x180048db1  mov     r8d, [rsi]; unsigned __int64
0x180048db4  lea     rdx, [rsi+4]; unsigned __int8 *
0x180048db8  lea     rcx, [rsp+130h+var_E0]; this
0x180048dbd  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x180048dc2  mov     ebx, eax
0x180048dc4  test    eax, eax
0x180048dc6  jns     short loc_180048DEC
0x180048dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180048dcf  cmp     rcx, r13
0x180048dd2  jz      loc_180048F29
0x180048dd8  cmp     byte ptr [rcx+19h], 2
0x180048ddc  jb      loc_180048F29
0x180048de2  mov     edx, 0Eh
0x180048de7  jmp     loc_180048F16
0x180048dec  lea     r8, [rsp+130h+var_E0]; struct CSbSafeBuffer *
0x180048df1  mov     edx, 5Ah ; 'Z'; enum tagWCN_ATTRIBUTE_TYPE
0x180048df6  lea     rcx, [rbp+57h+var_80]; this
0x180048dfa  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x180048dff  mov     ebx, eax
0x180048e01  test    eax, eax
0x180048e03  jns     short loc_180048E29
0x180048e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e0c  cmp     rcx, r13
0x180048e0f  jz      loc_180048F29
0x180048e15  cmp     byte ptr [rcx+19h], 2
0x180048e19  jb      loc_180048F29
0x180048e1f  mov     edx, 0Fh
0x180048e24  jmp     loc_180048F16
0x180048e29  mov     r8d, 6; unsigned __int64
0x180048e2f  lea     rdx, [rdi+18h]; unsigned __int8 *
0x180048e33  lea     rcx, [rsp+130h+var_100]; this
0x180048e38  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x180048e3d  mov     ebx, eax
0x180048e3f  test    eax, eax
0x180048e41  jns     short loc_180048E67
0x180048e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e4a  cmp     rcx, r13
0x180048e4d  jz      loc_180048F29
0x180048e53  cmp     byte ptr [rcx+19h], 2
0x180048e57  jb      loc_180048F29
0x180048e5d  mov     edx, 10h
0x180048e62  jmp     loc_180048F16
0x180048e67  lea     r8, [rsp+130h+var_100]; struct CSbSafeBuffer *
0x180048e6c  mov     edx, 5Bh ; '['; enum tagWCN_ATTRIBUTE_TYPE
0x180048e71  lea     rcx, [rbp+57h+var_C0]; this
0x180048e75  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x180048e7a  mov     ebx, eax
0x180048e7c  test    eax, eax
0x180048e7e  jns     short loc_180048EA1
0x180048e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e87  cmp     rcx, r13
0x180048e8a  jz      loc_180048F29
0x180048e90  cmp     byte ptr [rcx+19h], 2
0x180048e94  jb      loc_180048F29
0x180048e9a  mov     edx, 11h
0x180048e9f  jmp     short loc_180048F16
0x180048ea1  lea     r14, [r15+0B0h]
0x180048ea8  mov     edx, 5Ah ; 'Z'; enum tagWCN_ATTRIBUTE_TYPE
0x180048ead  mov     rcx, r14; this
0x180048eb0  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x180048eb5  mov     edx, 5Bh ; '['; enum tagWCN_ATTRIBUTE_TYPE
0x180048eba  mov     rcx, r14; this
0x180048ebd  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x180048ec2  lea     rdx, [rbp+57h+var_80]; struct CWcnAttribute *
0x180048ec6  mov     rcx, r14; this
0x180048ec9  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x180048ece  mov     ebx, eax
0x180048ed0  test    eax, eax
0x180048ed2  jns     short loc_180048EED
0x180048ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180048edb  cmp     rcx, r13
0x180048ede  jz      short loc_180048F29
0x180048ee0  cmp     byte ptr [rcx+19h], 2
0x180048ee4  jb      short loc_180048F29
0x180048ee6  mov     edx, 12h
0x180048eeb  jmp     short loc_180048F16
0x180048eed  lea     rdx, [rbp+57h+var_C0]; struct CWcnAttribute *
0x180048ef1  mov     rcx, r14; this
0x180048ef4  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x180048ef9  mov     ebx, eax
0x180048efb  test    eax, eax
0x180048efd  jns     short loc_180048F38
0x180048eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180048f06  cmp     rcx, r13
0x180048f09  jz      short loc_180048F29
0x180048f0b  cmp     byte ptr [rcx+19h], 2
0x180048f0f  jb      short loc_180048F29
0x180048f11  mov     edx, 13h
0x180048f16  mov     r9d, eax
0x180048f19  lea     r8, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids
0x180048f20  mov     rcx, [rcx+10h]
0x180048f24  call    WPP_SF_d
0x180048f29  lea     rcx, [r15+0A8h]; SRWLock
0x180048f30  call    cs:__imp_ReleaseSRWLockExclusive
0x180048f36  jmp     short loc_180048F70
0x180048f38  lea     rcx, [r15+0A8h]; SRWLock
0x180048f3f  call    cs:__imp_ReleaseSRWLockExclusive
0x180048f45  movups  xmm0, xmmword ptr [rsi]
0x180048f48  movups  xmmword ptr [rdi+20h], xmm0
0x180048f4c  movups  xmm1, xmmword ptr [rsi+10h]
0x180048f50  movups  xmmword ptr [rdi+30h], xmm1
0x180048f54  mov     eax, [rsi+20h]
0x180048f57  mov     [rdi+40h], eax
0x180048f5a  cmp     byte ptr [rdi+44h], 0
0x180048f5e  jz      short loc_180048F6C
0x180048f60  lea     rcx, [r15+88h]; this
0x180048f67  call    ?SetDataIsStale@CWcnIdentity@@QEAAXXZ; CWcnIdentity::SetDataIsStale(void)
0x180048f6c  mov     byte ptr [rdi+44h], 1
0x180048f70  mov     r10, cs:WPP_GLOBAL_Control
0x180048f77  cmp     r10, r13
0x180048f7a  jz      short loc_180048FAC
0x180048f7c  test    ebx, ebx
0x180048f7e  js      short loc_180048F87
0x180048f80  cmp     byte ptr [r10+19h], 6
0x180048f85  jb      short loc_180048FAC
0x180048f87  or      ecx, 0FFFFFFFFh; int
0x180048f8a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180048f8f  mov     edx, 14h
0x180048f94  mov     [rsp+130h+var_110], ebx
0x180048f98  mov     r9, rax
0x180048f9b  lea     r8, WPP_368e40a8c2c73a9a7c2b683299c48cf7_Traceguids
0x180048fa2  mov     rcx, [r10+10h]
0x180048fa6  call    WPP_SF_sd
0x180048fab  nop
0x180048fac  lea     rcx, [rbp+57h+var_A8]; this
0x180048fb0  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180048fb5  nop
0x180048fb6  lea     rcx, [rsp+130h+var_100]; this
0x180048fbb  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180048fc0  nop
0x180048fc1  lea     rcx, [rbp+57h+var_68]; this
0x180048fc5  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180048fca  nop
0x180048fcb  lea     rcx, [rsp+130h+var_E0]; this
0x180048fd0  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180048fd5  mov     eax, ebx
0x180048fd7  mov     rcx, [rbp+57h+var_40]
0x180048fdb  xor     rcx, rsp; StackCookie
0x180048fde  call    __security_check_cookie
0x180048fe3  mov     rbx, [rsp+130h+arg_8]
0x180048feb  add     rsp, 100h
0x180048ff2  pop     r15
0x180048ff4  pop     r14
0x180048ff6  pop     r13
0x180048ff8  pop     r12
0x180048ffa  pop     rdi
0x180048ffb  pop     rsi
0x180048ffc  pop     rbp
0x180048ffd  retn
```
