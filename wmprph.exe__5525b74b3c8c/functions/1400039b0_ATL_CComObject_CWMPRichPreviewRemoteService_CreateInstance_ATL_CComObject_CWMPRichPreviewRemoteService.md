# ATL::CComObject<CWMPRichPreviewRemoteService>::CreateInstance(ATL::CComObject<CWMPRichPreviewRemoteService> * *)

- ea: `0x1400039b0`
- end: `0x140003a9d`
- name: `?CreateInstance@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@SAJPEAPEAV12@@Z`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x140003d60`

## callees

- `0x140001008`
- `0x140001014`
- `0x140002190`
- `0x1400039b0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140003a5e`
- `ole32!CoCreateInstance` at `0x140003a5e`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::CreateInstance(LPVOID **a1)
{
  LPVOID *v3; // rax
  LPVOID *v4; // rbx
  unsigned int Instance; // esi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (LPVOID *)operator new(0x48u);
  v4 = v3;
  if ( !v3 )
  {
    Instance = -2147024882;
    goto LABEL_7;
  }
  *((_DWORD *)v3 + 6) = 0;
  v3[5] = 0;
  v3[6] = 0;
  v3[7] = 0;
  *((_DWORD *)v3 + 16) = 0;
  *((_WORD *)v3 + 34) = 4;
  *v3 = &ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>'};
  v3[1] = &ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IServiceProviderImpl<CWMPRichPreviewRemoteService>'};
  v3[2] = &ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `IWMPRemoteMediaServices'};
  _InterlockedIncrement(&dword_1400153D8);
  Instance = CoCreateInstance(
               &GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f,
               0,
               0x17u,
               &GUID_f676c15d_596a_4ce2_8234_33996f445db1,
               v3 + 5);
  if ( Instance )
  {
    ATL::CComObject<CWMPRichPreviewRemoteService>::~CComObject<CWMPRichPreviewRemoteService>((__int64)v4);
    operator delete(v4, 0x48u);
LABEL_7:
    v4 = 0;
  }
  *a1 = v4;
  return Instance;
}

```

## disassembly

```asm
0x1400039b0  mov     [rsp+arg_0], rbx
0x1400039b5  mov     [rsp+arg_8], rsi
0x1400039ba  push    rdi
0x1400039bb  sub     rsp, 30h
0x1400039bf  mov     rdi, rcx
0x1400039c2  test    rcx, rcx
0x1400039c5  jnz     short loc_1400039D1
0x1400039c7  mov     eax, 80004003h
0x1400039cc  jmp     loc_140003A8D
0x1400039d1  mov     qword ptr [rcx], 0
0x1400039d8  mov     ecx, 48h ; 'H'; Size
0x1400039dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400039e2  mov     rbx, rax
0x1400039e5  test    rax, rax
0x1400039e8  jz      loc_140003A81
0x1400039ee  mov     dword ptr [rax+18h], 0
0x1400039f5  mov     qword ptr [rax+28h], 0
0x1400039fd  mov     qword ptr [rax+30h], 0
0x140003a05  mov     qword ptr [rax+38h], 0
0x140003a0d  mov     dword ptr [rax+40h], 0
0x140003a14  mov     word ptr [rax+44h], 4
0x140003a1a  lea     rax, ??_7?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@6B?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>'}
0x140003a21  mov     [rbx], rax
0x140003a24  lea     rax, ??_7?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@6B?$IServiceProviderImpl@VCWMPRichPreviewRemoteService@@@1@@; const ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `ATL::IServiceProviderImpl<CWMPRichPreviewRemoteService>'}
0x140003a2b  mov     [rbx+8], rax
0x140003a2f  lea     rax, ??_7?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@6BIWMPRemoteMediaServices@@@; const ATL::CComObject<CWMPRichPreviewRemoteService>::`vftable'{for `IWMPRemoteMediaServices'}
0x140003a36  mov     [rbx+10h], rax
0x140003a3a  lock inc cs:dword_1400153D8
0x140003a41  xor     edx, edx; pUnkOuter
0x140003a43  lea     rax, [rbx+28h]
0x140003a47  lea     r9, _GUID_f676c15d_596a_4ce2_8234_33996f445db1; riid
0x140003a4e  mov     [rsp+38h+ppv], rax; ppv
0x140003a53  lea     rcx, _GUID_50ef4544_ac9f_4a8e_b21b_8a26180db13f; rclsid
0x140003a5a  lea     r8d, [rdx+17h]; dwClsContext
0x140003a5e  call    cs:__imp_CoCreateInstance
0x140003a64  mov     esi, eax
0x140003a66  test    eax, eax
0x140003a68  jz      short loc_140003A88
0x140003a6a  mov     rcx, rbx
0x140003a6d  call    ??1?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@QEAA@XZ; ATL::CComObject<CWMPRichPreviewRemoteService>::~CComObject<CWMPRichPreviewRemoteService>(void)
0x140003a72  mov     edx, 48h ; 'H'; unsigned __int64
0x140003a77  mov     rcx, rbx; void *
0x140003a7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003a7f  jmp     short loc_140003A86
0x140003a81  mov     esi, 8007000Eh
0x140003a86  xor     ebx, ebx
0x140003a88  mov     [rdi], rbx
0x140003a8b  mov     eax, esi
0x140003a8d  mov     rbx, [rsp+38h+arg_0]
0x140003a92  mov     rsi, [rsp+38h+arg_8]
0x140003a97  add     rsp, 30h
0x140003a9b  pop     rdi
0x140003a9c  retn
```
