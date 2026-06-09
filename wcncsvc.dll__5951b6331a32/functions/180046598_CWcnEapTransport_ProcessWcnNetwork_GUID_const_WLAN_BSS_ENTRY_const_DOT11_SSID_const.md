# CWcnEapTransport::ProcessWcnNetwork(_GUID const *,_WLAN_BSS_ENTRY const *,_DOT11_SSID const *)

- ea: `0x180046598`
- end: `0x180046775`
- name: `?ProcessWcnNetwork@CWcnEapTransport@@AEAAXPEBU_GUID@@PEBU_WLAN_BSS_ENTRY@@PEBU_DOT11_SSID@@@Z`
- size: `477`
- prototype: `void __fastcall(CWcnEapTransport *__hidden this, const struct _GUID *, const struct _WLAN_BSS_ENTRY *, const struct _DOT11_SSID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800457b4`

## callees

- `0x180002940`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x180044dd8`
- `0x1800460f4`
- `0x180046598`
- `0x180053004`
- `0x1800565b8`
- `0x180056e30`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18004671a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18004671a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWcnEapTransport::ProcessWcnNetwork(
        CWcnEapTransport *this,
        const struct _GUID *a2,
        const struct _WLAN_BSS_ENTRY *a3,
        const struct _DOT11_SSID *a4)
{
  int v8; // ebx
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  ULONG ulIeSize; // eax
  void *v13; // rax
  void *v14; // rdi
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // r10
  ULONG v20; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v21[32]; // [rsp+38h] [rbp-70h] BYREF

  v8 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 59, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  ulIeSize = a3->ulIeSize;
  v20 = ulIeSize;
  if ( ulIeSize >= 0x2800 )
    goto LABEL_22;
  v13 = operator new[](ulIeSize, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  if ( v13 )
  {
    if ( !(unsigned int)WcnGetRawWpsIe(a3, v13, &v20) )
    {
LABEL_20:
      operator delete[](v14);
      goto LABEL_21;
    }
    CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v21);
    v15 = CSbSafeBuffer::CopyFromBuffer<unsigned char *>((__int64)v21, (__int64)v14, (__int64)v14 + v20);
    v8 = v15;
    if ( v15 >= 0 )
    {
      v15 = CWcnEapTransport::ParseWpsIe(this, a2, a3, a4, (const struct CSbSafeBuffer *)v21);
      v8 = v15;
      if ( v15 >= 0 )
        goto LABEL_19;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_19;
      v17 = 62;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_19;
      v17 = 61;
    }
    WPP_SF_d(v16[2], v17, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, (unsigned int)v15);
LABEL_19:
    CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v21);
    goto LABEL_20;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  v8 = -2147024882;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, "pIeBuffer");
LABEL_21:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && (v8 < 0 || v9[25] >= 6u) )
  {
    v18 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 63, (unsigned int)WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v18, v8);
  }
}

```

## disassembly

```asm
0x180046598  push    rbx
0x18004659a  push    rbp
0x18004659b  push    rsi
0x18004659c  push    rdi
0x18004659d  push    r12
0x18004659f  push    r13
0x1800465a1  push    r14
0x1800465a3  push    r15
0x1800465a5  sub     rsp, 68h
0x1800465a9  mov     rax, cs:__security_cookie
0x1800465b0  xor     rax, rsp
0x1800465b3  mov     [rsp+0A8h+var_50], rax
0x1800465b8  mov     r15, r9
0x1800465bb  mov     rsi, r8
0x1800465be  mov     r14, rdx
0x1800465c1  mov     rbp, rcx
0x1800465c4  xor     ebx, ebx
0x1800465c6  lea     r12, WPP_GLOBAL_Control
0x1800465cd  lea     r13, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800465d4  mov     r10, cs:WPP_GLOBAL_Control
0x1800465db  cmp     r10, r12
0x1800465de  jz      short loc_180046608
0x1800465e0  cmp     byte ptr [r10+19h], 6
0x1800465e5  jb      short loc_180046608
0x1800465e7  lea     ecx, [rbx+1]; int
0x1800465ea  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800465ef  lea     edx, [rbx+3Bh]
0x1800465f2  mov     r9, rax
0x1800465f5  mov     r8, r13
0x1800465f8  mov     rcx, [r10+10h]
0x1800465fc  call    WPP_SF_s
0x180046601  mov     r10, cs:WPP_GLOBAL_Control
0x180046608  mov     eax, [rsi+164h]
0x18004660e  mov     [rsp+0A8h+var_78], eax
0x180046612  cmp     eax, 2800h
0x180046617  jnb     loc_180046727
0x18004661d  mov     ecx, eax; unsigned __int64
0x18004661f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180046626  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004662b  mov     rdi, rax
0x18004662e  test    rax, rax
0x180046631  jnz     short loc_18004666E
0x180046633  mov     r10, cs:WPP_GLOBAL_Control
0x18004663a  cmp     r10, r12
0x18004663d  jz      loc_180046757
0x180046643  mov     ebx, 8007000Eh
0x180046648  cmp     byte ptr [r10+19h], 2
0x18004664d  jb      loc_180046727
0x180046653  lea     edx, [rax+3Ch]
0x180046656  lea     r9, aPiebuffer; "pIeBuffer"
0x18004665d  mov     r8, r13
0x180046660  mov     rcx, [r10+10h]
0x180046664  call    WPP_SF_s
0x180046669  jmp     loc_180046720
0x18004666e  lea     r8, [rsp+0A8h+var_78]
0x180046673  mov     rdx, rdi
0x180046676  mov     rcx, rsi
0x180046679  call    WcnGetRawWpsIe
0x18004667e  test    eax, eax
0x180046680  jz      loc_180046717
0x180046686  lea     rcx, [rsp+0A8h+var_70]; this
0x18004668b  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x180046690  nop
0x180046691  mov     r8d, [rsp+0A8h+var_78]
0x180046696  add     r8, rdi
0x180046699  mov     rdx, rdi
0x18004669c  lea     rcx, [rsp+0A8h+var_70]
0x1800466a1  call    ??$CopyFromBuffer@PEAE@CSbSafeBuffer@@QEAAJPEAE0@Z; CSbSafeBuffer::CopyFromBuffer<uchar *>(uchar *,uchar *)
0x1800466a6  mov     ebx, eax
0x1800466a8  test    eax, eax
0x1800466aa  jns     short loc_1800466C5
0x1800466ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800466b3  cmp     rcx, r12
0x1800466b6  jz      short loc_18004670D
0x1800466b8  cmp     byte ptr [rcx+19h], 2
0x1800466bc  jb      short loc_18004670D
0x1800466be  mov     edx, 3Dh ; '='
0x1800466c3  jmp     short loc_1800466FD
0x1800466c5  lea     rax, [rsp+0A8h+var_70]
0x1800466ca  mov     [rsp+0A8h+var_88], rax; struct CSbSafeBuffer *
0x1800466cf  mov     r9, r15; struct _DOT11_SSID *
0x1800466d2  mov     r8, rsi; struct _WLAN_BSS_ENTRY *
0x1800466d5  mov     rdx, r14; struct _GUID *
0x1800466d8  mov     rcx, rbp; this
0x1800466db  call    ?ParseWpsIe@CWcnEapTransport@@AEAAJPEBU_GUID@@PEBU_WLAN_BSS_ENTRY@@PEBU_DOT11_SSID@@PEBVCSbSafeBuffer@@@Z; CWcnEapTransport::ParseWpsIe(_GUID const *,_WLAN_BSS_ENTRY const *,_DOT11_SSID const *,CSbSafeBuffer const *)
0x1800466e0  mov     ebx, eax
0x1800466e2  test    eax, eax
0x1800466e4  jns     short loc_18004670D
0x1800466e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800466ed  cmp     rcx, r12
0x1800466f0  jz      short loc_18004670D
0x1800466f2  cmp     byte ptr [rcx+19h], 2
0x1800466f6  jb      short loc_18004670D
0x1800466f8  mov     edx, 3Eh ; '>'
0x1800466fd  mov     r9d, eax
0x180046700  mov     r8, r13
0x180046703  mov     rcx, [rcx+10h]
0x180046707  call    WPP_SF_d
0x18004670c  nop
0x18004670d  lea     rcx, [rsp+0A8h+var_70]; this
0x180046712  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180046717  mov     rcx, rdi
0x18004671a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180046720  mov     r10, cs:WPP_GLOBAL_Control
0x180046727  cmp     r10, r12
0x18004672a  jz      short loc_180046757
0x18004672c  test    ebx, ebx
0x18004672e  js      short loc_180046737
0x180046730  cmp     byte ptr [r10+19h], 6
0x180046735  jb      short loc_180046757
0x180046737  or      ecx, 0FFFFFFFFh; int
0x18004673a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004673f  mov     edx, 3Fh ; '?'
0x180046744  mov     dword ptr [rsp+0A8h+var_88], ebx
0x180046748  mov     r9, rax
0x18004674b  mov     r8, r13
0x18004674e  mov     rcx, [r10+10h]
0x180046752  call    WPP_SF_sd
0x180046757  mov     rcx, [rsp+0A8h+var_50]
0x18004675c  xor     rcx, rsp; StackCookie
0x18004675f  call    __security_check_cookie
0x180046764  add     rsp, 68h
0x180046768  pop     r15
0x18004676a  pop     r14
0x18004676c  pop     r13
0x18004676e  pop     r12
0x180046770  pop     rdi
0x180046771  pop     rsi
0x180046772  pop     rbp
0x180046773  pop     rbx
0x180046774  retn
```
