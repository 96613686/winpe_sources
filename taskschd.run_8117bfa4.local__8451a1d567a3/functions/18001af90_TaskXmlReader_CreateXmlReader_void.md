# TaskXmlReader::CreateXmlReader(void)

- ea: `0x18001af90`
- end: `0x18001b32d`
- name: `?CreateXmlReader@TaskXmlReader@@AEAAJXZ`
- size: `925`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800193f0`

## callees

- `0x180001880`
- `0x180004ee0`
- `0x180005924`
- `0x180005c50`
- `0x180007e90`
- `0x180019228`
- `0x18001af90`
- `0x180020ddc`
- `0x1800361b0`
- `0x180036bd8`
- `0x18003b514`
- `0x18003b74c`
- `0x18004c438`
- `0x18005260b`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `msvcrt!free` at `0x18001b0fb`
- `msvcrt!free` at `0x18001b0fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001b1b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001b1b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b1ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b1ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001b1d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001b1d3`
- `XmlLite!CreateXmlReader` at `0x18001afd4`
- `XmlLite!CreateXmlReader` at `0x18001afd4`

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
      if ( v4 == dword_18007E850[v16] )
      {
        v17 = dword_18007E854[v16];
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
      if ( v4 == dword_180077870[4 * j] )
        break;
    }
    v19 = (&off_180077878)[2 * j];
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
0x18001af90  push    rbx
0x18001af92  push    rbp
0x18001af93  push    rsi
0x18001af94  push    rdi
0x18001af95  push    r14
0x18001af97  push    r15
0x18001af99  sub     rsp, 278h
0x18001afa0  mov     rax, cs:__security_cookie
0x18001afa7  xor     rax, rsp
0x18001afaa  mov     [rsp+2A8h+var_48], rax
0x18001afb2  mov     rsi, rcx
0x18001afb5  xor     r15d, r15d
0x18001afb8  mov     edi, r15d
0x18001afbb  mov     dword ptr [rsp+2A8h+phModule], r15d
0x18001afc0  mov     [rsp+2A8h+ppvObject], r15
0x18001afc5  xor     r8d, r8d; pMalloc
0x18001afc8  lea     rdx, [rsp+2A8h+ppvObject]; ppvObject
0x18001afcd  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18001afd4  call    cs:__imp_CreateXmlReader
0x18001afdb  nop     dword ptr [rax+rax+00h]
0x18001afe0  mov     ebx, eax
0x18001afe2  test    eax, eax
0x18001afe4  jns     short loc_18001B02C
0x18001afe6  cmp     eax, 0C00CEE00h
0x18001afeb  jge     loc_18001B154
0x18001aff1  mov     [rsp+2A8h+var_280], r15d; unsigned int
0x18001aff6  mov     [rsp+2A8h+var_288], r15; unsigned __int16 *
0x18001affb  mov     edx, ebx; int
0x18001affd  xor     r9d, r9d; unsigned int
0x18001b000  xor     r8d, r8d; unsigned __int16 *
0x18001b003  mov     rcx, rsi; this
0x18001b006  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x18001b00b  mov     rcx, [rsp+2A8h+var_48]
0x18001b013  xor     rcx, rsp; StackCookie
0x18001b016  call    __security_check_cookie
0x18001b01b  add     rsp, 278h
0x18001b022  pop     r15
0x18001b024  pop     r14
0x18001b026  pop     rdi
0x18001b027  pop     rsi
0x18001b028  pop     rbp
0x18001b029  pop     rbx
0x18001b02a  retn
0x18001b02c  mov     rcx, [rsp+2A8h+ppvObject]
0x18001b031  mov     rbx, rcx
0x18001b034  mov     [rsp+2A8h+var_260], rcx
0x18001b039  test    rcx, rcx
0x18001b03c  jz      short loc_18001B04F
0x18001b03e  mov     rax, [rcx]
0x18001b041  mov     rax, [rax+8]
0x18001b045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b04a  mov     rcx, [rsp+2A8h+ppvObject]
0x18001b04f  mov     rax, [rcx]
0x18001b052  mov     rax, [rax+10h]
0x18001b056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b05b  test    rbx, rbx
0x18001b05e  jz      loc_18001B253
0x18001b064  mov     rax, [rbx]
0x18001b067  mov     rdx, [rsi+20h]
0x18001b06b  mov     rcx, rbx
0x18001b06e  mov     rax, [rax+18h]
0x18001b072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b077  test    eax, eax
0x18001b079  jns     short loc_18001B09E
0x18001b07b  mov     edx, eax; int
0x18001b07d  mov     rcx, rsi; this
0x18001b080  call    ?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z; TaskXmlReader::SetErrorInfoXmlLite(long)
0x18001b085  mov     edi, eax
0x18001b087  mov     rcx, [rbx]
0x18001b08a  mov     rax, [rcx+10h]
0x18001b08e  mov     rcx, rbx
0x18001b091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b096  nop
0x18001b097  mov     eax, edi
0x18001b099  jmp     loc_18001B00B
0x18001b09e  lea     rcx, [rsi+38h]
0x18001b0a2  mov     r14, [rcx]
0x18001b0a5  cmp     r14, rbx
0x18001b0a8  jz      short loc_18001B0BB
0x18001b0aa  mov     [rcx], rbx
0x18001b0ad  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x18001b0b2  test    r14, r14
0x18001b0b5  jnz     loc_18001B25E
0x18001b0bb  cmp     byte ptr [rsi+28h], 0
0x18001b0bf  jnz     loc_18001B272
0x18001b0c5  mov     rax, [rbx]
0x18001b0c8  mov     rcx, rbx
0x18001b0cb  mov     rax, [rax+10h]
0x18001b0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0d4  nop
0x18001b0d5  xor     eax, eax
0x18001b0d7  jmp     loc_18001B00B
0x18001b0dc  cmp     qword ptr [rsi+18h], 0
0x18001b0e1  jz      loc_18001B2AE
0x18001b0e7  mov     r14, [rsi+10h]
0x18001b0eb  test    r14, r14
0x18001b0ee  jz      short loc_18001B107
0x18001b0f0  mov     rcx, r14; this
0x18001b0f3  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x18001b0f8  mov     rcx, r14; Block
0x18001b0fb  call    cs:__imp_free
0x18001b102  nop     dword ptr [rax+rax+00h]
0x18001b107  mov     ecx, 0A0h; unsigned __int64
0x18001b10c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b111  mov     r14, rax
0x18001b114  mov     [rsp+2A8h+var_258], rax
0x18001b119  test    rax, rax
0x18001b11c  jz      loc_18001B2C8
0x18001b122  mov     dword ptr [rsp+2A8h+phModule], 10006h
0x18001b12a  lea     rdx, [rsi+18h]
0x18001b12e  lea     rcx, [rsp+2A8h+var_268]
0x18001b133  call    ??$?0V?$CComPtr@UIStream@@@ATL@@@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@AEBV?$CComPtr@UIStream@@@ATL@@@Z; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(ATL::CComPtr<IStream> const &)
0x18001b138  mov     edi, 1
0x18001b13d  lea     r8, [rsp+2A8h+phModule]
0x18001b142  lea     rdx, [rsp+2A8h+var_268]
0x18001b147  mov     rcx, r14
0x18001b14a  call    ??0TaskXmlWriter@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEBUSchema@@@Z; TaskXmlWriter::TaskXmlWriter(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,Schema const &)
0x18001b14f  jmp     loc_18001B2CB
0x18001b154  cmp     ebx, 0C00CEFFFh
0x18001b15a  jg      loc_18001AFF1
0x18001b160  xor     edx, edx; Val
0x18001b162  mov     r8d, 200h; Size
0x18001b168  lea     rcx, [rsp+2A8h+Buffer]; void *
0x18001b16d  call    memset_0
0x18001b172  mov     ecx, r15d
0x18001b175  lea     rbp, __ImageBase
0x18001b17c  cmp     ecx, 3Ch ; '<'
0x18001b17f  jnb     short loc_18001B200
0x18001b181  mov     eax, ecx
0x18001b183  lea     rax, ds:0[rax*8]
0x18001b18b  cmp     ebx, [rax+rbp+7E850h]
0x18001b192  jz      short loc_18001B198
0x18001b194  inc     ecx
0x18001b196  jmp     short loc_18001B17C
0x18001b198  mov     edi, [rax+rbp+7E854h]
0x18001b19f  mov     [rsp+2A8h+phModule], r15
0x18001b1a4  lea     r8, [rsp+2A8h+phModule]; phModule
0x18001b1a9  mov     rdx, rbp; lpModuleName
0x18001b1ac  mov     ecx, 4; dwFlags
0x18001b1b1  call    cs:__imp_GetModuleHandleExW
0x18001b1b8  nop     dword ptr [rax+rax+00h]
0x18001b1bd  test    eax, eax
0x18001b1bf  jz      short loc_18001B200
0x18001b1c1  mov     r9d, 100h; cchBufferMax
0x18001b1c7  lea     r8, [rsp+2A8h+Buffer]; lpBuffer
0x18001b1cc  mov     edx, edi; uID
0x18001b1ce  mov     rcx, [rsp+2A8h+phModule]; hInstance
0x18001b1d3  call    cs:__imp_LoadStringW
0x18001b1da  nop     dword ptr [rax+rax+00h]
0x18001b1df  lea     rdi, [rsp+2A8h+Buffer]
0x18001b1e4  test    eax, eax
0x18001b1e6  cmovz   rdi, r15
0x18001b1ea  mov     rcx, [rsp+2A8h+phModule]; hLibModule
0x18001b1ef  call    cs:__imp_FreeLibrary
0x18001b1f6  nop     dword ptr [rax+rax+00h]
0x18001b1fb  test    rdi, rdi
0x18001b1fe  jnz     short loc_18001B227
0x18001b200  mov     eax, r15d
0x18001b203  cmp     eax, 3Ch ; '<'
0x18001b206  jnb     short loc_18001B23A
0x18001b208  mov     edi, eax
0x18001b20a  add     rdi, rdi
0x18001b20d  cmp     ebx, ss:rva dword_180077870[rbp+rdi*8]
0x18001b214  jz      short loc_18001B21A
0x18001b216  inc     eax
0x18001b218  jmp     short loc_18001B203
0x18001b21a  mov     rdi, ss:rva off_180077878[rbp+rdi*8]; "ERROR: unexpected end of input" ...
0x18001b222  test    rdi, rdi
0x18001b225  jz      short loc_18001B23D
0x18001b227  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001b22e  inc     rax
0x18001b231  cmp     [rdi+rax*2], r15w
0x18001b236  jnz     short loc_18001B22E
0x18001b238  jmp     short loc_18001B240
0x18001b23a  mov     rdi, r15
0x18001b23d  mov     rax, r15
0x18001b240  mov     [rsp+2A8h+var_280], eax
0x18001b244  mov     [rsp+2A8h+var_288], rdi
0x18001b249  mov     edx, 8004131Ah
0x18001b24e  jmp     loc_18001AFFD
0x18001b253  mov     ecx, 80004003h; int
0x18001b258  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001b25e  mov     rax, [r14]
0x18001b261  mov     rcx, r14
0x18001b264  mov     rax, [rax+10h]
0x18001b268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b26d  jmp     loc_18001B0BB
0x18001b272  mov     ecx, 28h ; '('; unsigned __int64
0x18001b277  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b27c  mov     [rsp+2A8h+var_268], rax
0x18001b281  test    rax, rax
0x18001b284  jz      short loc_18001B290
0x18001b286  mov     rcx, rax; this
0x18001b289  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18001b28e  jmp     short loc_18001B293
0x18001b290  mov     rax, r15
0x18001b293  cmp     [rsi+18h], rax
0x18001b297  jz      loc_18001B0DC
0x18001b29d  mov     rdx, rax; struct IUnknown *
0x18001b2a0  lea     rcx, [rsi+18h]; struct IUnknown **
0x18001b2a4  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001b2a9  jmp     loc_18001B0DC
0x18001b2ae  mov     rax, [rbx]
0x18001b2b1  mov     rcx, rbx
0x18001b2b4  mov     rax, [rax+10h]
0x18001b2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2bd  nop
0x18001b2be  mov     eax, 8007000Eh
0x18001b2c3  jmp     loc_18001B00B
0x18001b2c8  mov     rax, r15
0x18001b2cb  mov     [rsi+10h], rax
0x18001b2cf  test    dil, 1
0x18001b2d3  jz      short loc_18001B2DF
0x18001b2d5  lea     rcx, [rsp+2A8h+var_268]
0x18001b2da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001b2df  mov     rcx, [rsi+10h]
0x18001b2e3  test    rcx, rcx
0x18001b2e6  jnz     short loc_18001B302
0x18001b2e8  mov     rax, [rbx]
0x18001b2eb  mov     rcx, rbx
0x18001b2ee  mov     rax, [rax+10h]
0x18001b2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2f7  nop
0x18001b2f8  mov     eax, 8007000Eh
0x18001b2fd  jmp     loc_18001B00B
0x18001b302  mov     edx, 10006h
0x18001b307  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x18001b30c  mov     edi, eax
0x18001b30e  test    eax, eax
0x18001b310  jns     loc_18001B0C5
0x18001b316  mov     rcx, [rbx]
0x18001b319  mov     rax, [rcx+10h]
0x18001b31d  mov     rcx, rbx
0x18001b320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b325  nop
0x18001b326  mov     eax, edi
0x18001b328  jmp     loc_18001B00B
```
