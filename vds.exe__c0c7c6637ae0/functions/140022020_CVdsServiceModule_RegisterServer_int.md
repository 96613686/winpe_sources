# CVdsServiceModule::RegisterServer(int)

- ea: `0x140022020`
- end: `0x1400223f7`
- name: `?RegisterServer@CVdsServiceModule@@QEAAJH@Z`
- size: `983`
- prototype: `__int64 __fastcall(CVdsServiceModule *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140036870`

## callees

- `0x140013298`
- `0x140022020`
- `0x14002e123`
- `0x140031658`
- `0x140033374`
- `0x140034d84`
- `0x140035f8c`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400223c5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400223c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400220c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400220c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002232f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002234d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002236b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022389`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002232f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002234d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002236b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002210a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400221f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002210a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400221f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400222fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400222fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140022242`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140022242`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002228b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400222d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002228b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400222d1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140022219`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140022219`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400221ea`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400221ea`
- `vdsutil!InitializeSecurityDescriptorHelper` at `0x1400221b5`
- `vdsutil!InitializeSecurityDescriptorHelper` at `0x1400221b5`
- `vdsutil!VdsHeapFree` at `0x14002233d`
- `vdsutil!VdsHeapFree` at `0x14002235b`
- `vdsutil!VdsHeapFree` at `0x140022379`
- `vdsutil!VdsHeapFree` at `0x140022397`
- `vdsutil!VdsHeapFree` at `0x14002233d`
- `vdsutil!VdsHeapFree` at `0x14002235b`
- `vdsutil!VdsHeapFree` at `0x140022379`
- `vdsutil!VdsHeapFree` at `0x140022397`
- `vdsutil!VdsTraceEx` at `0x140022324`
- `vdsutil!VdsTraceEx` at `0x140022324`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140022099`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140022099`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400223d0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400223d0`

## string_xrefs

- `0x140022315`: `CVdsServiceModule::RegisterServer, 10, %lX`
- `0x1400221d0`: `CVdsServiceModule::RegisterServer, 5, %lX`
- `0x14002225d`: `CVdsServiceModule::RegisterServer, 7, %lX`
- `0x14002211f`: `CVdsServiceModule::RegisterServer, 3, %lX`
- `0x140022209`: `CVdsServiceModule::RegisterServer, 6, %lX`
- `0x1400222a6`: `CVdsServiceModule::RegisterServer, 8, %lX`
- `0x1400222ec`: `CVdsServiceModule::RegisterServer, 9, %lX`
- `0x140022087`: `CVdsServiceModule::RegisterServer()`
- `0x1400220d4`: `CVdsServiceModule::RegisterServer, 1, %lX`
- `0x1400220f1`: `CVdsServiceModule::RegisterServer, 2, %lX`
- `0x140022181`: `CVdsServiceModule::RegisterServer, 4, %lX`
- `0x1400222c5`: `AccessPermission`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsServiceModule::RegisterServer(CVdsServiceModule *this)
{
  unsigned int v2; // esi
  HRESULT v3; // eax
  signed int v4; // edi
  const char *v5; // r8
  signed int v6; // eax
  ATL::_ATL_OBJMAP_ENTRY30 *v7; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax
  int v9; // eax
  signed int LastError; // eax
  DWORD cbData; // ebx
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rbx
  HANDLE v23; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwBufferLength; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  _BYTE v33[24]; // [rsp+88h] [rbp-78h] BYREF
  BYTE pSelfRelativeSecurityDescriptor[256]; // [rsp+A0h] [rbp-60h] BYREF

  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v2 = 0;
  dwBufferLength = 256;
  hKey = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v33, 0x5Eu, "CVdsServiceModule::RegisterServer()");
  memset_0(pSelfRelativeSecurityDescriptor, 0, sizeof(pSelfRelativeSecurityDescriptor));
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  v32 = 0;
  v3 = CoInitializeEx(0, 0);
  v4 = v3;
  if ( v3 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsServiceModule::RegisterServer, 1, %lX", (unsigned int)v3);
    goto LABEL_48;
  }
  if ( (unsigned int)CVdsServiceModule::Uninstall(this) )
  {
    if ( (unsigned int)CVdsServiceModule::Install(this) == 1 )
    {
      v7 = qword_14009B0C8;
      if ( qword_14009B0C8 )
      {
        while ( *(_QWORD *)v7 )
        {
          v4 = (*((__int64 (__fastcall **)(__int64))v7 + 1))(1);
          if ( v4 < 0 )
            goto LABEL_16;
          v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v7 + 7))();
          v4 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 1);
          if ( v4 < 0 )
            goto LABEL_16;
          v7 = (ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v7 + 72);
        }
      }
      v4 = ATL::CAtlModuleT<ATL::CComModule>::RegisterServer();
LABEL_16:
      if ( v4 >= 0 )
      {
        v9 = InitializeSecurityDescriptorHelper(1, pAbsoluteSecurityDescriptor, &v27, &v28, &v29, &v30);
        v2 = v9;
        if ( v9 )
        {
          if ( v9 > 0 )
            v4 = (unsigned __int16)v9 | 0x80070000;
          else
            v4 = v9;
          v5 = "CVdsServiceModule::RegisterServer, 5, %lX";
        }
        else if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, pSelfRelativeSecurityDescriptor, &dwBufferLength) )
        {
          cbData = GetSecurityDescriptorLength(pSelfRelativeSecurityDescriptor);
          v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID\\{F290BFB2-1864-45B1-8804-2654194A87E7}", 0, 0x2000000u, &hKey);
          v2 = v12;
          if ( v12 )
          {
            if ( v12 > 0 )
              v4 = (unsigned __int16)v12 | 0x80070000;
            else
              v4 = v12;
            v5 = "CVdsServiceModule::RegisterServer, 7, %lX";
          }
          else
          {
            v13 = RegSetValueExW(hKey, L"LaunchPermission", 0, 3u, pSelfRelativeSecurityDescriptor, cbData);
            v2 = v13;
            if ( v13 )
            {
              if ( v13 > 0 )
                v4 = (unsigned __int16)v13 | 0x80070000;
              else
                v4 = v13;
              v5 = "CVdsServiceModule::RegisterServer, 8, %lX";
            }
            else
            {
              v14 = RegSetValueExW(hKey, L"AccessPermission", 0, 3u, pSelfRelativeSecurityDescriptor, cbData);
              v2 = v14;
              if ( v14 )
              {
                if ( v14 > 0 )
                  v4 = (unsigned __int16)v14 | 0x80070000;
                else
                  v4 = v14;
                v5 = "CVdsServiceModule::RegisterServer, 9, %lX";
              }
              else
              {
                v15 = RegCloseKey(hKey);
                v2 = v15;
                if ( !v15 )
                  goto LABEL_48;
                if ( v15 > 0 )
                  v4 = (unsigned __int16)v15 | 0x80070000;
                else
                  v4 = v15;
                v5 = "CVdsServiceModule::RegisterServer, 10, %lX";
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          v5 = "CVdsServiceModule::RegisterServer, 6, %lX";
        }
      }
      else
      {
        v5 = "CVdsServiceModule::RegisterServer, 4, %lX";
      }
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      v5 = "CVdsServiceModule::RegisterServer, 3, %lX";
    }
  }
  else
  {
    v4 = -2147467259;
    v5 = "CVdsServiceModule::RegisterServer, 2, %lX";
  }
  VdsTraceEx(94, 0, v5, (unsigned int)v4);
LABEL_48:
  v16 = v27;
  ProcessHeap = GetProcessHeap();
  VdsHeapFree(ProcessHeap, 0, v16);
  v27 = 0;
  v18 = v28;
  v19 = GetProcessHeap();
  VdsHeapFree(v19, 0, v18);
  v28 = 0;
  v20 = v29;
  v21 = GetProcessHeap();
  VdsHeapFree(v21, 0, v20);
  v29 = 0;
  v22 = v30;
  v23 = GetProcessHeap();
  VdsHeapFree(v23, 0, v22);
  v30 = 0;
  if ( v4 < 0 )
    VdsLogError(0xC2000001, 0, 0, v2, 0x2010009u, 0);
  CoUninitialize();
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v33);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140022020  push    rbp
0x140022022  push    rbx
0x140022023  push    rsi
0x140022024  push    rdi
0x140022025  push    r14
0x140022027  push    r15
0x140022029  lea     rbp, [rsp-0B8h]
0x140022031  sub     rsp, 1B8h
0x140022038  mov     rax, cs:__security_cookie
0x14002203f  xor     rax, rsp
0x140022042  mov     [rbp+0E0h+var_40], rax
0x140022049  mov     rbx, rcx
0x14002204c  xor     r14d, r14d
0x14002204f  mov     [rsp+1E0h+var_1A0], r14
0x140022054  mov     [rsp+1E0h+var_198], r14
0x140022059  mov     [rsp+1E0h+var_190], r14
0x14002205e  mov     [rsp+1E0h+var_188], r14
0x140022063  mov     esi, r14d
0x140022066  mov     edi, 100h
0x14002206b  mov     [rsp+1E0h+dwBufferLength], edi
0x14002206f  mov     [rsp+1E0h+hKey], r14
0x140022074  xorps   xmm0, xmm0
0x140022077  xor     eax, eax
0x140022079  movups  [rsp+1E0h+pAbsoluteSecurityDescriptor], xmm0
0x14002207e  movups  [rsp+1E0h+var_170], xmm0
0x140022083  mov     [rbp+0E0h+var_160], rax
0x140022087  lea     r8, aCvdsservicemod_27; "CVdsServiceModule::RegisterServer()"
0x14002208e  lea     r15d, [r14+5Eh]
0x140022092  mov     edx, r15d
0x140022095  lea     rcx, [rbp+0E0h+var_158]
0x140022099  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002209f  nop
0x1400220a0  mov     r8d, edi; Size
0x1400220a3  xor     edx, edx; Val
0x1400220a5  lea     rcx, [rbp+0E0h+pSelfRelativeSecurityDescriptor]; void *
0x1400220a9  call    memset_0
0x1400220ae  xorps   xmm0, xmm0
0x1400220b1  xor     eax, eax
0x1400220b3  movups  [rsp+1E0h+pAbsoluteSecurityDescriptor], xmm0
0x1400220b8  movups  [rsp+1E0h+var_170], xmm0
0x1400220bd  mov     [rbp+0E0h+var_160], rax
0x1400220c1  xor     edx, edx; dwCoInit
0x1400220c3  xor     ecx, ecx; pvReserved
0x1400220c5  call    cs:__imp_CoInitializeEx
0x1400220cb  mov     edi, eax
0x1400220cd  test    eax, eax
0x1400220cf  jns     short loc_1400220E0
0x1400220d1  mov     r9d, eax
0x1400220d4  lea     r8, aCvdsservicemod_5; "CVdsServiceModule::RegisterServer, 1, %"...
0x1400220db  jmp     loc_14002231F
0x1400220e0  mov     rcx, rbx; this
0x1400220e3  call    ?Uninstall@CVdsServiceModule@@QEAAHXZ; CVdsServiceModule::Uninstall(void)
0x1400220e8  test    eax, eax
0x1400220ea  jnz     short loc_1400220FD
0x1400220ec  mov     edi, 80004005h
0x1400220f1  lea     r8, aCvdsservicemod; "CVdsServiceModule::RegisterServer, 2, %"...
0x1400220f8  jmp     loc_14002231C
0x1400220fd  mov     rcx, rbx; this
0x140022100  call    ?Install@CVdsServiceModule@@QEAAHXZ; CVdsServiceModule::Install(void)
0x140022105  cmp     eax, 1
0x140022108  jz      short loc_14002212B
0x14002210a  call    cs:__imp_GetLastError
0x140022110  mov     edi, eax
0x140022112  test    eax, eax
0x140022114  jle     short loc_14002211F
0x140022116  movzx   edi, ax
0x140022119  or      edi, 80070000h
0x14002211f  lea     r8, aCvdsservicemod_17; "CVdsServiceModule::RegisterServer, 3, %"...
0x140022126  jmp     loc_14002231C
0x14002212b  mov     rbx, cs:qword_14009B0C8
0x140022132  test    rbx, rbx
0x140022135  jz      short loc_140022176
0x140022137  jmp     short loc_140022171
0x140022139  mov     ecx, 1
0x14002213e  mov     rax, [rbx+8]
0x140022142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022147  mov     edi, eax
0x140022149  test    eax, eax
0x14002214b  js      short loc_14002217D
0x14002214d  mov     rax, [rbx+38h]
0x140022151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022156  mov     r8d, 1; int
0x14002215c  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x14002215f  mov     rcx, [rbx]; rguid
0x140022162  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x140022167  mov     edi, eax
0x140022169  test    eax, eax
0x14002216b  js      short loc_14002217D
0x14002216d  add     rbx, 48h ; 'H'
0x140022171  cmp     [rbx], r14
0x140022174  jnz     short loc_140022139
0x140022176  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x14002217b  mov     edi, eax
0x14002217d  test    edi, edi
0x14002217f  jns     short loc_14002218D
0x140022181  lea     r8, aCvdsservicemod_20; "CVdsServiceModule::RegisterServer, 4, %"...
0x140022188  jmp     loc_14002231C
0x14002218d  lea     rax, [rsp+1E0h+var_188]
0x140022192  mov     qword ptr [rsp+1E0h+cbData], rax
0x140022197  lea     rax, [rsp+1E0h+var_190]
0x14002219c  mov     [rsp+1E0h+phkResult], rax
0x1400221a1  lea     r9, [rsp+1E0h+var_198]
0x1400221a6  lea     r8, [rsp+1E0h+var_1A0]
0x1400221ab  lea     rdx, [rsp+1E0h+pAbsoluteSecurityDescriptor]
0x1400221b0  mov     ecx, 1
0x1400221b5  call    cs:__imp_InitializeSecurityDescriptorHelper
0x1400221bb  mov     esi, eax
0x1400221bd  test    eax, eax
0x1400221bf  jz      short loc_1400221DC
0x1400221c1  jg      short loc_1400221C7
0x1400221c3  mov     edi, eax
0x1400221c5  jmp     short loc_1400221D0
0x1400221c7  movzx   edi, ax
0x1400221ca  or      edi, 80070000h
0x1400221d0  lea     r8, aCvdsservicemod_1; "CVdsServiceModule::RegisterServer, 5, %"...
0x1400221d7  jmp     loc_14002231C
0x1400221dc  lea     r8, [rsp+1E0h+dwBufferLength]; lpdwBufferLength
0x1400221e1  lea     rdx, [rbp+0E0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1400221e5  lea     rcx, [rsp+1E0h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1400221ea  call    cs:__imp_MakeSelfRelativeSD
0x1400221f0  test    eax, eax
0x1400221f2  jnz     short loc_140022215
0x1400221f4  call    cs:__imp_GetLastError
0x1400221fa  mov     edi, eax
0x1400221fc  test    eax, eax
0x1400221fe  jle     short loc_140022209
0x140022200  movzx   edi, ax
0x140022203  or      edi, 80070000h
0x140022209  lea     r8, aCvdsservicemod_14; "CVdsServiceModule::RegisterServer, 6, %"...
0x140022210  jmp     loc_14002231C
0x140022215  lea     rcx, [rbp+0E0h+pSelfRelativeSecurityDescriptor]; pSecurityDescriptor
0x140022219  call    cs:__imp_GetSecurityDescriptorLength
0x14002221f  mov     ebx, eax
0x140022221  lea     rax, [rsp+1E0h+hKey]
0x140022226  mov     [rsp+1E0h+phkResult], rax; phkResult
0x14002222b  mov     r9d, 2000000h; samDesired
0x140022231  xor     r8d, r8d; ulOptions
0x140022234  lea     rdx, SubKey; "AppID\\{F290BFB2-1864-45B1-8804-2654194"...
0x14002223b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140022242  call    cs:__imp_RegOpenKeyExW
0x140022248  mov     esi, eax
0x14002224a  test    eax, eax
0x14002224c  jz      short loc_140022269
0x14002224e  jg      short loc_140022254
0x140022250  mov     edi, eax
0x140022252  jmp     short loc_14002225D
0x140022254  movzx   edi, ax
0x140022257  or      edi, 80070000h
0x14002225d  lea     r8, aCvdsservicemod_23; "CVdsServiceModule::RegisterServer, 7, %"...
0x140022264  jmp     loc_14002231C
0x140022269  mov     [rsp+1E0h+cbData], ebx; cbData
0x14002226d  lea     rax, [rbp+0E0h+pSelfRelativeSecurityDescriptor]
0x140022271  mov     [rsp+1E0h+phkResult], rax; lpData
0x140022276  mov     r9d, 3; dwType
0x14002227c  xor     r8d, r8d; Reserved
0x14002227f  lea     rdx, ValueName; "LaunchPermission"
0x140022286  mov     rcx, [rsp+1E0h+hKey]; hKey
0x14002228b  call    cs:__imp_RegSetValueExW
0x140022291  mov     esi, eax
0x140022293  test    eax, eax
0x140022295  jz      short loc_1400222AF
0x140022297  jg      short loc_14002229D
0x140022299  mov     edi, eax
0x14002229b  jmp     short loc_1400222A6
0x14002229d  movzx   edi, ax
0x1400222a0  or      edi, 80070000h
0x1400222a6  lea     r8, aCvdsservicemod_12; "CVdsServiceModule::RegisterServer, 8, %"...
0x1400222ad  jmp     short loc_14002231C
0x1400222af  mov     [rsp+1E0h+cbData], ebx; cbData
0x1400222b3  lea     rax, [rbp+0E0h+pSelfRelativeSecurityDescriptor]
0x1400222b7  mov     [rsp+1E0h+phkResult], rax; lpData
0x1400222bc  mov     r9d, 3; dwType
0x1400222c2  xor     r8d, r8d; Reserved
0x1400222c5  lea     rdx, aAccesspermissi; "AccessPermission"
0x1400222cc  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1400222d1  call    cs:__imp_RegSetValueExW
0x1400222d7  mov     esi, eax
0x1400222d9  test    eax, eax
0x1400222db  jz      short loc_1400222F5
0x1400222dd  jg      short loc_1400222E3
0x1400222df  mov     edi, eax
0x1400222e1  jmp     short loc_1400222EC
0x1400222e3  movzx   edi, ax
0x1400222e6  or      edi, 80070000h
0x1400222ec  lea     r8, aCvdsservicemod_26; "CVdsServiceModule::RegisterServer, 9, %"...
0x1400222f3  jmp     short loc_14002231C
0x1400222f5  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1400222fa  call    cs:__imp_RegCloseKey
0x140022300  mov     esi, eax
0x140022302  test    eax, eax
0x140022304  jz      short loc_14002232A
0x140022306  jg      short loc_14002230C
0x140022308  mov     edi, eax
0x14002230a  jmp     short loc_140022315
0x14002230c  movzx   edi, ax
0x14002230f  or      edi, 80070000h
0x140022315  lea     r8, aCvdsservicemod_25; "CVdsServiceModule::RegisterServer, 10, "...
0x14002231c  mov     r9d, edi
0x14002231f  xor     edx, edx
0x140022321  mov     ecx, r15d
0x140022324  call    cs:__imp_VdsTraceEx
0x14002232a  mov     rbx, [rsp+1E0h+var_1A0]
0x14002232f  call    cs:__imp_GetProcessHeap
0x140022335  mov     r8, rbx
0x140022338  xor     edx, edx
0x14002233a  mov     rcx, rax
0x14002233d  call    cs:__imp_VdsHeapFree
0x140022343  mov     [rsp+1E0h+var_1A0], r14
0x140022348  mov     rbx, [rsp+1E0h+var_198]
0x14002234d  call    cs:__imp_GetProcessHeap
0x140022353  mov     r8, rbx
0x140022356  xor     edx, edx
0x140022358  mov     rcx, rax
0x14002235b  call    cs:__imp_VdsHeapFree
0x140022361  mov     [rsp+1E0h+var_198], r14
0x140022366  mov     rbx, [rsp+1E0h+var_190]
0x14002236b  call    cs:__imp_GetProcessHeap
0x140022371  mov     r8, rbx
0x140022374  xor     edx, edx
0x140022376  mov     rcx, rax
0x140022379  call    cs:__imp_VdsHeapFree
0x14002237f  mov     [rsp+1E0h+var_190], r14
0x140022384  mov     rbx, [rsp+1E0h+var_188]
0x140022389  call    cs:__imp_GetProcessHeap
0x14002238f  mov     r8, rbx
0x140022392  xor     edx, edx
0x140022394  mov     rcx, rax
0x140022397  call    cs:__imp_VdsHeapFree
0x14002239d  mov     [rsp+1E0h+var_188], r14
0x1400223a2  test    edi, edi
0x1400223a4  jns     short loc_1400223C5
0x1400223a6  mov     qword ptr [rsp+1E0h+cbData], r14; unsigned __int16 *
0x1400223ab  mov     dword ptr [rsp+1E0h+phkResult], 2010009h; unsigned int
0x1400223b3  mov     r9d, esi; unsigned int
0x1400223b6  xor     r8d, r8d; void *
0x1400223b9  xor     edx, edx; unsigned int
0x1400223bb  mov     ecx, 0C2000001h; unsigned int
0x1400223c0  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400223c5  call    cs:__imp_CoUninitialize
0x1400223cb  nop
0x1400223cc  lea     rcx, [rbp+0E0h+var_158]
0x1400223d0  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400223d6  mov     eax, edi
0x1400223d8  mov     rcx, [rbp+0E0h+var_40]
0x1400223df  xor     rcx, rsp; StackCookie
0x1400223e2  call    __security_check_cookie
0x1400223e7  add     rsp, 1B8h
0x1400223ee  pop     r15
0x1400223f0  pop     r14
0x1400223f2  pop     rdi
0x1400223f3  pop     rsi
0x1400223f4  pop     rbx
0x1400223f5  pop     rbp
0x1400223f6  retn
```
