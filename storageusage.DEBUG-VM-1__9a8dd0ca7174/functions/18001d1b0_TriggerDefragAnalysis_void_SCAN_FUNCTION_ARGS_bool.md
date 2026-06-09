# TriggerDefragAnalysis(void *,SCAN_FUNCTION_ARGS,bool &)

- ea: `0x18001d1b0`
- end: `0x18001d600`
- name: `?TriggerDefragAnalysis@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z`
- size: `1104`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001010`
- `0x1800010b0`
- `0x1800050f0`
- `0x180013ae4`
- `0x180017bc0`
- `0x18001d1b0`
- `0x18001f178`
- `0x18001f76c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d1f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d544`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d1f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d544`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001d23d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001d23d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d44f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d469`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d44f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d469`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d504`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d300`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d300`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TriggerDefragAnalysis(void *a1)
{
  ULONGLONG TickCount64; // r15
  HRESULT v3; // edi
  unsigned int v4; // ebx
  __int64 v5; // r14
  char *v6; // rcx
  unsigned int i; // esi
  __int64 v8; // rbx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  GUID v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  GUID v16; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+80h] [rbp-80h] BYREF
  char v18; // [rsp+84h] [rbp-7Ch]
  GUID ActivityId; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v20[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v21; // [rsp+D0h] [rbp-30h]
  __int64 v22; // [rsp+D8h] [rbp-28h]
  GUID *v23; // [rsp+E0h] [rbp-20h]
  __int64 v24; // [rsp+E8h] [rbp-18h]
  __int64 *v25; // [rsp+F0h] [rbp-10h]
  __int64 v26; // [rsp+F8h] [rbp-8h]

  v16 = GUID_NULL;
  ppv = 0;
  pv = 0;
  v11 = 0;
  TickCount64 = GetTickCount64();
  v17 = 0;
  v18 = 0;
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v17 = 1;
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
  {
    v13 = 0x1000000;
    v21 = &v13;
    v22 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180040010, byte_180037ECB, &ActivityId, 0, 3, v20);
  }
  if ( IsTaskCancelled(a1) )
  {
LABEL_22:
    v3 = -2147023673;
    goto LABEL_23;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  v3 = CoCreateInstance(&CLSID_CDefragEngine, 0, 4u, &IID_IDefragEngine, &ppv);
  if ( v3 < 0 )
    goto LABEL_23;
  if ( !ppv )
  {
    v3 = -2147467259;
    goto LABEL_23;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)ppv + 128LL))(ppv, 0, &v11, &pv);
  if ( v3 >= 0 )
  {
    if ( !v11 )
    {
      v3 = -1996488697;
      goto LABEL_23;
    }
    v4 = 0;
    while ( !IsTaskCancelled(a1) )
    {
      v5 = 208LL * v4;
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, _QWORD, GUID *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             *(_QWORD *)((char *)pv + v5 + 112),
             0,
             &v16) >= 0 )
      {
        v14 = v16;
        (*(void (__fastcall **)(LPVOID, GUID *))(*(_QWORD *)ppv + 168LL))(ppv, &v14);
        if ( (*(int (__fastcall **)(LPVOID, _QWORD, _QWORD, GUID *))(*(_QWORD *)ppv + 120LL))(
               ppv,
               *(_QWORD *)((char *)pv + v5 + 112),
               0,
               &v16) >= 0 )
        {
          v14 = v16;
          (*(void (__fastcall **)(LPVOID, GUID *))(*(_QWORD *)ppv + 168LL))(ppv, &v14);
        }
      }
      if ( ++v4 >= v11 )
        goto LABEL_23;
    }
    goto LABEL_22;
  }
LABEL_23:
  v6 = (char *)pv;
  if ( pv )
  {
    for ( i = 0; i < v11; v6 = (char *)pv )
    {
      v8 = 208LL * i;
      CoTaskMemFree(*(LPVOID *)&v6[v8 + 104]);
      *(_QWORD *)((char *)pv + v8 + 104) = 0;
      CoTaskMemFree(*(LPVOID *)((char *)pv + v8 + 120));
      *(_QWORD *)((char *)pv + v8 + 120) = 0;
      CoTaskMemFree(*(LPVOID *)((char *)pv + v8 + 128));
      *(_QWORD *)((char *)pv + v8 + 128) = 0;
      CoTaskMemFree(*(LPVOID *)((char *)pv + v8 + 144));
      *(_QWORD *)((char *)pv + v8 + 144) = 0;
      CoTaskMemFree(*(LPVOID *)((char *)pv + v8 + 136));
      *(_QWORD *)((char *)pv + v8 + 136) = 0;
      CoTaskMemFree(*(LPVOID *)((char *)pv + v8 + 112));
      *(_QWORD *)((char *)pv + v8 + 112) = 0;
      ++i;
    }
    CoTaskMemFree(v6);
    pv = 0;
  }
  v17 = 2;
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
  {
    v15 = 0x1000000;
    *(_QWORD *)&v14.Data1 = GetTickCount64() - TickCount64;
    LODWORD(v13) = v3;
    v25 = &v15;
    v26 = 8;
    v23 = &v14;
    v24 = 8;
    v21 = &v13;
    v22 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180040010, byte_1800376D3, &ActivityId, 0, 5, v20);
  }
  if ( v3 == -1996488698 )
  {
    v3 = -2147023673;
  }
  else if ( v3 != 1223 )
  {
    v3 = 0;
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageUsageProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageUsageProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v17);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001d1b0  push    rbp
0x18001d1b2  push    rbx
0x18001d1b3  push    rsi
0x18001d1b4  push    rdi
0x18001d1b5  push    r12
0x18001d1b7  push    r13
0x18001d1b9  push    r14
0x18001d1bb  push    r15
0x18001d1bd  lea     rbp, [rsp-18h]
0x18001d1c2  sub     rsp, 118h
0x18001d1c9  mov     rax, cs:__security_cookie
0x18001d1d0  xor     rax, rsp
0x18001d1d3  mov     [rbp+50h+var_50], rax
0x18001d1d7  mov     rsi, rcx
0x18001d1da  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001d1e1  movdqu  [rsp+150h+var_E0], xmm0
0x18001d1e7  xor     r12d, r12d
0x18001d1ea  mov     [rsp+150h+var_110], r12
0x18001d1ef  mov     [rsp+150h+pv], r12
0x18001d1f4  mov     [rsp+150h+var_118], r12d
0x18001d1f9  call    cs:__imp_GetTickCount64
0x18001d1ff  mov     r15, rax
0x18001d202  mov     [rbp+50h+var_D0], r12d
0x18001d206  mov     [rbp+50h+var_CC], r12b
0x18001d20a  mov     ecx, cs:dword_180040010
0x18001d210  lea     ebx, [r12+3]
0x18001d215  lea     r13, dword_180040010
0x18001d21c  cmp     ecx, 5
0x18001d21f  jbe     short loc_18001D245
0x18001d221  mov     rdx, 400000000000h
0x18001d22b  mov     rcx, r13
0x18001d22e  call    _tlgKeywordOn
0x18001d233  test    al, al
0x18001d235  jz      short loc_18001D245
0x18001d237  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x18001d23b  mov     ecx, ebx; ControlCode
0x18001d23d  call    cs:__imp_EventActivityIdControl
0x18001d243  jmp     short loc_18001D24C
0x18001d245  xorps   xmm0, xmm0
0x18001d248  movups  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x18001d24c  mov     [rbp+50h+var_D0], 1
0x18001d253  mov     eax, cs:dword_180040010
0x18001d259  cmp     eax, 5
0x18001d25c  jbe     short loc_18001D2C8
0x18001d25e  mov     rdx, 400000000000h
0x18001d268  mov     rcx, r13
0x18001d26b  call    _tlgKeywordOn
0x18001d270  test    al, al
0x18001d272  jz      short loc_18001D2C8
0x18001d274  mov     [rsp+150h+var_108], 1000000h
0x18001d27d  cmp     [rbp+50h+var_CC], r12b
0x18001d281  jz      short loc_18001D294
0x18001d283  lea     rcx, [rbp+50h+var_B8]; struct _GUID *
0x18001d287  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18001d28c  test    al, al
0x18001d28e  lea     r9, [rbp+50h+var_B8]
0x18001d292  jz      short loc_18001D297
0x18001d294  mov     r9, r12
0x18001d297  lea     rax, [rsp+150h+var_108]
0x18001d29c  mov     [rbp+50h+var_80], rax
0x18001d2a0  mov     [rbp+50h+var_78], 8
0x18001d2a8  lea     rax, [rbp+50h+var_A0]
0x18001d2ac  mov     [rsp+150h+var_128], rax
0x18001d2b1  mov     dword ptr [rsp+150h+ppv], ebx
0x18001d2b5  lea     r8, [rbp+50h+ActivityId]
0x18001d2b9  lea     rdx, byte_180037ECB
0x18001d2c0  mov     rcx, r13
0x18001d2c3  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d2c8  mov     rcx, rsi; void *
0x18001d2cb  call    ?IsTaskCancelled@@YA_NPEAX@Z; IsTaskCancelled(void *)
0x18001d2d0  test    al, al
0x18001d2d2  jnz     loc_18001D420
0x18001d2d8  lea     rcx, [rsp+150h+var_110]
0x18001d2dd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d2e2  lea     rax, [rsp+150h+var_110]
0x18001d2e7  mov     [rsp+150h+ppv], rax; ppv
0x18001d2ec  lea     r9, IID_IDefragEngine; riid
0x18001d2f3  xor     edx, edx; pUnkOuter
0x18001d2f5  lea     r8d, [rdx+4]; dwClsContext
0x18001d2f9  lea     rcx, CLSID_CDefragEngine; rclsid
0x18001d300  call    cs:__imp_CoCreateInstance
0x18001d306  mov     edi, eax
0x18001d308  test    eax, eax
0x18001d30a  js      loc_18001D425
0x18001d310  mov     rcx, [rsp+150h+var_110]
0x18001d315  test    rcx, rcx
0x18001d318  jnz     short loc_18001D324
0x18001d31a  mov     edi, 80004005h
0x18001d31f  jmp     loc_18001D425
0x18001d324  mov     rax, [rcx]
0x18001d327  lea     r9, [rsp+150h+pv]
0x18001d32c  lea     r8, [rsp+150h+var_118]
0x18001d331  xor     edx, edx
0x18001d333  mov     rax, [rax+80h]
0x18001d33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d33f  mov     edi, eax
0x18001d341  test    eax, eax
0x18001d343  js      loc_18001D425
0x18001d349  cmp     [rsp+150h+var_118], r12d
0x18001d34e  jnz     short loc_18001D35A
0x18001d350  mov     edi, 89000007h
0x18001d355  jmp     loc_18001D425
0x18001d35a  mov     ebx, r12d
0x18001d35d  jbe     loc_18001D425
0x18001d363  mov     rcx, rsi; void *
0x18001d366  call    ?IsTaskCancelled@@YA_NPEAX@Z; IsTaskCancelled(void *)
0x18001d36b  test    al, al
0x18001d36d  jnz     loc_18001D420
0x18001d373  mov     rcx, [rsp+150h+var_110]
0x18001d378  mov     eax, ebx
0x18001d37a  imul    r14, rax, 0D0h
0x18001d381  mov     rax, [rcx]
0x18001d384  lea     r9, [rsp+150h+var_E0]
0x18001d389  xor     r8d, r8d
0x18001d38c  mov     rdx, [rsp+150h+pv]
0x18001d391  mov     rdx, [r14+rdx+70h]
0x18001d396  mov     rax, [rax+18h]
0x18001d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d39f  test    eax, eax
0x18001d3a1  js      short loc_18001D412
0x18001d3a3  mov     rcx, [rsp+150h+var_110]
0x18001d3a8  movaps  xmm0, [rsp+150h+var_E0]
0x18001d3ad  movdqa  [rsp+150h+var_100], xmm0
0x18001d3b3  mov     rax, [rcx]
0x18001d3b6  lea     rdx, [rsp+150h+var_100]
0x18001d3bb  mov     rax, [rax+0A8h]
0x18001d3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c7  mov     rcx, [rsp+150h+var_110]
0x18001d3cc  mov     rax, [rcx]
0x18001d3cf  lea     r9, [rsp+150h+var_E0]
0x18001d3d4  xor     r8d, r8d
0x18001d3d7  mov     rdx, [rsp+150h+pv]
0x18001d3dc  mov     rdx, [r14+rdx+70h]
0x18001d3e1  mov     rax, [rax+78h]
0x18001d3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ea  test    eax, eax
0x18001d3ec  js      short loc_18001D412
0x18001d3ee  mov     rcx, [rsp+150h+var_110]
0x18001d3f3  movaps  xmm0, [rsp+150h+var_E0]
0x18001d3f8  movdqa  [rsp+150h+var_100], xmm0
0x18001d3fe  mov     rax, [rcx]
0x18001d401  lea     rdx, [rsp+150h+var_100]
0x18001d406  mov     rax, [rax+0A8h]
0x18001d40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d412  inc     ebx
0x18001d414  cmp     ebx, [rsp+150h+var_118]
0x18001d418  jb      loc_18001D363
0x18001d41e  jmp     short loc_18001D425
0x18001d420  mov     edi, 800704C7h
0x18001d425  mov     rcx, [rsp+150h+pv]
0x18001d42a  test    rcx, rcx
0x18001d42d  jz      loc_18001D50F
0x18001d433  mov     esi, r12d
0x18001d436  cmp     [rsp+150h+var_118], r12d
0x18001d43b  jbe     loc_18001D504
0x18001d441  mov     eax, esi
0x18001d443  imul    rbx, rax, 0D0h
0x18001d44a  mov     rcx, [rbx+rcx+68h]; pv
0x18001d44f  call    cs:__imp_CoTaskMemFree
0x18001d455  mov     rax, [rsp+150h+pv]
0x18001d45a  mov     [rbx+rax+68h], r12
0x18001d45f  mov     rcx, [rsp+150h+pv]
0x18001d464  mov     rcx, [rbx+rcx+78h]; pv
0x18001d469  call    cs:__imp_CoTaskMemFree
0x18001d46f  mov     rax, [rsp+150h+pv]
0x18001d474  mov     [rbx+rax+78h], r12
0x18001d479  mov     rcx, [rsp+150h+pv]
0x18001d47e  mov     rcx, [rbx+rcx+80h]; pv
0x18001d486  call    cs:__imp_CoTaskMemFree
0x18001d48c  mov     rax, [rsp+150h+pv]
0x18001d491  mov     [rbx+rax+80h], r12
0x18001d499  mov     rcx, [rsp+150h+pv]
0x18001d49e  mov     rcx, [rbx+rcx+90h]; pv
0x18001d4a6  call    cs:__imp_CoTaskMemFree
0x18001d4ac  mov     rax, [rsp+150h+pv]
0x18001d4b1  mov     [rbx+rax+90h], r12
0x18001d4b9  mov     rcx, [rsp+150h+pv]
0x18001d4be  mov     rcx, [rbx+rcx+88h]; pv
0x18001d4c6  call    cs:__imp_CoTaskMemFree
0x18001d4cc  mov     rax, [rsp+150h+pv]
0x18001d4d1  mov     [rbx+rax+88h], r12
0x18001d4d9  mov     rcx, [rsp+150h+pv]
0x18001d4de  mov     rcx, [rbx+rcx+70h]; pv
0x18001d4e3  call    cs:__imp_CoTaskMemFree
0x18001d4e9  mov     rax, [rsp+150h+pv]
0x18001d4ee  mov     [rbx+rax+70h], r12
0x18001d4f3  inc     esi
0x18001d4f5  mov     rcx, [rsp+150h+pv]; pv
0x18001d4fa  cmp     esi, [rsp+150h+var_118]
0x18001d4fe  jb      loc_18001D441
0x18001d504  call    cs:__imp_CoTaskMemFree
0x18001d50a  mov     [rsp+150h+pv], r12
0x18001d50f  mov     [rbp+50h+var_D0], 2
0x18001d516  mov     eax, cs:dword_180040010
0x18001d51c  cmp     eax, 5
0x18001d51f  jbe     loc_18001D5B0
0x18001d525  mov     rdx, 400000000000h
0x18001d52f  mov     rcx, r13
0x18001d532  call    _tlgKeywordOn
0x18001d537  test    al, al
0x18001d539  jz      short loc_18001D5B0
0x18001d53b  mov     [rsp+150h+var_F0], 1000000h
0x18001d544  call    cs:__imp_GetTickCount64
0x18001d54a  sub     rax, r15
0x18001d54d  mov     qword ptr [rsp+150h+var_100], rax
0x18001d552  mov     dword ptr [rsp+150h+var_108], edi
0x18001d556  lea     rax, [rsp+150h+var_F0]
0x18001d55b  mov     [rbp+50h+var_60], rax
0x18001d55f  mov     [rbp+50h+var_58], 8
0x18001d567  lea     rax, [rsp+150h+var_100]
0x18001d56c  mov     [rbp+50h+var_70], rax
0x18001d570  mov     [rbp+50h+var_68], 8
0x18001d578  lea     rax, [rsp+150h+var_108]
0x18001d57d  mov     [rbp+50h+var_80], rax
0x18001d581  mov     [rbp+50h+var_78], 4
0x18001d589  lea     rax, [rbp+50h+var_A0]
0x18001d58d  mov     [rsp+150h+var_128], rax
0x18001d592  mov     dword ptr [rsp+150h+ppv], 5
0x18001d59a  xor     r9d, r9d
0x18001d59d  lea     r8, [rbp+50h+ActivityId]
0x18001d5a1  lea     rdx, byte_1800376D3
0x18001d5a8  mov     rcx, r13
0x18001d5ab  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d5b0  cmp     edi, 89000006h
0x18001d5b6  jz      short loc_18001D5C5
0x18001d5b8  cmp     edi, 4C7h
0x18001d5be  jz      short loc_18001D5CA
0x18001d5c0  mov     edi, r12d
0x18001d5c3  jmp     short loc_18001D5CA
0x18001d5c5  mov     edi, 800704C7h
0x18001d5ca  lea     rcx, [rbp+50h+var_D0]
0x18001d5ce  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageUsageProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageUsageProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageUsageProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18001d5d3  nop
0x18001d5d4  lea     rcx, [rsp+150h+var_110]
0x18001d5d9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d5de  mov     eax, edi
0x18001d5e0  mov     rcx, [rbp+50h+var_50]
0x18001d5e4  xor     rcx, rsp; StackCookie
0x18001d5e7  call    __security_check_cookie
0x18001d5ec  add     rsp, 118h
0x18001d5f3  pop     r15
0x18001d5f5  pop     r14
0x18001d5f7  pop     r13
0x18001d5f9  pop     r12
0x18001d5fb  pop     rdi
0x18001d5fc  pop     rsi
0x18001d5fd  pop     rbx
0x18001d5fe  pop     rbp
0x18001d5ff  retn
```
