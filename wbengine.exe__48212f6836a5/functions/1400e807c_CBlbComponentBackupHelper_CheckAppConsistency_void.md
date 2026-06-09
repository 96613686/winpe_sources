# CBlbComponentBackupHelper::CheckAppConsistency(void)

- ea: `0x1400e807c`
- end: `0x1400e858a`
- name: `?CheckAppConsistency@CBlbComponentBackupHelper@@QEAAJXZ`
- size: `1294`
- prototype: `__int64 __fastcall(CBlbComponentBackupHelper *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x140006d7c`
- `0x140006d94`
- `0x140007ad3`
- `0x140007ec8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x1400889f0`
- `0x1400e807c`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400e82ab`
- `ole32!CoTaskMemAlloc` at `0x1400e82d3`
- `ole32!CoTaskMemAlloc` at `0x1400e82ab`
- `ole32!CoTaskMemAlloc` at `0x1400e82d3`
- `ole32!CoTaskMemFree` at `0x1400e8417`
- `ole32!CoTaskMemFree` at `0x1400e842e`
- `ole32!CoTaskMemFree` at `0x1400e8452`
- `ole32!CoTaskMemFree` at `0x1400e8467`
- `ole32!CoTaskMemFree` at `0x1400e8417`
- `ole32!CoTaskMemFree` at `0x1400e842e`
- `ole32!CoTaskMemFree` at `0x1400e8452`
- `ole32!CoTaskMemFree` at `0x1400e8467`
- `ole32!CoCreateInstance` at `0x1400e825a`
- `ole32!CoCreateInstance` at `0x1400e825a`

## string_xrefs

- `0x1400e80cc`: `base\stor\blb\engine\componenthelper\componentbackuphelper.cpp`
- `0x1400e810e`: `m_pSppMetadata->pwszBackupComponents != NULL`

## pseudocode

```c
__int64 __fastcall CBlbComponentBackupHelper::CheckAppConsistency(CBlbComponentBackupHelper *this)
{
  unsigned __int16 **v2; // r15
  unsigned __int16 **v3; // r14
  unsigned int v4; // r12d
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  CBlbServiceModule *v7; // rcx
  __int64 (__fastcall **v8)(_QWORD *, GUID *, __int64 *); // rax
  HRESULT v9; // edi
  PVOID *v10; // rcx
  __int64 v11; // rdx
  SIZE_T v12; // rdi
  unsigned __int16 **v13; // rax
  unsigned __int16 **v14; // rax
  __int64 i; // rbp
  __int64 v16; // r12
  int v17; // edx
  __int64 v18; // r9
  __int64 v19; // rbx
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rcx
  unsigned int v23; // [rsp+90h] [rbp+8h]
  LPVOID ppv; // [rsp+98h] [rbp+10h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids);
  }
  if ( !*((_QWORD *)this + 6) )
    BlbAssert("base\\stor\\blb\\engine\\componenthelper\\componentbackuphelper.cpp", 0x80Cu, "m_pSppMetadata != NULL");
  if ( !*((_QWORD *)this + 8) )
    BlbAssert("base\\stor\\blb\\engine\\componenthelper\\componentbackuphelper.cpp", 0x80Du, "m_pSppGroupProp != NULL");
  if ( !**((_QWORD **)this + 6) )
    BlbAssert(
      "base\\stor\\blb\\engine\\componenthelper\\componentbackuphelper.cpp",
      0x80Eu,
      "m_pSppMetadata->pwszBackupComponents != NULL");
  if ( !*((_BYTE *)this + 33) )
    BlbAssert("base\\stor\\blb\\engine\\componenthelper\\componentbackuphelper.cpp", 0x80Fu, "m_bInitialized");
  v2 = 0;
  ppv = 0;
  v25 = 0;
  v3 = 0;
  v4 = 0;
  v5 = operator new(0x48u);
  v6 = v5;
  if ( !v5 )
  {
    v6 = 0;
    goto LABEL_27;
  }
  v7 = ATL::_pAtlModule;
  *((_DWORD *)v5 + 2) = 0;
  *((_OWORD *)v5 + 1) = 0;
  *((_OWORD *)v5 + 2) = 0;
  v5[6] = 0;
  *((_BYTE *)v5 + 56) = 0;
  v5[8] = 0;
  *v5 = &ATL::CComObject<CBlbConsistencyCheckCallback>::`vftable';
  (*(void (__fastcall **)(CBlbServiceModule *))(*(_QWORD *)v7 + 8LL))(v7);
  (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
  v8 = (__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v6;
  v6[8] = this;
  v9 = (*v8)(v6, &IID_IBlbsrvAppConsistencyCallback, &v25);
  if ( v9 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 72;
LABEL_19:
      WPP_SF_d(v10[2], v11, &WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids);
LABEL_20:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  v9 = CoCreateInstance(&CLSID_BlbsrvCheckAppConsistency, 0, 1u, &IID_IBlbsrvCheckAppConsistency, &ppv);
  if ( v9 >= 0 )
  {
    v23 = *(_DWORD *)(*((_QWORD *)this + 8) + 80LL);
    v4 = v23;
    v12 = 8LL * v23;
    v13 = (unsigned __int16 **)CoTaskMemAlloc(v12);
    v2 = v13;
    if ( v13 )
    {
      memset_0(v13, 0, v12);
      v14 = (unsigned __int16 **)CoTaskMemAlloc(v12);
      v3 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, v12);
        for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
        {
          v16 = 56LL * (unsigned int)i;
          v9 = BlbutilDuplicateString(
                 *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 8) + 88LL) + v16 + 16),
                 &v2[i],
                 0);
          if ( v9 < 0 )
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = 74;
              v18 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 88LL) + v16 + 16);
LABEL_38:
              WPP_SF_Sd(
                (unsigned int)v10[2],
                v17,
                (unsigned int)&WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids,
                v18,
                v9);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
LABEL_39:
            v4 = v23;
            goto LABEL_40;
          }
          v9 = BlbutilDuplicateString(
                 *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 8) + 88LL) + v16 + 24),
                 &v3[i],
                 0);
          if ( v9 < 0 )
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = 75;
              v18 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 88LL) + v16 + 24);
              goto LABEL_38;
            }
            goto LABEL_39;
          }
          v4 = v23;
        }
        v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, unsigned int, unsigned __int16 **, unsigned __int16 **, __int64))(*(_QWORD *)ppv + 24LL))(
               ppv,
               **((_QWORD **)this + 6),
               *(unsigned int *)(*((_QWORD *)this + 6) + 8LL),
               *(_QWORD *)(*((_QWORD *)this + 6) + 16LL),
               v4,
               v2,
               v3,
               v25);
        if ( v9 >= 0 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
        else
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = 76;
            goto LABEL_19;
          }
        }
        goto LABEL_40;
      }
    }
LABEL_27:
    v9 = -2147024882;
    goto LABEL_20;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 73;
    goto LABEL_19;
  }
LABEL_40:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    ppv = 0;
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    *v6 = &CBlbConsistencyCheckCallback::`vftable';
    ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(v6 + 2));
    operator delete(v6);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v19 = 0;
  if ( v4 )
  {
    do
    {
      v20 = v2[v19];
      if ( v20 )
      {
        CoTaskMemFree(v20);
        v2[v19] = 0;
      }
      v21 = v3[v19];
      if ( v21 )
      {
        CoTaskMemFree(v21);
        v3[v19] = 0;
      }
      v19 = (unsigned int)(v19 + 1);
    }
    while ( (unsigned int)v19 < v4 );
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    CoTaskMemFree(v2);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    CoTaskMemFree(v3);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_(v10[2], 77, &WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400e807c  mov     [rsp+arg_18], rbx
0x1400e8081  push    rbp
0x1400e8082  push    rsi
0x1400e8083  push    rdi
0x1400e8084  push    r12
0x1400e8086  push    r13
0x1400e8088  push    r14
0x1400e808a  push    r15
0x1400e808c  sub     rsp, 50h
0x1400e8090  mov     rsi, rcx
0x1400e8093  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e809a  lea     r13, WPP_GLOBAL_Control
0x1400e80a1  cmp     rcx, r13
0x1400e80a4  jz      short loc_1400E80C7
0x1400e80a6  test    byte ptr [rcx+1Ch], 1
0x1400e80aa  jz      short loc_1400E80C7
0x1400e80ac  cmp     byte ptr [rcx+19h], 4
0x1400e80b0  jb      short loc_1400E80C7
0x1400e80b2  mov     rcx, [rcx+10h]
0x1400e80b6  lea     r8, WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids
0x1400e80bd  mov     edx, 47h ; 'G'
0x1400e80c2  call    WPP_SF_
0x1400e80c7  cmp     qword ptr [rsi+30h], 0
0x1400e80cc  lea     rbx, aBaseStorBlbEng_53; "base\\stor\\blb\\engine\\componenthelpe"...
0x1400e80d3  jnz     short loc_1400E80E9
0x1400e80d5  lea     r8, aMPsppmetadataN; "m_pSppMetadata != NULL"
0x1400e80dc  mov     edx, 80Ch; unsigned int
0x1400e80e1  mov     rcx, rbx; char *
0x1400e80e4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e80e9  cmp     qword ptr [rsi+40h], 0
0x1400e80ee  jnz     short loc_1400E8104
0x1400e80f0  lea     r8, aMPsppgroupprop; "m_pSppGroupProp != NULL"
0x1400e80f7  mov     edx, 80Dh; unsigned int
0x1400e80fc  mov     rcx, rbx; char *
0x1400e80ff  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e8104  mov     rax, [rsi+30h]
0x1400e8108  cmp     qword ptr [rax], 0
0x1400e810c  jnz     short loc_1400E8122
0x1400e810e  lea     r8, aMPsppmetadataP; "m_pSppMetadata->pwszBackupComponents !="...
0x1400e8115  mov     edx, 80Eh; unsigned int
0x1400e811a  mov     rcx, rbx; char *
0x1400e811d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e8122  cmp     byte ptr [rsi+21h], 0
0x1400e8126  jnz     short loc_1400E813C
0x1400e8128  lea     r8, aMBinitialized_0; "m_bInitialized"
0x1400e812f  mov     edx, 80Fh; unsigned int
0x1400e8134  mov     rcx, rbx; char *
0x1400e8137  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e813c  xor     r15d, r15d
0x1400e813f  mov     [rsp+88h+arg_8], 0
0x1400e814b  mov     [rsp+88h+arg_10], 0
0x1400e8157  xor     r14d, r14d
0x1400e815a  xor     r12d, r12d
0x1400e815d  lea     ebp, [r15+48h]
0x1400e8161  mov     ecx, ebp; Size
0x1400e8163  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400e8168  mov     [rsp+88h+arg_0], rax
0x1400e8170  mov     rbx, rax
0x1400e8173  test    rax, rax
0x1400e8176  jz      loc_1400E8583
0x1400e817c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400e8183  xorps   xmm0, xmm0
0x1400e8186  mov     [rax+8], r12d
0x1400e818a  xor     eax, eax
0x1400e818c  movups  xmmword ptr [rbx+10h], xmm0
0x1400e8190  movups  xmmword ptr [rbx+20h], xmm0
0x1400e8194  mov     [rbx+30h], rax
0x1400e8198  mov     [rbx+38h], al
0x1400e819b  mov     [rbx+40h], rax
0x1400e819f  lea     rax, ??_7?$CComObject@VCBlbConsistencyCheckCallback@@@ATL@@6B@; const ATL::CComObject<CBlbConsistencyCheckCallback>::`vftable'
0x1400e81a6  mov     [rbx], rax
0x1400e81a9  mov     rax, [rcx]
0x1400e81ac  mov     rax, [rax+8]
0x1400e81b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e81b5  test    rbx, rbx
0x1400e81b8  jz      loc_1400E82B9
0x1400e81be  mov     rax, [rbx]
0x1400e81c1  mov     rcx, rbx
0x1400e81c4  mov     rax, [rax+8]
0x1400e81c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e81cd  mov     rax, [rbx]
0x1400e81d0  lea     r8, [rsp+88h+arg_10]
0x1400e81d8  lea     rdx, IID_IBlbsrvAppConsistencyCallback
0x1400e81df  mov     [rbx+40h], rsi
0x1400e81e3  mov     rcx, rbx
0x1400e81e6  mov     rax, [rax]
0x1400e81e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e81ee  mov     edi, eax
0x1400e81f0  test    eax, eax
0x1400e81f2  jns     short loc_1400E8239
0x1400e81f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e81fb  cmp     rcx, r13
0x1400e81fe  jz      loc_1400E83A2
0x1400e8204  test    byte ptr [rcx+1Ch], 1
0x1400e8208  jz      loc_1400E83A2
0x1400e820e  cmp     byte ptr [rcx+19h], 2
0x1400e8212  jb      loc_1400E83A2
0x1400e8218  mov     edx, ebp
0x1400e821a  mov     rcx, [rcx+10h]
0x1400e821e  lea     r8, WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids
0x1400e8225  mov     r9d, eax
0x1400e8228  call    WPP_SF_d
0x1400e822d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8234  jmp     loc_1400E83A2
0x1400e8239  xor     edx, edx; pUnkOuter
0x1400e823b  lea     rax, [rsp+88h+arg_8]
0x1400e8243  lea     r9, IID_IBlbsrvCheckAppConsistency; riid
0x1400e824a  mov     [rsp+88h+ppv], rax; ppv
0x1400e824f  lea     rcx, CLSID_BlbsrvCheckAppConsistency; rclsid
0x1400e8256  lea     r8d, [rdx+1]; dwClsContext
0x1400e825a  call    cs:__imp_CoCreateInstance
0x1400e8260  mov     edi, eax
0x1400e8262  test    eax, eax
0x1400e8264  jns     short loc_1400E8291
0x1400e8266  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e826d  cmp     rcx, r13
0x1400e8270  jz      loc_1400E83A2
0x1400e8276  test    byte ptr [rcx+1Ch], 1
0x1400e827a  jz      loc_1400E83A2
0x1400e8280  cmp     byte ptr [rcx+19h], 2
0x1400e8284  jb      loc_1400E83A2
0x1400e828a  mov     edx, 49h ; 'I'
0x1400e828f  jmp     short loc_1400E821A
0x1400e8291  mov     rax, [rsi+40h]
0x1400e8295  mov     r12d, [rax+50h]
0x1400e8299  mov     edi, r12d
0x1400e829c  mov     dword ptr [rsp+88h+arg_0], r12d
0x1400e82a4  shl     rdi, 3
0x1400e82a8  mov     rcx, rdi; cb
0x1400e82ab  call    cs:__imp_CoTaskMemAlloc
0x1400e82b1  mov     r15, rax
0x1400e82b4  test    rax, rax
0x1400e82b7  jnz     short loc_1400E82C3
0x1400e82b9  mov     edi, 8007000Eh
0x1400e82be  jmp     loc_1400E822D
0x1400e82c3  mov     r8, rdi; Size
0x1400e82c6  xor     edx, edx; Val
0x1400e82c8  mov     rcx, r15; void *
0x1400e82cb  call    memset_0
0x1400e82d0  mov     rcx, rdi; cb
0x1400e82d3  call    cs:__imp_CoTaskMemAlloc
0x1400e82d9  mov     r14, rax
0x1400e82dc  test    rax, rax
0x1400e82df  jz      short loc_1400E82B9
0x1400e82e1  mov     r8, rdi; Size
0x1400e82e4  xor     edx, edx; Val
0x1400e82e6  mov     rcx, rax; void *
0x1400e82e9  call    memset_0
0x1400e82ee  xor     ebp, ebp
0x1400e82f0  cmp     ebp, r12d
0x1400e82f3  jnb     loc_1400E84F6
0x1400e82f9  mov     rax, [rsi+40h]
0x1400e82fd  lea     rdx, [r15+rbp*8]; unsigned __int16 **
0x1400e8301  mov     r13d, ebp
0x1400e8304  xor     r8d, r8d; unsigned __int64
0x1400e8307  imul    r12, r13, 38h ; '8'
0x1400e830b  mov     rcx, [rax+58h]
0x1400e830f  mov     rcx, [rcx+r12+10h]; unsigned __int16 *
0x1400e8314  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400e8319  mov     edi, eax
0x1400e831b  test    eax, eax
0x1400e831d  js      loc_1400E84B4
0x1400e8323  mov     rax, [rsi+40h]
0x1400e8327  lea     rdx, [r14+rbp*8]; unsigned __int16 **
0x1400e832b  xor     r8d, r8d; unsigned __int64
0x1400e832e  mov     rcx, [rax+58h]
0x1400e8332  mov     rcx, [rcx+r12+18h]; unsigned __int16 *
0x1400e8337  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400e833c  mov     edi, eax
0x1400e833e  test    eax, eax
0x1400e8340  js      short loc_1400E834E
0x1400e8342  mov     r12d, dword ptr [rsp+88h+arg_0]
0x1400e834a  inc     ebp
0x1400e834c  jmp     short loc_1400E82F0
0x1400e834e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8355  lea     r13, WPP_GLOBAL_Control
0x1400e835c  cmp     rcx, r13
0x1400e835f  jz      short loc_1400E839A
0x1400e8361  test    byte ptr [rcx+1Ch], 1
0x1400e8365  jz      short loc_1400E839A
0x1400e8367  cmp     byte ptr [rcx+19h], 2
0x1400e836b  jb      short loc_1400E839A
0x1400e836d  mov     rax, [rsi+40h]
0x1400e8371  mov     edx, 4Bh ; 'K'
0x1400e8376  mov     r9, [rax+58h]
0x1400e837a  mov     r9, [r9+r12+18h]
0x1400e837f  mov     rcx, [rcx+10h]
0x1400e8383  lea     r8, WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids
0x1400e838a  mov     dword ptr [rsp+88h+ppv], edi
0x1400e838e  call    WPP_SF_Sd
0x1400e8393  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e839a  mov     r12d, dword ptr [rsp+88h+arg_0]
0x1400e83a2  mov     rdx, [rsp+88h+arg_8]
0x1400e83aa  test    rdx, rdx
0x1400e83ad  jz      short loc_1400E83D1
0x1400e83af  mov     rax, [rdx]
0x1400e83b2  mov     rcx, rdx
0x1400e83b5  mov     rax, [rax+10h]
0x1400e83b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e83be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e83c5  mov     [rsp+88h+arg_8], 0
0x1400e83d1  test    rbx, rbx
0x1400e83d4  jz      short loc_1400E8407
0x1400e83d6  mov     rax, [rbx]
0x1400e83d9  mov     rcx, rbx
0x1400e83dc  mov     rax, [rax+10h]
0x1400e83e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e83e5  lea     rax, ??_7CBlbConsistencyCheckCallback@@6B@; const CBlbConsistencyCheckCallback::`vftable'
0x1400e83ec  lea     rcx, [rbx+10h]; this
0x1400e83f0  mov     [rbx], rax
0x1400e83f3  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x1400e83f8  mov     rcx, rbx; Block
0x1400e83fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400e8400  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8407  xor     ebx, ebx
0x1400e8409  test    r12d, r12d
0x1400e840c  jz      short loc_1400E844A
0x1400e840e  mov     rcx, [r15+rbx*8]; pv
0x1400e8412  test    rcx, rcx
0x1400e8415  jz      short loc_1400E8425
0x1400e8417  call    cs:__imp_CoTaskMemFree
0x1400e841d  mov     qword ptr [r15+rbx*8], 0
0x1400e8425  mov     rcx, [r14+rbx*8]; pv
0x1400e8429  test    rcx, rcx
0x1400e842c  jz      short loc_1400E843C
0x1400e842e  call    cs:__imp_CoTaskMemFree
0x1400e8434  mov     qword ptr [r14+rbx*8], 0
0x1400e843c  inc     ebx
0x1400e843e  cmp     ebx, r12d
0x1400e8441  jb      short loc_1400E840E
0x1400e8443  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e844a  test    r15, r15
0x1400e844d  jz      short loc_1400E845F
0x1400e844f  mov     rcx, r15; pv
0x1400e8452  call    cs:__imp_CoTaskMemFree
0x1400e8458  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e845f  test    r14, r14
0x1400e8462  jz      short loc_1400E8474
0x1400e8464  mov     rcx, r14; pv
0x1400e8467  call    cs:__imp_CoTaskMemFree
0x1400e846d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8474  cmp     rcx, r13
0x1400e8477  jz      short loc_1400E849A
0x1400e8479  test    byte ptr [rcx+1Ch], 1
0x1400e847d  jz      short loc_1400E849A
0x1400e847f  cmp     byte ptr [rcx+19h], 4
0x1400e8483  jb      short loc_1400E849A
0x1400e8485  mov     rcx, [rcx+10h]
0x1400e8489  lea     r8, WPP_dc2a72229e733de72c9f3614b53eb640_Traceguids
0x1400e8490  mov     edx, 4Dh ; 'M'
0x1400e8495  call    WPP_SF_
0x1400e849a  mov     rbx, [rsp+88h+arg_18]
0x1400e84a2  mov     eax, edi
0x1400e84a4  add     rsp, 50h
0x1400e84a8  pop     r15
0x1400e84aa  pop     r14
0x1400e84ac  pop     r13
0x1400e84ae  pop     r12
0x1400e84b0  pop     rdi
0x1400e84b1  pop     rsi
0x1400e84b2  pop     rbp
0x1400e84b3  retn
0x1400e84b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e84bb  lea     r13, WPP_GLOBAL_Control
0x1400e84c2  cmp     rcx, r13
0x1400e84c5  jz      loc_1400E839A
0x1400e84cb  test    byte ptr [rcx+1Ch], 1
0x1400e84cf  jz      loc_1400E839A
0x1400e84d5  cmp     byte ptr [rcx+19h], 2
0x1400e84d9  jb      loc_1400E839A
0x1400e84df  mov     rax, [rsi+40h]
0x1400e84e3  mov     edx, 4Ah ; 'J'
0x1400e84e8  mov     r9, [rax+58h]
0x1400e84ec  mov     r9, [r9+r12+10h]
0x1400e84f1  jmp     loc_1400E837F
0x1400e84f6  mov     rdx, [rsi+30h]
0x1400e84fa  mov     r8, [rsp+88h+arg_10]
0x1400e8502  mov     rcx, [rsp+88h+arg_8]
0x1400e850a  mov     [rsp+88h+var_50], r8
0x1400e850f  mov     r9, [rdx+10h]
0x1400e8513  mov     r8d, [rdx+8]
0x1400e8517  mov     rax, [rcx]
0x1400e851a  mov     rdx, [rdx]
0x1400e851d  mov     [rsp+88h+var_58], r14
0x1400e8522  mov     [rsp+88h+var_60], r15
0x1400e8527  mov     rax, [rax+18h]
0x1400e852b  mov     dword ptr [rsp+88h+ppv], r12d
0x1400e8530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e8535  mov     edi, eax
0x1400e8537  test    eax, eax
0x1400e8539  jns     short loc_1400E8570
0x1400e853b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8542  lea     r13, WPP_GLOBAL_Control
0x1400e8549  cmp     rcx, r13
0x1400e854c  jz      loc_1400E83A2
0x1400e8552  test    byte ptr [rcx+1Ch], 1
0x1400e8556  jz      loc_1400E83A2
0x1400e855c  cmp     byte ptr [rcx+19h], 2
0x1400e8560  jb      loc_1400E83A2
0x1400e8566  mov     edx, 4Ch ; 'L'
  ... truncated ...
```
