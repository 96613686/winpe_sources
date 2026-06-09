# CWerService::_ProcessConnectionRequest(_WERSVC_MSG *)

- ea: `0x18001d070`
- end: `0x18001d37a`
- name: `?_ProcessConnectionRequest@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180015d18`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180002a00`
- `0x1800035e8`
- `0x180006a80`
- `0x180011ef8`
- `0x180011f38`
- `0x18001d070`

## import_xrefs

- `ntdll!NtClose` at `0x18001d152`
- `ntdll!NtClose` at `0x18001d207`
- `ntdll!NtClose` at `0x18001d33e`
- `ntdll!NtClose` at `0x18001d152`
- `ntdll!NtClose` at `0x18001d207`
- `ntdll!NtClose` at `0x18001d33e`
- `ntdll!NtAlpcAcceptConnectPort` at `0x18001d236`
- `ntdll!NtAlpcAcceptConnectPort` at `0x18001d320`
- `ntdll!NtAlpcAcceptConnectPort` at `0x18001d236`
- `ntdll!NtAlpcAcceptConnectPort` at `0x18001d320`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001d1e5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001d1e5`

## pseudocode

```c
__int64 __fastcall CWerService::_ProcessConnectionRequest(CWerService *this, struct _WERSVC_MSG *a2)
{
  unsigned int v4; // r14d
  int v5; // r15d
  HANDLE *v6; // rcx
  PVOID *i; // rbx
  _QWORD *v8; // rax
  HANDLE *v9; // rdi
  _OWORD *v10; // r14
  PVOID v11; // rax
  PVOID v12; // rdi
  PVOID v13; // r15
  __int64 v14; // r12
  void *v15; // rcx
  int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // rdx
  HANDLE *v19; // rsi
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+80h] [rbp-80h]
  __int128 v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+A0h] [rbp-60h]
  _OWORD v26[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  __int128 v29; // [rsp+E0h] [rbp-20h]
  int v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+F4h] [rbp-Ch]

  memset_0(v26, 0, 0x48u);
  v4 = *((_DWORD *)a2 + 2);
  v5 = *((_DWORD *)a2 + 4);
  v6 = (HANDLE *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      v4,
      *((_DWORD *)a2 + 4));
    v6 = (HANDLE *)WPP_GLOBAL_Control;
  }
  for ( i = (PVOID *)*((_QWORD *)this + 45); ; ++i )
  {
    if ( i == *((PVOID **)this + 46) )
    {
      i = 0;
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
        WPP_SF_(v6[2], 89, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
      v17 = -805305802;
LABEL_34:
      v18 = *((_QWORD *)this + 49);
      v21 = 0;
      NtAlpcAcceptConnectPort(&v21, v18, 0, 0, 0, 0, a2, 0, 0);
      if ( !i )
        return v17;
      goto LABEL_35;
    }
    if ( !*i )
      break;
  }
  v8 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
  {
    *v8 = 0;
    v8[1] = 0;
  }
  else
  {
    v8 = 0;
  }
  v9 = (HANDLE *)*i;
  *i = v8;
  if ( v9 )
  {
    if ( *v9 )
      NtClose(*v9);
    operator delete(v9, (const struct std::nothrow_t *)0x10);
  }
  if ( !*i )
  {
    v17 = -2147024882;
    goto LABEL_34;
  }
  *((_DWORD *)*i + 2) = v4;
  *((_DWORD *)*i + 3) = v5;
  if ( *((__int16 *)a2 + 2) < 0 )
  {
    v10 = v26;
    memset_0(&v22, 0, 0x48u);
    v26[0] = v22;
    v28 = *((_QWORD *)&v23 + 1);
    v31 = HIDWORD(v25);
    v26[1] = _mm_load_si128((const __m128i *)&_xmm);
    v29 = v24;
    LODWORD(v26[0]) = 0x80000;
    v30 = 4;
    v27 = 89600;
  }
  else
  {
    v10 = 0;
  }
  v11 = EncodePointer(*i);
  v12 = *i;
  v13 = v11;
  v14 = *((_QWORD *)this + 49);
  v15 = *(void **)*i;
  *(_QWORD *)*i = 0;
  if ( v15 )
    NtClose(v15);
  v16 = NtAlpcAcceptConnectPort(v12, v14, 0, 0, v10, v13, a2, 0, 1);
  v17 = v16 | 0x10000000;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v17);
LABEL_35:
    v19 = (HANDLE *)*i;
    if ( *i )
    {
      *i = 0;
      if ( *v19 )
        NtClose(*v19);
      operator delete(v19, (const struct std::nothrow_t *)0x10);
    }
    return v17;
  }
  *((_DWORD *)this + 53) |= 2u;
  v17 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  return v17;
}

```

## disassembly

```asm
0x18001d070  mov     [rsp-8+arg_10], rbx
0x18001d075  push    rbp
0x18001d076  push    rsi
0x18001d077  push    rdi
0x18001d078  push    r12
0x18001d07a  push    r13
0x18001d07c  push    r14
0x18001d07e  push    r15
0x18001d080  lea     rbp, [rsp-10h]
0x18001d085  sub     rsp, 110h
0x18001d08c  mov     rax, cs:__security_cookie
0x18001d093  xor     rax, rsp
0x18001d096  mov     [rbp+40h+var_40], rax
0x18001d09a  mov     r13, rdx
0x18001d09d  mov     rsi, rcx
0x18001d0a0  xor     edx, edx; Val
0x18001d0a2  lea     rcx, [rbp+40h+var_90]; void *
0x18001d0a6  lea     r8d, [rdx+48h]; Size
0x18001d0aa  call    memset_0
0x18001d0af  mov     r14d, [r13+8]
0x18001d0b3  mov     r15d, [r13+10h]
0x18001d0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0be  lea     rax, WPP_GLOBAL_Control
0x18001d0c5  cmp     rcx, rax
0x18001d0c8  jz      short loc_18001D0FB
0x18001d0ca  test    byte ptr [rcx+1Ch], 4
0x18001d0ce  jz      short loc_18001D0FB
0x18001d0d0  mov     rcx, [rcx+10h]
0x18001d0d4  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d0db  mov     edx, 58h ; 'X'
0x18001d0e0  mov     dword ptr [rsp+140h+var_120], r15d
0x18001d0e5  mov     r9d, r14d
0x18001d0e8  call    WPP_SF_Dd
0x18001d0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0f4  lea     rax, WPP_GLOBAL_Control
0x18001d0fb  mov     rbx, [rsi+168h]
0x18001d102  xor     r12d, r12d
0x18001d105  cmp     rbx, [rsi+170h]
0x18001d10c  jz      loc_18001D2C8
0x18001d112  cmp     [rbx], r12
0x18001d115  jz      short loc_18001D11D
0x18001d117  add     rbx, 8
0x18001d11b  jmp     short loc_18001D105
0x18001d11d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d124  mov     ecx, 10h; unsigned __int64
0x18001d129  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d12e  test    rax, rax
0x18001d131  jz      short loc_18001D13C
0x18001d133  mov     [rax], r12
0x18001d136  mov     [rax+8], r12
0x18001d13a  jmp     short loc_18001D13F
0x18001d13c  mov     rax, r12
0x18001d13f  mov     rdi, [rbx]
0x18001d142  mov     [rbx], rax
0x18001d145  test    rdi, rdi
0x18001d148  jz      short loc_18001D165
0x18001d14a  mov     rcx, [rdi]; Handle
0x18001d14d  test    rcx, rcx
0x18001d150  jz      short loc_18001D158
0x18001d152  call    cs:__imp_NtClose
0x18001d158  mov     edx, 10h; struct std::nothrow_t *
0x18001d15d  mov     rcx, rdi; void *
0x18001d160  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d165  mov     rax, [rbx]
0x18001d168  test    rax, rax
0x18001d16b  jz      loc_18001D2C1
0x18001d171  mov     [rax+8], r14d
0x18001d175  mov     rax, [rbx]
0x18001d178  mov     [rax+0Ch], r15d
0x18001d17c  cmp     [r13+4], r12w
0x18001d181  jl      short loc_18001D188
0x18001d183  mov     r14, r12
0x18001d186  jmp     short loc_18001D1E2
0x18001d188  xor     edx, edx; Val
0x18001d18a  lea     rcx, [rsp+140h+var_E0]; void *
0x18001d18f  lea     r14, [rbp+40h+var_90]
0x18001d193  lea     r8d, [rdx+48h]; Size
0x18001d197  call    memset_0
0x18001d19c  movaps  xmm0, [rsp+140h+var_E0]
0x18001d1a1  movaps  xmm1, [rbp+40h+var_B0]
0x18001d1a5  movaps  [rbp+40h+var_90], xmm0
0x18001d1a9  movaps  xmm0, [rbp+40h+var_C0]
0x18001d1ad  movaps  [rbp+40h+var_70], xmm0
0x18001d1b1  movsd   xmm0, [rbp+40h+var_A0]
0x18001d1b6  movsd   qword ptr [rbp+40h+var_50], xmm0
0x18001d1bb  movdqa  xmm0, cs:__xmm@00000000000000000000000000000578
0x18001d1c3  movdqa  [rbp+40h+var_80], xmm0
0x18001d1c8  movaps  [rbp+40h+var_60], xmm1
0x18001d1cc  mov     dword ptr [rbp+40h+var_90], 80000h
0x18001d1d3  mov     [rbp+40h+var_50], 4
0x18001d1da  mov     qword ptr [rbp+40h+var_70], 15E00h
0x18001d1e2  mov     rcx, [rbx]; Ptr
0x18001d1e5  call    cs:__imp_EncodePointer
0x18001d1eb  mov     rdi, [rbx]
0x18001d1ee  mov     r15, rax
0x18001d1f1  mov     r12, [rsi+188h]
0x18001d1f8  mov     rcx, [rdi]; Handle
0x18001d1fb  mov     qword ptr [rdi], 0
0x18001d202  test    rcx, rcx
0x18001d205  jz      short loc_18001D20D
0x18001d207  call    cs:__imp_NtClose
0x18001d20d  mov     [rsp+140h+var_100], 1
0x18001d212  xor     r9d, r9d
0x18001d215  mov     [rsp+140h+var_108], 0
0x18001d21e  xor     r8d, r8d
0x18001d221  mov     [rsp+140h+var_110], r13
0x18001d226  mov     rdx, r12
0x18001d229  mov     [rsp+140h+var_118], r15
0x18001d22e  mov     rcx, rdi
0x18001d231  mov     [rsp+140h+var_120], r14
0x18001d236  call    cs:__imp_NtAlpcAcceptConnectPort
0x18001d23c  mov     edi, eax
0x18001d23e  or      edi, 10000000h
0x18001d244  jge     short loc_18001D27F
0x18001d246  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d24d  lea     rax, WPP_GLOBAL_Control
0x18001d254  cmp     rcx, rax
0x18001d257  jz      short loc_18001D277
0x18001d259  test    byte ptr [rcx+1Ch], 1
0x18001d25d  jz      short loc_18001D277
0x18001d25f  mov     rcx, [rcx+10h]
0x18001d263  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d26a  mov     edx, 5Ah ; 'Z'
0x18001d26f  mov     r9d, edi
0x18001d272  call    WPP_SF_d
0x18001d277  xor     r12d, r12d
0x18001d27a  jmp     loc_18001D32B
0x18001d27f  or      dword ptr [rsi+0D4h], 2
0x18001d286  xor     edi, edi
0x18001d288  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d28f  lea     rax, WPP_GLOBAL_Control
0x18001d296  cmp     rcx, rax
0x18001d299  jz      loc_18001D351
0x18001d29f  test    byte ptr [rcx+1Ch], 4
0x18001d2a3  jz      loc_18001D351
0x18001d2a9  mov     rcx, [rcx+10h]
0x18001d2ad  lea     edx, [rdi+5Bh]
0x18001d2b0  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d2b7  call    WPP_SF_
0x18001d2bc  jmp     loc_18001D351
0x18001d2c1  mov     edi, 8007000Eh
0x18001d2c6  jmp     short loc_18001D2F0
0x18001d2c8  mov     rbx, r12
0x18001d2cb  cmp     rcx, rax
0x18001d2ce  jz      short loc_18001D2EB
0x18001d2d0  test    byte ptr [rcx+1Ch], 1
0x18001d2d4  jz      short loc_18001D2EB
0x18001d2d6  mov     rcx, [rcx+10h]
0x18001d2da  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d2e1  mov     edx, 59h ; 'Y'
0x18001d2e6  call    WPP_SF_
0x18001d2eb  mov     edi, 0D0000236h
0x18001d2f0  mov     rdx, [rsi+188h]
0x18001d2f7  lea     rcx, [rsp+140h+var_F0]
0x18001d2fc  mov     [rsp+140h+var_100], r12b
0x18001d301  xor     r9d, r9d
0x18001d304  mov     [rsp+140h+var_108], r12
0x18001d309  xor     r8d, r8d
0x18001d30c  mov     [rsp+140h+var_110], r13
0x18001d311  mov     [rsp+140h+var_118], r12
0x18001d316  mov     [rsp+140h+var_120], r12
0x18001d31b  mov     [rsp+140h+var_F0], r12
0x18001d320  call    cs:__imp_NtAlpcAcceptConnectPort
0x18001d326  test    rbx, rbx
0x18001d329  jz      short loc_18001D351
0x18001d32b  mov     rsi, [rbx]
0x18001d32e  test    rsi, rsi
0x18001d331  jz      short loc_18001D351
0x18001d333  mov     [rbx], r12
0x18001d336  mov     rcx, [rsi]; Handle
0x18001d339  test    rcx, rcx
0x18001d33c  jz      short loc_18001D344
0x18001d33e  call    cs:__imp_NtClose
0x18001d344  mov     edx, 10h; struct std::nothrow_t *
0x18001d349  mov     rcx, rsi; void *
0x18001d34c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d351  mov     eax, edi
0x18001d353  mov     rcx, [rbp+40h+var_40]
0x18001d357  xor     rcx, rsp; StackCookie
0x18001d35a  call    __security_check_cookie
0x18001d35f  mov     rbx, [rsp+140h+arg_10]
0x18001d367  add     rsp, 110h
0x18001d36e  pop     r15
0x18001d370  pop     r14
0x18001d372  pop     r13
0x18001d374  pop     r12
0x18001d376  pop     rdi
0x18001d377  pop     rsi
0x18001d378  pop     rbp
0x18001d379  retn
```
