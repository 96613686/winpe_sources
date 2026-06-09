# CContentDirectory::~CContentDirectory(void)

- ea: `0x14005a1fc`
- end: `0x14005a315`
- name: `??1CContentDirectory@@UEAA@XZ`
- size: `281`
- prototype: `void __fastcall(CContentDirectory *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140054d24`

## callees

- `0x14000c920`
- `0x140024688`
- `0x140039ca8`
- `0x140047798`
- `0x140057c88`
- `0x14005a1fc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14005a23e`
- `KERNEL32!DeleteCriticalSection` at `0x14005a24b`
- `KERNEL32!DeleteCriticalSection` at `0x14005a23e`
- `KERNEL32!DeleteCriticalSection` at `0x14005a24b`

## pseudocode

```c
void __fastcall CContentDirectory::~CContentDirectory(CContentDirectory *this)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 46);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 45);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 44);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 43);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 42);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 41);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 40);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 39);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 38);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>((_QWORD *)this + 36);
  UPnPEventPublisher::~UPnPEventPublisher((CContentDirectory *)((char *)this + 88));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 10);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CContentDirectory *)((char *)this + 32));
}

```

## disassembly

```asm
0x14005a1fc  mov     [rsp+arg_0], rbx
0x14005a201  push    rdi
0x14005a202  sub     rsp, 20h
0x14005a206  mov     rbx, rcx
0x14005a209  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a210  lea     rdi, WPP_GLOBAL_Control
0x14005a217  cmp     rcx, rdi
0x14005a21a  jz      short loc_14005A237
0x14005a21c  test    byte ptr [rcx+1Ch], 1
0x14005a220  jz      short loc_14005A237
0x14005a222  mov     rcx, [rcx+10h]
0x14005a226  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005a22d  mov     edx, 0Ch
0x14005a232  call    WPP_SF_
0x14005a237  lea     rcx, [rbx+188h]; lpCriticalSection
0x14005a23e  call    cs:__imp_DeleteCriticalSection
0x14005a244  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x14005a24b  call    cs:__imp_DeleteCriticalSection
0x14005a251  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a258  cmp     rcx, rdi
0x14005a25b  jz      short loc_14005A278
0x14005a25d  test    byte ptr [rcx+1Ch], 1
0x14005a261  jz      short loc_14005A278
0x14005a263  mov     rcx, [rcx+10h]
0x14005a267  lea     r8, WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids
0x14005a26e  mov     edx, 0Dh
0x14005a273  call    WPP_SF_
0x14005a278  lea     rcx, [rbx+170h]
0x14005a27f  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a284  lea     rcx, [rbx+168h]
0x14005a28b  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a290  lea     rcx, [rbx+160h]
0x14005a297  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a29c  lea     rcx, [rbx+158h]
0x14005a2a3  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a2a8  lea     rcx, [rbx+150h]
0x14005a2af  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a2b4  lea     rcx, [rbx+148h]
0x14005a2bb  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a2c0  lea     rcx, [rbx+140h]
0x14005a2c7  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a2cc  lea     rcx, [rbx+138h]
0x14005a2d3  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a2d8  lea     rcx, [rbx+130h]
0x14005a2df  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a2e4  lea     rcx, [rbx+120h]
0x14005a2eb  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14005a2f0  lea     rcx, [rbx+58h]; this
0x14005a2f4  call    ??1UPnPEventPublisher@@UEAA@XZ; UPnPEventPublisher::~UPnPEventPublisher(void)
0x14005a2f9  lea     rcx, [rbx+50h]
0x14005a2fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14005a302  lea     rcx, [rbx+20h]; this
0x14005a306  mov     rbx, [rsp+28h+arg_0]
0x14005a30b  add     rsp, 20h
0x14005a30f  pop     rdi
0x14005a310  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
