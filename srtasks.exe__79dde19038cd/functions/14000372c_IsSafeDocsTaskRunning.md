# IsSafeDocsTaskRunning

- ea: `0x14000372c`
- end: `0x140003947`
- name: `IsSafeDocsTaskRunning`
- size: `539`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140002f30`

## callees

- `0x14000372c`
- `0x140006e40`
- `0x14000e324`
- `0x14000e41c`
- `0x140011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400037bc`
- `ole32!CoCreateInstance` at `0x1400037bc`

## string_xrefs

- `0x140003744`: `IsSafeDocsTaskRunning`

## pseudocode

```c
__int64 __fastcall IsSafeDocsTaskRunning(_DWORD *a1)
{
  struct IRegisteredTask *v2; // rdx
  __int64 v3; // r8
  struct IRegisteredTask *v4; // rbx
  HRESULT Instance; // edi
  __int16 v6; // ax
  struct ITaskServiceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rax
  int WMIBackupTask; // eax
  bool v10; // sf
  int v12; // [rsp+30h] [rbp-99h] BYREF
  __int16 v13; // [rsp+34h] [rbp-95h]
  __int16 v14; // [rsp+36h] [rbp-93h]
  _QWORD v15[4]; // [rsp+70h] [rbp-59h] BYREF
  __int16 v16; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v17[22]; // [rsp+92h] [rbp-37h]
  __int16 v18; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v19[22]; // [rsp+B2h] [rbp-17h]
  __int16 v20; // [rsp+D0h] [rbp+7h] BYREF
  _OWORD v21[4]; // [rsp+D2h] [rbp+9h]
  int v22; // [rsp+130h] [rbp+67h] BYREF
  struct ITaskService *ppv; // [rsp+138h] [rbp+6Fh] BYREF
  struct IRegisteredTask *v24; // [rsp+140h] [rbp+77h] BYREF
  __int64 v25; // [rsp+148h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "IsSafeDocsTaskRunning", 557, 1);
  v4 = 0;
  ppv = 0;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  memset((char *)v15 + 2, 0, 22);
  if ( a1 )
  {
    v13 = 565;
    *a1 = 0;
    v12 = 0;
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, (LPVOID *)&ppv);
    v12 = Instance;
    v6 = 568;
    if ( Instance < 0 )
      goto LABEL_3;
    v13 = 568;
    *(_OWORD *)v17 = *(_OWORD *)((char *)v15 + 2);
    lpVtbl = ppv->lpVtbl;
    *(_OWORD *)v19 = *(_OWORD *)((char *)v15 + 2);
    v16 = 1;
    v21[0] = *(_OWORD *)((char *)v15 + 2);
    Connect = lpVtbl->Connect;
    *(_QWORD *)&v17[14] = 0;
    v18 = 1;
    *(_QWORD *)&v19[14] = 0;
    v20 = 1;
    *(_QWORD *)((char *)v21 + 14) = 0;
    LOWORD(v15[0]) = 1;
    v15[2] = 0;
    Instance = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD *, __int16 *, __int16 *, __int16 *))Connect)(
                 ppv,
                 v15,
                 &v20,
                 &v18,
                 &v16);
    v12 = Instance;
    v6 = 569;
    if ( Instance < 0 )
      goto LABEL_3;
    v13 = 569;
    WMIBackupTask = GetWMIBackupTask(ppv, v2, &v24);
    v4 = v24;
    Instance = WMIBackupTask;
    v12 = WMIBackupTask;
    v10 = WMIBackupTask < 0;
    v6 = 572;
    if ( v10 )
      goto LABEL_3;
    v13 = 572;
    Instance = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD, __int64 *))v24->lpVtbl->GetInstances)(
                 v24,
                 0,
                 &v25);
    v12 = Instance;
    v6 = 575;
    if ( Instance < 0
      || (v13 = 575,
          Instance = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 56LL))(v25, &v22),
          v12 = Instance,
          v6 = 577,
          Instance < 0) )
    {
LABEL_3:
      v14 = v6;
    }
    else
    {
      v13 = 577;
      *a1 = v22 > 0;
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v4 )
      ((void (__fastcall *)(struct IRegisteredTask *))v4->lpVtbl->Release)(v4);
    if ( ppv )
      ((void (__fastcall *)(struct ITaskService *))ppv->lpVtbl->Release)(ppv);
  }
  else
  {
    Instance = -2147024809;
    v14 = 565;
    v12 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12, (__int64)v2, v3);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14000372c  push    rbp
0x14000372e  push    rbx
0x14000372f  push    rsi
0x140003730  push    rdi
0x140003731  push    r12
0x140003733  push    r15
0x140003735  lea     rbp, [rsp-2Fh]
0x14000373a  sub     rsp, 0F8h
0x140003741  mov     rsi, rcx
0x140003744  lea     rdx, aIssafedocstask; "IsSafeDocsTaskRunning"
0x14000374b  mov     r15d, 1
0x140003751  lea     rcx, [rsp+120h+var_F0]; this
0x140003756  mov     r9d, r15d; unsigned __int16
0x140003759  mov     r8d, 22Dh; unsigned __int16
0x14000375f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140003764  xor     ebx, ebx
0x140003766  mov     [rbp+57h+arg_8], 0
0x14000376e  xor     r12d, r12d
0x140003771  mov     [rbp+57h+arg_10], rbx
0x140003775  mov     [rbp+57h+arg_18], rbx
0x140003779  xorps   xmm0, xmm0
0x14000377c  mov     [rbp+57h+arg_0], ebx
0x14000377f  mov     eax, 235h
0x140003784  movups  xmmword ptr [rbp+57h+var_AE], xmm0
0x140003788  mov     qword ptr [rbp+57h+var_AE+0Eh], r12
0x14000378c  test    rsi, rsi
0x14000378f  jz      loc_14000391D
0x140003795  mov     [rsp+120h+var_EC], ax
0x14000379a  lea     r9, IID_ITaskService; riid
0x1400037a1  lea     rax, [rbp+57h+arg_8]
0x1400037a5  mov     [rsi], ebx
0x1400037a7  mov     r8d, r15d; dwClsContext
0x1400037aa  mov     [rsp+120h+ppv], rax; ppv
0x1400037af  xor     edx, edx; pUnkOuter
0x1400037b1  mov     [rsp+120h+var_F0], ebx
0x1400037b5  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400037bc  call    cs:__imp_CoCreateInstance
0x1400037c2  mov     edi, eax
0x1400037c4  mov     [rsp+120h+var_F0], eax
0x1400037c8  test    eax, eax
0x1400037ca  mov     eax, 238h
0x1400037cf  jns     short loc_1400037DB
0x1400037d1  mov     [rsp+120h+var_EA], ax
0x1400037d6  jmp     loc_1400038DD
0x1400037db  movups  xmm1, xmmword ptr [rbp+57h+var_AE]
0x1400037df  mov     rcx, [rbp+57h+arg_8]
0x1400037e3  lea     rdx, [rbp+57h+var_90]
0x1400037e7  mov     [rsp+120h+var_EC], ax
0x1400037ec  lea     r9, [rbp+57h+var_70]
0x1400037f0  mov     [rsp+120h+ppv], rdx
0x1400037f5  lea     r8, [rbp+57h+var_50]
0x1400037f9  movups  xmmword ptr [rbp+57h+var_8E], xmm1
0x1400037fd  mov     rax, [rcx]
0x140003800  lea     rdx, [rbp+57h+var_B0]
0x140003804  movups  xmmword ptr [rbp+57h+var_6E], xmm1
0x140003808  mov     [rbp+57h+var_90], r15w
0x14000380d  movups  [rbp+57h+var_4E], xmm1
0x140003811  mov     rax, [rax+50h]
0x140003815  movups  xmmword ptr [rbp+57h+var_AE], xmm1
0x140003819  mov     qword ptr [rbp+57h+var_8E+0Eh], r12
0x14000381d  mov     [rbp+57h+var_70], r15w
0x140003822  mov     qword ptr [rbp+57h+var_6E+0Eh], r12
0x140003826  mov     [rbp+57h+var_50], r15w
0x14000382b  mov     qword ptr [rbp+57h+var_4E+0Eh], r12
0x14000382f  mov     [rbp+57h+var_B0], r15w
0x140003834  mov     qword ptr [rbp+57h+var_AE+0Eh], r12
0x140003838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000383d  mov     edi, eax
0x14000383f  mov     [rsp+120h+var_F0], eax
0x140003843  test    eax, eax
0x140003845  mov     eax, 239h
0x14000384a  js      short loc_1400037D1
0x14000384c  mov     rcx, [rbp+57h+arg_8]; struct ITaskService *
0x140003850  lea     r8, [rbp+57h+arg_10]; struct IRegisteredTask **
0x140003854  mov     [rsp+120h+var_EC], ax
0x140003859  call    ?GetWMIBackupTask@@YAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z; GetWMIBackupTask(ITaskService *,ushort const *,IRegisteredTask * *)
0x14000385e  mov     rbx, [rbp+57h+arg_10]
0x140003862  mov     edi, eax
0x140003864  mov     [rsp+120h+var_F0], eax
0x140003868  test    eax, eax
0x14000386a  mov     eax, 23Ch
0x14000386f  js      loc_1400037D1
0x140003875  mov     [rsp+120h+var_EC], ax
0x14000387a  lea     r8, [rbp+57h+arg_18]
0x14000387e  mov     rax, [rbx]
0x140003881  xor     edx, edx
0x140003883  mov     rcx, rbx
0x140003886  mov     rax, [rax+70h]
0x14000388a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000388f  mov     edi, eax
0x140003891  mov     [rsp+120h+var_F0], eax
0x140003895  test    eax, eax
0x140003897  mov     eax, 23Fh
0x14000389c  js      loc_1400037D1
0x1400038a2  mov     rcx, [rbp+57h+arg_18]
0x1400038a6  lea     rdx, [rbp+57h+arg_0]
0x1400038aa  mov     [rsp+120h+var_EC], ax
0x1400038af  mov     rax, [rcx]
0x1400038b2  mov     rax, [rax+38h]
0x1400038b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038bb  mov     edi, eax
0x1400038bd  mov     [rsp+120h+var_F0], eax
0x1400038c1  test    eax, eax
0x1400038c3  mov     eax, 241h
0x1400038c8  js      loc_1400037D1
0x1400038ce  mov     [rsp+120h+var_EC], ax
0x1400038d3  xor     eax, eax
0x1400038d5  cmp     [rbp+57h+arg_0], eax
0x1400038d8  setnle  al
0x1400038db  mov     [rsi], eax
0x1400038dd  mov     rcx, [rbp+57h+arg_18]
0x1400038e1  test    rcx, rcx
0x1400038e4  jz      short loc_1400038F2
0x1400038e6  mov     rax, [rcx]
0x1400038e9  mov     rax, [rax+10h]
0x1400038ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038f2  test    rbx, rbx
0x1400038f5  jz      short loc_140003906
0x1400038f7  mov     rax, [rbx]
0x1400038fa  mov     rcx, rbx
0x1400038fd  mov     rax, [rax+10h]
0x140003901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003906  mov     rcx, [rbp+57h+arg_8]
0x14000390a  test    rcx, rcx
0x14000390d  jz      short loc_14000392B
0x14000390f  mov     rax, [rcx]
0x140003912  mov     rax, [rax+10h]
0x140003916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000391b  jmp     short loc_14000392B
0x14000391d  mov     edi, 80070057h
0x140003922  mov     [rsp+120h+var_EA], ax
0x140003927  mov     [rsp+120h+var_F0], edi
0x14000392b  lea     rcx, [rsp+120h+var_F0]; this
0x140003930  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140003935  mov     eax, edi
0x140003937  add     rsp, 0F8h
0x14000393e  pop     r15
0x140003940  pop     r12
0x140003942  pop     rdi
0x140003943  pop     rsi
0x140003944  pop     rbx
0x140003945  pop     rbp
0x140003946  retn
```
