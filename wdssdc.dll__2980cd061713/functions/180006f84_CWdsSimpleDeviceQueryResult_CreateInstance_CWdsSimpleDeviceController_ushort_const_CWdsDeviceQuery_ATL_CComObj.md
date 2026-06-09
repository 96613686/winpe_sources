# CWdsSimpleDeviceQueryResult::CreateInstance(CWdsSimpleDeviceController *,ushort const *,CWdsDeviceQuery *,ATL::CComObject<CWdsSimpleDeviceQueryResult> * *)

- ea: `0x180006f84`
- end: `0x1800070c5`
- name: `?CreateInstance@CWdsSimpleDeviceQueryResult@@SAJPEAVCWdsSimpleDeviceController@@PEBGPEAUCWdsDeviceQuery@@PEAPEAV?$CComObject@VCWdsSimpleDeviceQueryResult@@@ATL@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(struct CWdsSimpleDeviceController *, unsigned __int16 *, struct CWdsDeviceQuery *, CWdsSimpleDeviceQueryResult **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006210`
- `0x180006320`
- `0x180006460`
- `0x180006598`

## callees

- `0x1800018e4`
- `0x1800038ec`
- `0x180006f84`
- `0x180007214`
- `0x180007808`
- `0x18000d010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006fe1`
- `KERNEL32!InitializeCriticalSection` at `0x180006fe1`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceQueryResult::CreateInstance(
        struct CWdsSimpleDeviceController *a1,
        unsigned __int16 *a2,
        struct CWdsDeviceQuery *a3,
        CWdsSimpleDeviceQueryResult **a4)
{
  CWdsSimpleDeviceQueryResult *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8

  v8 = (CWdsSimpleDeviceQueryResult *)operator new(0x90u);
  *((_DWORD *)v8 + 2) = 0;
  *((_OWORD *)v8 + 1) = 0;
  *((_OWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 6) = 0;
  *((_BYTE *)v8 + 56) = 0;
  *((_QWORD *)v8 + 8) = 0;
  *((_QWORD *)v8 + 9) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 104));
  v9 = ATL::_pAtlModule;
  *(_QWORD *)v8 = &ATL::CComObject<CWdsSimpleDeviceQueryResult>::`vftable';
  *((_QWORD *)v8 + 11) = 0;
  *((_DWORD *)v8 + 24) = 0;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
  LODWORD(v11) = ATL::CComCriticalSection::Init((CWdsSimpleDeviceQueryResult *)((char *)v8 + 16));
  if ( (int)v11 < 0 )
  {
    (*(void (__fastcall **)(CWdsSimpleDeviceQueryResult *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
    v8 = 0;
  }
  else
  {
    *((_BYTE *)v8 + 56) = 1;
    LODWORD(v11) = 0;
  }
  if ( (int)ElValidateHr_0((unsigned int)v11, v10, v12, 489) < 0
    || ((*(void (__fastcall **)(CWdsSimpleDeviceQueryResult *))(*(_QWORD *)v8 + 8LL))(v8),
        v11 = (unsigned int)CWdsSimpleDeviceQueryResult::Initialize(v8, a1, a2, a3),
        (int)ElValidateHr_0(v11, v13, v14, 494) < 0) )
  {
    if ( v8 )
      (*(void (__fastcall **)(CWdsSimpleDeviceQueryResult *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    *a4 = v8;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006f84  mov     rax, rsp
0x180006f87  mov     [rax+8], rbx
0x180006f8b  mov     [rax+10h], rbp
0x180006f8f  mov     [rax+18h], rsi
0x180006f93  mov     [rax+20h], rdi
0x180006f97  push    r12
0x180006f99  push    r14
0x180006f9b  push    r15
0x180006f9d  sub     rsp, 20h
0x180006fa1  mov     r12, rcx
0x180006fa4  mov     r14, r9
0x180006fa7  mov     ecx, 90h; Size
0x180006fac  mov     rbp, r8
0x180006faf  mov     r15, rdx
0x180006fb2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006fb7  mov     rbx, rax
0x180006fba  xorps   xmm0, xmm0
0x180006fbd  mov     dword ptr [rax+8], 0
0x180006fc4  xor     eax, eax
0x180006fc6  movups  xmmword ptr [rbx+10h], xmm0
0x180006fca  lea     rcx, [rbx+68h]; lpCriticalSection
0x180006fce  movups  xmmword ptr [rbx+20h], xmm0
0x180006fd2  mov     [rbx+30h], rax
0x180006fd6  mov     [rbx+38h], al
0x180006fd9  mov     [rbx+40h], rax
0x180006fdd  mov     [rbx+48h], rax
0x180006fe1  call    cs:__imp_InitializeCriticalSection
0x180006fe8  nop     dword ptr [rax+rax+00h]
0x180006fed  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006ff4  lea     rax, ??_7?$CComObject@VCWdsSimpleDeviceQueryResult@@@ATL@@6B@; const ATL::CComObject<CWdsSimpleDeviceQueryResult>::`vftable'
0x180006ffb  mov     [rbx], rax
0x180006ffe  mov     qword ptr [rbx+58h], 0
0x180007006  mov     dword ptr [rbx+60h], 0
0x18000700d  mov     rax, [rcx]
0x180007010  mov     rax, [rax+8]
0x180007014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007019  lea     rcx, [rbx+10h]; this
0x18000701d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180007022  mov     edi, eax
0x180007024  test    eax, eax
0x180007026  js      short loc_180007030
0x180007028  mov     byte ptr [rbx+38h], 1
0x18000702c  xor     edi, edi
0x18000702e  jmp     short loc_180007046
0x180007030  mov     rax, [rbx]
0x180007033  mov     edx, 1
0x180007038  mov     rcx, rbx
0x18000703b  mov     rax, [rax+38h]
0x18000703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007044  xor     ebx, ebx
0x180007046  mov     r9d, 1E9h
0x18000704c  mov     ecx, edi
0x18000704e  call    ElValidateHr_0
0x180007053  test    eax, eax
0x180007055  js      short loc_18000708F
0x180007057  mov     rax, [rbx]
0x18000705a  mov     rcx, rbx
0x18000705d  mov     rax, [rax+8]
0x180007061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007066  mov     r9, rbp; struct CWdsDeviceQuery *
0x180007069  mov     r8, r15; unsigned __int16 *
0x18000706c  mov     rdx, r12; struct CWdsSimpleDeviceController *
0x18000706f  mov     rcx, rbx; this
0x180007072  call    ?Initialize@CWdsSimpleDeviceQueryResult@@AEAAJPEAVCWdsSimpleDeviceController@@PEBGPEAUCWdsDeviceQuery@@@Z; CWdsSimpleDeviceQueryResult::Initialize(CWdsSimpleDeviceController *,ushort const *,CWdsDeviceQuery *)
0x180007077  mov     r9d, 1EEh
0x18000707d  mov     ecx, eax
0x18000707f  mov     edi, eax
0x180007081  call    ElValidateHr_0
0x180007086  test    eax, eax
0x180007088  js      short loc_18000708F
0x18000708a  mov     [r14], rbx
0x18000708d  jmp     short loc_1800070A3
0x18000708f  test    rbx, rbx
0x180007092  jz      short loc_1800070A3
0x180007094  mov     rax, [rbx]
0x180007097  mov     rcx, rbx
0x18000709a  mov     rax, [rax+10h]
0x18000709e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a3  mov     rbx, [rsp+38h+arg_0]
0x1800070a8  mov     eax, edi
0x1800070aa  mov     rdi, [rsp+38h+arg_18]
0x1800070af  mov     rbp, [rsp+38h+arg_8]
0x1800070b4  mov     rsi, [rsp+38h+arg_10]
0x1800070b9  add     rsp, 20h
0x1800070bd  pop     r15
0x1800070bf  pop     r14
0x1800070c1  pop     r12
0x1800070c3  retn
```
