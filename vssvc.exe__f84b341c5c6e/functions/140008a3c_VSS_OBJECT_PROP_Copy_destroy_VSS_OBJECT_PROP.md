# VSS_OBJECT_PROP_Copy::destroy(_VSS_OBJECT_PROP *)

- ea: `0x140008a3c`
- end: `0x140008cc8`
- name: `?destroy@VSS_OBJECT_PROP_Copy@@SAXPEAU_VSS_OBJECT_PROP@@@Z`
- size: `652`
- prototype: `void __fastcall(struct _VSS_OBJECT_PROP *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140007250`
- `0x140008a10`
- `0x140019eb0`
- `0x14001cafc`
- `0x14001e49c`
- `0x14009d634`

## callees

- `0x140006020`
- `0x140008a3c`
- `0x1400137c0`
- `0x140013cb0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008afa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008afa`
- `VssTrace!__imp_VssTraceMessage` at `0x140008c04`
- `VssTrace!__imp_VssTraceMessage` at `0x140008c04`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008b5b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008b5b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140008b4c`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140008b4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008c95`

## string_xrefs

- `0x140008a60`: `VSS_OBJECT_PROP_Copy::destroy`
- `0x140008a52`: `base\stor\vss\modules\prop\copy.cxx`
- `0x140008a6e`: `PRPCOPYC`

## pseudocode

```c
void __fastcall VSS_OBJECT_PROP_Copy::destroy(struct _VSS_OBJECT_PROP *a1)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // edi
  unsigned __int64 v5; // [rsp+50h] [rbp-138h] BYREF
  int v6; // [rsp+58h] [rbp-130h]
  const unsigned __int16 *v7; // [rsp+60h] [rbp-128h]
  const unsigned __int16 *v8; // [rsp+68h] [rbp-120h]
  unsigned int v9; // [rsp+70h] [rbp-118h]
  int v10; // [rsp+74h] [rbp-114h]
  const unsigned __int16 *v11; // [rsp+78h] [rbp-110h]
  unsigned int v12; // [rsp+80h] [rbp-108h]
  DWORD TickCount; // [rsp+84h] [rbp-104h]
  int v14; // [rsp+88h] [rbp-100h]
  __int128 v15; // [rsp+90h] [rbp-F8h]
  __int128 v16; // [rsp+A0h] [rbp-E8h]
  __int64 v17; // [rsp+B0h] [rbp-D8h]
  _QWORD v18[3]; // [rsp+D8h] [rbp-B0h] BYREF
  int v19; // [rsp+F0h] [rbp-98h]
  int v20; // [rsp+F4h] [rbp-94h]
  int v21; // [rsp+F8h] [rbp-90h]
  _DWORD v22[32]; // [rsp+100h] [rbp-88h] BYREF
  __int64 v23; // [rsp+190h] [rbp+8h] BYREF

  v18[0] = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v18[1] = L"VSS_OBJECT_PROP_Copy::destroy";
  v18[2] = L"PRPCOPYC";
  v19 = 180;
  v20 = 11;
  v21 = 255;
  v22[30] = 0x1000000;
  memset_0(v22, 0, 0x78u);
  v6 = 0;
  v11 = L"VSS_OBJECT_PROP_Copy::destroy";
  v7 = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v8 = L"PRPCOPYC";
  v9 = 180;
  v10 = 11;
  TickCount = GetTickCount();
  v14 = 255;
  v5 = 0xFFFFFFFF00000000uLL;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  v23 = 0;
  if ( (int)VssGetTracingContextPerThread(&v23) < 0 )
  {
    v3 = v17;
  }
  else
  {
    v2 = VssSetTracingContextPerThread(&v5);
    v3 = v17;
    if ( v2 >= 0 )
      v3 = v23;
    v17 = v3;
  }
  if ( v3 )
    v12 = *(_DWORD *)(v3 + 48) + 1;
  else
    v12 = 0;
  v4 = 160;
  if ( v14 != 255 )
    v4 = v14;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v5) )
    VssTraceMessage(v7, v8, v9, v12, v10, v11, L"ENTER", v4, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v18);
  if ( a1 )
  {
    if ( a1->Type == VSS_OBJECT_SNAPSHOT )
    {
      CoTaskMemFree(a1->Obj.Snap.m_pwszOriginalVolumeName);
      a1->Obj.Snap.m_pwszOriginalVolumeName = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszSnapshotDeviceObject);
      a1->Obj.Snap.m_pwszSnapshotDeviceObject = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszOriginatingMachine);
      a1->Obj.Snap.m_pwszOriginatingMachine = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszServiceMachine);
      a1->Obj.Snap.m_pwszServiceMachine = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszExposedName);
      a1->Obj.Snap.m_pwszExposedName = 0;
      CoTaskMemFree(a1->Obj.Snap.m_pwszExposedPath);
      a1->Obj.Snap.m_pwszExposedPath = 0;
    }
    else if ( a1->Type == VSS_OBJECT_PROVIDER )
    {
      CoTaskMemFree(a1->Obj.Prov.m_pwszProviderName);
      a1->Obj.Prov.m_pwszProviderName = 0;
      CoTaskMemFree(a1->Obj.Prov.m_pwszProviderVersion);
      a1->Obj.Prov.m_pwszProviderVersion = 0;
    }
    a1->Type = VSS_OBJECT_UNKNOWN;
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v5);
}

```

## disassembly

```asm
0x140008a3c  mov     r11, rsp
0x140008a3f  mov     [r11+10h], rbx
0x140008a43  mov     [r11+18h], rsi
0x140008a47  push    rdi
0x140008a48  sub     rsp, 180h
0x140008a4f  mov     rbx, rcx
0x140008a52  lea     rax, aBaseStorVssMod_32; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x140008a59  mov     [r11-0B0h], rax
0x140008a60  lea     rax, aVssObjectPropC; "VSS_OBJECT_PROP_Copy::destroy"
0x140008a67  mov     [r11-0A8h], rax
0x140008a6e  lea     rax, aPrpcopyc; "PRPCOPYC"
0x140008a75  mov     [r11-0A0h], rax
0x140008a7c  mov     [rsp+188h+var_98], 0B4h
0x140008a87  mov     [rsp+188h+var_94], 0Bh
0x140008a92  mov     [rsp+188h+var_90], 0FFh
0x140008a9d  xor     esi, esi
0x140008a9f  mov     dword ptr [r11-10h], 1000000h
0x140008aa7  xor     edx, edx; Val
0x140008aa9  lea     r8d, [rsi+78h]; Size
0x140008aad  lea     rcx, [r11-88h]; void *
0x140008ab4  call    memset_0
0x140008ab9  mov     [rsp+188h+var_130], esi
0x140008abd  mov     rax, [rsp+188h+var_A8]
0x140008ac5  mov     [rsp+188h+var_110], rax
0x140008aca  mov     rax, [rsp+188h+var_B0]
0x140008ad2  mov     [rsp+188h+var_128], rax
0x140008ad7  mov     rax, [rsp+188h+var_A0]
0x140008adf  mov     [rsp+188h+var_120], rax
0x140008ae4  mov     eax, [rsp+188h+var_98]
0x140008aeb  mov     [rsp+188h+var_118], eax
0x140008aef  mov     eax, [rsp+188h+var_94]
0x140008af6  mov     [rsp+188h+var_114], eax
0x140008afa  call    cs:__imp_GetTickCount
0x140008b00  mov     [rsp+188h+var_104], eax
0x140008b07  mov     [rsp+188h+var_134], 0FFFFFFFFh
0x140008b0f  mov     eax, [rsp+188h+var_90]
0x140008b16  mov     [rsp+188h+var_100], eax
0x140008b1d  mov     [rsp+188h+var_138], esi
0x140008b21  mov     [rsp+188h+var_D8], rsi
0x140008b29  xorps   xmm0, xmm0
0x140008b2c  movups  [rsp+188h+var_F8], xmm0
0x140008b34  movups  [rsp+188h+var_E8], xmm0
0x140008b3c  mov     [rsp+188h+arg_0], rsi
0x140008b44  lea     rcx, [rsp+188h+arg_0]
0x140008b4c  call    cs:__imp_VssGetTracingContextPerThread
0x140008b52  test    eax, eax
0x140008b54  js      short loc_140008B7E
0x140008b56  lea     rcx, [rsp+188h+var_138]
0x140008b5b  call    cs:__imp_VssSetTracingContextPerThread
0x140008b61  mov     rcx, [rsp+188h+var_D8]
0x140008b69  test    eax, eax
0x140008b6b  cmovns  rcx, [rsp+188h+arg_0]
0x140008b74  mov     [rsp+188h+var_D8], rcx
0x140008b7c  jmp     short loc_140008B86
0x140008b7e  mov     rcx, [rsp+188h+var_D8]
0x140008b86  test    rcx, rcx
0x140008b89  jz      short loc_140008B99
0x140008b8b  mov     eax, [rcx+30h]
0x140008b8e  inc     eax
0x140008b90  mov     [rsp+188h+var_108], eax
0x140008b97  jmp     short loc_140008BA0
0x140008b99  mov     [rsp+188h+var_108], esi
0x140008ba0  mov     edi, 0A0h
0x140008ba5  cmp     [rsp+188h+var_100], 0FFh
0x140008bb0  cmovnz  edi, [rsp+188h+var_100]
0x140008bb8  lea     rcx, [rsp+188h+var_138]; this
0x140008bbd  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140008bc2  test    eax, eax
0x140008bc4  jz      short loc_140008C0A
0x140008bc6  mov     [rsp+188h+var_148], rsi
0x140008bcb  mov     [rsp+188h+var_150], edi
0x140008bcf  lea     rax, aEnter; "ENTER"
0x140008bd6  mov     [rsp+188h+var_158], rax
0x140008bdb  mov     rax, [rsp+188h+var_110]
0x140008be0  mov     [rsp+188h+var_160], rax
0x140008be5  mov     eax, [rsp+188h+var_114]
0x140008be9  mov     [rsp+188h+var_168], eax
0x140008bed  mov     r9d, [rsp+188h+var_108]
0x140008bf5  mov     r8d, [rsp+188h+var_118]
0x140008bfa  mov     rdx, [rsp+188h+var_120]
0x140008bff  mov     rcx, [rsp+188h+var_128]
0x140008c04  call    cs:__imp_VssTraceMessage
0x140008c0a  lea     rcx, [rsp+188h+var_B0]; this
0x140008c12  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140008c17  nop
0x140008c18  test    rbx, rbx
0x140008c1b  jz      loc_140008CA1
0x140008c21  mov     ecx, [rbx]
0x140008c23  sub     ecx, 3
0x140008c26  jz      short loc_140008C4B
0x140008c28  cmp     ecx, 1
0x140008c2b  jnz     short loc_140008C9F
0x140008c2d  mov     rcx, [rbx+18h]; pv
0x140008c31  call    cs:__imp_CoTaskMemFree
0x140008c37  mov     [rbx+18h], rsi
0x140008c3b  mov     rcx, [rbx+28h]; pv
0x140008c3f  call    cs:__imp_CoTaskMemFree
0x140008c45  mov     [rbx+28h], rsi
0x140008c49  jmp     short loc_140008C9F
0x140008c4b  mov     rcx, [rbx+38h]; pv
0x140008c4f  call    cs:__imp_CoTaskMemFree
0x140008c55  mov     [rbx+38h], rsi
0x140008c59  mov     rcx, [rbx+30h]; pv
0x140008c5d  call    cs:__imp_CoTaskMemFree
0x140008c63  mov     [rbx+30h], rsi
0x140008c67  mov     rcx, [rbx+40h]; pv
0x140008c6b  call    cs:__imp_CoTaskMemFree
0x140008c71  mov     [rbx+40h], rsi
0x140008c75  mov     rcx, [rbx+48h]; pv
0x140008c79  call    cs:__imp_CoTaskMemFree
0x140008c7f  mov     [rbx+48h], rsi
0x140008c83  mov     rcx, [rbx+50h]; pv
0x140008c87  call    cs:__imp_CoTaskMemFree
0x140008c8d  mov     [rbx+50h], rsi
0x140008c91  mov     rcx, [rbx+58h]; pv
0x140008c95  call    cs:__imp_CoTaskMemFree
0x140008c9b  mov     [rbx+58h], rsi
0x140008c9f  mov     [rbx], esi
0x140008ca1  jmp     short loc_140008CA9
0x140008ca3  jmp     short loc_140008CA9
0x140008ca5  jmp     short loc_140008CA9
0x140008ca7  jmp     short $+2
0x140008ca9  lea     rcx, [rsp+188h+var_138]; this
0x140008cae  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140008cb3  lea     r11, [rsp+188h+var_8]
0x140008cbb  mov     rbx, [r11+18h]
0x140008cbf  mov     rsi, [r11+20h]
0x140008cc3  mov     rsp, r11
0x140008cc6  pop     rdi
0x140008cc7  retn
```
