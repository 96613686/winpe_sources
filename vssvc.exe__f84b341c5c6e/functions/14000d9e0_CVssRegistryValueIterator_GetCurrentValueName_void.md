# CVssRegistryValueIterator::GetCurrentValueName(void)

- ea: `0x14000d9e0`
- end: `0x14000dcbf`
- name: `?GetCurrentValueName@CVssRegistryValueIterator@@QEAAPEAGXZ`
- size: `735`
- prototype: `unsigned __int16 *__fastcall(CVssRegistryValueIterator *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c84c`
- `0x14002b160`

## callees

- `0x14000d9e0`
- `0x14000dcd0`
- `0x1400138e0`
- `0x140013c60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000da7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000db6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000da7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000db6b`
- `VssTrace!__imp_VssTraceMessage` at `0x14000dcb4`
- `VssTrace!__imp_VssTraceMessage` at `0x14000dcb4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000dc26`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000dc54`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000dc26`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000dc54`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000dabd`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000dabd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000dc3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000dc3f`

## string_xrefs

- `0x14000da03`: `CVssRegistryValueIterator::GetCurrentValueName`
- `0x14000d9f8`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CVssRegistryValueIterator::GetCurrentValueName(CVssRegistryValueIterator *this)
{
  __int64 v2; // rax
  unsigned int v3; // r15d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  __int64 v7; // r14
  DWORD v8; // esi
  __int64 v10; // [rsp+20h] [rbp-E0h]
  __int64 v11; // [rsp+28h] [rbp-D8h]
  __int64 v12; // [rsp+30h] [rbp-D0h]
  __int64 v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  _DWORD v15[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v17; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v18; // [rsp+68h] [rbp-98h]
  unsigned int v19; // [rsp+70h] [rbp-90h]
  unsigned int v20; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v21; // [rsp+78h] [rbp-88h]
  unsigned int v22; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v24; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v26[2]; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v28; // [rsp+C0h] [rbp-40h]
  const wchar_t *v29; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v30; // [rsp+D0h] [rbp-30h]
  int v31; // [rsp+D8h] [rbp-28h]
  int v32; // [rsp+DCh] [rbp-24h]
  int v33; // [rsp+E0h] [rbp-20h]
  LPVOID v34[2]; // [rsp+E8h] [rbp-18h]
  __int128 v35; // [rsp+F8h] [rbp-8h]
  __int128 v36; // [rsp+108h] [rbp+8h]
  __int128 v37; // [rsp+118h] [rbp+18h]
  __int128 v38; // [rsp+128h] [rbp+28h]
  __int128 v39; // [rsp+138h] [rbp+38h]
  __int128 v40; // [rsp+148h] [rbp+48h]
  __int64 v41; // [rsp+158h] [rbp+58h]
  int v42; // [rsp+160h] [rbp+60h]
  __int64 v43; // [rsp+1B0h] [rbp+B0h] BYREF

  v28 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v29 = L"CVssRegistryValueIterator::GetCurrentValueName";
  v30 = L"REGREGSC";
  v31 = 854;
  v32 = 11;
  v33 = 255;
  v42 = 0x1000000;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v16 = 0;
  v21 = L"CVssRegistryValueIterator::GetCurrentValueName";
  v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v18 = L"REGREGSC";
  v19 = 854;
  v20 = 11;
  TickCount = GetTickCount();
  v15[1] = -1;
  v24 = 255;
  v15[0] = 0;
  v27 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v26 = 0;
  v43 = 0;
  if ( (int)VssGetTracingContextPerThread(&v43) < 0 || (int)VssSetTracingContextPerThread(v15) < 0 )
  {
    v2 = v27;
  }
  else
  {
    v2 = v43;
    v27 = v43;
  }
  if ( v2 )
    v22 = *(_DWORD *)(v2 + 48) + 1;
  else
    v22 = 0;
  v3 = 160;
  v4 = 160;
  if ( v24 != 255 )
    v4 = v24;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v15, v20) )
    VssTraceMessage(v17, v18, v19, v22, v20, v21, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = v34[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      v34[i] = 0;
    }
  }
  CVssRegistryValueIterator::ReadCurrentValueDetails(this);
  v7 = *((_QWORD *)this + 4);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v26[0]);
  v26[0] = 0;
  CoTaskMemFree(v26[1]);
  v26[1] = 0;
  v8 = GetTickCount() - TickCount;
  if ( v24 != 255 )
    v3 = v24;
  LODWORD(v14) = v8;
  LODWORD(v13) = v8 % 0x3E8;
  LODWORD(v12) = v8 / 0x3E8 % 0x3C;
  LODWORD(v11) = v8 / 0xEA60 % 0x3C;
  LODWORD(v10) = v8 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v15,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v10,
    v11,
    v12,
    v13,
    v14,
    v16);
  VssSetTracingContextPerThread(v27);
  return (unsigned __int16 *)v7;
}

```

## disassembly

```asm
0x14000d9e0  push    rbp
0x14000d9e2  push    rbx
0x14000d9e3  push    rsi
0x14000d9e4  push    rdi
0x14000d9e5  push    r14
0x14000d9e7  push    r15
0x14000d9e9  lea     rbp, [rsp-78h]
0x14000d9ee  sub     rsp, 178h
0x14000d9f5  mov     r14, rcx
0x14000d9f8  lea     r8, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000d9ff  mov     [rbp+0A0h+var_E0], r8
0x14000da03  lea     rcx, aCvssregistryva_0; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000da0a  mov     [rbp+0A0h+var_D8], rcx
0x14000da0e  lea     rdx, aRegregsc; "REGREGSC"
0x14000da15  mov     [rbp+0A0h+var_D0], rdx
0x14000da19  mov     [rbp+0A0h+var_C8], 356h
0x14000da20  mov     [rbp+0A0h+var_C4], 0Bh
0x14000da27  mov     [rbp+0A0h+var_C0], 0FFh
0x14000da2e  xor     edi, edi
0x14000da30  mov     [rbp+0A0h+var_40], 1000000h
0x14000da37  xorps   xmm0, xmm0
0x14000da3a  xor     eax, eax
0x14000da3c  movups  xmmword ptr [rbp+0A0h+var_B8], xmm0
0x14000da40  movups  [rbp+0A0h+var_A8], xmm0
0x14000da44  movups  [rbp+0A0h+var_98], xmm0
0x14000da48  movups  [rbp+0A0h+var_88], xmm0
0x14000da4c  movups  [rbp+0A0h+var_78], xmm0
0x14000da50  movups  [rbp+0A0h+var_68], xmm0
0x14000da54  movups  [rbp+0A0h+var_58], xmm0
0x14000da58  mov     [rbp+0A0h+var_48], rax
0x14000da5c  mov     [rsp+1A0h+var_148], edi
0x14000da60  mov     [rsp+1A0h+var_128], rcx
0x14000da65  mov     [rsp+1A0h+var_140], r8
0x14000da6a  mov     [rsp+1A0h+var_138], rdx
0x14000da6f  mov     [rsp+1A0h+var_130], 356h
0x14000da77  mov     [rsp+1A0h+var_12C], 0Bh
0x14000da7f  call    cs:__imp_GetTickCount
0x14000da85  mov     [rbp+0A0h+var_11C], eax
0x14000da88  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x14000da90  mov     [rbp+0A0h+var_118], 0FFh
0x14000da97  mov     [rsp+1A0h+var_150], edi
0x14000da9b  mov     [rbp+0A0h+var_F0], rdi
0x14000da9f  xorps   xmm0, xmm0
0x14000daa2  movdqa  xmmword ptr [rbp+0A0h+pv], xmm0
0x14000daa7  xorps   xmm1, xmm1
0x14000daaa  movdqa  xmmword ptr [rbp+0A0h+var_100], xmm1
0x14000daaf  mov     [rbp+0A0h+arg_0], rdi
0x14000dab6  lea     rcx, [rbp+0A0h+arg_0]
0x14000dabd  call    cs:__imp_VssGetTracingContextPerThread
0x14000dac3  test    eax, eax
0x14000dac5  jns     loc_14000DC4F
0x14000dacb  mov     rax, [rbp+0A0h+var_F0]
0x14000dacf  test    rax, rax
0x14000dad2  jz      loc_14000DC72
0x14000dad8  mov     eax, [rax+30h]
0x14000dadb  inc     eax
0x14000dadd  mov     [rbp+0A0h+var_120], eax
0x14000dae0  mov     r15d, 0A0h
0x14000dae6  mov     ebx, r15d
0x14000dae9  cmp     [rbp+0A0h+var_118], 0FFh
0x14000daf0  cmovnz  ebx, [rbp+0A0h+var_118]
0x14000daf4  mov     edx, [rsp+1A0h+var_12C]; unsigned int
0x14000daf8  lea     rcx, [rsp+1A0h+var_150]; this
0x14000dafd  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000db02  test    eax, eax
0x14000db04  jnz     loc_14000DC7A
0x14000db0a  mov     rbx, rdi
0x14000db0d  nop     dword ptr [rax]
0x14000db10  mov     rcx, [rbp+rbx*8+0A0h+var_B8]; pv
0x14000db15  test    rcx, rcx
0x14000db18  jnz     loc_14000DC3F
0x14000db1e  inc     rbx
0x14000db21  cmp     rbx, 0Fh
0x14000db25  jnz     short loc_14000DB10
0x14000db27  mov     rcx, r14; this
0x14000db2a  call    ?ReadCurrentValueDetails@CVssRegistryValueIterator@@AEAAXXZ; CVssRegistryValueIterator::ReadCurrentValueDetails(void)
0x14000db2f  mov     r14, [r14+20h]
0x14000db33  mov     rcx, [rbp+0A0h+pv]; pv
0x14000db37  call    cs:__imp_CoTaskMemFree
0x14000db3d  mov     [rbp+0A0h+pv], rdi
0x14000db41  mov     rcx, [rbp+0A0h+pv+8]; pv
0x14000db45  call    cs:__imp_CoTaskMemFree
0x14000db4b  mov     [rbp+0A0h+pv+8], rdi
0x14000db4f  mov     rcx, [rbp+0A0h+var_100]; pv
0x14000db53  call    cs:__imp_CoTaskMemFree
0x14000db59  mov     [rbp+0A0h+var_100], rdi
0x14000db5d  mov     rcx, [rbp+0A0h+var_100+8]; pv
0x14000db61  call    cs:__imp_CoTaskMemFree
0x14000db67  mov     [rbp+0A0h+var_100+8], rdi
0x14000db6b  call    cs:__imp_GetTickCount
0x14000db71  mov     esi, eax
0x14000db73  sub     esi, [rbp+0A0h+var_11C]
0x14000db76  mov     eax, 10624DD3h
0x14000db7b  mul     esi
0x14000db7d  mov     edi, edx
0x14000db7f  shr     edi, 6
0x14000db82  mov     eax, 88888889h
0x14000db87  mul     edi
0x14000db89  shr     edx, 5
0x14000db8c  imul    ecx, edx, 3Ch ; '<'
0x14000db8f  mov     ebx, edi
0x14000db91  sub     ebx, ecx
0x14000db93  mov     eax, 45E7B273h
0x14000db98  mul     esi
0x14000db9a  mov     r11d, edx
0x14000db9d  shr     r11d, 0Eh
0x14000dba1  mov     eax, 88888889h
0x14000dba6  mul     r11d
0x14000dba9  shr     edx, 5
0x14000dbac  imul    ecx, edx, 3Ch ; '<'
0x14000dbaf  sub     r11d, ecx
0x14000dbb2  mov     eax, 95217CB1h
0x14000dbb7  mul     esi
0x14000dbb9  mov     r10d, edx
0x14000dbbc  shr     r10d, 15h
0x14000dbc0  mov     eax, 88888889h
0x14000dbc5  mul     r10d
0x14000dbc8  shr     edx, 5
0x14000dbcb  imul    eax, edx, 3Ch ; '<'
0x14000dbce  sub     r10d, eax
0x14000dbd1  mov     r9d, [rsp+1A0h+var_148]
0x14000dbd6  cmp     [rbp+0A0h+var_118], 0FFh
0x14000dbdd  cmovnz  r15d, [rbp+0A0h+var_118]
0x14000dbe2  imul    ecx, edi, 3E8h
0x14000dbe8  mov     edx, esi
0x14000dbea  sub     edx, ecx
0x14000dbec  mov     [rsp+1A0h+var_158], r9d
0x14000dbf1  mov     dword ptr [rsp+1A0h+var_160], esi
0x14000dbf5  mov     dword ptr [rsp+1A0h+var_168], edx
0x14000dbf9  mov     dword ptr [rsp+1A0h+var_170], ebx
0x14000dbfd  mov     dword ptr [rsp+1A0h+var_178], r11d
0x14000dc02  mov     dword ptr [rsp+1A0h+var_180], r10d
0x14000dc07  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14000dc0e  mov     r8d, r15d; unsigned int
0x14000dc11  lea     rdx, aExit; "EXIT"
0x14000dc18  lea     rcx, [rsp+1A0h+var_150]; this
0x14000dc1d  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14000dc22  mov     rcx, [rbp+0A0h+var_F0]
0x14000dc26  call    cs:__imp_VssSetTracingContextPerThread
0x14000dc2c  mov     rax, r14
0x14000dc2f  add     rsp, 178h
0x14000dc36  pop     r15
0x14000dc38  pop     r14
0x14000dc3a  pop     rdi
0x14000dc3b  pop     rsi
0x14000dc3c  pop     rbx
0x14000dc3d  pop     rbp
0x14000dc3e  retn
0x14000dc3f  call    cs:__imp_CoTaskMemFree
0x14000dc45  mov     [rbp+rbx*8+0A0h+var_B8], rdi
0x14000dc4a  jmp     loc_14000DB1E
0x14000dc4f  lea     rcx, [rsp+1A0h+var_150]
0x14000dc54  call    cs:__imp_VssSetTracingContextPerThread
0x14000dc5a  test    eax, eax
0x14000dc5c  js      loc_14000DACB
0x14000dc62  mov     rax, [rbp+0A0h+arg_0]
0x14000dc69  mov     [rbp+0A0h+var_F0], rax
0x14000dc6d  jmp     loc_14000DACF
0x14000dc72  mov     [rbp+0A0h+var_120], edi
0x14000dc75  jmp     loc_14000DAE0
0x14000dc7a  mov     [rsp+1A0h+var_160], rdi
0x14000dc7f  mov     dword ptr [rsp+1A0h+var_168], ebx
0x14000dc83  lea     rax, aEnter; "ENTER"
0x14000dc8a  mov     [rsp+1A0h+var_170], rax
0x14000dc8f  mov     rax, [rsp+1A0h+var_128]
0x14000dc94  mov     [rsp+1A0h+var_178], rax
0x14000dc99  mov     eax, [rsp+1A0h+var_12C]
0x14000dc9d  mov     dword ptr [rsp+1A0h+var_180], eax
0x14000dca1  mov     r9d, [rbp+0A0h+var_120]
0x14000dca5  mov     r8d, [rsp+1A0h+var_130]
0x14000dcaa  mov     rdx, [rsp+1A0h+var_138]
0x14000dcaf  mov     rcx, [rsp+1A0h+var_140]
0x14000dcb4  call    cs:__imp_VssTraceMessage
0x14000dcba  jmp     loc_14000DB0A
```
