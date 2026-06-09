# CCDLAgent::~CCDLAgent(void)

- ea: `0x180003a7c`
- end: `0x180003bca`
- name: `??1CCDLAgent@@EEAA@XZ`
- size: `334`
- prototype: `void __fastcall(CCDLAgent *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180003bd0`

## callees

- `0x180003a7c`
- `0x1800042c0`
- `0x180004bd0`
- `0x18001ba40`
- `0x18002a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003b1e`
- `ole32!CoTaskMemFree` at `0x180003bac`
- `ole32!CoTaskMemFree` at `0x180003b1e`
- `ole32!CoTaskMemFree` at `0x180003bac`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b3b`

## pseudocode

```c
void __fastcall CCDLAgent::~CCDLAgent(CCDLAgent *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  OLECHAR *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  *(_QWORD *)this = &CCDLAgent::`vftable'{for `ISubscriptionAgentControl'};
  *((_QWORD *)this + 1) = &CCDLAgent::`vftable'{for `IShellPropSheetExt'};
  *((_QWORD *)this + 2) = &CWebCrawler::`vftable'{for `IExtractIconA'};
  *((_QWORD *)this + 3) = &CCDLAgent::`vftable'{for `IExtractIconW'};
  *((_QWORD *)this + 4) = &CWebCrawler::`vftable'{for `ISubscriptionAgentShellExt'};
  *((_QWORD *)this + 14) = &CCDLAgent::`vftable';
  v2 = *((_QWORD *)this + 15);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 15) = 0;
  }
  v3 = *((_QWORD *)this + 30);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 30) = 0;
  }
  CRunDeliveryAgent::SafeRelease((struct CRunDeliveryAgent **)this + 35);
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 27);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 27) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 21);
  if ( v6 )
  {
    operator delete(v6);
    *((_QWORD *)this + 21) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 20);
  if ( v7 )
  {
    operator delete(v7);
    *((_QWORD *)this + 20) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 22);
  if ( v8 )
  {
    operator delete(v8);
    *((_QWORD *)this + 22) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 17);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 17) = 0;
  }
  CDeliveryAgent::~CDeliveryAgent(this);
}

```

## disassembly

```asm
0x180003a7c  push    rbx
0x180003a7e  sub     rsp, 20h
0x180003a82  lea     rax, ??_7CCDLAgent@@6BISubscriptionAgentControl@@@; const CCDLAgent::`vftable'{for `ISubscriptionAgentControl'}
0x180003a89  mov     rbx, rcx
0x180003a8c  mov     [rcx], rax
0x180003a8f  lea     rax, ??_7CCDLAgent@@6BIShellPropSheetExt@@@; const CCDLAgent::`vftable'{for `IShellPropSheetExt'}
0x180003a96  mov     [rcx+8], rax
0x180003a9a  lea     rax, ??_7CWebCrawler@@6BIExtractIconA@@@; const CWebCrawler::`vftable'{for `IExtractIconA'}
0x180003aa1  mov     [rcx+10h], rax
0x180003aa5  lea     rax, ??_7CCDLAgent@@6BIExtractIconW@@@; const CCDLAgent::`vftable'{for `IExtractIconW'}
0x180003aac  mov     [rcx+18h], rax
0x180003ab0  lea     rax, ??_7CWebCrawler@@6BISubscriptionAgentShellExt@@@; const CWebCrawler::`vftable'{for `ISubscriptionAgentShellExt'}
0x180003ab7  mov     [rcx+20h], rax
0x180003abb  lea     rax, ??_7CCDLAgent@@6B@; const CCDLAgent::`vftable'
0x180003ac2  mov     [rcx+70h], rax
0x180003ac6  mov     rcx, [rcx+78h]
0x180003aca  test    rcx, rcx
0x180003acd  jz      short loc_180003AE3
0x180003acf  mov     rax, [rcx]
0x180003ad2  mov     rax, [rax+10h]
0x180003ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003adb  mov     qword ptr [rbx+78h], 0
0x180003ae3  mov     rcx, [rbx+0F0h]
0x180003aea  test    rcx, rcx
0x180003aed  jz      short loc_180003B06
0x180003aef  mov     rax, [rcx]
0x180003af2  mov     rax, [rax+10h]
0x180003af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afb  mov     qword ptr [rbx+0F0h], 0
0x180003b06  lea     rcx, [rbx+118h]; struct CRunDeliveryAgent **
0x180003b0d  call    ?SafeRelease@CRunDeliveryAgent@@SAXAEAPEAV1@@Z; CRunDeliveryAgent::SafeRelease(CRunDeliveryAgent * &)
0x180003b12  mov     rcx, [rbx+80h]; pv
0x180003b19  test    rcx, rcx
0x180003b1c  jz      short loc_180003B2F
0x180003b1e  call    cs:__imp_CoTaskMemFree
0x180003b24  mov     qword ptr [rbx+80h], 0
0x180003b2f  mov     rcx, [rbx+0D8h]; bstrString
0x180003b36  test    rcx, rcx
0x180003b39  jz      short loc_180003B4C
0x180003b3b  call    cs:__imp_SysFreeString
0x180003b41  mov     qword ptr [rbx+0D8h], 0
0x180003b4c  mov     rcx, [rbx+0A8h]; lpMem
0x180003b53  test    rcx, rcx
0x180003b56  jz      short loc_180003B68
0x180003b58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b5d  mov     qword ptr [rbx+0A8h], 0
0x180003b68  mov     rcx, [rbx+0A0h]; lpMem
0x180003b6f  test    rcx, rcx
0x180003b72  jz      short loc_180003B84
0x180003b74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b79  mov     qword ptr [rbx+0A0h], 0
0x180003b84  mov     rcx, [rbx+0B0h]; lpMem
0x180003b8b  test    rcx, rcx
0x180003b8e  jz      short loc_180003BA0
0x180003b90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b95  mov     qword ptr [rbx+0B0h], 0
0x180003ba0  mov     rcx, [rbx+88h]; pv
0x180003ba7  test    rcx, rcx
0x180003baa  jz      short loc_180003BBD
0x180003bac  call    cs:__imp_CoTaskMemFree
0x180003bb2  mov     qword ptr [rbx+88h], 0
0x180003bbd  mov     rcx, rbx; this
0x180003bc0  add     rsp, 20h
0x180003bc4  pop     rbx
0x180003bc5  jmp     ??1CDeliveryAgent@@MEAA@XZ; CDeliveryAgent::~CDeliveryAgent(void)
```
