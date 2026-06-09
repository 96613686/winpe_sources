# RemotePushSubscription::Initialize(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18000dac0`
- end: `0x18000de7b`
- name: `?Initialize@RemotePushSubscription@@QEAAXPEB_W00@Z`
- size: `955`
- prototype: `void __fastcall(Session **this, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d050`

## callees

- `0x180006aec`
- `0x180008924`
- `0x18000a020`
- `0x18000a298`
- `0x18000c204`
- `0x18000dac0`
- `0x18000de84`
- `0x18000decc`
- `0x18000df24`
- `0x18000dff8`
- `0x18000e73c`
- `0x18000e890`
- `0x180023548`
- `0x180024a50`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dc73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dc73`
- `RPCRT4!NdrClientCall3` at `0x18000db9a`
- `RPCRT4!NdrClientCall3` at `0x18000db9a`

## pseudocode

```c
void __fastcall RemotePushSubscription::Initialize(
        Session **this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  ObjectTable *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  void **v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned int Pointer; // ebx
  BookmarkChannels *v15; // rax
  unsigned int i; // ebx
  __int64 v17; // rbx
  __int64 v18; // rsi
  __int64 v19; // rdi
  DWORD CurrentProcessId; // eax
  int v21; // [rsp+70h] [rbp-69h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-61h] BYREF
  __int64 v23; // [rsp+88h] [rbp-51h]
  int v24; // [rsp+90h] [rbp-49h]
  int v25; // [rsp+94h] [rbp-45h]
  int v26; // [rsp+98h] [rbp-41h]
  char v27; // [rsp+9Ch] [rbp-3Dh]
  _QWORD v28[2]; // [rsp+A0h] [rbp-39h] BYREF
  _QWORD v29[2]; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD v30[2]; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v31; // [rsp+D0h] [rbp-9h] BYREF
  int v32; // [rsp+D8h] [rbp-1h]

  v31 = 0;
  v32 = 0;
  LastErrInfo::Reset((LastErrInfo *)this);
  v9 = ObjectTable::AddObject(v8, this[24], (struct EvtHandleRef *)(this + 25));
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, v9);
    }
    v24 = v10;
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    v26 = -1;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v23 = 0;
    v25 = -1;
    v27 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v11 = (void **)(this + 30);
  v12 = tlx::replace<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>(this + 30);
  v13 = tlx::replace<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>(this + 29);
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0,
                            0,
                            *((_QWORD *)this[6] + 9),
                            a2,
                            a3,
                            a4,
                            *((_DWORD *)this + 82),
                            v13,
                            v12,
                            this + 42,
                            this + 26,
                            &v31).Pointer;
  v21 = 0;
  if ( !v31 && v32 )
  {
    v21 = v32;
    v32 = 0;
  }
  LastErrInfo::Set(0, (struct tag_RpcInfo *)&v31);
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, Pointer);
    }
    v24 = Pointer;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v27 = 0;
    v26 = -1;
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    v23 = 0;
    v25 = -1;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !this[29] || !*v11 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, 1359);
    }
    v23 = 0;
    v24 = 1359;
    v25 = -1;
    pExceptionObject = 0;
    v26 = 281;
    throw (EvtException *)&pExceptionObject;
  }
  v15 = (BookmarkChannels *)operator new(0x28u);
  v28[0] = v15;
  if ( v15 )
  {
    *(_OWORD *)v15 = 0;
    *((_OWORD *)v15 + 1) = 0;
    *((_QWORD *)v15 + 4) = 0;
    v15 = BookmarkChannels::BookmarkChannels(v15);
  }
  wmi::AutoRef<BookmarkChannels>::operator=(this + 27, v15);
  for ( i = 0; i < *((_DWORD *)this + 84); ++i )
    BookmarkChannels::AddChannel(this[27], *((const wchar_t **)this[26] + 2 * i));
  Session::AddControllableObject(this[6], *v11);
  if ( !a4 )
    a4 = (const wchar_t *)&dword_180040824;
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( a4[v18] );
  v19 = -1;
  if ( !a3 )
    a3 = (const wchar_t *)&dword_180040824;
  do
    ++v19;
  while ( a3[v19] );
  if ( !a2 )
    a2 = (const wchar_t *)&dword_180040824;
  do
    ++v17;
  while ( a2[v17] );
  CurrentProcessId = GetCurrentProcessId();
  v28[0] = a4;
  v28[1] = v18;
  v29[0] = a3;
  v29[1] = v19;
  v30[0] = a2;
  v30[1] = v17;
  LogSubscriptionRpcTrackingEvent(CurrentProcessId, v21, (unsigned int)v30, (unsigned int)v29, (__int64)v28, 1);
  RemotePushSubscription::QueryNextAsync((HANDLE *)this);
}

```

## disassembly

```asm
0x18000dac0  push    rbp
0x18000dac2  push    rbx
0x18000dac3  push    rsi
0x18000dac4  push    rdi
0x18000dac5  push    r12
0x18000dac7  push    r13
0x18000dac9  push    r14
0x18000dacb  push    r15
0x18000dacd  lea     rbp, [rsp-1Fh]
0x18000dad2  sub     rsp, 0F8h
0x18000dad9  mov     rax, cs:__security_cookie
0x18000dae0  xor     rax, rsp
0x18000dae3  mov     [rbp+57h+var_50], rax
0x18000dae7  xor     eax, eax
0x18000dae9  mov     r13, r9
0x18000daec  mov     [rbp+57h+var_60], rax
0x18000daf0  mov     r12, r8
0x18000daf3  mov     [rbp+57h+var_58], eax
0x18000daf6  mov     r15, rdx
0x18000daf9  mov     r14, rcx
0x18000dafc  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18000db01  mov     rdx, [r14+0C0h]; struct Object *
0x18000db08  lea     r8, [r14+0C8h]; struct EvtHandleRef *
0x18000db0f  call    ?AddObject@ObjectTable@@QEAAKPEAVObject@@AEAVEvtHandleRef@@@Z; ObjectTable::AddObject(Object *,EvtHandleRef &)
0x18000db14  xor     edi, edi
0x18000db16  mov     ebx, eax
0x18000db18  test    eax, eax
0x18000db1a  jnz     loc_18000DD26
0x18000db20  lea     rsi, [r14+0F0h]
0x18000db27  mov     rcx, rsi
0x18000db2a  call    ??$replace@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>> &)
0x18000db2f  lea     rdi, [r14+0E8h]
0x18000db36  mov     rbx, rax
0x18000db39  mov     rcx, rdi
0x18000db3c  call    ??$replace@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>> &)
0x18000db41  mov     r9, [r14+30h]
0x18000db45  lea     r8, [rbp+57h+var_60]
0x18000db49  mov     [rsp+130h+var_D0], r8
0x18000db4e  lea     rdx, [r14+0D0h]
0x18000db55  mov     [rsp+130h+var_D8], rdx
0x18000db5a  lea     rcx, [r14+150h]
0x18000db61  mov     [rsp+130h+var_E0], rcx
0x18000db66  xor     r8d, r8d; pReturnValue
0x18000db69  mov     r9, [r9+48h]
0x18000db6d  lea     rcx, pProxyInfo; pProxyInfo
0x18000db74  mov     [rsp+130h+var_E8], rbx
0x18000db79  xor     edx, edx; nProcNum
0x18000db7b  mov     [rsp+130h+var_F0], rax
0x18000db80  mov     eax, [r14+148h]
0x18000db87  mov     [rsp+130h+var_F8], eax
0x18000db8b  mov     [rsp+130h+var_100], r13
0x18000db90  mov     [rsp+130h+var_108], r12
0x18000db95  mov     [rsp+130h+var_110], r15
0x18000db9a  call    cs:__imp_NdrClientCall3
0x18000dba0  xor     ecx, ecx; this
0x18000dba2  mov     rbx, rax
0x18000dba5  mov     [rbp+57h+var_C0], ecx
0x18000dba8  cmp     dword ptr [rbp+57h+var_60], ecx
0x18000dbab  jz      loc_18000DD07
0x18000dbb1  lea     rdx, [rbp+57h+var_60]; struct tag_RpcInfo *
0x18000dbb5  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x18000dbba  xor     edx, edx
0x18000dbbc  test    ebx, ebx
0x18000dbbe  jnz     loc_18000DD98
0x18000dbc4  cmp     [rdi], rdx
0x18000dbc7  jz      loc_18000DE0D
0x18000dbcd  cmp     [rsi], rdx
0x18000dbd0  jz      loc_18000DE0D
0x18000dbd6  lea     ecx, [rdx+28h]; dwBytes
0x18000dbd9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dbde  mov     [rbp+57h+var_90], rax
0x18000dbe2  test    rax, rax
0x18000dbe5  jz      short loc_18000DBFF
0x18000dbe7  xor     ecx, ecx
0x18000dbe9  xorps   xmm0, xmm0
0x18000dbec  movups  xmmword ptr [rax], xmm0
0x18000dbef  movups  xmmword ptr [rax+10h], xmm0
0x18000dbf3  mov     [rax+20h], rcx
0x18000dbf7  mov     rcx, rax; this
0x18000dbfa  call    ??0BookmarkChannels@@QEAA@XZ; BookmarkChannels::BookmarkChannels(void)
0x18000dbff  lea     rdi, [r14+0D8h]
0x18000dc06  mov     rdx, rax
0x18000dc09  mov     rcx, rdi
0x18000dc0c  call    ??4?$AutoRef@VBookmarkChannels@@@wmi@@QEAAAEAV01@PEAVBookmarkChannels@@@Z; wmi::AutoRef<BookmarkChannels>::operator=(BookmarkChannels *)
0x18000dc11  xor     ebx, ebx
0x18000dc13  cmp     [r14+150h], ebx
0x18000dc1a  ja      loc_18000DCDE
0x18000dc20  mov     rdx, [rsi]; void *
0x18000dc23  mov     rcx, [r14+30h]; this
0x18000dc27  call    ?AddControllableObject@Session@@QEAAXPEAX@Z; Session::AddControllableObject(void *)
0x18000dc2c  xor     eax, eax
0x18000dc2e  lea     rcx, dword_180040824
0x18000dc35  test    r13, r13
0x18000dc38  cmovz   r13, rcx
0x18000dc3c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dc40  mov     rsi, rbx
0x18000dc43  inc     rsi
0x18000dc46  cmp     [r13+rsi*2+0], ax
0x18000dc4c  jnz     short loc_18000DC43
0x18000dc4e  test    r12, r12
0x18000dc51  mov     rdi, rbx
0x18000dc54  cmovz   r12, rcx
0x18000dc58  inc     rdi
0x18000dc5b  cmp     [r12+rdi*2], ax
0x18000dc60  jnz     short loc_18000DC58
0x18000dc62  test    r15, r15
0x18000dc65  cmovz   r15, rcx
0x18000dc69  inc     rbx
0x18000dc6c  cmp     [r15+rbx*2], ax
0x18000dc71  jnz     short loc_18000DC69
0x18000dc73  call    cs:__imp_GetCurrentProcessId
0x18000dc79  mov     edx, [rbp+57h+var_C0]
0x18000dc7c  lea     rcx, [rbp+57h+var_90]
0x18000dc80  mov     byte ptr [rsp+130h+var_108], 1
0x18000dc85  lea     r9, [rbp+57h+var_80]
0x18000dc89  mov     [rsp+130h+var_110], rcx
0x18000dc8e  lea     r8, [rbp+57h+var_70]
0x18000dc92  mov     ecx, eax
0x18000dc94  mov     [rbp+57h+var_90], r13
0x18000dc98  mov     [rbp+57h+var_88], rsi
0x18000dc9c  mov     [rbp+57h+var_80], r12
0x18000dca0  mov     [rbp+57h+var_78], rdi
0x18000dca4  mov     [rbp+57h+var_70], r15
0x18000dca8  mov     [rbp+57h+var_68], rbx
0x18000dcac  call    ?LogSubscriptionRpcTrackingEvent@@YAXKKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@00_N@Z; LogSubscriptionRpcTrackingEvent(ulong,ulong,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)
0x18000dcb1  mov     rcx, r14; this
0x18000dcb4  call    ?QueryNextAsync@RemotePushSubscription@@AEAAXXZ; RemotePushSubscription::QueryNextAsync(void)
0x18000dcb9  mov     rcx, [rbp+57h+var_50]
0x18000dcbd  xor     rcx, rsp; StackCookie
0x18000dcc0  call    __security_check_cookie
0x18000dcc5  add     rsp, 0F8h
0x18000dccc  pop     r15
0x18000dcce  pop     r14
0x18000dcd0  pop     r13
0x18000dcd2  pop     r12
0x18000dcd4  pop     rdi
0x18000dcd5  pop     rsi
0x18000dcd6  pop     rbx
0x18000dcd7  pop     rbp
0x18000dcd8  retn
0x18000dcd9  jmp     loc_18000DBFF
0x18000dcde  mov     rdx, [r14+0D0h]
0x18000dce5  mov     rcx, [rdi]; this
0x18000dce8  mov     eax, ebx
0x18000dcea  add     rax, rax
0x18000dced  mov     rdx, [rdx+rax*8]; wchar_t *
0x18000dcf1  call    ?AddChannel@BookmarkChannels@@QEAAXPEB_W@Z; BookmarkChannels::AddChannel(wchar_t const *)
0x18000dcf6  inc     ebx
0x18000dcf8  cmp     ebx, [r14+150h]
0x18000dcff  jnb     loc_18000DC20
0x18000dd05  jmp     short loc_18000DCDE
0x18000dd07  cmp     dword ptr [rbp+57h+var_60+4], ecx
0x18000dd0a  jnz     loc_18000DBB1
0x18000dd10  mov     eax, [rbp+57h+var_58]
0x18000dd13  test    eax, eax
0x18000dd15  jz      loc_18000DBB1
0x18000dd1b  mov     [rbp+57h+var_C0], eax
0x18000dd1e  mov     [rbp+57h+var_58], ecx
0x18000dd21  jmp     loc_18000DBB1
0x18000dd26  mov     r10, cs:WPP_GLOBAL_Control
0x18000dd2d  lea     rcx, WPP_GLOBAL_Control
0x18000dd34  cmp     r10, rcx
0x18000dd37  jz      short loc_18000DD5F
0x18000dd39  test    byte ptr [r10+1Ch], 40h
0x18000dd3e  jz      short loc_18000DD5F
0x18000dd40  cmp     byte ptr [r10+19h], 2
0x18000dd45  jb      short loc_18000DD5F
0x18000dd47  mov     rcx, [r10+10h]
0x18000dd4b  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x18000dd52  mov     edx, 12h
0x18000dd57  mov     r9d, ebx
0x18000dd5a  call    WPP_SF_D
0x18000dd5f  mov     [rbp+57h+var_A0], ebx
0x18000dd62  lea     rax, word_18004024A
0x18000dd69  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dd6d  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000dd71  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000dd78  mov     [rbp+57h+var_98], ebx
0x18000dd7b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000dd7f  mov     qword ptr [rbp+57h+pExceptionObject+8], rdi
0x18000dd83  mov     [rbp+57h+var_A8], rdi
0x18000dd87  mov     [rbp+57h+var_9C], 0FFFFFFFFh
0x18000dd8e  mov     [rbp+57h+var_94], dil
0x18000dd92  call    _CxxThrowException_0
0x18000dd98  mov     rax, cs:WPP_GLOBAL_Control
0x18000dd9f  lea     rcx, WPP_GLOBAL_Control
0x18000dda6  cmp     rax, rcx
0x18000dda9  jz      short loc_18000DDD1
0x18000ddab  test    byte ptr [rax+1Ch], 40h
0x18000ddaf  jz      short loc_18000DDD1
0x18000ddb1  cmp     byte ptr [rax+19h], 2
0x18000ddb5  jb      short loc_18000DDD1
0x18000ddb7  mov     rcx, [rax+10h]
0x18000ddbb  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x18000ddc2  mov     edx, 13h
0x18000ddc7  mov     r9d, ebx
0x18000ddca  call    WPP_SF_D
0x18000ddcf  xor     edx, edx
0x18000ddd1  mov     [rbp+57h+var_A0], ebx
0x18000ddd4  lea     rax, word_18004024A
0x18000dddb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dddf  mov     qword ptr [rbp+57h+pExceptionObject+8], rdx
0x18000dde3  mov     [rbp+57h+var_94], dl
0x18000dde6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000ddea  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000ddf1  mov     [rbp+57h+var_98], ebx
0x18000ddf4  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000ddf8  mov     [rbp+57h+var_A8], 0
0x18000de00  mov     [rbp+57h+var_9C], 0FFFFFFFFh
0x18000de07  call    _CxxThrowException_0
0x18000de0d  mov     rax, cs:WPP_GLOBAL_Control
0x18000de14  lea     rcx, WPP_GLOBAL_Control
0x18000de1b  mov     ebx, 54Fh
0x18000de20  cmp     rax, rcx
0x18000de23  jz      short loc_18000DE49
0x18000de25  test    byte ptr [rax+1Ch], 40h
0x18000de29  jz      short loc_18000DE49
0x18000de2b  cmp     byte ptr [rax+19h], 2
0x18000de2f  jb      short loc_18000DE49
0x18000de31  mov     rcx, [rax+10h]
0x18000de35  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x18000de3c  mov     edx, 14h
0x18000de41  mov     r9d, ebx
0x18000de44  call    WPP_SF_D
0x18000de49  xorps   xmm0, xmm0
0x18000de4c  mov     [rbp+57h+var_A8], 0
0x18000de54  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000de5b  mov     [rbp+57h+var_A0], ebx
0x18000de5e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000de62  mov     [rbp+57h+var_9C], 0FFFFFFFFh
0x18000de69  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18000de6e  mov     [rbp+57h+var_98], 119h
0x18000de75  call    _CxxThrowException_0
```
