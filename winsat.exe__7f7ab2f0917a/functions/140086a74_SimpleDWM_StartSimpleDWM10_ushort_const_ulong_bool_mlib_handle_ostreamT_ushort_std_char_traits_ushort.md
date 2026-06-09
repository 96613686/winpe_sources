# SimpleDWM::StartSimpleDWM10(ushort const *,ulong,bool,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> *)

- ea: `0x140086a74`
- end: `0x140086db1`
- name: `?StartSimpleDWM10@SimpleDWM@@YAJPEBGK_NPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140079e98`

## callees

- `0x14000398c`
- `0x14007fa4c`
- `0x14007fec8`
- `0x14007fef4`
- `0x1400803b0`
- `0x14008064c`
- `0x140081584`
- `0x140085890`
- `0x140086a74`
- `0x14008a990`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140086aa9`
- `KERNEL32!GetCurrentProcessId` at `0x140086aa9`
- `msvcrt!srand` at `0x140086ac4`
- `msvcrt!srand` at `0x140086ac4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SimpleDWM::StartSimpleDWM10(__int64 a1, __int64 a2, bool a3, __int64 a4)
{
  unsigned int *v7; // r9
  unsigned int *v8; // r9
  SimpleDWM::SimpleDWMState10 *v9; // rax
  unsigned int *v10; // r9
  __int64 v11; // rsi
  int v12; // edi
  D3DCommon::DX10Framework *v13; // rax
  unsigned __int16 v14; // dx
  D3DCommon::DX10Framework *v15; // rbx
  UINT v16; // ecx
  UINT v17; // eax
  unsigned int *v18; // r9
  unsigned int v20[2]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  DXGI_SWAP_CHAIN_DESC v22; // [rsp+40h] [rbp-29h] BYREF

  v20[0] = GetCurrentProcessId();
  D3DCommon::g_bVerbose = a3;
  D3DCommon::g_phStdOut = a4;
  srand(0xA017200u);
  D3DCommon::LogMessage((D3DCommon *)0x53, 1, 0, v7);
  D3DCommon::LogMessage((D3DCommon *)0x5A, 1, (int *)v20, v8);
  v9 = (SimpleDWM::SimpleDWMState10 *)operator new(0x3C8u, (const struct std::nothrow_t *)std::nothrow);
  *(_QWORD *)v20 = v9;
  if ( v9 )
    v11 = SimpleDWM::SimpleDWMState10::SimpleDWMState10(v9);
  else
    v11 = 0;
  if ( v11 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
    v20[0] = v12;
    if ( v12 < 0 )
      goto LABEL_25;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 40LL))(v11, a1);
    v20[0] = v12;
    if ( v12 < 0 )
      goto LABEL_25;
    *(_DWORD *)(v11 + 60) = 1;
    v13 = (D3DCommon::DX10Framework *)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
    v15 = v13;
    if ( !v13 )
    {
      v12 = -2147024882;
      v20[0] = -2147024882;
      D3DCommon::ERR((D3DCommon *)0x74, v14);
      goto LABEL_25;
    }
    *(_QWORD *)v13 = 0;
    *((_DWORD *)v13 + 4) = -1;
    *((_QWORD *)v13 + 3) = 0;
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    *((_QWORD *)v13 + 8) = 0;
    *((_QWORD *)v13 + 9) = 0;
    *((_DWORD *)v13 + 20) = 0;
    *((_BYTE *)v13 + 84) = 0;
    *((_DWORD *)v13 + 5) = 0;
    v20[0] = 0;
    *((_QWORD *)v13 + 1) = v11;
    if ( *(_QWORD *)(v11 + 152) )
    {
      if ( *(_QWORD *)(v11 + 160) )
      {
        *(_QWORD *)v13 = v11 + 344;
        v12 = D3DCommon::DXCreateWindow(
                L"SimpleDWM10 Back to Front",
                (const unsigned __int16 *)*(unsigned int *)(v11 + 88));
        v20[0] = v12;
        if ( v12 >= 0 )
        {
          *(_QWORD *)&v22.BufferCount = 1;
          *(_QWORD *)&v22.Flags = 0;
          v22.BufferDesc.Width = 1024;
          v22.BufferDesc.Height = 768;
          v16 = 60;
          v22.BufferDesc.RefreshRate.Numerator = 60;
          v22.BufferDesc.RefreshRate.Denominator = 1;
          v22.BufferDesc.Format = DXGI_FORMAT_R8G8B8A8_UNORM;
          *(_QWORD *)&v22.BufferDesc.ScanlineOrdering = 1;
          v22.SampleDesc = (DXGI_SAMPLE_DESC)1LL;
          v22.BufferUsage = 32;
          v22.OutputWindow = hWnd;
          *(_QWORD *)&v22.Windowed = 1;
          v22.SampleDesc = *(DXGI_SAMPLE_DESC *)(v11 + 376);
          v17 = 1;
          if ( *(_DWORD *)(v11 + 88) != 128 )
            v17 = 4;
          v22.BufferCount = v17;
          v22.BufferDesc.Width = *(_DWORD *)(v11 + 24);
          v22.BufferDesc.Height = *(_DWORD *)(v11 + 28);
          if ( *(_BYTE *)(v11 + 32) )
          {
            if ( *(_DWORD *)(v11 + 36) )
              v16 = *(_DWORD *)(v11 + 36);
            v22.BufferDesc.RefreshRate.Numerator = v16;
          }
          v21 = 0;
          v21 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v11 + 360) - *(_QWORD *)(v11 + 352)) >> 2);
          v12 = D3DCommon::DX10Framework::CreateDevice(v15, 1, &v22, &v21, *(D3D10_DRIVER_TYPE **)(v11 + 352));
          v20[0] = v12;
          if ( v12 >= 0 )
          {
            D3DCommon::LogMessage((D3DCommon *)0x59, 1, (int *)(v11 + 212), v18);
            v12 = D3DCommon::DX10Framework::RunMainLoop(v15);
            v20[0] = v12;
            D3DCommon::DX10Framework::DestroyDevice(v15);
          }
        }
        goto LABEL_23;
      }
      D3DCommon::ERR((D3DCommon *)0x6D, (unsigned __int16)L"pState->m_pTexHeight", L"SimpleDWM::StartSimpleDWM10");
    }
    else
    {
      D3DCommon::ERR((D3DCommon *)0x6D, (unsigned __int16)L"pState->m_pTexWidth", L"SimpleDWM::StartSimpleDWM10");
    }
    v12 = -2147024882;
    v20[0] = -2147024882;
LABEL_23:
    D3DCommon::DX10Framework::DestroyDevice(v15);
    D3DCommon::DX10Framework::`scalar deleting destructor'(v15);
LABEL_25:
    (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
    goto LABEL_26;
  }
  v12 = -2147024882;
  v20[0] = -2147024882;
LABEL_26:
  D3DCommon::LogMessage((D3DCommon *)0x45, 1, (int *)v20, v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140086a74  mov     [rsp-8+arg_8], rbx
0x140086a79  mov     [rsp-8+arg_10], rsi
0x140086a7e  push    rbp
0x140086a7f  push    rdi
0x140086a80  push    r12
0x140086a82  push    r14
0x140086a84  push    r15
0x140086a86  lea     rbp, [rsp-37h]
0x140086a8b  sub     rsp, 0A0h
0x140086a92  mov     rax, cs:__security_cookie
0x140086a99  xor     rax, rsp
0x140086a9c  mov     [rbp+57h+var_30], rax
0x140086aa0  mov     rdi, r9
0x140086aa3  mov     bl, r8b
0x140086aa6  mov     r14, rcx
0x140086aa9  call    cs:__imp_GetCurrentProcessId
0x140086aaf  mov     [rbp+57h+var_90], eax
0x140086ab2  mov     cs:?g_bVerbose@D3DCommon@@3_NA, bl; bool D3DCommon::g_bVerbose
0x140086ab8  mov     cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA, rdi; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x140086abf  mov     ecx, 0A017200h; Seed
0x140086ac4  call    cs:__imp_srand
0x140086aca  mov     ecx, 53h ; 'S'; this
0x140086acf  xor     r8d, r8d; unsigned int
0x140086ad2  lea     r12d, [rcx-52h]
0x140086ad6  mov     edx, r12d; unsigned __int16
0x140086ad9  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x140086ade  lea     ecx, [r12+59h]; this
0x140086ae3  lea     r8, [rbp+57h+var_90]; unsigned int
0x140086ae7  mov     edx, r12d; unsigned __int16
0x140086aea  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x140086aef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140086af6  mov     ecx, 3C8h; unsigned __int64
0x140086afb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140086b00  mov     qword ptr [rbp+57h+var_90], rax
0x140086b04  xor     r15d, r15d
0x140086b07  test    rax, rax
0x140086b0a  jz      short loc_140086B19
0x140086b0c  mov     rcx, rax; this
0x140086b0f  call    ??0SimpleDWMState10@SimpleDWM@@QEAA@XZ; SimpleDWM::SimpleDWMState10::SimpleDWMState10(void)
0x140086b14  mov     rsi, rax
0x140086b17  jmp     short loc_140086B1C
0x140086b19  mov     rsi, r15
0x140086b1c  test    rsi, rsi
0x140086b1f  jnz     short loc_140086B2E
0x140086b21  mov     edi, 8007000Eh
0x140086b26  mov     [rbp+57h+var_90], edi
0x140086b29  jmp     loc_140086D76
0x140086b2e  mov     rax, [rsi]
0x140086b31  mov     rcx, rsi
0x140086b34  mov     rax, [rax+18h]
0x140086b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086b3d  mov     edi, eax
0x140086b3f  mov     [rbp+57h+var_90], eax
0x140086b42  test    eax, eax
0x140086b44  js      loc_140086D65
0x140086b4a  mov     rax, [rsi]
0x140086b4d  mov     rdx, r14
0x140086b50  mov     rcx, rsi
0x140086b53  mov     rax, [rax+28h]
0x140086b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086b5c  mov     edi, eax
0x140086b5e  mov     [rbp+57h+var_90], eax
0x140086b61  test    eax, eax
0x140086b63  js      loc_140086D65
0x140086b69  mov     [rsi+3Ch], r12d
0x140086b6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140086b74  mov     ecx, 58h ; 'X'; unsigned __int64
0x140086b79  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140086b7e  mov     rbx, rax
0x140086b81  test    rax, rax
0x140086b84  jz      loc_140086D53
0x140086b8a  mov     [rax], r15
0x140086b8d  mov     dword ptr [rax+10h], 0FFFFFFFFh
0x140086b94  mov     [rax+18h], r15
0x140086b98  mov     [rax+20h], r15
0x140086b9c  mov     [rax+28h], r15
0x140086ba0  mov     [rax+30h], r15
0x140086ba4  mov     [rax+38h], r15
0x140086ba8  mov     [rax+40h], r15
0x140086bac  mov     [rax+48h], r15
0x140086bb0  mov     [rax+50h], r15d
0x140086bb4  mov     [rax+54h], r15b
0x140086bb8  mov     [rax+14h], r15d
0x140086bbc  mov     [rbp+57h+var_90], r15d
0x140086bc0  mov     [rax+8], rsi
0x140086bc4  cmp     [rsi+98h], r15
0x140086bcb  jnz     short loc_140086BF2
0x140086bcd  lea     rdx, aPstateMPtexwid; "pState->m_pTexWidth"
0x140086bd4  lea     r8, aSimpledwmStart; "SimpleDWM::StartSimpleDWM10"
0x140086bdb  mov     ecx, 6Dh ; 'm'; this
0x140086be0  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140086be5  mov     edi, 8007000Eh
0x140086bea  mov     [rbp+57h+var_90], edi
0x140086bed  jmp     loc_140086D41
0x140086bf2  cmp     [rsi+0A0h], r15
0x140086bf9  jnz     short loc_140086C04
0x140086bfb  lea     rdx, aPstateMPtexhei; "pState->m_pTexHeight"
0x140086c02  jmp     short loc_140086BD4
0x140086c04  lea     rax, [rsi+158h]
0x140086c0b  mov     [rbx], rax
0x140086c0e  mov     edx, [rsi+58h]; unsigned __int16 *
0x140086c11  lea     rcx, aSimpledwm10Bac; "SimpleDWM10 Back to Front"
0x140086c18  call    ?DXCreateWindow@D3DCommon@@YAJPEBGI@Z; D3DCommon::DXCreateWindow(ushort const *,uint)
0x140086c1d  mov     edi, eax
0x140086c1f  mov     [rbp+57h+var_90], eax
0x140086c22  test    eax, eax
0x140086c24  js      loc_140086D41
0x140086c2a  mov     qword ptr [rbp+57h+var_80.BufferCount], 1
0x140086c32  mov     qword ptr [rbp+57h+var_80.Flags], r15
0x140086c36  mov     [rbp+57h+var_80.BufferDesc.Width], 400h
0x140086c3d  mov     [rbp+57h+var_80.BufferDesc.Height], 300h
0x140086c44  mov     ecx, 3Ch ; '<'
0x140086c49  mov     [rbp+57h+var_80.BufferDesc.RefreshRate.Numerator], ecx
0x140086c4c  mov     [rbp+57h+var_80.BufferDesc.RefreshRate.Denominator], r12d
0x140086c50  mov     [rbp+57h+var_80.BufferDesc.Format], 1Ch
0x140086c57  mov     qword ptr [rbp+57h+var_80.BufferDesc.ScanlineOrdering], 1
0x140086c5f  mov     qword ptr [rbp+57h+var_80.SampleDesc.Count], 1
0x140086c67  mov     [rbp+57h+var_80.BufferUsage], 20h ; ' '
0x140086c6e  mov     rax, cs:hWnd
0x140086c75  mov     [rbp+57h+var_80.OutputWindow], rax
0x140086c79  mov     qword ptr [rbp+57h+var_80.Windowed], 1
0x140086c81  mov     eax, [rsi+178h]
0x140086c87  mov     [rbp+57h+var_80.SampleDesc.Count], eax
0x140086c8a  mov     eax, [rsi+17Ch]
0x140086c90  mov     [rbp+57h+var_80.SampleDesc.Quality], eax
0x140086c93  mov     eax, r12d
0x140086c96  lea     edx, [rcx-38h]
0x140086c99  cmp     dword ptr [rsi+58h], 80h
0x140086ca0  cmovnz  eax, edx
0x140086ca3  mov     [rbp+57h+var_80.BufferCount], eax
0x140086ca6  mov     eax, [rsi+18h]
0x140086ca9  mov     [rbp+57h+var_80.BufferDesc.Width], eax
0x140086cac  mov     eax, [rsi+1Ch]
0x140086caf  mov     [rbp+57h+var_80.BufferDesc.Height], eax
0x140086cb2  cmp     [rsi+20h], r15b
0x140086cb6  jz      short loc_140086CC3
0x140086cb8  cmp     [rsi+24h], r15d
0x140086cbc  cmovnz  ecx, [rsi+24h]
0x140086cc0  mov     [rbp+57h+var_80.BufferDesc.RefreshRate.Numerator], ecx
0x140086cc3  mov     [rbp+57h+var_88], r15
0x140086cc7  mov     rax, [rsi+168h]
0x140086cce  sub     rax, [rsi+160h]
0x140086cd5  sar     rax, 2
0x140086cd9  mov     rcx, 0AAAAAAAAAAAAAAABh
0x140086ce3  imul    rax, rcx
0x140086ce7  mov     [rbp+57h+var_88], rax
0x140086ceb  mov     [rsp+0C0h+var_98], r15; struct IDXGIAdapter *
0x140086cf0  mov     rax, [rsi+160h]
0x140086cf7  mov     [rsp+0C0h+var_A0], rax; struct D3DCommon::DX10DeviceDesc *
0x140086cfc  lea     r9, [rbp+57h+var_88]; unsigned __int64 *
0x140086d00  lea     r8, [rbp+57h+var_80]; struct DXGI_SWAP_CHAIN_DESC *
0x140086d04  mov     edx, r12d; unsigned int
0x140086d07  mov     rcx, rbx; this
0x140086d0a  call    ?CreateDevice@DX10Framework@D3DCommon@@QEAAJKPEAUDXGI_SWAP_CHAIN_DESC@@AEA_KQEAUDX10DeviceDesc@2@PEAUIDXGIAdapter@@@Z; D3DCommon::DX10Framework::CreateDevice(ulong,DXGI_SWAP_CHAIN_DESC *,unsigned __int64 &,D3DCommon::DX10DeviceDesc * const,IDXGIAdapter *)
0x140086d0f  mov     edi, eax
0x140086d11  mov     [rbp+57h+var_90], eax
0x140086d14  test    eax, eax
0x140086d16  js      short loc_140086D41
0x140086d18  lea     r8, [rsi+0D4h]; unsigned int
0x140086d1f  mov     ecx, 59h ; 'Y'; this
0x140086d24  mov     edx, r12d; unsigned __int16
0x140086d27  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x140086d2c  mov     rcx, rbx; this
0x140086d2f  call    ?RunMainLoop@DX10Framework@D3DCommon@@QEAAJXZ; D3DCommon::DX10Framework::RunMainLoop(void)
0x140086d34  mov     edi, eax
0x140086d36  mov     [rbp+57h+var_90], eax
0x140086d39  mov     rcx, rbx; this
0x140086d3c  call    ?DestroyDevice@DX10Framework@D3DCommon@@QEAAXXZ; D3DCommon::DX10Framework::DestroyDevice(void)
0x140086d41  mov     rcx, rbx; this
0x140086d44  call    ?DestroyDevice@DX10Framework@D3DCommon@@QEAAXXZ; D3DCommon::DX10Framework::DestroyDevice(void)
0x140086d49  mov     rcx, rbx; this
0x140086d4c  call    ??_GDX10Framework@D3DCommon@@AEAAPEAXI@Z; D3DCommon::DX10Framework::`scalar deleting destructor'(uint)
0x140086d51  jmp     short loc_140086D65
0x140086d53  mov     edi, 8007000Eh
0x140086d58  mov     [rbp+57h+var_90], edi
0x140086d5b  mov     ecx, 74h ; 't'; this
0x140086d60  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140086d65  mov     rcx, [rsi]
0x140086d68  mov     rax, [rcx]
0x140086d6b  mov     edx, r12d
0x140086d6e  mov     rcx, rsi
0x140086d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086d76  mov     ecx, 45h ; 'E'; this
0x140086d7b  lea     r8, [rbp+57h+var_90]; unsigned int
0x140086d7f  mov     edx, r12d; unsigned __int16
0x140086d82  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x140086d87  mov     eax, edi
0x140086d89  mov     rcx, [rbp+57h+var_30]
0x140086d8d  xor     rcx, rsp; StackCookie
0x140086d90  call    __security_check_cookie
0x140086d95  lea     r11, [rsp+0C0h+var_20]
0x140086d9d  mov     rbx, [r11+38h]
0x140086da1  mov     rsi, [r11+40h]
0x140086da5  mov     rsp, r11
0x140086da8  pop     r15
0x140086daa  pop     r14
0x140086dac  pop     r12
0x140086dae  pop     rdi
0x140086daf  pop     rbp
0x140086db0  retn
```
