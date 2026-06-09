# TransformXML(ushort const *,ushort const *,ushort const *)

- ea: `0x14003012c`
- end: `0x1400305aa`
- name: `?TransformXML@@YAJPEBG00@Z`
- size: `1150`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140016ae0`
- `0x1400192b4`

## callees

- `0x14003012c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003027e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400302ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400302d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003027e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400302ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400302d8`
- `OLEAUT32!__imp_SysAllocString` at `0x140030235`
- `OLEAUT32!__imp_SysAllocString` at `0x140030246`
- `OLEAUT32!__imp_SysAllocString` at `0x140030235`
- `OLEAUT32!__imp_SysAllocString` at `0x140030246`
- `OLEAUT32!__imp_VariantInit` at `0x1400301b9`
- `OLEAUT32!__imp_VariantInit` at `0x1400301c3`
- `OLEAUT32!__imp_VariantInit` at `0x1400301cd`
- `OLEAUT32!__imp_VariantInit` at `0x1400301b9`
- `OLEAUT32!__imp_VariantInit` at `0x1400301c3`
- `OLEAUT32!__imp_VariantInit` at `0x1400301cd`
- `OLEAUT32!__imp_VariantClear` at `0x140030563`
- `OLEAUT32!__imp_VariantClear` at `0x14003056d`
- `OLEAUT32!__imp_VariantClear` at `0x140030563`
- `OLEAUT32!__imp_VariantClear` at `0x14003056d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030208`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400301f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400301f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030586`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030586`

## pseudocode

```c
__int64 __fastcall TransformXML(OLECHAR *psz, OLECHAR *a2, LPCWSTR lpFileName)
{
  int v6; // edi
  signed int LastError; // eax
  BSTR v8; // rax
  BSTR v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 *v13; // rcx
  IRecordInfo *v14; // xmm6_8
  void (__fastcall *v15)(__int64 *, VARIANTARG *); // rax
  __int64 v16; // rax
  __int64 *v18; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID v19; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID v21; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v22; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *v23; // [rsp+88h] [rbp-80h] BYREF
  void **v24; // [rsp+90h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-70h]
  char v26; // [rsp+A0h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v28; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v29; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v30; // [rsp+F0h] [rbp-18h]
  __int128 v31; // [rsp+F8h] [rbp-10h]
  __int16 v32; // [rsp+190h] [rbp+88h] BYREF

  ppv = 0;
  v30 = 0;
  v19 = 0;
  v23 = 0;
  v21 = 0;
  v18 = 0;
  v24 = &FileOutputStream::`vftable';
  v26 = 0;
  v32 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v28, 0, sizeof(v28));
  memset(&v29, 0, sizeof(v29));
  v31 = 0;
  VariantInit(&pvarg);
  VariantInit(&v28);
  VariantInit(&v29);
  v6 = 0;
  hObject = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  if ( hObject != (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  v26 = 1;
  if ( v6 >= 0 )
  {
    pvarg.vt = 8;
    v8 = SysAllocString(psz);
    v28.vt = 8;
    pvarg.llVal = (LONGLONG)v8;
    v9 = SysAllocString(a2);
    v29.iVal = -1;
    v28.llVal = (LONGLONG)v9;
    v29.vt = 11;
    v6 = CoCreateInstance(
           &GUID_88d96a06_f192_11d4_a65f_0040963251e5,
           0,
           0x15u,
           &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
           &ppv);
    if ( v6 >= 0 )
    {
      v6 = CoCreateInstance(
             &GUID_88d96a06_f192_11d4_a65f_0040963251e5,
             0,
             0x15u,
             &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
             &v19);
      if ( v6 >= 0 )
      {
        v6 = CoCreateInstance(
               &GUID_88d96a08_f192_11d4_a65f_0040963251e5,
               0,
               0x15u,
               &GUID_2933bf93_7b36_11d2_b20e_00c04f983e60,
               &v21);
        if ( v6 >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
          v10 = *(_QWORD *)ppv;
          v22 = pvarg;
          v6 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v10 + 464))(ppv, &v22, &v32);
          if ( v6 >= 0 )
          {
            if ( v32 )
            {
              (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v19 + 576LL))(v19, 0xFFFFFFFFLL);
              (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v19 + 504LL))(v19, 0);
              v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 **))v19)(
                     v19,
                     &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                     &v23);
              if ( v6 >= 0 )
              {
                v11 = *v23;
                v22 = v29;
                (*(void (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v11 + 640))(
                  v23,
                  L"AllowXsltScript",
                  &v22);
                v12 = *(_QWORD *)v19;
                v22 = v28;
                v6 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v12 + 464))(v19, &v22, &v32);
                if ( v6 >= 0 )
                {
                  if ( v32 )
                  {
                    (*(void (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v21 + 56LL))(v21, v19);
                    LOWORD(v31) = 13;
                    *((_QWORD *)&v31 + 1) = ppv;
                    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(*(_QWORD *)v21 + 72LL))(v21, &v18);
                    if ( v6 >= 0 )
                    {
                      v13 = v18;
                      if ( !v18 )
                        goto LABEL_17;
                      v14 = v30;
                      v15 = *(void (__fastcall **)(__int64 *, VARIANTARG *))(*v18 + 56);
                      *(_OWORD *)&v22.vt = v31;
                      v22.pRecInfo = v30;
                      v15(v18, &v22);
                      *((_QWORD *)&v31 + 1) = &v24;
                      v16 = *v18;
                      *(_OWORD *)&v22.vt = v31;
                      v22.pRecInfo = v14;
                      (*(void (__fastcall **)(__int64 *, VARIANTARG *))(v16 + 104))(v18, &v22);
                      v6 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v18 + 120))(v18, &v32);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v13 = v18;
LABEL_17:
  if ( v21 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
    v13 = v18;
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v23 )
    (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
  VariantClear(&pvarg);
  VariantClear(&v28);
  v24 = &FileOutputStream::`vftable';
  if ( v26 && hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003012c  mov     rax, rsp
0x14003012f  push    rbp
0x140030130  push    rbx
0x140030131  push    rsi
0x140030132  push    rdi
0x140030133  push    r12
0x140030135  push    r13
0x140030137  push    r14
0x140030139  push    r15
0x14003013b  lea     rbp, [rax-68h]
0x14003013f  sub     rsp, 128h
0x140030146  xor     r15d, r15d
0x140030149  movaps  xmmword ptr [rax-58h], xmm6
0x14003014d  xor     eax, eax
0x14003014f  mov     [rsp+160h+ppv], r15
0x140030154  xorps   xmm0, xmm0
0x140030157  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x14003015b  xorps   xmm1, xmm1
0x14003015e  mov     qword ptr [rbp+60h+var_A8+10h], rax
0x140030162  mov     r14, rcx
0x140030165  mov     qword ptr [rbp+60h+var_90+10h], rax
0x140030169  lea     r13, ??_7FileOutputStream@@6B@; const FileOutputStream::`vftable'
0x140030170  mov     [rbp+60h+var_78], rax
0x140030174  or      r12, 0FFFFFFFFFFFFFFFFh
0x140030178  mov     [rsp+160h+var_118], r15
0x14003017d  lea     rcx, [rbp+60h+pvarg]; pvarg
0x140030181  mov     [rbp+60h+var_E0], r15
0x140030185  mov     rbx, r8
0x140030188  mov     [rsp+160h+var_108], r15
0x14003018d  mov     rsi, rdx
0x140030190  mov     [rsp+160h+var_120], r15
0x140030195  mov     [rbp+60h+var_D8], r13
0x140030199  mov     [rbp+60h+var_C8], r15b
0x14003019d  mov     [rbp+60h+hObject], r12
0x1400301a1  mov     [rbp+60h+arg_18], r15w
0x1400301a9  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x1400301ad  movups  xmmword ptr [rbp+60h+var_A8], xmm1
0x1400301b1  movups  xmmword ptr [rbp+60h+var_90], xmm0
0x1400301b5  movups  [rbp+60h+var_70], xmm1
0x1400301b9  call    cs:__imp_VariantInit
0x1400301bf  lea     rcx, [rbp+60h+var_A8]; pvarg
0x1400301c3  call    cs:__imp_VariantInit
0x1400301c9  lea     rcx, [rbp+60h+var_90]; pvarg
0x1400301cd  call    cs:__imp_VariantInit
0x1400301d3  mov     [rsp+30h], r15; hTemplateFile
0x1400301d8  xor     r9d, r9d; lpSecurityAttributes
0x1400301db  mov     [rsp+160h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400301e3  xor     r8d, r8d; dwShareMode
0x1400301e6  mov     edx, 40000000h; dwDesiredAccess
0x1400301eb  mov     [rsp+160h+dwCreationDisposition], 2; dwCreationDisposition
0x1400301f3  mov     rcx, rbx; lpFileName
0x1400301f6  mov     edi, r15d
0x1400301f9  call    cs:__imp_CreateFileW
0x1400301ff  mov     [rbp+60h+hObject], rax
0x140030203  cmp     rax, r12
0x140030206  jz      short loc_14003021D
0x140030208  call    cs:__imp_GetLastError
0x14003020e  mov     edi, eax
0x140030210  test    eax, eax
0x140030212  jle     short loc_14003021D
0x140030214  movzx   edi, ax
0x140030217  or      edi, 80070000h
0x14003021d  mov     [rbp+60h+var_C8], 1
0x140030221  test    edi, edi
0x140030223  js      loc_1400304EA
0x140030229  mov     ebx, 8
0x14003022e  mov     rcx, r14; psz
0x140030231  mov     word ptr [rbp+60h+pvarg], bx
0x140030235  call    cs:__imp_SysAllocString
0x14003023b  mov     rcx, rsi; psz
0x14003023e  mov     word ptr [rbp+60h+var_A8], bx
0x140030242  mov     qword ptr [rbp+60h+pvarg+8], rax
0x140030246  call    cs:__imp_SysAllocString
0x14003024c  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x140030253  mov     word ptr [rbp+60h+var_90+8], r12w
0x140030258  mov     qword ptr [rbp+60h+var_A8+8], rax
0x14003025c  lea     rcx, _GUID_88d96a06_f192_11d4_a65f_0040963251e5; rclsid
0x140030263  lea     eax, [rbx+3]
0x140030266  xor     edx, edx; pUnkOuter
0x140030268  mov     word ptr [rbp+60h+var_90], ax
0x14003026c  mov     ebx, 15h
0x140030271  lea     rax, [rsp+160h+ppv]
0x140030276  mov     r8d, ebx; dwClsContext
0x140030279  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; ppv
0x14003027e  call    cs:__imp_CoCreateInstance
0x140030284  mov     edi, eax
0x140030286  test    eax, eax
0x140030288  js      loc_1400304EA
0x14003028e  lea     rax, [rsp+160h+var_118]
0x140030293  mov     r8d, ebx; dwClsContext
0x140030296  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x14003029d  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; ppv
0x1400302a2  xor     edx, edx; pUnkOuter
0x1400302a4  lea     rcx, _GUID_88d96a06_f192_11d4_a65f_0040963251e5; rclsid
0x1400302ab  call    cs:__imp_CoCreateInstance
0x1400302b1  mov     edi, eax
0x1400302b3  test    eax, eax
0x1400302b5  js      loc_1400304EA
0x1400302bb  lea     rax, [rsp+160h+var_108]
0x1400302c0  mov     r8d, ebx; dwClsContext
0x1400302c3  lea     r9, _GUID_2933bf93_7b36_11d2_b20e_00c04f983e60; riid
0x1400302ca  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; ppv
0x1400302cf  xor     edx, edx; pUnkOuter
0x1400302d1  lea     rcx, _GUID_88d96a08_f192_11d4_a65f_0040963251e5; rclsid
0x1400302d8  call    cs:__imp_CoCreateInstance
0x1400302de  mov     edi, eax
0x1400302e0  test    eax, eax
0x1400302e2  js      loc_1400304EA
0x1400302e8  mov     rcx, [rsp+160h+ppv]
0x1400302ed  mov     edx, r12d
0x1400302f0  mov     rax, [rcx]
0x1400302f3  mov     rax, [rax+240h]
0x1400302fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400302ff  mov     rcx, [rsp+160h+ppv]
0x140030304  xor     edx, edx
0x140030306  mov     rax, [rcx]
0x140030309  mov     rax, [rax+1F8h]
0x140030310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030315  mov     rcx, [rsp+160h+ppv]
0x14003031a  lea     r8, [rbp+60h+arg_18]
0x140030321  movups  xmm0, xmmword ptr [rbp+60h+pvarg]
0x140030325  lea     rdx, [rsp+160h+var_108+8]
0x14003032a  movsd   xmm1, qword ptr [rbp+60h+pvarg+10h]
0x14003032f  mov     rax, [rcx]
0x140030332  movaps  xmmword ptr [rsp+160h+var_108+8], xmm0
0x140030337  movsd   [rsp+160h+var_F0], xmm1
0x14003033d  mov     rax, [rax+1D0h]
0x140030344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030349  mov     edi, eax
0x14003034b  test    eax, eax
0x14003034d  js      loc_1400304EA
0x140030353  cmp     [rbp+60h+arg_18], r15w
0x14003035b  jz      loc_1400304EA
0x140030361  mov     rcx, [rsp+160h+var_118]
0x140030366  mov     edx, r12d
0x140030369  mov     rax, [rcx]
0x14003036c  mov     rax, [rax+240h]
0x140030373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030378  mov     rcx, [rsp+160h+var_118]
0x14003037d  xor     edx, edx
0x14003037f  mov     rax, [rcx]
0x140030382  mov     rax, [rax+1F8h]
0x140030389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003038e  mov     rcx, [rsp+160h+var_118]
0x140030393  lea     r8, [rbp+60h+var_E0]
0x140030397  lea     rdx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x14003039e  mov     rax, [rcx]
0x1400303a1  mov     rax, [rax]
0x1400303a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400303a9  mov     edi, eax
0x1400303ab  test    eax, eax
0x1400303ad  js      loc_1400304EA
0x1400303b3  mov     rcx, [rbp+60h+var_E0]
0x1400303b7  lea     r8, [rsp+160h+var_108+8]
0x1400303bc  movups  xmm0, xmmword ptr [rbp+60h+var_90]
0x1400303c0  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x1400303c7  movsd   xmm1, qword ptr [rbp+60h+var_90+10h]
0x1400303cc  mov     rax, [rcx]
0x1400303cf  movaps  xmmword ptr [rsp+160h+var_108+8], xmm0
0x1400303d4  movsd   [rsp+160h+var_F0], xmm1
0x1400303da  mov     rax, [rax+280h]
0x1400303e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400303e6  mov     rcx, [rsp+160h+var_118]
0x1400303eb  lea     r8, [rbp+60h+arg_18]
0x1400303f2  movups  xmm0, xmmword ptr [rbp+60h+var_A8]
0x1400303f6  lea     rdx, [rsp+160h+var_108+8]
0x1400303fb  movsd   xmm1, qword ptr [rbp+60h+var_A8+10h]
0x140030400  mov     rax, [rcx]
0x140030403  movaps  xmmword ptr [rsp+160h+var_108+8], xmm0
0x140030408  movsd   [rsp+160h+var_F0], xmm1
0x14003040e  mov     rax, [rax+1D0h]
0x140030415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003041a  mov     edi, eax
0x14003041c  test    eax, eax
0x14003041e  js      loc_1400304EA
0x140030424  cmp     [rbp+60h+arg_18], r15w
0x14003042c  jz      loc_1400304EA
0x140030432  mov     rcx, [rsp+160h+var_108]
0x140030437  mov     rdx, [rsp+160h+var_118]
0x14003043c  mov     rax, [rcx]
0x14003043f  mov     rax, [rax+38h]
0x140030443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030448  mov     rcx, [rsp+160h+var_108]
0x14003044d  lea     eax, [rbx-8]
0x140030450  mov     word ptr [rbp+60h+var_70], ax
0x140030454  lea     rdx, [rsp+160h+var_120]
0x140030459  mov     rax, [rsp+160h+ppv]
0x14003045e  mov     qword ptr [rbp+60h+var_70+8], rax
0x140030462  mov     rax, [rcx]
0x140030465  mov     rax, [rax+48h]
0x140030469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003046e  mov     edi, eax
0x140030470  test    eax, eax
0x140030472  js      short loc_1400304EA
0x140030474  mov     rcx, [rsp+160h+var_120]
0x140030479  test    rcx, rcx
0x14003047c  jz      short loc_1400304EF
0x14003047e  mov     rax, [rcx]
0x140030481  lea     rdx, [rsp+160h+var_108+8]
0x140030486  movups  xmm0, [rbp+60h+var_70]
0x14003048a  movsd   xmm6, [rbp+60h+var_78]
0x14003048f  mov     rax, [rax+38h]
0x140030493  movaps  xmmword ptr [rsp+160h+var_108+8], xmm0
0x140030498  movsd   [rsp+160h+var_F0], xmm6
0x14003049e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400304a3  mov     rcx, [rsp+160h+var_120]
0x1400304a8  lea     rax, [rbp+60h+var_D8]
0x1400304ac  mov     qword ptr [rbp+60h+var_70+8], rax
0x1400304b0  lea     rdx, [rsp+160h+var_108+8]
0x1400304b5  movups  xmm0, [rbp+60h+var_70]
0x1400304b9  mov     rax, [rcx]
0x1400304bc  movaps  xmmword ptr [rsp+160h+var_108+8], xmm0
0x1400304c1  movsd   [rsp+160h+var_F0], xmm6
0x1400304c7  mov     rax, [rax+68h]
0x1400304cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400304d0  mov     rcx, [rsp+160h+var_120]
0x1400304d5  lea     rdx, [rbp+60h+arg_18]
0x1400304dc  mov     rax, [rcx]
0x1400304df  mov     rax, [rax+78h]
0x1400304e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400304e8  mov     edi, eax
0x1400304ea  mov     rcx, [rsp+160h+var_120]
0x1400304ef  mov     rdx, [rsp+160h+var_108]
0x1400304f4  test    rdx, rdx
0x1400304f7  jz      short loc_14003050D
0x1400304f9  mov     rax, [rdx]
0x1400304fc  mov     rcx, rdx
0x1400304ff  mov     rax, [rax+10h]
0x140030503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030508  mov     rcx, [rsp+160h+var_120]
0x14003050d  test    rcx, rcx
0x140030510  jz      short loc_14003051E
0x140030512  mov     rax, [rcx]
0x140030515  mov     rax, [rax+10h]
0x140030519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003051e  mov     rcx, [rsp+160h+ppv]
0x140030523  test    rcx, rcx
0x140030526  jz      short loc_140030534
0x140030528  mov     rax, [rcx]
0x14003052b  mov     rax, [rax+10h]
0x14003052f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030534  mov     rcx, [rsp+160h+var_118]
0x140030539  test    rcx, rcx
0x14003053c  jz      short loc_14003054A
0x14003053e  mov     rax, [rcx]
0x140030541  mov     rax, [rax+10h]
0x140030545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003054a  mov     rcx, [rbp+60h+var_E0]
0x14003054e  test    rcx, rcx
0x140030551  jz      short loc_14003055F
0x140030553  mov     rax, [rcx]
0x140030556  mov     rax, [rax+10h]
0x14003055a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003055f  lea     rcx, [rbp+60h+pvarg]; pvarg
0x140030563  call    cs:__imp_VariantClear
0x140030569  lea     rcx, [rbp+60h+var_A8]; pvarg
0x14003056d  call    cs:__imp_VariantClear
0x140030573  mov     [rbp+60h+var_D8], r13
0x140030577  cmp     [rbp+60h+var_C8], r15b
0x14003057b  jz      short loc_14003058C
0x14003057d  mov     rcx, [rbp+60h+hObject]; hObject
0x140030581  cmp     rcx, r12
0x140030584  jz      short loc_14003058C
0x140030586  call    cs:__imp_CloseHandle
0x14003058c  movaps  xmm6, [rsp+160h+var_58+8]
0x140030594  mov     eax, edi
0x140030596  add     rsp, 128h
0x14003059d  pop     r15
0x14003059f  pop     r14
0x1400305a1  pop     r13
0x1400305a3  pop     r12
0x1400305a5  pop     rdi
0x1400305a6  pop     rsi
0x1400305a7  pop     rbx
0x1400305a8  pop     rbp
0x1400305a9  retn
```
