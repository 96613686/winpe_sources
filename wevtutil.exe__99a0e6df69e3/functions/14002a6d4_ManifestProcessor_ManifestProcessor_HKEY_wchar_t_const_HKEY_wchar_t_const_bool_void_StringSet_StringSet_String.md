# ManifestProcessor::ManifestProcessor(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,bool,void *,StringSet &,StringSet &,StringSet &,StringSet &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)

- ea: `0x14002a6d4`
- end: `0x14002a80e`
- name: `??0ManifestProcessor@@QEAA@PEAUHKEY__@@PEB_W01_NPEAXAEAVStringSet@@444V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@552@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140001ce0`

## callees

- `0x140005600`
- `0x140022cec`
- `0x14002a6d4`
- `0x14002aac4`
- `0x14002f284`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ManifestProcessor::ManifestProcessor(
        __int64 a1,
        HKEY a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int128 *a12,
        __int128 *a13,
        __int128 *a14,
        char a15)
{
  RegistryPaths *v18; // rcx
  const wchar_t *v19; // r8
  unsigned int v20; // ebx
  __int128 v22; // [rsp+30h] [rbp-48h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v24; // [rsp+58h] [rbp-20h]
  __int64 v25; // [rsp+5Ch] [rbp-1Ch]
  char v26; // [rsp+64h] [rbp-14h]

  *(_BYTE *)a1 = a6;
  *(_BYTE *)(a1 + 1) = a15;
  *(_QWORD *)(a1 + 8) = a7;
  *(_QWORD *)(a1 + 16) = a8;
  *(_QWORD *)(a1 + 24) = a9;
  *(_QWORD *)(a1 + 32) = a10;
  *(_QWORD *)(a1 + 40) = a11;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a1 + 48);
  v22 = *a12;
  CopyOrThrow(a1 + 80, &v22);
  v22 = *a13;
  CopyOrThrow(a1 + 112, &v22);
  v22 = *a14;
  CopyOrThrow(a1 + 144, &v22);
  v20 = RegistryPaths::Initialize(v18, a2, v19, a4);
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v20);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v24 = v20;
    v25 = -1;
    v26 = 0;
    throw (EvtException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x14002a6d4  mov     [rsp-20h+arg_0], rcx
0x14002a6d9  push    rbp
0x14002a6da  push    rbx
0x14002a6db  push    rsi
0x14002a6dc  push    rdi
0x14002a6dd  mov     rbp, rsp
0x14002a6e0  sub     rsp, 78h
0x14002a6e4  mov     rdi, r9
0x14002a6e7  mov     rbx, rdx
0x14002a6ea  mov     rsi, rcx
0x14002a6ed  mov     al, [rbp+arg_28]
0x14002a6f0  mov     [rcx], al
0x14002a6f2  mov     al, [rbp+arg_70]
0x14002a6f8  mov     [rcx+1], al
0x14002a6fb  mov     rax, [rbp+arg_30]
0x14002a6ff  mov     [rcx+8], rax
0x14002a703  mov     rax, [rbp+arg_38]
0x14002a707  mov     [rcx+10h], rax
0x14002a70b  mov     rax, [rbp+arg_40]
0x14002a70f  mov     [rcx+18h], rax
0x14002a713  mov     rax, [rbp+arg_48]
0x14002a717  mov     [rcx+20h], rax
0x14002a71b  mov     rax, [rbp+arg_50]
0x14002a71f  mov     [rcx+28h], rax
0x14002a723  add     rcx, 30h ; '0'
0x14002a727  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002a72c  nop
0x14002a72d  mov     rax, [rbp+arg_58]
0x14002a734  movaps  xmm0, xmmword ptr [rax]
0x14002a737  movdqa  [rbp+var_48], xmm0
0x14002a73c  lea     rcx, [rsi+50h]
0x14002a740  lea     rdx, [rbp+var_48]
0x14002a744  call    CopyOrThrow
0x14002a749  nop
0x14002a74a  mov     rax, [rbp+arg_60]
0x14002a751  movaps  xmm0, xmmword ptr [rax]
0x14002a754  movdqa  [rbp+var_48], xmm0
0x14002a759  lea     rcx, [rsi+70h]
0x14002a75d  lea     rdx, [rbp+var_48]
0x14002a761  call    CopyOrThrow
0x14002a766  nop
0x14002a767  mov     rax, [rbp+arg_68]
0x14002a76e  movaps  xmm0, xmmword ptr [rax]
0x14002a771  movdqa  [rbp+var_48], xmm0
0x14002a776  lea     rcx, [rsi+90h]
0x14002a77d  lea     rdx, [rbp+var_48]
0x14002a781  call    CopyOrThrow
0x14002a786  nop
0x14002a787  mov     r9, rdi; HKEY
0x14002a78a  mov     rdx, rbx; HKEY
0x14002a78d  call    ?Initialize@RegistryPaths@@QEAAKPEAUHKEY__@@PEB_W01@Z; RegistryPaths::Initialize(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *)
0x14002a792  mov     ebx, eax
0x14002a794  xor     edi, edi
0x14002a796  test    eax, eax
0x14002a798  jz      short loc_14002A802
0x14002a79a  lea     rax, WPP_GLOBAL_Control
0x14002a7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a7a8  cmp     rcx, rax
0x14002a7ab  jz      short loc_14002A7CF
0x14002a7ad  test    byte ptr [rcx+1Ch], 4
0x14002a7b1  jz      short loc_14002A7CF
0x14002a7b3  cmp     byte ptr [rcx+19h], 2
0x14002a7b7  jb      short loc_14002A7CF
0x14002a7b9  lea     edx, [rdi+15h]
0x14002a7bc  mov     r9d, ebx
0x14002a7bf  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14002a7c6  mov     rcx, [rcx+10h]
0x14002a7ca  call    WPP_SF_d
0x14002a7cf  lea     rax, word_14003838A
0x14002a7d6  mov     [rbp+pExceptionObject], rax
0x14002a7da  mov     [rbp+var_30], rdi
0x14002a7de  mov     [rbp+var_28], rdi
0x14002a7e2  mov     [rbp+var_20], ebx
0x14002a7e5  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x14002a7ed  mov     [rbp+var_14], dil
0x14002a7f1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002a7f8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002a7fc  call    _CxxThrowException_0
0x14002a802  mov     rax, rsi
0x14002a805  add     rsp, 78h
0x14002a809  pop     rdi
0x14002a80a  pop     rsi
0x14002a80b  pop     rbx
0x14002a80c  pop     rbp
0x14002a80d  retn
```
