# WcnNetworkProfileParse(ushort const *,ulong,tagWCN_NETPROFILE_SETTINGS *,_WFD_PROFILE * *)

- ea: `0x1800296a4`
- end: `0x180029990`
- name: `?WcnNetworkProfileParse@@YAJPEBGKPEAUtagWCN_NETPROFILE_SETTINGS@@PEAPEAU_WFD_PROFILE@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int16, struct tagWCN_NETPROFILE_SETTINGS *, struct _WFD_PROFILE **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800116cc`
- `0x18002b988`

## callees

- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001044c`
- `0x1800296a4`
- `0x180029998`
- `0x180029d60`
- `0x18002a31c`
- `0x18002de1c`
- `0x18002f810`

## string_xrefs

- `0x180029721`: `wszWlanXmlProfile`

## pseudocode

```c
__int64 __fastcall WcnNetworkProfileParse(
        unsigned __int16 *a1,
        __int16 a2,
        struct tagWCN_NETPROFILE_SETTINGS *a3,
        struct _WFD_PROFILE **a4)
{
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  const char *v12; // r9
  unsigned int v14; // eax
  __int64 v15; // r10
  int v16; // r11d
  const unsigned __int16 *v17; // rbx
  int i; // esi
  const char *v19; // rax
  __int64 v20; // r10
  _DWORD *v21; // r9
  char *v22; // r8
  int v23; // eax
  int v24; // ebx
  _QWORD *v25; // r10
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // r10

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 57, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 58;
    v12 = "wszWlanXmlProfile";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v8 + 2), v11, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v12);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 59;
    v12 = "pProfile";
    goto LABEL_12;
  }
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && v8[25] >= 5u )
  {
    v14 = (unsigned int)GetIndent(0);
    WPP_SF_sS(
      *(_QWORD *)(v15 + 16),
      v16,
      (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids,
      v14,
      (__int64)a1);
  }
  *((_QWORD *)a3 + 70) = 0;
  *((_BYTE *)a3 + 552) = 0;
  if ( (a2 & 0x100) == 0 )
  {
    v17 = a1;
    for ( i = 0; i < 2; ++i )
    {
      while ( *v17 != 60 && *v17 )
        ++v17;
      if ( !*v17 )
        break;
      if ( !wcsncmp_0(++v17, L"WFDProfile", 0xAu) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v19 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v20 + 16), 61, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v19);
        }
        a2 |= 0x100u;
        break;
      }
    }
  }
  v21 = (_DWORD *)((char *)a3 + 640);
  v22 = (char *)a3 + 512;
  if ( (a2 & 0x100) != 0 )
  {
    v23 = WcnParseInfoFromWfdProfile(
            (__int64)a1,
            (unsigned __int16 *)a3,
            (__int64)v22,
            v21,
            (_DWORD *)a3 + 161,
            (__int64)a3 + 552,
            a4);
    v24 = v23;
    if ( v23 >= 0 )
    {
LABEL_47:
      v25 = WPP_GLOBAL_Control;
      goto LABEL_48;
    }
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 62;
LABEL_35:
        WPP_SF_d(v25[2], v26, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, (unsigned int)v23);
        goto LABEL_47;
      }
      goto LABEL_48;
    }
  }
  else
  {
    v23 = WcnParseBasicInfoFromProfile((__int64)a1, (unsigned __int16 *)a3, (__int64)v22, v21, (_DWORD *)a3 + 161);
    v24 = v23;
    if ( v23 >= 0 )
    {
      if ( (a2 & 1) != 0 || *((_DWORD *)a3 + 160) == 1 && *((_DWORD *)a3 + 161) == 1 )
        goto LABEL_47;
      v23 = WcnParsePassphraseFromProfile(a1);
      v24 = v23;
      if ( v23 >= 0 )
        goto LABEL_47;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = 64;
          goto LABEL_35;
        }
        goto LABEL_48;
      }
    }
    else
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = 63;
          goto LABEL_35;
        }
LABEL_48:
        if ( v25 != &WPP_GLOBAL_Control && (v24 < 0 || *((_BYTE *)v25 + 25) >= 6u) )
        {
          v27 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v28 + 16), 65, (unsigned int)WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids, v27, v24);
        }
      }
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800296a4  push    rbx
0x1800296a6  push    rbp
0x1800296a7  push    rsi
0x1800296a8  push    rdi
0x1800296a9  push    r12
0x1800296ab  push    r13
0x1800296ad  push    r14
0x1800296af  push    r15
0x1800296b1  sub     rsp, 48h
0x1800296b5  mov     r13, r9
0x1800296b8  mov     rdi, r8
0x1800296bb  mov     r14d, edx
0x1800296be  mov     r15, rcx
0x1800296c1  mov     r10, cs:WPP_GLOBAL_Control
0x1800296c8  lea     rax, WPP_GLOBAL_Control
0x1800296cf  cmp     r10, rax
0x1800296d2  jz      short loc_18002970B
0x1800296d4  cmp     byte ptr [r10+19h], 6
0x1800296d9  jb      short loc_18002970B
0x1800296db  mov     ecx, 1; int
0x1800296e0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800296e5  mov     rcx, [r10+10h]
0x1800296e9  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x1800296f0  mov     edx, 39h ; '9'
0x1800296f5  mov     r9, rax
0x1800296f8  call    WPP_SF_s
0x1800296fd  mov     r10, cs:WPP_GLOBAL_Control
0x180029704  lea     rax, WPP_GLOBAL_Control
0x18002970b  xor     ebp, ebp
0x18002970d  test    r15, r15
0x180029710  jnz     short loc_18002972A
0x180029712  cmp     r10, rax
0x180029715  jz      short loc_180029755
0x180029717  cmp     byte ptr [r10+19h], 2
0x18002971c  jb      short loc_180029755
0x18002971e  lea     edx, [rbp+3Ah]
0x180029721  lea     r9, aWszwlanxmlprof; "wszWlanXmlProfile"
0x180029728  jmp     short loc_180029745
0x18002972a  test    rdi, rdi
0x18002972d  jnz     short loc_18002975F
0x18002972f  cmp     r10, rax
0x180029732  jz      short loc_180029755
0x180029734  cmp     byte ptr [r10+19h], 2
0x180029739  jb      short loc_180029755
0x18002973b  lea     edx, [rdi+3Bh]
0x18002973e  lea     r9, aPprofile; "pProfile"
0x180029745  mov     rcx, [r10+10h]
0x180029749  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029750  call    WPP_SF_s
0x180029755  mov     eax, 80004003h
0x18002975a  jmp     loc_18002997F
0x18002975f  mov     r11d, 3Ch ; '<'
0x180029765  cmp     r10, rax
0x180029768  jz      short loc_180029799
0x18002976a  cmp     byte ptr [r10+19h], 5
0x18002976f  jb      short loc_180029799
0x180029771  xor     ecx, ecx; int
0x180029773  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029778  mov     rcx, [r10+10h]
0x18002977c  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x180029783  mov     edx, r11d
0x180029786  mov     [rsp+88h+var_68], r15
0x18002978b  mov     r9, rax
0x18002978e  call    WPP_SF_sS
0x180029793  mov     r11d, 3Ch ; '<'
0x180029799  mov     [rdi+230h], rbp
0x1800297a0  lea     r12, [rdi+228h]
0x1800297a7  mov     [r12], bpl
0x1800297ab  bt      r14d, 8
0x1800297b0  jb      loc_18002983E
0x1800297b6  mov     rbx, r15
0x1800297b9  mov     esi, ebp
0x1800297bb  jmp     short loc_1800297C6
0x1800297bd  test    ax, ax
0x1800297c0  jz      short loc_1800297CF
0x1800297c2  add     rbx, 2
0x1800297c6  movzx   eax, word ptr [rbx]
0x1800297c9  cmp     ax, r11w
0x1800297cd  jnz     short loc_1800297BD
0x1800297cf  cmp     [rbx], bp
0x1800297d2  jz      short loc_18002983E
0x1800297d4  add     rbx, 2
0x1800297d8  lea     rdx, aWfdprofile; "WFDProfile"
0x1800297df  mov     rcx, rbx; String1
0x1800297e2  mov     r8d, 0Ah; MaxCount
0x1800297e8  call    wcsncmp_0
0x1800297ed  test    eax, eax
0x1800297ef  jz      short loc_180029800
0x1800297f1  inc     esi
0x1800297f3  mov     r11d, 3Ch ; '<'
0x1800297f9  cmp     esi, 2
0x1800297fc  jl      short loc_1800297C6
0x1800297fe  jmp     short loc_18002983E
0x180029800  mov     r10, cs:WPP_GLOBAL_Control
0x180029807  lea     rax, WPP_GLOBAL_Control
0x18002980e  cmp     r10, rax
0x180029811  jz      short loc_180029839
0x180029813  cmp     byte ptr [r10+19h], 5
0x180029818  jb      short loc_180029839
0x18002981a  xor     ecx, ecx; int
0x18002981c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029821  mov     rcx, [r10+10h]
0x180029825  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002982c  mov     edx, 3Dh ; '='
0x180029831  mov     r9, rax
0x180029834  call    WPP_SF_s
0x180029839  bts     r14d, 8
0x18002983e  lea     rsi, [rdi+280h]
0x180029845  mov     rdx, rdi
0x180029848  lea     rbp, [rdi+284h]
0x18002984f  mov     r9, rsi
0x180029852  lea     r8, [rdi+200h]
0x180029859  mov     rcx, r15
0x18002985c  bt      r14d, 8
0x180029861  jnb     short loc_1800298C0
0x180029863  mov     [rsp+88h+var_58], r13
0x180029868  mov     [rsp+88h+var_60], r12
0x18002986d  mov     [rsp+88h+var_68], rbp
0x180029872  call    WcnParseInfoFromWfdProfile
0x180029877  mov     ebx, eax
0x180029879  test    eax, eax
0x18002987b  jns     loc_18002993B
0x180029881  mov     r10, cs:WPP_GLOBAL_Control
0x180029888  lea     rdi, WPP_GLOBAL_Control
0x18002988f  cmp     r10, rdi
0x180029892  jz      loc_18002997D
0x180029898  cmp     byte ptr [r10+19h], 2
0x18002989d  jb      loc_180029949
0x1800298a3  mov     edx, 3Eh ; '>'
0x1800298a8  mov     rcx, [r10+10h]
0x1800298ac  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x1800298b3  mov     r9d, eax
0x1800298b6  call    WPP_SF_d
0x1800298bb  jmp     loc_180029942
0x1800298c0  mov     [rsp+88h+var_68], rbp
0x1800298c5  call    WcnParseBasicInfoFromProfile
0x1800298ca  mov     ebx, eax
0x1800298cc  test    eax, eax
0x1800298ce  jns     short loc_1800298F5
0x1800298d0  mov     r10, cs:WPP_GLOBAL_Control
0x1800298d7  lea     rdi, WPP_GLOBAL_Control
0x1800298de  cmp     r10, rdi
0x1800298e1  jz      loc_18002997D
0x1800298e7  cmp     byte ptr [r10+19h], 2
0x1800298ec  jb      short loc_180029949
0x1800298ee  mov     edx, 3Fh ; '?'
0x1800298f3  jmp     short loc_1800298A8
0x1800298f5  test    r14b, 1
0x1800298f9  jnz     short loc_18002993B
0x1800298fb  cmp     dword ptr [rsi], 1
0x1800298fe  jnz     short loc_180029906
0x180029900  cmp     dword ptr [rbp+0], 1
0x180029904  jz      short loc_18002993B
0x180029906  mov     rdx, r12
0x180029909  mov     rcx, r15; unsigned __int16 *
0x18002990c  call    WcnParsePassphraseFromProfile
0x180029911  mov     ebx, eax
0x180029913  test    eax, eax
0x180029915  jns     short loc_18002993B
0x180029917  mov     r10, cs:WPP_GLOBAL_Control
0x18002991e  lea     rdi, WPP_GLOBAL_Control
0x180029925  cmp     r10, rdi
0x180029928  jz      short loc_18002997D
0x18002992a  cmp     byte ptr [r10+19h], 2
0x18002992f  jb      short loc_180029949
0x180029931  mov     edx, 40h ; '@'
0x180029936  jmp     loc_1800298A8
0x18002993b  lea     rdi, WPP_GLOBAL_Control
0x180029942  mov     r10, cs:WPP_GLOBAL_Control
0x180029949  cmp     r10, rdi
0x18002994c  jz      short loc_18002997D
0x18002994e  test    ebx, ebx
0x180029950  js      short loc_180029959
0x180029952  cmp     byte ptr [r10+19h], 6
0x180029957  jb      short loc_18002997D
0x180029959  or      ecx, 0FFFFFFFFh; int
0x18002995c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029961  mov     rcx, [r10+10h]
0x180029965  lea     r8, WPP_0db0290a1fc530b29ab1052ac3978287_Traceguids
0x18002996c  mov     edx, 41h ; 'A'
0x180029971  mov     dword ptr [rsp+88h+var_68], ebx
0x180029975  mov     r9, rax
0x180029978  call    WPP_SF_sd
0x18002997d  mov     eax, ebx
0x18002997f  add     rsp, 48h
0x180029983  pop     r15
0x180029985  pop     r14
0x180029987  pop     r13
0x180029989  pop     r12
0x18002998b  pop     rdi
0x18002998c  pop     rsi
0x18002998d  pop     rbp
0x18002998e  pop     rbx
0x18002998f  retn
```
