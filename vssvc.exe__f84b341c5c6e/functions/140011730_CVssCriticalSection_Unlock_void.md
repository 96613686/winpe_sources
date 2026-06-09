# CVssCriticalSection::Unlock(void)

- ea: `0x140011730`
- end: `0x140011a87`
- name: `?Unlock@CVssCriticalSection@@QEAAXXZ`
- size: `855`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140011440`

## callees

- `0x140011730`
- `0x1400138e0`
- `0x140013c60`
- `0x140046aa0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011889`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011889`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400117d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400118c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400117d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400118c8`
- `VssTrace!__imp_VssTraceMessage` at `0x140011a12`
- `VssTrace!__imp_VssTraceMessage` at `0x140011a12`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011983`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400119b2`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011983`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400119b2`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140011811`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140011811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011894`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400118a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400118b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400118be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001199d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011894`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400118a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400118b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400118be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001199d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssCriticalSection::Unlock(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rax
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  DWORD v7; // esi
  __int64 v8; // [rsp+20h] [rbp-E0h]
  __int64 v9; // [rsp+28h] [rbp-D8h]
  __int64 v10; // [rsp+30h] [rbp-D0h]
  __int64 v11; // [rsp+38h] [rbp-C8h]
  __int64 v12; // [rsp+40h] [rbp-C0h]
  _DWORD v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v16; // [rsp+68h] [rbp-98h]
  unsigned int v17; // [rsp+70h] [rbp-90h]
  unsigned int v18; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v19; // [rsp+78h] [rbp-88h]
  unsigned int v20; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v22; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v24[2]; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v26; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v27; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D8h] [rbp-28h]
  int v30; // [rsp+DCh] [rbp-24h]
  int v31; // [rsp+E0h] [rbp-20h]
  LPVOID v32[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v33; // [rsp+F8h] [rbp-8h]
  __int128 v34; // [rsp+108h] [rbp+8h]
  __int128 v35; // [rsp+118h] [rbp+18h]
  __int128 v36; // [rsp+128h] [rbp+28h]
  __int128 v37; // [rsp+138h] [rbp+38h]
  __int128 v38; // [rsp+148h] [rbp+48h]
  __int64 v39; // [rsp+158h] [rbp+58h]
  int v40; // [rsp+160h] [rbp+60h]
  __int64 v41; // [rsp+1C0h] [rbp+C0h] BYREF

  v26 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v27 = L"CVssCriticalSection::Unlock";
  v28 = L"INCTYPEH";
  v29 = 220;
  v30 = 11;
  v31 = 255;
  v40 = 0x1000000;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v14 = 0;
  v19 = L"CVssCriticalSection::Unlock";
  v15 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v16 = L"INCTYPEH";
  v17 = 220;
  v18 = 11;
  TickCount = GetTickCount();
  v13[1] = -1;
  v22 = 255;
  v13[0] = 0;
  v25 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v24 = 0;
  v41 = 0;
  if ( (int)VssGetTracingContextPerThread(&v41) < 0 || (int)VssSetTracingContextPerThread(v13) < 0 )
  {
    v2 = v25;
  }
  else
  {
    v2 = v41;
    v25 = v41;
  }
  if ( v2 )
    v20 = *(_DWORD *)(v2 + 48) + 1;
  else
    v20 = 0;
  v3 = 160;
  v4 = 160;
  if ( v22 != 255 )
    v4 = v22;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v13, v18) )
    VssTraceMessage(v15, v16, v17, v20, v18, v19, L"ENTER", v4, 0);
  for ( i = 0; i != 15; ++i )
  {
    v6 = v32[i];
    if ( v6 )
    {
      CoTaskMemFree(v6);
      v32[i] = 0;
    }
  }
  if ( !LOBYTE(lpCriticalSection[1].DebugInfo) )
  {
    v26 = L"base\\stor\\vss\\inc\\vs_types.hxx";
    v27 = L"CVssCriticalSection::Unlock";
    v28 = L"INCTYPEH";
    v29 = 224;
    v30 = 11;
    v31 = 255;
    v40 = 0x1000000;
    memset_0(v32, 0, 0x78u);
    CVssFunctionTracer::ThrowIf(v13, BYTE1(lpCriticalSection[1].DebugInfo), &v26, 2147942414LL, L"Non-initialized CS");
  }
  _InterlockedDecrement((volatile signed __int32 *)&lpCriticalSection[1].DebugInfo + 1);
  LeaveCriticalSection(lpCriticalSection);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v24[0]);
  v24[0] = 0;
  CoTaskMemFree(v24[1]);
  v24[1] = 0;
  v7 = GetTickCount() - TickCount;
  if ( v22 != 255 )
    v3 = v22;
  LODWORD(v12) = v7;
  LODWORD(v11) = v7 % 0x3E8;
  LODWORD(v10) = v7 / 0x3E8 % 0x3C;
  LODWORD(v9) = v7 / 0xEA60 % 0x3C;
  LODWORD(v8) = v7 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v13,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v8,
    v9,
    v10,
    v11,
    v12,
    v14);
  VssSetTracingContextPerThread(v25);
}

```

## disassembly

```asm
0x140011730  push    rbp
0x140011732  push    rbx
0x140011733  push    rsi
0x140011734  push    rdi
0x140011735  push    r12
0x140011737  push    r13
0x140011739  push    r14
0x14001173b  push    r15
0x14001173d  lea     rbp, [rsp-78h]
0x140011742  sub     rsp, 178h
0x140011749  mov     rdi, rcx
0x14001174c  lea     r12, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140011753  mov     [rbp+0B0h+var_F0], r12
0x140011757  lea     r13, aCvsscriticalse_0; "CVssCriticalSection::Unlock"
0x14001175e  mov     [rbp+0B0h+var_E8], r13
0x140011762  lea     rcx, aInctypeh; "INCTYPEH"
0x140011769  mov     [rbp+0B0h+var_E0], rcx
0x14001176d  mov     [rbp+0B0h+var_D8], 0DCh
0x140011774  mov     [rbp+0B0h+var_D4], 0Bh
0x14001177b  mov     [rbp+0B0h+var_D0], 0FFh
0x140011782  xor     esi, esi
0x140011784  mov     [rbp+0B0h+var_50], 1000000h
0x14001178b  xorps   xmm0, xmm0
0x14001178e  xor     eax, eax
0x140011790  movups  xmmword ptr [rbp+0B0h+var_C8], xmm0
0x140011794  movups  [rbp+0B0h+var_B8], xmm0
0x140011798  movups  [rbp+0B0h+var_A8], xmm0
0x14001179c  movups  [rbp+0B0h+var_98], xmm0
0x1400117a0  movups  [rbp+0B0h+var_88], xmm0
0x1400117a4  movups  [rbp+0B0h+var_78], xmm0
0x1400117a8  movups  [rbp+0B0h+var_68], xmm0
0x1400117ac  mov     [rbp+0B0h+var_58], rax
0x1400117b0  mov     [rsp+1B0h+var_158], esi
0x1400117b4  mov     [rsp+1B0h+var_138], r13
0x1400117b9  mov     [rsp+1B0h+var_150], r12
0x1400117be  mov     [rsp+1B0h+var_148], rcx
0x1400117c3  mov     [rsp+1B0h+var_140], 0DCh
0x1400117cb  mov     [rsp+1B0h+var_13C], 0Bh
0x1400117d3  call    cs:__imp_GetTickCount
0x1400117d9  mov     [rbp+0B0h+var_12C], eax
0x1400117dc  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x1400117e4  mov     [rbp+0B0h+var_128], 0FFh
0x1400117eb  mov     [rsp+1B0h+var_160], esi
0x1400117ef  mov     [rbp+0B0h+var_100], rsi
0x1400117f3  xorps   xmm0, xmm0
0x1400117f6  movdqa  xmmword ptr [rbp+0B0h+pv], xmm0
0x1400117fb  xorps   xmm1, xmm1
0x1400117fe  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x140011803  mov     [rbp+0B0h+arg_0], rsi
0x14001180a  lea     rcx, [rbp+0B0h+arg_0]
0x140011811  call    cs:__imp_VssGetTracingContextPerThread
0x140011817  test    eax, eax
0x140011819  jns     loc_1400119AD
0x14001181f  mov     rax, [rbp+0B0h+var_100]
0x140011823  test    rax, rax
0x140011826  jz      loc_1400119D0
0x14001182c  mov     eax, [rax+30h]
0x14001182f  inc     eax
0x140011831  mov     [rbp+0B0h+var_130], eax
0x140011834  mov     r14d, 0A0h
0x14001183a  mov     ebx, r14d
0x14001183d  cmp     [rbp+0B0h+var_128], 0FFh
0x140011844  cmovnz  ebx, [rbp+0B0h+var_128]
0x140011848  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x14001184c  lea     rcx, [rsp+1B0h+var_160]; this
0x140011851  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140011856  test    eax, eax
0x140011858  jnz     loc_1400119D8
0x14001185e  mov     rbx, rsi
0x140011861  mov     rcx, [rbp+rbx*8+0B0h+var_C8]; pv
0x140011866  test    rcx, rcx
0x140011869  jnz     loc_14001199D
0x14001186f  inc     rbx
0x140011872  cmp     rbx, 0Fh
0x140011876  jnz     short loc_140011861
0x140011878  cmp     byte ptr [rdi+28h], 0
0x14001187c  jz      loc_140011A1D
0x140011882  lock dec dword ptr [rdi+2Ch]
0x140011886  mov     rcx, rdi; lpCriticalSection
0x140011889  call    cs:__imp_LeaveCriticalSection
0x14001188f  nop
0x140011890  mov     rcx, [rbp+0B0h+pv]; pv
0x140011894  call    cs:__imp_CoTaskMemFree
0x14001189a  mov     [rbp+0B0h+pv], rsi
0x14001189e  mov     rcx, [rbp+0B0h+pv+8]; pv
0x1400118a2  call    cs:__imp_CoTaskMemFree
0x1400118a8  mov     [rbp+0B0h+pv+8], rsi
0x1400118ac  mov     rcx, [rbp+0B0h+var_110]; pv
0x1400118b0  call    cs:__imp_CoTaskMemFree
0x1400118b6  mov     [rbp+0B0h+var_110], rsi
0x1400118ba  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x1400118be  call    cs:__imp_CoTaskMemFree
0x1400118c4  mov     [rbp+0B0h+var_110+8], rsi
0x1400118c8  call    cs:__imp_GetTickCount
0x1400118ce  mov     esi, eax
0x1400118d0  sub     esi, [rbp+0B0h+var_12C]
0x1400118d3  mov     eax, 10624DD3h
0x1400118d8  mul     esi
0x1400118da  mov     edi, edx
0x1400118dc  shr     edi, 6
0x1400118df  mov     eax, 88888889h
0x1400118e4  mul     edi
0x1400118e6  shr     edx, 5
0x1400118e9  imul    ecx, edx, 3Ch ; '<'
0x1400118ec  mov     ebx, edi
0x1400118ee  sub     ebx, ecx
0x1400118f0  mov     eax, 45E7B273h
0x1400118f5  mul     esi
0x1400118f7  mov     r11d, edx
0x1400118fa  shr     r11d, 0Eh
0x1400118fe  mov     eax, 88888889h
0x140011903  mul     r11d
0x140011906  shr     edx, 5
0x140011909  imul    ecx, edx, 3Ch ; '<'
0x14001190c  sub     r11d, ecx
0x14001190f  mov     eax, 95217CB1h
0x140011914  mul     esi
0x140011916  mov     r10d, edx
0x140011919  shr     r10d, 15h
0x14001191d  mov     eax, 88888889h
0x140011922  mul     r10d
0x140011925  shr     edx, 5
0x140011928  imul    eax, edx, 3Ch ; '<'
0x14001192b  sub     r10d, eax
0x14001192e  mov     r9d, [rsp+1B0h+var_158]
0x140011933  cmp     [rbp+0B0h+var_128], 0FFh
0x14001193a  cmovnz  r14d, [rbp+0B0h+var_128]
0x14001193f  imul    eax, edi, 3E8h
0x140011945  mov     ecx, esi
0x140011947  sub     ecx, eax
0x140011949  mov     [rsp+1B0h+var_168], r9d
0x14001194e  mov     dword ptr [rsp+1B0h+var_170], esi
0x140011952  mov     dword ptr [rsp+1B0h+var_178], ecx
0x140011956  mov     dword ptr [rsp+1B0h+var_180], ebx
0x14001195a  mov     dword ptr [rsp+1B0h+var_188], r11d
0x14001195f  mov     dword ptr [rsp+1B0h+var_190], r10d
0x140011964  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14001196b  mov     r8d, r14d; unsigned int
0x14001196e  lea     rdx, aExit; "EXIT"
0x140011975  lea     rcx, [rsp+1B0h+var_160]; this
0x14001197a  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14001197f  mov     rcx, [rbp+0B0h+var_100]
0x140011983  call    cs:__imp_VssSetTracingContextPerThread
0x140011989  add     rsp, 178h
0x140011990  pop     r15
0x140011992  pop     r14
0x140011994  pop     r13
0x140011996  pop     r12
0x140011998  pop     rdi
0x140011999  pop     rsi
0x14001199a  pop     rbx
0x14001199b  pop     rbp
0x14001199c  retn
0x14001199d  call    cs:__imp_CoTaskMemFree
0x1400119a3  mov     [rbp+rbx*8+0B0h+var_C8], rsi
0x1400119a8  jmp     loc_14001186F
0x1400119ad  lea     rcx, [rsp+1B0h+var_160]
0x1400119b2  call    cs:__imp_VssSetTracingContextPerThread
0x1400119b8  test    eax, eax
0x1400119ba  js      loc_14001181F
0x1400119c0  mov     rax, [rbp+0B0h+arg_0]
0x1400119c7  mov     [rbp+0B0h+var_100], rax
0x1400119cb  jmp     loc_140011823
0x1400119d0  mov     [rbp+0B0h+var_130], esi
0x1400119d3  jmp     loc_140011834
0x1400119d8  mov     [rsp+1B0h+var_170], rsi
0x1400119dd  mov     dword ptr [rsp+1B0h+var_178], ebx
0x1400119e1  lea     rax, aEnter; "ENTER"
0x1400119e8  mov     [rsp+1B0h+var_180], rax
0x1400119ed  mov     rax, [rsp+1B0h+var_138]
0x1400119f2  mov     [rsp+1B0h+var_188], rax
0x1400119f7  mov     eax, [rsp+1B0h+var_13C]
0x1400119fb  mov     dword ptr [rsp+1B0h+var_190], eax
0x1400119ff  mov     r9d, [rbp+0B0h+var_130]
0x140011a03  mov     r8d, [rsp+1B0h+var_140]
0x140011a08  mov     rdx, [rsp+1B0h+var_148]
0x140011a0d  mov     rcx, [rsp+1B0h+var_150]
0x140011a12  call    cs:__imp_VssTraceMessage
0x140011a18  jmp     loc_14001185E
0x140011a1d  mov     [rbp+0B0h+var_F0], r12
0x140011a21  mov     [rbp+0B0h+var_E8], r13
0x140011a25  lea     rax, aInctypeh; "INCTYPEH"
0x140011a2c  mov     [rbp+0B0h+var_E0], rax
0x140011a30  mov     [rbp+0B0h+var_D8], 0E0h
0x140011a37  mov     [rbp+0B0h+var_D4], 0Bh
0x140011a3e  mov     [rbp+0B0h+var_D0], 0FFh
0x140011a45  mov     [rbp+0B0h+var_50], 1000000h
0x140011a4c  xor     edx, edx; Val
0x140011a4e  mov     r8d, 78h ; 'x'; Size
0x140011a54  lea     rcx, [rbp+0B0h+var_C8]; void *
0x140011a58  call    memset_0
0x140011a5d  movzx   edx, byte ptr [rdi+29h]
0x140011a61  lea     rax, aNonInitialized; "Non-initialized CS"
0x140011a68  mov     [rsp+1B0h+var_190], rax
0x140011a6d  mov     r9d, 8007000Eh
0x140011a73  lea     r8, [rbp+0B0h+var_F0]
0x140011a77  lea     rcx, [rsp+1B0h+var_160]
0x140011a7c  call    ?ThrowIf@CVssFunctionTracer@@QEAAXHUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::ThrowIf(int,CVssDebugInfo,long,ushort * const,...)
0x140011a81  jmp     loc_140011882
```
