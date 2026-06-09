# TaskXmlReader::CreateXmlReader(void)

- ea: `0x180019de0`
- end: `0x18001a15e`
- name: `?CreateXmlReader@TaskXmlReader@@AEAAJXZ`
- size: `894`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800182b0`

## callees

- `0x1800017f0`
- `0x180004c00`
- `0x1800055f8`
- `0x180005990`
- `0x180007aa0`
- `0x1800180f0`
- `0x180019de0`
- `0x18001fd3c`
- `0x1800333d4`
- `0x180033e58`
- `0x180038404`
- `0x18003843c`
- `0x180048928`
- `0x18004e90f`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `msvcrt!free` at `0x180019f44`
- `msvcrt!free` at `0x180019f44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180019ff4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180019ff4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a026`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a026`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a010`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a010`
- `XmlLite!CreateXmlReader` at `0x180019e24`
- `XmlLite!CreateXmlReader` at `0x180019e24`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall TaskXmlReader::CreateXmlReader(TaskXmlReader *this)
{
  char v2; // di
  HRESULT v3; // eax
  HRESULT v4; // ebx
  void *v6; // rcx
  void *v7; // rbx
  struct IErrorInfo *v8; // rdx
  int v9; // eax
  int v10; // edi
  void *v11; // r14
  void *v12; // r14
  void *v13; // r14
  __int64 v14; // rax
  unsigned int i; // ecx
  __int64 v16; // rax
  UINT v17; // edi
  int StringW; // eax
  WCHAR *v19; // rdi
  unsigned int j; // eax
  __int64 v21; // rax
  CBstrWriter *v22; // rax
  struct IUnknown *v23; // rax
  int *v24; // rcx
  HRESULT started; // edi
  HMODULE phModule; // [rsp+30h] [rbp-278h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-270h] BYREF
  _QWORD v28[4]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR Buffer[256]; // [rsp+60h] [rbp-248h] BYREF

  v2 = 0;
  LODWORD(phModule) = 0;
  ppvObject = 0;
  v3 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v6 = ppvObject;
    v7 = ppvObject;
    v28[1] = ppvObject;
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 8LL))(ppvObject);
      v6 = ppvObject;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( !v7 )
      _com_raise_error(-2147467261, v8);
    v9 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, *((_QWORD *)this + 4));
    if ( v9 < 0 )
    {
      v10 = TaskXmlReader::SetErrorInfoXmlLite(this, v9);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
      return v10;
    }
    v11 = (void *)*((_QWORD *)this + 7);
    if ( v11 != v7 )
    {
      *((_QWORD *)this + 7) = v7;
      _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef();
      if ( v11 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( !*((_BYTE *)this + 40) )
      goto LABEL_13;
    v22 = (CBstrWriter *)operator new(0x28u);
    v28[0] = v22;
    if ( v22 )
      v23 = (struct IUnknown *)CBstrWriter::CBstrWriter(v22);
    else
      v23 = 0;
    if ( *((struct IUnknown **)this + 3) != v23 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 3, v23);
    if ( !*((_QWORD *)this + 3) )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
      return -2147024882;
    }
    v12 = (void *)*((_QWORD *)this + 2);
    if ( v12 )
    {
      TaskXmlWriter::~TaskXmlWriter(*((TaskXmlWriter **)this + 2));
      free(v12);
    }
    v13 = operator new(0xA0u);
    v28[2] = v13;
    if ( v13 )
    {
      LODWORD(phModule) = 65542;
      _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(
        v28,
        (char *)this + 24);
      v2 = 1;
      v14 = TaskXmlWriter::TaskXmlWriter(v13, v28, &phModule);
    }
    else
    {
      v14 = 0;
    }
    *((_QWORD *)this + 2) = v14;
    if ( (v2 & 1) != 0 )
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v28);
    v24 = (int *)*((_QWORD *)this + 2);
    if ( !v24 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
      return -2147024882;
    }
    started = TaskXmlWriter::StartDocument(v24, 65542);
    if ( started >= 0 )
    {
LABEL_13:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
      return 0;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
    return started;
  }
  else if ( v3 < -1072894464 || v3 > -1072893953 )
  {
    return TaskXmlReader::SetErrorInfo(this, v3, 0, 0, 0, 0);
  }
  else
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    for ( i = 0; i < 0x3C; ++i )
    {
      v16 = 2LL * i;
      if ( v4 == dword_18007A870[v16] )
      {
        v17 = dword_18007A874[v16];
        phModule = 0;
        if ( GetModuleHandleExW(4u, &_ImageBase, &phModule) )
        {
          StringW = LoadStringW(phModule, v17, Buffer, 256);
          v19 = Buffer;
          if ( !StringW )
            v19 = 0;
          FreeLibrary(phModule);
          if ( v19 )
          {
LABEL_33:
            v21 = -1;
            do
              ++v21;
            while ( v19[v21] );
            return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v19, v21);
          }
        }
        break;
      }
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= 0x3C )
      {
        v19 = 0;
        goto LABEL_37;
      }
      if ( v4 == dword_180073890[4 * j] )
        break;
    }
    v19 = (&off_180073898)[2 * j];
    if ( v19 )
      goto LABEL_33;
LABEL_37:
    LODWORD(v21) = 0;
    return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v19, v21);
  }
}

```

## disassembly

```asm
0x180019de0  push    rbx
0x180019de2  push    rbp
0x180019de3  push    rsi
0x180019de4  push    rdi
0x180019de5  push    r14
0x180019de7  push    r15
0x180019de9  sub     rsp, 278h
0x180019df0  mov     rax, cs:__security_cookie
0x180019df7  xor     rax, rsp
0x180019dfa  mov     [rsp+2A8h+var_48], rax
0x180019e02  mov     rsi, rcx
0x180019e05  xor     r15d, r15d
0x180019e08  mov     edi, r15d
0x180019e0b  mov     dword ptr [rsp+2A8h+phModule], r15d
0x180019e10  mov     [rsp+2A8h+ppvObject], r15
0x180019e15  xor     r8d, r8d; pMalloc
0x180019e18  lea     rdx, [rsp+2A8h+ppvObject]; ppvObject
0x180019e1d  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180019e24  call    cs:__imp_CreateXmlReader
0x180019e2a  mov     ebx, eax
0x180019e2c  test    eax, eax
0x180019e2e  jns     short loc_180019E75
0x180019e30  cmp     eax, 0C00CEE00h
0x180019e35  jge     loc_180019F97
0x180019e3b  mov     [rsp+2A8h+var_280], r15d; unsigned int
0x180019e40  mov     [rsp+2A8h+var_288], r15; unsigned __int16 *
0x180019e45  mov     edx, ebx; int
0x180019e47  xor     r9d, r9d; unsigned int
0x180019e4a  xor     r8d, r8d; unsigned __int16 *
0x180019e4d  mov     rcx, rsi; this
0x180019e50  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180019e55  mov     rcx, [rsp+2A8h+var_48]
0x180019e5d  xor     rcx, rsp; StackCookie
0x180019e60  call    __security_check_cookie
0x180019e65  add     rsp, 278h
0x180019e6c  pop     r15
0x180019e6e  pop     r14
0x180019e70  pop     rdi
0x180019e71  pop     rsi
0x180019e72  pop     rbp
0x180019e73  pop     rbx
0x180019e74  retn
0x180019e75  mov     rcx, [rsp+2A8h+ppvObject]
0x180019e7a  mov     rbx, rcx
0x180019e7d  mov     [rsp+2A8h+var_260], rcx
0x180019e82  test    rcx, rcx
0x180019e85  jz      short loc_180019E98
0x180019e87  mov     rax, [rcx]
0x180019e8a  mov     rax, [rax+8]
0x180019e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e93  mov     rcx, [rsp+2A8h+ppvObject]
0x180019e98  mov     rax, [rcx]
0x180019e9b  mov     rax, [rax+10h]
0x180019e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ea4  test    rbx, rbx
0x180019ea7  jz      loc_18001A084
0x180019ead  mov     rax, [rbx]
0x180019eb0  mov     rdx, [rsi+20h]
0x180019eb4  mov     rcx, rbx
0x180019eb7  mov     rax, [rax+18h]
0x180019ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ec0  test    eax, eax
0x180019ec2  jns     short loc_180019EE7
0x180019ec4  mov     edx, eax; int
0x180019ec6  mov     rcx, rsi; this
0x180019ec9  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x180019ece  mov     edi, eax
0x180019ed0  mov     rcx, [rbx]
0x180019ed3  mov     rax, [rcx+10h]
0x180019ed7  mov     rcx, rbx
0x180019eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019edf  nop
0x180019ee0  mov     eax, edi
0x180019ee2  jmp     loc_180019E55
0x180019ee7  lea     rcx, [rsi+38h]
0x180019eeb  mov     r14, [rcx]
0x180019eee  cmp     r14, rbx
0x180019ef1  jz      short loc_180019F04
0x180019ef3  mov     [rcx], rbx
0x180019ef6  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x180019efb  test    r14, r14
0x180019efe  jnz     loc_18001A08F
0x180019f04  cmp     byte ptr [rsi+28h], 0
0x180019f08  jnz     loc_18001A0A3
0x180019f0e  mov     rax, [rbx]
0x180019f11  mov     rcx, rbx
0x180019f14  mov     rax, [rax+10h]
0x180019f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f1d  nop
0x180019f1e  xor     eax, eax
0x180019f20  jmp     loc_180019E55
0x180019f25  cmp     qword ptr [rsi+18h], 0
0x180019f2a  jz      loc_18001A0DF
0x180019f30  mov     r14, [rsi+10h]
0x180019f34  test    r14, r14
0x180019f37  jz      short loc_180019F4A
0x180019f39  mov     rcx, r14; this
0x180019f3c  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x180019f41  mov     rcx, r14; Block
0x180019f44  call    cs:__imp_free
0x180019f4a  mov     ecx, 0A0h; unsigned __int64
0x180019f4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019f54  mov     r14, rax
0x180019f57  mov     [rsp+2A8h+var_258], rax
0x180019f5c  test    rax, rax
0x180019f5f  jz      loc_18001A0F9
0x180019f65  mov     dword ptr [rsp+2A8h+phModule], 10006h
0x180019f6d  lea     rdx, [rsi+18h]
0x180019f71  lea     rcx, [rsp+2A8h+var_268]
0x180019f76  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x180019f7b  mov     edi, 1
0x180019f80  lea     r8, [rsp+2A8h+phModule]
0x180019f85  lea     rdx, [rsp+2A8h+var_268]
0x180019f8a  mov     rcx, r14
0x180019f8d  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x180019f92  jmp     loc_18001A0FC
0x180019f97  cmp     ebx, 0C00CEFFFh
0x180019f9d  jg      loc_180019E3B
0x180019fa3  xor     edx, edx; Val
0x180019fa5  mov     r8d, 200h; Size
0x180019fab  lea     rcx, [rsp+2A8h+Buffer]; void *
0x180019fb0  call    memset_0
0x180019fb5  mov     ecx, r15d
0x180019fb8  lea     rbp, __ImageBase
0x180019fbf  cmp     ecx, 3Ch ; '<'
0x180019fc2  jnb     short loc_18001A031
0x180019fc4  mov     eax, ecx
0x180019fc6  lea     rax, ds:0[rax*8]
0x180019fce  cmp     ebx, [rax+rbp+7A870h]
0x180019fd5  jz      short loc_180019FDB
0x180019fd7  inc     ecx
0x180019fd9  jmp     short loc_180019FBF
0x180019fdb  mov     edi, [rax+rbp+7A874h]
0x180019fe2  mov     [rsp+2A8h+phModule], r15
0x180019fe7  lea     r8, [rsp+2A8h+phModule]; phModule
0x180019fec  mov     rdx, rbp; lpModuleName
0x180019fef  mov     ecx, 4; dwFlags
0x180019ff4  call    cs:__imp_GetModuleHandleExW
0x180019ffa  test    eax, eax
0x180019ffc  jz      short loc_18001A031
0x180019ffe  mov     r9d, 100h; cchBufferMax
0x18001a004  lea     r8, [rsp+2A8h+Buffer]; lpBuffer
0x18001a009  mov     edx, edi; uID
0x18001a00b  mov     rcx, [rsp+2A8h+phModule]; hInstance
0x18001a010  call    cs:__imp_LoadStringW
0x18001a016  lea     rdi, [rsp+2A8h+Buffer]
0x18001a01b  test    eax, eax
0x18001a01d  cmovz   rdi, r15
0x18001a021  mov     rcx, [rsp+2A8h+phModule]; hLibModule
0x18001a026  call    cs:__imp_FreeLibrary
0x18001a02c  test    rdi, rdi
0x18001a02f  jnz     short loc_18001A058
0x18001a031  mov     eax, r15d
0x18001a034  cmp     eax, 3Ch ; '<'
0x18001a037  jnb     short loc_18001A06B
0x18001a039  mov     edi, eax
0x18001a03b  add     rdi, rdi
0x18001a03e  cmp     ebx, ss:rva dword_180073890[rbp+rdi*8]
0x18001a045  jz      short loc_18001A04B
0x18001a047  inc     eax
0x18001a049  jmp     short loc_18001A034
0x18001a04b  mov     rdi, ss:rva off_180073898[rbp+rdi*8]; "ERROR: unexpected end of input" ...
0x18001a053  test    rdi, rdi
0x18001a056  jz      short loc_18001A06E
0x18001a058  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001a05f  inc     rax
0x18001a062  cmp     [rdi+rax*2], r15w
0x18001a067  jnz     short loc_18001A05F
0x18001a069  jmp     short loc_18001A071
0x18001a06b  mov     rdi, r15
0x18001a06e  mov     rax, r15
0x18001a071  mov     [rsp+2A8h+var_280], eax
0x18001a075  mov     [rsp+2A8h+var_288], rdi
0x18001a07a  mov     edx, 8004131Ah
0x18001a07f  jmp     loc_180019E47
0x18001a084  mov     ecx, 80004003h; int
0x18001a089  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001a08f  mov     rax, [r14]
0x18001a092  mov     rcx, r14
0x18001a095  mov     rax, [rax+10h]
0x18001a099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a09e  jmp     loc_180019F04
0x18001a0a3  mov     ecx, 28h ; '('; unsigned __int64
0x18001a0a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a0ad  mov     [rsp+2A8h+var_268], rax
0x18001a0b2  test    rax, rax
0x18001a0b5  jz      short loc_18001A0C1
0x18001a0b7  mov     rcx, rax; this
0x18001a0ba  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18001a0bf  jmp     short loc_18001A0C4
0x18001a0c1  mov     rax, r15
0x18001a0c4  cmp     [rsi+18h], rax
0x18001a0c8  jz      loc_180019F25
0x18001a0ce  mov     rdx, rax; struct IUnknown *
0x18001a0d1  lea     rcx, [rsi+18h]; struct IUnknown **
0x18001a0d5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001a0da  jmp     loc_180019F25
0x18001a0df  mov     rax, [rbx]
0x18001a0e2  mov     rcx, rbx
0x18001a0e5  mov     rax, [rax+10h]
0x18001a0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0ee  nop
0x18001a0ef  mov     eax, 8007000Eh
0x18001a0f4  jmp     loc_180019E55
0x18001a0f9  mov     rax, r15
0x18001a0fc  mov     [rsi+10h], rax
0x18001a100  test    dil, 1
0x18001a104  jz      short loc_18001A110
0x18001a106  lea     rcx, [rsp+2A8h+var_268]
0x18001a10b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a110  mov     rcx, [rsi+10h]
0x18001a114  test    rcx, rcx
0x18001a117  jnz     short loc_18001A133
0x18001a119  mov     rax, [rbx]
0x18001a11c  mov     rcx, rbx
0x18001a11f  mov     rax, [rax+10h]
0x18001a123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a128  nop
0x18001a129  mov     eax, 8007000Eh
0x18001a12e  jmp     loc_180019E55
0x18001a133  mov     edx, 10006h
0x18001a138  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x18001a13d  mov     edi, eax
0x18001a13f  test    eax, eax
0x18001a141  jns     loc_180019F0E
0x18001a147  mov     rcx, [rbx]
0x18001a14a  mov     rax, [rcx+10h]
0x18001a14e  mov     rcx, rbx
0x18001a151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a156  nop
0x18001a157  mov     eax, edi
0x18001a159  jmp     loc_180019E55
```
