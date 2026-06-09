# InvokeSmartScreen(HWND__ * const,ushort const * const,ushort const * const,int,IUnknown *,ushort const * const,bool,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel,bool,bool,SafeOpenPromptExperienceResults &,ulong &)

- ea: `0x18001794c`
- end: `0x180017c11`
- name: `?InvokeSmartScreen@@YAKQEAUHWND__@@QEBG1HPEAUIUnknown@@1_NV?$ComPtr@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@W4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@33AEAW4SafeOpenPromptExperienceResults@@AEAK@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d120`

## callees

- `0x180004370`
- `0x1800067a0`
- `0x18001354c`
- `0x180014334`
- `0x180014e94`
- `0x18001794c`
- `0x180018f90`
- `0x18001a59c`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall InvokeSmartScreen(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        __int64 *a8,
        char a9,
        char a10,
        char a11,
        __int64 *a12,
        unsigned int *a13)
{
  unsigned int *v13; // rsi
  __int64 v14; // r15
  __int64 *v15; // r14
  _BYTE *v16; // rdi
  __int64 *v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // r8d
  unsigned int v20; // ebx
  char *v21; // rbx
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+58h] [rbp-A8h]
  __int128 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+78h] [rbp-88h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 *v34; // [rsp+A0h] [rbp-60h]
  __int64 *v35; // [rsp+A8h] [rbp-58h]
  __int64 *v36; // [rsp+B0h] [rbp-50h]
  __int64 *v37; // [rsp+B8h] [rbp-48h]
  __int64 *v38; // [rsp+C0h] [rbp-40h]
  char *v39; // [rsp+C8h] [rbp-38h]
  char *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41[7]; // [rsp+D8h] [rbp-28h] BYREF
  char *v42; // [rsp+110h] [rbp+10h]
  _BYTE v43[56]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE *v44; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  __int64 v46; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v47; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v48; // [rsp+1B0h] [rbp+B0h] BYREF
  int v49; // [rsp+1B8h] [rbp+B8h] BYREF

  v49 = a4;
  v48 = a3;
  v47 = a2;
  v46 = a1;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v13 = a13;
  *(_QWORD *)&v28 = a13;
  *((_QWORD *)&v28 + 1) = &v46;
  *(_QWORD *)&v29 = &v49;
  *((_QWORD *)&v29 + 1) = &a5;
  *(_QWORD *)&v30 = &v23;
  *((_QWORD *)&v30 + 1) = &v47;
  *(_QWORD *)&v31 = &a6;
  *((_QWORD *)&v31 + 1) = &a7;
  *(_QWORD *)&v32 = &a9;
  v14 = (__int64)a12;
  *((_QWORD *)&v32 + 1) = a12;
  v15 = a8;
  v33 = (__int64)a8;
  v34 = &v27;
  v35 = &v26;
  v36 = &v25;
  v37 = &v48;
  v38 = &v24;
  v39 = &a11;
  v40 = &a10;
  v44 = 0;
  v16 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_6eaf0711442c7bca6cc0a2d2e85d1da2__long___lambda_6eaf0711442c7bca6cc0a2d2e85d1da2___(&v28);
  v44 = v16;
  v17 = (__int64 *)std::function<long (void)>::function<long (void)>(v41, v43);
  LODWORD(a13) = RunInSTAApartment(v17);
  if ( (int)a13 >= 0 )
  {
    v20 = *v13;
    if ( (*v13 & 0x80000000) == 0 )
      goto LABEL_7;
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xAFC, v19, (const char *)v20, v23);
  }
  a12 = v41;
  *(_QWORD *)&v28 = &a13;
  *((_QWORD *)&v28 + 1) = &v46;
  *(_QWORD *)&v29 = &v49;
  *((_QWORD *)&v29 + 1) = &a5;
  *(_QWORD *)&v30 = &v47;
  *((_QWORD *)&v30 + 1) = &a6;
  *(_QWORD *)&v31 = &a7;
  *((_QWORD *)&v31 + 1) = &a9;
  *(_QWORD *)&v32 = v14;
  *((_QWORD *)&v32 + 1) = v13;
  v42 = 0;
  v21 = (char *)operator new(0x58u);
  *(_QWORD *)v21 = off_18002A2E8;
  *(_OWORD *)(v21 + 8) = v28;
  *(_OWORD *)(v21 + 24) = v29;
  *(_OWORD *)(v21 + 40) = v30;
  *(_OWORD *)(v21 + 56) = v31;
  *(_OWORD *)(v21 + 72) = v32;
  a12 = 0;
  std::_Global_new_std::_Func_impl_no_alloc__lambda_133cfae19bd041bc854d98e7626409ca__long___lambda_133cfae19bd041bc854d98e7626409ca____::_2_::_Guard_type::__Guard_type(&a12);
  v42 = v21;
  LODWORD(a13) = RunInSTAApartment(v41);
  if ( (int)a13 < 0 )
    v20 = 1223;
  else
    v20 = *v13;
LABEL_7:
  if ( v16 )
  {
    LOBYTE(v18) = v16 != v43;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v16 + 32LL))(v16, v18);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
  return v20;
}

```

## disassembly

```asm
0x18001794c  mov     rax, rsp
0x18001794f  mov     [rax+20h], r9d
0x180017953  mov     [rax+18h], r8
0x180017957  mov     [rax+10h], rdx
0x18001795b  mov     [rax+8], rcx
0x18001795f  push    rbp
0x180017960  push    rbx
0x180017961  push    rsi
0x180017962  push    rdi
0x180017963  push    r14
0x180017965  push    r15
0x180017967  lea     rbp, [rsp-68h]
0x18001796c  sub     rsp, 168h
0x180017973  mov     [rsp+190h+var_150], 0
0x18001797c  mov     [rsp+190h+var_158], 0
0x180017985  mov     [rsp+190h+var_160], 0
0x18001798e  mov     [rsp+190h+var_168], 0
0x180017997  mov     [rsp+190h+var_170], 0; int
0x18001799f  mov     rsi, [rbp+90h+arg_60]
0x1800179a6  mov     qword ptr [rsp+190h+var_148], rsi
0x1800179ab  lea     rax, [rbp+90h+arg_0]
0x1800179b2  mov     qword ptr [rsp+190h+var_148+8], rax
0x1800179b7  lea     rax, [rbp+90h+arg_18]
0x1800179be  mov     qword ptr [rsp+190h+var_138], rax
0x1800179c3  lea     rax, [rbp+90h+arg_20]
0x1800179ca  mov     qword ptr [rsp+190h+var_138+8], rax
0x1800179cf  lea     rax, [rsp+190h+var_170]
0x1800179d4  mov     qword ptr [rsp+190h+var_128], rax
0x1800179d9  lea     rax, [rbp+90h+arg_8]
0x1800179e0  mov     qword ptr [rsp+190h+var_128+8], rax
0x1800179e5  lea     rax, [rbp+90h+arg_28]
0x1800179ec  mov     qword ptr [rsp+190h+var_118], rax
0x1800179f1  lea     rax, [rbp+90h+arg_30]
0x1800179f8  mov     qword ptr [rbp+90h+var_118+8], rax
0x1800179fc  lea     rax, [rbp+90h+arg_40]
0x180017a03  mov     qword ptr [rbp+90h+var_108], rax
0x180017a07  mov     r15, [rbp+90h+arg_58]
0x180017a0e  mov     qword ptr [rbp+90h+var_108+8], r15
0x180017a12  mov     r14, [rbp+90h+arg_38]
0x180017a19  mov     [rbp+90h+var_F8], r14
0x180017a1d  lea     rax, [rsp+190h+var_150]
0x180017a22  mov     [rbp+90h+var_F0], rax
0x180017a26  lea     rax, [rsp+190h+var_158]
0x180017a2b  mov     [rbp+90h+var_E8], rax
0x180017a2f  lea     rax, [rsp+190h+var_160]
0x180017a34  mov     [rbp+90h+var_E0], rax
0x180017a38  lea     rax, [rbp+90h+arg_10]
0x180017a3f  mov     [rbp+90h+var_D8], rax
0x180017a43  lea     rax, [rsp+190h+var_168]
0x180017a48  mov     [rbp+90h+var_D0], rax
0x180017a4c  lea     rax, [rbp+90h+arg_50]
0x180017a53  mov     [rbp+90h+var_C8], rax
0x180017a57  lea     rax, [rbp+90h+arg_48]
0x180017a5e  mov     [rbp+90h+var_C0], rax
0x180017a62  mov     [rbp+90h+var_38], 0
0x180017a6a  lea     rcx, [rsp+190h+var_148]
0x180017a6f  call    std___Global_new_std___Func_impl_no_alloc__lambda_6eaf0711442c7bca6cc0a2d2e85d1da2__long___lambda_6eaf0711442c7bca6cc0a2d2e85d1da2___
0x180017a74  mov     rdi, rax
0x180017a77  mov     [rbp+90h+var_38], rax
0x180017a7b  lea     rdx, [rbp+90h+var_70]
0x180017a7f  lea     rcx, [rbp+90h+var_B8]
0x180017a83  call    ??0?$function@$$A6AJXZ@std@@QEAA@AEBV01@@Z; std::function<long (void)>::function<long (void)>(std::function<long (void)> const &)
0x180017a88  mov     rcx, rax
0x180017a8b  call    ?RunInSTAApartment@@YAJV?$function@$$A6AJXZ@std@@@Z; RunInSTAApartment(std::function<long (void)>)
0x180017a90  mov     dword ptr [rbp+90h+arg_60], eax
0x180017a96  test    eax, eax
0x180017a98  js      short loc_180017AB8
0x180017a9a  mov     ebx, [rsi]
0x180017a9c  mov     rcx, [rbp+98h]; this
0x180017aa3  test    ebx, ebx
0x180017aa5  jns     loc_180017BAC
0x180017aab  mov     r9d, ebx; char *
0x180017aae  mov     edx, 0AFCh; void *
0x180017ab3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017ab8  lea     rax, [rbp+90h+var_B8]
0x180017abc  mov     [rbp+90h+arg_58], rax
0x180017ac3  lea     rax, [rbp+90h+arg_60]
0x180017aca  mov     qword ptr [rsp+190h+var_148], rax
0x180017acf  lea     rax, [rbp+90h+arg_0]
0x180017ad6  mov     qword ptr [rsp+190h+var_148+8], rax
0x180017adb  lea     rax, [rbp+90h+arg_18]
0x180017ae2  mov     qword ptr [rsp+190h+var_138], rax
0x180017ae7  lea     rax, [rbp+90h+arg_20]
0x180017aee  mov     qword ptr [rsp+190h+var_138+8], rax
0x180017af3  lea     rax, [rbp+90h+arg_8]
0x180017afa  mov     qword ptr [rsp+190h+var_128], rax
0x180017aff  lea     rax, [rbp+90h+arg_28]
0x180017b06  mov     qword ptr [rsp+190h+var_128+8], rax
0x180017b0b  lea     rax, [rbp+90h+arg_30]
0x180017b12  mov     qword ptr [rsp+190h+var_118], rax
0x180017b17  lea     rax, [rbp+90h+arg_40]
0x180017b1e  mov     qword ptr [rbp+90h+var_118+8], rax
0x180017b22  mov     qword ptr [rbp+90h+var_108], r15
0x180017b26  mov     qword ptr [rbp+90h+var_108+8], rsi
0x180017b2a  mov     [rbp+90h+var_80], 0
0x180017b32  mov     ecx, 58h ; 'X'; unsigned __int64
0x180017b37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017b3c  mov     rbx, rax
0x180017b3f  lea     rax, off_18002A2E8
0x180017b46  mov     [rbx], rax
0x180017b49  movups  xmm0, [rsp+190h+var_148]
0x180017b4e  movups  xmmword ptr [rbx+8], xmm0
0x180017b52  movups  xmm1, [rsp+190h+var_138]
0x180017b57  movups  xmmword ptr [rbx+18h], xmm1
0x180017b5b  movups  xmm0, [rsp+190h+var_128]
0x180017b60  movups  xmmword ptr [rbx+28h], xmm0
0x180017b64  movups  xmm1, [rsp+190h+var_118]
0x180017b69  movups  xmmword ptr [rbx+38h], xmm1
0x180017b6d  movups  xmm0, [rbp+90h+var_108]
0x180017b71  movups  xmmword ptr [rbx+48h], xmm0
0x180017b75  mov     [rbp+90h+arg_58], 0
0x180017b80  lea     rcx, [rbp+90h+arg_58]
0x180017b87  call    _std___Global_new_std___Func_impl_no_alloc__lambda_133cfae19bd041bc854d98e7626409ca__long___lambda_133cfae19bd041bc854d98e7626409ca_______2____Guard_type____Guard_type
0x180017b8c  mov     [rbp+90h+var_80], rbx
0x180017b90  lea     rcx, [rbp+90h+var_B8]
0x180017b94  call    ?RunInSTAApartment@@YAJV?$function@$$A6AJXZ@std@@@Z; RunInSTAApartment(std::function<long (void)>)
0x180017b99  mov     dword ptr [rbp+90h+arg_60], eax
0x180017b9f  test    eax, eax
0x180017ba1  js      short loc_180017BA7
0x180017ba3  mov     ebx, [rsi]
0x180017ba5  jmp     short loc_180017BAC
0x180017ba7  mov     ebx, 4C7h
0x180017bac  test    rdi, rdi
0x180017baf  jz      short loc_180017BCB
0x180017bb1  lea     rcx, [rbp+90h+var_70]
0x180017bb5  cmp     rdi, rcx
0x180017bb8  mov     rax, [rdi]
0x180017bbb  setnz   dl
0x180017bbe  mov     rcx, rdi
0x180017bc1  mov     rax, [rax+20h]
0x180017bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bca  nop
0x180017bcb  lea     rcx, [rsp+190h+var_168]
0x180017bd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017bd5  nop
0x180017bd6  lea     rcx, [rsp+190h+var_160]
0x180017bdb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017be0  nop
0x180017be1  lea     rcx, [rsp+190h+var_158]
0x180017be6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017beb  nop
0x180017bec  lea     rcx, [rsp+190h+var_150]
0x180017bf1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017bf6  nop
0x180017bf7  mov     rcx, r14
0x180017bfa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017bff  mov     eax, ebx
0x180017c01  add     rsp, 168h
0x180017c08  pop     r15
0x180017c0a  pop     r14
0x180017c0c  pop     rdi
0x180017c0d  pop     rsi
0x180017c0e  pop     rbx
0x180017c0f  pop     rbp
0x180017c10  retn
```
