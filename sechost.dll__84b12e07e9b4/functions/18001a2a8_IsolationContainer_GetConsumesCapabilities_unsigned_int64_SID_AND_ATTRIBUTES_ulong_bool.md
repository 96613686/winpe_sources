# IsolationContainer::GetConsumesCapabilities(unsigned __int64,_SID_AND_ATTRIBUTES * *,ulong *,bool *)

- ea: `0x18001a2a8`
- end: `0x18001a587`
- name: `?GetConsumesCapabilities@IsolationContainer@@QEBA_N_KPEAPEAU_SID_AND_ATTRIBUTES@@PEAKPEA_N@Z`
- size: `735`
- prototype: `bool __usercall@<al>(IsolationContainer *__hidden this@<rcx>, unsigned __int64@<rdx>, struct _SID_AND_ATTRIBUTES **@<r8>, unsigned int *@<r9>, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180042868`

## callees

- `0x180008010`
- `0x180016a88`
- `0x180019b70`
- `0x18001a2a8`
- `0x18001a590`
- `0x18001df6c`
- `0x1800466a0`
- `0x180046d18`
- `0x180046f0c`
- `0x180047fb0`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a3e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a3e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a3f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a3f5`

## pseudocode

```c
char __fastcall IsolationContainer::GetConsumesCapabilities(
        IsolationContainer *this,
        __int64 a2,
        struct _SID_AND_ATTRIBUTES **a3,
        unsigned int *a4,
        bool *a5)
{
  char *v6; // r12
  _QWORD *v7; // rdi
  char *v8; // r15
  _QWORD *v9; // rbx
  __int64 v10; // rsi
  int v11; // edx
  char *v12; // rcx
  char *v13; // rdi
  __int64 v14; // rdi
  __int64 v15; // rax
  unsigned int v16; // edx
  SIZE_T v17; // rbx
  HANDLE ProcessHeap; // rax
  void **v19; // rax
  struct _SID_AND_ATTRIBUTES *v20; // r14
  int v21; // edx
  unsigned int v22; // r13d
  char *i; // rsi
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rcx
  _QWORD *v27; // rdx
  _QWORD *j; // rbx
  _QWORD *v29; // rax
  WCHAR *k; // rdi
  __int64 v31; // rax
  const WCHAR *v32; // rcx
  BOOL v33; // eax
  __int64 v34; // rdx
  BOOL v35; // r14d
  struct _SID_AND_ATTRIBUTES *v36; // rcx
  int v38; // [rsp+20h] [rbp-60h]
  unsigned int v39; // [rsp+20h] [rbp-60h]
  struct _SID_AND_ATTRIBUTES *v40; // [rsp+28h] [rbp-58h]
  struct _SID_AND_ATTRIBUTES *v41; // [rsp+38h] [rbp-48h]
  char *v42; // [rsp+40h] [rbp-40h]
  void *v45[2]; // [rsp+58h] [rbp-28h] BYREF
  char *v46; // [rsp+68h] [rbp-18h]

  *a3 = 0;
  *a4 = 0;
  *(_OWORD *)v45 = 0;
  v6 = 0;
  v7 = (_QWORD *)((char *)this + 128);
  v8 = 0;
  *a5 = 0;
  v9 = (_QWORD *)*((_QWORD *)this + 16);
  v10 = *((_QWORD *)this + 31) | a2 & *((_QWORD *)this + 30);
  v11 = 0;
  v12 = 0;
  v46 = 0;
  v42 = (char *)this + 128;
  while ( 1 )
  {
    v9 = (_QWORD *)*v9;
    if ( v9 == (_QWORD *)*v7 )
      break;
    v13 = (char *)(v9 + 2);
    if ( (v10 & v9[2]) == v9[2] )
    {
      v11 += -991146299 * ((__int64)(v9[4] - v9[3]) >> 3);
      v38 = v11;
      if ( v13 >= v6 || v8 > v13 )
      {
        if ( v6 == v12 )
        {
          std::vector<unsigned __int64>::_Reserve(v45);
          v12 = v46;
          v11 = v38;
          v6 = (char *)v45[1];
          v8 = (char *)v45[0];
        }
        v15 = *(_QWORD *)v13;
      }
      else
      {
        v14 = (v13 - v8) >> 3;
        if ( v6 == v12 )
        {
          std::vector<unsigned __int64>::_Reserve(v45);
          v12 = v46;
          v11 = v38;
          v6 = (char *)v45[1];
          v8 = (char *)v45[0];
        }
        v15 = *(_QWORD *)&v8[8 * v14];
      }
      *(_QWORD *)v6 = v15;
      v6 += 8;
      v45[1] = v6;
    }
    v7 = (_QWORD *)((char *)this + 128);
  }
  if ( v11 )
  {
    v16 = v11 + 1;
    v17 = 16LL * v16;
    v39 = v16;
    ProcessHeap = GetProcessHeap();
    v19 = (void **)HeapAlloc(ProcessHeap, 8u, v17);
    v40 = (struct _SID_AND_ATTRIBUTES *)v19;
    v20 = (struct _SID_AND_ATTRIBUTES *)v19;
    if ( !v19 )
    {
LABEL_44:
      if ( v8 )
        operator delete(v8);
      return 0;
    }
    if ( !IsolationContainer::GetPackageCapabilitySid(this, v19) )
    {
      v21 = 0;
LABEL_42:
      v36 = v20;
LABEL_43:
      IsolationConfig::FreeSidArray(v36, v21);
      goto LABEL_44;
    }
    v20->Attributes = 4;
    v22 = 1;
    for ( i = v8; i != v6; i += 8 )
    {
      v24 = std::_Hash<std::_Umap_traits<unsigned __int64,unsigned long,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,unsigned long>>,0>>::_Hashval(
              v7,
              i);
      v25 = v7[2];
      v26 = 2 * v24;
      v27 = *(_QWORD **)(v25 + 16 * v24);
      for ( j = v27; ; j = (_QWORD *)*j )
      {
        v29 = v27 == (_QWORD *)*v7 ? (_QWORD *)*v7 : **(_QWORD ***)(v25 + 8 * v26 + 8);
        if ( j == v29 )
          break;
        if ( j[2] == *(_QWORD *)i )
        {
          if ( j != (_QWORD *)*v7 )
          {
            for ( k = (WCHAR *)j[3]; ; k += 52 )
            {
              if ( k == (WCHAR *)j[4] )
              {
                v7 = v42;
                goto LABEL_39;
              }
              if ( Capability::IsAllAppPackagesSid((Capability *)k) )
              {
                --v22;
                *a5 = 1;
              }
              else
              {
                if ( v22 >= v39 )
                {
                  v21 = v22;
                  goto LABEL_42;
                }
                v31 = Capability::SidString(k, (__int64)v45);
                v32 = (const WCHAR *)v31;
                if ( *(_QWORD *)(v31 + 24) >= 8u )
                  v32 = *(const WCHAR **)v31;
                v41 = &v20[v22];
                v33 = ConvertStringSidToSidW(v32, &v41->Sid);
                LOBYTE(v34) = 1;
                v35 = v33;
                std::wstring::_Tidy(v45, v34, 0);
                if ( !v35 )
                {
                  v36 = v40;
                  v21 = v22;
                  goto LABEL_43;
                }
                v20 = v40;
                v41->Attributes = 4;
              }
              ++v22;
            }
          }
          break;
        }
      }
LABEL_39:
      ;
    }
    *a4 = v22;
    *a3 = v20;
  }
  if ( v8 )
    operator delete(v8);
  return 1;
}

```

## disassembly

```asm
0x18001a2a8  mov     [rsp-38h+arg_8], rbx
0x18001a2ad  push    rbp
0x18001a2ae  push    rsi
0x18001a2af  push    rdi
0x18001a2b0  push    r12
0x18001a2b2  push    r13
0x18001a2b4  push    r14
0x18001a2b6  push    r15
0x18001a2b8  mov     rbp, rsp
0x18001a2bb  sub     rsp, 80h
0x18001a2c2  mov     rax, cs:__security_cookie
0x18001a2c9  xor     rax, rsp
0x18001a2cc  mov     [rbp+var_8], rax
0x18001a2d0  mov     r13, rcx
0x18001a2d3  mov     qword ptr [r8], 0
0x18001a2da  mov     rcx, [rbp+arg_20]
0x18001a2de  xorps   xmm0, xmm0
0x18001a2e1  mov     dword ptr [r9], 0
0x18001a2e8  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18001a2ed  mov     r12, [rbp+var_28+8]
0x18001a2f1  lea     rdi, [r13+80h]
0x18001a2f8  mov     r15, [rbp+var_28]
0x18001a2fc  mov     byte ptr [rcx], 0
0x18001a2ff  mov     rsi, [r13+0F0h]
0x18001a306  mov     rbx, [rdi]
0x18001a309  and     rsi, rdx
0x18001a30c  or      rsi, [r13+0F8h]
0x18001a313  xor     edx, edx
0x18001a315  mov     [rbp+var_50], rcx
0x18001a319  xor     ecx, ecx
0x18001a31b  mov     [rbp+var_18], rcx
0x18001a31f  mov     [rbp+var_38], r9
0x18001a323  mov     [rbp+var_30], r8
0x18001a327  mov     [rbp+var_40], rdi
0x18001a32b  mov     rbx, [rbx]
0x18001a32e  cmp     rbx, [rdi]
0x18001a331  jz      loc_18001A3D1
0x18001a337  lea     rdi, [rbx+10h]
0x18001a33b  mov     rax, [rdi]
0x18001a33e  and     rax, rsi
0x18001a341  cmp     rax, [rdi]
0x18001a344  jnz     short loc_18001A3C5
0x18001a346  mov     rax, [rbx+20h]
0x18001a34a  mov     r8, 4EC4EC4EC4EC4EC5h
0x18001a354  sub     rax, [rbx+18h]
0x18001a358  sar     rax, 3
0x18001a35c  imul    rax, r8
0x18001a360  add     edx, eax
0x18001a362  mov     [rbp+var_60], edx
0x18001a365  cmp     rdi, r12
0x18001a368  jnb     short loc_18001A399
0x18001a36a  cmp     r15, rdi
0x18001a36d  ja      short loc_18001A399
0x18001a36f  sub     rdi, r15
0x18001a372  sar     rdi, 3
0x18001a376  cmp     r12, rcx
0x18001a379  jnz     short loc_18001A393
0x18001a37b  lea     rcx, [rbp+var_28]
0x18001a37f  call    ?_Reserve@?$vector@_KV?$allocator@_K@std@@@std@@IEAAX_K@Z; std::vector<unsigned __int64>::_Reserve(unsigned __int64)
0x18001a384  mov     rcx, [rbp+var_18]
0x18001a388  mov     edx, [rbp+var_60]
0x18001a38b  mov     r12, [rbp+var_28+8]
0x18001a38f  mov     r15, [rbp+var_28]
0x18001a393  mov     rax, [r15+rdi*8]
0x18001a397  jmp     short loc_18001A3B9
0x18001a399  cmp     r12, rcx
0x18001a39c  jnz     short loc_18001A3B6
0x18001a39e  lea     rcx, [rbp+var_28]
0x18001a3a2  call    ?_Reserve@?$vector@_KV?$allocator@_K@std@@@std@@IEAAX_K@Z; std::vector<unsigned __int64>::_Reserve(unsigned __int64)
0x18001a3a7  mov     rcx, [rbp+var_18]
0x18001a3ab  mov     edx, [rbp+var_60]
0x18001a3ae  mov     r12, [rbp+var_28+8]
0x18001a3b2  mov     r15, [rbp+var_28]
0x18001a3b6  mov     rax, [rdi]
0x18001a3b9  mov     [r12], rax
0x18001a3bd  add     r12, 8
0x18001a3c1  mov     [rbp+var_28+8], r12
0x18001a3c5  lea     rdi, [r13+80h]
0x18001a3cc  jmp     loc_18001A32B
0x18001a3d1  test    edx, edx
0x18001a3d3  jz      loc_18001A551
0x18001a3d9  inc     edx
0x18001a3db  mov     ebx, edx
0x18001a3dd  shl     rbx, 4
0x18001a3e1  mov     [rbp+var_60], edx
0x18001a3e4  call    cs:__imp_GetProcessHeap
0x18001a3ea  mov     r8, rbx; dwBytes
0x18001a3ed  mov     edx, 8; dwFlags
0x18001a3f2  mov     rcx, rax; hHeap
0x18001a3f5  call    cs:__imp_HeapAlloc
0x18001a3fb  mov     [rbp+var_58], rax
0x18001a3ff  mov     r14, rax
0x18001a402  test    rax, rax
0x18001a405  jz      loc_18001A532
0x18001a40b  mov     rdx, rax; void **
0x18001a40e  mov     rcx, r13; this
0x18001a411  call    ?GetPackageCapabilitySid@IsolationContainer@@AEBA_NPEAPEAX@Z; IsolationContainer::GetPackageCapabilitySid(void * *)
0x18001a416  test    al, al
0x18001a418  jnz     short loc_18001A421
0x18001a41a  xor     edx, edx
0x18001a41c  jmp     loc_18001A52A
0x18001a421  mov     dword ptr [r14+8], 4
0x18001a429  mov     r13d, 1
0x18001a42f  mov     rsi, r15
0x18001a432  cmp     rsi, r12
0x18001a435  jz      loc_18001A543
0x18001a43b  mov     rdx, rsi
0x18001a43e  mov     rcx, rdi
0x18001a441  call    ?_Hashval@?$_Hash@V?$_Umap_traits@_KKV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KK@std@@@2@$0A@@std@@@std@@IEBA_KAEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,ulong,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,ulong>>,0>>::_Hashval(unsigned __int64 const &)
0x18001a446  mov     r8, [rdi+10h]
0x18001a44a  mov     rcx, rax
0x18001a44d  add     rcx, rcx
0x18001a450  mov     rdx, [r8+rcx*8]
0x18001a454  mov     rbx, rdx
0x18001a457  cmp     rdx, [rdi]
0x18001a45a  jnz     short loc_18001A461
0x18001a45c  mov     rax, [rdi]
0x18001a45f  jmp     short loc_18001A469
0x18001a461  mov     rax, [r8+rcx*8+8]
0x18001a466  mov     rax, [rax]
0x18001a469  cmp     rbx, rax
0x18001a46c  jz      loc_18001A515
0x18001a472  mov     rax, [rsi]
0x18001a475  cmp     [rbx+10h], rax
0x18001a479  jz      short loc_18001A480
0x18001a47b  mov     rbx, [rbx]
0x18001a47e  jmp     short loc_18001A457
0x18001a480  cmp     rbx, [rdi]
0x18001a483  jz      loc_18001A515
0x18001a489  mov     rdi, [rbx+18h]
0x18001a48d  cmp     rdi, [rbx+20h]
0x18001a491  jz      short loc_18001A511
0x18001a493  mov     rcx, rdi; this
0x18001a496  call    ?IsAllAppPackagesSid@Capability@@QEBA_NXZ; Capability::IsAllAppPackagesSid(void)
0x18001a49b  test    al, al
0x18001a49d  jz      short loc_18001A4AB
0x18001a49f  mov     rax, [rbp+var_50]
0x18001a4a3  dec     r13d
0x18001a4a6  mov     byte ptr [rax], 1
0x18001a4a9  jmp     short loc_18001A505
0x18001a4ab  cmp     r13d, [rbp+var_60]
0x18001a4af  jnb     short loc_18001A527
0x18001a4b1  lea     rdx, [rbp+var_28]
0x18001a4b5  mov     rcx, rdi; SourceString
0x18001a4b8  call    ?SidString@Capability@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Capability::SidString(void)
0x18001a4bd  mov     rcx, rax
0x18001a4c0  cmp     qword ptr [rax+18h], 8
0x18001a4c5  jb      short loc_18001A4CA
0x18001a4c7  mov     rcx, [rax]; StringSid
0x18001a4ca  mov     eax, r13d
0x18001a4cd  shl     rax, 4
0x18001a4d1  add     rax, r14
0x18001a4d4  mov     rdx, rax; Sid
0x18001a4d7  mov     [rbp+var_48], rax
0x18001a4db  call    ConvertStringSidToSidW
0x18001a4e0  xor     r8d, r8d
0x18001a4e3  lea     rcx, [rbp+var_28]
0x18001a4e7  mov     dl, 1
0x18001a4e9  mov     r14d, eax
0x18001a4ec  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001a4f1  test    r14d, r14d
0x18001a4f4  jz      short loc_18001A51E
0x18001a4f6  mov     rax, [rbp+var_48]
0x18001a4fa  mov     r14, [rbp+var_58]
0x18001a4fe  mov     dword ptr [rax+8], 4
0x18001a505  add     rdi, 68h ; 'h'
0x18001a509  inc     r13d
0x18001a50c  jmp     loc_18001A48D
0x18001a511  mov     rdi, [rbp+var_40]
0x18001a515  add     rsi, 8
0x18001a519  jmp     loc_18001A432
0x18001a51e  mov     rcx, [rbp+var_58]
0x18001a522  mov     edx, r13d
0x18001a525  jmp     short loc_18001A52D
0x18001a527  mov     edx, r13d; unsigned int
0x18001a52a  mov     rcx, r14; lpMem
0x18001a52d  call    ?FreeSidArray@IsolationConfig@@SAXPEAU_SID_AND_ATTRIBUTES@@K@Z; IsolationConfig::FreeSidArray(_SID_AND_ATTRIBUTES *,ulong)
0x18001a532  test    r15, r15
0x18001a535  jz      short loc_18001A53F
0x18001a537  mov     rcx, r15; void *
0x18001a53a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a53f  xor     al, al
0x18001a541  jmp     short loc_18001A560
0x18001a543  mov     rcx, [rbp+var_38]
0x18001a547  mov     [rcx], r13d
0x18001a54a  mov     rcx, [rbp+var_30]
0x18001a54e  mov     [rcx], r14
0x18001a551  test    r15, r15
0x18001a554  jz      short loc_18001A55E
0x18001a556  mov     rcx, r15; void *
0x18001a559  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a55e  mov     al, 1
0x18001a560  mov     rcx, [rbp+var_8]
0x18001a564  xor     rcx, rsp; StackCookie
0x18001a567  call    __security_check_cookie
0x18001a56c  mov     rbx, [rsp+80h+arg_8]
0x18001a574  add     rsp, 80h
0x18001a57b  pop     r15
0x18001a57d  pop     r14
0x18001a57f  pop     r13
0x18001a581  pop     r12
0x18001a583  pop     rdi
0x18001a584  pop     rsi
0x18001a585  pop     rbp
0x18001a586  retn
```
