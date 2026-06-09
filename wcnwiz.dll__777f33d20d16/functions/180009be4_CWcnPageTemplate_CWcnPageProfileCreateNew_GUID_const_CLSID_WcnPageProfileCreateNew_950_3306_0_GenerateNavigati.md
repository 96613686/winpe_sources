# CWcnPageTemplate<CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,950,3306,0>::GenerateNavigationEvents(CWcnPageProfileCreateNew *,uint,unsigned __int64,__int64,__int64 &)

- ea: `0x180009be4`
- end: `0x180009d53`
- name: `?GenerateNavigationEvents@?$CWcnPageTemplate@VCWcnPageProfileCreateNew@@$1?CLSID_WcnPageProfileCreateNew@@3U_GUID@@B$0DLG@$0MOK@$0A@@@SAHPEAVCWcnPageProfileCreateNew@@I_K_JAEA_J@Z`
- size: `367`
- prototype: `__int64 __usercall@<rax>(CWcnPageProfileCreateNew *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aafc`

## callees

- `0x180009be4`
- `0x180014880`
- `0x180014cdc`
- `0x180014da0`
- `0x180014fe8`
- `0x18001515c`
- `0x1800153e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009c86`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009c86`
- `USER32!PostMessageW` at `0x180009c7b`
- `USER32!PostMessageW` at `0x180009c7b`
- `USER32!KillTimer` at `0x180009cd5`
- `USER32!KillTimer` at `0x180009cd5`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,950,3306,0>::GenerateNavigationEvents(
        HWND *this,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5)
{
  unsigned int v5; // ebx
  int v8; // edx
  int v9; // edx
  int v10; // eax
  char active; // al
  const struct _GUID *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx

  v5 = 0;
  v8 = a2 - 78;
  if ( v8 )
  {
    v9 = v8 - 194;
    if ( v9 )
    {
      if ( v9 == 3 )
      {
        *a5 = 0;
        return 1;
      }
    }
    else
    {
      CWcnPageProfileCreateNew::OnInitDialog((CWcnPageProfileCreateNew *)this);
    }
    return v5;
  }
  v10 = *(_DWORD *)(a4 + 16);
  if ( v10 == -207 )
  {
    v12 = CWcnPageProfileCreateNew::OnWizardNext((CWcnPageProfileCreateNew *)this);
    v13 = (__int64)v12;
    if ( v12 )
    {
      v14 = *(_QWORD *)&v12->Data1 - *(_QWORD *)&CLSID_WcnPageProfileCreateNew.Data1;
      if ( *(_QWORD *)&v12->Data1 == *(_QWORD *)&CLSID_WcnPageProfileCreateNew.Data1 )
        v14 = *(_QWORD *)v12->Data4 - *(_QWORD *)CLSID_WcnPageProfileCreateNew.Data4;
      if ( !v14 )
        v13 = -1;
      *a5 = v13;
      return 1;
    }
    return v5;
  }
  if ( v10 == -206 )
    return v5;
  if ( v10 != -201 )
  {
    if ( v10 != -200 )
      return v5;
    if ( ((_BYTE)this[24][222] & 2) != 0 )
    {
      PostMessageW(this[21], 0x471u, 2u, 0);
      return v5;
    }
    this[23] = (HWND)GetTickCount64();
    if ( a3 == 4294967089LL )
    {
      if ( !CWcnPageProfileCreateNew::OnSetActiveForward((CWcnPageProfileCreateNew *)this) )
        goto LABEL_15;
    }
    else if ( a3 != 4294967090LL )
    {
      return v5;
    }
    if ( CWcnPageProfileCreateNew::OnSetActive((CWcnPageProfileCreateNew *)this) )
      return v5;
LABEL_15:
    *a5 = -1;
    return 1;
  }
  KillTimer(this[21], 0x6C726143u);
  if ( a3 == 4294967089LL )
  {
    active = CWcnPageProfileCreateNew::OnKillActiveForward((CWcnPageProfileCreateNew *)this);
  }
  else
  {
    if ( a3 != 4294967090LL )
      return v5;
    active = CWcnPageProfileCreateNew::OnKillActiveBackward((CWcnPageProfileCreateNew *)this);
  }
  if ( !active )
  {
    v5 = 1;
    *a5 = 1;
  }
  return v5;
}

```

## disassembly

```asm
0x180009be4  push    rbx
0x180009be6  push    rbp
0x180009be7  push    rsi
0x180009be8  push    rdi
0x180009be9  push    r14
0x180009beb  sub     rsp, 20h
0x180009bef  xor     ebx, ebx
0x180009bf1  mov     rsi, r8
0x180009bf4  mov     rdi, rcx
0x180009bf7  sub     edx, 4Eh ; 'N'
0x180009bfa  jz      short loc_180009C24
0x180009bfc  sub     edx, 0C2h
0x180009c02  jz      short loc_180009C1A
0x180009c04  cmp     edx, 3
0x180009c07  jnz     loc_180009D46
0x180009c0d  mov     rax, [rsp+48h+arg_20]
0x180009c12  mov     [rax], rbx
0x180009c15  jmp     loc_180009D41
0x180009c1a  call    ?OnInitDialog@CWcnPageProfileCreateNew@@QEAAXXZ; CWcnPageProfileCreateNew::OnInitDialog(void)
0x180009c1f  jmp     loc_180009D46
0x180009c24  mov     eax, [r9+10h]
0x180009c28  mov     r14d, 0FFFFFF31h
0x180009c2e  cmp     eax, r14d
0x180009c31  jz      loc_180009D0A
0x180009c37  mov     ebp, 0FFFFFF32h
0x180009c3c  cmp     eax, ebp
0x180009c3e  jz      loc_180009D46
0x180009c44  cmp     eax, 0FFFFFF37h
0x180009c49  jz      short loc_180009CC9
0x180009c4b  cmp     eax, 0FFFFFF38h
0x180009c50  jnz     loc_180009D46
0x180009c56  mov     rax, [rcx+0C0h]
0x180009c5d  mov     r8d, 2; wParam
0x180009c63  test    [rax+378h], r8b
0x180009c6a  jz      short loc_180009C86
0x180009c6c  mov     rcx, [rcx+0A8h]; hWnd
0x180009c73  xor     r9d, r9d; lParam
0x180009c76  mov     edx, 471h; Msg
0x180009c7b  call    cs:__imp_PostMessageW
0x180009c81  jmp     loc_180009D46
0x180009c86  call    cs:__imp_GetTickCount64
0x180009c8c  mov     [rdi+0B8h], rax
0x180009c93  cmp     rsi, r14
0x180009c96  jnz     short loc_180009CC2
0x180009c98  mov     rcx, rdi; this
0x180009c9b  call    ?OnSetActiveForward@CWcnPageProfileCreateNew@@QEAA_NXZ; CWcnPageProfileCreateNew::OnSetActiveForward(void)
0x180009ca0  test    al, al
0x180009ca2  jz      short loc_180009CB4
0x180009ca4  mov     rcx, rdi; this
0x180009ca7  call    ?OnSetActive@CWcnPageProfileCreateNew@@QEAA_NXZ; CWcnPageProfileCreateNew::OnSetActive(void)
0x180009cac  test    al, al
0x180009cae  jnz     loc_180009D46
0x180009cb4  mov     rax, [rsp+48h+arg_20]
0x180009cb9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009cbd  mov     [rax], rdx
0x180009cc0  jmp     short loc_180009D41
0x180009cc2  cmp     rsi, rbp
0x180009cc5  jnz     short loc_180009D46
0x180009cc7  jmp     short loc_180009CA4
0x180009cc9  mov     rcx, [rcx+0A8h]; hWnd
0x180009cd0  mov     edx, 6C726143h; uIDEvent
0x180009cd5  call    cs:__imp_KillTimer
0x180009cdb  cmp     rsi, r14
0x180009cde  jnz     short loc_180009CEA
0x180009ce0  mov     rcx, rdi; this
0x180009ce3  call    ?OnKillActiveForward@CWcnPageProfileCreateNew@@QEAA_NXZ; CWcnPageProfileCreateNew::OnKillActiveForward(void)
0x180009ce8  jmp     short loc_180009CF7
0x180009cea  cmp     rsi, rbp
0x180009ced  jnz     short loc_180009D46
0x180009cef  mov     rcx, rdi; this
0x180009cf2  call    ?OnKillActiveBackward@CWcnPageProfileCreateNew@@QEAA_NXZ; CWcnPageProfileCreateNew::OnKillActiveBackward(void)
0x180009cf7  test    al, al
0x180009cf9  jnz     short loc_180009D46
0x180009cfb  mov     rax, [rsp+48h+arg_20]
0x180009d00  mov     ebx, 1
0x180009d05  mov     [rax], rbx
0x180009d08  jmp     short loc_180009D46
0x180009d0a  call    ?OnWizardNext@CWcnPageProfileCreateNew@@QEAAPEBU_GUID@@XZ; CWcnPageProfileCreateNew::OnWizardNext(void)
0x180009d0f  mov     r8, rax
0x180009d12  test    rax, rax
0x180009d15  jz      short loc_180009D46
0x180009d17  mov     rcx, [rax]
0x180009d1a  sub     rcx, qword ptr cs:CLSID_WcnPageProfileCreateNew.Data1
0x180009d21  jnz     short loc_180009D2E
0x180009d23  mov     rcx, [rax+8]
0x180009d27  sub     rcx, qword ptr cs:CLSID_WcnPageProfileCreateNew.Data4
0x180009d2e  mov     rax, [rsp+48h+arg_20]
0x180009d33  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009d37  test    rcx, rcx
0x180009d3a  cmovz   r8, rdx
0x180009d3e  mov     [rax], r8
0x180009d41  mov     ebx, 1
0x180009d46  mov     eax, ebx
0x180009d48  add     rsp, 20h
0x180009d4c  pop     r14
0x180009d4e  pop     rdi
0x180009d4f  pop     rsi
0x180009d50  pop     rbp
0x180009d51  pop     rbx
0x180009d52  retn
```
