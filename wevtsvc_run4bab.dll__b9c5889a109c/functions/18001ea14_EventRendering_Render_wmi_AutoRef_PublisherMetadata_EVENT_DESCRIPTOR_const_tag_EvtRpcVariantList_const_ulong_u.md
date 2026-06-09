# EventRendering::Render(wmi::AutoRef<PublisherMetadata>,_EVENT_DESCRIPTOR const &,tag_EvtRpcVariantList const &,ulong,ulong,ulong,uchar * *,ulong *,tag_RpcInfo &)

- ea: `0x18001ea14`
- end: `0x18001ec49`
- name: `?Render@EventRendering@@YAXV?$AutoRef@VPublisherMetadata@@@wmi@@AEBU_EVENT_DESCRIPTOR@@AEBUtag_EvtRpcVariantList@@KKKPEAPEAEPEAKAEAUtag_RpcInfo@@@Z`
- size: `565`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18007cbb0`
- `0x18007ce10`

## callees

- `0x180003de0`
- `0x18000bf10`
- `0x180014bd0`
- `0x180017b60`
- `0x18001c320`
- `0x18001d820`
- `0x18001ea14`
- `0x18001ec50`
- `0x18001ff40`
- `0x18002de70`
- `0x180092008`
- `0x1800d334c`
- `0x1800d3370`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001ea79`
- `RPCRT4!RpcImpersonateClient` at `0x18001ea79`
- `RPCRT4!RpcRevertToSelf` at `0x18001eabf`
- `RPCRT4!RpcRevertToSelf` at `0x18001eabf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EventRendering::Render(
        PublisherMetadata **a1,
        __int64 a2,
        unsigned int *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        _QWORD *a7,
        _DWORD *a8,
        __int64 a9)
{
  unsigned int v13; // ebx
  char *v14; // rcx
  unsigned __int64 v15; // rdx
  void *v16; // rax
  PublisherMetadata *v18; // rbx
  _QWORD v19[3]; // [rsp+40h] [rbp-61h] BYREF
  void *Src; // [rsp+58h] [rbp-49h] BYREF
  __int64 v21; // [rsp+60h] [rbp-41h]
  char v22; // [rsp+68h] [rbp-39h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+78h] [rbp-29h] BYREF
  unsigned int v24; // [rsp+90h] [rbp-11h]
  __int64 v25; // [rsp+94h] [rbp-Dh]
  char v26; // [rsp+9Ch] [rbp-5h]

  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v19);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&Src);
  *a7 = 0;
  *a8 = 0;
  if ( !*a3 || InitializeInsertsFromRpc(a3, v19) )
  {
    if ( !*a1 )
    {
      v18 = g_winmetaPublisherMetadata;
      if ( g_winmetaPublisherMetadata )
        _InterlockedIncrement((volatile signed __int32 *)g_winmetaPublisherMetadata + 2);
      wmi::AutoRef<PublisherMetadata>::Release(a1);
      *a1 = v18;
    }
    v13 = RpcImpersonateClient(0);
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, v13);
      }
      pExceptionObject[0] = &word_1800EC961;
      pExceptionObject[1] = 0;
      pExceptionObject[2] = 0;
      v24 = v13;
      v25 = -1;
      v26 = 0;
      throw (EvtException *)pExceptionObject;
    }
    EventRendering::GetEventDescription(a1, a2, a4, v19, a5, &Src, a9);
    RpcRevertToSelf();
    v14 = (char *)Src;
    v15 = (v21 - (__int64)Src) >> 1;
    if ( v15 > 0x100000 )
    {
      *a8 = 0;
      *(_QWORD *)a9 = 111;
      *(_DWORD *)(a9 + 8) = 0;
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&Src);
      goto LABEL_11;
    }
    *a8 = 2 * v15;
    if ( 2 * (int)v15 > a6 )
    {
      *(_QWORD *)a9 = 122;
      *(_DWORD *)(a9 + 8) = *a8;
      goto LABEL_9;
    }
    if ( !v15 )
      goto LABEL_9;
    v16 = MIDL_user_allocate((unsigned int)(2 * v15));
    *a7 = v16;
    if ( v16 )
    {
      memcpy_0(v16, Src, 2 * ((v21 - (__int64)Src) >> 1));
      v14 = (char *)Src;
      goto LABEL_9;
    }
    *(_QWORD *)a9 = 14;
    *(_DWORD *)(a9 + 8) = *a8;
  }
  else
  {
    *(_QWORD *)a9 = 13;
    *(_DWORD *)(a9 + 8) = 0;
  }
  v14 = (char *)Src;
LABEL_9:
  if ( v14 != &v22 )
    operator delete(v14);
LABEL_11:
  utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(v19);
  return wmi::AutoRef<PublisherMetadata>::Release(a1);
}

```

## disassembly

```asm
0x18001ea14  mov     [rsp-8+arg_0], rcx
0x18001ea19  push    rbp
0x18001ea1a  push    rbx
0x18001ea1b  push    rsi
0x18001ea1c  push    rdi
0x18001ea1d  push    r12
0x18001ea1f  push    r13
0x18001ea21  push    r14
0x18001ea23  push    r15
0x18001ea25  lea     rbp, [rsp-7]
0x18001ea2a  sub     rsp, 0A8h
0x18001ea31  mov     r15d, r9d
0x18001ea34  mov     rbx, r8
0x18001ea37  mov     r12, rdx
0x18001ea3a  mov     rdi, rcx
0x18001ea3d  lea     rcx, [rbp+3Fh+var_A0]; void *
0x18001ea41  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18001ea46  nop
0x18001ea47  lea     rcx, [rbp+3Fh+Src]; void *
0x18001ea4b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001ea50  nop
0x18001ea51  xor     r13d, r13d
0x18001ea54  mov     r14, [rbp+3Fh+arg_30]
0x18001ea58  mov     [r14], r13
0x18001ea5b  mov     rsi, [rbp+3Fh+arg_38]
0x18001ea62  mov     [rsi], r13d
0x18001ea65  cmp     [rbx], r13d
0x18001ea68  jnz     loc_18001EB62
0x18001ea6e  cmp     [rdi], r13
0x18001ea71  jz      loc_18001EB8A
0x18001ea77  xor     ecx, ecx; BindingHandle
0x18001ea79  call    cs:__imp_RpcImpersonateClient
0x18001ea7f  mov     ebx, eax
0x18001ea81  test    eax, eax
0x18001ea83  jnz     loc_18001EBBF
0x18001ea89  mov     byte ptr [rbp+3Fh+arg_30+1], 1
0x18001ea90  mov     rbx, [rbp+3Fh+arg_40]
0x18001ea97  mov     [rsp+0E0h+var_B0], rbx
0x18001ea9c  lea     rax, [rbp+3Fh+Src]
0x18001eaa0  mov     [rsp+0E0h+var_B8], rax
0x18001eaa5  mov     eax, [rbp+3Fh+arg_20]
0x18001eaa8  mov     [rsp+0E0h+var_C0], eax
0x18001eaac  lea     r9, [rbp+3Fh+var_A0]
0x18001eab0  mov     r8d, r15d
0x18001eab3  mov     rdx, r12
0x18001eab6  mov     rcx, rdi
0x18001eab9  call    ?GetEventDescription@EventRendering@@YAXAEAV?$AutoRef@VPublisherMetadata@@@wmi@@AEBU_EVENT_DESCRIPTOR@@KAEAV?$vector@VBinXmlVariantHolder@@V?$allocator@VBinXmlVariantHolder@@@utl@@@utl@@KAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@6@AEAUtag_RpcInfo@@@Z; EventRendering::GetEventDescription(wmi::AutoRef<PublisherMetadata> &,_EVENT_DESCRIPTOR const &,ulong,utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>> &,ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,tag_RpcInfo &)
0x18001eabe  nop
0x18001eabf  call    cs:__imp_RpcRevertToSelf
0x18001eac5  mov     rdx, [rbp+3Fh+var_80]
0x18001eac9  mov     rcx, [rbp+3Fh+Src]
0x18001eacd  sub     rdx, rcx
0x18001ead0  sar     rdx, 1
0x18001ead3  cmp     rdx, 100000h
0x18001eada  ja      loc_18001EC2C
0x18001eae0  lea     eax, [rdx+rdx]
0x18001eae3  mov     [rsi], eax
0x18001eae5  cmp     eax, [rbp+3Fh+arg_28]
0x18001eae8  ja      short loc_18001EB54
0x18001eaea  test    rdx, rdx
0x18001eaed  jz      short loc_18001EB1F
0x18001eaef  mov     ecx, eax; size
0x18001eaf1  call    MIDL_user_allocate
0x18001eaf6  mov     [r14], rax
0x18001eaf9  test    rax, rax
0x18001eafc  jz      loc_18001EBAA
0x18001eb02  mov     r8, [rbp+3Fh+var_80]
0x18001eb06  mov     rdx, [rbp+3Fh+Src]; Src
0x18001eb0a  sub     r8, rdx
0x18001eb0d  sar     r8, 1
0x18001eb10  add     r8, r8; Size
0x18001eb13  mov     rcx, rax; void *
0x18001eb16  call    memcpy_0
0x18001eb1b  mov     rcx, [rbp+3Fh+Src]; void *
0x18001eb1f  lea     rax, [rbp+3Fh+var_78]
0x18001eb23  cmp     rcx, rax
0x18001eb26  jz      short loc_18001EB2E
0x18001eb28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001eb2d  nop
0x18001eb2e  lea     rcx, [rbp+3Fh+var_A0]
0x18001eb32  call    ?_Uninit@?$vector@VBinXmlVariantHolder@@V?$allocator@VBinXmlVariantHolder@@@utl@@@utl@@AEAAXXZ; utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(void)
0x18001eb37  nop
0x18001eb38  mov     rcx, rdi
0x18001eb3b  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18001eb40  add     rsp, 0A8h
0x18001eb47  pop     r15
0x18001eb49  pop     r14
0x18001eb4b  pop     r13
0x18001eb4d  pop     r12
0x18001eb4f  pop     rdi
0x18001eb50  pop     rsi
0x18001eb51  pop     rbx
0x18001eb52  pop     rbp
0x18001eb53  retn
0x18001eb54  mov     qword ptr [rbx], 7Ah ; 'z'
0x18001eb5b  mov     eax, [rsi]
0x18001eb5d  mov     [rbx+8], eax
0x18001eb60  jmp     short loc_18001EB1F
0x18001eb62  lea     rdx, [rbp+3Fh+var_A0]
0x18001eb66  mov     rcx, rbx
0x18001eb69  call    InitializeInsertsFromRpc
0x18001eb6e  test    al, al
0x18001eb70  jnz     loc_18001EA6E
0x18001eb76  mov     rax, [rbp+3Fh+arg_40]
0x18001eb7d  mov     qword ptr [rax], 0Dh
0x18001eb84  mov     [rax+8], r13d
0x18001eb88  jmp     short loc_18001EBB6
0x18001eb8a  mov     rbx, cs:?g_winmetaPublisherMetadata@@3V?$AutoRef@VPublisherMetadata@@@wmi@@A; wmi::AutoRef<PublisherMetadata> g_winmetaPublisherMetadata
0x18001eb91  test    rbx, rbx
0x18001eb94  jz      short loc_18001EB9A
0x18001eb96  lock inc dword ptr [rbx+8]
0x18001eb9a  mov     rcx, rdi
0x18001eb9d  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18001eba2  mov     [rdi], rbx
0x18001eba5  jmp     loc_18001EA77
0x18001ebaa  mov     qword ptr [rbx], 0Eh
0x18001ebb1  mov     eax, [rsi]
0x18001ebb3  mov     [rbx+8], eax
0x18001ebb6  mov     rcx, [rbp+3Fh+Src]
0x18001ebba  jmp     loc_18001EB1F
0x18001ebbf  lea     rax, WPP_GLOBAL_Control
0x18001ebc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebcd  cmp     rcx, rax
0x18001ebd0  jz      short loc_18001EBF9
0x18001ebd2  test    dword ptr [rcx+1Ch], 800000h
0x18001ebd9  jz      short loc_18001EBF9
0x18001ebdb  cmp     byte ptr [rcx+19h], 2
0x18001ebdf  jb      short loc_18001EBF9
0x18001ebe1  mov     edx, 4Bh ; 'K'
0x18001ebe6  mov     r9d, ebx
0x18001ebe9  lea     r8, WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids
0x18001ebf0  mov     rcx, [rcx+10h]
0x18001ebf4  call    WPP_SF_d
0x18001ebf9  lea     rax, word_1800EC961
0x18001ec00  mov     [rbp+3Fh+pExceptionObject], rax
0x18001ec04  mov     [rbp+3Fh+var_60], r13
0x18001ec08  mov     [rbp+3Fh+var_58], r13
0x18001ec0c  mov     [rbp+3Fh+var_50], ebx
0x18001ec0f  mov     [rbp+3Fh+var_4C], 0FFFFFFFFFFFFFFFFh
0x18001ec17  mov     [rbp+3Fh+var_44], r13b
0x18001ec1b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001ec22  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18001ec26  call    _CxxThrowException_0
0x18001ec2c  mov     [rsi], r13d
0x18001ec2f  mov     qword ptr [rbx], 6Fh ; 'o'
0x18001ec36  mov     [rbx+8], r13d
0x18001ec3a  lea     rcx, [rbp+3Fh+Src]; void *
0x18001ec3e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001ec43  jmp     loc_18001EB2E
```
