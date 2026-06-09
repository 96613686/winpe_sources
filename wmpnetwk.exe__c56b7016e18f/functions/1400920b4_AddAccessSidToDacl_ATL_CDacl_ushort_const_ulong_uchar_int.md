# AddAccessSidToDacl(ATL::CDacl &,ushort const *,ulong,uchar,int &)

- ea: `0x1400920b4`
- end: `0x14009233f`
- name: `?AddAccessSidToDacl@@YAHAEAVCDacl@ATL@@PEBGKEAEAH@Z`
- size: `651`
- prototype: `__int64 __fastcall(struct ATL::CDacl *this, LPCWSTR StringSid, __int64, unsigned __int8, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140093330`
- `0x140093924`

## callees

- `0x14003f17c`
- `0x1400447f0`
- `0x140044884`
- `0x140045f20`
- `0x14004b650`
- `0x140092014`
- `0x1400920b4`
- `0x140092fa0`
- `0x140093c68`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x14009213a`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14009213a`
- `ADVAPI32!EqualSid` at `0x14009224e`
- `ADVAPI32!EqualSid` at `0x14009224e`
- `KERNEL32!LocalFree` at `0x1400921e8`
- `KERNEL32!LocalFree` at `0x1400921e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AddAccessSidToDacl(
        struct ATL::CDacl *this,
        LPCWSTR StringSid,
        __int64 a3,
        unsigned __int8 a4,
        int *a5)
{
  unsigned int v6; // r14d
  unsigned int v9; // edi
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  struct _SID *v12; // rdx
  bool v13; // al
  struct _GUID *v15; // [rsp+30h] [rbp-D0h]
  struct _GUID *v16; // [rsp+38h] [rbp-C8h]
  unsigned __int8 v17; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v18[3]; // [rsp+41h] [rbp-BFh] BYREF
  unsigned int v19; // [rsp+44h] [rbp-BCh] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pSid2[120]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pSid1[120]; // [rsp+D8h] [rbp-28h] BYREF

  v6 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_LD(*((_QWORD *)WPP_GLOBAL_Control + 2), StringSid, a3, (unsigned int)a3, a4);
  }
  v9 = 0;
  Sid = 0;
  ATL::CSid::CSid((ATL::CSid *)v21);
  *a5 = 0;
  v10 = ConvertStringSidToSidW(StringSid, &Sid);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v10);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 == 1 )
  {
    v12 = (struct _SID *)Sid;
    v10 = Sid != 0;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 4u )
    {
      WPP_SF_d(v11[2], 26, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, Sid != 0);
      v12 = (struct _SID *)Sid;
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 == 1 )
    {
      ATL::CSid::operator=((ATL::CSid *)v21, v12);
      LocalFree(Sid);
      Sid = 0;
      ATL::CSid::CSid((ATL::CSid *)v23);
      v19 = 0;
      v17 = 0;
      v18[0] = 0;
      while ( v9 < (*(unsigned int (__fastcall **)(struct ATL::CDacl *))(*(_QWORD *)this + 8LL))(this) )
      {
        ATL::CAcl::GetAclEntry(this, v9, (struct ATL::CSid *)v23, &v19, &v17, v18, v15, v16);
        if ( EqualSid(pSid1, pSid2) && !v17 && v19 == v6 && (v18[0] & a4) == a4 )
          goto LABEL_28;
        ++v9;
      }
      v13 = ATL::CDacl::AddAllowedAce(this, (const struct ATL::CSid *)v21, v6, a4);
      v10 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v13);
      }
      if ( v10 == 1 )
        *a5 = 1;
LABEL_28:
      ATL::CSid::~CSid((ATL::CSid *)v23);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    WPP_SF_d(v11[2], 28, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v10);
  ATL::CSid::~CSid((ATL::CSid *)v21);
  return v10;
}

```

## disassembly

```asm
0x1400920b4  push    rbp
0x1400920b6  push    rbx
0x1400920b7  push    rsi
0x1400920b8  push    rdi
0x1400920b9  push    r12
0x1400920bb  push    r14
0x1400920bd  push    r15
0x1400920bf  lea     rbp, [rsp-60h]
0x1400920c4  sub     rsp, 160h
0x1400920cb  mov     rax, cs:__security_cookie
0x1400920d2  xor     rax, rsp
0x1400920d5  mov     [rbp+90h+var_40], rax
0x1400920d9  movzx   esi, r9b
0x1400920dd  mov     r14d, r8d
0x1400920e0  mov     rbx, rdx
0x1400920e3  mov     r15, rcx
0x1400920e6  mov     r12, [rbp+90h+arg_20]
0x1400920ed  lea     rax, WPP_GLOBAL_Control
0x1400920f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400920fb  cmp     rcx, rax
0x1400920fe  jz      short loc_14009211C
0x140092100  test    byte ptr [rcx+1Ch], 1
0x140092104  jz      short loc_14009211C
0x140092106  cmp     byte ptr [rcx+19h], 5
0x14009210a  jb      short loc_14009211C
0x14009210c  mov     dword ptr [rsp+190h+var_170], esi
0x140092110  mov     r9d, r8d
0x140092113  mov     rcx, [rcx+10h]
0x140092117  call    WPP_SF_LD
0x14009211c  xor     edi, edi
0x14009211e  mov     [rsp+190h+Sid], rdi
0x140092123  lea     rcx, [rsp+190h+var_140]; this
0x140092128  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x14009212d  nop
0x14009212e  mov     [r12], edi
0x140092132  lea     rdx, [rsp+190h+Sid]; Sid
0x140092137  mov     rcx, rbx; StringSid
0x14009213a  call    cs:__imp_ConvertStringSidToSidW
0x140092140  mov     ebx, eax
0x140092142  mov     rcx, cs:WPP_GLOBAL_Control
0x140092149  lea     rax, WPP_GLOBAL_Control
0x140092150  cmp     rcx, rax
0x140092153  jz      short loc_140092185
0x140092155  test    byte ptr [rcx+1Ch], 2
0x140092159  jz      short loc_140092185
0x14009215b  cmp     byte ptr [rcx+19h], 4
0x14009215f  jb      short loc_140092185
0x140092161  lea     edx, [rdi+19h]
0x140092164  mov     r9d, ebx
0x140092167  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x14009216e  mov     rcx, [rcx+10h]
0x140092172  call    WPP_SF_d
0x140092177  mov     rcx, cs:WPP_GLOBAL_Control
0x14009217e  lea     rax, WPP_GLOBAL_Control
0x140092185  cmp     ebx, 1
0x140092188  jnz     loc_1400922E4
0x14009218e  mov     ebx, edi
0x140092190  mov     rdx, [rsp+190h+Sid]
0x140092195  test    rdx, rdx
0x140092198  setnz   bl
0x14009219b  cmp     rcx, rax
0x14009219e  jz      short loc_1400921D0
0x1400921a0  test    byte ptr [rcx+1Ch], 2
0x1400921a4  jz      short loc_1400921D0
0x1400921a6  cmp     byte ptr [rcx+19h], 4
0x1400921aa  jb      short loc_1400921D0
0x1400921ac  mov     edx, 1Ah
0x1400921b1  mov     r9d, ebx
0x1400921b4  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x1400921bb  mov     rcx, [rcx+10h]
0x1400921bf  call    WPP_SF_d
0x1400921c4  mov     rdx, [rsp+190h+Sid]; struct _SID *
0x1400921c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400921d0  cmp     ebx, 1
0x1400921d3  jnz     loc_1400922E4
0x1400921d9  lea     rcx, [rsp+190h+var_140]; this
0x1400921de  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x1400921e3  mov     rcx, [rsp+190h+Sid]; hMem
0x1400921e8  call    cs:__imp_LocalFree
0x1400921ee  mov     [rsp+190h+Sid], rdi
0x1400921f3  lea     rcx, [rbp+90h+var_C0]; this
0x1400921f7  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1400921fc  nop
0x1400921fd  mov     [rsp+190h+var_14C], edi
0x140092201  mov     [rsp+190h+var_150], dil
0x140092206  mov     [rsp+190h+var_14F], dil
0x14009220b  mov     rax, [r15]
0x14009220e  mov     rcx, r15
0x140092211  mov     rax, [rax+8]
0x140092215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009221a  mov     rcx, r15; this
0x14009221d  cmp     edi, eax
0x14009221f  jnb     short loc_140092276
0x140092221  lea     rax, [rsp+190h+var_14F]
0x140092226  mov     [rsp+190h+var_168], rax; unsigned __int8 *
0x14009222b  lea     rax, [rsp+190h+var_150]
0x140092230  mov     [rsp+190h+var_170], rax; unsigned __int8 *
0x140092235  lea     r9, [rsp+190h+var_14C]; unsigned int *
0x14009223a  lea     r8, [rbp+90h+var_C0]; struct ATL::CSid *
0x14009223e  mov     edx, edi; unsigned int
0x140092240  call    ?GetAclEntry@CAcl@ATL@@QEBAXIPEAVCSid@2@PEAKPEAE2PEAU_GUID@@3@Z; ATL::CAcl::GetAclEntry(uint,ATL::CSid *,ulong *,uchar *,uchar *,_GUID *,_GUID *)
0x140092245  lea     rdx, [rsp+190h+pSid2]; pSid2
0x14009224a  lea     rcx, [rbp+90h+pSid1]; pSid1
0x14009224e  call    cs:__imp_EqualSid
0x140092254  test    eax, eax
0x140092256  jz      short loc_140092272
0x140092258  cmp     [rsp+190h+var_150], 0
0x14009225d  jnz     short loc_140092272
0x14009225f  cmp     [rsp+190h+var_14C], r14d
0x140092264  jnz     short loc_140092272
0x140092266  mov     al, sil
0x140092269  and     al, [rsp+190h+var_14F]
0x14009226d  cmp     al, sil
0x140092270  jz      short loc_1400922CB
0x140092272  inc     edi
0x140092274  jmp     short loc_14009220B
0x140092276  mov     r9b, sil; unsigned __int8
0x140092279  mov     r8d, r14d; unsigned int
0x14009227c  lea     rdx, [rsp+190h+var_140]; struct ATL::CSid *
0x140092281  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x140092286  movzx   ebx, al
0x140092289  mov     rcx, cs:WPP_GLOBAL_Control
0x140092290  lea     rdi, WPP_GLOBAL_Control
0x140092297  cmp     rcx, rdi
0x14009229a  jz      short loc_1400922C0
0x14009229c  test    byte ptr [rcx+1Ch], 2
0x1400922a0  jz      short loc_1400922C0
0x1400922a2  cmp     byte ptr [rcx+19h], 4
0x1400922a6  jb      short loc_1400922C0
0x1400922a8  mov     edx, 1Bh
0x1400922ad  mov     r9d, ebx
0x1400922b0  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x1400922b7  mov     rcx, [rcx+10h]
0x1400922bb  call    WPP_SF_d
0x1400922c0  cmp     ebx, 1
0x1400922c3  jnz     short loc_1400922D2
0x1400922c5  mov     [r12], ebx
0x1400922c9  jmp     short loc_1400922D2
0x1400922cb  lea     rdi, WPP_GLOBAL_Control
0x1400922d2  lea     rcx, [rbp+90h+var_C0]; this
0x1400922d6  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1400922db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400922e2  jmp     short loc_1400922EB
0x1400922e4  lea     rdi, WPP_GLOBAL_Control
0x1400922eb  cmp     rcx, rdi
0x1400922ee  jz      short loc_140092315
0x1400922f0  test    byte ptr [rcx+1Ch], 1
0x1400922f4  jz      short loc_140092315
0x1400922f6  cmp     byte ptr [rcx+19h], 5
0x1400922fa  jb      short loc_140092315
0x1400922fc  mov     edx, 1Ch
0x140092301  mov     r9d, ebx
0x140092304  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x14009230b  mov     rcx, [rcx+10h]
0x14009230f  call    WPP_SF_d
0x140092314  nop
0x140092315  lea     rcx, [rsp+190h+var_140]; this
0x14009231a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14009231f  mov     eax, ebx
0x140092321  mov     rcx, [rbp+90h+var_40]
0x140092325  xor     rcx, rsp; StackCookie
0x140092328  call    __security_check_cookie
0x14009232d  add     rsp, 160h
0x140092334  pop     r15
0x140092336  pop     r14
0x140092338  pop     r12
0x14009233a  pop     rdi
0x14009233b  pop     rsi
0x14009233c  pop     rbx
0x14009233d  pop     rbp
0x14009233e  retn
```
