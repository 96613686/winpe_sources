# CVssCriticalSection::~CVssCriticalSection(void)

- ea: `0x140036d64`
- end: `0x140037020`
- name: `??1CVssCriticalSection@@QEAA@XZ`
- size: `700`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400369ec`
- `0x140036b90`
- `0x140036ba4`
- `0x1400f38e0`
- `0x1400f3920`

## callees

- `0x1400138e0`
- `0x140013cb0`
- `0x140036d64`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140036ea6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140036ea6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140036dfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140036ec8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140036dfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140036ec8`
- `VssTrace!__imp_VssTraceMessage` at `0x140037015`
- `VssTrace!__imp_VssTraceMessage` at `0x140037015`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036f83`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036fb6`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036f83`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036fb6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140036e34`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140036e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036eb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036eb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036fa1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssCriticalSection::~CVssCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rcx
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  __int64 j; // rbx
  DWORD v8; // eax
  DWORD v9; // esi
  int v10; // eax
  __int64 v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+28h] [rbp-D8h]
  __int64 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+38h] [rbp-C8h]
  __int64 v15; // [rsp+40h] [rbp-C0h]
  _DWORD v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v18; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp-98h]
  unsigned int v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v22; // [rsp+78h] [rbp-88h]
  unsigned int v23; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v25; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v29; // [rsp+C0h] [rbp-40h]
  const wchar_t *v30; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v31; // [rsp+D0h] [rbp-30h]
  int v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+DCh] [rbp-24h]
  int v34; // [rsp+E0h] [rbp-20h]
  LPVOID v35[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v36; // [rsp+160h] [rbp+60h]
  __int64 v37; // [rsp+190h] [rbp+90h] BYREF

  v32 = 185;
  v29 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v33 = 11;
  v30 = L"CVssCriticalSection::~CVssCriticalSection";
  v34 = 255;
  v31 = L"INCTYPEH";
  v36 = 0x1000000;
  memset_0(v35, 0, sizeof(v35));
  v22 = L"CVssCriticalSection::~CVssCriticalSection";
  v18 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v19 = L"INCTYPEH";
  v20 = 185;
  v21 = 11;
  v17 = 0;
  v16[1] = -1;
  TickCount = GetTickCount();
  v25 = 255;
  v16[0] = 0;
  v28 = 0;
  *(_OWORD *)pv = 0;
  v37 = 0;
  v27 = 0;
  if ( (int)VssGetTracingContextPerThread(&v37) >= 0 )
  {
    v10 = VssSetTracingContextPerThread(v16);
    v2 = v28;
    if ( v10 >= 0 )
      v2 = v37;
    v28 = v2;
  }
  else
  {
    v2 = v28;
  }
  if ( v2 )
    v23 = *(_DWORD *)(v2 + 48) + 1;
  else
    v23 = 0;
  v3 = 160;
  v4 = 160;
  if ( v25 != 255 )
    v4 = v25;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v16) )
    VssTraceMessage(v18, v19, v20, v23, v21, v22, L"ENTER", v4, 0);
  if ( HIBYTE(v36) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v6 = v35[i];
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v35[i] = 0;
      }
    }
  }
  if ( LOBYTE(lpCriticalSection[1].DebugInfo) )
    DeleteCriticalSection(lpCriticalSection);
  for ( j = 0; j != 4; ++j )
  {
    CoTaskMemFree(pv[j]);
    pv[j] = 0;
  }
  v8 = GetTickCount();
  v9 = v8 - TickCount;
  if ( v25 != 255 )
    v3 = v25;
  LODWORD(v14) = (v8 - TickCount) % 0x3E8;
  LODWORD(v13) = (v8 - TickCount) / 0x3E8 % 0x3C;
  LODWORD(v12) = v9 / 0xEA60 % 0x3C;
  LODWORD(v11) = v9 / 0x36EE80 % 0x3C;
  LODWORD(v15) = v8 - TickCount;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v16,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v11,
    v12,
    v13,
    v14,
    v15,
    v17);
  VssSetTracingContextPerThread(v28);
}

```

## disassembly

```asm
0x140036d64  mov     [rsp-8+arg_8], rbx
0x140036d69  mov     [rsp-8+arg_10], rsi
0x140036d6e  push    rbp
0x140036d6f  push    rdi
0x140036d70  push    r14
0x140036d72  lea     rbp, [rsp-70h]
0x140036d77  sub     rsp, 170h
0x140036d7e  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140036d85  mov     [rbp+80h+var_A8], 0B9h
0x140036d8c  mov     [rbp+80h+var_C0], rax
0x140036d90  mov     rdi, rcx
0x140036d93  lea     rax, aCvsscriticalse; "CVssCriticalSection::~CVssCriticalSecti"...
0x140036d9a  mov     [rbp+80h+var_A4], 0Bh
0x140036da1  mov     [rbp+80h+var_B8], rax
0x140036da5  lea     rcx, [rbp+80h+var_98]; void *
0x140036da9  lea     rax, aInctypeh; "INCTYPEH"
0x140036db0  mov     [rbp+80h+var_A0], 0FFh
0x140036db7  xor     esi, esi
0x140036db9  mov     [rbp+80h+var_B0], rax
0x140036dbd  xor     edx, edx; Val
0x140036dbf  mov     [rbp+80h+var_20], 1000000h
0x140036dc6  lea     r8d, [rsi+78h]; Size
0x140036dca  call    memset_0
0x140036dcf  mov     rax, [rbp+80h+var_B8]
0x140036dd3  mov     [rsp+180h+var_108], rax
0x140036dd8  mov     rax, [rbp+80h+var_C0]
0x140036ddc  mov     [rsp+180h+var_120], rax
0x140036de1  mov     rax, [rbp+80h+var_B0]
0x140036de5  mov     [rsp+180h+var_118], rax
0x140036dea  mov     eax, [rbp+80h+var_A8]
0x140036ded  mov     [rsp+180h+var_110], eax
0x140036df1  mov     eax, [rbp+80h+var_A4]
0x140036df4  mov     [rsp+180h+var_10C], eax
0x140036df8  mov     [rsp+180h+var_128], esi
0x140036dfc  call    cs:__imp_GetTickCount
0x140036e02  xorps   xmm0, xmm0
0x140036e05  mov     [rsp+180h+var_12C], 0FFFFFFFFh
0x140036e0d  mov     [rbp+80h+var_FC], eax
0x140036e10  lea     rcx, [rbp+80h+arg_0]
0x140036e17  mov     eax, [rbp+80h+var_A0]
0x140036e1a  mov     [rbp+80h+var_F8], eax
0x140036e1d  mov     [rsp+180h+var_130], esi
0x140036e21  mov     [rbp+80h+var_D0], rsi
0x140036e25  movups  xmmword ptr [rbp+80h+pv], xmm0
0x140036e29  mov     [rbp+80h+arg_0], rsi
0x140036e30  movups  [rbp+80h+var_E0], xmm0
0x140036e34  call    cs:__imp_VssGetTracingContextPerThread
0x140036e3a  test    eax, eax
0x140036e3c  jns     loc_140036FB1
0x140036e42  mov     rcx, [rbp+80h+var_D0]
0x140036e46  test    rcx, rcx
0x140036e49  jz      loc_140036FD3
0x140036e4f  mov     eax, [rcx+30h]
0x140036e52  inc     eax
0x140036e54  mov     [rbp+80h+var_100], eax
0x140036e57  cmp     [rbp+80h+var_F8], 0FFh
0x140036e5e  lea     rcx, [rsp+180h+var_130]; this
0x140036e63  mov     r14d, 0A0h
0x140036e69  mov     ebx, r14d
0x140036e6c  cmovnz  ebx, [rbp+80h+var_F8]
0x140036e70  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140036e75  test    eax, eax
0x140036e77  jnz     loc_140036FDB
0x140036e7d  cmp     byte ptr [rbp+80h+var_20+3], sil
0x140036e81  jz      short loc_140036E9D
0x140036e83  mov     rbx, rsi
0x140036e86  mov     rcx, [rbp+rbx*8+80h+var_98]; pv
0x140036e8b  test    rcx, rcx
0x140036e8e  jnz     loc_140036FA1
0x140036e94  inc     rbx
0x140036e97  cmp     rbx, 0Fh
0x140036e9b  jnz     short loc_140036E86
0x140036e9d  cmp     [rdi+28h], sil
0x140036ea1  jz      short loc_140036EAC
0x140036ea3  mov     rcx, rdi; lpCriticalSection
0x140036ea6  call    cs:__imp_DeleteCriticalSection
0x140036eac  mov     rbx, rsi
0x140036eaf  mov     rcx, [rbp+rbx*8+80h+pv]; pv
0x140036eb4  call    cs:__imp_CoTaskMemFree
0x140036eba  mov     [rbp+rbx*8+80h+pv], rsi
0x140036ebf  inc     rbx
0x140036ec2  cmp     rbx, 4
0x140036ec6  jnz     short loc_140036EAF
0x140036ec8  call    cs:__imp_GetTickCount
0x140036ece  mov     r9d, [rsp+180h+var_128]
0x140036ed3  mov     r8d, 88888889h
0x140036ed9  mov     esi, eax
0x140036edb  mov     [rsp+180h+var_138], r9d
0x140036ee0  sub     esi, [rbp+80h+var_FC]
0x140036ee3  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140036eea  mov     eax, 10624DD3h
0x140036eef  mov     dword ptr [rsp+180h+var_140], esi
0x140036ef3  mul     esi
0x140036ef5  mov     eax, r8d
0x140036ef8  mov     edi, edx
0x140036efa  shr     edi, 6
0x140036efd  mul     edi
0x140036eff  mov     eax, 45E7B273h
0x140036f04  mov     ebx, edi
0x140036f06  shr     edx, 5
0x140036f09  imul    ecx, edx, 3Ch ; '<'
0x140036f0c  mul     esi
0x140036f0e  sub     ebx, ecx
0x140036f10  mov     eax, r8d
0x140036f13  mov     r11d, edx
0x140036f16  shr     r11d, 0Eh
0x140036f1a  mul     r11d
0x140036f1d  mov     eax, 95217CB1h
0x140036f22  shr     edx, 5
0x140036f25  imul    ecx, edx, 3Ch ; '<'
0x140036f28  mul     esi
0x140036f2a  sub     r11d, ecx
0x140036f2d  mov     eax, r8d
0x140036f30  mov     r10d, edx
0x140036f33  mov     ecx, esi
0x140036f35  shr     r10d, 15h
0x140036f39  mul     r10d
0x140036f3c  shr     edx, 5
0x140036f3f  imul    eax, edx, 3Ch ; '<'
0x140036f42  lea     rdx, aExit; "EXIT"
0x140036f49  sub     r10d, eax
0x140036f4c  cmp     [rbp+80h+var_F8], 0FFh
0x140036f53  cmovnz  r14d, [rbp+80h+var_F8]
0x140036f58  imul    eax, edi, 3E8h
0x140036f5e  mov     r8d, r14d; unsigned int
0x140036f61  sub     ecx, eax
0x140036f63  mov     dword ptr [rsp+180h+var_148], ecx
0x140036f67  lea     rcx, [rsp+180h+var_130]; this
0x140036f6c  mov     dword ptr [rsp+180h+var_150], ebx
0x140036f70  mov     dword ptr [rsp+180h+var_158], r11d
0x140036f75  mov     dword ptr [rsp+180h+var_160], r10d
0x140036f7a  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140036f7f  mov     rcx, [rbp+80h+var_D0]
0x140036f83  call    cs:__imp_VssSetTracingContextPerThread
0x140036f89  lea     r11, [rsp+180h+var_10]
0x140036f91  mov     rbx, [r11+28h]
0x140036f95  mov     rsi, [r11+30h]
0x140036f99  mov     rsp, r11
0x140036f9c  pop     r14
0x140036f9e  pop     rdi
0x140036f9f  pop     rbp
0x140036fa0  retn
0x140036fa1  call    cs:__imp_CoTaskMemFree
0x140036fa7  mov     [rbp+rbx*8+80h+var_98], rsi
0x140036fac  jmp     loc_140036E94
0x140036fb1  lea     rcx, [rsp+180h+var_130]
0x140036fb6  call    cs:__imp_VssSetTracingContextPerThread
0x140036fbc  mov     rcx, [rbp+80h+var_D0]
0x140036fc0  test    eax, eax
0x140036fc2  cmovns  rcx, [rbp+80h+arg_0]
0x140036fca  mov     [rbp+80h+var_D0], rcx
0x140036fce  jmp     loc_140036E46
0x140036fd3  mov     [rbp+80h+var_100], esi
0x140036fd6  jmp     loc_140036E57
0x140036fdb  mov     r9d, [rbp+80h+var_100]
0x140036fdf  lea     rax, aEnter; "ENTER"
0x140036fe6  mov     r8d, [rsp+180h+var_110]
0x140036feb  mov     rdx, [rsp+180h+var_118]
0x140036ff0  mov     rcx, [rsp+180h+var_120]
0x140036ff5  mov     [rsp+180h+var_140], rsi
0x140036ffa  mov     dword ptr [rsp+180h+var_148], ebx
0x140036ffe  mov     [rsp+180h+var_150], rax
0x140037003  mov     rax, [rsp+180h+var_108]
0x140037008  mov     [rsp+180h+var_158], rax
0x14003700d  mov     eax, [rsp+180h+var_10C]
0x140037011  mov     dword ptr [rsp+180h+var_160], eax
0x140037015  call    cs:__imp_VssTraceMessage
0x14003701b  jmp     loc_140036E7D
```
