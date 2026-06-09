# CDetectISAPIConfigModule::OnBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001510`
- end: `0x1800017d9`
- name: `?OnBeginRequest@CDetectISAPIConfigModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *, void (__fastcall ***)(_QWORD, _QWORD))`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001510`
- `0x1800017e0`
- `0x180002268`
- `0x180002fd4`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CDetectISAPIConfigModule::OnBeginRequest(
        __int64 a1,
        struct IHttpContext *a2,
        void (__fastcall ***a3)(_QWORD, _QWORD))
{
  struct INativeSectionException *v5; // rdi
  int v6; // ebx
  int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rbp
  CDetectISAPIConfigModule *v10; // rcx
  CDetectISAPIConfigContext *v11; // r12
  int v12; // eax
  __int64 v13; // rax
  __int64 (__fastcall *v14)(struct IHttpContext *); // rax
  __int64 v15; // r10
  __int64 v16; // r10
  __int64 v18; // [rsp+88h] [rbp+10h] BYREF
  struct INativeSectionException *v19; // [rsp+98h] [rbp+20h] BYREF

  v19 = 0;
  v5 = 0;
  v18 = 0;
  v6 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    goto LABEL_19;
  }
  v7 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  v11 = (CDetectISAPIConfigContext *)(**(__int64 (__fastcall ***)(__int64, void *))v9)(
                                       v9,
                                       g_pDetectISAPIConfigModuleContext);
  if ( v11 )
    goto LABEL_8;
  v11 = (CDetectISAPIConfigContext *)operator new(0x18u);
  if ( !v11 )
  {
    v7 = -2147024888;
LABEL_22:
    v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) + 536) = 0;
    v14 = *(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL);
    if ( v18 )
    {
      v16 = v14(a2);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v16 + 24LL))(
        v16,
        500,
        "Internal Server Error",
        19,
        v7,
        v18,
        0);
    }
    else
    {
      v15 = v14(a2);
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
        v15,
        500,
        "Internal Server Error",
        0,
        v7,
        0,
        0);
    }
    (**a3)(a3, (unsigned int)v7);
    v6 = 1;
    goto LABEL_26;
  }
  *((_QWORD *)v11 + 1) = 0;
  *(_QWORD *)v11 = &CDetectISAPIConfigContext::`vftable';
  *((_QWORD *)v11 + 2) = 0;
  v7 = CDetectISAPIConfigContext::Initialize(v11, a2, &v19);
  if ( v7 < 0 )
    goto LABEL_15;
  v12 = (*(__int64 (__fastcall **)(__int64, CDetectISAPIConfigContext *, void *))(*(_QWORD *)v9 + 8LL))(
          v9,
          v11,
          g_pDetectISAPIConfigModuleContext);
  v7 = v12;
  if ( v12 != -2147024811 )
  {
    if ( v12 >= 0 )
      goto LABEL_7;
LABEL_15:
    (**(void (__fastcall ***)(CDetectISAPIConfigContext *))v11)(v11);
    v5 = v19;
    goto LABEL_19;
  }
  (**(void (__fastcall ***)(CDetectISAPIConfigContext *))v11)(v11);
  v11 = (CDetectISAPIConfigContext *)(**(__int64 (__fastcall ***)(__int64, void *))v9)(
                                       v9,
                                       g_pDetectISAPIConfigModuleContext);
  v7 = 0;
LABEL_7:
  v5 = v19;
LABEL_8:
  if ( v7 >= 0 )
  {
    if ( *((_DWORD *)v11 + 2) )
    {
      if ( !g_dwPipelineMode )
      {
        v7 = CDetectISAPIConfigModule::ValidateConfiguration(v10, a2, v11);
        if ( v7 == 1 )
          v6 = 1;
      }
    }
  }
LABEL_19:
  if ( v5 )
    (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v5)(
      v5,
      &IID_IAppHostConfigException,
      &v18);
  if ( v7 < 0 )
    goto LABEL_22;
LABEL_26:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v5 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v5 + 16LL))(v5);
  return v6 != 0 ? 2 : 0;
}

```

## disassembly

```asm
0x180001510  mov     rax, rsp
0x180001513  push    rbx
0x180001514  push    rdi
0x180001515  sub     rsp, 68h
0x180001519  mov     [rax+8], rbp
0x18000151d  mov     ebp, 1
0x180001522  mov     [rax-18h], rsi
0x180001526  mov     [rax-20h], r12
0x18000152a  mov     [rax-28h], r13
0x18000152e  xor     r13d, r13d
0x180001531  mov     [rax-30h], r14
0x180001535  mov     r14, rdx
0x180001538  mov     [rax-38h], r15
0x18000153c  mov     r15, r8
0x18000153f  mov     [rax+20h], r13
0x180001543  mov     edi, r13d
0x180001546  mov     [rax+10h], r13
0x18000154a  mov     ebx, r13d
0x18000154d  test    rdx, rdx
0x180001550  jz      loc_18000169A
0x180001556  mov     rax, [rdx]
0x180001559  mov     rcx, rdx
0x18000155c  mov     esi, r13d
0x18000155f  mov     rax, [rax+0A0h]
0x180001566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156b  mov     rdx, rax
0x18000156e  mov     rcx, [rax]
0x180001571  mov     rax, [rcx+18h]
0x180001575  mov     rcx, rdx
0x180001578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000157d  mov     rdx, cs:?g_pDetectISAPIConfigModuleContext@@3PEAXEA; void * g_pDetectISAPIConfigModuleContext
0x180001584  mov     rbp, rax
0x180001587  mov     rcx, [rax]
0x18000158a  mov     rax, [rcx]
0x18000158d  mov     rcx, rbp
0x180001590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001595  mov     r12, rax
0x180001598  test    rax, rax
0x18000159b  jnz     loc_18000163F
0x1800015a1  mov     ecx, 18h; Size
0x1800015a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800015ab  mov     r12, rax
0x1800015ae  test    rax, rax
0x1800015b1  jz      loc_18000168E
0x1800015b7  lea     rax, ??_7CDetectISAPIConfigContext@@6B@; const CDetectISAPIConfigContext::`vftable'
0x1800015be  mov     [r12+8], r13
0x1800015c3  lea     r8, [rsp+78h+arg_18]; struct INativeSectionException **
0x1800015cb  mov     [r12], rax
0x1800015cf  mov     rdx, r14; struct IHttpContext *
0x1800015d2  mov     [r12+10h], r13
0x1800015d7  mov     rcx, r12; this
0x1800015da  call    ?Initialize@CDetectISAPIConfigContext@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; CDetectISAPIConfigContext::Initialize(IHttpContext *,INativeSectionException * *)
0x1800015df  mov     esi, eax
0x1800015e1  test    eax, eax
0x1800015e3  js      loc_180001670
0x1800015e9  mov     rax, [rbp+0]
0x1800015ed  mov     rdx, r12
0x1800015f0  mov     r8, cs:?g_pDetectISAPIConfigModuleContext@@3PEAXEA; void * g_pDetectISAPIConfigModuleContext
0x1800015f7  mov     rcx, rbp
0x1800015fa  mov     rax, [rax+8]
0x1800015fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001603  mov     esi, eax
0x180001605  cmp     eax, 80070055h
0x18000160a  jnz     short loc_18000166C
0x18000160c  mov     rax, [r12]
0x180001610  mov     rcx, r12
0x180001613  mov     rax, [rax]
0x180001616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000161b  mov     rax, [rbp+0]
0x18000161f  mov     rcx, rbp
0x180001622  mov     rdx, cs:?g_pDetectISAPIConfigModuleContext@@3PEAXEA; void * g_pDetectISAPIConfigModuleContext
0x180001629  mov     rax, [rax]
0x18000162c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001631  mov     r12, rax
0x180001634  mov     esi, r13d
0x180001637  mov     rdi, [rsp+78h+arg_18]
0x18000163f  test    esi, esi
0x180001641  js      short loc_180001687
0x180001643  cmp     [r12+8], ebx
0x180001648  jz      short loc_180001687
0x18000164a  cmp     cs:?g_dwPipelineMode@@3KA, ebx; ulong g_dwPipelineMode
0x180001650  jnz     short loc_180001687
0x180001652  mov     r8, r12; struct CDetectISAPIConfigContext *
0x180001655  mov     rdx, r14; struct IHttpContext *
0x180001658  call    ?ValidateConfiguration@CDetectISAPIConfigModule@@AEAAJPEAVIHttpContext@@PEAVCDetectISAPIConfigContext@@@Z; CDetectISAPIConfigModule::ValidateConfiguration(IHttpContext *,CDetectISAPIConfigContext *)
0x18000165d  cmp     eax, 1
0x180001660  mov     ebp, 1
0x180001665  mov     esi, eax
0x180001667  cmovz   ebx, ebp
0x18000166a  jmp     short loc_18000169F
0x18000166c  test    eax, eax
0x18000166e  jns     short loc_180001637
0x180001670  mov     rax, [r12]
0x180001674  mov     rcx, r12
0x180001677  mov     rax, [rax]
0x18000167a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000167f  mov     rdi, [rsp+78h+arg_18]
0x180001687  mov     ebp, 1
0x18000168c  jmp     short loc_18000169F
0x18000168e  mov     esi, 80070008h
0x180001693  mov     ebp, 1
0x180001698  jmp     short loc_1800016C9
0x18000169a  mov     esi, 80070057h
0x18000169f  test    rdi, rdi
0x1800016a2  jz      short loc_1800016C1
0x1800016a4  mov     rax, [rdi]
0x1800016a7  lea     r8, [rsp+78h+arg_8]
0x1800016af  lea     rdx, IID_IAppHostConfigException
0x1800016b6  mov     rcx, rdi
0x1800016b9  mov     rax, [rax]
0x1800016bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016c1  test    esi, esi
0x1800016c3  jns     loc_180001775
0x1800016c9  mov     rax, [r14]
0x1800016cc  mov     rcx, r14
0x1800016cf  mov     rax, [rax+20h]
0x1800016d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d8  mov     rdx, rax
0x1800016db  mov     rcx, [rax]
0x1800016de  mov     rax, [rcx+8]
0x1800016e2  mov     rcx, rdx
0x1800016e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ea  mov     rcx, r14
0x1800016ed  mov     [rax+218h], r13w
0x1800016f5  mov     rax, [r14]
0x1800016f8  mov     rax, [rax+20h]
0x1800016fc  cmp     [rsp+78h+arg_8], r13
0x180001704  jnz     short loc_180001724
0x180001706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000170b  mov     r10, rax
0x18000170e  mov     [rsp+78h+var_48], r13d
0x180001713  xor     r9d, r9d
0x180001716  mov     [rsp+78h+var_50], r13
0x18000171b  mov     rcx, [rax]
0x18000171e  mov     rax, [rcx+18h]
0x180001722  jmp     short loc_18000174B
0x180001724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001729  mov     r10, rax
0x18000172c  mov     [rsp+78h+var_48], r13d
0x180001731  mov     r9d, 13h
0x180001737  mov     rcx, [rax]
0x18000173a  mov     rax, [rcx+18h]
0x18000173e  mov     rcx, [rsp+78h+arg_8]
0x180001746  mov     [rsp+78h+var_50], rcx
0x18000174b  lea     r8, aInternalServer; "Internal Server Error"
0x180001752  mov     [rsp+78h+var_58], esi
0x180001756  mov     edx, 1F4h
0x18000175b  mov     rcx, r10
0x18000175e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001763  mov     rax, [r15]
0x180001766  mov     edx, esi
0x180001768  mov     rcx, r15
0x18000176b  mov     rax, [rax]
0x18000176e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001773  mov     ebx, ebp
0x180001775  mov     rcx, [rsp+78h+arg_8]
0x18000177d  mov     r15, [rsp+78h+var_38]
0x180001782  mov     r14, [rsp+78h+var_30]
0x180001787  mov     r12, [rsp+78h+var_20]
0x18000178c  mov     rsi, [rsp+78h+var_18]
0x180001791  mov     rbp, [rsp+78h+arg_0]
0x180001799  test    rcx, rcx
0x18000179c  jz      short loc_1800017B2
0x18000179e  mov     rax, [rcx]
0x1800017a1  mov     rax, [rax+10h]
0x1800017a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017aa  mov     [rsp+78h+arg_8], r13
0x1800017b2  mov     r13, [rsp+78h+var_28]
0x1800017b7  test    rdi, rdi
0x1800017ba  jz      short loc_1800017CB
0x1800017bc  mov     rax, [rdi]
0x1800017bf  mov     rcx, rdi
0x1800017c2  mov     rax, [rax+10h]
0x1800017c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017cb  neg     ebx
0x1800017cd  sbb     eax, eax
0x1800017cf  and     eax, 2
0x1800017d2  add     rsp, 68h
0x1800017d6  pop     rdi
0x1800017d7  pop     rbx
0x1800017d8  retn
```
