# CVssAutomaticLock2::~CVssAutomaticLock2(void)

- ea: `0x140011440`
- end: `0x14001171f`
- name: `??1CVssAutomaticLock2@@QEAA@XZ`
- size: `735`
- prototype: `void __fastcall(LPCRITICAL_SECTION *this)`
- caller_count: `58`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001d90`
- `0x140002270`
- `0x1400037bc`
- `0x140003b70`
- `0x140004690`
- `0x140005050`
- `0x140005c38`
- `0x140016db0`
- `0x14001cafc`
- `0x1400376e0`
- `0x140037df4`
- `0x14003a930`
- `0x14003aa10`
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
- `0x1400da540`
- `0x1400daa82`
- `0x1400daec2`
- `0x1400db087`
- `0x1400db235`
- `0x1400dc8c0`
- `0x1400dc960`
- `0x1400dd4ad`
- `0x1400df9bc`
- `0x1400dfb5d`
- `0x1400e1f9f`
- `0x1400e3190`
- `0x1400e414b`
- `0x1400e416f`

## callees

- `0x140011440`
- `0x140011730`
- `0x1400138e0`
- `0x140013c60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400114df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400115cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400114df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400115cd`
- `VssTrace!__imp_VssTraceMessage` at `0x140011714`
- `VssTrace!__imp_VssTraceMessage` at `0x140011714`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011688`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400116b4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140011688`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400116b4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001151d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001151d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001169f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001169f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssAutomaticLock2::~CVssAutomaticLock2(LPCRITICAL_SECTION *this)
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
  const unsigned __int16 *v26; // [rsp+C0h] [rbp-40h]
  const wchar_t *v27; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D8h] [rbp-28h]
  int v30; // [rsp+DCh] [rbp-24h]
  int v31; // [rsp+E0h] [rbp-20h]
  LPVOID v32[2]; // [rsp+E8h] [rbp-18h]
  __int128 v33; // [rsp+F8h] [rbp-8h]
  __int128 v34; // [rsp+108h] [rbp+8h]
  __int128 v35; // [rsp+118h] [rbp+18h]
  __int128 v36; // [rsp+128h] [rbp+28h]
  __int128 v37; // [rsp+138h] [rbp+38h]
  __int128 v38; // [rsp+148h] [rbp+48h]
  __int64 v39; // [rsp+158h] [rbp+58h]
  int v40; // [rsp+160h] [rbp+60h]
  __int64 v41; // [rsp+1B0h] [rbp+B0h] BYREF

  v26 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v27 = L"CVssAutomaticLock2::~CVssAutomaticLock2";
  v28 = L"INCTYPEH";
  v29 = 264;
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
  v19 = L"CVssAutomaticLock2::~CVssAutomaticLock2";
  v15 = L"base\\stor\\vss\\inc\\vs_types.hxx";
  v16 = L"INCTYPEH";
  v17 = 264;
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
  if ( *((_BYTE *)this + 8) )
    CVssCriticalSection::Unlock(*this);
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
0x140011440  push    rbp
0x140011442  push    rbx
0x140011443  push    rsi
0x140011444  push    rdi
0x140011445  push    r14
0x140011447  push    r15
0x140011449  lea     rbp, [rsp-78h]
0x14001144e  sub     rsp, 178h
0x140011455  mov     rdi, rcx
0x140011458  lea     r8, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x14001145f  mov     [rbp+0A0h+var_E0], r8
0x140011463  lea     rcx, aCvssautomaticl; "CVssAutomaticLock2::~CVssAutomaticLock2"
0x14001146a  mov     [rbp+0A0h+var_D8], rcx
0x14001146e  lea     rdx, aInctypeh; "INCTYPEH"
0x140011475  mov     [rbp+0A0h+var_D0], rdx
0x140011479  mov     [rbp+0A0h+var_C8], 108h
0x140011480  mov     [rbp+0A0h+var_C4], 0Bh
0x140011487  mov     [rbp+0A0h+var_C0], 0FFh
0x14001148e  xor     esi, esi
0x140011490  mov     [rbp+0A0h+var_40], 1000000h
0x140011497  xorps   xmm0, xmm0
0x14001149a  xor     eax, eax
0x14001149c  movups  xmmword ptr [rbp+0A0h+var_B8], xmm0
0x1400114a0  movups  [rbp+0A0h+var_A8], xmm0
0x1400114a4  movups  [rbp+0A0h+var_98], xmm0
0x1400114a8  movups  [rbp+0A0h+var_88], xmm0
0x1400114ac  movups  [rbp+0A0h+var_78], xmm0
0x1400114b0  movups  [rbp+0A0h+var_68], xmm0
0x1400114b4  movups  [rbp+0A0h+var_58], xmm0
0x1400114b8  mov     [rbp+0A0h+var_48], rax
0x1400114bc  mov     [rsp+1A0h+var_148], esi
0x1400114c0  mov     [rsp+1A0h+var_128], rcx
0x1400114c5  mov     [rsp+1A0h+var_140], r8
0x1400114ca  mov     [rsp+1A0h+var_138], rdx
0x1400114cf  mov     [rsp+1A0h+var_130], 108h
0x1400114d7  mov     [rsp+1A0h+var_12C], 0Bh
0x1400114df  call    cs:__imp_GetTickCount
0x1400114e5  mov     [rbp+0A0h+var_11C], eax
0x1400114e8  mov     [rsp+1A0h+var_14C], 0FFFFFFFFh
0x1400114f0  mov     [rbp+0A0h+var_118], 0FFh
0x1400114f7  mov     [rsp+1A0h+var_150], esi
0x1400114fb  mov     [rbp+0A0h+var_F0], rsi
0x1400114ff  xorps   xmm0, xmm0
0x140011502  movdqa  xmmword ptr [rbp+0A0h+pv], xmm0
0x140011507  xorps   xmm1, xmm1
0x14001150a  movdqa  xmmword ptr [rbp+0A0h+var_100], xmm1
0x14001150f  mov     [rbp+0A0h+arg_0], rsi
0x140011516  lea     rcx, [rbp+0A0h+arg_0]
0x14001151d  call    cs:__imp_VssGetTracingContextPerThread
0x140011523  test    eax, eax
0x140011525  jns     loc_1400116AF
0x14001152b  mov     rax, [rbp+0A0h+var_F0]
0x14001152f  test    rax, rax
0x140011532  jz      loc_1400116D2
0x140011538  mov     eax, [rax+30h]
0x14001153b  inc     eax
0x14001153d  mov     [rbp+0A0h+var_120], eax
0x140011540  mov     r14d, 0A0h
0x140011546  mov     ebx, r14d
0x140011549  cmp     [rbp+0A0h+var_118], 0FFh
0x140011550  cmovnz  ebx, [rbp+0A0h+var_118]
0x140011554  mov     edx, [rsp+1A0h+var_12C]; unsigned int
0x140011558  lea     rcx, [rsp+1A0h+var_150]; this
0x14001155d  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140011562  test    eax, eax
0x140011564  jnz     loc_1400116DA
0x14001156a  mov     rbx, rsi
0x14001156d  nop     dword ptr [rax]
0x140011570  mov     rcx, [rbp+rbx*8+0A0h+var_B8]; pv
0x140011575  test    rcx, rcx
0x140011578  jnz     loc_14001169F
0x14001157e  inc     rbx
0x140011581  cmp     rbx, 0Fh
0x140011585  jnz     short loc_140011570
0x140011587  cmp     [rdi+8], sil
0x14001158b  jz      short loc_140011595
0x14001158d  mov     rcx, [rdi]; lpCriticalSection
0x140011590  call    ?Unlock@CVssCriticalSection@@QEAAXXZ; CVssCriticalSection::Unlock(void)
0x140011595  mov     rcx, [rbp+0A0h+pv]; pv
0x140011599  call    cs:__imp_CoTaskMemFree
0x14001159f  mov     [rbp+0A0h+pv], rsi
0x1400115a3  mov     rcx, [rbp+0A0h+pv+8]; pv
0x1400115a7  call    cs:__imp_CoTaskMemFree
0x1400115ad  mov     [rbp+0A0h+pv+8], rsi
0x1400115b1  mov     rcx, [rbp+0A0h+var_100]; pv
0x1400115b5  call    cs:__imp_CoTaskMemFree
0x1400115bb  mov     [rbp+0A0h+var_100], rsi
0x1400115bf  mov     rcx, [rbp+0A0h+var_100+8]; pv
0x1400115c3  call    cs:__imp_CoTaskMemFree
0x1400115c9  mov     [rbp+0A0h+var_100+8], rsi
0x1400115cd  call    cs:__imp_GetTickCount
0x1400115d3  mov     esi, eax
0x1400115d5  sub     esi, [rbp+0A0h+var_11C]
0x1400115d8  mov     eax, 10624DD3h
0x1400115dd  mul     esi
0x1400115df  mov     edi, edx
0x1400115e1  shr     edi, 6
0x1400115e4  mov     eax, 88888889h
0x1400115e9  mul     edi
0x1400115eb  shr     edx, 5
0x1400115ee  imul    ecx, edx, 3Ch ; '<'
0x1400115f1  mov     ebx, edi
0x1400115f3  sub     ebx, ecx
0x1400115f5  mov     eax, 45E7B273h
0x1400115fa  mul     esi
0x1400115fc  mov     r11d, edx
0x1400115ff  shr     r11d, 0Eh
0x140011603  mov     eax, 88888889h
0x140011608  mul     r11d
0x14001160b  shr     edx, 5
0x14001160e  imul    ecx, edx, 3Ch ; '<'
0x140011611  sub     r11d, ecx
0x140011614  mov     eax, 95217CB1h
0x140011619  mul     esi
0x14001161b  mov     r10d, edx
0x14001161e  shr     r10d, 15h
0x140011622  mov     eax, 88888889h
0x140011627  mul     r10d
0x14001162a  shr     edx, 5
0x14001162d  imul    eax, edx, 3Ch ; '<'
0x140011630  sub     r10d, eax
0x140011633  mov     r9d, [rsp+1A0h+var_148]
0x140011638  cmp     [rbp+0A0h+var_118], 0FFh
0x14001163f  cmovnz  r14d, [rbp+0A0h+var_118]
0x140011644  imul    eax, edi, 3E8h
0x14001164a  mov     ecx, esi
0x14001164c  sub     ecx, eax
0x14001164e  mov     [rsp+1A0h+var_158], r9d
0x140011653  mov     dword ptr [rsp+1A0h+var_160], esi
0x140011657  mov     dword ptr [rsp+1A0h+var_168], ecx
0x14001165b  mov     dword ptr [rsp+1A0h+var_170], ebx
0x14001165f  mov     dword ptr [rsp+1A0h+var_178], r11d
0x140011664  mov     dword ptr [rsp+1A0h+var_180], r10d
0x140011669  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140011670  mov     r8d, r14d; unsigned int
0x140011673  lea     rdx, aExit; "EXIT"
0x14001167a  lea     rcx, [rsp+1A0h+var_150]; this
0x14001167f  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140011684  mov     rcx, [rbp+0A0h+var_F0]
0x140011688  call    cs:__imp_VssSetTracingContextPerThread
0x14001168e  nop
0x14001168f  add     rsp, 178h
0x140011696  pop     r15
0x140011698  pop     r14
0x14001169a  pop     rdi
0x14001169b  pop     rsi
0x14001169c  pop     rbx
0x14001169d  pop     rbp
0x14001169e  retn
0x14001169f  call    cs:__imp_CoTaskMemFree
0x1400116a5  mov     [rbp+rbx*8+0A0h+var_B8], rsi
0x1400116aa  jmp     loc_14001157E
0x1400116af  lea     rcx, [rsp+1A0h+var_150]
0x1400116b4  call    cs:__imp_VssSetTracingContextPerThread
0x1400116ba  test    eax, eax
0x1400116bc  js      loc_14001152B
0x1400116c2  mov     rax, [rbp+0A0h+arg_0]
0x1400116c9  mov     [rbp+0A0h+var_F0], rax
0x1400116cd  jmp     loc_14001152F
0x1400116d2  mov     [rbp+0A0h+var_120], esi
0x1400116d5  jmp     loc_140011540
0x1400116da  mov     [rsp+1A0h+var_160], rsi
0x1400116df  mov     dword ptr [rsp+1A0h+var_168], ebx
0x1400116e3  lea     rax, aEnter; "ENTER"
0x1400116ea  mov     [rsp+1A0h+var_170], rax
0x1400116ef  mov     rax, [rsp+1A0h+var_128]
0x1400116f4  mov     [rsp+1A0h+var_178], rax
0x1400116f9  mov     eax, [rsp+1A0h+var_12C]
0x1400116fd  mov     dword ptr [rsp+1A0h+var_180], eax
0x140011701  mov     r9d, [rbp+0A0h+var_120]
0x140011705  mov     r8d, [rsp+1A0h+var_130]
0x14001170a  mov     rdx, [rsp+1A0h+var_138]
0x14001170f  mov     rcx, [rsp+1A0h+var_140]
0x140011714  call    cs:__imp_VssTraceMessage
0x14001171a  jmp     loc_14001156A
```
