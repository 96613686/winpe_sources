# RemoteSubscription::IndicateFromChannel(BinXmlReader &,utl::vector<int,utl::allocator<int>> const &)

- ea: `0x18004ae38`
- end: `0x18004b193`
- name: `?IndicateFromChannel@RemoteSubscription@@AEAAXAEAVBinXmlReader@@AEBV?$vector@HV?$allocator@H@utl@@@utl@@@Z`
- size: `859`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct BinXmlReader *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004ae10`

## callees

- `0x180016250`
- `0x18001c320`
- `0x180043c94`
- `0x18004ae38`
- `0x18004b19c`
- `0x18004b20c`
- `0x18004b378`
- `0x18004b4f8`
- `0x180090c60`
- `0x180092008`
- `0x1800d334c`
- `0x1800d3370`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ae68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ae68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ae82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ae82`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004af65`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004af65`

## pseudocode

```c
void __fastcall RemoteSubscription::IndicateFromChannel(RTL_SRWLOCK *this, struct BinXmlReader *a2, _QWORD *a3)
{
  RTL_SRWLOCK *v6; // r14
  __int64 v7; // r12
  PVOID Ptr; // rdi
  __int64 v9; // rbx
  struct _RPC_ASYNC_STATE *v10; // rcx
  unsigned int v11; // ebx
  void *v12; // rbx
  int v13; // ebx
  _DWORD *v14; // rbx
  _DWORD *v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _DWORD *v18; // r8
  __int128 v19; // [rsp+30h] [rbp-50h] BYREF
  __int128 *p_pExceptionObject; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h]
  __int64 v22; // [rsp+50h] [rbp-30h]
  __int128 pExceptionObject; // [rsp+58h] [rbp-28h] BYREF
  size_t Size; // [rsp+68h] [rbp-18h]
  unsigned int v25; // [rsp+70h] [rbp-10h]
  int v26; // [rsp+74h] [rbp-Ch]
  int v27; // [rsp+78h] [rbp-8h]
  unsigned int Reply; // [rsp+C0h] [rbp+40h] BYREF
  _DWORD *v29; // [rsp+D8h] [rbp+58h]

  v6 = this + 4;
  AcquireSRWLockExclusive(this + 4);
  if ( BYTE6(this[51].Ptr) )
    goto LABEL_3;
  if ( BYTE4(this[51].Ptr) )
    goto LABEL_3;
  v7 = *((_QWORD *)a2 + 22);
  Ptr = this[34].Ptr;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v19 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64, __int128 **))(*(_QWORD *)v7 + 16LL))(v7, &p_pExceptionObject);
  if ( (unsigned __int8)MergedLogQueryResult::IsPastEvent(Ptr, &v19, v9) )
    goto LABEL_3;
  if ( !this[7].Ptr )
  {
    RemoteSubscription::UpdateBookmarks((RemoteSubscription *)this, a2, 0);
    WORD2(this[51].Ptr) = 257;
    goto LABEL_3;
  }
  BYTE5(this[51].Ptr) = 0;
  if ( (HIDWORD(this[50].Ptr) & 0x10000000) == 0 )
  {
    RemoteSubscription::UpdateBookmarks((RemoteSubscription *)this, a2, 1);
    if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) == -1 )
      goto LABEL_3;
    *(_QWORD *)&pExceptionObject = &Buffer::`vftable';
    *((_QWORD *)&pExceptionObject + 1) = 0;
    Size = 0;
    LOBYTE(v25) = 1;
    v12 = operator new(0x500u);
    memcpy_0(v12, *((const void **)&pExceptionObject + 1), (unsigned int)Size);
    if ( (_BYTE)v25 )
      operator delete(*((void **)&pExceptionObject + 1));
    HIDWORD(Size) = 1280;
    *((_QWORD *)&pExceptionObject + 1) = v12;
    LOBYTE(v25) = 1;
    p_pExceptionObject = &pExceptionObject;
    v21 = 0;
    v22 = 0;
    v13 = (*(__int64 (__fastcall **)(__int128 *))(pExceptionObject + 16))(&pExceptionObject);
    v21 = (*(__int64 (__fastcall **)(__int128 *))(*(_QWORD *)p_pExceptionObject + 48LL))(p_pExceptionObject);
    HIDWORD(v22) = v13;
    if ( (unsigned int)RemoteSubscription::WriteEventToBuffer((__int64)this, a2, a3, (__int64)&p_pExceptionObject) != 1 )
    {
      Buffer::~Buffer((Buffer *)&pExceptionObject);
      goto LABEL_3;
    }
    v14 = operator new(4u);
    if ( v14 )
      *v14 = 0;
    else
      v14 = 0;
    v29 = v14;
    v15 = operator new(4u);
    if ( v15 )
      *v15 = 0;
    else
      v15 = 0;
    *v14 = 0;
    *v15 = v22;
    *(_DWORD *)this[9].Ptr = 1;
    v29 = 0;
    *(_QWORD *)this[10].Ptr = v14;
    *(_QWORD *)&v19 = 0;
    *(_QWORD *)this[11].Ptr = v15;
    *(_DWORD *)this[12].Ptr = v22;
    LOBYTE(v25) = 0;
    v16 = this[13].Ptr;
    *v16 = *((_QWORD *)&pExceptionObject + 1);
    v17 = *(unsigned int *)this[9].Ptr;
    v18 = this[12].Ptr;
    if ( (_DWORD)v17 )
    {
      if ( *v18 )
        goto LABEL_26;
    }
    else if ( !*v18 )
    {
      goto LABEL_26;
    }
    MicrosoftTelemetryAssertTriggeredArgs(v16, v17, (unsigned int)*v18);
LABEL_26:
    *(_QWORD *)&pExceptionObject = &Buffer::`vftable';
    if ( (_BYTE)v25 )
      operator delete(*((void **)&pExceptionObject + 1));
    goto LABEL_8;
  }
  RemoteSubscription::UpdateBookmarks((RemoteSubscription *)this, a2, 0);
  WORD2(this[51].Ptr) = 257;
LABEL_8:
  if ( RemoteSubscription::RpcStatusSubscription::Stop((RemoteSubscription::RpcStatusSubscription *)&this[14]) )
  {
    Reply = 0;
    v10 = (struct _RPC_ASYNC_STATE *)this[7].Ptr;
    this[7].Ptr = 0;
    this[8].Ptr = 0;
    this[9].Ptr = 0;
    this[10].Ptr = 0;
    this[11].Ptr = 0;
    this[12].Ptr = 0;
    this[13].Ptr = 0;
    v11 = RpcAsyncCompleteCall(v10, &Reply);
    Reply = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v11);
      }
      pExceptionObject = 0;
      Size = 0;
      v25 = v11;
      v26 = -1;
      v27 = 705;
      throw (EvtException *)&pExceptionObject;
    }
  }
LABEL_3:
  ReleaseSRWLockExclusive(v6);
}

```

## disassembly

```asm
0x18004ae38  mov     [rsp-38h+arg_8], rbx
0x18004ae3d  push    rbp
0x18004ae3e  push    rsi
0x18004ae3f  push    rdi
0x18004ae40  push    r12
0x18004ae42  push    r13
0x18004ae44  push    r14
0x18004ae46  push    r15
0x18004ae48  mov     rbp, rsp
0x18004ae4b  sub     rsp, 80h
0x18004ae52  mov     r13, r8
0x18004ae55  mov     r15, rdx
0x18004ae58  mov     rsi, rcx
0x18004ae5b  xor     ebx, ebx
0x18004ae5d  lea     r14, [rcx+20h]
0x18004ae61  mov     [rbp+var_60], r14
0x18004ae65  mov     rcx, r14; SRWLock
0x18004ae68  call    cs:__imp_AcquireSRWLockExclusive
0x18004ae6e  nop
0x18004ae6f  cmp     [rsi+19Eh], bl
0x18004ae75  jnz     short loc_18004AE7F
0x18004ae77  cmp     [rsi+19Ch], bl
0x18004ae7d  jz      short loc_18004AEA3
0x18004ae7f  mov     rcx, r14; SRWLock
0x18004ae82  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ae88  mov     rbx, [rsp+80h+arg_8]
0x18004ae90  add     rsp, 80h
0x18004ae97  pop     r15
0x18004ae99  pop     r14
0x18004ae9b  pop     r13
0x18004ae9d  pop     r12
0x18004ae9f  pop     rdi
0x18004aea0  pop     rsi
0x18004aea1  pop     rbp
0x18004aea2  retn
0x18004aea3  mov     r12, [r15+0B0h]
0x18004aeaa  mov     rdi, [rsi+110h]
0x18004aeb1  mov     rax, [r12]
0x18004aeb5  mov     rcx, r12
0x18004aeb8  mov     rax, [rax+8]
0x18004aebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aec1  mov     rbx, rax
0x18004aec4  mov     rdx, [r12]
0x18004aec8  mov     rax, [rdx+10h]
0x18004aecc  lea     rdx, [rbp+var_40]
0x18004aed0  mov     rcx, r12
0x18004aed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aed8  movups  xmm0, xmmword ptr [rax]
0x18004aedb  movdqu  [rbp+var_50], xmm0
0x18004aee0  mov     r8, rbx
0x18004aee3  lea     rdx, [rbp+var_50]
0x18004aee7  mov     rcx, rdi
0x18004aeea  call    ?IsPastEvent@MergedLogQueryResult@@QEAA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_K@Z; MergedLogQueryResult::IsPastEvent(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,unsigned __int64)
0x18004aeef  xor     edi, edi
0x18004aef1  test    al, al
0x18004aef3  jnz     short loc_18004AE7F
0x18004aef5  mov     rdx, r15; struct BinXmlReader *
0x18004aef8  mov     rcx, rsi; this
0x18004aefb  cmp     [rsi+38h], rdi
0x18004aeff  jz      loc_18004AFE0
0x18004af05  mov     [rsi+19Dh], dil
0x18004af0c  test    dword ptr [rsi+194h], 10000000h
0x18004af16  jz      loc_18004AFF6
0x18004af1c  xor     r8d, r8d; bool
0x18004af1f  call    ?UpdateBookmarks@RemoteSubscription@@AEAAXAEBVBinXmlReader@@_N@Z; RemoteSubscription::UpdateBookmarks(BinXmlReader const &,bool)
0x18004af24  mov     word ptr [rsi+19Ch], 101h
0x18004af2d  lea     rcx, [rsi+70h]; this
0x18004af31  call    ?Stop@RpcStatusSubscription@RemoteSubscription@@QEAA_NXZ; RemoteSubscription::RpcStatusSubscription::Stop(void)
0x18004af36  test    al, al
0x18004af38  jz      loc_18004AE7F
0x18004af3e  mov     [rbp+Reply], edi
0x18004af41  mov     rcx, [rsi+38h]; pAsync
0x18004af45  mov     [rsi+38h], rdi
0x18004af49  mov     [rsi+40h], rdi
0x18004af4d  mov     [rsi+48h], rdi
0x18004af51  mov     [rsi+50h], rdi
0x18004af55  mov     [rsi+58h], rdi
0x18004af59  mov     [rsi+60h], rdi
0x18004af5d  mov     [rsi+68h], rdi
0x18004af61  lea     rdx, [rbp+Reply]; Reply
0x18004af65  call    cs:__imp_RpcAsyncCompleteCall
0x18004af6b  mov     ebx, eax
0x18004af6d  mov     [rbp+Reply], eax
0x18004af70  test    eax, eax
0x18004af72  jz      loc_18004AE7F
0x18004af78  lea     rax, WPP_GLOBAL_Control
0x18004af7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004af86  cmp     rcx, rax
0x18004af89  jz      short loc_18004AFB2
0x18004af8b  test    dword ptr [rcx+1Ch], 100h
0x18004af92  jz      short loc_18004AFB2
0x18004af94  cmp     byte ptr [rcx+19h], 2
0x18004af98  jb      short loc_18004AFB2
0x18004af9a  mov     edx, 18h
0x18004af9f  mov     r9d, ebx
0x18004afa2  lea     r8, WPP_939241f3766634594ecc55fb100debfa_Traceguids
0x18004afa9  mov     rcx, [rcx+10h]
0x18004afad  call    WPP_SF_d
0x18004afb2  xorps   xmm0, xmm0
0x18004afb5  movdqu  [rbp+pExceptionObject], xmm0
0x18004afba  mov     [rbp+Size], rdi
0x18004afbe  mov     [rbp+var_10], ebx
0x18004afc1  mov     [rbp+var_C], 0FFFFFFFFh
0x18004afc8  mov     [rbp+var_8], 2C1h
0x18004afcf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18004afd6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004afda  call    _CxxThrowException_0
0x18004afe0  xor     r8d, r8d; bool
0x18004afe3  call    ?UpdateBookmarks@RemoteSubscription@@AEAAXAEBVBinXmlReader@@_N@Z; RemoteSubscription::UpdateBookmarks(BinXmlReader const &,bool)
0x18004afe8  mov     word ptr [rsi+19Ch], 101h
0x18004aff1  jmp     loc_18004AE7F
0x18004aff6  mov     r8b, 1; bool
0x18004aff9  call    ?UpdateBookmarks@RemoteSubscription@@AEAAXAEBVBinXmlReader@@_N@Z; RemoteSubscription::UpdateBookmarks(BinXmlReader const &,bool)
0x18004affe  mov     rax, [r12]
0x18004b002  mov     rcx, r12
0x18004b005  mov     rax, [rax+8]
0x18004b009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b00e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004b012  jz      loc_18004AE7F
0x18004b018  lea     r12, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18004b01f  mov     qword ptr [rbp+pExceptionObject], r12
0x18004b023  mov     qword ptr [rbp+pExceptionObject+8], rdi
0x18004b027  mov     [rbp+Size], rdi
0x18004b02b  mov     byte ptr [rbp+var_10], 1
0x18004b02f  mov     ecx, 500h; dwBytes
0x18004b034  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b039  mov     rbx, rax
0x18004b03c  mov     r8d, dword ptr [rbp+Size]; Size
0x18004b040  mov     rdx, qword ptr [rbp+pExceptionObject+8]; Src
0x18004b044  mov     rcx, rax; void *
0x18004b047  call    memcpy_0
0x18004b04c  cmp     byte ptr [rbp+var_10], dil
0x18004b050  jz      short loc_18004B05B
0x18004b052  mov     rcx, qword ptr [rbp+pExceptionObject+8]; void *
0x18004b056  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b05b  mov     dword ptr [rbp+Size+4], 500h
0x18004b062  mov     qword ptr [rbp+pExceptionObject+8], rbx
0x18004b066  mov     byte ptr [rbp+var_10], 1
0x18004b06a  lea     rax, [rbp+pExceptionObject]
0x18004b06e  mov     [rbp+var_40], rax
0x18004b072  mov     [rbp+var_38], rdi
0x18004b076  mov     [rbp+var_30], rdi
0x18004b07a  mov     rax, qword ptr [rbp+pExceptionObject]
0x18004b07e  lea     rcx, [rbp+pExceptionObject]
0x18004b082  mov     rax, [rax+10h]
0x18004b086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b08b  mov     ebx, eax
0x18004b08d  mov     rcx, [rbp+var_40]
0x18004b091  mov     rdx, [rcx]
0x18004b094  mov     rax, [rdx+30h]
0x18004b098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b09d  mov     [rbp+var_38], rax
0x18004b0a1  mov     dword ptr [rbp+var_30+4], ebx
0x18004b0a4  lea     r9, [rbp+var_40]
0x18004b0a8  mov     r8, r13
0x18004b0ab  mov     rdx, r15
0x18004b0ae  mov     rcx, rsi
0x18004b0b1  call    ?WriteEventToBuffer@RemoteSubscription@@AEAAKAEAVBinXmlReader@@AEBV?$vector@HV?$allocator@H@utl@@@utl@@AEAVWriteBuffer@@@Z; RemoteSubscription::WriteEventToBuffer(BinXmlReader &,utl::vector<int,utl::allocator<int>> const &,WriteBuffer &)
0x18004b0b6  cmp     eax, 1
0x18004b0b9  jnz     loc_18004B184
0x18004b0bf  lea     r15d, [rax+3]
0x18004b0c3  mov     ecx, r15d; dwBytes
0x18004b0c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b0cb  mov     rbx, rax
0x18004b0ce  test    rax, rax
0x18004b0d1  jz      loc_18004B174
0x18004b0d7  xor     eax, eax
0x18004b0d9  mov     [rbx], eax
0x18004b0db  mov     [rbp+arg_18], rbx
0x18004b0df  mov     rcx, r15; dwBytes
0x18004b0e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b0e7  mov     rcx, rax
0x18004b0ea  test    rax, rax
0x18004b0ed  jz      loc_18004B17C
0x18004b0f3  xor     eax, eax
0x18004b0f5  mov     [rcx], eax
0x18004b0f7  mov     [rbx], edi
0x18004b0f9  mov     eax, dword ptr [rbp+var_30]
0x18004b0fc  mov     [rcx], eax
0x18004b0fe  mov     rax, [rsi+48h]
0x18004b102  mov     dword ptr [rax], 1
0x18004b108  mov     [rbp+arg_18], rdi
0x18004b10c  mov     rax, [rsi+50h]
0x18004b110  mov     [rax], rbx
0x18004b113  mov     qword ptr [rbp+var_50], rdi
0x18004b117  mov     rax, [rsi+58h]
0x18004b11b  mov     [rax], rcx
0x18004b11e  mov     rcx, [rsi+60h]
0x18004b122  mov     eax, dword ptr [rbp+var_30]
0x18004b125  mov     [rcx], eax
0x18004b127  mov     byte ptr [rbp+var_10], dil
0x18004b12b  mov     rcx, [rsi+68h]
0x18004b12f  mov     rax, qword ptr [rbp+pExceptionObject+8]
0x18004b133  mov     [rcx], rax
0x18004b136  mov     rax, [rsi+48h]
0x18004b13a  mov     edx, [rax]
0x18004b13c  mov     r8, [rsi+60h]
0x18004b140  test    edx, edx
0x18004b142  jz      short loc_18004B165
0x18004b144  cmp     [r8], edi
0x18004b147  jz      short loc_18004B16A
0x18004b149  mov     qword ptr [rbp+pExceptionObject], r12
0x18004b14d  cmp     byte ptr [rbp+var_10], dil
0x18004b151  jz      loc_18004AF2D
0x18004b157  mov     rcx, qword ptr [rbp+pExceptionObject+8]; void *
0x18004b15b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b160  jmp     loc_18004AF2D
0x18004b165  cmp     [r8], edi
0x18004b168  jz      short loc_18004B149
0x18004b16a  mov     r8d, [r8]
0x18004b16d  call    MicrosoftTelemetryAssertTriggeredArgs
0x18004b172  jmp     short loc_18004B149
0x18004b174  mov     rbx, rdi
0x18004b177  jmp     loc_18004B0DB
0x18004b17c  mov     rcx, rdi
0x18004b17f  jmp     loc_18004B0F7
0x18004b184  lea     rcx, [rbp+pExceptionObject]; this
0x18004b188  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18004b18d  jmp     loc_18004AE7F
```
