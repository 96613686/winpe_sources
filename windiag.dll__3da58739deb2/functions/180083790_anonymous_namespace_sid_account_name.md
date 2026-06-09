# _anonymous_namespace_::sid_account_name

- ea: `0x180083790`
- end: `0x1800839ce`
- name: `_anonymous_namespace_::sid_account_name`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081518`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x18003a52c`
- `0x18003b0bc`
- `0x180048c8c`
- `0x180049674`
- `0x18006dc58`
- `0x180083790`

## import_xrefs

- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupAccountSidA` at `0x180083893`
- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupAccountSidA` at `0x180083893`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::sid_account_name(__int64 a1, void *a2)
{
  LPSTR v4; // rbx
  LPSTR v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // r8
  enum _SID_NAME_USE v8; // ecx
  __m128i si128; // xmm0
  enum _SID_NAME_USE peUse[4]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp-69h] BYREF
  DWORD cchReferencedDomainName; // [rsp+60h] [rbp-59h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-55h] BYREF
  LPSTR Name[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v16; // [rsp+78h] [rbp-41h]
  LPSTR ReferencedDomainName[2]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v18; // [rsp+90h] [rbp-29h]
  __int128 v19; // [rsp+A0h] [rbp-19h] BYREF
  __m128i v20; // [rsp+B0h] [rbp-9h]
  __int128 v21; // [rsp+C0h] [rbp+7h] BYREF
  __m128i v22; // [rsp+D0h] [rbp+17h]
  enum _SID_NAME_USE v23; // [rsp+E0h] [rbp+27h]
  int v24; // [rsp+E4h] [rbp+2Bh]

  cchReferencedDomainName = 260;
  *(_OWORD *)ReferencedDomainName = 0;
  v18 = 0;
  std::vector<char>::_Buy_nonzero(ReferencedDomainName, 260);
  v4 = ReferencedDomainName[0];
  memset_0(ReferencedDomainName[0], 0, 0x104u);
  ReferencedDomainName[1] = v4 + 260;
  v12[0] = 0;
  std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(v12);
  cchName = 260;
  *(_OWORD *)Name = 0;
  v16 = 0;
  std::vector<char>::_Buy_nonzero(Name, 260);
  v5 = Name[0];
  memset_0(Name[0], 0, 0x104u);
  Name[1] = v5 + 260;
  v12[0] = 0;
  std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(v12);
  peUse[0] = SidTypeInvalid;
  if ( LookupAccountSidA(0, a2, Name[0], &cchName, ReferencedDomainName[0], &cchReferencedDomainName, peUse) )
  {
    v19 = 0;
    v20 = 0;
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( Name[0][v7] );
    std::string::_Construct<1,char const *>(&v19, Name[0], v7);
    v21 = 0;
    v22 = 0;
    do
      ++v6;
    while ( ReferencedDomainName[0][v6] );
    std::string::_Construct<1,char const *>(&v21, ReferencedDomainName[0], v6);
    v8 = peUse[0];
    v23 = peUse[0];
    v24 = 0;
    *(_OWORD *)a1 = 0;
    *(_OWORD *)a1 = v19;
    *(__m128i *)(a1 + 16) = v20;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v20 = si128;
    LOBYTE(v19) = 0;
    *(_OWORD *)(a1 + 32) = v21;
    *(__m128i *)(a1 + 48) = v22;
    v22 = si128;
    LOBYTE(v21) = 0;
    *(_DWORD *)(a1 + 64) = v8;
    *(_BYTE *)(a1 + 72) = 1;
    std::string::~string(&v21);
    std::string::~string(&v19);
  }
  else
  {
    *(_BYTE *)(a1 + 72) = 0;
  }
  std::vector<char>::~vector<char>(Name);
  std::vector<char>::~vector<char>(ReferencedDomainName);
  return a1;
}

```

## disassembly

```asm
0x180083790  mov     [rsp-8+arg_10], rbx
0x180083795  mov     [rsp-8+arg_18], rsi
0x18008379a  push    rbp
0x18008379b  push    rdi
0x18008379c  push    r14
0x18008379e  lea     rbp, [rsp-47h]
0x1800837a3  sub     rsp, 100h
0x1800837aa  mov     rax, cs:__security_cookie
0x1800837b1  xor     rax, rsp
0x1800837b4  mov     [rbp+57h+var_20], rax
0x1800837b8  mov     rdi, rdx
0x1800837bb  mov     rsi, rcx
0x1800837be  mov     [rbp+57h+var_C0], rcx
0x1800837c2  mov     r14d, 104h
0x1800837c8  mov     [rbp+57h+var_B0], r14d
0x1800837cc  xorps   xmm0, xmm0
0x1800837cf  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800837d4  mov     [rbp+57h+var_80], 0
0x1800837dc  mov     edx, r14d
0x1800837df  lea     rcx, [rbp+57h+var_90]
0x1800837e3  call    ?_Buy_nonzero@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Buy_nonzero(unsigned __int64)
0x1800837e8  mov     rbx, [rbp+57h+var_90]
0x1800837ec  mov     r8d, r14d; Size
0x1800837ef  xor     edx, edx; Val
0x1800837f1  mov     rcx, rbx; void *
0x1800837f4  call    memset_0
0x1800837f9  lea     rax, [rbx+104h]
0x180083800  mov     [rbp+57h+var_90+8], rax
0x180083804  mov     [rbp+57h+var_C0], 0
0x18008380c  lea     rcx, [rbp+57h+var_C0]
0x180083810  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180083815  nop
0x180083816  mov     [rbp+57h+cchName], r14d
0x18008381a  xorps   xmm0, xmm0
0x18008381d  movdqu  xmmword ptr [rbp+57h+Name], xmm0
0x180083822  mov     [rbp+57h+var_98], 0
0x18008382a  mov     edx, r14d
0x18008382d  lea     rcx, [rbp+57h+Name]
0x180083831  call    ?_Buy_nonzero@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Buy_nonzero(unsigned __int64)
0x180083836  mov     rbx, [rbp+57h+Name]
0x18008383a  mov     r8d, r14d; Size
0x18008383d  xor     edx, edx; Val
0x18008383f  mov     rcx, rbx; void *
0x180083842  call    memset_0
0x180083847  lea     rax, [rbx+104h]
0x18008384e  mov     [rbp+57h+Name+8], rax
0x180083852  mov     [rbp+57h+var_C0], 0
0x18008385a  lea     rcx, [rbp+57h+var_C0]
0x18008385e  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180083863  nop
0x180083864  mov     [rbp+57h+var_D0], 7
0x18008386b  mov     rax, [rbp+57h+var_90]
0x18008386f  lea     rcx, [rbp+57h+var_D0]
0x180083873  mov     [rsp+110h+peUse], rcx; peUse
0x180083878  lea     rcx, [rbp+57h+var_B0]
0x18008387c  mov     [rsp+110h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180083881  mov     [rsp+110h+ReferencedDomainName], rax; ReferencedDomainName
0x180083886  lea     r9, [rbp+57h+cchName]; cchName
0x18008388a  mov     r8, [rbp+57h+Name]; Name
0x18008388e  mov     rdx, rdi; Sid
0x180083891  xor     ecx, ecx; lpSystemName
0x180083893  call    cs:__imp_LookupAccountSidA
0x180083899  test    eax, eax
0x18008389b  jz      loc_180083990
0x1800838a1  mov     rdx, [rbp+57h+Name]
0x1800838a5  xorps   xmm0, xmm0
0x1800838a8  movups  [rbp+57h+var_70], xmm0
0x1800838ac  xorps   xmm1, xmm1
0x1800838af  movdqa  [rbp+57h+var_60], xmm1
0x1800838b4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800838b8  mov     r8, rbx
0x1800838bb  inc     r8
0x1800838be  cmp     byte ptr [rdx+r8], 0
0x1800838c3  jnz     short loc_1800838BB
0x1800838c5  lea     rcx, [rbp+57h+var_70]
0x1800838c9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800838ce  nop
0x1800838cf  mov     rdx, [rbp+57h+var_90]
0x1800838d3  xorps   xmm0, xmm0
0x1800838d6  movups  [rbp+57h+var_50], xmm0
0x1800838da  xorps   xmm1, xmm1
0x1800838dd  movdqa  [rbp+57h+var_40], xmm1
0x1800838e2  inc     rbx
0x1800838e5  cmp     byte ptr [rdx+rbx], 0
0x1800838e9  jnz     short loc_1800838E2
0x1800838eb  mov     r8, rbx
0x1800838ee  lea     rcx, [rbp+57h+var_50]
0x1800838f2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800838f7  mov     ecx, [rbp+57h+var_D0]
0x1800838fa  mov     [rbp+57h+var_30], ecx
0x1800838fd  xor     eax, eax
0x1800838ff  mov     [rbp+57h+var_2C], eax
0x180083902  xorps   xmm0, xmm0
0x180083905  movups  xmmword ptr [rsi], xmm0
0x180083908  mov     al, byte ptr [rbp+57h+var_70]
0x18008390b  mov     [rsi], al
0x18008390d  movsd   xmm0, qword ptr [rbp+57h+var_70+1]
0x180083912  movsd   qword ptr [rsi+1], xmm0
0x180083917  mov     eax, dword ptr [rbp+57h+var_70+9]
0x18008391a  mov     [rsi+9], eax
0x18008391d  movzx   eax, word ptr [rbp+57h+var_70+0Dh]
0x180083921  mov     [rsi+0Dh], ax
0x180083925  mov     al, byte ptr [rbp+57h+var_70+0Fh]
0x180083928  mov     [rsi+0Fh], al
0x18008392b  mov     rax, qword ptr [rbp+57h+var_60]
0x18008392f  mov     [rsi+10h], rax
0x180083933  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180083937  mov     [rsi+18h], rax
0x18008393b  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180083943  movdqa  [rbp+57h+var_60], xmm0
0x180083948  mov     byte ptr [rbp+57h+var_70], 0
0x18008394c  mov     rax, qword ptr [rbp+57h+var_50]
0x180083950  mov     [rsi+20h], rax
0x180083954  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180083958  mov     [rsi+28h], rax
0x18008395c  mov     rax, qword ptr [rbp+57h+var_40]
0x180083960  mov     [rsi+30h], rax
0x180083964  mov     rax, qword ptr [rbp+57h+var_40+8]
0x180083968  mov     [rsi+38h], rax
0x18008396c  movdqa  [rbp+57h+var_40], xmm0
0x180083971  mov     byte ptr [rbp+57h+var_50], 0
0x180083975  mov     [rsi+40h], ecx
0x180083978  mov     byte ptr [rsi+48h], 1
0x18008397c  lea     rcx, [rbp+57h+var_50]
0x180083980  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180083985  lea     rcx, [rbp+57h+var_70]
0x180083989  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18008398e  jmp     short loc_180083994
0x180083990  mov     byte ptr [rsi+48h], 0
0x180083994  lea     rcx, [rbp+57h+Name]
0x180083998  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18008399d  nop
0x18008399e  lea     rcx, [rbp+57h+var_90]
0x1800839a2  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800839a7  mov     rax, rsi
0x1800839aa  mov     rcx, [rbp+57h+var_20]
0x1800839ae  xor     rcx, rsp; StackCookie
0x1800839b1  call    __security_check_cookie
0x1800839b6  lea     r11, [rsp+110h+var_10]
0x1800839be  mov     rbx, [r11+30h]
0x1800839c2  mov     rsi, [r11+38h]
0x1800839c6  mov     rsp, r11
0x1800839c9  pop     r14
0x1800839cb  pop     rdi
0x1800839cc  pop     rbp
0x1800839cd  retn
```
