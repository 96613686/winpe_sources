# SettingsResolverNode::CreateInstance(tagProxySettings const *,_SID *,int,int,ulong,IProxyResolver *,SettingsResolverNode * *)

- ea: `0x180050458`
- end: `0x1800506b6`
- name: `?CreateInstance@SettingsResolverNode@@SAJPEBUtagProxySettings@@PEAU_SID@@HHKPEAUIProxyResolver@@PEAPEAV1@@Z`
- size: `606`
- prototype: `static int(const struct tagProxySettings *, struct _SID *, int, int, unsigned int, struct IProxyResolver *, struct SettingsResolverNode **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009920c`

## callees

- `0x180050458`
- `0x1800519e0`
- `0x1800526c0`
- `0x180052794`
- `0x1800a2660`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005061b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005061b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005060d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005060d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800504ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800504ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005054d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005054d`

## pseudocode

```c
__int64 __fastcall SettingsResolverNode::CreateInstance(
        const struct tagProxySettings *a1,
        struct _SID *a2,
        int a3,
        int a4,
        unsigned int a5,
        struct IProxyResolver *a6,
        struct SettingsResolverNode **a7)
{
  _OWORD *v7; // rbx
  HANDLE v11; // rcx
  char *v12; // rax
  char *v13; // rsi
  int v14; // edi
  _OWORD *v16; // rax
  _OWORD *v17; // rdi
  __int64 v18; // rcx
  int v19; // eax
  signed int LastError; // eax
  void *v21; // [rsp+20h] [rbp-58h] BYREF
  int v22; // [rsp+2Ch] [rbp-4Ch]
  int v23; // [rsp+30h] [rbp-48h]

  v7 = 0;
  v23 = a3;
  HIDWORD(v21) = 0;
  if ( !a7 )
  {
    v14 = -2147024809;
    HIDWORD(v21) = 541;
    return (unsigned int)v14;
  }
  v11 = g_hWxProcessHeap;
  *a7 = 0;
  v12 = (char *)HeapAlloc(v11, 0, 0x88u);
  v13 = v12;
  if ( !v12 )
  {
    v14 = -2147024882;
    HIDWORD(v21) = 546;
    return (unsigned int)v14;
  }
  memset_0(v12, 0, 0x88u);
  *(_DWORD *)v13 = 1;
  *((_QWORD *)v13 + 13) = v13 + 32;
  *((_DWORD *)v13 + 32) = 0;
  memset_0(v13 + 32, 0, 0x44u);
  v22 = 0;
  if ( !a1 )
  {
    v22 = 499;
    v14 = -2147024809;
LABEL_31:
    HIDWORD(v21) = 553;
    SettingsResolverNode::Release((SettingsResolverNode *)v13);
    return (unsigned int)v14;
  }
  v22 = 0;
  v21 = 0;
  v16 = CoTaskMemAlloc(0x70u);
  v17 = v16;
  if ( !v16 )
  {
    v14 = -2147024882;
    v22 = 501;
    goto LABEL_19;
  }
  memset_0(v16, 0, 0x70u);
  v7 = v17;
  v21 = v17;
  v14 = CopyProxySettings<WxCoTaskAllocator>((__int128 *)a1, v17);
  if ( v14 < 0 )
  {
    v22 = 504;
    goto LABEL_19;
  }
  if ( !a2 )
    goto LABEL_14;
  if ( CopySid(0x44u, *((PSID *)v13 + 13), a2) )
  {
    *((_DWORD *)v13 + 28) = GetLengthSid(*((PSID *)v13 + 13));
    v14 = 0;
LABEL_14:
    if ( a6 )
      (*(void (__fastcall **)(struct IProxyResolver *))(*(_QWORD *)a6 + 8LL))(a6);
    v18 = *((_QWORD *)v13 + 3);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v19 = v23;
    *((_QWORD *)v13 + 3) = a6;
    *((_QWORD *)v13 + 2) = v7;
    v7 = 0;
    *((_DWORD *)v13 + 30) = v19;
    v21 = 0;
    *((_DWORD *)v13 + 29) = a4;
    *((_DWORD *)v13 + 31) = a5;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
  v22 = 510;
  if ( v14 >= 0 )
    v14 = -2147418113;
LABEL_19:
  if ( v7 )
    ProxySettingsAllocator::Free((void ***)&v21);
  if ( v14 < 0 )
    goto LABEL_31;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 17, WPP_162471f81aa1348c530653e1923df6cd_Traceguids);
  *a7 = (struct SettingsResolverNode *)v13;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180050458  mov     [rsp+arg_10], rbx
0x18005045d  push    rbp
0x18005045e  push    rsi
0x18005045f  push    rdi
0x180050460  push    r12
0x180050462  push    r13
0x180050464  push    r14
0x180050466  push    r15
0x180050468  sub     rsp, 40h
0x18005046c  mov     r15, [rsp+78h+arg_30]
0x180050474  xor     ebx, ebx
0x180050476  mov     r14, [rsp+78h+arg_28]
0x18005047e  mov     r13d, r9d
0x180050481  mov     [rsp+78h+var_48], r8d
0x180050486  mov     rbp, rdx
0x180050489  mov     dword ptr [rsp+78h+var_58+4], ebx
0x18005048d  mov     r12, rcx
0x180050490  test    r15, r15
0x180050493  jz      loc_180050675
0x180050499  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800504a0  mov     edi, 88h
0x1800504a5  mov     r8d, edi; dwBytes
0x1800504a8  mov     [r15], rbx
0x1800504ab  xor     edx, edx; dwFlags
0x1800504ad  call    cs:__imp_HeapAlloc
0x1800504b3  mov     rsi, rax
0x1800504b6  test    rax, rax
0x1800504b9  jnz     short loc_180050506
0x1800504bb  mov     edi, 8007000Eh
0x1800504c0  mov     dword ptr [rsp+78h+var_58+4], 222h
0x1800504c8  jmp     short loc_1800504EC
0x1800504ca  lea     rcx, [rsp+78h+var_58]; void **
0x1800504cf  call    ?Free@ProxySettingsAllocator@@SAXPEAPEAX@Z; ProxySettingsAllocator::Free(void * *)
0x1800504d4  test    edi, edi
0x1800504d6  js      loc_180050694
0x1800504dc  test    byte ptr cs:xmmword_180107A60, 20h
0x1800504e3  jnz     loc_18005062B
0x1800504e9  mov     [r15], rsi
0x1800504ec  mov     rbx, [rsp+78h+arg_10]
0x1800504f4  mov     eax, edi
0x1800504f6  add     rsp, 40h
0x1800504fa  pop     r15
0x1800504fc  pop     r14
0x1800504fe  pop     r13
0x180050500  pop     r12
0x180050502  pop     rdi
0x180050503  pop     rsi
0x180050504  pop     rbp
0x180050505  retn
0x180050506  mov     r8, rdi; Size
0x180050509  xor     edx, edx; Val
0x18005050b  mov     rcx, rsi; void *
0x18005050e  call    memset_0
0x180050513  mov     dword ptr [rsi], 1
0x180050519  lea     rcx, [rsi+20h]; void *
0x18005051d  xor     edx, edx; Val
0x18005051f  mov     [rsi+68h], rcx
0x180050523  mov     [rsi+80h], ebx
0x180050529  lea     r8d, [rdx+44h]; Size
0x18005052d  call    memset_0
0x180050532  mov     [rsp+78h+var_4C], ebx
0x180050536  test    r12, r12
0x180050539  jz      loc_180050687
0x18005053f  mov     ecx, 70h ; 'p'; cb
0x180050544  mov     [rsp+78h+var_4C], ebx
0x180050548  mov     [rsp+78h+var_58], rbx
0x18005054d  call    cs:__imp_CoTaskMemAlloc
0x180050553  mov     rdi, rax
0x180050556  test    rax, rax
0x180050559  jz      loc_1800505EA
0x18005055f  xor     edx, edx; Val
0x180050561  mov     rcx, rax; void *
0x180050564  lea     r8d, [rdx+70h]; Size
0x180050568  call    memset_0
0x18005056d  mov     rbx, rdi
0x180050570  mov     [rsp+78h+var_58], rbx
0x180050575  mov     rdx, rdi
0x180050578  mov     rcx, r12
0x18005057b  call    ??$CopyProxySettings@VWxCoTaskAllocator@@@@YAJPEBUtagProxySettings@@PEAU0@@Z; CopyProxySettings<WxCoTaskAllocator>(tagProxySettings const *,tagProxySettings *)
0x180050580  mov     edi, eax
0x180050582  test    eax, eax
0x180050584  js      loc_1800506A9
0x18005058a  test    rbp, rbp
0x18005058d  jnz     short loc_180050601
0x18005058f  test    r14, r14
0x180050592  jz      short loc_1800505A3
0x180050594  mov     rax, [r14]
0x180050597  mov     rcx, r14
0x18005059a  mov     rax, [rax+8]
0x18005059e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505a3  mov     rcx, [rsi+18h]
0x1800505a7  test    rcx, rcx
0x1800505aa  jz      short loc_1800505B8
0x1800505ac  mov     rax, [rcx]
0x1800505af  mov     rax, [rax+10h]
0x1800505b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505b8  mov     eax, [rsp+78h+var_48]
0x1800505bc  mov     [rsi+18h], r14
0x1800505c0  mov     [rsi+10h], rbx
0x1800505c4  xor     ebx, ebx
0x1800505c6  mov     [rsi+78h], eax
0x1800505c9  mov     eax, [rsp+78h+arg_20]
0x1800505d0  mov     [rsp+78h+var_58], rbx
0x1800505d5  mov     [rsi+74h], r13d
0x1800505d9  mov     [rsi+7Ch], eax
0x1800505dc  test    rbx, rbx
0x1800505df  jnz     loc_1800504CA
0x1800505e5  jmp     loc_1800504D4
0x1800505ea  mov     [rsp+78h+var_4C], 4Ch ; 'L'
0x1800505f2  mov     edi, 8007000Eh
0x1800505f7  mov     [rsp+78h+var_4C], 1F5h
0x1800505ff  jmp     short loc_1800505DC
0x180050601  mov     rdx, [rsi+68h]; pDestinationSid
0x180050605  mov     r8, rbp; pSourceSid
0x180050608  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18005060d  call    cs:__imp_CopySid
0x180050613  test    eax, eax
0x180050615  jz      short loc_180050649
0x180050617  mov     rcx, [rsi+68h]; pSid
0x18005061b  call    cs:__imp_GetLengthSid
0x180050621  mov     [rsi+70h], eax
0x180050624  xor     edi, edi
0x180050626  jmp     loc_18005058F
0x18005062b  mov     edx, 11h
0x180050630  lea     r8, WPP_162471f81aa1348c530653e1923df6cd_Traceguids
0x180050637  mov     ecx, 405h
0x18005063c  mov     r9, rsi
0x18005063f  call    WPP_SF_q
0x180050644  jmp     loc_1800504E9
0x180050649  call    cs:__imp_GetLastError
0x18005064f  mov     edi, eax
0x180050651  test    eax, eax
0x180050653  jle     short loc_18005065E
0x180050655  movzx   edi, ax
0x180050658  or      edi, 80070000h
0x18005065e  test    edi, edi
0x180050660  mov     [rsp+78h+var_4C], 1FEh
0x180050668  mov     eax, 8000FFFFh
0x18005066d  cmovns  edi, eax
0x180050670  jmp     loc_1800505DC
0x180050675  mov     edi, 80070057h
0x18005067a  mov     dword ptr [rsp+78h+var_58+4], 21Dh
0x180050682  jmp     loc_1800504EC
0x180050687  mov     [rsp+78h+var_4C], 1F3h
0x18005068f  mov     edi, 80070057h
0x180050694  mov     rcx, rsi; this
0x180050697  mov     dword ptr [rsp+78h+var_58+4], 229h
0x18005069f  call    ?Release@SettingsResolverNode@@QEAAKXZ; SettingsResolverNode::Release(void)
0x1800506a4  jmp     loc_1800504EC
0x1800506a9  mov     [rsp+78h+var_4C], 1F8h
0x1800506b1  jmp     loc_1800505DC
```
