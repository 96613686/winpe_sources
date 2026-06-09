# CDataTransferBroker::InvokeTarget(SHARING_ACTIVATION_INFO const *)

- ea: `0x18006b250`
- end: `0x18006b3d6`
- name: `?InvokeTarget@CDataTransferBroker@@UEAAJPEBUSHARING_ACTIVATION_INFO@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(CDataTransferBroker *__hidden this, const struct SHARING_ACTIVATION_INFO *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d010`
- `0x1800299c8`
- `0x18005f630`
- `0x180060f88`
- `0x1800610dc`
- `0x18006b250`
- `0x18006df74`
- `0x18006e0c8`
- `0x18006e7e8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b267`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b267`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b3c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b3c1`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18006b358`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18006b358`

## pseudocode

```c
__int64 __fastcall CDataTransferBroker::InvokeTarget(unsigned __int64 this, const struct SHARING_ACTIVATION_INFO *a2)
{
  __int64 SharableItemType; // r15
  __int64 v5; // rcx
  int SharableItemError; // edi
  volatile int *v7; // rdx
  signed __int64 v8; // rax
  signed __int64 v9; // rtt

  EnterCriticalSection((LPCRITICAL_SECTION)(this + 24));
  SharableItemType = (unsigned int)CDataTransferBroker::_GetSharableItemType(
                                     this - 48,
                                     *(unsigned int *)(this - 48 + 160));
  SharableItemError = CDataTransferBroker::_GetSharableItemError(v5, SharableItemType);
  if ( SharableItemError >= 0 )
  {
    FreeSharingActivationInfo((struct SHARING_ACTIVATION_INFO *)(this + 408));
    SharableItemError = CreateSharingActivationInfo(
                          *(_QWORD *)a2,
                          *((unsigned int *)a2 + 2),
                          *((_QWORD *)a2 + 2),
                          *((_QWORD *)a2 + 3),
                          *((_QWORD *)a2 + 4),
                          *((_WORD *)a2 + 20),
                          (char *)a2 + 48,
                          this + 408);
    if ( SharableItemError >= 0 )
    {
      if ( (_DWORD)SharableItemType == 1 )
      {
        SharableItemError = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(this + 88) + 56LL))(
                              *(_QWORD *)(this + 88),
                              this & ((unsigned __int128)-(__int128)(this - 48) >> 64));
      }
      else
      {
        v8 = *(_QWORD *)(this + 16);
        while ( v8 >= 0 )
        {
          if ( (_DWORD)v8 != 0x7FFFFFFF )
          {
            v9 = v8;
            v8 = _InterlockedCompareExchange64((volatile signed __int64 *)(this + 16), v8 + 1, v8);
            if ( v9 != v8 )
              continue;
          }
          goto LABEL_11;
        }
        Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v8 + 16), v7);
LABEL_11:
        if ( SHCreateThread(
               CDataTransferBroker::_InvokeTargetThreadProc,
               (void *)(this - 48),
               *(_BYTE *)(this + 480) != 0 ? 40 : 4096,
               0) )
        {
          SharableItemError = 0;
        }
        else
        {
          SharableItemError = ResultFromKnownLastError();
          if ( SharableItemError < 0 )
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,CWRLObjectWithSite,IServiceProvider,IDataTransferBroker>::Release(this - 48);
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qdS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      23,
      (unsigned int)WPP_477f27c87956328522d5ba61c1bdbc13_Traceguids,
      this - 48,
      SharableItemError,
      *((_QWORD *)a2 + 2));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 24));
  return (unsigned int)SharableItemError;
}

```

## disassembly

```asm
0x18006b250  push    rbx
0x18006b252  push    rbp
0x18006b253  push    rsi
0x18006b254  push    rdi
0x18006b255  push    r14
0x18006b257  push    r15
0x18006b259  sub     rsp, 48h
0x18006b25d  mov     rsi, rcx
0x18006b260  mov     r14, rdx
0x18006b263  add     rcx, 18h; lpCriticalSection
0x18006b267  call    cs:__imp_EnterCriticalSection
0x18006b26d  lea     rbp, [rsi-30h]
0x18006b271  mov     edx, [rbp+0A0h]
0x18006b277  mov     rcx, rbp
0x18006b27a  call    ?_GetSharableItemType@CDataTransferBroker@@AEAA?AW4SharableItemType@@K@Z; CDataTransferBroker::_GetSharableItemType(ulong)
0x18006b27f  mov     edx, eax
0x18006b281  mov     r15d, eax
0x18006b284  call    ?_GetSharableItemError@CDataTransferBroker@@AEAAJW4SharableItemType@@@Z; CDataTransferBroker::_GetSharableItemError(SharableItemType)
0x18006b289  mov     edi, eax
0x18006b28b  test    eax, eax
0x18006b28d  js      loc_18006B379
0x18006b293  lea     rdi, [rsi+198h]
0x18006b29a  mov     rcx, rdi; struct SHARING_ACTIVATION_INFO *
0x18006b29d  call    ?FreeSharingActivationInfo@@YAXPEAUSHARING_ACTIVATION_INFO@@@Z; FreeSharingActivationInfo(SHARING_ACTIVATION_INFO *)
0x18006b2a2  movzx   eax, word ptr [r14+28h]
0x18006b2a7  lea     rcx, [r14+30h]
0x18006b2ab  mov     r9, [r14+18h]
0x18006b2af  mov     r8, [r14+10h]
0x18006b2b3  mov     edx, [r14+8]
0x18006b2b7  mov     [rsp+78h+var_40], rdi
0x18006b2bc  mov     [rsp+78h+var_48], rcx
0x18006b2c1  mov     rcx, [r14]
0x18006b2c4  mov     word ptr [rsp+78h+var_50], ax
0x18006b2c9  mov     rax, [r14+20h]
0x18006b2cd  mov     [rsp+78h+var_58], rax
0x18006b2d2  call    ?CreateSharingActivationInfo@@YAJPEBGW4__MIDL___MIDL_itf_sharinganddevicesprivate_0000_0000_0001@@000GPEBUSHARABLE_ITEM_DESCRIPTOR@@PEAUSHARING_ACTIVATION_INFO@@@Z; CreateSharingActivationInfo(ushort const *,__MIDL___MIDL_itf_sharinganddevicesprivate_0000_0000_0001,ushort const *,ushort const *,ushort const *,ushort,SHARABLE_ITEM_DESCRIPTOR const *,SHARING_ACTIVATION_INFO *)
0x18006b2d7  mov     edi, eax
0x18006b2d9  test    eax, eax
0x18006b2db  js      loc_18006B379
0x18006b2e1  cmp     r15d, 1
0x18006b2e5  jnz     short loc_18006B307
0x18006b2e7  mov     rcx, [rsi+58h]
0x18006b2eb  mov     rax, rbp
0x18006b2ee  neg     rax
0x18006b2f1  sbb     rdx, rdx
0x18006b2f4  mov     r8, [rcx]
0x18006b2f7  and     rdx, rsi
0x18006b2fa  mov     rax, [r8+38h]
0x18006b2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b303  mov     edi, eax
0x18006b305  jmp     short loc_18006B379
0x18006b307  mov     rax, [rsi+10h]
0x18006b30b  test    rax, rax
0x18006b30e  js      short loc_18006B325
0x18006b310  cmp     eax, 7FFFFFFFh
0x18006b315  jz      short loc_18006B332
0x18006b317  lea     rcx, [rax+1]
0x18006b31b  lock cmpxchg [rsi+10h], rcx
0x18006b321  jnz     short loc_18006B30B
0x18006b323  jmp     short loc_18006B332
0x18006b325  lea     rcx, ds:10h[rax*2]; this
0x18006b32d  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18006b332  mov     al, [rsi+1E0h]
0x18006b338  lea     rcx, ?_InvokeTargetThreadProc@CDataTransferBroker@@CAKPEAX@Z; pfnThreadProc
0x18006b33f  neg     al
0x18006b341  mov     rdx, rbp; pData
0x18006b344  sbb     r8d, r8d
0x18006b347  xor     r9d, r9d; pfnCallback
0x18006b34a  and     r8d, 0FFFFF028h
0x18006b351  add     r8d, 1000h; flags
0x18006b358  call    cs:__imp_SHCreateThread
0x18006b35e  test    eax, eax
0x18006b360  jz      short loc_18006B366
0x18006b362  xor     edi, edi
0x18006b364  jmp     short loc_18006B379
0x18006b366  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006b36b  mov     edi, eax
0x18006b36d  test    eax, eax
0x18006b36f  jns     short loc_18006B379
0x18006b371  mov     rcx, rbp
0x18006b374  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIInspectable@@VCWRLObjectWithSite@@UIServiceProvider@@UIDataTransferBroker@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,CWRLObjectWithSite,IServiceProvider,IDataTransferBroker>::Release(void)
0x18006b379  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b380  lea     rax, WPP_GLOBAL_Control
0x18006b387  cmp     rcx, rax
0x18006b38a  jz      short loc_18006B3BD
0x18006b38c  test    byte ptr [rcx+44h], 1
0x18006b390  jz      short loc_18006B3BD
0x18006b392  cmp     byte ptr [rcx+41h], 4
0x18006b396  jb      short loc_18006B3BD
0x18006b398  mov     rax, [r14+10h]
0x18006b39c  lea     r8, WPP_477f27c87956328522d5ba61c1bdbc13_Traceguids
0x18006b3a3  mov     rcx, [rcx+38h]
0x18006b3a7  mov     edx, 17h
0x18006b3ac  mov     [rsp+78h+var_50], rax
0x18006b3b1  mov     r9, rbp
0x18006b3b4  mov     dword ptr [rsp+78h+var_58], edi
0x18006b3b8  call    WPP_SF_qdS
0x18006b3bd  lea     rcx, [rsi+18h]; lpCriticalSection
0x18006b3c1  call    cs:__imp_LeaveCriticalSection
0x18006b3c7  mov     eax, edi
0x18006b3c9  add     rsp, 48h
0x18006b3cd  pop     r15
0x18006b3cf  pop     r14
0x18006b3d1  pop     rdi
0x18006b3d2  pop     rsi
0x18006b3d3  pop     rbp
0x18006b3d4  pop     rbx
0x18006b3d5  retn
```
