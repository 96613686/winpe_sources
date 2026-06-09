# WcnpRpcCreateManagementHandle

- ea: `0x180034d20`
- end: `0x180034eba`
- name: `WcnpRpcCreateManagementHandle`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180034d20`
- `0x18003aa08`
- `0x18003bdb0`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180034e72`
- `msvcrt!??3@YAXPEAX@Z` at `0x180034e72`

## pseudocode

```c
__int64 __fastcall WcnpRpcCreateManagementHandle(__int64 a1, CWcnRpcHandle **a2)
{
  _QWORD *v3; // r10
  const char *Indent; // rax
  __int64 v5; // r10
  int v7; // eax
  int v8; // ebx
  _BYTE *v9; // r10
  _BYTE *v10; // rax
  CWcnRpcHandle *v11; // rcx
  CWcnRpcHandle *v12; // rdi
  unsigned int v13; // eax
  __int64 v14; // r10
  CWcnRpcHandle *v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 164, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, Indent);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) >= 2u )
      WPP_SF_s(v3[2], 165, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, "phManagement");
    return 2147500035LL;
  }
  v7 = CWcnRpcHandleTracker::CreateRpcHandle(*((_QWORD *)g_pWcnService + 7) + 1408LL, 3, &v15);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_19;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      166,
      WPP_b6f763267c4d324c721a67068f3e4818_Traceguids,
      (unsigned int)v7);
    goto LABEL_18;
  }
  v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
  {
    v11 = v15;
    v10[16] = 0;
    *((_QWORD *)v11 + 1) = v10;
    *a2 = v11;
    goto LABEL_21;
  }
  v8 = -2147024882;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, "pNewMgmt");
LABEL_18:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_19:
  v12 = v15;
  if ( !v15 )
    goto LABEL_22;
  CWcnRpcHandle::~CWcnRpcHandle(v15);
  operator delete(v12);
LABEL_21:
  v9 = WPP_GLOBAL_Control;
LABEL_22:
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && (v8 < 0 || v9[25] >= 6u) )
  {
    v13 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v14 + 16), 168, (unsigned int)WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v13, v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180034d20  push    rbx
0x180034d22  push    rbp
0x180034d23  push    rsi
0x180034d24  push    rdi
0x180034d25  sub     rsp, 38h
0x180034d29  mov     rdi, rdx
0x180034d2c  mov     [rsp+58h+arg_8], 0
0x180034d35  mov     r10, cs:WPP_GLOBAL_Control
0x180034d3c  lea     rsi, WPP_GLOBAL_Control
0x180034d43  lea     rbp, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180034d4a  cmp     r10, rsi
0x180034d4d  jz      short loc_180034D7B
0x180034d4f  cmp     byte ptr [r10+19h], 6
0x180034d54  jb      short loc_180034D7B
0x180034d56  mov     ecx, 1; int
0x180034d5b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180034d60  mov     rcx, [r10+10h]
0x180034d64  mov     edx, 0A4h
0x180034d69  mov     r9, rax
0x180034d6c  mov     r8, rbp
0x180034d6f  call    WPP_SF_s
0x180034d74  mov     r10, cs:WPP_GLOBAL_Control
0x180034d7b  test    rdi, rdi
0x180034d7e  jnz     short loc_180034DAE
0x180034d80  cmp     r10, rsi
0x180034d83  jz      short loc_180034DA4
0x180034d85  cmp     byte ptr [r10+19h], 2
0x180034d8a  jb      short loc_180034DA4
0x180034d8c  mov     rcx, [r10+10h]
0x180034d90  lea     r9, aPhmanagement; "phManagement"
0x180034d97  mov     edx, 0A5h
0x180034d9c  mov     r8, rbp
0x180034d9f  call    WPP_SF_s
0x180034da4  mov     eax, 80004003h
0x180034da9  jmp     loc_180034EB1
0x180034dae  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x180034db5  lea     r8, [rsp+58h+arg_8]
0x180034dba  mov     edx, 3
0x180034dbf  mov     rcx, [rax+38h]
0x180034dc3  add     rcx, 580h
0x180034dca  call    ?CreateRpcHandle@CWcnRpcHandleTracker@@QEAAJW4tagWCNPRPC_HANDLE_TYPE@@PEAPEAVCWcnRpcHandle@@@Z; CWcnRpcHandleTracker::CreateRpcHandle(tagWCNPRPC_HANDLE_TYPE,CWcnRpcHandle * *)
0x180034dcf  mov     ebx, eax
0x180034dd1  test    eax, eax
0x180034dd3  jns     short loc_180034DFE
0x180034dd5  mov     r10, cs:WPP_GLOBAL_Control
0x180034ddc  cmp     r10, rsi
0x180034ddf  jz      short loc_180034E5D
0x180034de1  cmp     byte ptr [r10+19h], 2
0x180034de6  jb      short loc_180034E5D
0x180034de8  mov     rcx, [r10+10h]
0x180034dec  mov     edx, 0A6h
0x180034df1  mov     r9d, eax
0x180034df4  mov     r8, rbp
0x180034df7  call    WPP_SF_d
0x180034dfc  jmp     short loc_180034E56
0x180034dfe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034e05  mov     ecx, 18h; unsigned __int64
0x180034e0a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034e0f  test    rax, rax
0x180034e12  jz      short loc_180034E26
0x180034e14  mov     rcx, [rsp+58h+arg_8]
0x180034e19  mov     byte ptr [rax+10h], 0
0x180034e1d  mov     [rcx+8], rax
0x180034e21  mov     [rdi], rcx
0x180034e24  jmp     short loc_180034E78
0x180034e26  mov     ebx, 8007000Eh
0x180034e2b  mov     r10, cs:WPP_GLOBAL_Control
0x180034e32  cmp     r10, rsi
0x180034e35  jz      short loc_180034E5D
0x180034e37  cmp     byte ptr [r10+19h], 2
0x180034e3c  jb      short loc_180034E5D
0x180034e3e  mov     rcx, [r10+10h]
0x180034e42  lea     r9, aPnewmgmt; "pNewMgmt"
0x180034e49  mov     edx, 0A7h
0x180034e4e  mov     r8, rbp
0x180034e51  call    WPP_SF_s
0x180034e56  mov     r10, cs:WPP_GLOBAL_Control
0x180034e5d  mov     rdi, [rsp+58h+arg_8]
0x180034e62  test    rdi, rdi
0x180034e65  jz      short loc_180034E7F
0x180034e67  mov     rcx, rdi; this
0x180034e6a  call    ??1CWcnRpcHandle@@QEAA@XZ; CWcnRpcHandle::~CWcnRpcHandle(void)
0x180034e6f  mov     rcx, rdi
0x180034e72  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180034e78  mov     r10, cs:WPP_GLOBAL_Control
0x180034e7f  cmp     r10, rsi
0x180034e82  jz      short loc_180034EAF
0x180034e84  test    ebx, ebx
0x180034e86  js      short loc_180034E8F
0x180034e88  cmp     byte ptr [r10+19h], 6
0x180034e8d  jb      short loc_180034EAF
0x180034e8f  or      ecx, 0FFFFFFFFh; int
0x180034e92  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180034e97  mov     rcx, [r10+10h]
0x180034e9b  mov     edx, 0A8h
0x180034ea0  mov     r9, rax
0x180034ea3  mov     [rsp+58h+var_38], ebx
0x180034ea7  mov     r8, rbp
0x180034eaa  call    WPP_SF_sd
0x180034eaf  mov     eax, ebx
0x180034eb1  add     rsp, 38h
0x180034eb5  pop     rdi
0x180034eb6  pop     rsi
0x180034eb7  pop     rbp
0x180034eb8  pop     rbx
0x180034eb9  retn
```
