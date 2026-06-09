# CTsBusUMBus::InitializeBus(utl::unique_ptr<ITsPropertyCfg,utl::default_delete<ITsPropertyCfg>>)

- ea: `0x180045b20`
- end: `0x180045c47`
- name: `?InitializeBus@CTsBusUMBus@@UEAAJV?$unique_ptr@VITsPropertyCfg@@U?$default_delete@VITsPropertyCfg@@@utl@@@utl@@@Z`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000abc0`
- `0x18000b8f8`
- `0x18000f79c`
- `0x18002e974`
- `0x180045ab8`
- `0x180045b20`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045b58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045b58`

## pseudocode

```c
__int64 __fastcall CTsBusUMBus::InitializeBus(__int64 a1, _QWORD *a2)
{
  __int64 *v2; // rdi
  HRESULT Instance; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, __int64); // rbx
  _QWORD *PropertyStoreFromCfg; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // rdx
  char v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = (__int64 *)(a1 + 456);
  Instance = CoCreateInstance(
               &GUID_9197e04d_2b9f_4849_8bf7_75294eb5c043,
               0,
               0x17u,
               &GUID_712f2e95_9b00_4c34_b049_bd3c9c1402cc,
               (LPVOID *)(a1 + 456));
  if ( Instance >= 0 && (v6 = *v2) != 0 )
  {
    v7 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v6 + 48LL);
    PropertyStoreFromCfg = (_QWORD *)CTsBusUMBus::GetPropertyStoreFromCfg(&v12, *a2);
    Instance = v7(v6, a1 + 8, *PropertyStoreFromCfg, 0, a1 + 464);
    TCntPtr<IDispatch>::SafeRelease(&v12);
    if ( (Instance < 0 || !*(_QWORD *)(a1 + 464))
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 13;
LABEL_13:
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v10,
        &WPP_6d1c079da0c63cec2f751b57a91d015f_Traceguids,
        CurrentThreadActivityIdPrefix,
        Instance);
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 12;
    goto LABEL_13;
  }
  utl::unique_ptr<ITsPropertyCfg,utl::default_delete<ITsPropertyCfg>>::~unique_ptr<ITsPropertyCfg,utl::default_delete<ITsPropertyCfg>>(a2);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180045b20  mov     [rsp+arg_8], rbx
0x180045b25  mov     [rsp+arg_10], rbp
0x180045b2a  push    rsi
0x180045b2b  push    rdi
0x180045b2c  push    r14
0x180045b2e  sub     rsp, 30h
0x180045b32  lea     rdi, [rcx+1C8h]
0x180045b39  mov     r14, rdx
0x180045b3c  xor     edx, edx; pUnkOuter
0x180045b3e  mov     [rsp+48h+ppv], rdi; ppv
0x180045b43  mov     rsi, rcx
0x180045b46  lea     r9, _GUID_712f2e95_9b00_4c34_b049_bd3c9c1402cc; riid
0x180045b4d  lea     rcx, _GUID_9197e04d_2b9f_4849_8bf7_75294eb5c043; rclsid
0x180045b54  lea     r8d, [rdx+17h]; dwClsContext
0x180045b58  call    cs:__imp_CoCreateInstance
0x180045b5e  mov     ebx, eax
0x180045b60  test    eax, eax
0x180045b62  js      short loc_180045BE3
0x180045b64  mov     rdi, [rdi]
0x180045b67  test    rdi, rdi
0x180045b6a  jz      short loc_180045BE3
0x180045b6c  mov     rax, [rdi]
0x180045b6f  lea     rcx, [rsp+48h+arg_0]
0x180045b74  mov     rdx, [r14]
0x180045b77  mov     rbx, [rax+30h]
0x180045b7b  call    ?GetPropertyStoreFromCfg@CTsBusUMBus@@KA?AV?$ComPlainSmartPtr@UIPropertyStore@@@@PEAVITsPropertyCfg@@@Z; CTsBusUMBus::GetPropertyStoreFromCfg(ITsPropertyCfg *)
0x180045b80  lea     rbp, [rsi+1D0h]
0x180045b87  xor     r9d, r9d
0x180045b8a  lea     rdx, [rsi+8]
0x180045b8e  mov     [rsp+48h+ppv], rbp
0x180045b93  mov     rcx, rdi
0x180045b96  mov     r8, [rax]
0x180045b99  mov     rax, rbx
0x180045b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ba1  lea     rcx, [rsp+48h+arg_0]
0x180045ba6  mov     ebx, eax
0x180045ba8  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x180045bad  test    ebx, ebx
0x180045baf  js      short loc_180045BB8
0x180045bb1  cmp     qword ptr [rbp+0], 0
0x180045bb6  jnz     short loc_180045C2A
0x180045bb8  mov     rax, cs:WPP_GLOBAL_Control
0x180045bbf  lea     rcx, WPP_GLOBAL_Control
0x180045bc6  cmp     rax, rcx
0x180045bc9  jz      short loc_180045C2A
0x180045bcb  test    byte ptr [rax+1Ch], 1
0x180045bcf  jz      short loc_180045C2A
0x180045bd1  cmp     byte ptr [rax+19h], 2
0x180045bd5  jb      short loc_180045C2A
0x180045bd7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045bdc  mov     edx, 0Dh
0x180045be1  jmp     short loc_180045C0C
0x180045be3  mov     rax, cs:WPP_GLOBAL_Control
0x180045bea  lea     rcx, WPP_GLOBAL_Control
0x180045bf1  cmp     rax, rcx
0x180045bf4  jz      short loc_180045C2A
0x180045bf6  test    byte ptr [rax+1Ch], 1
0x180045bfa  jz      short loc_180045C2A
0x180045bfc  cmp     byte ptr [rax+19h], 2
0x180045c00  jb      short loc_180045C2A
0x180045c02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045c07  mov     edx, 0Ch
0x180045c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c13  lea     r8, WPP_6d1c079da0c63cec2f751b57a91d015f_Traceguids
0x180045c1a  mov     r9d, eax
0x180045c1d  mov     dword ptr [rsp+48h+ppv], ebx
0x180045c21  mov     rcx, [rcx+10h]
0x180045c25  call    WPP_SF_Dd
0x180045c2a  mov     rcx, r14
0x180045c2d  call    ??1?$unique_ptr@VITsPropertyCfg@@U?$default_delete@VITsPropertyCfg@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ITsPropertyCfg,utl::default_delete<ITsPropertyCfg>>::~unique_ptr<ITsPropertyCfg,utl::default_delete<ITsPropertyCfg>>(void)
0x180045c32  mov     rbp, [rsp+48h+arg_10]
0x180045c37  mov     eax, ebx
0x180045c39  mov     rbx, [rsp+48h+arg_8]
0x180045c3e  add     rsp, 30h
0x180045c42  pop     r14
0x180045c44  pop     rdi
0x180045c45  pop     rsi
0x180045c46  retn
```
