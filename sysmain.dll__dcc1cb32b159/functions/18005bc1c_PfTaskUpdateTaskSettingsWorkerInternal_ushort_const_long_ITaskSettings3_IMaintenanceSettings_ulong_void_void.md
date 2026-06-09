# PfTaskUpdateTaskSettingsWorkerInternal(ushort const *,long (*)(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *),void *)

- ea: `0x18005bc1c`
- end: `0x18005bfc4`
- name: `?PfTaskUpdateTaskSettingsWorkerInternal@@YAJPEBGP6AJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z4@Z`
- size: `936`
- prototype: `__int64 __fastcall(OLECHAR *psz, __int64 (__fastcall *)(__int64, __int64, int *, void *), void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005bbf0`

## callees

- `0x18005bc1c`
- `0x1800b7010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005bd2d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005bd48`
- `OLEAUT32!__imp_SysAllocString` at `0x18005bd2d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005bd48`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bed6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bee4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bed6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bee4`
- `OLEAUT32!__imp_VariantInit` at `0x18005bc7d`
- `OLEAUT32!__imp_VariantInit` at `0x18005bc7d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005bcb9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005bcb9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005bfa0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005bfa0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005bc87`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005bc87`

## pseudocode

```c
__int64 __fastcall PfTaskUpdateTaskSettingsWorkerInternal(
        OLECHAR *psz,
        __int64 (__fastcall *a2)(__int64, __int64, int *, void *),
        void *a3)
{
  HRESULT v6; // ebx
  int v7; // edi
  __int64 v8; // rax
  __int64 (__fastcall *v9)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  OLECHAR *v10; // r14
  OLECHAR *v11; // rsi
  __int64 (__fastcall *v12)(__int64, OLECHAR *, __int64, __int64, VARIANTARG *, VARIANTARG *, int, VARIANTARG *, __int64 *); // rax
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20; // [rsp+80h] [rbp-80h] BYREF
  __int64 v21; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v23; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v24; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v25; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v26; // [rsp+110h] [rbp+10h] BYREF
  IRecordInfo *pRecInfo; // [rsp+120h] [rbp+20h]
  int v28; // [rsp+178h] [rbp+78h] BYREF

  v28 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  ppv = 0;
  v16 = 0;
  v20 = 0;
  v21 = 0;
  v15 = 0;
  v19 = 0;
  v14 = 0;
  v18 = 0;
  VariantInit(&pvarg);
  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    if ( v6 >= 0 )
    {
      v26 = *(_OWORD *)&pvarg.vt;
      v8 = *(_QWORD *)ppv;
      pRecInfo = pvarg.pRecInfo;
      v23 = pvarg;
      v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v8 + 80);
      v24 = pvarg;
      v25 = pvarg;
      v6 = v9(ppv, &v25, &v24, &v23, &v26);
      if ( v6 >= 0 )
      {
        v10 = SysAllocString(L"\\Microsoft\\Windows\\Sysmain");
        if ( v10 )
        {
          v11 = SysAllocString(psz);
          if ( v11 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v10, &v16);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v16 + 104LL))(v16, v11, &v20);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 152LL))(v20, &v15);
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 88LL))(v15, &v19);
                  if ( v6 >= 0 )
                  {
                    v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
                           v19,
                           &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                           &v14);
                    if ( v6 >= 0 )
                    {
                      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 408LL))(v14, &v18);
                      if ( v6 >= 0 )
                      {
                        v6 = a2(v14, v18, &v28, a3);
                        if ( v6 >= 0 )
                        {
                          if ( !v28
                            || (v12 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, VARIANTARG *, VARIANTARG *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v16 + 136LL),
                                v25 = pvarg,
                                v24 = pvarg,
                                v23 = pvarg,
                                v6 = v12(v16, v11, v15, 4, &v23, &v24, 5, &v25, &v21),
                                v6 >= 0) )
                          {
                            v6 = 0;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
            v6 = -2147024882;
          }
          SysFreeString(v10);
          if ( v11 )
            SysFreeString(v11);
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v7 )
    CoUninitialize();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005bc1c  mov     [rsp-8+arg_0], rbx
0x18005bc21  mov     [rsp-8+arg_8], rsi
0x18005bc26  push    rbp
0x18005bc27  push    rdi
0x18005bc28  push    r12
0x18005bc2a  push    r14
0x18005bc2c  push    r15
0x18005bc2e  lea     rbp, [rsp-30h]
0x18005bc33  sub     rsp, 130h
0x18005bc3a  xor     eax, eax
0x18005bc3c  mov     rsi, rcx
0x18005bc3f  xorps   xmm0, xmm0
0x18005bc42  mov     qword ptr [rbp+50h+pvarg+10h], rax
0x18005bc46  lea     rcx, [rbp+50h+pvarg]; pvarg
0x18005bc4a  mov     [rbp+50h+arg_18], eax
0x18005bc4d  movups  xmmword ptr [rbp+50h+pvarg], xmm0
0x18005bc51  mov     [rsp+150h+var_E8], rax
0x18005bc56  mov     r15, r8
0x18005bc59  mov     [rsp+150h+var_F0], rax
0x18005bc5e  mov     r12, rdx
0x18005bc61  mov     [rbp+50h+var_D0], rax
0x18005bc65  mov     [rbp+50h+var_C8], rax
0x18005bc69  mov     [rsp+150h+var_F8], rax
0x18005bc6e  mov     [rsp+150h+var_D8], rax
0x18005bc73  mov     [rsp+150h+var_100], rax
0x18005bc78  mov     [rsp+150h+var_E0], rax
0x18005bc7d  call    cs:__imp_VariantInit
0x18005bc83  xor     edx, edx; dwCoInit
0x18005bc85  xor     ecx, ecx; pvReserved
0x18005bc87  call    cs:__imp_CoInitializeEx
0x18005bc8d  mov     ebx, eax
0x18005bc8f  test    eax, eax
0x18005bc91  js      loc_18005BEEC
0x18005bc97  lea     rax, [rsp+150h+var_E8]
0x18005bc9c  mov     edi, 1
0x18005bca1  mov     r8d, edi; dwClsContext
0x18005bca4  mov     [rsp+150h+ppv], rax; ppv
0x18005bca9  lea     r9, IID_ITaskService; riid
0x18005bcb0  xor     edx, edx; pUnkOuter
0x18005bcb2  lea     rcx, CLSID_TaskScheduler; rclsid
0x18005bcb9  call    cs:__imp_CoCreateInstance
0x18005bcbf  mov     ebx, eax
0x18005bcc1  test    eax, eax
0x18005bcc3  js      loc_18005BEEE
0x18005bcc9  movups  xmm1, xmmword ptr [rbp+50h+pvarg]
0x18005bccd  lea     rdx, [rbp+50h+var_40]
0x18005bcd1  mov     rcx, [rsp+150h+var_E8]
0x18005bcd6  movsd   xmm0, qword ptr [rbp+50h+pvarg+10h]
0x18005bcdb  lea     r9, [rbp+50h+var_A0]
0x18005bcdf  mov     [rsp+150h+ppv], rdx
0x18005bce4  lea     r8, [rbp+50h+var_80]
0x18005bce8  lea     rdx, [rbp+50h+var_60]
0x18005bcec  movaps  [rbp+50h+var_40], xmm1
0x18005bcf0  mov     rax, [rcx]
0x18005bcf3  movsd   [rbp+50h+var_30], xmm0
0x18005bcf8  movaps  [rbp+50h+var_A0], xmm1
0x18005bcfc  movsd   [rbp+50h+var_90], xmm0
0x18005bd01  mov     rax, [rax+50h]
0x18005bd05  movaps  [rbp+50h+var_80], xmm1
0x18005bd09  movsd   [rbp+50h+var_70], xmm0
0x18005bd0e  movaps  [rbp+50h+var_60], xmm1
0x18005bd12  movsd   [rbp+50h+var_50], xmm0
0x18005bd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd1c  mov     ebx, eax
0x18005bd1e  test    eax, eax
0x18005bd20  js      loc_18005BEEE
0x18005bd26  lea     rcx, psz; "\\Microsoft\\Windows\\Sysmain"
0x18005bd2d  call    cs:__imp_SysAllocString
0x18005bd33  mov     r14, rax
0x18005bd36  test    rax, rax
0x18005bd39  jnz     short loc_18005BD45
0x18005bd3b  mov     ebx, 8007000Eh
0x18005bd40  jmp     loc_18005BEEE
0x18005bd45  mov     rcx, rsi; psz
0x18005bd48  call    cs:__imp_SysAllocString
0x18005bd4e  mov     rsi, rax
0x18005bd51  test    rax, rax
0x18005bd54  jnz     short loc_18005BD60
0x18005bd56  mov     ebx, 8007000Eh
0x18005bd5b  jmp     loc_18005BED3
0x18005bd60  mov     rcx, [rsp+150h+var_E8]
0x18005bd65  lea     r8, [rsp+150h+var_F0]
0x18005bd6a  mov     rdx, r14
0x18005bd6d  mov     rax, [rcx]
0x18005bd70  mov     rax, [rax+38h]
0x18005bd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd79  mov     ebx, eax
0x18005bd7b  test    eax, eax
0x18005bd7d  js      loc_18005BED3
0x18005bd83  mov     rcx, [rsp+150h+var_F0]
0x18005bd88  lea     r8, [rbp+50h+var_D0]
0x18005bd8c  mov     rdx, rsi
0x18005bd8f  mov     rax, [rcx]
0x18005bd92  mov     rax, [rax+68h]
0x18005bd96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd9b  mov     ebx, eax
0x18005bd9d  test    eax, eax
0x18005bd9f  js      loc_18005BED3
0x18005bda5  mov     rcx, [rbp+50h+var_D0]
0x18005bda9  lea     rdx, [rsp+150h+var_F8]
0x18005bdae  mov     rax, [rcx]
0x18005bdb1  mov     rax, [rax+98h]
0x18005bdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdbd  mov     ebx, eax
0x18005bdbf  test    eax, eax
0x18005bdc1  js      loc_18005BED3
0x18005bdc7  mov     rcx, [rsp+150h+var_F8]
0x18005bdcc  lea     rdx, [rsp+150h+var_D8]
0x18005bdd1  mov     rax, [rcx]
0x18005bdd4  mov     rax, [rax+58h]
0x18005bdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bddd  mov     ebx, eax
0x18005bddf  test    eax, eax
0x18005bde1  js      loc_18005BED3
0x18005bde7  mov     rcx, [rsp+150h+var_D8]
0x18005bdec  lea     r8, [rsp+150h+var_100]
0x18005bdf1  lea     rdx, _GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528
0x18005bdf8  mov     rax, [rcx]
0x18005bdfb  mov     rax, [rax]
0x18005bdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be03  mov     ebx, eax
0x18005be05  test    eax, eax
0x18005be07  js      loc_18005BED3
0x18005be0d  mov     rcx, [rsp+150h+var_100]
0x18005be12  lea     rdx, [rsp+150h+var_E0]
0x18005be17  mov     rax, [rcx]
0x18005be1a  mov     rax, [rax+198h]
0x18005be21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be26  mov     ebx, eax
0x18005be28  test    eax, eax
0x18005be2a  js      loc_18005BED3
0x18005be30  mov     rdx, [rsp+150h+var_E0]
0x18005be35  lea     r8, [rbp+50h+arg_18]
0x18005be39  mov     rcx, [rsp+150h+var_100]
0x18005be3e  mov     r9, r15
0x18005be41  mov     rax, r12
0x18005be44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be49  mov     ebx, eax
0x18005be4b  test    eax, eax
0x18005be4d  js      loc_18005BED3
0x18005be53  cmp     [rbp+50h+arg_18], 0
0x18005be57  jz      short loc_18005BED1
0x18005be59  movups  xmm1, xmmword ptr [rbp+50h+pvarg]
0x18005be5d  lea     rdx, [rbp+50h+var_C8]
0x18005be61  mov     rcx, [rsp+150h+var_F0]
0x18005be66  movsd   xmm0, qword ptr [rbp+50h+pvarg+10h]
0x18005be6b  mov     r9d, 4
0x18005be71  mov     r8, [rsp+150h+var_F8]
0x18005be76  mov     [rsp+150h+var_110], rdx
0x18005be7b  lea     rdx, [rbp+50h+var_60]
0x18005be7f  mov     rax, [rcx]
0x18005be82  mov     [rsp+150h+var_118], rdx
0x18005be87  lea     rdx, [rbp+50h+var_80]
0x18005be8b  mov     [rsp+150h+var_120], 5
0x18005be93  mov     [rsp+150h+var_128], rdx
0x18005be98  lea     rdx, [rbp+50h+var_A0]
0x18005be9c  mov     rax, [rax+88h]
0x18005bea3  mov     [rsp+150h+ppv], rdx
0x18005bea8  mov     rdx, rsi
0x18005beab  movaps  [rbp+50h+var_60], xmm1
0x18005beaf  movsd   [rbp+50h+var_50], xmm0
0x18005beb4  movaps  [rbp+50h+var_80], xmm1
0x18005beb8  movsd   [rbp+50h+var_70], xmm0
0x18005bebd  movaps  [rbp+50h+var_A0], xmm1
0x18005bec1  movsd   [rbp+50h+var_90], xmm0
0x18005bec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005becb  mov     ebx, eax
0x18005becd  test    eax, eax
0x18005becf  js      short loc_18005BED3
0x18005bed1  xor     ebx, ebx
0x18005bed3  mov     rcx, r14; bstrString
0x18005bed6  call    cs:__imp_SysFreeString
0x18005bedc  test    rsi, rsi
0x18005bedf  jz      short loc_18005BEEE
0x18005bee1  mov     rcx, rsi; bstrString
0x18005bee4  call    cs:__imp_SysFreeString
0x18005beea  jmp     short loc_18005BEEE
0x18005beec  xor     edi, edi
0x18005beee  mov     rcx, [rbp+50h+var_C8]
0x18005bef2  test    rcx, rcx
0x18005bef5  jz      short loc_18005BF03
0x18005bef7  mov     rax, [rcx]
0x18005befa  mov     rax, [rax+10h]
0x18005befe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf03  mov     rcx, [rsp+150h+var_E0]
0x18005bf08  test    rcx, rcx
0x18005bf0b  jz      short loc_18005BF19
0x18005bf0d  mov     rax, [rcx]
0x18005bf10  mov     rax, [rax+10h]
0x18005bf14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf19  mov     rcx, [rsp+150h+var_100]
0x18005bf1e  test    rcx, rcx
0x18005bf21  jz      short loc_18005BF2F
0x18005bf23  mov     rax, [rcx]
0x18005bf26  mov     rax, [rax+10h]
0x18005bf2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf2f  mov     rcx, [rsp+150h+var_D8]
0x18005bf34  test    rcx, rcx
0x18005bf37  jz      short loc_18005BF45
0x18005bf39  mov     rax, [rcx]
0x18005bf3c  mov     rax, [rax+10h]
0x18005bf40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf45  mov     rcx, [rsp+150h+var_F8]
0x18005bf4a  test    rcx, rcx
0x18005bf4d  jz      short loc_18005BF5B
0x18005bf4f  mov     rax, [rcx]
0x18005bf52  mov     rax, [rax+10h]
0x18005bf56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf5b  mov     rcx, [rbp+50h+var_D0]
0x18005bf5f  test    rcx, rcx
0x18005bf62  jz      short loc_18005BF70
0x18005bf64  mov     rax, [rcx]
0x18005bf67  mov     rax, [rax+10h]
0x18005bf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf70  mov     rcx, [rsp+150h+var_F0]
0x18005bf75  test    rcx, rcx
0x18005bf78  jz      short loc_18005BF86
0x18005bf7a  mov     rax, [rcx]
0x18005bf7d  mov     rax, [rax+10h]
0x18005bf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf86  mov     rcx, [rsp+150h+var_E8]
0x18005bf8b  test    rcx, rcx
0x18005bf8e  jz      short loc_18005BF9C
0x18005bf90  mov     rax, [rcx]
0x18005bf93  mov     rax, [rax+10h]
0x18005bf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf9c  test    edi, edi
0x18005bf9e  jz      short loc_18005BFA6
0x18005bfa0  call    cs:__imp_CoUninitialize
0x18005bfa6  lea     r11, [rsp+150h+var_20]
0x18005bfae  mov     eax, ebx
0x18005bfb0  mov     rbx, [r11+30h]
0x18005bfb4  mov     rsi, [r11+38h]
0x18005bfb8  mov     rsp, r11
0x18005bfbb  pop     r15
0x18005bfbd  pop     r14
0x18005bfbf  pop     r12
0x18005bfc1  pop     rdi
0x18005bfc2  pop     rbp
0x18005bfc3  retn
```
