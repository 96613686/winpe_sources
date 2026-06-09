# TaskDefinitionImpl::GenerateXmlText(int)

- ea: `0x180004fd0`
- end: `0x1800055f0`
- name: `?GenerateXmlText@TaskDefinitionImpl@@AEAAJH@Z`
- size: `1568`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180004570`
- `0x18000e4d0`

## callees

- `0x1800017f0`
- `0x1800024e0`
- `0x180002c10`
- `0x180003d68`
- `0x180004c00`
- `0x180004fd0`
- `0x1800055f8`
- `0x180005990`
- `0x180012380`
- `0x180013820`
- `0x180013f20`
- `0x180030b54`
- `0x180033e58`
- `0x1800351ec`
- `0x18003b51c`
- `0x18004aee4`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `msvcrt!malloc` at `0x18000502e`
- `msvcrt!malloc` at `0x18000502e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800052e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000501e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000501e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000535a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000535a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000551d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000551d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall TaskDefinitionImpl::GenerateXmlText(TaskDefinitionImpl *this, int a2)
{
  char *v4; // rdi
  CBstrWriter *v5; // rax
  CBstrWriter *v6; // rax
  CBstrWriter *v7; // rbx
  __int64 v8; // rsi
  int v9; // r15d
  HRESULT started; // esi
  int v12; // esi
  int v13; // esi
  OLECHAR *v14; // rcx
  int v15; // esi
  unsigned __int16 *Copy; // rax
  unsigned __int16 *v17; // r15
  OLECHAR *v18; // rcx
  __int64 v19; // rdx
  int v20; // [rsp+34h] [rbp-134h] BYREF
  CBstrWriter *v21; // [rsp+38h] [rbp-130h] BYREF
  char *v22; // [rsp+40h] [rbp-128h] BYREF
  int v23; // [rsp+48h] [rbp-120h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-118h] BYREF
  char v25; // [rsp+58h] [rbp-110h]
  __int64 *v26; // [rsp+60h] [rbp-108h]
  __int64 v27; // [rsp+68h] [rbp-100h]
  __int64 v28; // [rsp+70h] [rbp-F8h]
  int v29; // [rsp+78h] [rbp-F0h]
  __int64 v30; // [rsp+7Ch] [rbp-ECh]
  __int64 v31; // [rsp+88h] [rbp-E0h]
  struct IErrorInfo v32; // [rsp+90h] [rbp-D8h] BYREF
  CBstrWriter *v33; // [rsp+98h] [rbp-D0h] BYREF
  _QWORD *v34; // [rsp+A0h] [rbp-C8h]
  int v35; // [rsp+128h] [rbp-40h]

  v4 = (char *)this + 16;
  if ( !this )
    v4 = 0;
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v22 = v4;
  v5 = (CBstrWriter *)malloc(0x28u);
  if ( !v5 )
  {
    v25 = 0;
    v26 = &qword_180077320;
    v27 = 0;
    v28 = 0;
    v29 = 14;
    v30 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v6 = CBstrWriter::CBstrWriter(v5);
  v7 = v6;
  v21 = v6;
  if ( v6 )
    (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v7 )
  {
    v20 = 65542;
    v8 = *((_QWORD *)this + 10);
    v31 = v8;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    if ( *((_QWORD *)this + 10) )
    {
      v23 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 280LL))(v8, &v23);
      if ( v9 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v7 + 16LL))(v7);
        if ( v4 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
        return (unsigned int)v9;
      }
      if ( v23 == 3 )
      {
        v20 = 65539;
      }
      else
      {
        switch ( v23 )
        {
          case 0:
            v20 = 0x10000;
            break;
          case 1:
            v20 = 65537;
            break;
          case 2:
            v20 = 65538;
            break;
          case 4:
            v20 = 65540;
            break;
          case 5:
            v20 = 65541;
            break;
          case 6:
            v20 = 65542;
            break;
          default:
            break;
        }
      }
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v7 + 8LL))(v7);
    LODWORD(v32.lpVtbl) = v20;
    v33 = v7;
    _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(&v33);
    v34 = 0;
    v35 = 0;
    (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v7 + 16LL))(v7);
    started = TaskXmlWriter::StartDocument((int *)&v32, v20);
    if ( started < 0 )
    {
      if ( v34 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v34 + 16LL))(v34, *v34);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v4 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
      return (unsigned int)started;
    }
    v12 = TaskDefinitionImpl::WritePropIdentificationXml(this, (struct TaskXmlWriter *)&v32, a2);
    if ( v12 < 0 || (v12 = TaskDefinitionImpl::WriteTriggersXml(this, (struct TaskXmlWriter *)&v32), v12 < 0) )
    {
      TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)&v32);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
      ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v22);
      return (unsigned int)v12;
    }
    v13 = TaskDefinitionImpl::WritePrincipalXml(this, (struct TaskXmlWriter *)&v32, (const struct Schema *)&v20, a2);
    if ( v13 < 0
      || (v13 = TaskDefinitionImpl::WriteJobSettingsXml(this, &v32), v13 < 0)
      || (v14 = (OLECHAR *)*((_QWORD *)this + 15)) != 0
      && SysStringLen(v14)
      && (v13 = TaskXmlWriter::ElementCData(&v32, v19, *((_QWORD *)this + 15)), v13 < 0) )
    {
LABEL_60:
      TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)&v32);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
      ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v22);
      return (unsigned int)v13;
    }
    v15 = TaskDefinitionImpl::WriteActionsXml(this, (struct TaskXmlWriter *)&v32, a2);
    if ( v15 >= 0 )
    {
      v13 = TaskXmlWriter::EndDocument((TaskXmlWriter *)&v32);
      if ( v13 < 0 )
        goto LABEL_60;
      Copy = CBstrWriter::GetCopy(v7);
      v17 = Copy;
      if ( Copy )
      {
        v18 = (OLECHAR *)*((_QWORD *)this + 14);
        if ( v18 != Copy )
        {
          SysFreeString(v18);
          *((_QWORD *)this + 14) = v17;
        }
        if ( v34 )
          (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
        (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v7 + 16LL))(v7);
        if ( v4 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
        return (unsigned int)v13;
      }
      else
      {
        TaskXmlWriter::~TaskXmlWriter((TaskXmlWriter *)&v32);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
        ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v22);
        return 2147942414LL;
      }
    }
    else
    {
      if ( v34 )
        (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      (*(void (__fastcall **)(CBstrWriter *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v4 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
      return (unsigned int)v15;
    }
  }
  else
  {
    if ( v4 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180004fd0  mov     [rsp+arg_10], rbx
0x180004fd5  mov     [rsp+arg_18], rsi
0x180004fda  push    rdi
0x180004fdb  push    r12
0x180004fdd  push    r13
0x180004fdf  push    r14
0x180004fe1  push    r15
0x180004fe3  sub     rsp, 140h
0x180004fea  mov     rax, cs:__security_cookie
0x180004ff1  xor     rax, rsp
0x180004ff4  mov     [rsp+168h+var_38], rax
0x180004ffc  mov     r12d, edx
0x180004fff  mov     r14, rcx
0x180005002  xor     r13d, r13d
0x180005005  mov     [rsp+168h+var_138], r13d
0x18000500a  lea     rdi, [rcx+10h]
0x18000500e  test    rcx, rcx
0x180005011  cmovz   rdi, r13
0x180005015  test    rdi, rdi
0x180005018  jz      short loc_180005024
0x18000501a  lea     rcx, [rdi+8]; lpCriticalSection
0x18000501e  call    cs:__imp_EnterCriticalSection
0x180005024  mov     [rsp+168h+var_128], rdi
0x180005029  mov     ecx, 28h ; '('; Size
0x18000502e  call    cs:__imp_malloc
0x180005034  test    rax, rax
0x180005037  jz      loc_1800053F7
0x18000503d  mov     [rsp+168h+var_130], rax
0x180005042  mov     rcx, rax; this
0x180005045  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x18000504a  mov     rbx, rax
0x18000504d  mov     [rsp+168h+var_130], rax
0x180005052  test    rax, rax
0x180005055  jz      short loc_180005067
0x180005057  mov     rax, [rax]
0x18000505a  mov     rcx, rbx
0x18000505d  mov     rax, [rax+8]
0x180005061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005066  nop
0x180005067  test    rbx, rbx
0x18000506a  jz      loc_1800052E0
0x180005070  mov     [rsp+168h+var_134], 10006h
0x180005078  mov     rsi, [r14+50h]
0x18000507c  mov     [rsp+168h+var_E0], rsi
0x180005084  test    rsi, rsi
0x180005087  jz      short loc_180005099
0x180005089  mov     rax, [rsi]
0x18000508c  mov     rcx, rsi
0x18000508f  mov     rax, [rax+8]
0x180005093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005098  nop
0x180005099  cmp     qword ptr [r14+50h], 0
0x18000509e  jz      short def_180005313; jumptable 0000000180005313 default case, case 3
0x1800050a0  mov     [rsp+168h+var_120], r13d
0x1800050a5  mov     rax, [rsi]
0x1800050a8  lea     rdx, [rsp+168h+var_120]
0x1800050ad  mov     rcx, rsi
0x1800050b0  mov     rax, [rax+118h]
0x1800050b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050bc  mov     r15d, eax
0x1800050bf  mov     [rsp+168h+var_138], eax
0x1800050c3  test    eax, eax
0x1800050c5  js      loc_1800053C0
0x1800050cb  movsxd  rax, [rsp+168h+var_120]
0x1800050d0  cmp     eax, 3
0x1800050d3  jnz     loc_1800052F9
0x1800050d9  mov     [rsp+168h+var_134], 10003h
0x1800050e1  test    rsi, rsi; jumptable 0000000180005313 default case, case 3
0x1800050e4  jz      short loc_1800050F6
0x1800050e6  mov     rax, [rsi]
0x1800050e9  mov     rcx, rsi
0x1800050ec  mov     rax, [rax+10h]
0x1800050f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050f5  nop
0x1800050f6  test    rbx, rbx
0x1800050f9  jz      short loc_18000510B
0x1800050fb  mov     rax, [rbx]
0x1800050fe  mov     rcx, rbx
0x180005101  mov     rax, [rax+8]
0x180005105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510a  nop
0x18000510b  mov     eax, [rsp+168h+var_134]
0x18000510f  mov     dword ptr [rsp+168h+var_D8], eax
0x180005116  mov     [rsp+168h+var_D0], rbx
0x18000511e  lea     rcx, [rsp+168h+var_D0]
0x180005126  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x18000512b  mov     [rsp+168h+var_C8], r13
0x180005133  mov     [rsp+168h+var_40], r13d
0x18000513b  test    rbx, rbx
0x18000513e  jz      short loc_180005150
0x180005140  mov     rax, [rbx]
0x180005143  mov     rcx, rbx
0x180005146  mov     rax, [rax+10h]
0x18000514a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514f  nop
0x180005150  mov     edx, [rsp+168h+var_134]
0x180005154  lea     rcx, [rsp+168h+var_D8]
0x18000515c  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x180005161  mov     esi, eax
0x180005163  mov     [rsp+168h+var_138], eax
0x180005167  test    eax, eax
0x180005169  jns     short loc_1800051E1
0x18000516b  mov     rcx, [rsp+168h+var_C8]
0x180005173  test    rcx, rcx
0x180005176  jz      short loc_180005185
0x180005178  mov     rdx, [rcx]
0x18000517b  mov     rax, [rdx+10h]
0x18000517f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005184  nop
0x180005185  lea     rcx, [rsp+168h+var_D0]
0x18000518d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005192  nop
0x180005193  mov     rax, [rbx]
0x180005196  mov     rcx, rbx
0x180005199  mov     rax, [rax+10h]
0x18000519d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a2  nop
0x1800051a3  test    rdi, rdi
0x1800051a6  jz      short loc_1800051B2
0x1800051a8  lea     rcx, [rdi+8]; lpCriticalSection
0x1800051ac  call    cs:__imp_LeaveCriticalSection
0x1800051b2  mov     eax, esi
0x1800051b4  mov     rcx, [rsp+168h+var_38]
0x1800051bc  xor     rcx, rsp; StackCookie
0x1800051bf  call    __security_check_cookie
0x1800051c4  lea     r11, [rsp+168h+var_28]
0x1800051cc  mov     rbx, [r11+40h]
0x1800051d0  mov     rsi, [r11+48h]
0x1800051d4  mov     rsp, r11
0x1800051d7  pop     r15
0x1800051d9  pop     r14
0x1800051db  pop     r13
0x1800051dd  pop     r12
0x1800051df  pop     rdi
0x1800051e0  retn
0x1800051e1  mov     r8d, r12d; int
0x1800051e4  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x1800051ec  mov     rcx, r14; this
0x1800051ef  call    ?WritePropIdentificationXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z; TaskDefinitionImpl::WritePropIdentificationXml(TaskXmlWriter &,int)
0x1800051f4  mov     esi, eax
0x1800051f6  mov     [rsp+168h+var_138], eax
0x1800051fa  test    eax, eax
0x1800051fc  js      loc_180005475
0x180005202  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x18000520a  mov     rcx, r14; this
0x18000520d  call    ?WriteTriggersXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@@Z; TaskDefinitionImpl::WriteTriggersXml(TaskXmlWriter &)
0x180005212  mov     esi, eax
0x180005214  mov     [rsp+168h+var_138], eax
0x180005218  test    eax, eax
0x18000521a  js      loc_18000549F
0x180005220  mov     r9d, r12d; int
0x180005223  lea     r8, [rsp+168h+var_134]; struct Schema *
0x180005228  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x180005230  mov     rcx, r14; this
0x180005233  call    ?WritePrincipalXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@AEBUSchema@@H@Z; TaskDefinitionImpl::WritePrincipalXml(TaskXmlWriter &,Schema const &,int)
0x180005238  mov     esi, eax
0x18000523a  mov     [rsp+168h+var_138], eax
0x18000523e  test    eax, eax
0x180005240  js      loc_1800054C9
0x180005246  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x18000524e  mov     rcx, r14; this
0x180005251  call    ?WriteJobSettingsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@@Z; TaskDefinitionImpl::WriteJobSettingsXml(TaskXmlWriter &)
0x180005256  mov     esi, eax
0x180005258  mov     [rsp+168h+var_138], eax
0x18000525c  test    eax, eax
0x18000525e  js      loc_1800054F3
0x180005264  mov     rcx, [r14+78h]; pbstr
0x180005268  test    rcx, rcx
0x18000526b  jnz     loc_18000551D
0x180005271  mov     r8d, r12d; int
0x180005274  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x18000527c  mov     rcx, r14; this
0x18000527f  call    ?WriteActionsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z; TaskDefinitionImpl::WriteActionsXml(TaskXmlWriter &,int)
0x180005284  mov     esi, eax
0x180005286  mov     [rsp+168h+var_138], eax
0x18000528a  test    eax, eax
0x18000528c  jns     loc_180005322
0x180005292  mov     rcx, [rsp+168h+var_C8]
0x18000529a  test    rcx, rcx
0x18000529d  jz      short loc_1800052AC
0x18000529f  mov     rdx, [rcx]
0x1800052a2  mov     rax, [rdx+10h]
0x1800052a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ab  nop
0x1800052ac  lea     rcx, [rsp+168h+var_D0]
0x1800052b4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800052b9  nop
0x1800052ba  mov     rax, [rbx]
0x1800052bd  mov     rcx, rbx
0x1800052c0  mov     rax, [rax+10h]
0x1800052c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c9  nop
0x1800052ca  test    rdi, rdi
0x1800052cd  jz      short loc_1800052D9
0x1800052cf  lea     rcx, [rdi+8]; lpCriticalSection
0x1800052d3  call    cs:__imp_LeaveCriticalSection
0x1800052d9  mov     eax, esi
0x1800052db  jmp     loc_1800051B4
0x1800052e0  test    rdi, rdi
0x1800052e3  jz      short loc_1800052EF
0x1800052e5  lea     rcx, [rdi+8]; lpCriticalSection
0x1800052e9  call    cs:__imp_LeaveCriticalSection
0x1800052ef  mov     eax, 8007000Eh
0x1800052f4  jmp     loc_1800051B4
0x1800052f9  cmp     eax, 6; switch 7 cases
0x1800052fc  ja      def_180005313; jumptable 0000000180005313 default case, case 3
0x180005302  lea     rdx, __ImageBase
0x180005309  mov     ecx, ds:(jpt_180005313 - 180000000h)[rdx+rax*4]
0x180005310  add     rcx, rdx
0x180005313  jmp     rcx; switch jump
0x180005315  mov     [rsp+168h+var_134], 10002h; jumptable 0000000180005313 case 2
0x18000531d  jmp     def_180005313; jumptable 0000000180005313 default case, case 3
0x180005322  lea     rcx, [rsp+168h+var_D8]; this
0x18000532a  call    ?EndDocument@TaskXmlWriter@@QEAAJXZ; TaskXmlWriter::EndDocument(void)
0x18000532f  mov     esi, eax
0x180005331  mov     [rsp+168h+var_138], eax
0x180005335  test    eax, eax
0x180005337  js      loc_180005574
0x18000533d  mov     rcx, rbx; this
0x180005340  call    ?GetCopy@CBstrWriter@@QEAAPEAGXZ; CBstrWriter::GetCopy(void)
0x180005345  mov     r15, rax
0x180005348  test    rax, rax
0x18000534b  jz      loc_18000559E
0x180005351  mov     rcx, [r14+70h]; bstrString
0x180005355  cmp     rcx, rax
0x180005358  jz      short loc_180005364
0x18000535a  call    cs:__imp_SysFreeString
0x180005360  mov     [r14+70h], r15
0x180005364  mov     rcx, [rsp+168h+var_C8]
0x18000536c  test    rcx, rcx
0x18000536f  jz      short loc_18000537E
0x180005371  mov     rax, [rcx]
0x180005374  mov     rax, [rax+10h]
0x180005378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000537d  nop
0x18000537e  lea     rcx, [rsp+168h+var_D0]
0x180005386  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000538b  nop
0x18000538c  mov     rax, [rbx]
0x18000538f  mov     rcx, rbx
0x180005392  mov     rax, [rax+10h]
0x180005396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539b  nop
0x18000539c  test    rdi, rdi
0x18000539f  jz      short loc_1800053AC
0x1800053a1  lea     rcx, [rdi+8]; lpCriticalSection
0x1800053a5  call    cs:__imp_LeaveCriticalSection
0x1800053ab  nop
0x1800053ac  mov     eax, esi
0x1800053ae  jmp     loc_1800051B4
0x1800053b3  mov     [rsp+168h+var_134], 10004h; jumptable 0000000180005313 case 4
0x1800053bb  jmp     def_180005313; jumptable 0000000180005313 default case, case 3
0x1800053c0  mov     rcx, [rsi]
0x1800053c3  mov     rax, [rcx+10h]
0x1800053c7  mov     rcx, rsi
0x1800053ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cf  nop
0x1800053d0  mov     rax, [rbx]
0x1800053d3  mov     rcx, rbx
0x1800053d6  mov     rax, [rax+10h]
0x1800053da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053df  nop
0x1800053e0  test    rdi, rdi
0x1800053e3  jz      short loc_1800053EF
0x1800053e5  lea     rcx, [rdi+8]; lpCriticalSection
0x1800053e9  call    cs:__imp_LeaveCriticalSection
0x1800053ef  mov     eax, r15d
0x1800053f2  jmp     loc_1800051B4
0x1800053f7  mov     [rsp+168h+var_110], 0
0x1800053fc  lea     rax, qword_180077320
0x180005403  mov     [rsp+168h+var_108], rax
0x180005408  mov     [rsp+168h+var_100], r13
0x18000540d  mov     [rsp+168h+var_F8], r13
0x180005412  mov     [rsp+168h+var_F0], 0Eh
0x18000541a  mov     [rsp+168h+var_EC], 0FFFFFFFFFFFFFFFFh
0x180005423  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000542a  mov     [rsp+168h+pExceptionObject], rax
0x18000542f  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180005436  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18000543b  call    _CxxThrowException_0
0x180005441  mov     [rsp+168h+var_134], 10000h; jumptable 0000000180005313 case 0
0x180005449  jmp     def_180005313; jumptable 0000000180005313 default case, case 3
0x18000544e  mov     [rsp+168h+var_134], 10001h; jumptable 0000000180005313 case 1
0x180005456  jmp     def_180005313; jumptable 0000000180005313 default case, case 3
0x18000545b  mov     [rsp+168h+var_134], 10005h; jumptable 0000000180005313 case 5
0x180005463  jmp     def_180005313; jumptable 0000000180005313 default case, case 3
0x180005468  mov     [rsp+168h+var_134], 10006h; jumptable 0000000180005313 case 6
0x180005470  jmp     def_180005313; jumptable 0000000180005313 default case, case 3
0x180005475  lea     rcx, [rsp+168h+var_D8]; this
0x18000547d  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x180005482  nop
0x180005483  lea     rcx, [rsp+168h+var_130]
0x180005488  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000548d  nop
0x18000548e  lea     rcx, [rsp+168h+var_128]
0x180005493  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180005498  mov     eax, esi
0x18000549a  jmp     loc_1800051B4
0x18000549f  lea     rcx, [rsp+168h+var_D8]; this
0x1800054a7  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
  ... truncated ...
```
