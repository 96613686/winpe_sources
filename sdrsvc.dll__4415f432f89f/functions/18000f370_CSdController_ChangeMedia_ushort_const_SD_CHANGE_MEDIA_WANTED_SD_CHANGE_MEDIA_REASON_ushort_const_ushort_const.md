# CSdController::ChangeMedia(ushort const *,_SD_CHANGE_MEDIA_WANTED,_SD_CHANGE_MEDIA_REASON,ushort const *,ushort const *)

- ea: `0x18000f370`
- end: `0x18000f7bd`
- name: `?ChangeMedia@CSdController@@UEAAJPEBGW4_SD_CHANGE_MEDIA_WANTED@@W4_SD_CHANGE_MEDIA_REASON@@00@Z`
- size: `1101`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000f370`
- `0x180011cb8`
- `0x1800138bc`
- `0x180014d1c`
- `0x18001586c`
- `0x180015974`
- `0x18001a448`
- `0x18001a654`
- `0x1800216e6`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f426`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f426`

## pseudocode

```c
__int64 __fastcall CSdController::ChangeMedia(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  GUID v7; // xmm6
  struct ISdCallback2 *v8; // rbx
  struct ISdCallback2 *v9; // r15
  struct AsyncISdCallback2 *v10; // r14
  HRESULT v11; // esi
  __int16 v12; // ax
  CSdController *v13; // r13
  unsigned int v14; // r12d
  __int64 v15; // rax
  int v16; // eax
  struct IUnknown *v17; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v19; // rax
  struct ISdCallback2 *v20; // rcx
  int v21; // edi
  int v22; // eax
  bool v23; // sf
  int v24; // eax
  struct AsyncISdCallback2 *v26; // [rsp+48h] [rbp-C0h] BYREF
  struct IUnknown *v27; // [rsp+50h] [rbp-B8h] BYREF
  int v28; // [rsp+58h] [rbp-B0h] BYREF
  __int16 v29; // [rsp+5Ch] [rbp-ACh]
  __int16 v30; // [rsp+5Eh] [rbp-AAh]
  struct ISdCallback2 *v31; // [rsp+90h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v33; // [rsp+A0h] [rbp-68h]
  unsigned int v34; // [rsp+A4h] [rbp-64h]
  struct _GUID v35; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-50h]
  __int64 v37; // [rsp+C0h] [rbp-48h]
  __int64 v38; // [rsp+C8h] [rbp-40h]
  GUID Buf2; // [rsp+D8h] [rbp-30h] BYREF
  GUID Buf1; // [rsp+E8h] [rbp-20h] BYREF

  v37 = a5;
  v33 = a4;
  v34 = a3;
  v38 = a2;
  v36 = a6;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "CSdController::ChangeMedia", 0xC39u, 1u);
  v7 = GUID_NULL;
  v8 = 0;
  v9 = 0;
  v27 = 0;
  v10 = 0;
  Buf2 = GUID_NULL;
  v31 = 0;
  v26 = 0;
  ppv = 0;
  Buf1 = GUID_NULL;
  v11 = CoCreateInstance(&CLSID_CSdWhcNotifier, 0, 1u, &IID_ISdWhcNotifier, &ppv);
  v28 = v11;
  v12 = 3145;
  if ( v11 >= 0 )
  {
    v29 = 3145;
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 10);
    v28 = v11;
    v12 = 3147;
    if ( v11 >= 0 )
    {
      v29 = 3147;
      v13 = (CSdController *)(a1 - 8);
      v14 = 0;
      while ( 1 )
      {
        if ( v9 )
        {
          v15 = *(_QWORD *)v9;
          v31 = 0;
          (*(void (__fastcall **)(struct ISdCallback2 *))(v15 + 16))(v9);
        }
        v28 = CSdController::_WaitForUI(v13, &v31, &Buf1);
        v11 = v28;
        if ( v28 < 0 )
        {
          v9 = v31;
          v30 = 3152;
          goto LABEL_39;
        }
        v29 = 3152;
        v16 = memcmp_0(&Buf1, &Buf2, 0x10u);
        v9 = v31;
        if ( v16 )
        {
          v17 = v27;
          if ( v27 )
          {
            lpVtbl = v27->lpVtbl;
            v27 = 0;
            ((void (__fastcall *)(struct IUnknown *))lpVtbl->Release)(v17);
          }
          if ( v10 )
          {
            v19 = *(_QWORD *)v10;
            v26 = 0;
            (*(void (__fastcall **)(struct AsyncISdCallback2 *))(v19 + 16))(v10);
          }
          if ( v8 )
          {
            v20 = v8;
            v8 = 0;
            (*(void (__fastcall **)(struct ISdCallback2 *))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( v9 )
          {
            v8 = v9;
            (*(void (__fastcall **)(struct ISdCallback2 *))(*(_QWORD *)v9 + 8LL))(v9);
          }
          v7 = Buf1;
          Buf2 = Buf1;
          v21 = CSdController::_GetAsyncCallObject((CSdController *)v17, v8, &v26, (struct ISynchronize **)&v27);
          if ( !(unsigned int)IsRPCError(v21) )
          {
            v35 = v7;
            v22 = CSdController::_ReleaseUI(v13, &v35);
            v10 = v26;
            v11 = v22;
            v28 = v22;
            v23 = v22 < 0;
            v12 = 3177;
LABEL_28:
            if ( v23 )
              break;
            v29 = v12;
            ++v14;
            goto LABEL_30;
          }
          v10 = v26;
          v11 = v21;
          v28 = v21;
          v12 = 3182;
          if ( v21 < 0 )
            break;
          v29 = 3182;
          v21 = (*(__int64 (__fastcall **)(struct AsyncISdCallback2 *, __int64, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)v26 + 24LL))(
                  v26,
                  v38,
                  v34,
                  v33,
                  v37,
                  v36);
          if ( !(unsigned int)IsRPCError(v21) )
          {
            v35 = v7;
            v11 = CSdController::_ReleaseUI(v13, &v35);
            v28 = v11;
            v23 = v11 < 0;
            v12 = 3191;
            goto LABEL_28;
          }
          v28 = v21;
          if ( v21 < 0 )
          {
            v30 = 3195;
            v11 = v21;
            goto LABEL_39;
          }
          v29 = 3195;
          ConfigureProxySecurityBlanket(v27);
        }
        v24 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64))v27->lpVtbl[1].QueryInterface)(v27, 1, 5000);
        v21 = v24;
        if ( v24 != -2147417835 )
        {
          v11 = v24;
          v28 = v24;
          v23 = v24 < 0;
          v12 = 3214;
          if ( v23 )
            break;
          v29 = 3214;
          v21 = (*(__int64 (__fastcall **)(struct AsyncISdCallback2 *))(*(_QWORD *)v10 + 32LL))(v10);
          if ( (unsigned int)IsRPCError(v21) )
          {
            v28 = v21;
            v11 = v21;
            if ( v21 < 0 )
            {
              v12 = 3227;
              break;
            }
            v12 = 3228;
            goto LABEL_37;
          }
          v35 = v7;
          v11 = CSdController::_ReleaseUI(v13, &v35);
          v28 = v11;
          v23 = v11 < 0;
          v12 = 3219;
          goto LABEL_28;
        }
LABEL_30:
        if ( v14 >= 2 )
        {
          v28 = v21;
          v12 = 3234;
          v11 = v21;
          if ( v21 < 0 )
            break;
LABEL_37:
          v29 = v12;
          goto LABEL_39;
        }
      }
    }
  }
  v30 = v12;
LABEL_39:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 11);
    v11 = v28;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( v27 )
    ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
  if ( v10 )
    (*(void (__fastcall **)(struct AsyncISdCallback2 *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v8 )
    (*(void (__fastcall **)(struct ISdCallback2 *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 )
    (*(void (__fastcall **)(struct ISdCallback2 *))(*(_QWORD *)v9 + 16LL))(v9);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f370  mov     rax, rsp
0x18000f373  push    rbp
0x18000f374  push    rbx
0x18000f375  push    rsi
0x18000f376  push    rdi
0x18000f377  push    r12
0x18000f379  push    r13
0x18000f37b  push    r14
0x18000f37d  push    r15
0x18000f37f  lea     rbp, [rax-58h]
0x18000f383  sub     rsp, 118h
0x18000f38a  movaps  xmmword ptr [rax-58h], xmm6
0x18000f38e  mov     rax, cs:__security_cookie
0x18000f395  xor     rax, rsp
0x18000f398  mov     [rbp+50h+var_60], rax
0x18000f39c  mov     rax, [rbp+50h+arg_20]
0x18000f3a3  mov     rdi, rcx
0x18000f3a6  mov     [rbp+50h+var_98], rax
0x18000f3aa  lea     rcx, [rsp+150h+var_100]; this
0x18000f3af  mov     rax, [rbp+50h+arg_28]
0x18000f3b6  mov     esi, 1
0x18000f3bb  mov     [rbp+50h+var_B8], r9d
0x18000f3bf  mov     r9d, esi; unsigned __int16
0x18000f3c2  mov     [rbp+50h+var_B4], r8d
0x18000f3c6  mov     r8d, 0C39h; unsigned __int16
0x18000f3cc  mov     [rbp+50h+var_90], rdx
0x18000f3d0  lea     rdx, aCsdcontrollerC; "CSdController::ChangeMedia"
0x18000f3d7  mov     [rbp+50h+var_A0], rax
0x18000f3db  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f3e0  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18000f3e7  xor     ebx, ebx
0x18000f3e9  lea     rax, [rbp+50h+var_C0]
0x18000f3ed  xor     r15d, r15d
0x18000f3f0  mov     [rsp+150h+var_108], rbx
0x18000f3f5  xor     r14d, r14d
0x18000f3f8  movaps  [rbp+50h+Buf2], xmm6
0x18000f3fc  lea     r9, IID_ISdWhcNotifier; riid
0x18000f403  mov     [rbp+50h+var_C8], r15
0x18000f407  mov     r8d, esi; dwClsContext
0x18000f40a  mov     [rsp+150h+var_110], r14
0x18000f40f  xor     edx, edx; pUnkOuter
0x18000f411  mov     [rbp+50h+var_C0], rbx
0x18000f415  lea     rcx, CLSID_CSdWhcNotifier; rclsid
0x18000f41c  mov     [rsp+150h+ppv], rax; ppv
0x18000f421  movdqu  [rbp+50h+Buf1], xmm6
0x18000f426  call    cs:__imp_CoCreateInstance
0x18000f42c  mov     esi, eax
0x18000f42e  mov     [rsp+150h+var_100], eax
0x18000f432  test    eax, eax
0x18000f434  mov     eax, 0C49h
0x18000f439  jns     short loc_18000F445
0x18000f43b  mov     [rsp+150h+var_FA], ax
0x18000f440  jmp     loc_18000F704
0x18000f445  mov     rcx, [rbp+50h+var_C0]
0x18000f449  mov     edx, 0Ah
0x18000f44e  mov     [rsp+150h+var_FC], ax
0x18000f453  mov     rax, [rcx]
0x18000f456  mov     rax, [rax+18h]
0x18000f45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f45f  mov     esi, eax
0x18000f461  mov     [rsp+150h+var_100], eax
0x18000f465  test    eax, eax
0x18000f467  mov     eax, 0C4Bh
0x18000f46c  js      short loc_18000F43B
0x18000f46e  mov     [rsp+150h+var_FC], ax
0x18000f473  lea     r13, [rdi-8]
0x18000f477  xor     r12d, r12d
0x18000f47a  mov     edi, 0C50h
0x18000f47f  test    r15, r15
0x18000f482  jz      short loc_18000F49B
0x18000f484  mov     rax, [r15]
0x18000f487  mov     rcx, r15
0x18000f48a  mov     [rbp+50h+var_C8], 0
0x18000f492  mov     rax, [rax+10h]
0x18000f496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f49b  lea     r8, [rbp+50h+Buf1]; struct _GUID *
0x18000f49f  mov     rcx, r13; this
0x18000f4a2  lea     rdx, [rbp+50h+var_C8]; struct ISdCallback2 **
0x18000f4a6  call    ?_WaitForUI@CSdController@@AEAAJPEAPEAUISdCallback2@@PEAU_GUID@@@Z; CSdController::_WaitForUI(ISdCallback2 * *,_GUID *)
0x18000f4ab  mov     [rsp+150h+var_100], eax
0x18000f4af  mov     esi, eax
0x18000f4b1  test    eax, eax
0x18000f4b3  js      loc_18000F6FB
0x18000f4b9  mov     r8d, 10h; Size
0x18000f4bf  mov     [rsp+150h+var_FC], di
0x18000f4c4  lea     rdx, [rbp+50h+Buf2]; Buf2
0x18000f4c8  lea     rcx, [rbp+50h+Buf1]; Buf1
0x18000f4cc  call    memcmp_0
0x18000f4d1  mov     r15, [rbp+50h+var_C8]
0x18000f4d5  test    eax, eax
0x18000f4d7  jz      loc_18000F62F
0x18000f4dd  mov     rcx, [rsp+150h+var_108]
0x18000f4e2  test    rcx, rcx
0x18000f4e5  jz      short loc_18000F4FC
0x18000f4e7  mov     rax, [rcx]
0x18000f4ea  mov     [rsp+150h+var_108], 0
0x18000f4f3  mov     rax, [rax+10h]
0x18000f4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4fc  test    r14, r14
0x18000f4ff  jz      short loc_18000F519
0x18000f501  mov     rax, [r14]
0x18000f504  mov     rcx, r14
0x18000f507  mov     [rsp+150h+var_110], 0
0x18000f510  mov     rax, [rax+10h]
0x18000f514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f519  test    rbx, rbx
0x18000f51c  jz      short loc_18000F52F
0x18000f51e  mov     rcx, rbx
0x18000f521  xor     ebx, ebx
0x18000f523  mov     rax, [rcx]
0x18000f526  mov     rax, [rax+10h]
0x18000f52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f52f  test    r15, r15
0x18000f532  jz      short loc_18000F546
0x18000f534  mov     rax, [r15]
0x18000f537  mov     rbx, r15
0x18000f53a  mov     rcx, rbx
0x18000f53d  mov     rax, [rax+8]
0x18000f541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f546  movaps  xmm6, [rbp+50h+Buf1]
0x18000f54a  lea     r9, [rsp+150h+var_108]; struct ISynchronize **
0x18000f54f  lea     r8, [rsp+150h+var_110]; struct AsyncISdCallback2 **
0x18000f554  movaps  [rbp+50h+Buf2], xmm6
0x18000f558  mov     rdx, rbx; struct ISdCallback2 *
0x18000f55b  call    ?_GetAsyncCallObject@CSdController@@AEAAJPEAUISdCallback2@@PEAPEAUAsyncISdCallback2@@PEAPEAUISynchronize@@@Z; CSdController::_GetAsyncCallObject(ISdCallback2 *,AsyncISdCallback2 * *,ISynchronize * *)
0x18000f560  mov     ecx, eax; int
0x18000f562  mov     edi, eax
0x18000f564  call    ?IsRPCError@@YAJJ@Z; IsRPCError(long)
0x18000f569  test    eax, eax
0x18000f56b  jnz     short loc_18000F595
0x18000f56d  lea     rdx, [rbp+50h+var_B0]; struct _GUID
0x18000f571  movdqa  xmmword ptr [rbp+50h+var_B0.Data1], xmm6
0x18000f576  mov     rcx, r13; this
0x18000f579  call    ?_ReleaseUI@CSdController@@AEAAJU_GUID@@@Z; CSdController::_ReleaseUI(_GUID)
0x18000f57e  mov     r14, [rsp+150h+var_110]
0x18000f583  mov     esi, eax
0x18000f585  mov     [rsp+150h+var_100], eax
0x18000f589  test    eax, eax
0x18000f58b  mov     eax, 0C69h
0x18000f590  jmp     loc_18000F6A6
0x18000f595  mov     r14, [rsp+150h+var_110]
0x18000f59a  mov     esi, edi
0x18000f59c  mov     [rsp+150h+var_100], edi
0x18000f5a0  mov     eax, 0C6Eh
0x18000f5a5  test    edi, edi
0x18000f5a7  js      loc_18000F43B
0x18000f5ad  mov     rcx, [rbp+50h+var_A0]
0x18000f5b1  mov     r9d, [rbp+50h+var_B8]
0x18000f5b5  mov     r8d, [rbp+50h+var_B4]
0x18000f5b9  mov     rdx, [rbp+50h+var_90]
0x18000f5bd  mov     [rsp+28h], rcx
0x18000f5c2  mov     rcx, [rbp+50h+var_98]
0x18000f5c6  mov     [rsp+150h+var_FC], ax
0x18000f5cb  mov     rax, [r14]
0x18000f5ce  mov     [rsp+150h+ppv], rcx
0x18000f5d3  mov     rcx, r14
0x18000f5d6  mov     rax, [rax+18h]
0x18000f5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5df  mov     ecx, eax; int
0x18000f5e1  mov     edi, eax
0x18000f5e3  call    ?IsRPCError@@YAJJ@Z; IsRPCError(long)
0x18000f5e8  test    eax, eax
0x18000f5ea  jnz     short loc_18000F60F
0x18000f5ec  lea     rdx, [rbp+50h+var_B0]; struct _GUID
0x18000f5f0  movdqa  xmmword ptr [rbp+50h+var_B0.Data1], xmm6
0x18000f5f5  mov     rcx, r13; this
0x18000f5f8  call    ?_ReleaseUI@CSdController@@AEAAJU_GUID@@@Z; CSdController::_ReleaseUI(_GUID)
0x18000f5fd  mov     esi, eax
0x18000f5ff  mov     [rsp+150h+var_100], eax
0x18000f603  test    eax, eax
0x18000f605  mov     eax, 0C77h
0x18000f60a  jmp     loc_18000F6A6
0x18000f60f  mov     [rsp+150h+var_100], edi
0x18000f613  mov     eax, 0C7Bh
0x18000f618  test    edi, edi
0x18000f61a  js      loc_18000F6D2
0x18000f620  mov     rcx, [rsp+150h+var_108]; struct IUnknown *
0x18000f625  mov     [rsp+150h+var_FC], ax
0x18000f62a  call    ?ConfigureProxySecurityBlanket@@YAJPEAUIUnknown@@@Z; ConfigureProxySecurityBlanket(IUnknown *)
0x18000f62f  mov     rcx, [rsp+150h+var_108]
0x18000f634  mov     edx, 1
0x18000f639  mov     r8d, 1388h
0x18000f63f  mov     rax, [rcx]
0x18000f642  mov     rax, [rax+18h]
0x18000f646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64b  mov     edi, eax
0x18000f64d  cmp     eax, 80010115h
0x18000f652  jz      short loc_18000F6B4
0x18000f654  mov     esi, eax
0x18000f656  mov     [rsp+150h+var_100], eax
0x18000f65a  test    eax, eax
0x18000f65c  mov     eax, 0C8Eh
0x18000f661  js      loc_18000F43B
0x18000f667  mov     [rsp+150h+var_FC], ax
0x18000f66c  mov     rcx, r14
0x18000f66f  mov     rax, [r14]
0x18000f672  mov     rax, [rax+20h]
0x18000f676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f67b  mov     ecx, eax; int
0x18000f67d  mov     edi, eax
0x18000f67f  call    ?IsRPCError@@YAJJ@Z; IsRPCError(long)
0x18000f684  test    eax, eax
0x18000f686  jnz     short loc_18000F6DB
0x18000f688  lea     rdx, [rbp+50h+var_B0]; struct _GUID
0x18000f68c  movdqa  xmmword ptr [rbp+50h+var_B0.Data1], xmm6
0x18000f691  mov     rcx, r13; this
0x18000f694  call    ?_ReleaseUI@CSdController@@AEAAJU_GUID@@@Z; CSdController::_ReleaseUI(_GUID)
0x18000f699  mov     esi, eax
0x18000f69b  mov     [rsp+150h+var_100], eax
0x18000f69f  test    eax, eax
0x18000f6a1  mov     eax, 0C93h
0x18000f6a6  js      loc_18000F43B
0x18000f6ac  mov     [rsp+150h+var_FC], ax
0x18000f6b1  inc     r12d
0x18000f6b4  cmp     r12d, 2
0x18000f6b8  jb      loc_18000F47A
0x18000f6be  mov     [rsp+150h+var_100], edi
0x18000f6c2  mov     eax, 0CA2h
0x18000f6c7  mov     esi, edi
0x18000f6c9  test    edi, edi
0x18000f6cb  jns     short loc_18000F6F4
0x18000f6cd  jmp     loc_18000F43B
0x18000f6d2  mov     [rsp+150h+var_FA], ax
0x18000f6d7  mov     esi, edi
0x18000f6d9  jmp     short loc_18000F704
0x18000f6db  mov     [rsp+150h+var_100], edi
0x18000f6df  mov     esi, edi
0x18000f6e1  test    edi, edi
0x18000f6e3  jns     short loc_18000F6EF
0x18000f6e5  mov     eax, 0C9Bh
0x18000f6ea  jmp     loc_18000F43B
0x18000f6ef  mov     eax, 0C9Ch
0x18000f6f4  mov     [rsp+150h+var_FC], ax
0x18000f6f9  jmp     short loc_18000F704
0x18000f6fb  mov     r15, [rbp+50h+var_C8]
0x18000f6ff  mov     [rsp+150h+var_FA], di
0x18000f704  mov     rcx, [rbp+50h+var_C0]
0x18000f708  test    rcx, rcx
0x18000f70b  jz      short loc_18000F737
0x18000f70d  mov     rax, [rcx]
0x18000f710  mov     edx, 0Bh
0x18000f715  mov     rax, [rax+18h]
0x18000f719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f71e  mov     rcx, [rbp+50h+var_C0]
0x18000f722  mov     esi, [rsp+150h+var_100]
0x18000f726  test    rcx, rcx
0x18000f729  jz      short loc_18000F737
0x18000f72b  mov     rax, [rcx]
0x18000f72e  mov     rax, [rax+10h]
0x18000f732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f737  mov     rcx, [rsp+150h+var_108]
0x18000f73c  test    rcx, rcx
0x18000f73f  jz      short loc_18000F74D
0x18000f741  mov     rax, [rcx]
0x18000f744  mov     rax, [rax+10h]
0x18000f748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f74d  test    r14, r14
0x18000f750  jz      short loc_18000F761
0x18000f752  mov     rax, [r14]
0x18000f755  mov     rcx, r14
0x18000f758  mov     rax, [rax+10h]
0x18000f75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f761  test    rbx, rbx
0x18000f764  jz      short loc_18000F775
0x18000f766  mov     rax, [rbx]
0x18000f769  mov     rcx, rbx
0x18000f76c  mov     rax, [rax+10h]
0x18000f770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f775  test    r15, r15
0x18000f778  jz      short loc_18000F789
0x18000f77a  mov     rcx, [r15]
0x18000f77d  mov     rax, [rcx+10h]
0x18000f781  mov     rcx, r15
0x18000f784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f789  lea     rcx, [rsp+150h+var_100]; this
0x18000f78e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f793  mov     eax, esi
0x18000f795  mov     rcx, [rbp+50h+var_60]
0x18000f799  xor     rcx, rsp; StackCookie
0x18000f79c  call    __security_check_cookie
0x18000f7a1  movaps  xmm6, [rsp+150h+var_58+8]
0x18000f7a9  add     rsp, 118h
0x18000f7b0  pop     r15
0x18000f7b2  pop     r14
0x18000f7b4  pop     r13
0x18000f7b6  pop     r12
0x18000f7b8  pop     rdi
0x18000f7b9  pop     rsi
0x18000f7ba  pop     rbx
0x18000f7bb  pop     rbp
0x18000f7bc  retn
```
