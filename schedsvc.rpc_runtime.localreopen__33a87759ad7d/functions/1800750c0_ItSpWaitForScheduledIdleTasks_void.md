# ItSpWaitForScheduledIdleTasks(void)

- ea: `0x1800750c0`
- end: `0x1800753c5`
- name: `?ItSpWaitForScheduledIdleTasks@@YAJXZ`
- size: `773`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180074200`

## callees

- `0x18004f0dc`
- `0x180074a20`
- `0x180074a44`
- `0x1800750c0`
- `0x1800753cc`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18007527f`
- `OLEAUT32!__imp_SysFreeString` at `0x18007537d`
- `OLEAUT32!__imp_SysFreeString` at `0x18007527f`
- `OLEAUT32!__imp_SysFreeString` at `0x18007537d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007534a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007534a`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180075383`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180075383`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075143`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075143`

## pseudocode

```c
__int64 ItSpWaitForScheduledIdleTasks(void)
{
  int v0; // edi
  HRESULT v1; // ebx
  __int64 v2; // rax
  __int64 (__fastcall *v3)(LPVOID, __int128 *, __int128 *, __int128 *, _QWORD *); // rax
  __int64 v4; // xmm6_8
  int v5; // r12d
  __int64 *v6; // rcx
  int v7; // esi
  int v8; // r15d
  int v9; // r14d
  int v10; // ebx
  __int64 v11; // rax
  int IsIdleStarted; // eax
  EventManager *v13; // rcx
  void *v14; // r9
  int v15; // r13d
  DWORD v16; // eax
  BSTR bstrString; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v19; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+58h] [rbp-B0h]
  __int64 v23; // [rsp+68h] [rbp-A0h]
  _QWORD v24[5]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v25; // [rsp+98h] [rbp-70h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-60h]
  __int128 v27; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-40h]
  __int128 v29; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-20h]
  int v31; // [rsp+158h] [rbp+50h] BYREF
  int v32; // [rsp+160h] [rbp+58h] BYREF
  unsigned int v33; // [rsp+168h] [rbp+60h]
  int v34; // [rsp+170h] [rbp+68h]

  ppv = 0;
  v0 = 0;
  v23 = 0;
  v31 = 0;
  v32 = 0;
  bstrString = 0;
  v19 = 0;
  *(_OWORD *)&v24[1] = 0;
  v21 = 0;
  LOWORD(v24[1]) = 1;
  v22 = 0;
  v1 = CoCreateInstance(&CLSID_TaskScheduler, 0, 0x17u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v1 >= 0 )
  {
    v24[3] = 0;
    v2 = *(_QWORD *)ppv;
    v27 = *(_OWORD *)&v24[1];
    v28 = 0;
    v29 = *(_OWORD *)&v24[1];
    v3 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, _QWORD *))(v2 + 80);
    v30 = 0;
    v25 = *(_OWORD *)&v24[1];
    v26 = 0;
    v1 = v3(ppv, &v25, &v29, &v27, &v24[1]);
    if ( v1 >= 0 )
    {
      v4 = v23;
      v34 = 0;
      v5 = 0;
      v33 = 0;
      while ( 1 )
      {
        v6 = v19;
        if ( v19 )
        {
          v19 = 0;
          (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
        }
        v1 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)ppv + 64LL))(ppv, 1, &v19);
        if ( v1 < 0 )
          break;
        v1 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v19 + 56))(v19, &v31);
        if ( v1 < 0 )
          break;
        v7 = 0;
        v8 = 0;
        v9 = 0;
        v10 = 1;
        if ( v31 < 1 )
          goto LABEL_28;
        do
        {
          LOWORD(v22) = 3;
          DWORD2(v22) = v10;
          ATL::CComPtrBase<IRunningTask>::Release(&v21);
          v26 = v4;
          v11 = *v19;
          v25 = v22;
          IsIdleStarted = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))(v11 + 64))(v19, &v25, &v21);
          if ( IsIdleStarted < 0 )
            goto LABEL_17;
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          IsIdleStarted = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 72LL))(v21, &bstrString);
          if ( IsIdleStarted < 0
            || (IsIdleStarted = ItSpScheduledTaskIsIdleStarted((struct ITaskService *)ppv, bstrString, &v32),
                IsIdleStarted < 0) )
          {
LABEL_17:
            if ( IsIdleStarted == -2147216629 )
              ++v9;
            else
              ++v8;
          }
          else if ( v32 )
          {
            ++v7;
            if ( v5 )
              break;
            EventManager::EvtReport(v13, &JOB_COMPLETION_PENDING, bstrString, v14);
          }
          ++v10;
        }
        while ( v10 <= v31 );
        v15 = v34;
        if ( v7 )
        {
          v0 = 0;
          goto LABEL_29;
        }
        if ( v9 && (++v33, v33 < 0x3C) || v8 && (++v34, (unsigned int)(v15 + 1) < 0xF) )
        {
          v0 = 0;
        }
        else
        {
LABEL_28:
          if ( (unsigned int)++v0 >= 3 )
          {
            v1 = 0;
            break;
          }
        }
LABEL_29:
        v16 = WaitForSingleObject(hObject, 0x2710u);
        if ( !v16 )
        {
          v1 = -2147023641;
          break;
        }
        if ( v16 != 258 )
        {
          v1 = -2147467259;
          break;
        }
        ++v5;
      }
    }
  }
  if ( bstrString )
    SysFreeString(bstrString);
  CoFreeUnusedLibraries();
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v21);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v19);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&ppv);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800750c0  mov     rax, rsp
0x1800750c3  push    rbp
0x1800750c4  push    rbx
0x1800750c5  push    rsi
0x1800750c6  push    rdi
0x1800750c7  push    r12
0x1800750c9  push    r13
0x1800750cb  push    r14
0x1800750cd  push    r15
0x1800750cf  lea     rbp, [rax-48h]
0x1800750d3  sub     rsp, 108h
0x1800750da  movaps  xmmword ptr [rax-58h], xmm6
0x1800750de  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800750e5  xor     eax, eax
0x1800750e7  mov     [rsp+140h+ppv], 0
0x1800750f0  xor     edi, edi
0x1800750f2  mov     [rsp+140h+var_E0], rax
0x1800750f7  xorps   xmm0, xmm0
0x1800750fa  mov     [rbp+40h+arg_0], eax
0x1800750fd  mov     [rbp+40h+arg_8], eax
0x180075100  lea     rcx, CLSID_TaskScheduler; rclsid
0x180075107  mov     [rsp+140h+bstrString], rax
0x18007510c  xorps   xmm1, xmm1
0x18007510f  lea     rax, [rsp+140h+ppv]
0x180075114  mov     [rsp+140h+var_108], 0
0x18007511d  movups  xmmword ptr [rsp+140h+var_D8+8], xmm0
0x180075122  lea     esi, [rdi+1]
0x180075125  mov     qword ptr [rsp+140h+var_F8], 0
0x18007512e  xor     edx, edx; pUnkOuter
0x180075130  mov     word ptr [rsp+140h+var_D8+8], si
0x180075135  lea     r8d, [rdi+17h]; dwClsContext
0x180075139  mov     [rsp+20h], rax; ppv
0x18007513e  movups  [rsp+140h+var_F8+8], xmm1
0x180075143  call    cs:__imp_CoCreateInstance
0x180075149  mov     ebx, eax
0x18007514b  test    eax, eax
0x18007514d  js      loc_180075373
0x180075153  movups  xmm1, xmmword ptr [rsp+140h+var_D8+8]
0x180075158  mov     rcx, [rsp+140h+ppv]
0x18007515d  lea     rdx, [rsp+140h+var_D8+8]
0x180075162  mov     [rsp+20h], rdx; struct _GUID *
0x180075167  lea     r9, [rbp+40h+var_90]
0x18007516b  lea     r8, [rbp+40h+var_70]
0x18007516f  movaps  xmmword ptr [rsp+140h+var_D8+8], xmm1
0x180075174  lea     rdx, [rbp+40h+var_B0]
0x180075178  mov     [rbp+40h+var_C0], rdi
0x18007517c  mov     rax, [rcx]
0x18007517f  movaps  [rbp+40h+var_90], xmm1
0x180075183  mov     [rbp+40h+var_80], rdi
0x180075187  movaps  [rbp+40h+var_70], xmm1
0x18007518b  mov     rax, [rax+50h]
0x18007518f  mov     [rbp+40h+var_60], rdi
0x180075193  movaps  [rbp+40h+var_B0], xmm1
0x180075197  mov     [rbp+40h+var_A0], rdi
0x18007519b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751a0  mov     ebx, eax
0x1800751a2  test    eax, eax
0x1800751a4  js      loc_180075373
0x1800751aa  movsd   xmm6, [rsp+140h+var_E0]
0x1800751b0  xor     r13d, r13d
0x1800751b3  mov     [rbp+40h+arg_18], r13d
0x1800751b7  xor     r12d, r12d
0x1800751ba  mov     [rbp+40h+arg_10], edi
0x1800751bd  mov     rcx, [rsp+140h+var_108]
0x1800751c2  test    rcx, rcx
0x1800751c5  jz      short loc_1800751DC
0x1800751c7  mov     [rsp+140h+var_108], 0
0x1800751d0  mov     rax, [rcx]
0x1800751d3  mov     rax, [rax+10h]
0x1800751d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751dc  mov     rcx, [rsp+140h+ppv]
0x1800751e1  lea     r8, [rsp+140h+var_108]
0x1800751e6  mov     edx, esi
0x1800751e8  mov     rax, [rcx]
0x1800751eb  mov     rax, [rax+40h]
0x1800751ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751f4  mov     ebx, eax
0x1800751f6  test    eax, eax
0x1800751f8  js      loc_180075373
0x1800751fe  mov     rcx, [rsp+140h+var_108]
0x180075203  lea     rdx, [rbp+40h+arg_0]
0x180075207  mov     rax, [rcx]
0x18007520a  mov     rax, [rax+38h]
0x18007520e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075213  mov     ebx, eax
0x180075215  test    eax, eax
0x180075217  js      loc_180075373
0x18007521d  xor     esi, esi
0x18007521f  xor     r15d, r15d
0x180075222  xor     r14d, r14d
0x180075225  lea     ebx, [rsi+1]
0x180075228  cmp     [rbp+40h+arg_0], ebx
0x18007522b  jl      loc_180075332
0x180075231  lea     r13d, [rsi+3]
0x180075235  lea     rcx, [rsp+140h+var_F8]
0x18007523a  mov     word ptr [rsp+140h+var_F8+8], r13w
0x180075240  mov     dword ptr [rsp+140h+var_E8], ebx
0x180075244  call    ?Release@?$CComPtrBase@UIRunningTask@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IRunningTask>::Release(void)
0x180075249  mov     rcx, [rsp+140h+var_108]
0x18007524e  lea     r8, [rsp+140h+var_F8]
0x180075253  movups  xmm0, [rsp+140h+var_F8+8]
0x180075258  lea     rdx, [rbp+40h+var_B0]
0x18007525c  movsd   [rbp+40h+var_A0], xmm6
0x180075261  mov     rax, [rcx]
0x180075264  movaps  [rbp+40h+var_B0], xmm0
0x180075268  mov     rax, [rax+40h]
0x18007526c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075271  test    eax, eax
0x180075273  js      short loc_1800752DF
0x180075275  mov     rcx, [rsp+140h+bstrString]; bstrString
0x18007527a  test    rcx, rcx
0x18007527d  jz      short loc_18007528E
0x18007527f  call    cs:__imp_SysFreeString
0x180075285  mov     [rsp+140h+bstrString], 0
0x18007528e  mov     rcx, qword ptr [rsp+140h+var_F8]
0x180075293  lea     rdx, [rsp+140h+bstrString]
0x180075298  mov     rax, [rcx]
0x18007529b  mov     rax, [rax+48h]
0x18007529f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800752a4  test    eax, eax
0x1800752a6  js      short loc_1800752DF
0x1800752a8  mov     rdx, [rsp+140h+bstrString]; unsigned __int16 *
0x1800752ad  lea     r8, [rbp+40h+arg_8]; int *
0x1800752b1  mov     rcx, [rsp+140h+ppv]; struct ITaskService *
0x1800752b6  call    ?ItSpScheduledTaskIsIdleStarted@@YAJPEAUITaskService@@QEAGPEAH@Z; ItSpScheduledTaskIsIdleStarted(ITaskService *,ushort * const,int *)
0x1800752bb  test    eax, eax
0x1800752bd  js      short loc_1800752DF
0x1800752bf  cmp     [rbp+40h+arg_8], 0
0x1800752c3  jz      short loc_1800752EE
0x1800752c5  inc     esi
0x1800752c7  test    r12d, r12d
0x1800752ca  jnz     short loc_1800752F9
0x1800752cc  mov     r8, [rsp+140h+bstrString]; unsigned __int16 *
0x1800752d1  lea     rdx, JOB_COMPLETION_PENDING; struct _EVENT_DESCRIPTOR *
0x1800752d8  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,void *,_GUID const *)
0x1800752dd  jmp     short loc_1800752EE
0x1800752df  cmp     eax, 8004130Bh
0x1800752e4  jnz     short loc_1800752EB
0x1800752e6  inc     r14d
0x1800752e9  jmp     short loc_1800752EE
0x1800752eb  inc     r15d
0x1800752ee  inc     ebx
0x1800752f0  cmp     ebx, [rbp+40h+arg_0]
0x1800752f3  jle     loc_180075235
0x1800752f9  mov     r13d, [rbp+40h+arg_18]
0x1800752fd  test    esi, esi
0x1800752ff  jz      short loc_180075305
0x180075301  xor     edi, edi
0x180075303  jmp     short loc_180075339
0x180075305  mov     esi, 1
0x18007530a  test    r14d, r14d
0x18007530d  jz      short loc_180075320
0x18007530f  mov     eax, [rbp+40h+arg_10]
0x180075312  add     eax, esi
0x180075314  mov     [rbp+40h+arg_10], eax
0x180075317  cmp     eax, 3Ch ; '<'
0x18007531a  jnb     short loc_180075320
0x18007531c  xor     edi, edi
0x18007531e  jmp     short loc_18007533E
0x180075320  test    r15d, r15d
0x180075323  jz      short loc_180075332
0x180075325  add     r13d, esi
0x180075328  mov     [rbp+40h+arg_18], r13d
0x18007532c  cmp     r13d, 0Fh
0x180075330  jb      short loc_18007531C
0x180075332  inc     edi
0x180075334  cmp     edi, 3
0x180075337  jnb     short loc_180075371
0x180075339  mov     esi, 1
0x18007533e  mov     rcx, cs:hObject; hHandle
0x180075345  mov     edx, 2710h; dwMilliseconds
0x18007534a  call    cs:__imp_WaitForSingleObject
0x180075350  test    eax, eax
0x180075352  jz      short loc_18007536A
0x180075354  cmp     eax, 102h
0x180075359  jnz     short loc_180075363
0x18007535b  add     r12d, esi
0x18007535e  jmp     loc_1800751BD
0x180075363  mov     ebx, 80004005h
0x180075368  jmp     short loc_180075373
0x18007536a  mov     ebx, 800704E7h
0x18007536f  jmp     short loc_180075373
0x180075371  xor     ebx, ebx
0x180075373  mov     rcx, [rsp+140h+bstrString]; bstrString
0x180075378  test    rcx, rcx
0x18007537b  jz      short loc_180075383
0x18007537d  call    cs:__imp_SysFreeString
0x180075383  call    cs:__imp_CoFreeUnusedLibraries
0x180075389  lea     rcx, [rsp+140h+var_F8]
0x18007538e  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180075393  lea     rcx, [rsp+140h+var_108]
0x180075398  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18007539d  lea     rcx, [rsp+140h+ppv]
0x1800753a2  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800753a7  movaps  xmm6, [rsp+140h+var_58+8]
0x1800753af  mov     eax, ebx
0x1800753b1  add     rsp, 108h
0x1800753b8  pop     r15
0x1800753ba  pop     r14
0x1800753bc  pop     r13
0x1800753be  pop     r12
0x1800753c0  pop     rdi
0x1800753c1  pop     rsi
0x1800753c2  pop     rbx
0x1800753c3  pop     rbp
0x1800753c4  retn
```
