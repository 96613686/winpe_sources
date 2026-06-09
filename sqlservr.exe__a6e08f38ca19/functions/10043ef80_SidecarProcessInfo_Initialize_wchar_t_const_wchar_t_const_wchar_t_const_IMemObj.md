# SidecarProcessInfo::Initialize(wchar_t const *,wchar_t const *,wchar_t const *,IMemObj *)

- ea: `0x10043ef80`
- end: `0x10043f1b7`
- name: `?Initialize@SidecarProcessInfo@@QEAAJPEB_W00PEAVIMemObj@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(SidecarProcessInfo *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, struct IMemObj *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10043f6a0`

## callees

- `0x10043ef80`
- `0x1004404f0`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043efce`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043f076`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043f121`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043efce`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043f076`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043f121`

## string_xrefs

- `0x10043efaf`: `Sql\Ntdbms\xdb\containers\xdbcontainerscommon.cpp`
- `0x10043f057`: `Sql\Ntdbms\xdb\containers\xdbcontainerscommon.cpp`
- `0x10043f102`: `Sql\Ntdbms\xdb\containers\xdbcontainerscommon.cpp`
- `0x10043f0ea`: `[%hs] ERROR: Failed to initialize command line : %s`
- `0x10043f03f`: `[%hs] ERROR: Failed to initialize executin path : %s`
- `0x10043f038`: `SidecarProcessInfo::Initialize`
- `0x10043f0e3`: `SidecarProcessInfo::Initialize`
- `0x10043f17c`: `SidecarProcessInfo::Initialize`

## pseudocode

```c
__int64 __fastcall SidecarProcessInfo::Initialize(
        SidecarProcessInfo *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        struct IMemObj *a5)
{
  _WORD *v9; // rax
  _WORD *v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rcx
  char *v13; // r8
  __int16 v14; // ax
  _WORD *v15; // rax
  unsigned int v16; // edi
  unsigned int v17; // esi
  _WORD *v19; // rax
  _WORD *v20; // rdx
  __int64 v21; // r8
  char *v22; // r9
  __int16 v23; // ax
  _WORD *v24; // rax
  unsigned int v25; // esi
  _WORD *v26; // rax
  _WORD *v27; // rdx
  char *v28; // r8
  __int16 v29; // ax
  _WORD *v30; // rax

  v9 = operator new[](0x20Au, a5, 1, "Sql\\Ntdbms\\xdb\\containers\\xdbcontainerscommon.cpp", 49, 6u);
  *(_QWORD *)this = v9;
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  v11 = 261;
  v12 = 261;
  v13 = (char *)((char *)a2 - (char *)v9);
  do
  {
    if ( v12 == -2147483385 )
      break;
    v14 = *(_WORD *)((char *)v10 + (_QWORD)v13);
    if ( !v14 )
      break;
    *v10++ = v14;
    --v12;
  }
  while ( v12 );
  v15 = v10 - 1;
  v16 = -2147024774;
  if ( v12 )
    v15 = v10;
  v17 = -2147024774;
  if ( v12 )
    v17 = 0;
  *v15 = 0;
  if ( !v12 )
  {
    _mm_lfence();
    log_unlocalized(L"[%hs] ERROR: Failed to initialize executin path : %s", "SidecarProcessInfo::Initialize", a2);
    return v17;
  }
  v19 = operator new[](0x20Au, a5, 1, "Sql\\Ntdbms\\xdb\\containers\\xdbcontainerscommon.cpp", 62, 6u);
  *((_QWORD *)this + 1) = v19;
  v20 = v19;
  if ( !v19 )
    return 2147942414LL;
  v21 = 261;
  v22 = (char *)((char *)a3 - (char *)v19);
  do
  {
    if ( v21 == -2147483385 )
      break;
    v23 = *(_WORD *)((char *)v20 + (_QWORD)v22);
    if ( !v23 )
      break;
    *v20++ = v23;
    --v21;
  }
  while ( v21 );
  v24 = v20 - 1;
  v25 = -2147024774;
  if ( v21 )
  {
    v24 = v20;
    v25 = 0;
  }
  *v24 = 0;
  if ( !v21 )
  {
    _mm_lfence();
    log_unlocalized(L"[%hs] ERROR: Failed to initialize command line : %s", "SidecarProcessInfo::Initialize", a3, v22);
    return v25;
  }
  v26 = operator new[](0x20Au, a5, 1, "Sql\\Ntdbms\\xdb\\containers\\xdbcontainerscommon.cpp", 75, 6u);
  *((_QWORD *)this + 2) = v26;
  v27 = v26;
  if ( !v26 )
    return 2147942414LL;
  v28 = (char *)((char *)a4 - (char *)v26);
  do
  {
    if ( v11 == -2147483385 )
      break;
    v29 = *(_WORD *)((char *)v27 + (_QWORD)v28);
    if ( !v29 )
      break;
    *v27++ = v29;
    --v11;
  }
  while ( v11 );
  v30 = v27 - 1;
  if ( v11 )
  {
    v30 = v27;
    v16 = 0;
  }
  *v30 = 0;
  _mm_lfence();
  if ( !v11 )
    log_unlocalized(L"[%hs] ERROR: Failed to initialize source name : %s", "SidecarProcessInfo::Initialize", a4);
  return v16;
}

```

## disassembly

```asm
0x10043ef80  mov     [rsp+arg_0], rbx
0x10043ef85  mov     [rsp+arg_8], rbp
0x10043ef8a  mov     [rsp+arg_10], rsi
0x10043ef8f  mov     [rsp+arg_18], rdi
0x10043ef94  push    r13
0x10043ef96  push    r14
0x10043ef98  push    r15
0x10043ef9a  sub     rsp, 30h
0x10043ef9e  mov     r13, r9
0x10043efa1  mov     r14, r8
0x10043efa4  mov     rbp, rdx
0x10043efa7  mov     r15, rcx
0x10043efaa  mov     rdx, [rsp+48h+arg_20]
0x10043efaf  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\containers\\xdbcontai"...
0x10043efb6  mov     [rsp+48h+var_20], 6
0x10043efbb  mov     r8d, 1
0x10043efc1  mov     ecx, 20Ah
0x10043efc6  mov     [rsp+48h+var_28], 31h ; '1'
0x10043efce  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043efd4  mov     [r15], rax
0x10043efd7  mov     rdx, rax
0x10043efda  test    rax, rax
0x10043efdd  jz      loc_10043F193
0x10043efe3  mov     ebx, 105h
0x10043efe8  mov     r8, rbp
0x10043efeb  mov     ecx, ebx
0x10043efed  sub     r8, rax
0x10043eff0  lea     rax, [rcx+7FFFFEF9h]
0x10043eff7  test    rax, rax
0x10043effa  jz      short loc_10043F013
0x10043effc  movzx   eax, word ptr [r8+rdx]
0x10043f001  test    ax, ax
0x10043f004  jz      short loc_10043F013
0x10043f006  mov     [rdx], ax
0x10043f009  add     rdx, 2
0x10043f00d  sub     rcx, 1
0x10043f011  jnz     short loc_10043EFF0
0x10043f013  test    rcx, rcx
0x10043f016  lea     rax, [rdx-2]
0x10043f01a  mov     edi, 8007007Ah
0x10043f01f  cmovnz  rax, rdx
0x10043f023  mov     esi, edi
0x10043f025  xor     edx, edx
0x10043f027  test    rcx, rcx
0x10043f02a  cmovnz  esi, edx
0x10043f02d  mov     [rax], dx
0x10043f030  jnz     short loc_10043F052
0x10043f032  lfence
0x10043f035  mov     r8, rbp
0x10043f038  lea     rdx, aSidecarprocess; "SidecarProcessInfo::Initialize"
0x10043f03f  lea     rcx, aHsErrorFailedT_3; "[%hs] ERROR: Failed to initialize execu"...
0x10043f046  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f04b  mov     eax, esi
0x10043f04d  jmp     loc_10043F198
0x10043f052  mov     rdx, [rsp+48h+arg_20]
0x10043f057  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\containers\\xdbcontai"...
0x10043f05e  mov     [rsp+48h+var_20], 6
0x10043f063  mov     r8d, 1
0x10043f069  mov     ecx, 20Ah
0x10043f06e  mov     [rsp+48h+var_28], 3Eh ; '>'
0x10043f076  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043f07c  mov     [r15+8], rax
0x10043f080  mov     rdx, rax
0x10043f083  test    rax, rax
0x10043f086  jz      loc_10043F193
0x10043f08c  mov     r9, r14
0x10043f08f  mov     r8, rbx
0x10043f092  sub     r9, rax
0x10043f095  nop     word ptr [rax+rax+00000000h]
0x10043f0a0  lea     rcx, [r8+7FFFFEF9h]
0x10043f0a7  test    rcx, rcx
0x10043f0aa  jz      short loc_10043F0C3
0x10043f0ac  movzx   eax, word ptr [r9+rdx]
0x10043f0b1  test    ax, ax
0x10043f0b4  jz      short loc_10043F0C3
0x10043f0b6  mov     [rdx], ax
0x10043f0b9  add     rdx, 2
0x10043f0bd  sub     r8, 1
0x10043f0c1  jnz     short loc_10043F0A0
0x10043f0c3  test    r8, r8
0x10043f0c6  lea     rax, [rdx-2]
0x10043f0ca  mov     esi, edi
0x10043f0cc  cmovnz  rax, rdx
0x10043f0d0  xor     ebp, ebp
0x10043f0d2  test    r8, r8
0x10043f0d5  cmovnz  esi, ebp
0x10043f0d8  mov     [rax], bp
0x10043f0db  jnz     short loc_10043F0FD
0x10043f0dd  lfence
0x10043f0e0  mov     r8, r14
0x10043f0e3  lea     rdx, aSidecarprocess; "SidecarProcessInfo::Initialize"
0x10043f0ea  lea     rcx, aHsErrorFailedT_2; "[%hs] ERROR: Failed to initialize comma"...
0x10043f0f1  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f0f6  mov     eax, esi
0x10043f0f8  jmp     loc_10043F198
0x10043f0fd  mov     rdx, [rsp+48h+arg_20]
0x10043f102  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\containers\\xdbcontai"...
0x10043f109  mov     [rsp+48h+var_20], 6
0x10043f10e  mov     r8d, 1
0x10043f114  mov     ecx, 20Ah
0x10043f119  mov     [rsp+48h+var_28], 4Bh ; 'K'
0x10043f121  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043f127  mov     [r15+10h], rax
0x10043f12b  mov     rdx, rax
0x10043f12e  test    rax, rax
0x10043f131  jz      short loc_10043F193
0x10043f133  mov     r8, r13
0x10043f136  sub     r8, rax
0x10043f139  nop     dword ptr [rax+00000000h]
0x10043f140  lea     rcx, [rbx+7FFFFEF9h]
0x10043f147  test    rcx, rcx
0x10043f14a  jz      short loc_10043F163
0x10043f14c  movzx   eax, word ptr [r8+rdx]
0x10043f151  test    ax, ax
0x10043f154  jz      short loc_10043F163
0x10043f156  mov     [rdx], ax
0x10043f159  add     rdx, 2
0x10043f15d  sub     rbx, 1
0x10043f161  jnz     short loc_10043F140
0x10043f163  test    rbx, rbx
0x10043f166  lea     rax, [rdx-2]
0x10043f16a  cmovnz  rax, rdx
0x10043f16e  cmovnz  edi, ebp
0x10043f171  mov     [rax], bp
0x10043f174  lfence
0x10043f177  jnz     short loc_10043F18F
0x10043f179  mov     r8, r13
0x10043f17c  lea     rdx, aSidecarprocess; "SidecarProcessInfo::Initialize"
0x10043f183  lea     rcx, aHsErrorFailedT_0; "[%hs] ERROR: Failed to initialize sourc"...
0x10043f18a  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f18f  mov     eax, edi
0x10043f191  jmp     short loc_10043F198
0x10043f193  mov     eax, 8007000Eh
0x10043f198  mov     rbx, [rsp+48h+arg_0]
0x10043f19d  mov     rbp, [rsp+48h+arg_8]
0x10043f1a2  mov     rsi, [rsp+48h+arg_10]
0x10043f1a7  mov     rdi, [rsp+48h+arg_18]
0x10043f1ac  add     rsp, 30h
0x10043f1b0  pop     r15
0x10043f1b2  pop     r14
0x10043f1b4  pop     r13
0x10043f1b6  retn
```
