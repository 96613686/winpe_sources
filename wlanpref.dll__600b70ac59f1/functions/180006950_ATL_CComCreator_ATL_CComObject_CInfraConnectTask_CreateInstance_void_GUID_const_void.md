# ATL::CComCreator<ATL::CComObject<CInfraConnectTask>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006950`
- end: `0x180006a6d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCInfraConnectTask@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800058f0`

## callees

- `0x18000130c`
- `0x180006950`
- `0x1800080a0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CInfraConnectTask>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  GUID *v7; // rax
  GUID *v8; // rdi
  int v9; // eax
  int v10; // ecx
  GUID *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (GUID *)operator new(0x60u);
    v8 = v7;
    if ( v7 )
    {
      *(_DWORD *)v7->Data4 = 0;
      v7[1] = 0;
      v7[2] = 0;
      *(_QWORD *)&v7[3].Data1 = 0;
      v7[3].Data4[0] = 0;
      *(_QWORD *)&v7[4].Data1 = 0;
      *(_QWORD *)v7[4].Data4 = 0;
      v7[5] = GUID_NULL;
      *(_QWORD *)&v7->Data1 = &ATL::CComObject<CInfraConnectTask>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)&v8[1]);
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(GUID *, __int64, _QWORD *))&v8->Data1)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(GUID *, __int64))(*(_QWORD *)&v8->Data1 + 136LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006950  mov     [rsp+arg_10], r8
0x180006955  mov     [rsp+arg_8], rdx
0x18000695a  mov     [rsp+arg_0], rcx
0x18000695f  push    rsi
0x180006960  push    rdi
0x180006961  push    r14
0x180006963  push    r15
0x180006965  sub     rsp, 28h
0x180006969  mov     r14, r8
0x18000696c  mov     r15, rdx
0x18000696f  test    r8, r8
0x180006972  jnz     short loc_18000697E
0x180006974  mov     eax, 80004003h
0x180006979  jmp     loc_180006A62
0x18000697e  mov     qword ptr [r8], 0
0x180006985  mov     esi, 8007000Eh
0x18000698a  mov     dword ptr [rsp+48h+arg_0], esi
0x18000698e  mov     [rsp+48h+arg_18], 0
0x180006997  mov     ecx, 60h ; '`'; Size
0x18000699c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069a1  mov     rdi, rax
0x1800069a4  test    rdi, rdi
0x1800069a7  jz      short loc_1800069F5
0x1800069a9  mov     dword ptr [rax+8], 0
0x1800069b0  xorps   xmm0, xmm0
0x1800069b3  xor     eax, eax
0x1800069b5  movups  xmmword ptr [rdi+10h], xmm0
0x1800069b9  movups  xmmword ptr [rdi+20h], xmm0
0x1800069bd  mov     [rdi+30h], rax
0x1800069c1  mov     [rdi+38h], al
0x1800069c4  mov     [rdi+40h], rax
0x1800069c8  mov     [rdi+48h], rax
0x1800069cc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800069d3  movdqu  xmmword ptr [rdi+50h], xmm0
0x1800069d8  lea     rax, ??_7?$CComObject@VCInfraConnectTask@@@ATL@@6B@; const ATL::CComObject<CInfraConnectTask>::`vftable'
0x1800069df  mov     [rdi], rax
0x1800069e2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800069e9  mov     rax, [rcx]
0x1800069ec  mov     rax, [rax+8]
0x1800069f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f5  mov     [rsp+48h+arg_18], rdi
0x1800069fa  jmp     short loc_180006A0F
0x1800069fc  mov     r14, [rsp+48h+arg_10]
0x180006a01  mov     r15, [rsp+48h+arg_8]
0x180006a06  mov     esi, dword ptr [rsp+48h+arg_0]
0x180006a0a  mov     rdi, [rsp+48h+arg_18]
0x180006a0f  test    rdi, rdi
0x180006a12  jz      short loc_180006A60
0x180006a14  lea     rcx, [rdi+10h]; this
0x180006a18  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006a1d  xor     ecx, ecx
0x180006a1f  test    eax, eax
0x180006a21  cmovs   ecx, eax
0x180006a24  xor     esi, esi
0x180006a26  test    ecx, ecx
0x180006a28  cmovs   esi, ecx
0x180006a2b  test    esi, esi
0x180006a2d  jnz     short loc_180006A49
0x180006a2f  mov     rax, [rdi]
0x180006a32  mov     r8, r14
0x180006a35  mov     rdx, r15
0x180006a38  mov     rcx, rdi
0x180006a3b  mov     rax, [rax]
0x180006a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a43  mov     esi, eax
0x180006a45  test    eax, eax
0x180006a47  jz      short loc_180006A60
0x180006a49  mov     rdx, [rdi]
0x180006a4c  mov     rax, [rdx+88h]
0x180006a53  mov     edx, 1
0x180006a58  mov     rcx, rdi
0x180006a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a60  mov     eax, esi
0x180006a62  add     rsp, 28h
0x180006a66  pop     r15
0x180006a68  pop     r14
0x180006a6a  pop     rdi
0x180006a6b  pop     rsi
0x180006a6c  retn
```
