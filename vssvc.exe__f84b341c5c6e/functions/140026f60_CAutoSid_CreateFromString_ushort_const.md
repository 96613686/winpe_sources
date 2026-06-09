# CAutoSid::CreateFromString(ushort const *)

- ea: `0x140026f60`
- end: `0x1400272d1`
- name: `?CreateFromString@CAutoSid@@QEAAXPEBG@Z`
- size: `881`
- prototype: `void(CAutoSid *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001b9f0`

## callees

- `0x1400138e0`
- `0x140013c60`
- `0x140026f60`
- `0x140028b48`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027215`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027008`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027104`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027008`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140027104`
- `VssTrace!__imp_VssTraceMessage` at `0x1400272c6`
- `VssTrace!__imp_VssTraceMessage` at `0x1400272c6`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400271bf`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400271ee`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400271bf`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400271ee`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140027047`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140027047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400271d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400270fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400271d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400270be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400270be`

## string_xrefs

- `0x140026f7f`: `base\stor\vss\modules\sec\security.cxx`
- `0x140027276`: `ConvertStringSidToSid(%s)`
- `0x140026f8a`: `CAutoSid::CreateFromString`
- `0x140027230`: `CAutoSid::CreateFromString`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAutoSid::CreateFromString(PSID *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  __int64 i; // rbx
  void *v8; // rcx
  DWORD v9; // esi
  signed int LastError; // eax
  __int64 v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+28h] [rbp-D8h]
  __int64 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+38h] [rbp-C8h]
  __int64 v15; // [rsp+40h] [rbp-C0h]
  _DWORD v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  signed int v17; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v18; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp-98h]
  unsigned int v20; // [rsp+70h] [rbp-90h]
  unsigned int v21; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v22; // [rsp+78h] [rbp-88h]
  unsigned int v23; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v25; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v27[2]; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v29; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v30; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v31; // [rsp+D0h] [rbp-30h]
  int v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+DCh] [rbp-24h]
  int v34; // [rsp+E0h] [rbp-20h]
  LPVOID v35[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v36; // [rsp+F8h] [rbp-8h]
  __int128 v37; // [rsp+108h] [rbp+8h]
  __int128 v38; // [rsp+118h] [rbp+18h]
  __int128 v39; // [rsp+128h] [rbp+28h]
  __int128 v40; // [rsp+138h] [rbp+38h]
  __int128 v41; // [rsp+148h] [rbp+48h]
  __int64 v42; // [rsp+158h] [rbp+58h]
  int v43; // [rsp+160h] [rbp+60h]
  __int64 v44; // [rsp+1C0h] [rbp+C0h] BYREF

  v29 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v30 = L"CAutoSid::CreateFromString";
  v31 = L"SECSECRC";
  v32 = 914;
  v33 = 11;
  v34 = 255;
  v43 = 0x1000000;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v17 = 0;
  v22 = L"CAutoSid::CreateFromString";
  v18 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v19 = L"SECSECRC";
  v20 = 914;
  v21 = 11;
  TickCount = GetTickCount();
  v16[1] = -1;
  v25 = 255;
  v16[0] = 0;
  v28 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v27 = 0;
  v44 = 0;
  if ( (int)VssGetTracingContextPerThread(&v44) < 0 || (int)VssSetTracingContextPerThread(v16) < 0 )
  {
    v4 = v28;
  }
  else
  {
    v4 = v44;
    v28 = v44;
  }
  if ( v4 )
    v23 = *(_DWORD *)(v4 + 48) + 1;
  else
    v23 = 0;
  v5 = 160;
  v6 = 160;
  if ( v25 != 255 )
    v6 = v25;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v16, v21) )
    VssTraceMessage(v18, v19, v20, v23, v21, v22, L"ENTER", v6, 0);
  for ( i = 0; i != 15; ++i )
  {
    v8 = v35[i];
    if ( v8 )
    {
      CoTaskMemFree(v8);
      v35[i] = 0;
    }
  }
  if ( !ConvertStringSidToSidW(a2, this + 1) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v17 = LastError;
    v29 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v30 = L"CAutoSid::CreateFromString";
    v31 = L"SECSECRC";
    v32 = 921;
    v33 = 11;
    v34 = 255;
    v43 = 0x1000000;
    memset_0(v35, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(v16, &v29, L"ConvertStringSidToSid(%s)", a2);
  }
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v27[0]);
  v27[0] = 0;
  CoTaskMemFree(v27[1]);
  v27[1] = 0;
  v9 = GetTickCount() - TickCount;
  if ( v25 != 255 )
    v5 = v25;
  LODWORD(v15) = v9;
  LODWORD(v14) = v9 % 0x3E8;
  LODWORD(v13) = v9 / 0x3E8 % 0x3C;
  LODWORD(v12) = v9 / 0xEA60 % 0x3C;
  LODWORD(v11) = v9 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v16,
    L"EXIT",
    v5,
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
0x140026f60  push    rbp
0x140026f62  push    rbx
0x140026f63  push    rsi
0x140026f64  push    rdi
0x140026f65  push    r12
0x140026f67  push    r13
0x140026f69  push    r14
0x140026f6b  push    r15
0x140026f6d  lea     rbp, [rsp-78h]
0x140026f72  sub     rsp, 178h
0x140026f79  mov     rdi, rdx
0x140026f7c  mov     rsi, rcx
0x140026f7f  lea     r13, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140026f86  mov     [rbp+0B0h+var_F0], r13
0x140026f8a  lea     rcx, aCautosidCreate_0; "CAutoSid::CreateFromString"
0x140026f91  mov     [rbp+0B0h+var_E8], rcx
0x140026f95  lea     rdx, aSecsecrc; "SECSECRC"
0x140026f9c  mov     [rbp+0B0h+var_E0], rdx
0x140026fa0  mov     [rbp+0B0h+var_D8], 392h
0x140026fa7  mov     [rbp+0B0h+var_D4], 0Bh
0x140026fae  mov     [rbp+0B0h+var_D0], 0FFh
0x140026fb5  xor     r15d, r15d
0x140026fb8  mov     [rbp+0B0h+var_50], 1000000h
0x140026fbf  xorps   xmm0, xmm0
0x140026fc2  xor     eax, eax
0x140026fc4  movups  xmmword ptr [rbp+0B0h+var_C8], xmm0
0x140026fc8  movups  [rbp+0B0h+var_B8], xmm0
0x140026fcc  movups  [rbp+0B0h+var_A8], xmm0
0x140026fd0  movups  [rbp+0B0h+var_98], xmm0
0x140026fd4  movups  [rbp+0B0h+var_88], xmm0
0x140026fd8  movups  [rbp+0B0h+var_78], xmm0
0x140026fdc  movups  [rbp+0B0h+var_68], xmm0
0x140026fe0  mov     [rbp+0B0h+var_58], rax
0x140026fe4  mov     [rsp+1B0h+var_158], r15d
0x140026fe9  mov     [rsp+1B0h+var_138], rcx
0x140026fee  mov     [rsp+1B0h+var_150], r13
0x140026ff3  mov     [rsp+1B0h+var_148], rdx
0x140026ff8  mov     [rsp+1B0h+var_140], 392h
0x140027000  mov     [rsp+1B0h+var_13C], 0Bh
0x140027008  call    cs:__imp_GetTickCount
0x14002700e  mov     [rbp+0B0h+var_12C], eax
0x140027011  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x140027019  mov     [rbp+0B0h+var_128], 0FFh
0x140027020  mov     [rsp+1B0h+var_160], r15d
0x140027025  mov     [rbp+0B0h+var_100], r15
0x140027029  xorps   xmm0, xmm0
0x14002702c  movdqa  xmmword ptr [rbp+0B0h+pv], xmm0
0x140027031  xorps   xmm1, xmm1
0x140027034  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x140027039  mov     [rbp+0B0h+arg_0], r15
0x140027040  lea     rcx, [rbp+0B0h+arg_0]
0x140027047  call    cs:__imp_VssGetTracingContextPerThread
0x14002704d  test    eax, eax
0x14002704f  jns     loc_1400271E9
0x140027055  mov     rax, [rbp+0B0h+var_100]
0x140027059  test    rax, rax
0x14002705c  jz      loc_14002720C
0x140027062  mov     eax, [rax+30h]
0x140027065  inc     eax
0x140027067  mov     [rbp+0B0h+var_130], eax
0x14002706a  mov     r14d, 0A0h
0x140027070  mov     ebx, r14d
0x140027073  cmp     [rbp+0B0h+var_128], 0FFh
0x14002707a  cmovnz  ebx, [rbp+0B0h+var_128]
0x14002707e  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x140027082  lea     rcx, [rsp+1B0h+var_160]; this
0x140027087  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14002708c  test    eax, eax
0x14002708e  jnz     loc_14002728C
0x140027094  mov     rbx, r15
0x140027097  nop     word ptr [rax+rax+00000000h]
0x1400270a0  mov     rcx, [rbp+rbx*8+0B0h+var_C8]; pv
0x1400270a5  test    rcx, rcx
0x1400270a8  jnz     loc_1400271D9
0x1400270ae  inc     rbx
0x1400270b1  cmp     rbx, 0Fh
0x1400270b5  jnz     short loc_1400270A0
0x1400270b7  lea     rdx, [rsi+8]; Sid
0x1400270bb  mov     rcx, rdi; StringSid
0x1400270be  call    cs:__imp_ConvertStringSidToSidW
0x1400270c4  test    eax, eax
0x1400270c6  jz      loc_140027215
0x1400270cc  mov     rcx, [rbp+0B0h+pv]; pv
0x1400270d0  call    cs:__imp_CoTaskMemFree
0x1400270d6  mov     [rbp+0B0h+pv], r15
0x1400270da  mov     rcx, [rbp+0B0h+pv+8]; pv
0x1400270de  call    cs:__imp_CoTaskMemFree
0x1400270e4  mov     [rbp+0B0h+pv+8], r15
0x1400270e8  mov     rcx, [rbp+0B0h+var_110]; pv
0x1400270ec  call    cs:__imp_CoTaskMemFree
0x1400270f2  mov     [rbp+0B0h+var_110], r15
0x1400270f6  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x1400270fa  call    cs:__imp_CoTaskMemFree
0x140027100  mov     [rbp+0B0h+var_110+8], r15
0x140027104  call    cs:__imp_GetTickCount
0x14002710a  mov     esi, eax
0x14002710c  sub     esi, [rbp+0B0h+var_12C]
0x14002710f  mov     eax, 10624DD3h
0x140027114  mul     esi
0x140027116  mov     edi, edx
0x140027118  shr     edi, 6
0x14002711b  mov     eax, 88888889h
0x140027120  mul     edi
0x140027122  shr     edx, 5
0x140027125  imul    ecx, edx, 3Ch ; '<'
0x140027128  mov     ebx, edi
0x14002712a  sub     ebx, ecx
0x14002712c  mov     eax, 45E7B273h
0x140027131  mul     esi
0x140027133  mov     r11d, edx
0x140027136  shr     r11d, 0Eh
0x14002713a  mov     eax, 88888889h
0x14002713f  mul     r11d
0x140027142  shr     edx, 5
0x140027145  imul    ecx, edx, 3Ch ; '<'
0x140027148  sub     r11d, ecx
0x14002714b  mov     eax, 95217CB1h
0x140027150  mul     esi
0x140027152  mov     r10d, edx
0x140027155  shr     r10d, 15h
0x140027159  mov     eax, 88888889h
0x14002715e  mul     r10d
0x140027161  shr     edx, 5
0x140027164  imul    eax, edx, 3Ch ; '<'
0x140027167  sub     r10d, eax
0x14002716a  mov     r9d, [rsp+1B0h+var_158]
0x14002716f  cmp     [rbp+0B0h+var_128], 0FFh
0x140027176  cmovnz  r14d, [rbp+0B0h+var_128]
0x14002717b  imul    eax, edi, 3E8h
0x140027181  mov     ecx, esi
0x140027183  sub     ecx, eax
0x140027185  mov     [rsp+1B0h+var_168], r9d
0x14002718a  mov     dword ptr [rsp+1B0h+var_170], esi
0x14002718e  mov     dword ptr [rsp+1B0h+var_178], ecx
0x140027192  mov     dword ptr [rsp+1B0h+var_180], ebx
0x140027196  mov     dword ptr [rsp+1B0h+var_188], r11d
0x14002719b  mov     dword ptr [rsp+1B0h+var_190], r10d
0x1400271a0  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x1400271a7  mov     r8d, r14d; unsigned int
0x1400271aa  lea     rdx, aExit; "EXIT"
0x1400271b1  lea     rcx, [rsp+1B0h+var_160]; this
0x1400271b6  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400271bb  mov     rcx, [rbp+0B0h+var_100]
0x1400271bf  call    cs:__imp_VssSetTracingContextPerThread
0x1400271c5  add     rsp, 178h
0x1400271cc  pop     r15
0x1400271ce  pop     r14
0x1400271d0  pop     r13
0x1400271d2  pop     r12
0x1400271d4  pop     rdi
0x1400271d5  pop     rsi
0x1400271d6  pop     rbx
0x1400271d7  pop     rbp
0x1400271d8  retn
0x1400271d9  call    cs:__imp_CoTaskMemFree
0x1400271df  mov     [rbp+rbx*8+0B0h+var_C8], r15
0x1400271e4  jmp     loc_1400270AE
0x1400271e9  lea     rcx, [rsp+1B0h+var_160]
0x1400271ee  call    cs:__imp_VssSetTracingContextPerThread
0x1400271f4  test    eax, eax
0x1400271f6  js      loc_140027055
0x1400271fc  mov     rax, [rbp+0B0h+arg_0]
0x140027203  mov     [rbp+0B0h+var_100], rax
0x140027207  jmp     loc_140027059
0x14002720c  mov     [rbp+0B0h+var_130], r15d
0x140027210  jmp     loc_14002706A
0x140027215  call    cs:__imp_GetLastError
0x14002721b  nop
0x14002721c  test    eax, eax
0x14002721e  jle     short loc_140027228
0x140027220  movzx   eax, ax
0x140027223  or      eax, 80070000h
0x140027228  mov     [rsp+1B0h+var_158], eax
0x14002722c  mov     [rbp+0B0h+var_F0], r13
0x140027230  lea     rax, aCautosidCreate_0; "CAutoSid::CreateFromString"
0x140027237  mov     [rbp+0B0h+var_E8], rax
0x14002723b  lea     rax, aSecsecrc; "SECSECRC"
0x140027242  mov     [rbp+0B0h+var_E0], rax
0x140027246  mov     [rbp+0B0h+var_D8], 399h
0x14002724d  mov     [rbp+0B0h+var_D4], 0Bh
0x140027254  mov     [rbp+0B0h+var_D0], 0FFh
0x14002725b  mov     [rbp+0B0h+var_50], 1000000h
0x140027262  xor     edx, edx; Val
0x140027264  mov     r8d, 78h ; 'x'; Size
0x14002726a  lea     rcx, [rbp+0B0h+var_C8]; void *
0x14002726e  call    memset_0
0x140027273  mov     r9, rdi
0x140027276  lea     r8, aConvertstrings_0; "ConvertStringSidToSid(%s)"
0x14002727d  lea     rdx, [rbp+0B0h+var_F0]
0x140027281  lea     rcx, [rsp+1B0h+var_160]
0x140027286  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14002728c  mov     [rsp+1B0h+var_170], r15
0x140027291  mov     dword ptr [rsp+1B0h+var_178], ebx
0x140027295  lea     rax, aEnter; "ENTER"
0x14002729c  mov     [rsp+1B0h+var_180], rax
0x1400272a1  mov     rax, [rsp+1B0h+var_138]
0x1400272a6  mov     [rsp+1B0h+var_188], rax
0x1400272ab  mov     eax, [rsp+1B0h+var_13C]
0x1400272af  mov     dword ptr [rsp+1B0h+var_190], eax
0x1400272b3  mov     r9d, [rbp+0B0h+var_130]
0x1400272b7  mov     r8d, [rsp+1B0h+var_140]
0x1400272bc  mov     rdx, [rsp+1B0h+var_148]
0x1400272c1  mov     rcx, [rsp+1B0h+var_150]
0x1400272c6  call    cs:__imp_VssTraceMessage
0x1400272cc  jmp     loc_140027094
```
