# CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)

- ea: `0x140016710`
- end: `0x140016a00`
- name: `??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z`
- size: `752`
- prototype: `CVssAutomaticLock2 *__fastcall(CVssAutomaticLock2 *__hidden this, struct CVssCriticalSection *)`
- caller_count: `29`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001d90`
- `0x1400037bc`
- `0x140004690`
- `0x14001cafc`
- `0x140037df4`
- `0x14003a930`
- `0x140040944`
- `0x1400433b8`
- `0x140043b1c`
- `0x140046958`
- `0x1400475f0`
- `0x140047f80`
- `0x14004f04c`
- `0x14004f628`
- `0x14004f700`
- `0x140055e00`
- `0x140056164`
- `0x140082290`
- `0x1400844c0`
- `0x140085360`
- `0x140099aa0`
- `0x14009a280`
- `0x14009c6b0`
- `0x14009c970`
- `0x14009cfa0`
- `0x14009df00`
- `0x14009e168`
- `0x14009f9c0`
- `0x1400a6cec`

## callees

- `0x1400138e0`
- `0x140013c60`
- `0x140015950`
- `0x140016710`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400167b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400168ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400167b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400168ac`
- `VssTrace!__imp_VssTraceMessage` at `0x1400169f5`
- `VssTrace!__imp_VssTraceMessage` at `0x1400169f5`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016967`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016995`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016967`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140016995`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400167f4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400167f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016894`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400168a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016894`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400168a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140016980`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CVssAutomaticLock2 *__fastcall CVssAutomaticLock2::CVssAutomaticLock2(
        CVssAutomaticLock2 *this,
        struct CVssCriticalSection *a2)
{
  __int64 v3; // rax
  unsigned int v4; // r15d
  unsigned int v5; // ebx
  __int64 i; // rbx
  void *v7; // rcx
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

  *(_QWORD *)this = a2;
  *((_BYTE *)this + 8) = 0;
  v28 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v29 = L"CVssAutomaticLock2::CVssAutomaticLock2";
  v30 = L"INCTYPEH";
  v31 = 256;
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
  v21 = L"CVssAutomaticLock2::CVssAutomaticLock2";
  v17 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v18 = L"INCTYPEH";
  v19 = 256;
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
    v3 = v27;
  }
  else
  {
    v3 = v43;
    v27 = v43;
  }
  if ( v3 )
    v22 = *(_DWORD *)(v3 + 48) + 1;
  else
    v22 = 0;
  v4 = 160;
  v5 = 160;
  if ( v24 != 255 )
    v5 = v24;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v15, v20) )
    VssTraceMessage(v17, v18, v19, v22, v20, v21, L"ENTER", v5, 0);
  for ( i = 0; i != 15; ++i )
  {
    v7 = v34[i];
    if ( v7 )
    {
      CoTaskMemFree(v7);
      v34[i] = 0;
    }
  }
  CVssCriticalSection::Lock(*(LPCRITICAL_SECTION *)this);
  *((_BYTE *)this + 8) = 1;
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
    v4 = v24;
  LODWORD(v14) = v8;
  LODWORD(v13) = v8 % 0x3E8;
  LODWORD(v12) = v8 / 0x3E8 % 0x3C;
  LODWORD(v11) = v8 / 0xEA60 % 0x3C;
  LODWORD(v10) = v8 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v15,
    L"EXIT",
    v4,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v10,
    v11,
    v12,
    v13,
    v14,
    v16);
  VssSetTracingContextPerThread(v27);
  return this;
}

```

## disassembly

```asm
0x140016710  push    rbp
0x140016712  push    rbx
0x140016713  push    rsi
0x140016714  push    rdi
0x140016715  push    r14
0x140016717  push    r15
0x140016719  lea     rbp, [rsp-78h]
0x14001671e  sub     rsp, 178h
0x140016725  mov     r14, rcx
0x140016728  mov     [rcx], rdx
0x14001672b  mov     byte ptr [rcx+8], 0
0x14001672f  lea     r8, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140016736  mov     [rbp+0A0h+var_E0], r8
0x14001673a  lea     rcx, aCvssautomaticl_0; "CVssAutomaticLock2::CVssAutomaticLock2"
0x140016741  mov     [rbp+0A0h+var_D8], rcx
0x140016745  lea     rdx, aInctypeh; "INCTYPEH"
0x14001674c  mov     [rbp+0A0h+var_D0], rdx
0x140016750  mov     [rbp+0A0h+var_C8], 100h
0x140016757  mov     [rbp+0A0h+var_C4], 0Bh
0x14001675e  mov     [rbp+0A0h+var_C0], 0FFh
0x140016765  xor     edi, edi
0x140016767  mov     [rbp+0A0h+var_40], 1000000h
0x14001676e  xorps   xmm0, xmm0
0x140016771  xor     eax, eax
0x140016773  movups  xmmword ptr [rbp+0A0h+var_B8], xmm0
0x140016777  movups  [rbp+0A0h+var_A8], xmm0
0x14001677b  movups  [rbp+0A0h+var_98], xmm0
0x14001677f  movups  [rbp+0A0h+var_88], xmm0
0x140016783  movups  [rbp+0A0h+var_78], xmm0
0x140016787  movups  [rbp+0A0h+var_68], xmm0
0x14001678b  movups  [rbp+0A0h+var_58], xmm0
0x14001678f  mov     [rbp+0A0h+var_48], rax
0x140016793  mov     [rsp+1A0h+var_148], edi
0x140016797  mov     [rsp+1A0h+var_128], rcx
0x14001679c  mov     [rsp+1A0h+var_140], r8
0x1400167a1  mov     [rsp+1A0h+var_138], rdx
0x1400167a6  mov     [rsp+1A0h+var_130], 100h
0x1400167ae  mov     [rsp+1A0h+var_12C], 0Bh
0x1400167b6  call    cs:__imp_GetTickCount
0x1400167bc  mov     [rbp+0A0h+var_11C], eax
0x1400167bf  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x1400167c7  mov     [rbp+0A0h+var_118], 0FFh
0x1400167ce  mov     [rsp+1A0h+var_150], edi
0x1400167d2  mov     [rbp+0A0h+var_F0], rdi
0x1400167d6  xorps   xmm0, xmm0
0x1400167d9  movdqa  xmmword ptr [rbp+0A0h+pv], xmm0
0x1400167de  xorps   xmm1, xmm1
0x1400167e1  movdqa  xmmword ptr [rbp+0A0h+var_100], xmm1
0x1400167e6  mov     [rbp+0A0h+arg_0], rdi
0x1400167ed  lea     rcx, [rbp+0A0h+arg_0]
0x1400167f4  call    cs:__imp_VssGetTracingContextPerThread
0x1400167fa  test    eax, eax
0x1400167fc  jns     loc_140016990
0x140016802  mov     rax, [rbp+0A0h+var_F0]
0x140016806  test    rax, rax
0x140016809  jz      loc_1400169B3
0x14001680f  mov     eax, [rax+30h]
0x140016812  inc     eax
0x140016814  mov     [rbp+0A0h+var_120], eax
0x140016817  mov     r15d, 0A0h
0x14001681d  mov     ebx, r15d
0x140016820  cmp     [rbp+0A0h+var_118], 0FFh
0x140016827  cmovnz  ebx, [rbp+0A0h+var_118]
0x14001682b  mov     edx, [rsp+1A0h+var_12C]; unsigned int
0x14001682f  lea     rcx, [rsp+1A0h+var_150]; this
0x140016834  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140016839  test    eax, eax
0x14001683b  jnz     loc_1400169BB
0x140016841  mov     rbx, rdi
0x140016844  nop     dword ptr [rax+00h]
0x140016848  nop     dword ptr [rax+rax+00000000h]
0x140016850  mov     rcx, [rbp+rbx*8+0A0h+var_B8]; pv
0x140016855  test    rcx, rcx
0x140016858  jnz     loc_140016980
0x14001685e  inc     rbx
0x140016861  cmp     rbx, 0Fh
0x140016865  jnz     short loc_140016850
0x140016867  mov     rcx, [r14]; lpCriticalSection
0x14001686a  call    ?Lock@CVssCriticalSection@@QEAAXXZ; CVssCriticalSection::Lock(void)
0x14001686f  mov     byte ptr [r14+8], 1
0x140016874  mov     rcx, [rbp+0A0h+pv]; pv
0x140016878  call    cs:__imp_CoTaskMemFree
0x14001687e  mov     [rbp+0A0h+pv], rdi
0x140016882  mov     rcx, [rbp+0A0h+pv+8]; pv
0x140016886  call    cs:__imp_CoTaskMemFree
0x14001688c  mov     [rbp+0A0h+pv+8], rdi
0x140016890  mov     rcx, [rbp+0A0h+var_100]; pv
0x140016894  call    cs:__imp_CoTaskMemFree
0x14001689a  mov     [rbp+0A0h+var_100], rdi
0x14001689e  mov     rcx, [rbp+0A0h+var_100+8]; pv
0x1400168a2  call    cs:__imp_CoTaskMemFree
0x1400168a8  mov     [rbp+0A0h+var_100+8], rdi
0x1400168ac  call    cs:__imp_GetTickCount
0x1400168b2  mov     esi, eax
0x1400168b4  sub     esi, [rbp+0A0h+var_11C]
0x1400168b7  mov     eax, 10624DD3h
0x1400168bc  mul     esi
0x1400168be  mov     edi, edx
0x1400168c0  shr     edi, 6
0x1400168c3  mov     eax, 88888889h
0x1400168c8  mul     edi
0x1400168ca  shr     edx, 5
0x1400168cd  imul    ecx, edx, 3Ch ; '<'
0x1400168d0  mov     ebx, edi
0x1400168d2  sub     ebx, ecx
0x1400168d4  mov     eax, 45E7B273h
0x1400168d9  mul     esi
0x1400168db  mov     r11d, edx
0x1400168de  shr     r11d, 0Eh
0x1400168e2  mov     eax, 88888889h
0x1400168e7  mul     r11d
0x1400168ea  shr     edx, 5
0x1400168ed  imul    ecx, edx, 3Ch ; '<'
0x1400168f0  sub     r11d, ecx
0x1400168f3  mov     eax, 95217CB1h
0x1400168f8  mul     esi
0x1400168fa  mov     r10d, edx
0x1400168fd  shr     r10d, 15h
0x140016901  mov     eax, 88888889h
0x140016906  mul     r10d
0x140016909  shr     edx, 5
0x14001690c  imul    eax, edx, 3Ch ; '<'
0x14001690f  sub     r10d, eax
0x140016912  mov     r9d, [rsp+1A0h+var_148]
0x140016917  cmp     [rbp+0A0h+var_118], 0FFh
0x14001691e  cmovnz  r15d, [rbp+0A0h+var_118]
0x140016923  imul    eax, edi, 3E8h
0x140016929  mov     ecx, esi
0x14001692b  sub     ecx, eax
0x14001692d  mov     [rsp+1A0h+var_158], r9d
0x140016932  mov     dword ptr [rsp+1A0h+var_160], esi
0x140016936  mov     dword ptr [rsp+1A0h+var_168], ecx
0x14001693a  mov     dword ptr [rsp+1A0h+var_170], ebx
0x14001693e  mov     dword ptr [rsp+1A0h+var_178], r11d
0x140016943  mov     dword ptr [rsp+1A0h+var_180], r10d
0x140016948  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14001694f  mov     r8d, r15d; unsigned int
0x140016952  lea     rdx, aExit; "EXIT"
0x140016959  lea     rcx, [rsp+1A0h+var_150]; this
0x14001695e  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140016963  mov     rcx, [rbp+0A0h+var_F0]
0x140016967  call    cs:__imp_VssSetTracingContextPerThread
0x14001696d  mov     rax, r14
0x140016970  add     rsp, 178h
0x140016977  pop     r15
0x140016979  pop     r14
0x14001697b  pop     rdi
0x14001697c  pop     rsi
0x14001697d  pop     rbx
0x14001697e  pop     rbp
0x14001697f  retn
0x140016980  call    cs:__imp_CoTaskMemFree
0x140016986  mov     [rbp+rbx*8+0A0h+var_B8], rdi
0x14001698b  jmp     loc_14001685E
0x140016990  lea     rcx, [rsp+1A0h+var_150]
0x140016995  call    cs:__imp_VssSetTracingContextPerThread
0x14001699b  test    eax, eax
0x14001699d  js      loc_140016802
0x1400169a3  mov     rax, [rbp+0A0h+arg_0]
0x1400169aa  mov     [rbp+0A0h+var_F0], rax
0x1400169ae  jmp     loc_140016806
0x1400169b3  mov     [rbp+0A0h+var_120], edi
0x1400169b6  jmp     loc_140016817
0x1400169bb  mov     [rsp+1A0h+var_160], rdi
0x1400169c0  mov     dword ptr [rsp+1A0h+var_168], ebx
0x1400169c4  lea     rax, aEnter; "ENTER"
0x1400169cb  mov     [rsp+1A0h+var_170], rax
0x1400169d0  mov     rax, [rsp+1A0h+var_128]
0x1400169d5  mov     [rsp+1A0h+var_178], rax
0x1400169da  mov     eax, [rsp+1A0h+var_12C]
0x1400169de  mov     dword ptr [rsp+1A0h+var_180], eax
0x1400169e2  mov     r9d, [rbp+0A0h+var_120]
0x1400169e6  mov     r8d, [rsp+1A0h+var_130]
0x1400169eb  mov     rdx, [rsp+1A0h+var_138]
0x1400169f0  mov     rcx, [rsp+1A0h+var_140]
0x1400169f5  call    cs:__imp_VssTraceMessage
0x1400169fb  jmp     loc_140016841
```
