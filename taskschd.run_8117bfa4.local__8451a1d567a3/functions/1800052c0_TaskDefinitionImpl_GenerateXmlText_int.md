# TaskDefinitionImpl::GenerateXmlText(int)

- ea: `0x1800052c0`
- end: `0x18000591c`
- name: `?GenerateXmlText@TaskDefinitionImpl@@AEAAJH@Z`
- size: `1628`
- prototype: `__int64 __fastcall(TaskDefinitionImpl *__hidden this, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180004800`
- `0x18000e4f0`

## callees

- `0x180001880`
- `0x1800025b0`
- `0x180002db0`
- `0x180003f7c`
- `0x180004ee0`
- `0x1800052c0`
- `0x180005924`
- `0x180005c50`
- `0x180012e60`
- `0x180014df0`
- `0x180033528`
- `0x180034628`
- `0x180036bd8`
- `0x180037cf0`
- `0x18003e88c`
- `0x18004eac4`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `msvcrt!malloc` at `0x180005324`
- `msvcrt!malloc` at `0x180005324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005708`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005708`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000530e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000530e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000566d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000566d`
- `OLEAUT32!__imp_SysStringLen` at `0x180005842`
- `OLEAUT32!__imp_SysStringLen` at `0x180005842`

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
    v26 = &qword_18007B2F0;
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
0x1800052c0  mov     [rsp+arg_10], rbx
0x1800052c5  mov     [rsp+arg_18], rsi
0x1800052ca  push    rdi
0x1800052cb  push    r12
0x1800052cd  push    r13
0x1800052cf  push    r14
0x1800052d1  push    r15
0x1800052d3  sub     rsp, 140h
0x1800052da  mov     rax, cs:__security_cookie
0x1800052e1  xor     rax, rsp
0x1800052e4  mov     [rsp+168h+var_38], rax
0x1800052ec  mov     r12d, edx
0x1800052ef  mov     r14, rcx
0x1800052f2  xor     r13d, r13d
0x1800052f5  mov     [rsp+168h+var_138], r13d
0x1800052fa  lea     rdi, [rcx+10h]
0x1800052fe  test    rcx, rcx
0x180005301  cmovz   rdi, r13
0x180005305  test    rdi, rdi
0x180005308  jz      short loc_18000531A
0x18000530a  lea     rcx, [rdi+8]; lpCriticalSection
0x18000530e  call    cs:__imp_EnterCriticalSection
0x180005315  nop     dword ptr [rax+rax+00h]
0x18000531a  mov     [rsp+168h+var_128], rdi
0x18000531f  mov     ecx, 28h ; '('; Size
0x180005324  call    cs:__imp_malloc
0x18000532b  nop     dword ptr [rax+rax+00h]
0x180005330  test    rax, rax
0x180005333  jz      loc_18000571C
0x180005339  mov     [rsp+168h+var_130], rax
0x18000533e  mov     rcx, rax; this
0x180005341  call    ??0CBstrWriter@@QEAA@XZ; CBstrWriter::CBstrWriter(void)
0x180005346  mov     rbx, rax
0x180005349  mov     [rsp+168h+var_130], rax
0x18000534e  test    rax, rax
0x180005351  jz      short loc_180005363
0x180005353  mov     rax, [rax]
0x180005356  mov     rcx, rbx
0x180005359  mov     rax, [rax+8]
0x18000535d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005362  nop
0x180005363  test    rbx, rbx
0x180005366  jz      loc_1800055E9
0x18000536c  mov     [rsp+168h+var_134], 10006h
0x180005374  mov     rsi, [r14+50h]
0x180005378  mov     [rsp+168h+var_E0], rsi
0x180005380  test    rsi, rsi
0x180005383  jz      short loc_180005395
0x180005385  mov     rax, [rsi]
0x180005388  mov     rcx, rsi
0x18000538b  mov     rax, [rax+8]
0x18000538f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005394  nop
0x180005395  cmp     qword ptr [r14+50h], 0
0x18000539a  jz      short def_180005622; jumptable 0000000180005622 default case, case 3
0x18000539c  mov     [rsp+168h+var_120], r13d
0x1800053a1  mov     rax, [rsi]
0x1800053a4  lea     rdx, [rsp+168h+var_120]
0x1800053a9  mov     rcx, rsi
0x1800053ac  mov     rax, [rax+118h]
0x1800053b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b8  mov     r15d, eax
0x1800053bb  mov     [rsp+168h+var_138], eax
0x1800053bf  test    eax, eax
0x1800053c1  js      loc_1800056DF
0x1800053c7  movsxd  rax, [rsp+168h+var_120]
0x1800053cc  cmp     eax, 3
0x1800053cf  jnz     loc_180005608
0x1800053d5  mov     [rsp+168h+var_134], 10003h
0x1800053dd  test    rsi, rsi; jumptable 0000000180005622 default case, case 3
0x1800053e0  jz      short loc_1800053F2
0x1800053e2  mov     rax, [rsi]
0x1800053e5  mov     rcx, rsi
0x1800053e8  mov     rax, [rax+10h]
0x1800053ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f1  nop
0x1800053f2  test    rbx, rbx
0x1800053f5  jz      short loc_180005407
0x1800053f7  mov     rax, [rbx]
0x1800053fa  mov     rcx, rbx
0x1800053fd  mov     rax, [rax+8]
0x180005401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005406  nop
0x180005407  mov     eax, [rsp+168h+var_134]
0x18000540b  mov     dword ptr [rsp+168h+var_D8], eax
0x180005412  mov     [rsp+168h+var_D0], rbx
0x18000541a  lea     rcx, [rsp+168h+var_D0]
0x180005422  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXmlReader@@$1?_GUID_7279fc81_709d_4095_b63d_69fe4b0d9030@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::_AddRef(void)
0x180005427  mov     [rsp+168h+var_C8], r13
0x18000542f  mov     [rsp+168h+var_40], r13d
0x180005437  test    rbx, rbx
0x18000543a  jz      short loc_18000544C
0x18000543c  mov     rax, [rbx]
0x18000543f  mov     rcx, rbx
0x180005442  mov     rax, [rax+10h]
0x180005446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000544b  nop
0x18000544c  mov     edx, [rsp+168h+var_134]
0x180005450  lea     rcx, [rsp+168h+var_D8]
0x180005458  call    ?StartDocument@TaskXmlWriter@@QEAAJW4Version@Schema@@@Z; TaskXmlWriter::StartDocument(Schema::Version)
0x18000545d  mov     esi, eax
0x18000545f  mov     [rsp+168h+var_138], eax
0x180005463  test    eax, eax
0x180005465  jns     short loc_1800054E4
0x180005467  mov     rcx, [rsp+168h+var_C8]
0x18000546f  test    rcx, rcx
0x180005472  jz      short loc_180005481
0x180005474  mov     rdx, [rcx]
0x180005477  mov     rax, [rdx+10h]
0x18000547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005480  nop
0x180005481  lea     rcx, [rsp+168h+var_D0]
0x180005489  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000548e  nop
0x18000548f  mov     rax, [rbx]
0x180005492  mov     rcx, rbx
0x180005495  mov     rax, [rax+10h]
0x180005499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000549e  nop
0x18000549f  test    rdi, rdi
0x1800054a2  jz      short loc_1800054B4
0x1800054a4  lea     rcx, [rdi+8]; lpCriticalSection
0x1800054a8  call    cs:__imp_LeaveCriticalSection
0x1800054af  nop     dword ptr [rax+rax+00h]
0x1800054b4  mov     eax, esi
0x1800054b6  mov     rcx, [rsp+168h+var_38]
0x1800054be  xor     rcx, rsp; StackCookie
0x1800054c1  call    __security_check_cookie
0x1800054c6  lea     r11, [rsp+168h+var_28]
0x1800054ce  mov     rbx, [r11+40h]
0x1800054d2  mov     rsi, [r11+48h]
0x1800054d6  mov     rsp, r11
0x1800054d9  pop     r15
0x1800054db  pop     r14
0x1800054dd  pop     r13
0x1800054df  pop     r12
0x1800054e1  pop     rdi
0x1800054e2  retn
0x1800054e4  mov     r8d, r12d; int
0x1800054e7  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x1800054ef  mov     rcx, r14; this
0x1800054f2  call    ?WritePropIdentificationXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z; TaskDefinitionImpl::WritePropIdentificationXml(TaskXmlWriter &,int)
0x1800054f7  mov     esi, eax
0x1800054f9  mov     [rsp+168h+var_138], eax
0x1800054fd  test    eax, eax
0x1800054ff  js      loc_18000579A
0x180005505  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x18000550d  mov     rcx, r14; this
0x180005510  call    ?WriteTriggersXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@@Z; TaskDefinitionImpl::WriteTriggersXml(TaskXmlWriter &)
0x180005515  mov     esi, eax
0x180005517  mov     [rsp+168h+var_138], eax
0x18000551b  test    eax, eax
0x18000551d  js      loc_1800057C4
0x180005523  mov     r9d, r12d; int
0x180005526  lea     r8, [rsp+168h+var_134]; struct Schema *
0x18000552b  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x180005533  mov     rcx, r14; this
0x180005536  call    ?WritePrincipalXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@AEBUSchema@@H@Z; TaskDefinitionImpl::WritePrincipalXml(TaskXmlWriter &,Schema const &,int)
0x18000553b  mov     esi, eax
0x18000553d  mov     [rsp+168h+var_138], eax
0x180005541  test    eax, eax
0x180005543  js      loc_1800057EE
0x180005549  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x180005551  mov     rcx, r14; this
0x180005554  call    ?WriteJobSettingsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@@Z; TaskDefinitionImpl::WriteJobSettingsXml(TaskXmlWriter &)
0x180005559  mov     esi, eax
0x18000555b  mov     [rsp+168h+var_138], eax
0x18000555f  test    eax, eax
0x180005561  js      loc_180005818
0x180005567  mov     rcx, [r14+78h]; pbstr
0x18000556b  test    rcx, rcx
0x18000556e  jnz     loc_180005842
0x180005574  mov     r8d, r12d; int
0x180005577  lea     rdx, [rsp+168h+var_D8]; struct TaskXmlWriter *
0x18000557f  mov     rcx, r14; this
0x180005582  call    ?WriteActionsXml@TaskDefinitionImpl@@AEAAJAEAVTaskXmlWriter@@H@Z; TaskDefinitionImpl::WriteActionsXml(TaskXmlWriter &,int)
0x180005587  mov     esi, eax
0x180005589  mov     [rsp+168h+var_138], eax
0x18000558d  test    eax, eax
0x18000558f  jns     loc_180005635
0x180005595  mov     rcx, [rsp+168h+var_C8]
0x18000559d  test    rcx, rcx
0x1800055a0  jz      short loc_1800055AF
0x1800055a2  mov     rdx, [rcx]
0x1800055a5  mov     rax, [rdx+10h]
0x1800055a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ae  nop
0x1800055af  lea     rcx, [rsp+168h+var_D0]
0x1800055b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800055bc  nop
0x1800055bd  mov     rax, [rbx]
0x1800055c0  mov     rcx, rbx
0x1800055c3  mov     rax, [rax+10h]
0x1800055c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055cc  nop
0x1800055cd  test    rdi, rdi
0x1800055d0  jz      short loc_1800055E2
0x1800055d2  lea     rcx, [rdi+8]; lpCriticalSection
0x1800055d6  call    cs:__imp_LeaveCriticalSection
0x1800055dd  nop     dword ptr [rax+rax+00h]
0x1800055e2  mov     eax, esi
0x1800055e4  jmp     loc_1800054B6
0x1800055e9  test    rdi, rdi
0x1800055ec  jz      short loc_1800055FE
0x1800055ee  lea     rcx, [rdi+8]; lpCriticalSection
0x1800055f2  call    cs:__imp_LeaveCriticalSection
0x1800055f9  nop     dword ptr [rax+rax+00h]
0x1800055fe  mov     eax, 8007000Eh
0x180005603  jmp     loc_1800054B6
0x180005608  cmp     eax, 6; switch 7 cases
0x18000560b  ja      def_180005622; jumptable 0000000180005622 default case, case 3
0x180005611  lea     rdx, __ImageBase
0x180005618  mov     ecx, ds:(jpt_180005622 - 180000000h)[rdx+rax*4]
0x18000561f  add     rcx, rdx
0x180005622  jmp     rcx; switch jump
0x180005628  mov     [rsp+168h+var_134], 10002h; jumptable 0000000180005622 case 2
0x180005630  jmp     def_180005622; jumptable 0000000180005622 default case, case 3
0x180005635  lea     rcx, [rsp+168h+var_D8]; this
0x18000563d  call    ?EndDocument@TaskXmlWriter@@QEAAJXZ; TaskXmlWriter::EndDocument(void)
0x180005642  mov     esi, eax
0x180005644  mov     [rsp+168h+var_138], eax
0x180005648  test    eax, eax
0x18000564a  js      loc_18000589F
0x180005650  mov     rcx, rbx; this
0x180005653  call    ?GetCopy@CBstrWriter@@QEAAPEAGXZ; CBstrWriter::GetCopy(void)
0x180005658  mov     r15, rax
0x18000565b  test    rax, rax
0x18000565e  jz      loc_1800058C9
0x180005664  mov     rcx, [r14+70h]; bstrString
0x180005668  cmp     rcx, rax
0x18000566b  jz      short loc_18000567D
0x18000566d  call    cs:__imp_SysFreeString
0x180005674  nop     dword ptr [rax+rax+00h]
0x180005679  mov     [r14+70h], r15
0x18000567d  mov     rcx, [rsp+168h+var_C8]
0x180005685  test    rcx, rcx
0x180005688  jz      short loc_180005697
0x18000568a  mov     rax, [rcx]
0x18000568d  mov     rax, [rax+10h]
0x180005691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005696  nop
0x180005697  lea     rcx, [rsp+168h+var_D0]
0x18000569f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800056a4  nop
0x1800056a5  mov     rax, [rbx]
0x1800056a8  mov     rcx, rbx
0x1800056ab  mov     rax, [rax+10h]
0x1800056af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b4  nop
0x1800056b5  test    rdi, rdi
0x1800056b8  jz      short loc_1800056CB
0x1800056ba  lea     rcx, [rdi+8]; lpCriticalSection
0x1800056be  call    cs:__imp_LeaveCriticalSection
0x1800056c5  nop     dword ptr [rax+rax+00h]
0x1800056ca  nop
0x1800056cb  mov     eax, esi
0x1800056cd  jmp     loc_1800054B6
0x1800056d2  mov     [rsp+168h+var_134], 10004h; jumptable 0000000180005622 case 4
0x1800056da  jmp     def_180005622; jumptable 0000000180005622 default case, case 3
0x1800056df  mov     rcx, [rsi]
0x1800056e2  mov     rax, [rcx+10h]
0x1800056e6  mov     rcx, rsi
0x1800056e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ee  nop
0x1800056ef  mov     rax, [rbx]
0x1800056f2  mov     rcx, rbx
0x1800056f5  mov     rax, [rax+10h]
0x1800056f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056fe  nop
0x1800056ff  test    rdi, rdi
0x180005702  jz      short loc_180005714
0x180005704  lea     rcx, [rdi+8]; lpCriticalSection
0x180005708  call    cs:__imp_LeaveCriticalSection
0x18000570f  nop     dword ptr [rax+rax+00h]
0x180005714  mov     eax, r15d
0x180005717  jmp     loc_1800054B6
0x18000571c  mov     [rsp+168h+var_110], 0
0x180005721  lea     rax, qword_18007B2F0
0x180005728  mov     [rsp+168h+var_108], rax
0x18000572d  mov     [rsp+168h+var_100], r13
0x180005732  mov     [rsp+168h+var_F8], r13
0x180005737  mov     [rsp+168h+var_F0], 0Eh
0x18000573f  mov     [rsp+168h+var_EC], 0FFFFFFFFFFFFFFFFh
0x180005748  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000574f  mov     [rsp+168h+pExceptionObject], rax
0x180005754  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000575b  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x180005760  call    _CxxThrowException_0
0x180005766  mov     [rsp+168h+var_134], 10000h; jumptable 0000000180005622 case 0
0x18000576e  jmp     def_180005622; jumptable 0000000180005622 default case, case 3
0x180005773  mov     [rsp+168h+var_134], 10001h; jumptable 0000000180005622 case 1
0x18000577b  jmp     def_180005622; jumptable 0000000180005622 default case, case 3
0x180005780  mov     [rsp+168h+var_134], 10005h; jumptable 0000000180005622 case 5
0x180005788  jmp     def_180005622; jumptable 0000000180005622 default case, case 3
0x18000578d  mov     [rsp+168h+var_134], 10006h; jumptable 0000000180005622 case 6
0x180005795  jmp     def_180005622; jumptable 0000000180005622 default case, case 3
0x18000579a  lea     rcx, [rsp+168h+var_D8]; this
0x1800057a2  call    ??1TaskXmlWriter@@QEAA@XZ; TaskXmlWriter::~TaskXmlWriter(void)
0x1800057a7  nop
0x1800057a8  lea     rcx, [rsp+168h+var_130]
  ... truncated ...
```
