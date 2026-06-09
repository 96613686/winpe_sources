# CSupportedDeviceEnum::_Init(void)

- ea: `0x18000d63c`
- end: `0x18000d9a7`
- name: `?_Init@CSupportedDeviceEnum@@AEAAJXZ`
- size: `875`
- prototype: `__int64 __fastcall(CSupportedDeviceEnum *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ba84`

## callees

- `0x18000d540`
- `0x18000d63c`
- `0x18000e4d4`
- `0x180021590`
- `0x18002ff5c`
- `0x180035590`
- `0x180039e80`
- `0x180055bbc`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000d8dd`
- `ole32!CoTaskMemFree` at `0x18000d8f6`
- `ole32!CoTaskMemFree` at `0x18000d8dd`
- `ole32!CoTaskMemFree` at `0x18000d8f6`
- `ole32!CoCreateInstance` at `0x18000d6f0`
- `ole32!CoCreateInstance` at `0x18000d6f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSupportedDeviceEnum::_Init(CSupportedDeviceEnum *this)
{
  int WpdDevicePathFromAnyPath; // ebx
  __int64 v3; // rax
  HRESULT Instance; // eax
  CSupportedDeviceEnum *v5; // rcx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int Devices; // eax
  unsigned int v10; // r9d
  _QWORD *v11; // rdi
  __int64 i; // rsi
  const WCHAR *v13; // rdx
  int v14; // r12d
  unsigned int v15; // r9d
  int v16; // eax
  int v17; // edx
  unsigned __int16 *v18; // r9
  __int64 j; // rsi
  void *v20; // rcx
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+4Ch] [rbp-B4h] BYREF
  struct IPortableDeviceManager *ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v28[264]; // [rsp+70h] [rbp-90h] BYREF

  pv[0] = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v23 = 0;
  ppv = 0;
  if ( *((_QWORD *)this + 1) )
  {
    WpdDevicePathFromAnyPath = -2147418113;
LABEL_45:
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_46:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      WPP_SF_d(v6[2], 19, &WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids, (unsigned int)WpdDevicePathFromAnyPath);
    goto LABEL_49;
  }
  v3 = IsolationAwareDPA_Create(4);
  *((_QWORD *)this + 1) = v3;
  if ( !v3 )
  {
    WpdDevicePathFromAnyPath = -2147024882;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_49;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_46;
    v7 = 14;
    v8 = 2147942414LL;
LABEL_44:
    WPP_SF_d(v6[2], v7, &WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids, v8);
    goto LABEL_45;
  }
  Instance = CoCreateInstance(
               &CLSID_PortableDeviceManager,
               0,
               1u,
               &GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40,
               (LPVOID *)&ppv);
  WpdDevicePathFromAnyPath = Instance;
  if ( Instance < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_49;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_46;
    v7 = 15;
    v8 = (unsigned int)Instance;
    goto LABEL_44;
  }
  Devices = CSupportedDeviceEnum::_GetDevices(v5, ppv, (unsigned __int16 ***)pv, &v22);
  WpdDevicePathFromAnyPath = Devices;
  v11 = pv[0];
  if ( Devices < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids,
        (unsigned int)Devices);
LABEL_32:
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_33;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v22 )
      goto LABEL_32;
    v13 = (const WCHAR *)v11[i];
    if ( !v13 )
      continue;
    v14 = 0;
    *(GUID *)pv = GUID_DEVINTERFACE_WPD;
    WpdDevicePathFromAnyPath = GetWpdDevicePathFromAnyPath((GUID *)pv, v13, v28, v10);
    if ( WpdDevicePathFromAnyPath < 0 )
      break;
LABEL_18:
    v24 = 4;
    v23 = 0;
    if ( ((int (__fastcall *)(struct IPortableDeviceManager *, _QWORD, const wchar_t *, int *, int *, int *))ppv->lpVtbl->GetDeviceProperty)(
           ppv,
           v11[i],
           L"PortableDeviceNameSpaceExcludeFromShell",
           &v25,
           &v24,
           &v23) < 0 )
    {
      if ( v14 == 1 )
        continue;
    }
    else if ( v23 == 4 && v25 )
    {
      continue;
    }
    v16 = CSupportedDeviceEnum::_AddDevice(this, v28);
    WpdDevicePathFromAnyPath = v16;
    if ( v16 < 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 18;
        v18 = v28;
        goto LABEL_28;
      }
      goto LABEL_33;
    }
  }
  *(GUID *)pv = GUID_DEVINTERFACE_WPD_PRIVATE;
  v16 = GetWpdDevicePathFromAnyPath((GUID *)pv, (PCWSTR)v11[i], v28, v15);
  WpdDevicePathFromAnyPath = v16;
  if ( v16 >= 0 )
  {
    v14 = 1;
    goto LABEL_18;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v17 = 17;
    v18 = (unsigned __int16 *)v11[i];
LABEL_28:
    WPP_SF_Sd(
      (unsigned int)v6[2],
      v17,
      (unsigned int)&WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids,
      (_DWORD)v18,
      v16);
    goto LABEL_32;
  }
LABEL_33:
  if ( v11 )
  {
    for ( j = 0; (unsigned int)j < v22; j = (unsigned int)(j + 1) )
    {
      v20 = (void *)v11[j];
      if ( v20 )
      {
        CoTaskMemFree(v20);
        v11[j] = 0;
      }
    }
    CoTaskMemFree(v11);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( WpdDevicePathFromAnyPath < 0 )
    goto LABEL_46;
LABEL_49:
  if ( ppv )
    ((void (__fastcall *)(struct IPortableDeviceManager *))ppv->lpVtbl->Release)(ppv);
  return (unsigned int)WpdDevicePathFromAnyPath;
}

```

## disassembly

```asm
0x18000d63c  mov     [rsp-8+arg_8], rbx
0x18000d641  mov     [rsp-8+arg_10], rsi
0x18000d646  push    rbp
0x18000d647  push    rdi
0x18000d648  push    r12
0x18000d64a  push    r14
0x18000d64c  push    r15
0x18000d64e  lea     rbp, [rsp-190h]
0x18000d656  sub     rsp, 290h
0x18000d65d  mov     rax, cs:__security_cookie
0x18000d664  xor     rax, rsp
0x18000d667  mov     [rbp+1B0h+var_30], rax
0x18000d66e  mov     r15, rcx
0x18000d671  mov     [rsp+2B0h+pv], 0
0x18000d67a  mov     [rsp+2B0h+var_270], 0
0x18000d682  mov     [rsp+2B0h+var_268], 0
0x18000d68a  mov     [rsp+2B0h+var_264], 0
0x18000d692  mov     [rsp+2B0h+var_26C], 0
0x18000d69a  mov     [rsp+2B0h+var_260], 0
0x18000d6a3  lea     r12, WPP_GLOBAL_Control
0x18000d6aa  cmp     qword ptr [rcx+8], 0
0x18000d6af  jz      short loc_18000D6BB
0x18000d6b1  mov     ebx, 8000FFFFh
0x18000d6b6  jmp     loc_18000D938
0x18000d6bb  mov     ecx, 4
0x18000d6c0  call    IsolationAwareDPA_Create
0x18000d6c5  mov     [r15+8], rax
0x18000d6c9  test    rax, rax
0x18000d6cc  jz      loc_18000D909
0x18000d6d2  lea     rax, [rsp+2B0h+var_260]
0x18000d6d7  mov     [rsp+2B0h+ppv], rax; ppv
0x18000d6dc  lea     r9, _GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40; riid
0x18000d6e3  xor     edx, edx; pUnkOuter
0x18000d6e5  lea     r8d, [rdx+1]; dwClsContext
0x18000d6e9  lea     rcx, CLSID_PortableDeviceManager; rclsid
0x18000d6f0  call    cs:__imp_CoCreateInstance
0x18000d6f6  mov     ebx, eax
0x18000d6f8  test    eax, eax
0x18000d6fa  jns     short loc_18000D723
0x18000d6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d703  cmp     rcx, r12
0x18000d706  jz      loc_18000D963
0x18000d70c  test    byte ptr [rcx+1Ch], 2
0x18000d710  jz      loc_18000D93F
0x18000d716  mov     edx, 0Fh
0x18000d71b  mov     r9d, eax
0x18000d71e  jmp     loc_18000D928
0x18000d723  lea     r9, [rsp+2B0h+var_270]; unsigned int *
0x18000d728  lea     r8, [rsp+2B0h+pv]; unsigned __int16 ***
0x18000d72d  mov     rdx, [rsp+2B0h+var_260]; struct IPortableDeviceManager *
0x18000d732  call    ?_GetDevices@CSupportedDeviceEnum@@AEAAJPEAUIPortableDeviceManager@@PEAPEAPEAGPEAK@Z; CSupportedDeviceEnum::_GetDevices(IPortableDeviceManager *,ushort * * *,ulong *)
0x18000d737  mov     ebx, eax
0x18000d739  mov     rdi, [rsp+2B0h+pv]
0x18000d73e  test    eax, eax
0x18000d740  jns     short loc_18000D779
0x18000d742  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d749  cmp     rcx, r12
0x18000d74c  jz      loc_18000D8C7
0x18000d752  test    byte ptr [rcx+1Ch], 2
0x18000d756  jz      loc_18000D8C7
0x18000d75c  mov     edx, 10h
0x18000d761  mov     r9d, eax
0x18000d764  lea     r8, WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids
0x18000d76b  mov     rcx, [rcx+10h]
0x18000d76f  call    WPP_SF_d
0x18000d774  jmp     loc_18000D8C0
0x18000d779  xor     esi, esi
0x18000d77b  cmp     esi, [rsp+2B0h+var_270]
0x18000d77f  jnb     loc_18000D8B9
0x18000d785  mov     rdx, [rdi+rsi*8]; DevicePath
0x18000d789  test    rdx, rdx
0x18000d78c  jz      loc_18000D855
0x18000d792  xor     r12d, r12d
0x18000d795  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_WPD.Data1
0x18000d79c  movdqu  xmmword ptr [rsp+2B0h+pv], xmm0
0x18000d7a2  lea     r8, [rsp+2B0h+var_240]; unsigned __int16 *
0x18000d7a7  lea     rcx, [rsp+2B0h+pv]; AliasInterfaceClassGuid
0x18000d7ac  call    ?GetWpdDevicePathFromAnyPath@@YAJU_GUID@@PEBGPEAGI@Z; GetWpdDevicePathFromAnyPath(_GUID,ushort const *,ushort *,uint)
0x18000d7b1  mov     ebx, eax
0x18000d7b3  test    eax, eax
0x18000d7b5  jns     short loc_18000D7E3
0x18000d7b7  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_WPD_PRIVATE.Data1
0x18000d7be  movdqu  xmmword ptr [rsp+2B0h+pv], xmm0
0x18000d7c4  lea     r8, [rsp+2B0h+var_240]; unsigned __int16 *
0x18000d7c9  mov     rdx, [rdi+rsi*8]; DevicePath
0x18000d7cd  lea     rcx, [rsp+2B0h+pv]; AliasInterfaceClassGuid
0x18000d7d2  call    ?GetWpdDevicePathFromAnyPath@@YAJU_GUID@@PEBGPEAGI@Z; GetWpdDevicePathFromAnyPath(_GUID,ushort const *,ushort *,uint)
0x18000d7d7  mov     ebx, eax
0x18000d7d9  test    eax, eax
0x18000d7db  js      short loc_18000D85C
0x18000d7dd  mov     r12d, 1
0x18000d7e3  mov     [rsp+2B0h+var_268], 4
0x18000d7eb  mov     [rsp+2B0h+var_26C], 0
0x18000d7f3  mov     rcx, [rsp+2B0h+var_260]
0x18000d7f8  mov     rax, [rcx]
0x18000d7fb  lea     rdx, [rsp+2B0h+var_26C]
0x18000d800  mov     [rsp+2B0h+var_288], rdx
0x18000d805  lea     rdx, [rsp+2B0h+var_268]
0x18000d80a  mov     [rsp+2B0h+ppv], rdx
0x18000d80f  lea     r9, [rsp+2B0h+var_264]
0x18000d814  lea     r8, aPortabledevice; "PortableDeviceNameSpaceExcludeFromShell"
0x18000d81b  mov     rdx, [rdi+rsi*8]
0x18000d81f  mov     rax, [rax+40h]
0x18000d823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d828  test    eax, eax
0x18000d82a  js      short loc_18000D83C
0x18000d82c  cmp     [rsp+2B0h+var_26C], 4
0x18000d831  jnz     short loc_18000D842
0x18000d833  cmp     [rsp+2B0h+var_264], 0
0x18000d838  jnz     short loc_18000D855
0x18000d83a  jmp     short loc_18000D842
0x18000d83c  cmp     r12d, 1
0x18000d840  jz      short loc_18000D855
0x18000d842  lea     rdx, [rsp+2B0h+var_240]; unsigned __int16 *
0x18000d847  mov     rcx, r15; this
0x18000d84a  call    ?_AddDevice@CSupportedDeviceEnum@@AEAAJPEBG@Z; CSupportedDeviceEnum::_AddDevice(ushort const *)
0x18000d84f  mov     ebx, eax
0x18000d851  test    eax, eax
0x18000d853  js      short loc_18000D894
0x18000d855  inc     esi
0x18000d857  jmp     loc_18000D77B
0x18000d85c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d863  lea     r12, WPP_GLOBAL_Control
0x18000d86a  cmp     rcx, r12
0x18000d86d  jz      short loc_18000D8C7
0x18000d86f  test    byte ptr [rcx+1Ch], 2
0x18000d873  jz      short loc_18000D8C7
0x18000d875  mov     edx, 11h
0x18000d87a  mov     r9, [rdi+rsi*8]
0x18000d87e  mov     dword ptr [rsp+2B0h+ppv], eax
0x18000d882  lea     r8, WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids
0x18000d889  mov     rcx, [rcx+10h]
0x18000d88d  call    WPP_SF_Sd
0x18000d892  jmp     short loc_18000D8C0
0x18000d894  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d89b  lea     r12, WPP_GLOBAL_Control
0x18000d8a2  cmp     rcx, r12
0x18000d8a5  jz      short loc_18000D8C7
0x18000d8a7  test    byte ptr [rcx+1Ch], 2
0x18000d8ab  jz      short loc_18000D8C7
0x18000d8ad  mov     edx, 12h
0x18000d8b2  lea     r9, [rsp+2B0h+var_240]
0x18000d8b7  jmp     short loc_18000D87E
0x18000d8b9  lea     r12, WPP_GLOBAL_Control
0x18000d8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8c7  test    rdi, rdi
0x18000d8ca  jz      short loc_18000D903
0x18000d8cc  xor     esi, esi
0x18000d8ce  cmp     [rsp+2B0h+var_270], esi
0x18000d8d2  jbe     short loc_18000D8F3
0x18000d8d4  mov     rcx, [rdi+rsi*8]; pv
0x18000d8d8  test    rcx, rcx
0x18000d8db  jz      short loc_18000D8EB
0x18000d8dd  call    cs:__imp_CoTaskMemFree
0x18000d8e3  mov     qword ptr [rdi+rsi*8], 0
0x18000d8eb  inc     esi
0x18000d8ed  cmp     esi, [rsp+2B0h+var_270]
0x18000d8f1  jb      short loc_18000D8D4
0x18000d8f3  mov     rcx, rdi; pv
0x18000d8f6  call    cs:__imp_CoTaskMemFree
0x18000d8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d903  test    ebx, ebx
0x18000d905  js      short loc_18000D93F
0x18000d907  jmp     short loc_18000D963
0x18000d909  mov     ebx, 8007000Eh
0x18000d90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d915  cmp     rcx, r12
0x18000d918  jz      short loc_18000D963
0x18000d91a  test    byte ptr [rcx+1Ch], 2
0x18000d91e  jz      short loc_18000D93F
0x18000d920  mov     edx, 0Eh
0x18000d925  mov     r9d, ebx
0x18000d928  lea     r8, WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids
0x18000d92f  mov     rcx, [rcx+10h]
0x18000d933  call    WPP_SF_d
0x18000d938  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d93f  cmp     rcx, r12
0x18000d942  jz      short loc_18000D963
0x18000d944  test    byte ptr [rcx+1Ch], 2
0x18000d948  jz      short loc_18000D963
0x18000d94a  mov     edx, 13h
0x18000d94f  mov     r9d, ebx
0x18000d952  lea     r8, WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids
0x18000d959  mov     rcx, [rcx+10h]
0x18000d95d  call    WPP_SF_d
0x18000d962  nop
0x18000d963  mov     rcx, [rsp+2B0h+var_260]
0x18000d968  test    rcx, rcx
0x18000d96b  jz      short loc_18000D97A
0x18000d96d  mov     rax, [rcx]
0x18000d970  mov     rax, [rax+10h]
0x18000d974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d979  nop
0x18000d97a  mov     eax, ebx
0x18000d97c  mov     rcx, [rbp+1B0h+var_30]
0x18000d983  xor     rcx, rsp; StackCookie
0x18000d986  call    __security_check_cookie
0x18000d98b  lea     r11, [rsp+2B0h+var_20]
0x18000d993  mov     rbx, [r11+38h]
0x18000d997  mov     rsi, [r11+40h]
0x18000d99b  mov     rsp, r11
0x18000d99e  pop     r15
0x18000d9a0  pop     r14
0x18000d9a2  pop     r12
0x18000d9a4  pop     rdi
0x18000d9a5  pop     rbp
0x18000d9a6  retn
```
