# WcnUpnpReferenceGit(void)

- ea: `0x1800402e4`
- end: `0x180040535`
- name: `?WcnUpnpReferenceGit@@YAJXZ`
- size: `593`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003dfb0`
- `0x18003f2c0`
- `0x180042994`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x1800402e4`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800404c7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800404c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800403b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800403b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 WcnUpnpReferenceGit(void)
{
  int v0; // ebx
  const char *Indent; // rax
  __int64 v2; // r10
  struct CWcnUpnpGit *v3; // rax
  struct CWcnUpnpGit *v4; // rbx
  const char *v5; // rax
  __int64 v6; // r10
  HRESULT Instance; // eax
  _BYTE *v8; // r10
  unsigned int v9; // eax
  __int64 v10; // r10
  struct CWcnUpnpGit *v11; // rdi
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r10

  v0 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v2 + 16), 39, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, Indent);
  }
  if ( g_WcnUpnpGitRefCnt )
    goto LABEL_30;
  v3 = (struct CWcnUpnpGit *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( v3 )
  {
    *((_QWORD *)v3 + 2) = 0;
    g_pWcnUpnpGit = v3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v5 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v6 + 16), 10, WPP_0fe6f8abec263b59ca366f8c0564ad38_Traceguids, v5);
    }
    Instance = CoCreateInstance(
                 &CLSID_StdGlobalInterfaceTable,
                 0,
                 1u,
                 &GUID_00000146_0000_0000_c000_000000000046,
                 (LPVOID *)v4 + 2);
    v0 = Instance;
    if ( Instance < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_18;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_14:
        if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v0 < 0 || v8[25] >= 6u) )
        {
          v9 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v10 + 16), 12, (unsigned int)WPP_0fe6f8abec263b59ca366f8c0564ad38_Traceguids, v9, v0);
          v8 = WPP_GLOBAL_Control;
        }
LABEL_18:
        if ( v0 < 0 )
        {
          if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && v8[25] >= 2u )
          {
            WPP_SF_d(*((_QWORD *)v8 + 2), 41, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, (unsigned int)v0);
LABEL_25:
            v8 = WPP_GLOBAL_Control;
            goto LABEL_26;
          }
          goto LABEL_26;
        }
LABEL_30:
        ++g_WcnUpnpGitRefCnt;
LABEL_31:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_32;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_0fe6f8abec263b59ca366f8c0564ad38_Traceguids,
        (unsigned int)Instance);
    }
    v8 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  g_pWcnUpnpGit = 0;
  v0 = -2147024882;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, "g_pWcnUpnpGit");
    goto LABEL_25;
  }
LABEL_26:
  v11 = g_pWcnUpnpGit;
  if ( g_pWcnUpnpGit )
  {
    v12 = *((_QWORD *)g_pWcnUpnpGit + 2);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    operator delete(v11);
    g_pWcnUpnpGit = 0;
    goto LABEL_31;
  }
LABEL_32:
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v0 < 0 || v8[25] >= 6u) )
  {
    v13 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v14 + 16), 42, (unsigned int)WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v13, v0);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800402e4  mov     [rsp+arg_0], rbx
0x1800402e9  mov     [rsp+arg_8], rbp
0x1800402ee  push    rdi
0x1800402ef  sub     rsp, 30h
0x1800402f3  xor     ebx, ebx
0x1800402f5  lea     rbp, WPP_GLOBAL_Control
0x1800402fc  lea     edi, [rbx+1]
0x1800402ff  mov     r10, cs:WPP_GLOBAL_Control
0x180040306  cmp     r10, rbp
0x180040309  jz      short loc_18004032F
0x18004030b  cmp     byte ptr [r10+19h], 6
0x180040310  jb      short loc_18004032F
0x180040312  mov     ecx, edi; int
0x180040314  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040319  lea     edx, [rbx+27h]
0x18004031c  mov     r9, rax
0x18004031f  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x180040326  mov     rcx, [r10+10h]
0x18004032a  call    WPP_SF_s
0x18004032f  mov     eax, cs:?g_WcnUpnpGitRefCnt@@3JC; long volatile g_WcnUpnpGitRefCnt
0x180040335  test    eax, eax
0x180040337  jnz     loc_1800404DA
0x18004033d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180040344  lea     ecx, [rax+18h]; unsigned __int64
0x180040347  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004034c  mov     rbx, rax
0x18004034f  test    rax, rax
0x180040352  jz      loc_18004045C
0x180040358  mov     qword ptr [rax+10h], 0
0x180040360  mov     cs:?g_pWcnUpnpGit@@3PEAVCWcnUpnpGit@@EA, rax; CWcnUpnpGit * g_pWcnUpnpGit
0x180040367  mov     r10, cs:WPP_GLOBAL_Control
0x18004036e  cmp     r10, rbp
0x180040371  jz      short loc_180040399
0x180040373  cmp     byte ptr [r10+19h], 6
0x180040378  jb      short loc_180040399
0x18004037a  mov     ecx, edi; int
0x18004037c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040381  mov     edx, 0Ah
0x180040386  mov     r9, rax
0x180040389  lea     r8, WPP_0fe6f8abec263b59ca366f8c0564ad38_Traceguids
0x180040390  mov     rcx, [r10+10h]
0x180040394  call    WPP_SF_s
0x180040399  lea     rax, [rbx+10h]
0x18004039d  mov     [rsp+38h+ppv], rax; ppv
0x1800403a2  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800403a9  mov     r8d, edi; dwClsContext
0x1800403ac  xor     edx, edx; pUnkOuter
0x1800403ae  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800403b5  call    cs:__imp_CoCreateInstance
0x1800403bb  mov     ebx, eax
0x1800403bd  test    eax, eax
0x1800403bf  jns     short loc_1800403EC
0x1800403c1  mov     r10, cs:WPP_GLOBAL_Control
0x1800403c8  cmp     r10, rbp
0x1800403cb  jz      short loc_18004042E
0x1800403cd  cmp     byte ptr [r10+19h], 2
0x1800403d2  jb      short loc_1800403F3
0x1800403d4  mov     edx, 0Bh
0x1800403d9  mov     r9d, eax
0x1800403dc  lea     r8, WPP_0fe6f8abec263b59ca366f8c0564ad38_Traceguids
0x1800403e3  mov     rcx, [r10+10h]
0x1800403e7  call    WPP_SF_d
0x1800403ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800403f3  cmp     r10, rbp
0x1800403f6  jz      short loc_18004042E
0x1800403f8  test    ebx, ebx
0x1800403fa  js      short loc_180040403
0x1800403fc  cmp     byte ptr [r10+19h], 6
0x180040401  jb      short loc_18004042E
0x180040403  or      ecx, 0FFFFFFFFh; int
0x180040406  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004040b  mov     edx, 0Ch
0x180040410  mov     dword ptr [rsp+38h+ppv], ebx
0x180040414  mov     r9, rax
0x180040417  lea     r8, WPP_0fe6f8abec263b59ca366f8c0564ad38_Traceguids
0x18004041e  mov     rcx, [r10+10h]
0x180040422  call    WPP_SF_sd
0x180040427  mov     r10, cs:WPP_GLOBAL_Control
0x18004042e  test    ebx, ebx
0x180040430  jns     loc_1800404DA
0x180040436  cmp     r10, rbp
0x180040439  jz      short loc_1800404A2
0x18004043b  cmp     byte ptr [r10+19h], 2
0x180040440  jb      short loc_1800404A2
0x180040442  mov     edx, 29h ; ')'
0x180040447  mov     r9d, ebx
0x18004044a  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x180040451  mov     rcx, [r10+10h]
0x180040455  call    WPP_SF_d
0x18004045a  jmp     short loc_18004049B
0x18004045c  mov     cs:?g_pWcnUpnpGit@@3PEAVCWcnUpnpGit@@EA, 0; CWcnUpnpGit * g_pWcnUpnpGit
0x180040467  mov     ebx, 8007000Eh
0x18004046c  mov     r10, cs:WPP_GLOBAL_Control
0x180040473  cmp     r10, rbp
0x180040476  jz      short loc_1800404A2
0x180040478  cmp     byte ptr [r10+19h], 2
0x18004047d  jb      short loc_1800404A2
0x18004047f  mov     edx, 28h ; '('
0x180040484  lea     r9, aGPwcnupnpgit; "g_pWcnUpnpGit"
0x18004048b  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x180040492  mov     rcx, [r10+10h]
0x180040496  call    WPP_SF_s
0x18004049b  mov     r10, cs:WPP_GLOBAL_Control
0x1800404a2  mov     rdi, cs:?g_pWcnUpnpGit@@3PEAVCWcnUpnpGit@@EA; CWcnUpnpGit * g_pWcnUpnpGit
0x1800404a9  test    rdi, rdi
0x1800404ac  jz      short loc_1800404EF
0x1800404ae  mov     rcx, [rdi+10h]
0x1800404b2  test    rcx, rcx
0x1800404b5  jz      short loc_1800404C4
0x1800404b7  mov     rax, [rcx]
0x1800404ba  mov     rax, [rax+10h]
0x1800404be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404c3  nop
0x1800404c4  mov     rcx, rdi
0x1800404c7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800404cd  mov     cs:?g_pWcnUpnpGit@@3PEAVCWcnUpnpGit@@EA, 0; CWcnUpnpGit * g_pWcnUpnpGit
0x1800404d8  jmp     short loc_1800404E8
0x1800404da  mov     eax, cs:?g_WcnUpnpGitRefCnt@@3JC; long volatile g_WcnUpnpGitRefCnt
0x1800404e0  add     eax, edi
0x1800404e2  mov     cs:?g_WcnUpnpGitRefCnt@@3JC, eax; long volatile g_WcnUpnpGitRefCnt
0x1800404e8  mov     r10, cs:WPP_GLOBAL_Control
0x1800404ef  cmp     r10, rbp
0x1800404f2  jz      short loc_180040523
0x1800404f4  test    ebx, ebx
0x1800404f6  js      short loc_1800404FF
0x1800404f8  cmp     byte ptr [r10+19h], 6
0x1800404fd  jb      short loc_180040523
0x1800404ff  or      ecx, 0FFFFFFFFh; int
0x180040502  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040507  mov     edx, 2Ah ; '*'
0x18004050c  mov     dword ptr [rsp+38h+ppv], ebx
0x180040510  mov     r9, rax
0x180040513  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x18004051a  mov     rcx, [r10+10h]
0x18004051e  call    WPP_SF_sd
0x180040523  mov     eax, ebx
0x180040525  mov     rbx, [rsp+38h+arg_0]
0x18004052a  mov     rbp, [rsp+38h+arg_8]
0x18004052f  add     rsp, 30h
0x180040533  pop     rdi
0x180040534  retn
```
