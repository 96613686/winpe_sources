# CPropertyBagFieldsProxy::SetProperty(ushort const *,ushort const *,long,ulong,_FsrmPropertyDefinitionType)

- ea: `0x18004c5f0`
- end: `0x18004c8a3`
- name: `?SetProperty@CPropertyBagFieldsProxy@@UEAAXPEBG0JKW4_FsrmPropertyDefinitionType@@@Z`
- size: `691`
- prototype: `void(CPropertyBagFieldsProxy *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, enum _FsrmPropertyDefinitionType)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x18004c5f0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x18004c6ca`
- `ole32!CoTaskMemRealloc` at `0x18004c6ca`
- `ole32!CoTaskMemFree` at `0x18004c804`
- `ole32!CoTaskMemFree` at `0x18004c817`
- `ole32!CoTaskMemFree` at `0x18004c829`
- `ole32!CoTaskMemFree` at `0x18004c804`
- `ole32!CoTaskMemFree` at `0x18004c817`
- `ole32!CoTaskMemFree` at `0x18004c829`

## string_xrefs

- `0x18004c636`: `base\fs\fsrm\service\modulewrp\pbfproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CPropertyBagFieldsProxy::SetProperty(
        CPropertyBagFieldsProxy *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        enum _FsrmPropertyDefinitionType a6)
{
  int v10; // ebx
  __int64 v11; // rcx
  unsigned int v12; // ebx
  LPVOID v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rsi
  void *v18; // rbx
  const unsigned __int16 *v19; // rdx
  _QWORD *v20; // rax
  void *v21; // rax
  __int64 v22; // rax
  int v23; // eax
  char Hr; // al
  _QWORD *v25; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  void *v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+54h] [rbp-ACh]
  int v31; // [rsp+58h] [rbp-A8h]
  _BYTE v32[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+C0h] [rbp-40h]
  void **v34; // [rsp+D0h] [rbp-30h] BYREF
  int v35; // [rsp+D8h] [rbp-28h]

  v25 = v28;
  v28[0] = L"base\\fs\\fsrm\\service\\modulewrp\\pbfproxy.cpp";
  v28[1] = L"CPropertyBagFieldsProxy::SetProperty";
  v28[2] = L"PBFPROXC";
  v29 = 395;
  v30 = 22;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v34, (const struct CSrmDebugInfo *)v28, 0);
  v10 = *((_DWORD *)this + 123);
  v11 = *((_QWORD *)this + 50);
  if ( *(_DWORD *)(v11 + 16) == v10 )
  {
    if ( v10 )
      v12 = 2 * v10;
    else
      v12 = 4;
    v13 = CoTaskMemRealloc(*(LPVOID *)(v11 + 24), 40LL * v12);
    if ( !v13 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v34, -2147024882);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v34);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v34, 0x198u, Hr, 0, v25);
    }
    v35 = 0;
    *(_QWORD *)(*((_QWORD *)this + 50) + 24LL) = v13;
    *((_DWORD *)this + 123) = v12;
    memset_0(
      (void *)(*(_QWORD *)(*((_QWORD *)this + 50) + 24LL) + 40LL * *(unsigned int *)(*((_QWORD *)this + 50) + 16LL)),
      0,
      8LL * (v12 - *(_DWORD *)(*((_QWORD *)this + 50) + 16LL)));
  }
  v14 = *((_QWORD *)this + 50);
  v15 = *(unsigned int *)(v14 + 16);
  v16 = 5 * v15;
  v17 = *(_QWORD *)(v14 + 24);
  *(_DWORD *)(v14 + 16) = v15 + 1;
  v25 = 0;
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v25, a2);
  v18 = 0;
  v27 = 0;
  if ( a3 )
  {
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v27, a3);
    v18 = v27;
  }
  v26 = 0;
  v19 = (const unsigned __int16 *)((char *)this + 352);
  if ( *((_QWORD *)this + 47) >= 8u )
    v19 = *(const unsigned __int16 **)v19;
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v26, v19);
  v20 = v25;
  v25 = 0;
  *(_QWORD *)(v17 + 8 * v16) = v20;
  if ( a3 )
  {
    v21 = v18;
    v18 = 0;
    v27 = 0;
  }
  else
  {
    v21 = 0;
  }
  *(_QWORD *)(v17 + 8 * v16 + 8) = v21;
  v22 = v26;
  v26 = 0;
  *(_QWORD *)(v17 + 8 * v16 + 16) = v22;
  if ( *((_DWORD *)this + 34) == 3 )
    v23 = *((_DWORD *)this + 74);
  else
    v23 = 0;
  *(_DWORD *)(v17 + 8 * v16 + 24) = v23;
  *(_DWORD *)(v17 + 8 * v16 + 28) = a4;
  *(_DWORD *)(v17 + 8 * v16 + 32) = a5;
  *(_DWORD *)(v17 + 8 * v16 + 36) = a6;
  *((_BYTE *)this + 392) = 1;
  CoTaskMemFree(0);
  v26 = 0;
  CoTaskMemFree(v18);
  v27 = 0;
  CoTaskMemFree(0);
  v25 = 0;
  v34 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v34);
}

```

## disassembly

```asm
0x18004c5f0  mov     [rsp-8+arg_18], rbx
0x18004c5f5  push    rbp
0x18004c5f6  push    rsi
0x18004c5f7  push    rdi
0x18004c5f8  push    r12
0x18004c5fa  push    r13
0x18004c5fc  push    r14
0x18004c5fe  push    r15
0x18004c600  lea     rbp, [rsp-90h]
0x18004c608  sub     rsp, 190h
0x18004c60f  mov     rax, cs:__security_cookie
0x18004c616  xor     rax, rsp
0x18004c619  mov     [rbp+0C0h+var_40], rax
0x18004c620  mov     r13d, r9d
0x18004c623  mov     r15, r8
0x18004c626  mov     r12, rdx
0x18004c629  mov     r14, rcx
0x18004c62c  lea     rax, [rsp+1C0h+var_188]
0x18004c631  mov     [rsp+1C0h+var_1A0], rax
0x18004c636  lea     rax, aBaseFsFsrmServ_15; "base\\fs\\fsrm\\service\\modulewrp\\pbf"...
0x18004c63d  mov     [rsp+1C0h+var_188], rax
0x18004c642  lea     rax, aCpropertybagfi_5; "CPropertyBagFieldsProxy::SetProperty"
0x18004c649  mov     [rsp+1C0h+var_180], rax
0x18004c64e  lea     rax, aPbfproxc; "PBFPROXC"
0x18004c655  mov     [rsp+1C0h+var_178], rax
0x18004c65a  mov     [rsp+1C0h+var_170], 18Bh
0x18004c662  mov     [rsp+1C0h+var_16C], 16h
0x18004c66a  mov     [rsp+1C0h+var_168], 0FFh
0x18004c672  mov     [rbp+0C0h+var_100], 1000000h
0x18004c679  xor     edx, edx; Val
0x18004c67b  lea     r8d, [rdx+60h]; Size
0x18004c67f  lea     rcx, [rsp+1C0h+var_160]; void *
0x18004c684  call    memset_0
0x18004c689  nop
0x18004c68a  xor     r8d, r8d
0x18004c68d  lea     rdx, [rsp+1C0h+var_188]
0x18004c692  lea     rcx, [rbp+0C0h+var_F0]
0x18004c696  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18004c69b  nop
0x18004c69c  mov     ebx, [r14+1ECh]
0x18004c6a3  mov     rcx, [r14+190h]
0x18004c6aa  cmp     [rcx+10h], ebx
0x18004c6ad  jnz     short loc_18004C721
0x18004c6af  test    ebx, ebx
0x18004c6b1  jnz     short loc_18004C6BA
0x18004c6b3  mov     ebx, 4
0x18004c6b8  jmp     short loc_18004C6BC
0x18004c6ba  add     ebx, ebx
0x18004c6bc  mov     eax, ebx
0x18004c6be  lea     rdx, [rax+rax*4]
0x18004c6c2  shl     rdx, 3; cb
0x18004c6c6  mov     rcx, [rcx+18h]; pv
0x18004c6ca  call    cs:__imp_CoTaskMemRealloc
0x18004c6d0  mov     rdx, rax
0x18004c6d3  mov     ecx, [rbp+0C0h+var_E8]
0x18004c6d6  mov     [rbp+0C0h+var_E8], ecx
0x18004c6d9  test    rax, rax
0x18004c6dc  jz      loc_18004C877
0x18004c6e2  mov     [rbp+0C0h+var_E8], 0
0x18004c6e9  mov     rax, [r14+190h]
0x18004c6f0  mov     [rax+18h], rdx
0x18004c6f4  mov     [r14+1ECh], ebx
0x18004c6fb  mov     rdx, [r14+190h]
0x18004c702  mov     eax, [rdx+10h]
0x18004c705  sub     ebx, eax
0x18004c707  mov     r8d, ebx
0x18004c70a  shl     r8, 3; Size
0x18004c70e  lea     rcx, [rax+rax*4]
0x18004c712  mov     rax, [rdx+18h]
0x18004c716  lea     rcx, [rax+rcx*8]; void *
0x18004c71a  xor     edx, edx; Val
0x18004c71c  call    memset_0
0x18004c721  mov     rcx, [r14+190h]
0x18004c728  mov     eax, [rcx+10h]
0x18004c72b  lea     rdi, [rax+rax*4]
0x18004c72f  mov     rsi, [rcx+18h]
0x18004c733  inc     eax
0x18004c735  mov     [rcx+10h], eax
0x18004c738  mov     [rsp+1C0h+var_1A0], 0
0x18004c741  mov     rdx, r12; unsigned __int16 *
0x18004c744  lea     rcx, [rsp+1C0h+var_1A0]; this
0x18004c749  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18004c74e  xor     r12d, r12d
0x18004c751  mov     ebx, r12d
0x18004c754  mov     [rsp+1C0h+var_190], rbx
0x18004c759  test    r15, r15
0x18004c75c  jz      short loc_18004C770
0x18004c75e  mov     rdx, r15; unsigned __int16 *
0x18004c761  lea     rcx, [rsp+1C0h+var_190]; this
0x18004c766  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18004c76b  mov     rbx, [rsp+1C0h+var_190]
0x18004c770  mov     [rsp+1C0h+var_198], r12
0x18004c775  lea     rdx, [r14+160h]
0x18004c77c  cmp     qword ptr [rdx+18h], 8
0x18004c781  jb      short loc_18004C786
0x18004c783  mov     rdx, [rdx]; unsigned __int16 *
0x18004c786  lea     rcx, [rsp+1C0h+var_198]; this
0x18004c78b  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18004c790  mov     rax, [rsp+1C0h+var_1A0]
0x18004c795  mov     [rsp+1C0h+var_1A0], r12
0x18004c79a  mov     [rsi+rdi*8], rax
0x18004c79e  test    r15, r15
0x18004c7a1  jz      short loc_18004C7B0
0x18004c7a3  mov     rax, rbx
0x18004c7a6  mov     rbx, r12
0x18004c7a9  mov     [rsp+1C0h+var_190], rbx
0x18004c7ae  jmp     short loc_18004C7B3
0x18004c7b0  mov     rax, r12
0x18004c7b3  mov     [rsi+rdi*8+8], rax
0x18004c7b8  mov     rax, [rsp+1C0h+var_198]
0x18004c7bd  mov     [rsp+1C0h+var_198], r12
0x18004c7c2  mov     [rsi+rdi*8+10h], rax
0x18004c7c7  cmp     dword ptr [r14+88h], 3
0x18004c7cf  jnz     short loc_18004C7DA
0x18004c7d1  mov     eax, [r14+128h]
0x18004c7d8  jmp     short loc_18004C7DD
0x18004c7da  mov     eax, r12d
0x18004c7dd  mov     [rsi+rdi*8+18h], eax
0x18004c7e1  mov     [rsi+rdi*8+1Ch], r13d
0x18004c7e6  mov     eax, [rbp+0C0h+arg_20]
0x18004c7ec  mov     [rsi+rdi*8+20h], eax
0x18004c7f0  mov     eax, [rbp+0C0h+arg_28]
0x18004c7f6  mov     [rsi+rdi*8+24h], eax
0x18004c7fa  mov     byte ptr [r14+188h], 1
0x18004c802  xor     ecx, ecx; pv
0x18004c804  call    cs:__imp_CoTaskMemFree
0x18004c80a  mov     [rsp+1C0h+var_198], r12
0x18004c80f  mov     [rsp+1C0h+var_198], r12
0x18004c814  mov     rcx, rbx; pv
0x18004c817  call    cs:__imp_CoTaskMemFree
0x18004c81d  mov     [rsp+1C0h+var_190], r12
0x18004c822  mov     [rsp+1C0h+var_190], r12
0x18004c827  xor     ecx, ecx; pv
0x18004c829  call    cs:__imp_CoTaskMemFree
0x18004c82f  mov     [rsp+1C0h+var_1A0], r12
0x18004c834  mov     [rsp+1C0h+var_1A0], r12
0x18004c839  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004c840  mov     [rbp+0C0h+var_F0], rax
0x18004c844  lea     rcx, [rbp+0C0h+var_F0]; this
0x18004c848  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18004c84d  mov     rcx, [rbp+0C0h+var_40]
0x18004c854  xor     rcx, rsp; StackCookie
0x18004c857  call    __security_check_cookie
0x18004c85c  mov     rbx, [rsp+1C0h+arg_18]
0x18004c864  add     rsp, 190h
0x18004c86b  pop     r15
0x18004c86d  pop     r14
0x18004c86f  pop     r13
0x18004c871  pop     r12
0x18004c873  pop     rdi
0x18004c874  pop     rsi
0x18004c875  pop     rbp
0x18004c876  retn
0x18004c877  mov     edx, 8007000Eh; int
0x18004c87c  lea     rcx, [rbp+0C0h+var_F0]; this
0x18004c880  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18004c885  lea     rcx, [rbp+0C0h+var_F0]; this
0x18004c889  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18004c88e  mov     r8d, eax; char
0x18004c891  xor     r9d, r9d; unsigned __int16 *
0x18004c894  mov     edx, 198h; unsigned int
0x18004c899  lea     rcx, [rbp+0C0h+var_F0]; this
0x18004c89d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
