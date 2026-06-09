# CMediaReceiverRegistrar::~CMediaReceiverRegistrar(void)

- ea: `0x14005f1e8`
- end: `0x14005f2c2`
- name: `??1CMediaReceiverRegistrar@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(CMediaReceiverRegistrar *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140054d7c`

## callees

- `0x14000c920`
- `0x140024688`
- `0x140039ca8`
- `0x140047798`
- `0x140057c88`
- `0x14005f1e8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14005f264`
- `KERNEL32!DeleteCriticalSection` at `0x14005f264`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005f22f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005f24c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005f22f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005f24c`

## pseudocode

```c
void __fastcall CMediaReceiverRegistrar::~CMediaReceiverRegistrar(CMediaReceiverRegistrar *this)
{
  SAFEARRAY *v2; // rcx
  SAFEARRAY *v3; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_cfe372551e093b9f0da9f257a05b1fd6_Traceguids);
  v2 = (SAFEARRAY *)*((_QWORD *)this + 31);
  if ( v2 )
  {
    SafeArrayDestroy(v2);
    *((_QWORD *)this + 31) = 0;
  }
  v3 = (SAFEARRAY *)*((_QWORD *)this + 32);
  if ( v3 )
  {
    SafeArrayDestroy(v3);
    *((_QWORD *)this + 32) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_cfe372551e093b9f0da9f257a05b1fd6_Traceguids);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 30);
  UPnPEventPublisher::~UPnPEventPublisher((CMediaReceiverRegistrar *)((char *)this + 80));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 9);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CMediaReceiverRegistrar *)((char *)this + 24));
}

```

## disassembly

```asm
0x14005f1e8  mov     [rsp+arg_0], rbx
0x14005f1ed  push    rdi
0x14005f1ee  sub     rsp, 20h
0x14005f1f2  mov     rbx, rcx
0x14005f1f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f1fc  lea     rdi, WPP_GLOBAL_Control
0x14005f203  cmp     rcx, rdi
0x14005f206  jz      short loc_14005F223
0x14005f208  test    byte ptr [rcx+1Ch], 1
0x14005f20c  jz      short loc_14005F223
0x14005f20e  mov     rcx, [rcx+10h]
0x14005f212  lea     r8, WPP_cfe372551e093b9f0da9f257a05b1fd6_Traceguids
0x14005f219  mov     edx, 0Ch
0x14005f21e  call    WPP_SF_
0x14005f223  mov     rcx, [rbx+0F8h]; psa
0x14005f22a  test    rcx, rcx
0x14005f22d  jz      short loc_14005F240
0x14005f22f  call    cs:__imp_SafeArrayDestroy
0x14005f235  mov     qword ptr [rbx+0F8h], 0
0x14005f240  mov     rcx, [rbx+100h]; psa
0x14005f247  test    rcx, rcx
0x14005f24a  jz      short loc_14005F25D
0x14005f24c  call    cs:__imp_SafeArrayDestroy
0x14005f252  mov     qword ptr [rbx+100h], 0
0x14005f25d  lea     rcx, [rbx+120h]; lpCriticalSection
0x14005f264  call    cs:__imp_DeleteCriticalSection
0x14005f26a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f271  cmp     rcx, rdi
0x14005f274  jz      short loc_14005F291
0x14005f276  test    byte ptr [rcx+1Ch], 1
0x14005f27a  jz      short loc_14005F291
0x14005f27c  mov     rcx, [rcx+10h]
0x14005f280  lea     r8, WPP_cfe372551e093b9f0da9f257a05b1fd6_Traceguids
0x14005f287  mov     edx, 0Dh
0x14005f28c  call    WPP_SF_
0x14005f291  lea     rcx, [rbx+0F0h]
0x14005f298  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005f29d  lea     rcx, [rbx+50h]; this
0x14005f2a1  call    ??1UPnPEventPublisher@@UEAA@XZ; UPnPEventPublisher::~UPnPEventPublisher(void)
0x14005f2a6  lea     rcx, [rbx+48h]
0x14005f2aa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14005f2af  lea     rcx, [rbx+18h]; this
0x14005f2b3  mov     rbx, [rsp+28h+arg_0]
0x14005f2b8  add     rsp, 20h
0x14005f2bc  pop     rdi
0x14005f2bd  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
