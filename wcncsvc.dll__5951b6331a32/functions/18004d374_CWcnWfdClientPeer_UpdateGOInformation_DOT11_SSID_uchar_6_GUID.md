# CWcnWfdClientPeer::UpdateGOInformation(_DOT11_SSID *,uchar (*)[6],_GUID *)

- ea: `0x18004d374`
- end: `0x18004d683`
- name: `?UpdateGOInformation@CWcnWfdClientPeer@@QEAAJPEAU_DOT11_SSID@@PEAY05EPEAU_GUID@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(CWcnWfdClientPeer *__hidden this, struct _DOT11_SSID *, unsigned __int8 (*)[6], struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18004b36c`

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
- `0x18004d374`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d435`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d435`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWcnWfdClientPeer::UpdateGOInformation(
        CWcnWfdClientPeer *this,
        struct _DOT11_SSID *a2,
        unsigned __int8 (*a3)[6],
        struct _GUID *a4)
{
  const char *Indent; // rax
  __int64 v9; // r10
  RTL_SRWLOCK *v10; // r15
  int appended; // eax
  int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r10
  _BYTE v18[32]; // [rsp+30h] [rbp-A9h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v20[24]; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v21[40]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v22[24]; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v23[40]; // [rsp+C8h] [rbp-11h] BYREF

  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v19);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v22);
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v18);
  CWcnAttribute::CWcnAttribute((CWcnAttribute *)v20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 12, WPP_d9093cb2dd693b4c537613c4eb2da927_Traceguids, Indent);
  }
  v10 = (RTL_SRWLOCK *)*((_QWORD *)this + 2);
  *((_DWORD *)this + 6) = *(_DWORD *)a3;
  *((_WORD *)this + 14) = *(_WORD *)&(*a3)[4];
  *(struct _GUID *)((char *)this + 72) = *a4;
  AcquireSRWLockExclusive(v10 + 21);
  appended = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v19, a2->ucSSID, a2->uSSIDLength);
  v12 = appended;
  if ( appended < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_29;
    v14 = 13;
LABEL_28:
    WPP_SF_d(v13[2], v14, WPP_d9093cb2dd693b4c537613c4eb2da927_Traceguids, (unsigned int)appended);
LABEL_29:
    ReleaseSRWLockExclusive(v10 + 21);
    goto LABEL_33;
  }
  appended = CWcnAttribute::SetValueFromBlob(
               (CWcnAttribute *)v22,
               WCN_TYPE_CURRENT_SSID,
               (const struct CSbSafeBuffer *)v19);
  v12 = appended;
  if ( appended < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_29;
    v14 = 14;
    goto LABEL_28;
  }
  appended = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)v18, (const unsigned __int8 *)this + 24, 6u);
  v12 = appended;
  if ( appended < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_29;
    v14 = 15;
    goto LABEL_28;
  }
  appended = CWcnAttribute::SetValueFromBlob((CWcnAttribute *)v20, WCN_TYPE_BSSID, (const struct CSbSafeBuffer *)v18);
  v12 = appended;
  if ( appended < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_29;
    v14 = 16;
    goto LABEL_28;
  }
  CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&v10[22], WCN_TYPE_CURRENT_SSID);
  CWcnAttributeDatabase::RemoveAllOfAttribute((CWcnAttributeDatabase *)&v10[22], WCN_TYPE_BSSID);
  appended = CWcnAttributeDatabase::AppendAttribute(
               (CWcnAttributeDatabase *)&v10[22],
               (const struct CWcnAttribute *)v22);
  v12 = appended;
  if ( appended < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_29;
    v14 = 17;
    goto LABEL_28;
  }
  appended = CWcnAttributeDatabase::AppendAttribute(
               (CWcnAttributeDatabase *)&v10[22],
               (const struct CWcnAttribute *)v20);
  v12 = appended;
  if ( appended < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_29;
    v14 = 18;
    goto LABEL_28;
  }
  ReleaseSRWLockExclusive(v10 + 21);
  *((_OWORD *)this + 2) = *(_OWORD *)&a2->uSSIDLength;
  *((_OWORD *)this + 3) = *(_OWORD *)&a2->ucSSID[12];
  *((_DWORD *)this + 16) = *(_DWORD *)&a2->ucSSID[28];
  if ( *((_BYTE *)this + 68) )
    CWcnIdentity::SetDataIsStale((CWcnIdentity *)&v10[17]);
  *((_BYTE *)this + 68) = 1;
LABEL_33:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v12 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v15 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v16 + 16), 19, (unsigned int)WPP_d9093cb2dd693b4c537613c4eb2da927_Traceguids, v15, v12);
  }
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v21);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v18);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v23);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004d374  mov     [rsp-8+arg_10], rbx
0x18004d379  push    rbp
0x18004d37a  push    rsi
0x18004d37b  push    rdi
0x18004d37c  push    r12
0x18004d37e  push    r13
0x18004d380  push    r14
0x18004d382  push    r15
0x18004d384  lea     rbp, [rsp-27h]
0x18004d389  sub     rsp, 100h
0x18004d390  mov     rax, cs:__security_cookie
0x18004d397  xor     rax, rsp
0x18004d39a  mov     [rbp+57h+var_40], rax
0x18004d39e  mov     r12, r9
0x18004d3a1  mov     rbx, r8
0x18004d3a4  mov     r14, rdx
0x18004d3a7  mov     rdi, rcx
0x18004d3aa  lea     rcx, [rsp+130h+var_E0]; this
0x18004d3af  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004d3b4  nop
0x18004d3b5  lea     rcx, [rbp+57h+var_80]; this
0x18004d3b9  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18004d3be  nop
0x18004d3bf  lea     rcx, [rsp+130h+var_100]; this
0x18004d3c4  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004d3c9  nop
0x18004d3ca  lea     rcx, [rbp+57h+var_C0]; this
0x18004d3ce  call    ??0CWcnAttribute@@QEAA@XZ; CWcnAttribute::CWcnAttribute(void)
0x18004d3d3  nop
0x18004d3d4  lea     r13, WPP_GLOBAL_Control
0x18004d3db  mov     r10, cs:WPP_GLOBAL_Control
0x18004d3e2  cmp     r10, r13
0x18004d3e5  jz      short loc_18004D410
0x18004d3e7  cmp     byte ptr [r10+19h], 6
0x18004d3ec  jb      short loc_18004D410
0x18004d3ee  mov     ecx, 1; int
0x18004d3f3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004d3f8  mov     edx, 0Ch
0x18004d3fd  mov     r9, rax
0x18004d400  lea     r8, WPP_d9093cb2dd693b4c537613c4eb2da927_Traceguids
0x18004d407  mov     rcx, [r10+10h]
0x18004d40b  call    WPP_SF_s
0x18004d410  mov     r15, [rdi+10h]
0x18004d414  mov     eax, [rbx]
0x18004d416  mov     [rdi+18h], eax
0x18004d419  movzx   eax, word ptr [rbx+4]
0x18004d41d  mov     [rdi+1Ch], ax
0x18004d421  movups  xmm0, xmmword ptr [r12]
0x18004d426  movdqu  xmmword ptr [rdi+48h], xmm0
0x18004d42b  lea     r12, [r15+0A8h]
0x18004d432  mov     rcx, r12; SRWLock
0x18004d435  call    cs:__imp_AcquireSRWLockExclusive
0x18004d43b  mov     r8d, [r14]; unsigned __int64
0x18004d43e  lea     rdx, [r14+4]; unsigned __int8 *
0x18004d442  lea     rcx, [rsp+130h+var_E0]; this
0x18004d447  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x18004d44c  mov     ebx, eax
0x18004d44e  test    eax, eax
0x18004d450  jns     short loc_18004D476
0x18004d452  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d459  cmp     rcx, r13
0x18004d45c  jz      loc_18004D5B3
0x18004d462  cmp     byte ptr [rcx+19h], 2
0x18004d466  jb      loc_18004D5B3
0x18004d46c  mov     edx, 0Dh
0x18004d471  jmp     loc_18004D5A0
0x18004d476  lea     r8, [rsp+130h+var_E0]; struct CSbSafeBuffer *
0x18004d47b  mov     edx, 5Ah ; 'Z'; enum tagWCN_ATTRIBUTE_TYPE
0x18004d480  lea     rcx, [rbp+57h+var_80]; this
0x18004d484  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x18004d489  mov     ebx, eax
0x18004d48b  test    eax, eax
0x18004d48d  jns     short loc_18004D4B3
0x18004d48f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d496  cmp     rcx, r13
0x18004d499  jz      loc_18004D5B3
0x18004d49f  cmp     byte ptr [rcx+19h], 2
0x18004d4a3  jb      loc_18004D5B3
0x18004d4a9  mov     edx, 0Eh
0x18004d4ae  jmp     loc_18004D5A0
0x18004d4b3  mov     r8d, 6; unsigned __int64
0x18004d4b9  lea     rdx, [rdi+18h]; unsigned __int8 *
0x18004d4bd  lea     rcx, [rsp+130h+var_100]; this
0x18004d4c2  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x18004d4c7  mov     ebx, eax
0x18004d4c9  test    eax, eax
0x18004d4cb  jns     short loc_18004D4F1
0x18004d4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d4d4  cmp     rcx, r13
0x18004d4d7  jz      loc_18004D5B3
0x18004d4dd  cmp     byte ptr [rcx+19h], 2
0x18004d4e1  jb      loc_18004D5B3
0x18004d4e7  mov     edx, 0Fh
0x18004d4ec  jmp     loc_18004D5A0
0x18004d4f1  lea     r8, [rsp+130h+var_100]; struct CSbSafeBuffer *
0x18004d4f6  mov     edx, 5Bh ; '['; enum tagWCN_ATTRIBUTE_TYPE
0x18004d4fb  lea     rcx, [rbp+57h+var_C0]; this
0x18004d4ff  call    ?SetValueFromBlob@CWcnAttribute@@QEAAJW4tagWCN_ATTRIBUTE_TYPE@@PEBVCSbSafeBuffer@@@Z; CWcnAttribute::SetValueFromBlob(tagWCN_ATTRIBUTE_TYPE,CSbSafeBuffer const *)
0x18004d504  mov     ebx, eax
0x18004d506  test    eax, eax
0x18004d508  jns     short loc_18004D52B
0x18004d50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d511  cmp     rcx, r13
0x18004d514  jz      loc_18004D5B3
0x18004d51a  cmp     byte ptr [rcx+19h], 2
0x18004d51e  jb      loc_18004D5B3
0x18004d524  mov     edx, 10h
0x18004d529  jmp     short loc_18004D5A0
0x18004d52b  lea     rsi, [r15+0B0h]
0x18004d532  mov     edx, 5Ah ; 'Z'; enum tagWCN_ATTRIBUTE_TYPE
0x18004d537  mov     rcx, rsi; this
0x18004d53a  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x18004d53f  mov     edx, 5Bh ; '['; enum tagWCN_ATTRIBUTE_TYPE
0x18004d544  mov     rcx, rsi; this
0x18004d547  call    ?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z; CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)
0x18004d54c  lea     rdx, [rbp+57h+var_80]; struct CWcnAttribute *
0x18004d550  mov     rcx, rsi; this
0x18004d553  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x18004d558  mov     ebx, eax
0x18004d55a  test    eax, eax
0x18004d55c  jns     short loc_18004D577
0x18004d55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d565  cmp     rcx, r13
0x18004d568  jz      short loc_18004D5B3
0x18004d56a  cmp     byte ptr [rcx+19h], 2
0x18004d56e  jb      short loc_18004D5B3
0x18004d570  mov     edx, 11h
0x18004d575  jmp     short loc_18004D5A0
0x18004d577  lea     rdx, [rbp+57h+var_C0]; struct CWcnAttribute *
0x18004d57b  mov     rcx, rsi; this
0x18004d57e  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x18004d583  mov     ebx, eax
0x18004d585  test    eax, eax
0x18004d587  jns     short loc_18004D5BE
0x18004d589  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d590  cmp     rcx, r13
0x18004d593  jz      short loc_18004D5B3
0x18004d595  cmp     byte ptr [rcx+19h], 2
0x18004d599  jb      short loc_18004D5B3
0x18004d59b  mov     edx, 12h
0x18004d5a0  mov     r9d, eax
0x18004d5a3  lea     r8, WPP_d9093cb2dd693b4c537613c4eb2da927_Traceguids
0x18004d5aa  mov     rcx, [rcx+10h]
0x18004d5ae  call    WPP_SF_d
0x18004d5b3  mov     rcx, r12; SRWLock
0x18004d5b6  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d5bc  jmp     short loc_18004D5F5
0x18004d5be  mov     rcx, r12; SRWLock
0x18004d5c1  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d5c7  movups  xmm0, xmmword ptr [r14]
0x18004d5cb  movups  xmmword ptr [rdi+20h], xmm0
0x18004d5cf  movups  xmm1, xmmword ptr [r14+10h]
0x18004d5d4  movups  xmmword ptr [rdi+30h], xmm1
0x18004d5d8  mov     eax, [r14+20h]
0x18004d5dc  mov     [rdi+40h], eax
0x18004d5df  cmp     byte ptr [rdi+44h], 0
0x18004d5e3  jz      short loc_18004D5F1
0x18004d5e5  lea     rcx, [r15+88h]; this
0x18004d5ec  call    ?SetDataIsStale@CWcnIdentity@@QEAAXXZ; CWcnIdentity::SetDataIsStale(void)
0x18004d5f1  mov     byte ptr [rdi+44h], 1
0x18004d5f5  mov     r10, cs:WPP_GLOBAL_Control
0x18004d5fc  cmp     r10, r13
0x18004d5ff  jz      short loc_18004D631
0x18004d601  test    ebx, ebx
0x18004d603  js      short loc_18004D60C
0x18004d605  cmp     byte ptr [r10+19h], 6
0x18004d60a  jb      short loc_18004D631
0x18004d60c  or      ecx, 0FFFFFFFFh; int
0x18004d60f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004d614  mov     edx, 13h
0x18004d619  mov     [rsp+130h+var_110], ebx
0x18004d61d  mov     r9, rax
0x18004d620  lea     r8, WPP_d9093cb2dd693b4c537613c4eb2da927_Traceguids
0x18004d627  mov     rcx, [r10+10h]
0x18004d62b  call    WPP_SF_sd
0x18004d630  nop
0x18004d631  lea     rcx, [rbp+57h+var_A8]; this
0x18004d635  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004d63a  nop
0x18004d63b  lea     rcx, [rsp+130h+var_100]; this
0x18004d640  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004d645  nop
0x18004d646  lea     rcx, [rbp+57h+var_68]; this
0x18004d64a  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004d64f  nop
0x18004d650  lea     rcx, [rsp+130h+var_E0]; this
0x18004d655  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004d65a  mov     eax, ebx
0x18004d65c  mov     rcx, [rbp+57h+var_40]
0x18004d660  xor     rcx, rsp; StackCookie
0x18004d663  call    __security_check_cookie
0x18004d668  mov     rbx, [rsp+130h+arg_10]
0x18004d670  add     rsp, 100h
0x18004d677  pop     r15
0x18004d679  pop     r14
0x18004d67b  pop     r13
0x18004d67d  pop     r12
0x18004d67f  pop     rdi
0x18004d680  pop     rsi
0x18004d681  pop     rbp
0x18004d682  retn
```
