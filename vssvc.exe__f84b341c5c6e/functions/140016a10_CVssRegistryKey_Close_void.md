# CVssRegistryKey::Close(void)

- ea: `0x140016a10`
- end: `0x140016d9e`
- name: `?Close@CVssRegistryKey@@QEAAXXZ`
- size: `910`
- prototype: `void __fastcall(CVssRegistryKey *__hidden this)`
- caller_count: `10`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140008420`
- `0x14000889c`
- `0x140009b50`
- `0x14000c84c`
- `0x14000fba0`
- `0x140015fb0`
- `0x140018130`
- `0x140028d60`
- `0x14002b160`
- `0x140055bec`

## callees

- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140016a10`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016b74`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140016ab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140016bd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140016ab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140016bd3`
- `VssTrace!__imp_VssTraceMessage` at `0x140016d32`
- `VssTrace!__imp_VssTraceMessage` at `0x140016d32`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016c8e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016cbd`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016c8e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016cbd`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140016af4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140016af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016b9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016bc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016ca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016b9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016bc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016ca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016cdb`

## string_xrefs

- `0x140016a4b`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140016a56`: `CVssRegistryKey::Close`

## pseudocode

```c
void __fastcall CVssRegistryKey::Close(CVssRegistryKey *this)
{
  __int64 v2; // rax
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  HKEY v7; // rcx
  LPVOID *v8; // rbx
  LSTATUS v9; // esi
  void *v10; // rcx
  DWORD v11; // esi
  __int64 v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  __int64 v14; // [rsp+30h] [rbp-D0h]
  __int64 v15; // [rsp+38h] [rbp-C8h]
  __int64 v16; // [rsp+40h] [rbp-C0h]
  _DWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v20; // [rsp+68h] [rbp-98h]
  unsigned int v21; // [rsp+70h] [rbp-90h]
  unsigned int v22; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v23; // [rsp+78h] [rbp-88h]
  unsigned int v24; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v26; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v28[2]; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v30; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v31; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v32; // [rsp+D0h] [rbp-30h]
  int v33; // [rsp+D8h] [rbp-28h]
  int v34; // [rsp+DCh] [rbp-24h]
  int v35; // [rsp+E0h] [rbp-20h]
  LPVOID v36[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v37; // [rsp+F8h] [rbp-8h]
  __int128 v38; // [rsp+108h] [rbp+8h]
  __int128 v39; // [rsp+118h] [rbp+18h]
  __int128 v40; // [rsp+128h] [rbp+28h]
  __int128 v41; // [rsp+138h] [rbp+38h]
  __int128 v42; // [rsp+148h] [rbp+48h]
  __int64 v43; // [rsp+158h] [rbp+58h]
  int v44; // [rsp+160h] [rbp+60h]
  __int64 v45; // [rsp+1C0h] [rbp+C0h] BYREF

  v33 = 668;
  v34 = 11;
  v35 = 255;
  v32 = L"REGREGSC";
  v20 = L"REGREGSC";
  v30 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v31 = L"CVssRegistryKey::Close";
  v44 = 0x1000000;
  *(_OWORD *)v36 = 0;
  v43 = 0;
  v37 = 0;
  v18 = 0;
  v38 = 0;
  v23 = L"CVssRegistryKey::Close";
  v39 = 0;
  v19 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v40 = 0;
  v21 = 668;
  v41 = 0;
  v22 = 11;
  v42 = 0;
  v17[1] = -1;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v28 = 0;
  TickCount = GetTickCount();
  v26 = 255;
  v17[0] = 0;
  v29 = 0;
  v45 = 0;
  if ( (int)VssGetTracingContextPerThread(&v45) < 0 || (int)VssSetTracingContextPerThread(v17) < 0 )
  {
    v2 = v29;
  }
  else
  {
    v2 = v45;
    v29 = v45;
  }
  if ( v2 )
    v24 = *(_DWORD *)(v2 + 48) + 1;
  else
    v24 = 0;
  v3 = 160;
  v4 = 160;
  if ( v26 != 255 )
    v4 = v26;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v17, v22) )
    VssTraceMessage(v19, v20, v21, v24, v22, v23, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = v36[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      v36[i] = 0;
    }
  }
  v7 = (HKEY)*((_QWORD *)this + 1);
  if ( v7 )
  {
    v8 = (LPVOID *)((char *)this + 24);
    v9 = RegCloseKey(v7);
    if ( v9 )
    {
      v30 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v32 = L"REGREGSC";
      v31 = L"CVssRegistryKey::Close";
      v33 = 675;
      v34 = 11;
      v35 = 255;
      v44 = 0x1000000;
      memset_0(v36, 0, 0x78u);
      LODWORD(v12) = v9;
      CVssFunctionTracer::Trace(v17, &v30, L"Error on closing key with name %s. lRes == 0x%08lx", *v8, v12);
    }
    *((_QWORD *)this + 1) = 0;
  }
  else
  {
    v8 = (LPVOID *)((char *)this + 24);
  }
  if ( *v8 )
    CoTaskMemFree(*v8);
  v10 = pv[0];
  *v8 = 0;
  CoTaskMemFree(v10);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v28[0]);
  v28[0] = 0;
  CoTaskMemFree(v28[1]);
  v28[1] = 0;
  v11 = GetTickCount() - TickCount;
  LODWORD(v16) = v11;
  if ( v26 != 255 )
    v3 = v26;
  LODWORD(v15) = v11 % 0x3E8;
  LODWORD(v14) = v11 / 0x3E8 % 0x3C;
  LODWORD(v13) = v11 / 0xEA60 % 0x3C;
  LODWORD(v12) = v11 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v17,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v12,
    v13,
    v14,
    v15,
    v16,
    v18);
  VssSetTracingContextPerThread(v29);
}

```

## disassembly

```asm
0x140016a10  push    rbp
0x140016a12  push    rbx
0x140016a13  push    rsi
0x140016a14  push    rdi
0x140016a15  push    r12
0x140016a17  push    r13
0x140016a19  push    r14
0x140016a1b  push    r15
0x140016a1d  lea     rbp, [rsp-78h]
0x140016a22  sub     rsp, 178h
0x140016a29  xorps   xmm0, xmm0
0x140016a2c  mov     [rbp+0B0h+var_D8], 29Ch
0x140016a33  mov     rdi, rcx
0x140016a36  mov     [rbp+0B0h+var_D4], 0Bh
0x140016a3d  lea     rcx, aRegregsc; "REGREGSC"
0x140016a44  mov     [rbp+0B0h+var_D0], 0FFh
0x140016a4b  lea     r12, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140016a52  mov     [rbp+0B0h+var_E0], rcx
0x140016a56  lea     r13, aCvssregistryke_1; "CVssRegistryKey::Close"
0x140016a5d  mov     [rsp+1B0h+var_148], rcx
0x140016a62  xor     eax, eax
0x140016a64  mov     [rbp+0B0h+var_F0], r12
0x140016a68  xor     r15d, r15d
0x140016a6b  mov     [rbp+0B0h+var_E8], r13
0x140016a6f  mov     [rbp+0B0h+var_50], 1000000h
0x140016a76  movups  xmmword ptr [rbp+0B0h+var_C8], xmm0
0x140016a7a  mov     [rbp+0B0h+var_58], rax
0x140016a7e  movups  [rbp+0B0h+var_B8], xmm0
0x140016a82  mov     [rsp+1B0h+var_158], r15d
0x140016a87  movups  [rbp+0B0h+var_A8], xmm0
0x140016a8b  mov     [rsp+1B0h+var_138], r13
0x140016a90  movups  [rbp+0B0h+var_98], xmm0
0x140016a94  mov     [rsp+1B0h+var_150], r12
0x140016a99  movups  [rbp+0B0h+var_88], xmm0
0x140016a9d  mov     [rsp+1B0h+var_140], 29Ch
0x140016aa5  movups  [rbp+0B0h+var_78], xmm0
0x140016aa9  mov     [rsp+1B0h+var_13C], 0Bh
0x140016ab1  movups  [rbp+0B0h+var_68], xmm0
0x140016ab5  call    cs:__imp_GetTickCount
0x140016abb  xorps   xmm0, xmm0
0x140016abe  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x140016ac6  xorps   xmm1, xmm1
0x140016ac9  movdqa  xmmword ptr [rbp+0B0h+pv], xmm0
0x140016ace  lea     rcx, [rbp+0B0h+arg_0]
0x140016ad5  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x140016ada  mov     [rbp+0B0h+var_12C], eax
0x140016add  mov     [rbp+0B0h+var_128], 0FFh
0x140016ae4  mov     [rsp+1B0h+var_160], r15d
0x140016ae9  mov     [rbp+0B0h+var_100], r15
0x140016aed  mov     [rbp+0B0h+arg_0], r15
0x140016af4  call    cs:__imp_VssGetTracingContextPerThread
0x140016afa  test    eax, eax
0x140016afc  jns     loc_140016CB8
0x140016b02  mov     rax, [rbp+0B0h+var_100]
0x140016b06  test    rax, rax
0x140016b09  jz      loc_140016CE6
0x140016b0f  mov     eax, [rax+30h]
0x140016b12  inc     eax
0x140016b14  mov     [rbp+0B0h+var_130], eax
0x140016b17  cmp     [rbp+0B0h+var_128], 0FFh
0x140016b1e  lea     rcx, [rsp+1B0h+var_160]; this
0x140016b23  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x140016b27  mov     r14d, 0A0h
0x140016b2d  mov     ebx, r14d
0x140016b30  cmovnz  ebx, [rbp+0B0h+var_128]
0x140016b34  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140016b39  test    eax, eax
0x140016b3b  jnz     loc_140016CF8
0x140016b41  mov     rbx, r15
0x140016b44  nop     dword ptr [rax+00h]
0x140016b48  nop     dword ptr [rax+rax+00000000h]
0x140016b50  mov     rcx, [rbp+rbx*8+0B0h+var_C8]; pv
0x140016b55  test    rcx, rcx
0x140016b58  jnz     loc_140016CA8
0x140016b5e  inc     rbx
0x140016b61  cmp     rbx, 0Fh
0x140016b65  jnz     short loc_140016B50
0x140016b67  mov     rcx, [rdi+8]; hKey
0x140016b6b  test    rcx, rcx
0x140016b6e  jz      loc_140016CEF
0x140016b74  call    cs:__imp_RegCloseKey
0x140016b7a  lea     rbx, [rdi+18h]
0x140016b7e  mov     esi, eax
0x140016b80  test    eax, eax
0x140016b82  jnz     loc_140016D3D
0x140016b88  mov     [rdi+8], r15
0x140016b8c  mov     rcx, [rbx]; pv
0x140016b8f  test    rcx, rcx
0x140016b92  jnz     loc_140016CDB
0x140016b98  mov     rcx, [rbp+0B0h+pv]; pv
0x140016b9c  mov     [rbx], r15
0x140016b9f  call    cs:__imp_CoTaskMemFree
0x140016ba5  mov     rcx, [rbp+0B0h+pv+8]; pv
0x140016ba9  mov     [rbp+0B0h+pv], r15
0x140016bad  call    cs:__imp_CoTaskMemFree
0x140016bb3  mov     rcx, [rbp+0B0h+var_110]; pv
0x140016bb7  mov     [rbp+0B0h+pv+8], r15
0x140016bbb  call    cs:__imp_CoTaskMemFree
0x140016bc1  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x140016bc5  mov     [rbp+0B0h+var_110], r15
0x140016bc9  call    cs:__imp_CoTaskMemFree
0x140016bcf  mov     [rbp+0B0h+var_110+8], r15
0x140016bd3  call    cs:__imp_GetTickCount
0x140016bd9  mov     r9d, [rsp+1B0h+var_158]
0x140016bde  mov     esi, eax
0x140016be0  sub     esi, [rbp+0B0h+var_12C]
0x140016be3  mov     eax, 10624DD3h
0x140016be8  mul     esi
0x140016bea  mov     [rsp+1B0h+var_168], r9d
0x140016bef  mov     eax, 88888889h
0x140016bf4  mov     edi, edx
0x140016bf6  mov     dword ptr [rsp+1B0h+var_170], esi
0x140016bfa  shr     edi, 6
0x140016bfd  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140016c04  mul     edi
0x140016c06  mov     eax, 45E7B273h
0x140016c0b  mov     ebx, edi
0x140016c0d  shr     edx, 5
0x140016c10  imul    ecx, edx, 3Ch ; '<'
0x140016c13  mul     esi
0x140016c15  sub     ebx, ecx
0x140016c17  mov     eax, 88888889h
0x140016c1c  mov     r11d, edx
0x140016c1f  shr     r11d, 0Eh
0x140016c23  mul     r11d
0x140016c26  mov     eax, 95217CB1h
0x140016c2b  shr     edx, 5
0x140016c2e  imul    ecx, edx, 3Ch ; '<'
0x140016c31  mul     esi
0x140016c33  sub     r11d, ecx
0x140016c36  mov     eax, 88888889h
0x140016c3b  mov     r10d, edx
0x140016c3e  mov     ecx, esi
0x140016c40  shr     r10d, 15h
0x140016c44  mul     r10d
0x140016c47  shr     edx, 5
0x140016c4a  imul    eax, edx, 3Ch ; '<'
0x140016c4d  lea     rdx, aExit; "EXIT"
0x140016c54  sub     r10d, eax
0x140016c57  cmp     [rbp+0B0h+var_128], 0FFh
0x140016c5e  cmovnz  r14d, [rbp+0B0h+var_128]
0x140016c63  imul    eax, edi, 3E8h
0x140016c69  mov     r8d, r14d; unsigned int
0x140016c6c  sub     ecx, eax
0x140016c6e  mov     dword ptr [rsp+1B0h+var_178], ecx
0x140016c72  lea     rcx, [rsp+1B0h+var_160]; this
0x140016c77  mov     dword ptr [rsp+1B0h+var_180], ebx
0x140016c7b  mov     dword ptr [rsp+1B0h+var_188], r11d
0x140016c80  mov     dword ptr [rsp+1B0h+var_190], r10d
0x140016c85  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140016c8a  mov     rcx, [rbp+0B0h+var_100]
0x140016c8e  call    cs:__imp_VssSetTracingContextPerThread
0x140016c94  add     rsp, 178h
0x140016c9b  pop     r15
0x140016c9d  pop     r14
0x140016c9f  pop     r13
0x140016ca1  pop     r12
0x140016ca3  pop     rdi
0x140016ca4  pop     rsi
0x140016ca5  pop     rbx
0x140016ca6  pop     rbp
0x140016ca7  retn
0x140016ca8  call    cs:__imp_CoTaskMemFree
0x140016cae  mov     [rbp+rbx*8+0B0h+var_C8], r15
0x140016cb3  jmp     loc_140016B5E
0x140016cb8  lea     rcx, [rsp+1B0h+var_160]
0x140016cbd  call    cs:__imp_VssSetTracingContextPerThread
0x140016cc3  test    eax, eax
0x140016cc5  js      loc_140016B02
0x140016ccb  mov     rax, [rbp+0B0h+arg_0]
0x140016cd2  mov     [rbp+0B0h+var_100], rax
0x140016cd6  jmp     loc_140016B06
0x140016cdb  call    cs:__imp_CoTaskMemFree
0x140016ce1  jmp     loc_140016B98
0x140016ce6  mov     [rbp+0B0h+var_130], r15d
0x140016cea  jmp     loc_140016B17
0x140016cef  lea     rbx, [rdi+18h]
0x140016cf3  jmp     loc_140016B8C
0x140016cf8  mov     r9d, [rbp+0B0h+var_130]
0x140016cfc  lea     rax, aEnter; "ENTER"
0x140016d03  mov     r8d, [rsp+1B0h+var_140]
0x140016d08  mov     rdx, [rsp+1B0h+var_148]
0x140016d0d  mov     rcx, [rsp+1B0h+var_150]
0x140016d12  mov     [rsp+1B0h+var_170], r15
0x140016d17  mov     dword ptr [rsp+1B0h+var_178], ebx
0x140016d1b  mov     [rsp+1B0h+var_180], rax
0x140016d20  mov     rax, [rsp+1B0h+var_138]
0x140016d25  mov     [rsp+1B0h+var_188], rax
0x140016d2a  mov     eax, [rsp+1B0h+var_13C]
0x140016d2e  mov     dword ptr [rsp+1B0h+var_190], eax
0x140016d32  call    cs:__imp_VssTraceMessage
0x140016d38  jmp     loc_140016B41
0x140016d3d  lea     rax, aRegregsc; "REGREGSC"
0x140016d44  mov     [rbp+0B0h+var_F0], r12
0x140016d48  xor     edx, edx; Val
0x140016d4a  mov     [rbp+0B0h+var_E0], rax
0x140016d4e  mov     r8d, 78h ; 'x'; Size
0x140016d54  mov     [rbp+0B0h+var_E8], r13
0x140016d58  lea     rcx, [rbp+0B0h+var_C8]; void *
0x140016d5c  mov     [rbp+0B0h+var_D8], 2A3h
0x140016d63  mov     [rbp+0B0h+var_D4], 0Bh
0x140016d6a  mov     [rbp+0B0h+var_D0], 0FFh
0x140016d71  mov     [rbp+0B0h+var_50], 1000000h
0x140016d78  call    memset_0
0x140016d7d  mov     r9, [rbx]
0x140016d80  lea     r8, aErrorOnClosing; "Error on closing key with name %s. lRes"...
0x140016d87  lea     rdx, [rbp+0B0h+var_F0]
0x140016d8b  mov     dword ptr [rsp+1B0h+var_190], esi
0x140016d8f  lea     rcx, [rsp+1B0h+var_160]
0x140016d94  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140016d99  jmp     loc_140016B88
```
