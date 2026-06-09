# Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync::StopActivity(void)

- ea: `0x180067090`
- end: `0x180067331`
- name: `?StopActivity@HomeCloudHandler_GetHomeCloudAsync@InternalLogger@CloudRequestor@Internal@Windows@@MEAAXXZ`
- size: `673`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800013a4`
- `0x180001a6c`
- `0x18004453c`
- `0x18004460c`
- `0x180045c98`
- `0x180067090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800670ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006728a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800670ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006728a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800672d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800672d1`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync::StopActivity(
        Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  struct Windows::Internal::CloudRequestor::InternalLogger *v6; // rax
  __int64 v7; // rcx
  _DWORD *v8; // r9
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  struct Windows::Internal::CloudRequestor::InternalLogger *v11; // rax
  __int64 v12; // rcx
  _DWORD *v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = Windows::Internal::CloudRequestor::InternalLogger::Instance();
    v7 = (__int64)v6 + 16;
    if ( !v6 )
      v7 = 8;
    v8 = *(_DWORD **)v7;
    if ( **(_DWORD **)v7 > 5u
      && (*((_QWORD *)v8 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v8 + 3) & 0x200000000000LL) == *((_QWORD *)v8 + 3) )
    {
      v9 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v30 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      LODWORD(v31) = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v32 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v27 = 0x1000000;
      v28[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)byte_18008E551,
        v9 + 8,
        (_DWORD)v8,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&SRWLock,
        (__int64)&v20,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = Windows::Internal::CloudRequestor::InternalLogger::Instance();
    v12 = (__int64)v11 + 16;
    if ( !v11 )
      v12 = 8;
    v13 = *(_DWORD **)v12;
    if ( **(_DWORD **)v12 > 5u
      && (*((_QWORD *)v13 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v13 + 3) & 0x200000000000LL) == *((_QWORD *)v13 + 3) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v15 + 72);
      v31 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v13,
        (unsigned int)&dword_18008E494,
        v15 + 8,
        v16,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180067090  push    rbp
0x180067092  push    rbx
0x180067093  push    rdi
0x180067094  lea     rbp, [rsp-47h]
0x180067099  sub     rsp, 100h
0x1800670a0  mov     rdi, [rcx+110h]
0x1800670a7  mov     rbx, rcx
0x1800670aa  mov     eax, [rdi+48h]
0x1800670ad  test    eax, eax
0x1800670af  jns     loc_18006726B
0x1800670b5  add     rdi, 50h ; 'P'
0x1800670b9  cmp     eax, [rdi+8]
0x1800670bc  jnz     loc_18006726B
0x1800670c2  test    rdi, rdi
0x1800670c5  jz      loc_18006726B
0x1800670cb  lea     rdx, [rbp+57h+SRWLock]
0x1800670cf  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800670d4  mov     rax, [rbx+110h]
0x1800670db  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800670df  mov     dword ptr [rax], 2
0x1800670e5  test    rcx, rcx
0x1800670e8  jz      short loc_1800670F0
0x1800670ea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800670f0  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x1800670f5  test    rax, rax
0x1800670f8  mov     edx, 8
0x1800670fd  lea     rcx, [rax+10h]
0x180067101  cmovz   rcx, rdx
0x180067105  mov     r9, [rcx]
0x180067108  mov     eax, [r9]
0x18006710b  cmp     eax, 5
0x18006710e  jbe     loc_18006731F
0x180067114  mov     r8, [r9+18h]
0x180067118  mov     rcx, 200000000000h
0x180067122  mov     rax, [r9+10h]
0x180067126  test    rcx, rax
0x180067129  jz      loc_18006731F
0x18006712f  mov     rax, r8
0x180067132  and     rax, rcx
0x180067135  cmp     rax, r8
0x180067138  jnz     loc_18006731F
0x18006713e  mov     rax, [rdi+78h]
0x180067142  mov     rcx, r9
0x180067145  mov     r8, [rbx+110h]
0x18006714c  mov     [rbp+57h+var_68], rax
0x180067150  add     r8, rdx
0x180067153  mov     rax, [rdi+70h]
0x180067157  lea     rdx, byte_18008E551
0x18006715e  mov     [rbp+57h+var_60], rax
0x180067162  mov     eax, [rdi+68h]
0x180067165  mov     dword ptr [rbp+57h+SRWLock], eax
0x180067168  mov     rax, [rdi+60h]
0x18006716c  mov     [rbp+57h+var_58], rax
0x180067170  mov     rax, [rdi+58h]
0x180067174  mov     [rbp+57h+var_50], rax
0x180067178  mov     eax, [rdi+50h]
0x18006717b  mov     [rbp+57h+arg_8], eax
0x18006717e  mov     rax, [rdi+48h]
0x180067182  mov     [rbp+57h+var_48], rax
0x180067186  mov     eax, [rdi+20h]
0x180067189  mov     dword ptr [rbp+57h+arg_10], eax
0x18006718c  mov     rax, [rdi+18h]
0x180067190  mov     [rbp+57h+var_40], rax
0x180067194  mov     eax, [rdi]
0x180067196  mov     [rbp+57h+arg_18], eax
0x180067199  mov     rax, [rdi+80h]
0x1800671a0  mov     [rbp+57h+var_38], rax
0x1800671a4  mov     eax, [rdi+40h]
0x1800671a7  mov     [rbp+57h+var_70], eax
0x1800671aa  mov     rax, [rdi+38h]
0x1800671ae  mov     [rbp+57h+var_30], rax
0x1800671b2  mov     eax, [rdi+8]
0x1800671b5  mov     [rbp+57h+var_6C], eax
0x1800671b8  mov     eax, 1000000h
0x1800671bd  mov     [rbp+57h+var_28], rax
0x1800671c1  mov     [rbp+57h+var_20], rax
0x1800671c5  lea     rax, [rbp+57h+var_68]
0x1800671c9  mov     [rsp+110h+var_78], rax
0x1800671d1  lea     rax, [rbp+57h+var_60]
0x1800671d5  mov     [rsp+110h+var_80], rax
0x1800671dd  lea     rax, [rbp+57h+SRWLock]
0x1800671e1  mov     [rsp+110h+var_88], rax
0x1800671e9  lea     rax, [rbp+57h+var_58]
0x1800671ed  mov     [rsp+110h+var_90], rax
0x1800671f5  lea     rax, [rbp+57h+var_50]
0x1800671f9  mov     [rsp+110h+var_98], rax
0x1800671fe  lea     rax, [rbp+57h+arg_8]
0x180067202  mov     [rsp+110h+var_A0], rax
0x180067207  lea     rax, [rbp+57h+var_48]
0x18006720b  mov     [rsp+110h+var_A8], rax
0x180067210  lea     rax, [rbp+57h+arg_10]
0x180067214  mov     [rsp+110h+var_B0], rax
0x180067219  lea     rax, [rbp+57h+var_40]
0x18006721d  mov     [rsp+110h+var_B8], rax
0x180067222  lea     rax, [rbp+57h+arg_18]
0x180067226  mov     [rsp+110h+var_C0], rax
0x18006722b  lea     rax, [rbp+57h+var_38]
0x18006722f  mov     [rsp+110h+var_C8], rax
0x180067234  lea     rax, [rbp+57h+var_70]
0x180067238  mov     [rsp+110h+var_D0], rax
0x18006723d  lea     rax, [rbp+57h+var_30]
0x180067241  mov     [rsp+110h+var_D8], rax
0x180067246  lea     rax, [rbp+57h+var_6C]
0x18006724a  mov     [rsp+110h+var_E0], rax
0x18006724f  lea     rax, [rbp+57h+var_28]
0x180067253  mov     [rsp+110h+var_E8], rax
0x180067258  lea     rax, [rbp+57h+var_20]
0x18006725c  mov     [rsp+110h+var_F0], rax
0x180067261  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180067266  jmp     loc_18006731F
0x18006726b  lea     rdx, [rbp+57h+SRWLock]
0x18006726f  call    ?LockExclusive@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180067274  mov     rax, [rbx+110h]
0x18006727b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006727f  mov     dword ptr [rax], 2
0x180067285  test    rcx, rcx
0x180067288  jz      short loc_180067290
0x18006728a  call    cs:__imp_ReleaseSRWLockExclusive
0x180067290  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180067295  test    rax, rax
0x180067298  mov     edx, 8
0x18006729d  lea     rcx, [rax+10h]
0x1800672a1  cmovz   rcx, rdx
0x1800672a5  mov     rdi, [rcx]
0x1800672a8  mov     eax, [rdi]
0x1800672aa  cmp     eax, 5
0x1800672ad  jbe     short loc_18006731F
0x1800672af  mov     rdx, [rdi+18h]
0x1800672b3  mov     rcx, 200000000000h
0x1800672bd  mov     rax, [rdi+10h]
0x1800672c1  test    rcx, rax
0x1800672c4  jz      short loc_18006731F
0x1800672c6  mov     rax, rdx
0x1800672c9  and     rax, rcx
0x1800672cc  cmp     rax, rdx
0x1800672cf  jnz     short loc_18006731F
0x1800672d1  call    cs:__imp_GetCurrentThreadId
0x1800672d7  mov     r8, [rbx+110h]
0x1800672de  lea     rdx, dword_18008E494
0x1800672e5  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800672e8  mov     rcx, rdi
0x1800672eb  mov     eax, [r8+48h]
0x1800672ef  add     r8, 8
0x1800672f3  mov     [rbp+57h+arg_8], eax
0x1800672f6  mov     eax, 1000000h
0x1800672fb  mov     [rbp+57h+arg_10], rax
0x1800672ff  lea     rax, [rbp+57h+SRWLock]
0x180067303  mov     [rsp+110h+var_E0], rax
0x180067308  lea     rax, [rbp+57h+arg_8]
0x18006730c  mov     [rsp+110h+var_E8], rax
0x180067311  lea     rax, [rbp+57h+arg_10]
0x180067315  mov     [rsp+110h+var_F0], rax
0x18006731a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006731f  mov     rcx, rbx
0x180067322  add     rsp, 100h
0x180067329  pop     rdi
0x18006732a  pop     rbx
0x18006732b  pop     rbp
0x18006732c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
