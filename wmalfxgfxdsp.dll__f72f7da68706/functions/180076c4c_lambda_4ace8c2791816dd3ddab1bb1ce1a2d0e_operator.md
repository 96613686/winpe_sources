# _lambda_4ace8c2791816dd3ddab1bb1ce1a2d0e_::operator()

- ea: `0x180076c4c`
- end: `0x180076f66`
- name: `_lambda_4ace8c2791816dd3ddab1bb1ce1a2d0e_::operator()`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009040`

## callees

- `0x180008d30`
- `0x18000a154`
- `0x18000a388`
- `0x180014d58`
- `0x180076c4c`
- `0x180086010`

## import_xrefs

- `PROPSYS!InitPropVariantFromCLSID` at `0x180076e34`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180076e34`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180076eca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180076ee1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180076eca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180076ee1`

## pseudocode

```c
__int64 __fastcall lambda_4ace8c2791816dd3ddab1bb1ce1a2d0e_::operator()(__int64 **a1)
{
  _DWORD **v1; // rsi
  __int64 v3; // rdi
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 *v7; // r15
  __int64 *v8; // r14
  __int64 v9; // rax
  __int64 v10; // rcx
  void (__fastcall *v11)(__int64 *, SID *, GUID *, __int64); // r12
  __int64 *v12; // rdx
  __int64 v13; // rcx
  __int64 *v14; // r14
  __int64 *v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rcx
  int (__fastcall *v18)(__int64 *, _QWORD, __int64); // r15
  __int64 *v19; // rax
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-30h]
  PROPVARIANT ppropvar; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v26; // [rsp+80h] [rbp+30h] BYREF
  __int64 v27; // [rsp+88h] [rbp+38h] BYREF

  v1 = (_DWORD **)(a1 + 1);
  v3 = **a1;
  if ( v3 )
  {
    if ( !**v1 )
    {
      v5 = -2147467261;
      v4 = 2282;
      goto LABEL_5;
    }
  }
  else if ( **v1 )
  {
    v4 = 2281;
LABEL_4:
    v5 = -2147024809;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
      (const char *)v5,
      v23);
    return v5;
  }
  if ( **v1 != 80 )
    return 2147942487LL;
  *(_OWORD *)((char *)a1[2] + 156) = *(_OWORD *)(v3 + 56);
  *((_DWORD *)a1[2] + 43) = *(_DWORD *)(v3 + 72);
  v7 = *(__int64 **)(v3 + 32);
  v8 = a1[2];
  v9 = *v7;
  v10 = v8[53];
  v8[53] = 0;
  v11 = *(void (__fastcall **)(__int64 *, SID *, GUID *, __int64))(v9 + 24);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11(v7, &SID_AudioProcessingObjectLoggingService, &GUID_698f0107_1745_4708_95a5_d84478a62a65, (__int64)(v8 + 53));
  v12 = a1[2];
  if ( (*(__int64 *)((char *)v12 + 156) != *(_QWORD *)&GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
     || *(__int64 *)((char *)v12 + 164) != *(_QWORD *)GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4)
    && (*(__int64 *)((char *)v12 + 156) != *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
     || *(__int64 *)((char *)v12 + 164) != *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4) )
  {
    v4 = 2300;
    goto LABEL_4;
  }
  if ( *(_DWORD *)v3 != **v1 )
  {
    v4 = 2303;
    goto LABEL_4;
  }
  v13 = *(_QWORD *)(v3 + 40);
  if ( v13 )
  {
    v26 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 24LL))(v13, &v26) >= 0 && v26 )
    {
      v14 = *(__int64 **)(v3 + 40);
      v15 = a1[2];
      v16 = *v14;
      v17 = v15[52];
      v15[52] = 0;
      v18 = *(int (__fastcall **)(__int64 *, _QWORD, __int64))(v16 + 32);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v18(v14, (unsigned int)(v26 - 1), (__int64)(v15 + 52)) >= 0 )
      {
        memset(&ppropvar, 0, sizeof(ppropvar));
        if ( InitPropVariantFromCLSID(&WMALFXGFXAPO_PROPERTYSTORE_CONTEXT, &ppropvar) >= 0 )
        {
          v19 = a1[2];
          v27 = 0;
          if ( (*(int (__fastcall **)(__int64, GUID *, __int64, PROPVARIANT *))(*(_QWORD *)v19[52] + 24LL))(
                 v19[52],
                 &GUID_302ae7f9_d7e0_43e4_971b_1f8293613d2a,
                 23,
                 &ppropvar) >= 0 )
          {
            v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 32LL))(v27, 2, a1[2] + 46);
            v21 = v20;
            if ( v20 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x911,
                (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
                (const char *)(unsigned int)v20,
                (int)&v27);
              wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(&v27);
              PropVariantClear(&ppropvar);
              return v21;
            }
          }
          wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(&v27);
        }
        PropVariantClear(&ppropvar);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v12[53] + 24LL))(
      v12[53],
      4,
      L"APO::Initialize(): APOInitSystemEffects::pDeviceCollection == NULL");
  }
  CCorrAPOBase::ParseEndpointProperties((CCorrAPOBase *)a1[2], *(struct IPropertyStore **)(v3 + 24));
  v22 = a1[2][46];
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
    CCorrAPOBase::CopyPropStore((CCorrAPOBase *)a1[2]);
  }
  return 0;
}

```

## disassembly

```asm
0x180076c4c  mov     [rsp-28h+arg_10], rbx
0x180076c51  mov     [rsp-28h+arg_18], rsi
0x180076c56  push    rbp
0x180076c57  push    rdi
0x180076c58  push    r12
0x180076c5a  push    r14
0x180076c5c  push    r15
0x180076c5e  mov     rbp, rsp
0x180076c61  sub     rsp, 50h
0x180076c65  mov     rax, [rcx]
0x180076c68  lea     rsi, [rcx+8]
0x180076c6c  mov     rbx, rcx
0x180076c6f  mov     rdi, [rax]
0x180076c72  test    rdi, rdi
0x180076c75  jnz     short loc_180076CA7
0x180076c77  mov     rax, [rsi]
0x180076c7a  cmp     [rax], edi
0x180076c7c  jz      short loc_180076CA2
0x180076c7e  mov     edx, 8E9h; void *
0x180076c83  mov     ebx, 80070057h
0x180076c88  mov     rcx, [rbp+28h]; this
0x180076c8c  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x180076c93  mov     r9d, ebx; char *
0x180076c96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076c9b  mov     eax, ebx
0x180076c9d  jmp     loc_180076F4D
0x180076ca2  test    rdi, rdi
0x180076ca5  jz      short loc_180076CBB
0x180076ca7  mov     rax, [rsi]
0x180076caa  cmp     dword ptr [rax], 0
0x180076cad  jnz     short loc_180076CBB
0x180076caf  mov     ebx, 80004003h
0x180076cb4  mov     edx, 8EAh
0x180076cb9  jmp     short loc_180076C88
0x180076cbb  mov     rax, [rsi]
0x180076cbe  cmp     dword ptr [rax], 50h ; 'P'
0x180076cc1  jnz     loc_180076F48
0x180076cc7  mov     rax, [rcx+10h]
0x180076ccb  movups  xmm0, xmmword ptr [rdi+38h]
0x180076ccf  movdqu  xmmword ptr [rax+9Ch], xmm0
0x180076cd7  mov     rcx, [rcx+10h]
0x180076cdb  mov     eax, [rdi+48h]
0x180076cde  mov     [rcx+0ACh], eax
0x180076ce4  mov     r15, [rdi+20h]
0x180076ce8  mov     r14, [rbx+10h]
0x180076cec  mov     rax, [r15]
0x180076cef  mov     rcx, [r14+1A8h]
0x180076cf6  mov     qword ptr [r14+1A8h], 0
0x180076d01  mov     r12, [rax+18h]
0x180076d05  test    rcx, rcx
0x180076d08  jz      short loc_180076D16
0x180076d0a  mov     rdx, [rcx]
0x180076d0d  mov     rax, [rdx+10h]
0x180076d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d16  lea     r9, [r14+1A8h]
0x180076d1d  mov     rcx, r15
0x180076d20  lea     r8, _GUID_698f0107_1745_4708_95a5_d84478a62a65
0x180076d27  mov     rax, r12
0x180076d2a  lea     rdx, SID_AudioProcessingObjectLoggingService
0x180076d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d36  mov     rdx, [rbx+10h]
0x180076d3a  mov     rax, [rdx+9Ch]
0x180076d41  cmp     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data1
0x180076d48  jnz     short loc_180076D5A
0x180076d4a  mov     rax, [rdx+0A4h]
0x180076d51  cmp     rax, qword ptr cs:_GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3.Data4
0x180076d58  jz      short loc_180076D82
0x180076d5a  mov     rax, [rdx+9Ch]
0x180076d61  cmp     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180076d68  jnz     loc_180076F3E
0x180076d6e  mov     rax, [rdx+0A4h]
0x180076d75  cmp     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x180076d7c  jnz     loc_180076F3E
0x180076d82  mov     rax, [rsi]
0x180076d85  mov     ecx, [rax]
0x180076d87  cmp     [rdi], ecx
0x180076d89  jz      short loc_180076D95
0x180076d8b  mov     edx, 8FFh
0x180076d90  jmp     loc_180076C83
0x180076d95  mov     rcx, [rdi+28h]
0x180076d99  test    rcx, rcx
0x180076d9c  jz      loc_180076EE9
0x180076da2  mov     [rbp+arg_0], 0
0x180076da9  lea     rdx, [rbp+arg_0]
0x180076dad  mov     rax, [rcx]
0x180076db0  mov     rax, [rax+18h]
0x180076db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076db9  test    eax, eax
0x180076dbb  js      loc_180076F08
0x180076dc1  cmp     [rbp+arg_0], 0
0x180076dc5  jbe     loc_180076F08
0x180076dcb  mov     r14, [rdi+28h]
0x180076dcf  mov     rsi, [rbx+10h]
0x180076dd3  mov     rax, [r14]
0x180076dd6  mov     rcx, [rsi+1A0h]
0x180076ddd  mov     qword ptr [rsi+1A0h], 0
0x180076de8  mov     r15, [rax+20h]
0x180076dec  test    rcx, rcx
0x180076def  jz      short loc_180076DFD
0x180076df1  mov     rdx, [rcx]
0x180076df4  mov     rax, [rdx+10h]
0x180076df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076dfd  mov     edx, [rbp+arg_0]
0x180076e00  lea     r8, [rsi+1A0h]
0x180076e07  dec     edx
0x180076e09  mov     rcx, r14
0x180076e0c  mov     rax, r15
0x180076e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e14  test    eax, eax
0x180076e16  js      loc_180076F08
0x180076e1c  xorps   xmm0, xmm0
0x180076e1f  lea     rdx, [rbp+ppropvar]; ppropvar
0x180076e23  xor     eax, eax
0x180076e25  lea     rcx, WMALFXGFXAPO_PROPERTYSTORE_CONTEXT; clsid
0x180076e2c  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180076e30  mov     qword ptr [rbp+ppropvar+10h], rax
0x180076e34  call    cs:__imp_InitPropVariantFromCLSID
0x180076e3a  test    eax, eax
0x180076e3c  js      loc_180076EDD
0x180076e42  mov     rax, [rbx+10h]
0x180076e46  lea     rdx, [rbp+arg_8]
0x180076e4a  mov     [rbp+arg_8], 0
0x180076e52  lea     r9, [rbp+ppropvar]
0x180076e56  mov     qword ptr [rsp+50h+var_30], rdx; int
0x180076e5b  mov     r8d, 17h
0x180076e61  lea     rdx, _GUID_302ae7f9_d7e0_43e4_971b_1f8293613d2a
0x180076e68  mov     rcx, [rax+1A0h]
0x180076e6f  mov     rax, [rcx]
0x180076e72  mov     rax, [rax+18h]
0x180076e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e7b  test    eax, eax
0x180076e7d  js      short loc_180076ED4
0x180076e7f  mov     rcx, [rbp+arg_8]
0x180076e83  mov     edx, 2
0x180076e88  mov     r8, [rbx+10h]
0x180076e8c  add     r8, 170h
0x180076e93  mov     rax, [rcx]
0x180076e96  mov     rax, [rax+20h]
0x180076e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e9f  mov     esi, eax
0x180076ea1  test    eax, eax
0x180076ea3  jns     short loc_180076ED4
0x180076ea5  mov     rcx, [rbp+28h]; this
0x180076ea9  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x180076eb0  mov     r9d, eax; char *
0x180076eb3  mov     edx, 911h; void *
0x180076eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076ebd  lea     rcx, [rbp+arg_8]
0x180076ec1  call    ??1?$com_ptr_t@UIAudioProcessingObjectLoggingService@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(void)
0x180076ec6  lea     rcx, [rbp+ppropvar]; pvar
0x180076eca  call    cs:__imp_PropVariantClear
0x180076ed0  mov     eax, esi
0x180076ed2  jmp     short loc_180076F4D
0x180076ed4  lea     rcx, [rbp+arg_8]
0x180076ed8  call    ??1?$com_ptr_t@UIAudioProcessingObjectLoggingService@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(void)
0x180076edd  lea     rcx, [rbp+ppropvar]; pvar
0x180076ee1  call    cs:__imp_PropVariantClear
0x180076ee7  jmp     short loc_180076F08
0x180076ee9  mov     rcx, [rdx+1A8h]
0x180076ef0  lea     r8, aApoInitializeA; "APO::Initialize(): APOInitSystemEffects"...
0x180076ef7  mov     edx, 4
0x180076efc  mov     rax, [rcx]
0x180076eff  mov     rax, [rax+18h]
0x180076f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f08  mov     rdx, [rdi+18h]; struct IPropertyStore *
0x180076f0c  mov     rcx, [rbx+10h]; this
0x180076f10  call    ?ParseEndpointProperties@CCorrAPOBase@@IEAAJPEAUIPropertyStore@@@Z; CCorrAPOBase::ParseEndpointProperties(IPropertyStore *)
0x180076f15  mov     rax, [rbx+10h]
0x180076f19  mov     rcx, [rax+170h]
0x180076f20  test    rcx, rcx
0x180076f23  jz      short loc_180076F3A
0x180076f25  mov     rax, [rcx]
0x180076f28  mov     rax, [rax+8]
0x180076f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f31  mov     rcx, [rbx+10h]; this
0x180076f35  call    ?CopyPropStore@CCorrAPOBase@@QEAAJXZ; CCorrAPOBase::CopyPropStore(void)
0x180076f3a  xor     eax, eax
0x180076f3c  jmp     short loc_180076F4D
0x180076f3e  mov     edx, 8FCh
0x180076f43  jmp     loc_180076C83
0x180076f48  mov     eax, 80070057h
0x180076f4d  lea     r11, [rsp+50h+var_s0]
0x180076f52  mov     rbx, [r11+40h]
0x180076f56  mov     rsi, [r11+48h]
0x180076f5a  mov     rsp, r11
0x180076f5d  pop     r15
0x180076f5f  pop     r14
0x180076f61  pop     r12
0x180076f63  pop     rdi
0x180076f64  pop     rbp
0x180076f65  retn
```
