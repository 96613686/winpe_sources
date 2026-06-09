# _ExecuteScopeRestorePoint(void)

- ea: `0x1400050f0`
- end: `0x14000543b`
- name: `?_ExecuteScopeRestorePoint@@YAJXZ`
- size: `843`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000312c`
- `0x140004a70`

## callees

- `0x140001b3c`
- `0x140002e1c`
- `0x1400050f0`
- `0x140005488`
- `0x140006334`
- `0x1400068d4`
- `0x140006ab0`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140011010`

## import_xrefs

- `SRCORE!SrFreeRpPropArray` at `0x140005380`
- `SRCORE!SrFreeRpPropArray` at `0x140005380`
- `ole32!CoTaskMemAlloc` at `0x140005305`
- `ole32!CoTaskMemAlloc` at `0x140005305`
- `ole32!CoCreateInstance` at `0x140005197`
- `ole32!CoCreateInstance` at `0x14000522c`
- `ole32!CoCreateInstance` at `0x140005197`
- `ole32!CoCreateInstance` at `0x14000522c`
- `ole32!CoTaskMemFree` at `0x140005373`
- `ole32!CoTaskMemFree` at `0x140005373`

## pseudocode

```c
__int64 _ExecuteScopeRestorePoint(void)
{
  _DWORD *v0; // rsi
  __int16 v1; // ax
  int v2; // ecx
  __int64 v3; // rbx
  unsigned __int64 v4; // r8
  unsigned int v5; // r9d
  unsigned __int64 v6; // rcx
  _DWORD *v7; // rax
  unsigned int v8; // edi
  unsigned int v9; // ebx
  LPVOID v11; // [rsp+30h] [rbp-39h] BYREF
  __int64 v12; // [rsp+38h] [rbp-31h] BYREF
  struct ISharedProtectionPoints *ppv; // [rsp+40h] [rbp-29h] BYREF
  HRESULT Instance; // [rsp+48h] [rbp-21h] BYREF
  __int16 v15; // [rsp+4Ch] [rbp-1Dh]
  __int16 v16; // [rsp+4Eh] [rbp-1Bh]
  unsigned __int8 v17; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int8 v18; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v19; // [rsp+E0h] [rbp+77h] BYREF
  int v20; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Instance, "_ExecuteScopeRestorePoint", 0x29Bu, 1u);
  v20 = 0;
  v17 = 0;
  v11 = 0;
  v19 = 0;
  v0 = 0;
  v12 = 0;
  ppv = 0;
  v18 = 0;
  Instance = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, (LPVOID *)&ppv);
  v1 = 683;
  if ( Instance < 0 )
    goto LABEL_5;
  v15 = 683;
  v2 = CheckSREnabled(ppv, &v20, 0);
  Instance = v2;
  v1 = 686;
  if ( v2 < 0 )
    goto LABEL_5;
  v15 = 686;
  if ( v2 != 1 )
  {
    Instance = SxShouldCreateScopedSnapshots(&v17);
    v1 = 693;
    if ( Instance >= 0 )
    {
      v15 = 693;
      if ( !v17 )
      {
        v1 = 697;
        goto LABEL_33;
      }
      Instance = CoCreateInstance(&CLSID_SrControl, 0, 1u, &IID_ISrControl, &v11);
      v1 = 700;
      if ( Instance >= 0 )
      {
        v15 = 700;
        Instance = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64 *))(*(_QWORD *)v11 + 32LL))(
                     v11,
                     &v19,
                     &v12);
        v1 = 702;
        if ( Instance >= 0 )
        {
          v15 = 702;
          if ( !v19 )
          {
            v1 = 706;
            goto LABEL_33;
          }
          v3 = 0;
          v4 = 0;
          v5 = 0;
          do
          {
            v6 = *(_QWORD *)(v12 + 152LL * v5 + 16);
            if ( v6 > v4 )
              v3 = v12 + 152LL * v5;
            ++v5;
            if ( v6 <= v4 )
              v6 = v4;
            v4 = v6;
          }
          while ( v5 < v19 );
          if ( *(_DWORD *)(v3 + 32) == 15 )
          {
            v1 = 723;
            goto LABEL_33;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
          {
            WPP_SF_L_guid_I(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v6, *(_DWORD *)(v3 + 24), v3);
          }
          v7 = CoTaskMemAlloc(4LL * *(unsigned int *)(v3 + 88));
          v0 = v7;
          if ( v7 )
          {
            memset_0(v7, 0, 4LL * *(unsigned int *)(v3 + 88));
            v8 = 0;
            if ( !*(_DWORD *)(v3 + 88) )
            {
LABEL_32:
              v1 = 751;
              goto LABEL_33;
            }
            while ( (unsigned int)SxIsBootVolume(*(const unsigned __int16 **)(*(_QWORD *)(v3 + 96) + 48LL * v8 + 16)) )
            {
              if ( ++v8 >= *(_DWORD *)(v3 + 88) )
                goto LABEL_32;
            }
            v0[v8] = 1;
            Instance = SxIsShadowCopyScoped(*(const unsigned __int16 **)(*(_QWORD *)(v3 + 96) + 48LL * v8 + 24), &v18);
            v1 = 755;
            if ( Instance >= 0 )
            {
              v15 = 755;
              if ( v18 )
              {
                v1 = 759;
                goto LABEL_33;
              }
              Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _DWORD *))(*(_QWORD *)v11 + 72LL))(
                           v11,
                           v3,
                           *(unsigned int *)(v3 + 88),
                           v0);
              v1 = 767;
              if ( Instance >= 0 )
                goto LABEL_34;
            }
          }
          else
          {
            Instance = -2147024882;
            v1 = 735;
          }
        }
      }
    }
LABEL_5:
    v16 = v1;
    goto LABEL_35;
  }
  v1 = 690;
LABEL_33:
  Instance = 0;
LABEL_34:
  v15 = v1;
LABEL_35:
  CoTaskMemFree(v0);
  SrFreeRpPropArray(v19, &v12);
  v9 = Instance;
  if ( ppv )
    (*(void (__fastcall **)(struct ISharedProtectionPoints *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v11 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Instance);
  return v9;
}

```

## disassembly

```asm
0x1400050f0  push    rbp
0x1400050f2  push    rbx
0x1400050f3  push    rsi
0x1400050f4  push    rdi
0x1400050f5  push    r12
0x1400050f7  push    r13
0x1400050f9  push    r14
0x1400050fb  push    r15
0x1400050fd  lea     rbp, [rsp-1Fh]
0x140005102  sub     rsp, 88h
0x140005109  mov     rcx, cs:WPP_GLOBAL_Control
0x140005110  lea     rdi, WPP_GLOBAL_Control
0x140005117  cmp     rcx, rdi
0x14000511a  jz      short loc_14000513A
0x14000511c  test    dword ptr [rcx+1Ch], 20000000h
0x140005123  jz      short loc_14000513A
0x140005125  mov     rcx, [rcx+10h]
0x140005129  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140005130  mov     edx, 2Bh ; '+'
0x140005135  call    WPP_SF_
0x14000513a  mov     r13d, 1
0x140005140  lea     rdx, aExecutescopere; "_ExecuteScopeRestorePoint"
0x140005147  mov     r9d, r13d; unsigned __int16
0x14000514a  lea     rcx, [rbp+57h+var_78]; this
0x14000514e  mov     r8d, 29Bh; unsigned __int16
0x140005154  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140005159  xor     r12d, r12d
0x14000515c  lea     rax, [rbp+57h+var_80]
0x140005160  lea     r9, IID_ISharedProtectionPoints; riid
0x140005167  mov     [rsp+0C0h+ppv], rax; ppv
0x14000516c  mov     r8d, r13d; dwClsContext
0x14000516f  mov     [rbp+57h+arg_18], r12d
0x140005173  xor     edx, edx; pUnkOuter
0x140005175  mov     [rbp+57h+arg_0], r12b
0x140005179  lea     rcx, CLSID_SPP; rclsid
0x140005180  mov     [rbp+57h+var_90], r12
0x140005184  mov     [rbp+57h+arg_10], r12d
0x140005188  mov     esi, r12d
0x14000518b  mov     [rbp+57h+var_88], r12
0x14000518f  mov     [rbp+57h+var_80], r12
0x140005193  mov     [rbp+57h+arg_8], r12b
0x140005197  call    cs:__imp_CoCreateInstance
0x14000519d  mov     [rbp+57h+var_78], eax
0x1400051a0  test    eax, eax
0x1400051a2  mov     eax, 2ABh
0x1400051a7  jns     short loc_1400051B2
0x1400051a9  mov     [rbp+57h+var_72], ax
0x1400051ad  jmp     loc_140005370
0x1400051b2  mov     rcx, [rbp+57h+var_80]; struct ISharedProtectionPoints *
0x1400051b6  lea     rdx, [rbp+57h+arg_18]; int *
0x1400051ba  xor     r8d, r8d; unsigned int *
0x1400051bd  mov     [rbp+57h+var_74], ax
0x1400051c1  call    ?CheckSREnabled@@YAJPEAUISharedProtectionPoints@@PEAHPEAK@Z; CheckSREnabled(ISharedProtectionPoints *,int *,ulong *)
0x1400051c6  mov     ecx, eax
0x1400051c8  mov     [rbp+57h+var_78], eax
0x1400051cb  test    eax, eax
0x1400051cd  mov     eax, 2AEh
0x1400051d2  js      short loc_1400051A9
0x1400051d4  mov     [rbp+57h+var_74], ax
0x1400051d8  cmp     ecx, r13d
0x1400051db  jnz     short loc_1400051E7
0x1400051dd  mov     eax, 2B2h
0x1400051e2  jmp     loc_140005368
0x1400051e7  lea     rcx, [rbp+57h+arg_0]; unsigned __int8 *
0x1400051eb  call    ?SxShouldCreateScopedSnapshots@@YAJPEAE@Z; SxShouldCreateScopedSnapshots(uchar *)
0x1400051f0  mov     [rbp+57h+var_78], eax
0x1400051f3  test    eax, eax
0x1400051f5  mov     eax, 2B5h
0x1400051fa  js      short loc_1400051A9
0x1400051fc  mov     [rbp+57h+var_74], ax
0x140005200  cmp     [rbp+57h+arg_0], r12b
0x140005204  jnz     short loc_140005210
0x140005206  mov     eax, 2B9h
0x14000520b  jmp     loc_140005368
0x140005210  lea     rax, [rbp+57h+var_90]
0x140005214  mov     r8d, r13d; dwClsContext
0x140005217  lea     r9, IID_ISrControl; riid
0x14000521e  mov     [rsp+0C0h+ppv], rax; ppv
0x140005223  xor     edx, edx; pUnkOuter
0x140005225  lea     rcx, CLSID_SrControl; rclsid
0x14000522c  call    cs:__imp_CoCreateInstance
0x140005232  mov     [rbp+57h+var_78], eax
0x140005235  test    eax, eax
0x140005237  mov     eax, 2BCh
0x14000523c  js      loc_1400051A9
0x140005242  mov     rcx, [rbp+57h+var_90]
0x140005246  lea     r8, [rbp+57h+var_88]
0x14000524a  mov     [rbp+57h+var_74], ax
0x14000524e  lea     rdx, [rbp+57h+arg_10]
0x140005252  mov     rax, [rcx]
0x140005255  mov     rax, [rax+20h]
0x140005259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000525e  mov     [rbp+57h+var_78], eax
0x140005261  test    eax, eax
0x140005263  mov     eax, 2BEh
0x140005268  js      loc_1400051A9
0x14000526e  mov     edx, [rbp+57h+arg_10]
0x140005271  mov     [rbp+57h+var_74], ax
0x140005275  test    edx, edx
0x140005277  jnz     short loc_140005283
0x140005279  mov     eax, 2C2h
0x14000527e  jmp     loc_140005368
0x140005283  mov     rbx, r12
0x140005286  mov     r8, r12
0x140005289  mov     r9d, r12d
0x14000528c  test    edx, edx
0x14000528e  jz      short loc_1400052BE
0x140005290  mov     r10, [rbp+57h+var_88]
0x140005294  mov     eax, r9d
0x140005297  imul    rax, 98h
0x14000529e  add     rax, r10
0x1400052a1  mov     rcx, [rax+10h]
0x1400052a5  cmp     rcx, r8
0x1400052a8  cmova   rbx, rax
0x1400052ac  add     r9d, r13d
0x1400052af  cmp     rcx, r8
0x1400052b2  cmovbe  rcx, r8
0x1400052b6  mov     r8, rcx
0x1400052b9  cmp     r9d, edx
0x1400052bc  jb      short loc_140005294
0x1400052be  cmp     dword ptr [rbx+20h], 0Fh
0x1400052c2  jnz     short loc_1400052CE
0x1400052c4  mov     eax, 2D3h
0x1400052c9  jmp     loc_140005368
0x1400052ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052d5  cmp     rcx, rdi
0x1400052d8  jz      short loc_1400052FE
0x1400052da  test    dword ptr [rcx+1Ch], 8000000h
0x1400052e1  jz      short loc_1400052FE
0x1400052e3  mov     rax, [rbx+10h]
0x1400052e7  mov     r9d, [rbx+18h]
0x1400052eb  mov     rcx, [rcx+10h]
0x1400052ef  mov     [rsp+0C0h+var_98], rax
0x1400052f4  mov     [rsp+0C0h+ppv], rbx
0x1400052f9  call    WPP_SF_L_guid_I
0x1400052fe  mov     ecx, [rbx+58h]
0x140005301  shl     rcx, 2; cb
0x140005305  call    cs:__imp_CoTaskMemAlloc
0x14000530b  mov     rsi, rax
0x14000530e  test    rax, rax
0x140005311  jnz     short loc_140005324
0x140005313  mov     [rbp+57h+var_78], 8007000Eh
0x14000531a  mov     eax, 2DFh
0x14000531f  jmp     loc_1400051A9
0x140005324  mov     r8d, [rbx+58h]
0x140005328  xor     edx, edx; Val
0x14000532a  shl     r8, 2; Size
0x14000532e  mov     rcx, rsi; void *
0x140005331  call    memset_0
0x140005336  mov     edi, r12d
0x140005339  cmp     [rbx+58h], r12d
0x14000533d  jbe     short loc_140005363
0x14000533f  mov     rcx, [rbx+60h]
0x140005343  mov     r15d, edi
0x140005346  lea     r14, [r15+r15*2]
0x14000534a  add     r14, r14
0x14000534d  mov     rcx, [rcx+r14*8+10h]; unsigned __int16 *
0x140005352  call    ?SxIsBootVolume@@YAJPEBG@Z; SxIsBootVolume(ushort const *)
0x140005357  test    eax, eax
0x140005359  jz      short loc_1400053D2
0x14000535b  add     edi, r13d
0x14000535e  cmp     edi, [rbx+58h]
0x140005361  jb      short loc_14000533F
0x140005363  mov     eax, 2EFh
0x140005368  mov     [rbp+57h+var_78], r12d
0x14000536c  mov     [rbp+57h+var_74], ax
0x140005370  mov     rcx, rsi; pv
0x140005373  call    cs:__imp_CoTaskMemFree
0x140005379  mov     ecx, [rbp+57h+arg_10]
0x14000537c  lea     rdx, [rbp+57h+var_88]
0x140005380  call    cs:__imp_SrFreeRpPropArray
0x140005386  mov     rcx, [rbp+57h+var_80]
0x14000538a  mov     ebx, [rbp+57h+var_78]
0x14000538d  test    rcx, rcx
0x140005390  jz      short loc_14000539E
0x140005392  mov     rax, [rcx]
0x140005395  mov     rax, [rax+10h]
0x140005399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000539e  mov     rcx, [rbp+57h+var_90]
0x1400053a2  test    rcx, rcx
0x1400053a5  jz      short loc_1400053B3
0x1400053a7  mov     rdx, [rcx]
0x1400053aa  mov     rax, [rdx+10h]
0x1400053ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053b3  lea     rcx, [rbp+57h+var_78]; this
0x1400053b7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400053bc  mov     eax, ebx
0x1400053be  add     rsp, 88h
0x1400053c5  pop     r15
0x1400053c7  pop     r14
0x1400053c9  pop     r13
0x1400053cb  pop     r12
0x1400053cd  pop     rdi
0x1400053ce  pop     rsi
0x1400053cf  pop     rbx
0x1400053d0  pop     rbp
0x1400053d1  retn
0x1400053d2  mov     [rsi+r15*4], r13d
0x1400053d6  lea     rdx, [rbp+57h+arg_8]; unsigned __int8 *
0x1400053da  mov     rcx, [rbx+60h]
0x1400053de  mov     rcx, [rcx+r14*8+18h]; unsigned __int16 *
0x1400053e3  call    ?SxIsShadowCopyScoped@@YAJPEBGPEAE@Z; SxIsShadowCopyScoped(ushort const *,uchar *)
0x1400053e8  mov     [rbp+57h+var_78], eax
0x1400053eb  test    eax, eax
0x1400053ed  mov     eax, 2F3h
0x1400053f2  js      loc_1400051A9
0x1400053f8  mov     [rbp+57h+var_74], ax
0x1400053fc  cmp     [rbp+57h+arg_8], r12b
0x140005400  jz      short loc_14000540C
0x140005402  mov     eax, 2F7h
0x140005407  jmp     loc_140005368
0x14000540c  mov     rcx, [rbp+57h+var_90]
0x140005410  mov     r9, rsi
0x140005413  mov     r8d, [rbx+58h]
0x140005417  mov     rdx, rbx
0x14000541a  mov     rax, [rcx]
0x14000541d  mov     rax, [rax+48h]
0x140005421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005426  mov     [rbp+57h+var_78], eax
0x140005429  test    eax, eax
0x14000542b  mov     eax, 2FFh
0x140005430  jns     loc_14000536C
0x140005436  jmp     loc_1400051A9
```
