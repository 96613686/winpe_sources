# ModuleHandler::ModuleHandler(std::unique_ptr<WindiagModuleWrapper,std::default_delete<WindiagModuleWrapper>>,void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)

- ea: `0x18001b290`
- end: `0x18001b5b2`
- name: `??0ModuleHandler@@QEAA@V?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEAXIPEBDV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(__int64, const char ****, __int64, int, char *, HANDLE *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180015d70`
- `0x180016208`

## callees

- `0x1800032e0`
- `0x180003304`
- `0x180003da4`
- `0x18000a4f0`
- `0x18000a80c`
- `0x180011578`
- `0x18001ae08`
- `0x18001b290`
- `0x18001bbc8`
- `0x1800238cc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b57e`

## pseudocode

```c
__int64 __fastcall ModuleHandler::ModuleHandler(
        __int64 a1,
        const char ****a2,
        __int64 a3,
        int a4,
        char *a5,
        HANDLE *a6)
{
  __int64 v8; // rsi
  __int64 v9; // rbx
  _QWORD *v10; // rcx
  const char **v11; // rbx
  const char ***v12; // rax
  __int64 v13; // rbx
  unsigned __int64 v14; // rdx
  void *v15; // rcx
  const char ***v16; // rbx
  unsigned __int64 v17; // rdx
  const char **v18; // rcx
  void **v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+28h] [rbp-D8h] BYREF
  char v22; // [rsp+2Ch] [rbp-D4h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  const char *v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  char v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  char v28[152]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v29; // [rsp+110h] [rbp+10h]
  int v30; // [rsp+120h] [rbp+20h]
  __int64 v31; // [rsp+128h] [rbp+28h]
  int *v32; // [rsp+130h] [rbp+30h]
  __int64 v33; // [rsp+138h] [rbp+38h]
  __int64 v34; // [rsp+140h] [rbp+40h]
  void ***v35; // [rsp+148h] [rbp+48h]
  __int64 v36; // [rsp+150h] [rbp+50h]
  int v37; // [rsp+158h] [rbp+58h]
  int *v38; // [rsp+160h] [rbp+60h]
  char v39; // [rsp+168h] [rbp+68h]
  _QWORD v40[42]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v41[42]; // [rsp+2C0h] [rbp+1C0h] BYREF

  *(_QWORD *)a1 = a3;
  *(_QWORD *)(a1 + 8) = *a6;
  *a6 = 0;
  *(_DWORD *)(a1 + 16) = a4;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  v8 = a1 + 40;
  v9 = a1 + 48;
  *(_DWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 52) = 0;
  *(_BYTE *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = "WhesvcModuleActivity";
  *(_QWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  v10 = (_QWORD *)(a1 + 128);
  v10[19] = 0;
  v10[20] = 0;
  memset_0(v10, 0, 0x98u);
  *(_DWORD *)(v9 + 248) = 1;
  *(_QWORD *)(v9 + 256) = 0;
  *(_QWORD *)(v8 + 272) = v9;
  *(_QWORD *)(v8 + 280) = 0;
  *(_QWORD *)(v8 + 288) = 0;
  *(_QWORD *)(v8 + 296) = v8;
  *(_QWORD *)(v8 + 304) = 0;
  *(_DWORD *)(v8 + 312) = 0;
  *(_QWORD *)(v8 + 320) = v8 + 48;
  *(_BYTE *)(v8 + 328) = 0;
  *(_QWORD *)v8 = &WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable';
  v11 = **a2;
  v21 = 0;
  v22 = 0;
  v26 = 0;
  v23 = 0;
  v24 = "WhesvcModuleActivity";
  v25 = 0;
  v27 = 0;
  v29 = 0;
  memset_0(v28, 0, sizeof(v28));
  v30 = 1;
  v31 = 0;
  v32 = &v21;
  v33 = 0;
  v34 = 0;
  v35 = &v20;
  v36 = 0;
  v37 = 0;
  v38 = &v23;
  v39 = 0;
  v20 = &WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable';
  WhesvcTelemetryProvider::WhesvcModuleActivity::StartActivity(
    (WhesvcTelemetryProvider::WhesvcModuleActivity *)&v20,
    *v11,
    a5);
  v12 = *a2;
  *a2 = 0;
  v13 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = v12;
  if ( v13 )
  {
    std::string::~string(v13 + 56);
    std::string::~string(v13 + 24);
    v15 = *(void **)(v13 + 8);
    if ( v15 )
      operator delete(v15, v14);
    if ( *(_QWORD *)v13 )
      operator delete(*(void **)v13, 0x18u);
    operator delete((void *)v13, 0x58u);
  }
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v40,
    (__int64)&v20,
    0);
  v40[0] = &WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable';
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v41,
    v8,
    *(_DWORD *)(v8 + 312) != 0);
  v41[0] = &WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable';
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(
    v8,
    v40);
  v41[0] = &WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable';
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v41);
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(v41);
  v40[0] = &WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable';
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v40);
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(v40);
  v20 = &WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable';
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v20);
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(&v20);
  v16 = *a2;
  if ( *a2 )
  {
    std::string::~string(v16 + 7);
    std::string::~string(v16 + 3);
    v18 = v16[1];
    if ( v18 )
      operator delete(v18, v17);
    if ( *v16 )
      operator delete(*v16, 0x18u);
    operator delete(v16, 0x58u);
  }
  if ( (char *)*a6 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*a6);
  return a1;
}

```

## disassembly

```asm
0x18001b290  mov     [rsp-8+arg_10], rbx
0x18001b295  mov     [rsp-8+arg_18], rsi
0x18001b29a  push    rbp
0x18001b29b  push    rdi
0x18001b29c  push    r12
0x18001b29e  push    r14
0x18001b2a0  push    r15
0x18001b2a2  lea     rbp, [rsp-320h]
0x18001b2aa  sub     rsp, 420h
0x18001b2b1  mov     rax, cs:__security_cookie
0x18001b2b8  xor     rax, rsp
0x18001b2bb  mov     [rbp+340h+var_30], rax
0x18001b2c2  mov     r12, rdx
0x18001b2c5  mov     r14, rcx
0x18001b2c8  mov     r15, [rbp+340h+arg_28]
0x18001b2cf  mov     rdi, [rbp+340h+arg_20]
0x18001b2d6  mov     [rcx], r8
0x18001b2d9  mov     rax, [r15]
0x18001b2dc  mov     [rcx+8], rax
0x18001b2e0  xor     edx, edx; Val
0x18001b2e2  mov     [r15], rdx
0x18001b2e5  mov     [rcx+10h], r9d
0x18001b2e9  mov     [rcx+18h], rdx
0x18001b2ed  mov     [rcx+20h], edx
0x18001b2f0  lea     rsi, [rcx+28h]
0x18001b2f4  lea     rbx, [rsi+8]
0x18001b2f8  mov     [rbx], edx
0x18001b2fa  mov     [rbx+4], dl
0x18001b2fd  mov     [rbx+40h], dl
0x18001b300  mov     [rbx+28h], edx
0x18001b303  lea     rax, aWhesvcmoduleac; "WhesvcModuleActivity"
0x18001b30a  mov     [rbx+30h], rax
0x18001b30e  mov     [rbx+38h], rdx
0x18001b312  mov     [rbx+48h], edx
0x18001b315  lea     rcx, [rbx+50h]; void *
0x18001b319  mov     [rcx+98h], rdx
0x18001b320  mov     [rcx+0A0h], rdx
0x18001b327  mov     r8d, 98h; Size
0x18001b32d  call    memset_0
0x18001b332  mov     dword ptr [rbx+0F8h], 1
0x18001b33c  xor     eax, eax
0x18001b33e  mov     [rbx+100h], rax
0x18001b345  mov     [rsi+110h], rbx
0x18001b34c  xor     ecx, ecx
0x18001b34e  mov     [rsi+118h], rcx
0x18001b355  mov     [rsi+120h], rcx
0x18001b35c  mov     [rsi+128h], rsi
0x18001b363  mov     [rsi+130h], rcx
0x18001b36a  mov     [rsi+138h], ecx
0x18001b370  lea     rax, [rsi+30h]
0x18001b374  mov     [rsi+140h], rax
0x18001b37b  mov     [rsi+148h], cl
0x18001b381  lea     rax, ??_7WhesvcModuleActivity@WhesvcTelemetryProvider@@6B@; const WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable'
0x18001b388  mov     [rsi], rax
0x18001b38b  mov     rax, [r12]
0x18001b38f  mov     rbx, [rax]
0x18001b392  mov     [rsp+440h+var_418], ecx
0x18001b396  mov     [rsp+440h+var_414], cl
0x18001b39a  mov     [rsp+440h+var_3D8], cl
0x18001b39e  mov     [rsp+440h+var_3F0], ecx
0x18001b3a2  lea     rax, aWhesvcmoduleac; "WhesvcModuleActivity"
0x18001b3a9  mov     [rsp+440h+var_3E8], rax
0x18001b3ae  mov     [rsp+440h+var_3E0], rcx
0x18001b3b3  mov     [rsp+440h+var_3D0], ecx
0x18001b3b7  xorps   xmm0, xmm0
0x18001b3ba  movdqa  [rbp+340h+var_330], xmm0
0x18001b3bf  xor     edx, edx; Val
0x18001b3c1  mov     r8d, 98h; Size
0x18001b3c7  lea     rcx, [rsp+440h+var_3C8]; void *
0x18001b3cc  call    memset_0
0x18001b3d1  mov     [rbp+340h+var_320], 1
0x18001b3d8  xor     eax, eax
0x18001b3da  mov     [rbp+340h+var_318], rax
0x18001b3de  lea     rax, [rsp+440h+var_418]
0x18001b3e3  mov     [rbp+340h+var_310], rax
0x18001b3e7  mov     [rbp+340h+var_308], 0
0x18001b3ef  mov     [rbp+340h+var_300], 0
0x18001b3f7  lea     rax, [rsp+440h+var_420]
0x18001b3fc  mov     [rbp+340h+var_2F8], rax
0x18001b400  mov     [rbp+340h+var_2F0], 0
0x18001b408  mov     [rbp+340h+var_2E8], 0
0x18001b40f  lea     rax, [rsp+440h+var_3F0]
0x18001b414  mov     [rbp+340h+var_2E0], rax
0x18001b418  mov     [rbp+340h+var_2D8], 0
0x18001b41c  lea     rax, ??_7WhesvcModuleActivity@WhesvcTelemetryProvider@@6B@; const WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable'
0x18001b423  mov     [rsp+440h+var_420], rax
0x18001b428  mov     r8, rdi; char *
0x18001b42b  mov     rdx, [rbx]; char *
0x18001b42e  lea     rcx, [rsp+440h+var_420]; this
0x18001b433  call    ?StartActivity@WhesvcModuleActivity@WhesvcTelemetryProvider@@QEAAXPEBD0@Z; WhesvcTelemetryProvider::WhesvcModuleActivity::StartActivity(char const *,char const *)
0x18001b438  nop
0x18001b439  mov     rax, [r12]
0x18001b43d  mov     qword ptr [r12], 0
0x18001b445  mov     rbx, [r14+18h]
0x18001b449  mov     [r14+18h], rax
0x18001b44d  mov     edi, 58h ; 'X'
0x18001b452  test    rbx, rbx
0x18001b455  jz      short loc_18001B494
0x18001b457  lea     rcx, [rbx+38h]
0x18001b45b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001b460  lea     rcx, [rbx+18h]
0x18001b464  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001b469  mov     rcx, [rbx+8]; void *
0x18001b46d  test    rcx, rcx
0x18001b470  jz      short loc_18001B477
0x18001b472  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b477  mov     rcx, [rbx]; void *
0x18001b47a  test    rcx, rcx
0x18001b47d  jz      short loc_18001B489
0x18001b47f  mov     edx, 18h; unsigned __int64
0x18001b484  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b489  mov     rdx, rdi; unsigned __int64
0x18001b48c  mov     rcx, rbx; void *
0x18001b48f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b494  xor     r8d, r8d
0x18001b497  lea     rdx, [rsp+440h+var_420]
0x18001b49c  lea     rcx, [rbp+340h+var_2D0]
0x18001b4a0  call    ??0?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18001b4a5  lea     rbx, ??_7WhesvcModuleActivity@WhesvcTelemetryProvider@@6B@; const WhesvcTelemetryProvider::WhesvcModuleActivity::`vftable'
0x18001b4ac  mov     [rbp+340h+var_2D0], rbx
0x18001b4b0  cmp     dword ptr [rsi+138h], 0
0x18001b4b7  setnz   r8b
0x18001b4bb  mov     rdx, rsi
0x18001b4be  lea     rcx, [rbp+340h+var_180]
0x18001b4c5  call    ??0?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18001b4ca  mov     [rbp+340h+var_180], rbx
0x18001b4d1  lea     rdx, [rbp+340h+var_2D0]
0x18001b4d5  mov     rcx, rsi
0x18001b4d8  call    ??4?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x18001b4dd  mov     [rbp+340h+var_180], rbx
0x18001b4e4  lea     rcx, [rbp+340h+var_180]
0x18001b4eb  call    ?Destroy@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001b4f0  lea     rcx, [rbp+340h+var_180]
0x18001b4f7  call    ??1?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001b4fc  mov     [rbp+340h+var_2D0], rbx
0x18001b500  lea     rcx, [rbp+340h+var_2D0]
0x18001b504  call    ?Destroy@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001b509  lea     rcx, [rbp+340h+var_2D0]
0x18001b50d  call    ??1?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001b512  mov     [rsp+440h+var_420], rbx
0x18001b517  lea     rcx, [rsp+440h+var_420]
0x18001b51c  call    ?Destroy@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001b521  lea     rcx, [rsp+440h+var_420]
0x18001b526  call    ??1?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001b52b  mov     rbx, [r12]
0x18001b52f  test    rbx, rbx
0x18001b532  jz      short loc_18001B571
0x18001b534  lea     rcx, [rbx+38h]
0x18001b538  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001b53d  lea     rcx, [rbx+18h]
0x18001b541  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001b546  mov     rcx, [rbx+8]; void *
0x18001b54a  test    rcx, rcx
0x18001b54d  jz      short loc_18001B554
0x18001b54f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b554  mov     rcx, [rbx]; void *
0x18001b557  test    rcx, rcx
0x18001b55a  jz      short loc_18001B566
0x18001b55c  mov     edx, 18h; unsigned __int64
0x18001b561  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b566  mov     rdx, rdi; unsigned __int64
0x18001b569  mov     rcx, rbx; void *
0x18001b56c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b571  mov     rcx, [r15]; hObject
0x18001b574  lea     rdx, [rcx-1]
0x18001b578  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001b57c  ja      short loc_18001B584
0x18001b57e  call    cs:__imp_CloseHandle
0x18001b584  mov     rax, r14
0x18001b587  mov     rcx, [rbp+340h+var_30]
0x18001b58e  xor     rcx, rsp; StackCookie
0x18001b591  call    __security_check_cookie
0x18001b596  lea     r11, [rsp+440h+var_20]
0x18001b59e  mov     rbx, [r11+40h]
0x18001b5a2  mov     rsi, [r11+48h]
0x18001b5a6  mov     rsp, r11
0x18001b5a9  pop     r15
0x18001b5ab  pop     r14
0x18001b5ad  pop     r12
0x18001b5af  pop     rdi
0x18001b5b0  pop     rbp
0x18001b5b1  retn
```
