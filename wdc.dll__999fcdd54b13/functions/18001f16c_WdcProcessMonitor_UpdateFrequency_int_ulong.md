# WdcProcessMonitor::UpdateFrequency(int,ulong)

- ea: `0x18001f16c`
- end: `0x18001f5a9`
- name: `?UpdateFrequency@WdcProcessMonitor@@AEAAJHK@Z`
- size: `1085`
- prototype: `__int64 __fastcall(WdcProcessMonitor *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c090`
- `0x18007f730`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18000e268`
- `0x18001f16c`
- `0x180023afc`
- `0x18007fb6c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001f56f`
- `ntdll!RtlNtStatusToDosError` at `0x18001f56f`
- `ntdll!NtQuerySystemInformationEx` at `0x18001f525`
- `ntdll!NtQuerySystemInformationEx` at `0x18001f525`

## string_xrefs

- `0x18001f1d0`: `WdcProcessMonitor::UpdateFrequency`
- `0x18001f384`: `WdcProcessMonitor::UpdateFrequency`
- `0x18001f419`: `WdcProcessMonitor::UpdateFrequency`

## pseudocode

```c
__int64 __fastcall WdcProcessMonitor::UpdateFrequency(WdcProcessMonitor *this, int a2, unsigned int a3)
{
  unsigned int v3; // ebx
  __int64 v5; // rsi
  __int64 v6; // r14
  __int64 v7; // rdx
  int v8; // r8d
  unsigned int *v9; // r15
  int v10; // eax
  unsigned int v11; // r11d
  __int64 i; // r12
  char *v13; // r9
  unsigned int v14; // r10d
  int v15; // eax
  unsigned int v16; // r13d
  int v17; // r15d
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned __int64 v20; // r10
  __int64 v21; // rdx
  double v22; // xmm0_8
  double v23; // xmm1_8
  double v24; // xmm0_8
  double v25; // xmm2_8
  double v26; // xmm1_8
  int v27; // eax
  SIZE_T v28; // rbx
  unsigned __int8 *v29; // rax
  unsigned __int8 *v30; // rsi
  NTSTATUS v31; // eax
  const char *v32; // rdx
  int v33; // r8d
  signed int v35; // eax
  __int64 v36; // [rsp+20h] [rbp-60h]
  __int64 v37; // [rsp+20h] [rbp-60h]
  __int64 v38; // [rsp+28h] [rbp-58h]
  __int64 v39; // [rsp+40h] [rbp-40h]
  int v40; // [rsp+50h] [rbp-30h]
  __int64 v41; // [rsp+50h] [rbp-30h]
  unsigned int v42; // [rsp+58h] [rbp-28h]
  int v43; // [rsp+5Ch] [rbp-24h]
  unsigned int v44; // [rsp+60h] [rbp-20h]
  char *v45; // [rsp+68h] [rbp-18h]
  unsigned int *v46; // [rsp+70h] [rbp-10h]
  unsigned __int16 v49; // [rsp+D8h] [rbp+58h] BYREF

  v40 = a2;
  v3 = 0;
  v49 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 64;
  v44 = 64;
  if ( MEMORY[0x7FFE03C4] <= 0x40u )
  {
    v7 = MEMORY[0x7FFE03C4];
    v44 = MEMORY[0x7FFE03C4];
  }
  v49 = 0;
  v8 = 0;
LABEL_4:
  if ( (unsigned __int16)v8 < (unsigned __int16)v7 )
  {
    v43 = WdcExpandingCall(
            (int (*)(struct _WDC_EXPANDING_CALL *))WdcQueryProcessorFrequency,
            (unsigned __int64 *)this + 1203,
            (void **)this + 1202,
            2u,
            &v49,
            2);
    v3 = v43;
    if ( v43 >= 0 )
    {
      v9 = (unsigned int *)*((_QWORD *)this + 1202);
      v8 = v49;
      v46 = v9;
      if ( *v9 <= *((_DWORD *)this + v49 + 2336) )
      {
LABEL_10:
        if ( (*((_BYTE *)this + 56) & 2) != 0 )
        {
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
            "WdcProcessMonitor::UpdateFrequency",
            0,
            L"Power States ===================");
          v8 = v49;
        }
        v11 = 0;
        v42 = 0;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= *v9 )
          {
            v7 = v44;
            LOWORD(v8) = v8 + 1;
            v49 = v8;
            goto LABEL_4;
          }
          v13 = (char *)v9 + v9[i + 1];
          v45 = v13;
          v14 = *((_DWORD *)v13 + 1);
          if ( v14 > (unsigned int)(*((_DWORD *)this + (unsigned __int16)v8 + 2670)
                                  / *((_DWORD *)this + (unsigned __int16)v8 + 2336)) )
          {
            v40 = 1;
            v15 = WdcProcessMonitor::SetPowerStates(this, v14, v8);
            v43 = v15;
            v3 = v15;
            if ( v15 < 0 )
            {
              LODWORD(v36) = v15;
              goto LABEL_30;
            }
            v8 = v49;
            v13 = v45;
            v11 = v42;
          }
          v16 = 0;
          if ( *((_DWORD *)v13 + 1) )
          {
            v17 = v40;
            do
            {
              v18 = *((_QWORD *)this + (unsigned __int16)v8 + 1367);
              v19 = 16LL * v16;
              v41 = v19;
              v20 = *(_QWORD *)&v13[v19 + 8];
              if ( *(_QWORD *)(v18 + 8LL * v11) > v20 )
                v17 = 1;
              v21 = v20 - *(_QWORD *)(v18 + 8LL * v11);
              v6 += v21;
              v5 += v21 * (unsigned __int8)v13[v19 + 16];
              if ( (*((_BYTE *)this + 56) & 2) != 0 )
              {
                LODWORD(v39) = (unsigned __int8)v13[v19 + 16];
                LODWORD(v38) = v16;
                LODWORD(v36) = i;
                WdcDebugMessage(
                  "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
                  "WdcProcessMonitor::UpdateFrequency",
                  0,
                  L"Processor[%2d] State[%2d] %4d (%3d) : %d %%",
                  v36,
                  v38,
                  v20,
                  v21,
                  v39);
                LOWORD(v8) = v49;
                v13 = v45;
                v11 = v42;
              }
              *(_QWORD *)(*((_QWORD *)this + (unsigned __int16)v8 + 1367) + 8LL * v11) = *(_QWORD *)&v13[v41 + 8];
              v8 = v49;
              ++v11;
              ++v16;
              v42 = v11;
            }
            while ( v16 < *((_DWORD *)v13 + 1) );
            v3 = v43;
            v40 = v17;
            v9 = v46;
          }
        }
      }
      v10 = WdcProcessMonitor::SetProcessors(this, *v9, v49);
      v3 = v10;
      if ( v10 < 0 )
      {
        LODWORD(v36) = v10;
        goto LABEL_30;
      }
      v40 = 1;
      v43 = WdcProcessMonitor::SetPowerStates(this, *(unsigned int *)((char *)v9 + v9[1] + 4), v49);
      v3 = v43;
      if ( v43 >= 0 )
      {
        v8 = v49;
        goto LABEL_10;
      }
    }
    goto LABEL_29;
  }
  v49 = 0;
  if ( !v40 && v5 && v6 )
  {
    if ( v5 < 0 )
      v22 = (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1)) + (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1));
    else
      v22 = (double)(int)v5;
    if ( v6 < 0 )
      v23 = (double)(int)(v6 & 1 | ((unsigned __int64)v6 >> 1)) + (double)(int)(v6 & 1 | ((unsigned __int64)v6 >> 1));
    else
      v23 = (double)(int)v6;
    v24 = v22 / v23;
    v25 = 0.0;
    if ( v24 >= 0.0 )
      v25 = v24;
    v26 = DOUBLE_100_0;
    if ( v24 <= 100.0 )
      v26 = v25;
    *((double *)this + a3 + 1083) = v26;
    return v3;
  }
  if ( a2 )
    return v3;
  v27 = *((_DWORD *)this + 2336);
  if ( !v27 )
    return v3;
  v28 = (unsigned int)(80 * v27);
  v29 = (unsigned __int8 *)WdcAlloc(v28, (const char *)v7, v8);
  v30 = v29;
  if ( v29 )
  {
    v31 = NtQuerySystemInformationEx(61, &v49, 2, v29, v28, 0);
    if ( v31 )
    {
      v35 = RtlNtStatusToDosError(v31);
      v3 = 0;
      if ( v35 )
      {
        if ( v35 > 0 )
          v3 = (unsigned __int16)v35 | 0x80070000;
        else
          v3 = v35;
      }
      if ( (v3 & 0x80000000) != 0 )
      {
        LODWORD(v37) = v3;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
          "WdcProcessMonitor::UpdateFrequency",
          0,
          L"FAILURE: 0x%08x",
          v37);
        goto LABEL_52;
      }
    }
    else
    {
      v3 = 0;
    }
    *((double *)this + a3 + 1083) = (double)*v30;
LABEL_52:
    WdcFree(v30, v32, v33);
    return v3;
  }
  v3 = -2147024882;
LABEL_29:
  LODWORD(v36) = v3;
LABEL_30:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
    "WdcProcessMonitor::UpdateFrequency",
    0,
    L"FAILURE: 0x%08x",
    v36);
  return v3;
}

```

## disassembly

```asm
0x18001f16c  mov     [rsp-38h+arg_0], rbx
0x18001f171  mov     [rsp-38h+arg_10], r8d
0x18001f176  mov     [rsp-38h+arg_8], edx
0x18001f17a  push    rbp
0x18001f17b  push    rsi
0x18001f17c  push    rdi
0x18001f17d  push    r12
0x18001f17f  push    r13
0x18001f181  push    r14
0x18001f183  push    r15
0x18001f185  mov     rbp, rsp
0x18001f188  sub     rsp, 80h
0x18001f18f  xor     eax, eax
0x18001f191  mov     dword ptr [rbp+var_30], edx
0x18001f194  xor     ebx, ebx
0x18001f196  mov     [rbp+arg_18], ax
0x18001f19a  mov     al, ds:7FFE03C4h
0x18001f1a1  mov     rdi, rcx
0x18001f1a4  movzx   ecx, al
0x18001f1a7  xor     esi, esi
0x18001f1a9  xor     r14d, r14d
0x18001f1ac  lea     edx, [rbx+40h]
0x18001f1af  mov     [rbp+var_20], edx
0x18001f1b2  cmp     cx, dx
0x18001f1b5  ja      short loc_18001F1BD
0x18001f1b7  movzx   edx, cx; char *
0x18001f1ba  mov     [rbp+var_20], edx
0x18001f1bd  xor     eax, eax
0x18001f1bf  mov     [rbp+arg_18], ax
0x18001f1c3  xor     r8d, r8d; int
0x18001f1c6  lea     ecx, [rax+1]
0x18001f1c9  lea     r12, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18001f1d0  lea     r13, aWdcprocessmoni; "WdcProcessMonitor::UpdateFrequency"
0x18001f1d7  cmp     r8w, dx
0x18001f1db  jnb     loc_18001F447
0x18001f1e1  lea     rax, [rbp+arg_18]
0x18001f1e5  mov     [rsp+80h+var_58], 2
0x18001f1ee  lea     r15, [rdi+2590h]
0x18001f1f5  mov     [rsp+80h+var_60], rax
0x18001f1fa  mov     r8, r15; void **
0x18001f1fd  lea     rdx, [rdi+2598h]; unsigned __int64 *
0x18001f204  mov     r9d, 2; unsigned int
0x18001f20a  lea     rcx, ?WdcQueryProcessorFrequency@@YAJPEAU_WDC_EXPANDING_CALL@@@Z; int (*)(struct _WDC_EXPANDING_CALL *)
0x18001f211  call    ?WdcExpandingCall@@YAJP6AJPEAU_WDC_EXPANDING_CALL@@@ZPEA_KPEAPEAXKZZ; WdcExpandingCall(long (*)(_WDC_EXPANDING_CALL *),unsigned __int64 *,void * *,ulong,...)
0x18001f216  mov     [rbp+var_24], eax
0x18001f219  mov     ebx, eax
0x18001f21b  test    eax, eax
0x18001f21d  js      loc_18001F429
0x18001f223  mov     r15, [r15]
0x18001f226  movzx   r8d, [rbp+arg_18]; unsigned __int16
0x18001f22b  mov     [rbp+var_10], r15
0x18001f22f  mov     edx, [r15]; unsigned int
0x18001f232  cmp     edx, [rdi+r8*4+2480h]
0x18001f23a  jbe     short loc_18001F27D
0x18001f23c  mov     rcx, rdi; this
0x18001f23f  call    ?SetProcessors@WdcProcessMonitor@@AEAAJKG@Z; WdcProcessMonitor::SetProcessors(ulong,ushort)
0x18001f244  mov     ebx, eax
0x18001f246  test    eax, eax
0x18001f248  js      loc_18001F40F
0x18001f24e  mov     edx, [r15+4]
0x18001f252  mov     rcx, rdi; this
0x18001f255  movzx   r8d, [rbp+arg_18]; unsigned __int16
0x18001f25a  mov     dword ptr [rbp+var_30], 1
0x18001f261  mov     edx, [rdx+r15+4]; unsigned int
0x18001f266  call    ?SetPowerStates@WdcProcessMonitor@@AEAAJKG@Z; WdcProcessMonitor::SetPowerStates(ulong,ushort)
0x18001f26b  mov     [rbp+var_24], eax
0x18001f26e  mov     ebx, eax
0x18001f270  test    eax, eax
0x18001f272  js      loc_18001F429
0x18001f278  movzx   r8d, [rbp+arg_18]
0x18001f27d  test    byte ptr [rdi+38h], 2
0x18001f281  jz      short loc_18001F29D
0x18001f283  lea     r9, aPowerStates; "Power States ==================="
0x18001f28a  xor     r8d, r8d; int
0x18001f28d  mov     rdx, r13; char *
0x18001f290  mov     rcx, r12; char *
0x18001f293  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001f298  movzx   r8d, [rbp+arg_18]; unsigned __int16
0x18001f29d  xor     r11d, r11d
0x18001f2a0  mov     [rbp+var_28], r11d
0x18001f2a4  xor     r12d, r12d
0x18001f2a7  lea     ecx, [r11+1]
0x18001f2ab  cmp     r12d, [r15]
0x18001f2ae  jnb     loc_18001F3FE
0x18001f2b4  mov     r9d, [r15+r12*4+4]
0x18001f2b9  xor     edx, edx
0x18001f2bb  movzx   ecx, r8w
0x18001f2bf  add     r9, r15
0x18001f2c2  mov     [rbp+var_18], r9
0x18001f2c6  mov     eax, [rdi+rcx*4+29B8h]
0x18001f2cd  div     dword ptr [rdi+rcx*4+2480h]
0x18001f2d4  mov     r10d, [r9+4]
0x18001f2d8  cmp     r10d, eax
0x18001f2db  jbe     short loc_18001F309
0x18001f2dd  mov     edx, r10d; unsigned int
0x18001f2e0  mov     dword ptr [rbp+var_30], 1
0x18001f2e7  mov     rcx, rdi; this
0x18001f2ea  call    ?SetPowerStates@WdcProcessMonitor@@AEAAJKG@Z; WdcProcessMonitor::SetPowerStates(ulong,ushort)
0x18001f2ef  mov     [rbp+var_24], eax
0x18001f2f2  mov     ebx, eax
0x18001f2f4  test    eax, eax
0x18001f2f6  js      loc_18001F415
0x18001f2fc  movzx   r8d, [rbp+arg_18]
0x18001f301  mov     r9, [rbp+var_18]
0x18001f305  mov     r11d, [rbp+var_28]
0x18001f309  xor     r13d, r13d
0x18001f30c  cmp     [r9+4], r13d
0x18001f310  jbe     loc_18001F3F1
0x18001f316  mov     r15d, dword ptr [rbp+var_30]
0x18001f31a  movzx   eax, r8w
0x18001f31e  mov     edx, r11d
0x18001f321  mov     ebx, r11d
0x18001f324  mov     rcx, [rdi+rax*8+2AB8h]
0x18001f32c  mov     eax, r13d
0x18001f32f  shl     rax, 4
0x18001f333  mov     [rbp+var_30], rax
0x18001f337  mov     r10, [rax+r9+8]
0x18001f33c  cmp     [rcx+rdx*8], r10
0x18001f340  mov     edx, 1
0x18001f345  cmova   r15d, edx
0x18001f349  mov     rdx, r10
0x18001f34c  sub     rdx, [rcx+rbx*8]
0x18001f350  movzx   ecx, byte ptr [rax+r9+10h]
0x18001f356  add     r14, rdx
0x18001f359  mov     eax, ecx
0x18001f35b  imul    rax, rdx
0x18001f35f  add     rsi, rax
0x18001f362  test    byte ptr [rdi+38h], 2
0x18001f366  jz      short loc_18001F3AA
0x18001f368  mov     [rsp+80h+var_40], ecx
0x18001f36c  lea     r9, aProcessor2dSta; "Processor[%2d] State[%2d] %4d (%3d) : %"...
0x18001f373  mov     [rsp+80h+var_48], rdx
0x18001f378  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18001f37f  mov     [rsp+80h+var_50], r10
0x18001f384  lea     rdx, aWdcprocessmoni; "WdcProcessMonitor::UpdateFrequency"
0x18001f38b  mov     dword ptr [rsp+80h+var_58], r13d
0x18001f390  xor     r8d, r8d; int
0x18001f393  mov     dword ptr [rsp+80h+var_60], r12d
0x18001f398  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001f39d  movzx   r8d, [rbp+arg_18]
0x18001f3a2  mov     r9, [rbp+var_18]
0x18001f3a6  mov     r11d, [rbp+var_28]
0x18001f3aa  movzx   eax, r8w
0x18001f3ae  mov     edx, r11d
0x18001f3b1  mov     rcx, [rdi+rax*8+2AB8h]
0x18001f3b9  mov     rax, [rbp+var_30]
0x18001f3bd  mov     rax, [rax+r9+8]
0x18001f3c2  mov     [rcx+rdx*8], rax
0x18001f3c6  mov     ecx, 1
0x18001f3cb  movzx   r8d, [rbp+arg_18]
0x18001f3d0  add     r11d, ecx
0x18001f3d3  add     r13d, ecx
0x18001f3d6  mov     [rbp+var_28], r11d
0x18001f3da  cmp     r13d, [r9+4]
0x18001f3de  jb      loc_18001F31A
0x18001f3e4  mov     ebx, [rbp+var_24]
0x18001f3e7  mov     dword ptr [rbp+var_30], r15d
0x18001f3eb  mov     r15, [rbp+var_10]
0x18001f3ef  jmp     short loc_18001F3F6
0x18001f3f1  mov     ecx, 1
0x18001f3f6  add     r12d, ecx
0x18001f3f9  jmp     loc_18001F2AB
0x18001f3fe  mov     edx, [rbp+var_20]
0x18001f401  add     r8w, cx
0x18001f405  mov     [rbp+arg_18], r8w
0x18001f40a  jmp     loc_18001F1C9
0x18001f40f  mov     dword ptr [rsp+80h+var_60], eax
0x18001f413  jmp     short loc_18001F42D
0x18001f415  mov     dword ptr [rsp+80h+var_60], eax
0x18001f419  lea     rdx, aWdcprocessmoni; "WdcProcessMonitor::UpdateFrequency"
0x18001f420  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18001f427  jmp     short loc_18001F433
0x18001f429  mov     dword ptr [rsp+80h+var_60], ebx
0x18001f42d  mov     rdx, r13; char *
0x18001f430  mov     rcx, r12; char *
0x18001f433  xor     r8d, r8d; int
0x18001f436  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001f43d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001f442  jmp     loc_18001F550
0x18001f447  xor     eax, eax
0x18001f449  mov     [rbp+arg_18], ax
0x18001f44d  cmp     dword ptr [rbp+var_30], eax
0x18001f450  jnz     loc_18001F4D7
0x18001f456  test    rsi, rsi
0x18001f459  jz      short loc_18001F4D7
0x18001f45b  test    r14, r14
0x18001f45e  jz      short loc_18001F4D7
0x18001f460  xorps   xmm0, xmm0
0x18001f463  test    rsi, rsi
0x18001f466  js      short loc_18001F46F
0x18001f468  cvtsi2sd xmm0, rsi
0x18001f46d  jmp     short loc_18001F484
0x18001f46f  mov     rax, rsi
0x18001f472  and     rsi, rcx
0x18001f475  shr     rax, 1
0x18001f478  or      rax, rsi
0x18001f47b  cvtsi2sd xmm0, rax
0x18001f480  addsd   xmm0, xmm0
0x18001f484  xorps   xmm1, xmm1
0x18001f487  test    r14, r14
0x18001f48a  js      short loc_18001F493
0x18001f48c  cvtsi2sd xmm1, r14
0x18001f491  jmp     short loc_18001F4A8
0x18001f493  mov     rax, r14
0x18001f496  and     r14, rcx
0x18001f499  shr     rax, 1
0x18001f49c  or      rax, r14
0x18001f49f  cvtsi2sd xmm1, rax
0x18001f4a4  addsd   xmm1, xmm1
0x18001f4a8  divsd   xmm0, xmm1
0x18001f4ac  xorps   xmm2, xmm2
0x18001f4af  comisd  xmm2, xmm0
0x18001f4b3  ja      short loc_18001F4B8
0x18001f4b5  movaps  xmm2, xmm0
0x18001f4b8  movsd   xmm1, cs:__real@4059000000000000
0x18001f4c0  comisd  xmm0, xmm1
0x18001f4c4  ja      short loc_18001F4C9
0x18001f4c6  movaps  xmm1, xmm2
0x18001f4c9  mov     eax, [rbp+arg_10]
0x18001f4cc  movsd   qword ptr [rdi+rax*8+21D8h], xmm1
0x18001f4d5  jmp     short loc_18001F550
0x18001f4d7  cmp     [rbp+arg_8], eax
0x18001f4da  jnz     short loc_18001F550
0x18001f4dc  mov     eax, [rdi+2480h]
0x18001f4e2  test    eax, eax
0x18001f4e4  jz      short loc_18001F550
0x18001f4e6  lea     eax, [rax+rax*4]
0x18001f4e9  shl     eax, 4
0x18001f4ec  mov     ecx, eax; dwBytes
0x18001f4ee  mov     ebx, eax
0x18001f4f0  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18001f4f5  mov     rsi, rax
0x18001f4f8  test    rax, rax
0x18001f4fb  jnz     short loc_18001F507
0x18001f4fd  mov     ebx, 8007000Eh
0x18001f502  jmp     loc_18001F429
0x18001f507  mov     r8d, 2
0x18001f50d  mov     [rsp+80h+var_58], 0
0x18001f516  mov     r9, rsi
0x18001f519  mov     dword ptr [rsp+80h+var_60], ebx
0x18001f51d  lea     rdx, [rbp+arg_18]
0x18001f521  lea     ecx, [r8+3Bh]
0x18001f525  call    cs:__imp_NtQuerySystemInformationEx
0x18001f52b  test    eax, eax
0x18001f52d  jnz     short loc_18001F56D
0x18001f52f  xor     ebx, ebx
0x18001f531  movzx   eax, byte ptr [rsi]
0x18001f534  movd    xmm0, eax
0x18001f538  mov     eax, [rbp+arg_10]
0x18001f53b  cvtdq2pd xmm0, xmm0
0x18001f53f  movsd   qword ptr [rdi+rax*8+21D8h], xmm0
0x18001f548  mov     rcx, rsi; void *
0x18001f54b  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18001f550  mov     eax, ebx
0x18001f552  mov     rbx, [rsp+80h+arg_0]
0x18001f55a  add     rsp, 80h
0x18001f561  pop     r15
0x18001f563  pop     r14
0x18001f565  pop     r13
0x18001f567  pop     r12
0x18001f569  pop     rdi
0x18001f56a  pop     rsi
0x18001f56b  pop     rbp
0x18001f56c  retn
0x18001f56d  mov     ecx, eax; Status
0x18001f56f  call    cs:__imp_RtlNtStatusToDosError
0x18001f575  xor     ebx, ebx
0x18001f577  test    eax, eax
0x18001f579  jz      short loc_18001F58A
0x18001f57b  jg      short loc_18001F581
0x18001f57d  mov     ebx, eax
0x18001f57f  jmp     short loc_18001F58A
0x18001f581  movzx   ebx, ax
0x18001f584  or      ebx, 80070000h
0x18001f58a  test    ebx, ebx
0x18001f58c  jns     short loc_18001F531
0x18001f58e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001f595  mov     dword ptr [rsp+80h+var_60], ebx
0x18001f599  xor     r8d, r8d; int
0x18001f59c  mov     rdx, r13; char *
0x18001f59f  mov     rcx, r12; char *
0x18001f5a2  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001f5a7  jmp     short loc_18001F548
```
