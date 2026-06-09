# CVssDiag::RecordWriterEvent(VSS_OPERATION,ulong,ulong,long,_GUID)

- ea: `0x140006078`
- end: `0x14000625b`
- name: `?RecordWriterEvent@CVssDiag@@QEAAXW4VSS_OPERATION@@KKJU_GUID@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140042688`
- `0x1400437e0`
- `0x140044d60`
- `0x14004500c`
- `0x140079cf8`
- `0x1400a3fc0`
- `0x1400a57d4`
- `0x1400a60fc`
- `0x1400a6f44`

## callees

- `0x140006020`
- `0x140006078`
- `0x140006270`
- `0x1400137c0`
- `0x140013cb0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000610d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000610d`
- `VssTrace!__imp_VssTraceMessage` at `0x140006250`
- `VssTrace!__imp_VssTraceMessage` at `0x140006250`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400061ee`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400061ee`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000614d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000614d`

## string_xrefs

- `0x14000609e`: `CVssDiag::RecordWriterEvent`
- `0x140006093`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssDiag::RecordWriterEvent(
        CVssDiag *a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        struct _GUID *a6)
{
  __int64 v9; // rcx
  int v10; // ebx
  int v11; // eax
  struct _GUID v12; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v15; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v16; // [rsp+78h] [rbp-88h]
  unsigned int v17; // [rsp+80h] [rbp-80h]
  int v18; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v19; // [rsp+88h] [rbp-78h]
  unsigned int v20; // [rsp+90h] [rbp-70h]
  DWORD TickCount; // [rsp+94h] [rbp-6Ch]
  int v22; // [rsp+98h] [rbp-68h]
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int128 v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  _QWORD v26[3]; // [rsp+D0h] [rbp-30h] BYREF
  int v27; // [rsp+E8h] [rbp-18h]
  int v28; // [rsp+ECh] [rbp-14h]
  int v29; // [rsp+F0h] [rbp-10h]
  _BYTE v30[120]; // [rsp+F8h] [rbp-8h] BYREF
  int v31; // [rsp+170h] [rbp+70h]

  v26[0] = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v26[1] = L"CVssDiag::RecordWriterEvent";
  v26[2] = L"REGREGSC";
  v27 = 1305;
  v28 = 11;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  v14 = 0;
  v19 = L"CVssDiag::RecordWriterEvent";
  v15 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v16 = L"REGREGSC";
  v17 = 1305;
  v18 = 11;
  TickCount = GetTickCount();
  v22 = 255;
  v13 = 0xFFFFFFFF00000000uLL;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  *(_QWORD *)&v12.Data1 = 0;
  if ( (int)VssGetTracingContextPerThread(&v12) >= 0 )
  {
    v11 = VssSetTracingContextPerThread(&v13);
    v9 = v25;
    if ( v11 >= 0 )
      v9 = *(_QWORD *)&v12.Data1;
    v25 = v9;
  }
  else
  {
    v9 = v25;
  }
  if ( v9 )
    v20 = *(_DWORD *)(v9 + 48) + 1;
  else
    v20 = 0;
  v10 = 160;
  if ( v22 != 255 )
    v10 = v22;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v13) )
    VssTraceMessage(v15, v16, v17, v20, v18, v19, L"ENTER", v10, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v26);
  v12 = *a6;
  CVssDiag::RecordGenericEvent(a1, a2, a3, 0, a5, &v12);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v13);
}

```

## disassembly

```asm
0x140006078  push    rbp
0x14000607a  push    rbx
0x14000607b  push    rsi
0x14000607c  push    rdi
0x14000607d  push    r14
0x14000607f  lea     rbp, [rsp-80h]
0x140006084  sub     rsp, 180h
0x14000608b  mov     edi, r8d
0x14000608e  mov     esi, edx
0x140006090  mov     r14, rcx
0x140006093  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000609a  mov     [rbp+0A0h+var_D0], rax
0x14000609e  lea     rax, aCvssdiagRecord_0; "CVssDiag::RecordWriterEvent"
0x1400060a5  mov     [rbp+0A0h+var_C8], rax
0x1400060a9  lea     rax, aRegregsc; "REGREGSC"
0x1400060b0  mov     [rbp+0A0h+var_C0], rax
0x1400060b4  mov     [rbp+0A0h+var_B8], 519h
0x1400060bb  mov     [rbp+0A0h+var_B4], 0Bh
0x1400060c2  mov     [rbp+0A0h+var_B0], 0FFh
0x1400060c9  mov     [rbp+0A0h+var_30], 1000000h
0x1400060d0  xor     edx, edx; Val
0x1400060d2  lea     r8d, [rdx+78h]; Size
0x1400060d6  lea     rcx, [rbp+0A0h+var_A8]; void *
0x1400060da  call    memset_0
0x1400060df  mov     [rsp+1A0h+var_138], 0
0x1400060e7  mov     rax, [rbp+0A0h+var_C8]
0x1400060eb  mov     [rbp+0A0h+var_118], rax
0x1400060ef  mov     rax, [rbp+0A0h+var_D0]
0x1400060f3  mov     [rsp+1A0h+var_130], rax
0x1400060f8  mov     rax, [rbp+0A0h+var_C0]
0x1400060fc  mov     [rsp+1A0h+var_128], rax
0x140006101  mov     eax, [rbp+0A0h+var_B8]
0x140006104  mov     [rbp+0A0h+var_120], eax
0x140006107  mov     eax, [rbp+0A0h+var_B4]
0x14000610a  mov     [rbp+0A0h+var_11C], eax
0x14000610d  call    cs:__imp_GetTickCount
0x140006113  mov     [rbp+0A0h+var_10C], eax
0x140006116  mov     [rsp+1A0h+var_13C], 0FFFFFFFFh
0x14000611e  mov     eax, [rbp+0A0h+var_B0]
0x140006121  mov     [rbp+0A0h+var_108], eax
0x140006124  mov     [rsp+1A0h+var_140], 0
0x14000612c  mov     [rbp+0A0h+var_E0], 0
0x140006134  xorps   xmm0, xmm0
0x140006137  movups  [rbp+0A0h+var_100], xmm0
0x14000613b  movups  [rbp+0A0h+var_F0], xmm0
0x14000613f  mov     qword ptr [rsp+1A0h+var_150.Data1], 0
0x140006148  lea     rcx, [rsp+1A0h+var_150]
0x14000614d  call    cs:__imp_VssGetTracingContextPerThread
0x140006153  test    eax, eax
0x140006155  jns     loc_1400061E9
0x14000615b  mov     rcx, [rbp+0A0h+var_E0]
0x14000615f  test    rcx, rcx
0x140006162  jz      loc_140006209
0x140006168  mov     eax, [rcx+30h]
0x14000616b  inc     eax
0x14000616d  mov     [rbp+0A0h+var_110], eax
0x140006170  mov     ebx, 0A0h
0x140006175  cmp     [rbp+0A0h+var_108], 0FFh
0x14000617c  cmovnz  ebx, [rbp+0A0h+var_108]
0x140006180  lea     rcx, [rsp+1A0h+var_140]; this
0x140006185  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14000618a  test    eax, eax
0x14000618c  jnz     loc_140006215
0x140006192  lea     rcx, [rbp+0A0h+var_D0]; this
0x140006196  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14000619b  nop
0x14000619c  mov     rax, [rbp+0A0h+arg_28]
0x1400061a3  movaps  xmm0, xmmword ptr [rax]
0x1400061a6  movdqa  xmmword ptr [rsp+1A0h+var_150.Data1], xmm0
0x1400061ac  lea     rax, [rsp+1A0h+var_150]
0x1400061b1  mov     [rsp+1A0h+var_178], rax; struct _GUID *
0x1400061b6  mov     eax, [rbp+0A0h+arg_20]
0x1400061bc  mov     [rsp+1A0h+var_180], eax; int
0x1400061c0  xor     r9d, r9d; unsigned int
0x1400061c3  mov     r8d, edi; unsigned int
0x1400061c6  mov     edx, esi; unsigned int
0x1400061c8  mov     rcx, r14; this
0x1400061cb  call    ?RecordGenericEvent@CVssDiag@@QEAAXKKKJU_GUID@@@Z; CVssDiag::RecordGenericEvent(ulong,ulong,ulong,long,_GUID)
0x1400061d0  nop
0x1400061d1  lea     rcx, [rsp+1A0h+var_140]; this
0x1400061d6  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400061db  add     rsp, 180h
0x1400061e2  pop     r14
0x1400061e4  pop     rdi
0x1400061e5  pop     rsi
0x1400061e6  pop     rbx
0x1400061e7  pop     rbp
0x1400061e8  retn
0x1400061e9  lea     rcx, [rsp+1A0h+var_140]
0x1400061ee  call    cs:__imp_VssSetTracingContextPerThread
0x1400061f4  mov     rcx, [rbp+0A0h+var_E0]
0x1400061f8  test    eax, eax
0x1400061fa  cmovns  rcx, qword ptr [rsp+1A0h+var_150.Data1]
0x140006200  mov     [rbp+0A0h+var_E0], rcx
0x140006204  jmp     loc_14000615F
0x140006209  mov     [rbp+0A0h+var_110], 0
0x140006210  jmp     loc_140006170
0x140006215  mov     [rsp+1A0h+var_160], 0
0x14000621e  mov     [rsp+1A0h+var_168], ebx
0x140006222  lea     rax, aEnter; "ENTER"
0x140006229  mov     [rsp+1A0h+var_170], rax
0x14000622e  mov     rax, [rbp+0A0h+var_118]
0x140006232  mov     [rsp+1A0h+var_178], rax
0x140006237  mov     eax, [rbp+0A0h+var_11C]
0x14000623a  mov     [rsp+1A0h+var_180], eax
0x14000623e  mov     r9d, [rbp+0A0h+var_110]
0x140006242  mov     r8d, [rbp+0A0h+var_120]
0x140006246  mov     rdx, [rsp+1A0h+var_128]
0x14000624b  mov     rcx, [rsp+1A0h+var_130]
0x140006250  call    cs:__imp_VssTraceMessage
0x140006256  jmp     loc_140006192
```
