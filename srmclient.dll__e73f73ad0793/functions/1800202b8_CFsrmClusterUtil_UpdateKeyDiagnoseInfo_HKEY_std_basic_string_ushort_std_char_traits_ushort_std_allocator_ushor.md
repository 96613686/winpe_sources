# CFsrmClusterUtil::UpdateKeyDiagnoseInfo(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800202b8`
- end: `0x1800205ef`
- name: `?UpdateKeyDiagnoseInfo@CFsrmClusterUtil@@SAXPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(HKEY hKey, BYTE *lpData)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e0d0`
- `0x18001e69c`
- `0x180021148`

## callees

- `0x180001350`
- `0x18001e9a0`
- `0x18001ed68`
- `0x1800202b8`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020383`
- `KERNEL32!GetLastError` at `0x180020433`
- `KERNEL32!GetLastError` at `0x1800204d4`
- `KERNEL32!GetLastError` at `0x180020383`
- `KERNEL32!GetLastError` at `0x180020433`
- `KERNEL32!GetLastError` at `0x1800204d4`
- `CLUSAPI!ClusterRegSetValue` at `0x180020379`
- `CLUSAPI!ClusterRegSetValue` at `0x180020429`
- `CLUSAPI!ClusterRegSetValue` at `0x1800204ca`
- `CLUSAPI!ClusterRegSetValue` at `0x180020379`
- `CLUSAPI!ClusterRegSetValue` at `0x180020429`
- `CLUSAPI!ClusterRegSetValue` at `0x1800204ca`

## string_xrefs

- `0x1800202ee`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x180020334`: `CFsrmClusterUtil::RegisterUpdateDiagnoseInfo`
- `0x1800202f9`: `CFsrmClusterUtil::UpdateKeyDiagnoseInfo`
- `0x1800203cc`: `WARNING: failed to update the operation property [0x%08lx]`
- `0x18002047c`: `WARNING: failed to update the computer name property [0x%08lx]`
- `0x18002051d`: `WARNING: failed to update the system time property [0x%08lx]`
- `0x1800204c0`: `LastUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFsrmClusterUtil::UpdateKeyDiagnoseInfo(HKEY hKey, BYTE *lpData)
{
  const BYTE *v4; // r9
  DWORD LastError; // ebx
  const BYTE *v6; // r9
  DWORD v7; // ebx
  const BYTE *v8; // r9
  DWORD v9; // ebx
  __int64 result; // rax
  const wchar_t *v11; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-C0h]
  const wchar_t *v13; // [rsp+48h] [rbp-B8h]
  __int64 v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+58h] [rbp-A8h]
  _BYTE v16[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+C0h] [rbp-40h]
  _QWORD v18[4]; // [rsp+C8h] [rbp-38h] BYREF
  int v19; // [rsp+E8h] [rbp-18h]
  _BYTE v20[96]; // [rsp+F0h] [rbp-10h] BYREF
  int v21; // [rsp+150h] [rbp+50h]
  BYTE *v22; // [rsp+158h] [rbp+58h]
  BYTE *v23[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v24; // [rsp+170h] [rbp+70h]
  unsigned __int64 v25; // [rsp+178h] [rbp+78h]
  BYTE *lpDataa[2]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v27; // [rsp+198h] [rbp+98h]
  unsigned __int64 v28; // [rsp+1A0h] [rbp+A0h]
  _QWORD v29[22]; // [rsp+1B0h] [rbp+B0h] BYREF

  v22 = lpData;
  v18[0] = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v18[1] = L"CFsrmClusterUtil::UpdateKeyDiagnoseInfo";
  v18[2] = L"CLUSUTLC";
  v18[3] = 592;
  v19 = 255;
  v21 = 0x1000000;
  memset_0(v20, 0, sizeof(v20));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)v29,
    (const struct CSrmDebugInfo *)v18,
    (__int64)L"CFsrmClusterUtil::RegisterUpdateDiagnoseInfo");
  if ( *((_QWORD *)lpData + 3) < 8u )
    v4 = lpData;
  else
    v4 = *(const BYTE **)lpData;
  if ( ClusterRegSetValue(hKey, L"LastOperation", 1u, v4, 2 * *((_DWORD *)lpData + 4) + 2) )
  {
    LastError = GetLastError();
    v11 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v12 = L"CFsrmClusterUtil::UpdateKeyDiagnoseInfo";
    v13 = L"CLUSUTLC";
    v14 = 603;
    v15 = 255;
    v17 = 0x1000000;
    memset_0(v16, 0, sizeof(v16));
    CSrmFunctionTracer::Trace(v29, &v11, L"WARNING: failed to update the operation property [0x%08lx]", LastError);
  }
  CFsrmClusterUtil::GetComputerNameAsString(lpDataa);
  v6 = (const BYTE *)lpDataa;
  if ( v28 >= 8 )
    v6 = lpDataa[0];
  if ( ClusterRegSetValue(hKey, L"FromNode", 1u, v6, 2 * v27 + 2) )
  {
    v7 = GetLastError();
    v11 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v12 = L"CFsrmClusterUtil::UpdateKeyDiagnoseInfo";
    v13 = L"CLUSUTLC";
    v14 = 616;
    v15 = 255;
    v17 = 0x1000000;
    memset_0(v16, 0, sizeof(v16));
    CSrmFunctionTracer::Trace(v29, &v11, L"WARNING: failed to update the computer name property [0x%08lx]", v7);
  }
  CFsrmClusterUtil::GetSystemTimeAsString(v23);
  v8 = (const BYTE *)v23;
  if ( v25 >= 8 )
    v8 = v23[0];
  if ( ClusterRegSetValue(hKey, L"LastUpdated", 1u, v8, 2 * v24 + 2) )
  {
    v9 = GetLastError();
    v11 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v12 = L"CFsrmClusterUtil::UpdateKeyDiagnoseInfo";
    v13 = L"CLUSUTLC";
    v14 = 628;
    v15 = 255;
    v17 = 0x1000000;
    memset_0(v16, 0, sizeof(v16));
    CSrmFunctionTracer::Trace(v29, &v11, L"WARNING: failed to update the system time property [0x%08lx]", v9);
  }
  if ( v25 >= 8 )
    operator delete(v23[0]);
  v25 = 7;
  v24 = 0;
  LOWORD(v23[0]) = 0;
  if ( v28 >= 8 )
    operator delete(lpDataa[0]);
  v28 = 7;
  v27 = 0;
  LOWORD(lpDataa[0]) = 0;
  v29[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v29);
  if ( *((_QWORD *)lpData + 3) >= 8u )
    operator delete(*(void **)lpData);
  *((_QWORD *)lpData + 3) = 7;
  *((_QWORD *)lpData + 2) = 0;
  result = 0;
  *(_WORD *)lpData = 0;
  return result;
}

```

## disassembly

```asm
0x1800202b8  mov     [rsp-8+arg_10], rbx
0x1800202bd  push    rbp
0x1800202be  push    rsi
0x1800202bf  push    rdi
0x1800202c0  push    r12
0x1800202c2  push    r13
0x1800202c4  lea     rbp, [rsp-170h]
0x1800202cc  sub     rsp, 270h
0x1800202d3  mov     rax, cs:__security_cookie
0x1800202da  xor     rax, rsp
0x1800202dd  mov     [rbp+190h+var_30], rax
0x1800202e4  mov     rdi, rdx
0x1800202e7  mov     rsi, rcx
0x1800202ea  mov     [rbp+190h+var_138], rdx
0x1800202ee  lea     r12, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x1800202f5  mov     [rbp+190h+var_1C8], r12
0x1800202f9  lea     r13, aCfsrmclusterut_2; "CFsrmClusterUtil::UpdateKeyDiagnoseInfo"
0x180020300  mov     [rbp+190h+var_1C0], r13
0x180020304  lea     rax, aClusutlc; "CLUSUTLC"
0x18002030b  mov     [rbp+190h+var_1B8], rax
0x18002030f  mov     [rbp+190h+var_1B0], 250h
0x180020317  mov     [rbp+190h+var_1A8], 0FFh
0x18002031e  mov     [rbp+190h+var_140], 1000000h
0x180020325  xor     edx, edx; Val
0x180020327  lea     r8d, [rdx+60h]; Size
0x18002032b  lea     rcx, [rbp+190h+var_1A0]; void *
0x18002032f  call    memset_0
0x180020334  lea     r8, aCfsrmclusterut_10; "CFsrmClusterUtil::RegisterUpdateDiagnos"...
0x18002033b  lea     rdx, [rbp+190h+var_1C8]
0x18002033f  lea     rcx, [rbp+190h+var_E0]
0x180020346  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18002034b  nop
0x18002034c  mov     eax, [rdi+10h]
0x18002034f  lea     eax, ds:2[rax*2]
0x180020356  cmp     qword ptr [rdi+18h], 8
0x18002035b  jb      short loc_180020362
0x18002035d  mov     r9, [rdi]
0x180020360  jmp     short loc_180020365
0x180020362  mov     r9, rdi; lpData
0x180020365  mov     [rsp+290h+cbData], eax; cbData
0x180020369  mov     r8d, 1; dwType
0x18002036f  lea     rdx, aLastoperation; "LastOperation"
0x180020376  mov     rcx, rsi; hKey
0x180020379  call    cs:__imp_ClusterRegSetValue
0x18002037f  test    eax, eax
0x180020381  jz      short loc_1800203E4
0x180020383  call    cs:__imp_GetLastError
0x180020389  mov     ebx, eax
0x18002038b  mov     [rsp+290h+var_258], r12
0x180020390  mov     [rsp+290h+var_250], r13
0x180020395  lea     rax, aClusutlc; "CLUSUTLC"
0x18002039c  mov     [rsp+290h+var_248], rax
0x1800203a1  mov     [rsp+290h+var_240], 25Bh
0x1800203aa  mov     [rsp+290h+var_238], 0FFh
0x1800203b2  mov     [rbp+190h+var_1D0], 1000000h
0x1800203b9  xor     edx, edx; Val
0x1800203bb  lea     r8d, [rdx+60h]; Size
0x1800203bf  lea     rcx, [rsp+290h+var_230]; void *
0x1800203c4  call    memset_0
0x1800203c9  mov     r9d, ebx
0x1800203cc  lea     r8, aWarningFailedT_0; "WARNING: failed to update the operation"...
0x1800203d3  lea     rdx, [rsp+290h+var_258]
0x1800203d8  lea     rcx, [rbp+190h+var_E0]
0x1800203df  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800203e4  lea     rcx, [rbp+190h+lpData]; void *
0x1800203eb  call    ?GetComputerNameAsString@CFsrmClusterUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CFsrmClusterUtil::GetComputerNameAsString(void)
0x1800203f0  nop
0x1800203f1  mov     eax, dword ptr [rbp+190h+var_F8]
0x1800203f7  lea     r9, [rbp+190h+lpData]
0x1800203fe  cmp     [rbp+190h+var_F0], 8
0x180020406  cmovnb  r9, [rbp+190h+lpData]; lpData
0x18002040e  lea     eax, ds:2[rax*2]
0x180020415  mov     [rsp+290h+cbData], eax; cbData
0x180020419  mov     r8d, 1; dwType
0x18002041f  lea     rdx, aFromnode; "FromNode"
0x180020426  mov     rcx, rsi; hKey
0x180020429  call    cs:__imp_ClusterRegSetValue
0x18002042f  test    eax, eax
0x180020431  jz      short loc_180020494
0x180020433  call    cs:__imp_GetLastError
0x180020439  mov     ebx, eax
0x18002043b  mov     [rsp+290h+var_258], r12
0x180020440  mov     [rsp+290h+var_250], r13
0x180020445  lea     rax, aClusutlc; "CLUSUTLC"
0x18002044c  mov     [rsp+290h+var_248], rax
0x180020451  mov     [rsp+290h+var_240], 268h
0x18002045a  mov     [rsp+290h+var_238], 0FFh
0x180020462  mov     [rbp+190h+var_1D0], 1000000h
0x180020469  xor     edx, edx; Val
0x18002046b  lea     r8d, [rdx+60h]; Size
0x18002046f  lea     rcx, [rsp+290h+var_230]; void *
0x180020474  call    memset_0
0x180020479  mov     r9d, ebx
0x18002047c  lea     r8, aWarningFailedT; "WARNING: failed to update the computer "...
0x180020483  lea     rdx, [rsp+290h+var_258]
0x180020488  lea     rcx, [rbp+190h+var_E0]
0x18002048f  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180020494  lea     rcx, [rbp+190h+var_130]; void *
0x180020498  call    ?GetSystemTimeAsString@CFsrmClusterUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CFsrmClusterUtil::GetSystemTimeAsString(void)
0x18002049d  nop
0x18002049e  mov     eax, dword ptr [rbp+190h+var_120]
0x1800204a1  lea     r9, [rbp+190h+var_130]
0x1800204a5  cmp     [rbp+190h+var_118], 8
0x1800204aa  cmovnb  r9, [rbp+190h+var_130]; lpData
0x1800204af  lea     eax, ds:2[rax*2]
0x1800204b6  mov     [rsp+290h+cbData], eax; cbData
0x1800204ba  mov     r8d, 1; dwType
0x1800204c0  lea     rdx, aLastupdated; "LastUpdated"
0x1800204c7  mov     rcx, rsi; hKey
0x1800204ca  call    cs:__imp_ClusterRegSetValue
0x1800204d0  test    eax, eax
0x1800204d2  jz      short loc_180020536
0x1800204d4  call    cs:__imp_GetLastError
0x1800204da  mov     ebx, eax
0x1800204dc  mov     [rsp+290h+var_258], r12
0x1800204e1  mov     [rsp+290h+var_250], r13
0x1800204e6  lea     rax, aClusutlc; "CLUSUTLC"
0x1800204ed  mov     [rsp+290h+var_248], rax
0x1800204f2  mov     [rsp+290h+var_240], 274h
0x1800204fb  mov     [rsp+290h+var_238], 0FFh
0x180020503  mov     [rbp+190h+var_1D0], 1000000h
0x18002050a  xor     edx, edx; Val
0x18002050c  lea     r8d, [rdx+60h]; Size
0x180020510  lea     rcx, [rsp+290h+var_230]; void *
0x180020515  call    memset_0
0x18002051a  mov     r9d, ebx
0x18002051d  lea     r8, aWarningFailedT_1; "WARNING: failed to update the system ti"...
0x180020524  lea     rdx, [rsp+290h+var_258]
0x180020529  lea     rcx, [rbp+190h+var_E0]
0x180020530  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180020535  nop
0x180020536  cmp     [rbp+190h+var_118], 8
0x18002053b  jb      short loc_180020546
0x18002053d  mov     rcx, [rbp+190h+var_130]; Block
0x180020541  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020546  mov     ebx, 7
0x18002054b  mov     [rbp+190h+var_118], rbx
0x18002054f  mov     [rbp+190h+var_120], 0
0x180020557  xor     eax, eax
0x180020559  mov     word ptr [rbp+190h+var_130], ax
0x18002055d  cmp     [rbp+190h+var_F0], 8
0x180020565  jb      short loc_180020573
0x180020567  mov     rcx, [rbp+190h+lpData]; Block
0x18002056e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020573  mov     [rbp+190h+var_F0], rbx
0x18002057a  mov     [rbp+190h+var_F8], 0
0x180020585  xor     eax, eax
0x180020587  mov     word ptr [rbp+190h+lpData], ax
0x18002058e  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180020595  mov     [rbp+190h+var_E0], rax
0x18002059c  lea     rcx, [rbp+190h+var_E0]; this
0x1800205a3  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800205a8  nop
0x1800205a9  cmp     qword ptr [rdi+18h], 8
0x1800205ae  jb      short loc_1800205B8
0x1800205b0  mov     rcx, [rdi]; Block
0x1800205b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800205b8  mov     [rdi+18h], rbx
0x1800205bc  mov     qword ptr [rdi+10h], 0
0x1800205c4  xor     eax, eax
0x1800205c6  mov     [rdi], ax
0x1800205c9  mov     rcx, [rbp+190h+var_30]
0x1800205d0  xor     rcx, rsp; StackCookie
0x1800205d3  call    __security_check_cookie
0x1800205d8  mov     rbx, [rsp+290h+arg_10]
0x1800205e0  add     rsp, 270h
0x1800205e7  pop     r13
0x1800205e9  pop     r12
0x1800205eb  pop     rdi
0x1800205ec  pop     rsi
0x1800205ed  pop     rbp
0x1800205ee  retn
```
