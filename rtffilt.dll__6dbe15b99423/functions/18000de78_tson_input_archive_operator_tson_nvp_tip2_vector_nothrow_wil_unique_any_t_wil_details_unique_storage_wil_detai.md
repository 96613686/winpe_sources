# tson::input_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x18000de78`
- end: `0x18000e02e`
- name: `??$?RV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `438`
- prototype: `__int64 __fastcall(tson *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180015a68`

## callees

- `0x1800028b4`
- `0x18000479c`
- `0x18000de78`
- `0x18000e748`
- `0x18000e980`
- `0x1800166dc`
- `0x180017524`
- `0x180017950`
- `0x180018eac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df61`

## pseudocode

```c
tson *__fastcall tson::input_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  char v4; // r10
  void **v8; // rbx
  __int64 v9; // rax
  void **v10; // r14
  __int64 v11; // rbx
  char *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int16 *v15; // rcx
  _WORD *v16; // rdx
  unsigned __int16 v17; // cx
  unsigned __int64 v18; // rdi
  void *v19; // rdi
  HANDLE ProcessHeap; // rax
  struct wil::StoredFailureInfo *v21; // r8
  __int64 v22; // rax
  _BYTE v24[152]; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+B8h] [rbp-40h]
  __int64 v26; // [rsp+C0h] [rbp-38h]

  v4 = *(_BYTE *)(a2 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v4;
  v8 = *(void ***)(a2 + 16);
  tson::input_archive::startNode(this);
  tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
    this,
    v8);
  tson::input_archive::finishNode(this);
  v9 = *a3;
  *((_BYTE *)this + 24) = *((_BYTE *)a3 + 8);
  *((_QWORD *)this + 2) = v9;
  v10 = (void **)a3[2];
  tson::input_archive::startNode(this);
  v11 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v12 = (char *)this + 32;
    v13 = *((_QWORD *)this + 17);
    if ( v13 )
      v12 = &v12[4 * v13 - 4];
    else
      *v12 = 1;
    if ( *((_DWORD *)v12 + 1) != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v14 = *(_QWORD *)this;
    v15 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    v16 = v15 + 1;
    if ( (unsigned __int64)(v15 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      v17 = 0;
      *(_BYTE *)(v14 + 24) = 1;
    }
    else
    {
      v17 = *v15;
      *(_QWORD *)(v14 + 8) = v16;
    }
    v11 = v17;
  }
  if ( *v10 )
  {
    v18 = 0;
    if ( v10[2] )
    {
      do
        wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)((char *)*v10 + 168 * v18++));
      while ( v18 < (unsigned __int64)v10[2] );
    }
    v19 = *v10;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v19);
    *v10 = 0;
  }
  v10[1] = 0;
  for ( v10[2] = 0; v11; --v11 )
  {
    v25 = 0;
    v26 = 0;
    memset_0(v24, 0, sizeof(v24));
    tson::input_archive::startNode(this);
    tson::load_nothrow(this, (struct tson::input_archive *)v24, v21);
    tson::input_archive::finishNode(this);
    tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(v10, v24);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)v24);
  }
  tson::input_archive::finishNode(this);
  v22 = *a4;
  *((_BYTE *)this + 24) = *((_BYTE *)a4 + 8);
  *((_QWORD *)this + 2) = v22;
  tson::input_archive::startNode(this);
  tson::load_nothrow<tip2::test_flag>(this);
  tson::input_archive::finishNode(this);
  return this;
}

```

## disassembly

```asm
0x18000de78  push    rbx
0x18000de7a  push    rsi
0x18000de7b  push    rdi
0x18000de7c  push    r14
0x18000de7e  push    r15
0x18000de80  sub     rsp, 0D0h
0x18000de87  mov     r10b, [rdx+8]
0x18000de8b  mov     r15, r9
0x18000de8e  mov     rax, [rdx]
0x18000de91  mov     rdi, r8
0x18000de94  mov     [rcx+10h], rax
0x18000de98  mov     rsi, rcx
0x18000de9b  mov     [rcx+18h], r10b
0x18000de9f  mov     rbx, [rdx+10h]
0x18000dea3  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18000dea8  mov     rdx, rbx
0x18000deab  mov     rcx, rsi; this
0x18000deae  call    ??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18000deb3  mov     rcx, rsi; this
0x18000deb6  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x18000debb  mov     cl, [rdi+8]
0x18000debe  mov     rax, [rdi]
0x18000dec1  mov     [rsi+18h], cl
0x18000dec4  mov     rcx, rsi; this
0x18000dec7  mov     [rsi+10h], rax
0x18000decb  mov     r14, [rdi+10h]
0x18000decf  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18000ded4  xor     ebx, ebx
0x18000ded6  cmp     [rsi+19h], bl
0x18000ded9  jnz     short loc_18000DF2A
0x18000dedb  lea     rax, [rsi+20h]
0x18000dedf  mov     rcx, [rax+68h]
0x18000dee3  test    rcx, rcx
0x18000dee6  jz      short loc_18000DEF2
0x18000dee8  lea     rax, [rax+rcx*4]
0x18000deec  add     rax, 0FFFFFFFFFFFFFFFCh
0x18000def0  jmp     short loc_18000DEF5
0x18000def2  mov     byte ptr [rax], 1
0x18000def5  cmp     dword ptr [rax+4], 1
0x18000def9  jz      short loc_18000DF07
0x18000defb  cmp     [rsi+8], ebx
0x18000defe  jl      short loc_18000DF07
0x18000df00  mov     dword ptr [rsi+8], 8007065Dh
0x18000df07  mov     rax, [rsi]
0x18000df0a  mov     rcx, [rax+8]
0x18000df0e  lea     rdx, [rcx+2]
0x18000df12  cmp     rdx, [rax+10h]
0x18000df16  ja      short loc_18000DF21
0x18000df18  movzx   ecx, word ptr [rcx]
0x18000df1b  mov     [rax+8], rdx
0x18000df1f  jmp     short loc_18000DF27
0x18000df21  xor     ecx, ecx
0x18000df23  mov     byte ptr [rax+18h], 1
0x18000df27  movzx   ebx, cx
0x18000df2a  cmp     qword ptr [r14], 0
0x18000df2e  jz      short loc_18000DF6E
0x18000df30  xor     edi, edi
0x18000df32  cmp     [r14+10h], rdi
0x18000df36  jbe     short loc_18000DF50
0x18000df38  imul    rcx, rdi, 0A8h
0x18000df3f  add     rcx, [r14]; this
0x18000df42  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x18000df47  inc     rdi
0x18000df4a  cmp     rdi, [r14+10h]
0x18000df4e  jb      short loc_18000DF38
0x18000df50  mov     rdi, [r14]
0x18000df53  call    cs:__imp_GetProcessHeap
0x18000df59  mov     r8, rdi; lpMem
0x18000df5c  xor     edx, edx; dwFlags
0x18000df5e  mov     rcx, rax; hHeap
0x18000df61  call    cs:__imp_HeapFree
0x18000df67  mov     qword ptr [r14], 0
0x18000df6e  mov     qword ptr [r14+8], 0
0x18000df76  mov     qword ptr [r14+10h], 0
0x18000df7e  test    rbx, rbx
0x18000df81  jz      short loc_18000DFE7
0x18000df83  xor     edx, edx; Val
0x18000df85  mov     [rsp+0F8h+var_40], 0
0x18000df91  mov     r8d, 98h; Size
0x18000df97  mov     [rsp+0F8h+var_38], 0
0x18000dfa3  lea     rcx, [rsp+0F8h+var_D8]; void *
0x18000dfa8  call    memset_0
0x18000dfad  mov     rcx, rsi; this
0x18000dfb0  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18000dfb5  lea     rdx, [rsp+0F8h+var_D8]; struct tson::input_archive *
0x18000dfba  mov     rcx, rsi; this
0x18000dfbd  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAVStoredFailureInfo@wil@@@Z; tson::load_nothrow(tson::input_archive &,wil::StoredFailureInfo &)
0x18000dfc2  mov     rcx, rsi; this
0x18000dfc5  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x18000dfca  lea     rdx, [rsp+0F8h+var_D8]
0x18000dfcf  mov     rcx, r14
0x18000dfd2  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x18000dfd7  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000dfdc  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x18000dfe1  sub     rbx, 1
0x18000dfe5  jnz     short loc_18000DF83
0x18000dfe7  mov     rcx, rsi; this
0x18000dfea  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x18000dfef  mov     cl, [r15+8]
0x18000dff3  mov     rax, [r15]
0x18000dff6  mov     [rsi+18h], cl
0x18000dff9  mov     rcx, rsi; this
0x18000dffc  mov     [rsi+10h], rax
0x18000e000  mov     rbx, [r15+10h]
0x18000e004  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18000e009  mov     rdx, rbx
0x18000e00c  mov     rcx, rsi; this
0x18000e00f  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x18000e014  mov     rcx, rsi; this
0x18000e017  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x18000e01c  mov     rax, rsi
0x18000e01f  add     rsp, 0D0h
0x18000e026  pop     r15
0x18000e028  pop     r14
0x18000e02a  pop     rdi
0x18000e02b  pop     rsi
0x18000e02c  pop     rbx
0x18000e02d  retn
```
