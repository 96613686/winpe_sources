# D3DCommon::DX10Framework::CreateDevice(ulong,DXGI_SWAP_CHAIN_DESC *,unsigned __int64 &,D3DCommon::DX10DeviceDesc * const,IDXGIAdapter *)

- ea: `0x14007fef4`
- end: `0x1400803aa`
- name: `?CreateDevice@DX10Framework@D3DCommon@@QEAAJKPEAUDXGI_SWAP_CHAIN_DESC@@AEA_KQEAUDX10DeviceDesc@2@PEAUIDXGIAdapter@@@Z`
- size: `1206`
- prototype: `__int64 __usercall@<rax>(D3DCommon::DX10Framework *__hidden this@<rcx>, unsigned int@<edx>, struct DXGI_SWAP_CHAIN_DESC *@<r8>, unsigned __int64 *@<r9>, struct D3DCommon::DX10DeviceDesc *const, struct IDXGIAdapter *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140086a74`

## callees

- `0x14003ec14`
- `0x14003f698`
- `0x14007fef4`
- `0x140080490`
- `0x14008088c`
- `0x140080994`
- `0x140081584`
- `0x14008ab24`
- `0x14008ab88`
- `0x14011a010`

## import_xrefs

- `d3d10_1!D3D10CreateDeviceAndSwapChain1` at `0x14007ffd2`
- `d3d10_1!D3D10CreateDeviceAndSwapChain1` at `0x14007ffd2`
- `d3d10!D3D10CreateDeviceAndSwapChain` at `0x140080072`
- `d3d10!D3D10CreateDeviceAndSwapChain` at `0x140080072`

## string_xrefs

- `0x1400800bb`: `ERROR: Failed on D3D10CreateDeviceAndSwapChain: %x`
- `0x14007ffe5`: `ERROR: Failed on D3D10CreateDeviceAndSwapChain1: %x`

## pseudocode

```c
__int64 __fastcall D3DCommon::DX10Framework::CreateDevice(
        D3DCommon::DX10Framework *this,
        __int64 a2,
        struct DXGI_SWAP_CHAIN_DESC *a3,
        unsigned __int64 *a4,
        D3D10_DRIVER_TYPE *a5)
{
  unsigned __int64 *v5; // rbp
  __int64 result; // rax
  unsigned int *v8; // r9
  unsigned __int64 v9; // r14
  IDXGIAdapter *v10; // rdi
  _QWORD *v11; // r13
  HRESULT DeviceAndSwapChain1; // eax
  unsigned int *v13; // r9
  HRESULT DeviceAndSwapChain; // esi
  __int64 v15; // rcx
  _QWORD *v16; // rbp
  _QWORD *v17; // r13
  _QWORD *v18; // rsi
  __int64 (__fastcall ***v19)(_QWORD, GUID *, char *); // rcx
  int Queries; // ebp
  void (*v21)(void); // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 (*v24)(HWND, unsigned int, unsigned __int64, __int64); // rdx
  HWND v25; // r9
  __int64 (*v26)(HWND, unsigned int, unsigned __int64, __int64); // rdx
  HWND v27; // r8
  __int64 v28; // rax
  __int64 (*v29)(HWND, unsigned int, unsigned __int64, __int64); // rdx
  unsigned int *v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  IDXGIAdapter *pAdapter; // [rsp+50h] [rbp-48h] BYREF

  v5 = a4;
  pAdapter = 0;
  if ( !a5 || !a3 || !*a4 )
    return 2147942487LL;
  result = D3DCommon::DX10Framework::GetDefaultAdapterPtr(&pAdapter);
  if ( (int)result < 0 )
    return result;
  v9 = 0;
  v10 = pAdapter;
  while ( 1 )
  {
    if ( v9 >= *v5 )
    {
      ((void (__fastcall *)(IDXGIAdapter *))v10->lpVtbl->Release)(v10);
      return 2174418945LL;
    }
    D3DCommon::LogMessage((D3DCommon *)0x54, 1u, 0, v8);
    if ( a5[3 * v9] == 10 )
    {
      v16 = (_QWORD *)((char *)this + 40);
      v17 = (_QWORD *)((char *)this + 32);
      DeviceAndSwapChain = D3D10CreateDeviceAndSwapChain(
                             v10,
                             a5[3 * v9 + 1],
                             0,
                             0,
                             0x1Du,
                             a3,
                             (IDXGISwapChain **)this + 4,
                             (ID3D10Device **)this + 5);
      if ( DeviceAndSwapChain < 0 )
      {
        if ( *v16 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 16LL))(*v16);
          *v16 = 0;
        }
        if ( *v17 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 16LL))(*v17);
          *v17 = 0;
        }
        Log_Text_F(
          "base\\winsat\\d3d\\dx10base.cpp",
          425,
          "ERROR: Failed on D3D10CreateDeviceAndSwapChain: %x",
          DeviceAndSwapChain);
      }
      v5 = a4;
    }
    else
    {
      if ( a5[3 * v9] != 101 )
      {
        ((void (__fastcall *)(IDXGIAdapter *))v10->lpVtbl->Release)(v10);
        return 2147500033LL;
      }
      v11 = (_QWORD *)((char *)this + 32);
      DeviceAndSwapChain1 = D3D10CreateDeviceAndSwapChain1(
                              v10,
                              a5[3 * v9 + 1],
                              0,
                              0,
                              (D3D10_FEATURE_LEVEL1)a5[3 * v9 + 2],
                              0x20u,
                              a3,
                              (IDXGISwapChain **)this + 4,
                              (ID3D10Device1 **)this + 6);
      DeviceAndSwapChain = DeviceAndSwapChain1;
      if ( DeviceAndSwapChain1 < 0 )
      {
        Log_Text_F(
          "base\\winsat\\d3d\\dx10base.cpp",
          465,
          "ERROR: Failed on D3D10CreateDeviceAndSwapChain1: %x",
          DeviceAndSwapChain1);
        v15 = *((_QWORD *)this + 6);
        if ( v15 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          *((_QWORD *)this + 6) = 0;
        }
        if ( *v11 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
          *v11 = 0;
        }
      }
    }
    D3DCommon::LogMessage((D3DCommon *)0x52, 1u, 0, v13);
    if ( DeviceAndSwapChain >= 0 )
      break;
    ++v9;
  }
  *(_QWORD *)((char *)this + 20) = *(_QWORD *)&a5[3 * v9];
  *((D3D10_DRIVER_TYPE *)this + 7) = a5[3 * v9 + 2];
  *v5 = v9;
  v18 = (_QWORD *)((char *)this + 40);
  if ( !*((_QWORD *)this + 5) )
  {
    v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 6);
    if ( v19 )
    {
      Queries = (**v19)(v19, &IID_ID3D10Device, (char *)this + 40);
      if ( Queries < 0 )
      {
        Record_FailingHresult_w(
          "base\\winsat\\d3d\\dx10base.cpp",
          504,
          (unsigned int)Queries,
          L"Failed quering interface.",
          &qword_14012B318);
        *((_DWORD *)this + 5) = 0;
        if ( !*v18 )
        {
LABEL_30:
          v22 = *((_QWORD *)this + 6);
          if ( v22 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            *((_QWORD *)this + 6) = 0;
          }
          v23 = *((_QWORD *)this + 4);
          if ( v23 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            *((_QWORD *)this + 4) = 0;
          }
          ((void (__fastcall *)(IDXGIAdapter *))v10->lpVtbl->Release)(v10);
          return (unsigned int)Queries;
        }
        v21 = *(void (**)(void))(*(_QWORD *)*v18 + 16LL);
LABEL_29:
        v21();
        *v18 = 0;
        goto LABEL_30;
      }
    }
  }
  Queries = D3DCommon::DX10Framework::p_CreateQueries(this);
  if ( Queries < 0 )
  {
    D3DCommon::DX10Framework::p_DestroyQueries(this);
    *((_DWORD *)this + 5) = 0;
    if ( !*v18 )
      goto LABEL_30;
    v21 = *(void (**)(void))(*(_QWORD *)*v18 + 16LL);
    goto LABEL_29;
  }
  *((_DWORD *)this + 4) = 1;
  D3DCommon::DX10Framework::sm_hrWndProcResult = 0;
  D3DCommon::DX10Framework::sm_pWndProcInstance = this;
  D3DCommon::DXSetWindowProc((D3DCommon *)D3DCommon::DX10Framework::sp_StaticWndProc, v24);
  if ( *(_QWORD *)this )
  {
    Queries = (*(__int64 (__fastcall **)(_QWORD, D3DCommon::DX10Framework *, _QWORD, _QWORD))(**(_QWORD **)this + 8LL))(
                *(_QWORD *)this,
                this,
                *((_QWORD *)this + 4),
                *v18);
    if ( Queries < 0 )
    {
      D3DCommon::DXSetWindowProc(0, v26);
      D3DCommon::DX10Framework::sm_pWndProcInstance = 0;
      D3DCommon::DX10Framework::p_DestroyQueries(this);
      *((_DWORD *)this + 5) = 0;
      if ( *v18 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 16LL))(*v18);
        *((_QWORD *)this + 5) = 0;
      }
      goto LABEL_30;
    }
  }
  v27 = 0;
  v28 = *((_QWORD *)this + 1);
  if ( v28 && *(_QWORD *)(v28 + 48) )
    v27 = *(HWND *)(v28 + 48);
  D3DCommon::DXResetWindow((D3DCommon *)a3->BufferDesc.Width, a3->BufferDesc.Height, v27, v25);
  *((_BYTE *)this + 84) = 1;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4), 0, 0) < 0 )
  {
    D3DCommon::DXSetWindowProc(0, v29);
    D3DCommon::DX10Framework::sm_pWndProcInstance = 0;
    D3DCommon::DX10Framework::p_DestroyQueries(this);
    *((_DWORD *)this + 5) = 0;
    v31 = *((_QWORD *)this + 5);
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      *((_QWORD *)this + 5) = 0;
    }
    v32 = *((_QWORD *)this + 6);
    if ( v32 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      *((_QWORD *)this + 6) = 0;
    }
    v33 = *((_QWORD *)this + 4);
    if ( v33 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      *((_QWORD *)this + 4) = 0;
    }
  }
  D3DCommon::LogMessage((D3DCommon *)0x31, 1u, 0, v30);
  ((void (__fastcall *)(IDXGIAdapter *))v10->lpVtbl->Release)(v10);
  return 0;
}

```

## disassembly

```asm
0x14007fef4  mov     rax, rsp
0x14007fef7  mov     [rax+8], rbx
0x14007fefb  mov     [rax+20h], r9
0x14007feff  mov     [rax+18h], r8
0x14007ff03  push    rbp
0x14007ff04  push    rsi
0x14007ff05  push    rdi
0x14007ff06  push    r12
0x14007ff08  push    r13
0x14007ff0a  push    r14
0x14007ff0c  push    r15
0x14007ff0e  sub     rsp, 60h
0x14007ff12  mov     rbp, r9
0x14007ff15  mov     rbx, rcx
0x14007ff18  xor     r13d, r13d
0x14007ff1b  mov     [rax-48h], r13
0x14007ff1f  mov     r15, [rsp+98h+arg_20]
0x14007ff27  test    r15, r15
0x14007ff2a  jz      loc_14008038D
0x14007ff30  test    r8, r8
0x14007ff33  jz      loc_14008038D
0x14007ff39  cmp     [r9], r13
0x14007ff3c  jbe     loc_14008038D
0x14007ff42  lea     rcx, [rax-48h]; struct IDXGIAdapter **
0x14007ff46  call    ?GetDefaultAdapterPtr@DX10Framework@D3DCommon@@SAJPEAPEAUIDXGIAdapter@@@Z; D3DCommon::DX10Framework::GetDefaultAdapterPtr(IDXGIAdapter * *)
0x14007ff4b  test    eax, eax
0x14007ff4d  js      loc_140080392
0x14007ff53  mov     esi, 80004005h
0x14007ff58  mov     r14d, r13d
0x14007ff5b  mov     rdi, [rsp+98h+pAdapter]
0x14007ff60  cmp     r14, [rbp+0]
0x14007ff64  jnb     loc_1400801EA
0x14007ff6a  mov     ecx, 54h ; 'T'; this
0x14007ff6f  xor     r8d, r8d; unsigned int
0x14007ff72  lea     edx, [rcx-53h]; unsigned __int16
0x14007ff75  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x14007ff7a  lea     r12, [r14+r14*2]
0x14007ff7e  mov     rcx, rdi; pAdapter
0x14007ff81  cmp     dword ptr [r15+r12*4], 0Ah
0x14007ff86  jz      loc_140080040
0x14007ff8c  cmp     dword ptr [r15+r12*4], 65h ; 'e'
0x14007ff91  jnz     loc_1400800FA
0x14007ff97  lea     rax, [rbx+30h]
0x14007ff9b  lea     r13, [rbx+20h]
0x14007ff9f  mov     [rsp+98h+ppDevice], rax; ppDevice
0x14007ffa4  mov     [rsp+98h+ppSwapChain], r13; ppSwapChain
0x14007ffa9  mov     rax, [rsp+98h+arg_10]
0x14007ffb1  mov     [rsp+98h+pSwapChainDesc], rax; pSwapChainDesc
0x14007ffb6  mov     [rsp+98h+SDKVersion], 20h ; ' '; SDKVersion
0x14007ffbe  mov     eax, [r15+r12*4+8]
0x14007ffc3  mov     [rsp+98h+HardwareLevel], eax; HardwareLevel
0x14007ffc7  xor     r9d, r9d; Flags
0x14007ffca  xor     r8d, r8d; Software
0x14007ffcd  mov     edx, [r15+r12*4+4]; DriverType
0x14007ffd2  call    cs:__imp_D3D10CreateDeviceAndSwapChain1
0x14007ffd8  mov     esi, eax
0x14007ffda  test    eax, eax
0x14007ffdc  jns     loc_1400800DB
0x14007ffe2  mov     r9d, eax
0x14007ffe5  lea     r8, aErrorFailedOnD_0; "ERROR: Failed on D3D10CreateDeviceAndSw"...
0x14007ffec  mov     edx, 1D1h
0x14007fff1  lea     rcx, aBaseWinsatD3dD_1; "base\\winsat\\d3d\\dx10base.cpp"
0x14007fff8  call    Log_Text_F
0x14007fffd  mov     rcx, [rbx+30h]
0x140080001  test    rcx, rcx
0x140080004  jz      short loc_14008001A
0x140080006  mov     rdx, [rcx]
0x140080009  mov     rax, [rdx+10h]
0x14008000d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080012  mov     qword ptr [rbx+30h], 0
0x14008001a  mov     rcx, [r13+0]
0x14008001e  test    rcx, rcx
0x140080021  jz      loc_1400800DB
0x140080027  mov     rax, [rcx]
0x14008002a  mov     rax, [rax+10h]
0x14008002e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080033  mov     qword ptr [r13+0], 0
0x14008003b  jmp     loc_1400800DB
0x140080040  lea     rbp, [rbx+28h]
0x140080044  lea     r13, [rbx+20h]
0x140080048  mov     [rsp+98h+ppSwapChain], rbp; ppDevice
0x14008004d  mov     [rsp+98h+pSwapChainDesc], r13; ppSwapChain
0x140080052  mov     rax, [rsp+98h+arg_10]
0x14008005a  mov     qword ptr [rsp+98h+SDKVersion], rax; pSwapChainDesc
0x14008005f  mov     [rsp+98h+HardwareLevel], 1Dh; SDKVersion
0x140080067  xor     r9d, r9d; Flags
0x14008006a  xor     r8d, r8d; Software
0x14008006d  mov     edx, [r15+r12*4+4]; DriverType
0x140080072  call    cs:__imp_D3D10CreateDeviceAndSwapChain
0x140080078  mov     esi, eax
0x14008007a  test    eax, eax
0x14008007c  jns     short loc_1400800D3
0x14008007e  mov     rcx, [rbp+0]
0x140080082  test    rcx, rcx
0x140080085  jz      short loc_14008009B
0x140080087  mov     rax, [rcx]
0x14008008a  mov     rax, [rax+10h]
0x14008008e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080093  mov     qword ptr [rbp+0], 0
0x14008009b  mov     rcx, [r13+0]
0x14008009f  test    rcx, rcx
0x1400800a2  jz      short loc_1400800B8
0x1400800a4  mov     rax, [rcx]
0x1400800a7  mov     rax, [rax+10h]
0x1400800ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400800b0  mov     qword ptr [r13+0], 0
0x1400800b8  mov     r9d, esi
0x1400800bb  lea     r8, aErrorFailedOnD; "ERROR: Failed on D3D10CreateDeviceAndSw"...
0x1400800c2  mov     edx, 1A9h
0x1400800c7  lea     rcx, aBaseWinsatD3dD_1; "base\\winsat\\d3d\\dx10base.cpp"
0x1400800ce  call    Log_Text_F
0x1400800d3  mov     rbp, [rsp+98h+arg_18]
0x1400800db  mov     ecx, 52h ; 'R'; this
0x1400800e0  xor     r8d, r8d; unsigned int
0x1400800e3  lea     edx, [rcx-51h]; unsigned __int16
0x1400800e6  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x1400800eb  xor     r13d, r13d
0x1400800ee  test    esi, esi
0x1400800f0  jns     short loc_140080110
0x1400800f2  inc     r14
0x1400800f5  jmp     loc_14007FF60
0x1400800fa  mov     rax, [rdi]
0x1400800fd  mov     rax, [rax+10h]
0x140080101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080106  mov     eax, 80004001h
0x14008010b  jmp     loc_140080392
0x140080110  movsd   xmm0, qword ptr [r15+r12*4]
0x140080116  movsd   qword ptr [rbx+14h], xmm0
0x14008011b  mov     eax, [r15+r12*4+8]
0x140080120  mov     [rbx+1Ch], eax
0x140080123  mov     [rbp+0], r14
0x140080127  lea     rsi, [rbx+28h]
0x14008012b  cmp     [rsi], r13
0x14008012e  jnz     loc_14008020B
0x140080134  mov     rcx, [rbx+30h]
0x140080138  test    rcx, rcx
0x14008013b  jz      loc_14008020B
0x140080141  mov     rax, [rcx]
0x140080144  mov     r8, rsi
0x140080147  lea     rdx, IID_ID3D10Device
0x14008014e  mov     rax, [rax]
0x140080151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080156  mov     ebp, eax
0x140080158  test    eax, eax
0x14008015a  jns     loc_14008020B
0x140080160  lea     rax, qword_14012B318
0x140080167  mov     qword ptr [rsp+98h+HardwareLevel], rax
0x14008016c  lea     r9, aFailedQueringI; "Failed quering interface."
0x140080173  mov     r8d, ebp
0x140080176  mov     edx, 1F8h
0x14008017b  lea     rcx, aBaseWinsatD3dD_1; "base\\winsat\\d3d\\dx10base.cpp"
0x140080182  call    Record_FailingHresult_w
0x140080187  mov     [rbx+14h], r13d
0x14008018b  mov     rcx, [rsi]
0x14008018e  test    rcx, rcx
0x140080191  jz      short loc_1400801A2
0x140080193  mov     rax, [rcx]
0x140080196  mov     rax, [rax+10h]
0x14008019a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008019f  mov     [rsi], r13
0x1400801a2  mov     rcx, [rbx+30h]
0x1400801a6  test    rcx, rcx
0x1400801a9  jz      short loc_1400801BB
0x1400801ab  mov     rax, [rcx]
0x1400801ae  mov     rax, [rax+10h]
0x1400801b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400801b7  mov     [rbx+30h], r13
0x1400801bb  mov     rcx, [rbx+20h]
0x1400801bf  test    rcx, rcx
0x1400801c2  jz      short loc_1400801D4
0x1400801c4  mov     rax, [rcx]
0x1400801c7  mov     rax, [rax+10h]
0x1400801cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400801d0  mov     [rbx+20h], r13
0x1400801d4  mov     rax, [rdi]
0x1400801d7  mov     rcx, rdi
0x1400801da  mov     rax, [rax+10h]
0x1400801de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400801e3  mov     eax, ebp
0x1400801e5  jmp     loc_140080392
0x1400801ea  test    esi, esi
0x1400801ec  jns     loc_140080127
0x1400801f2  mov     rax, [rdi]
0x1400801f5  mov     rcx, rdi
0x1400801f8  mov     rax, [rax+10h]
0x1400801fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080201  mov     eax, 819B0001h
0x140080206  jmp     loc_140080392
0x14008020b  mov     rcx, rbx; this
0x14008020e  call    ?p_CreateQueries@DX10Framework@D3DCommon@@AEAAJXZ; D3DCommon::DX10Framework::p_CreateQueries(void)
0x140080213  mov     ebp, eax
0x140080215  test    eax, eax
0x140080217  jns     short loc_14008023D
0x140080219  mov     rcx, rbx; this
0x14008021c  call    ?p_DestroyQueries@DX10Framework@D3DCommon@@AEAAXXZ; D3DCommon::DX10Framework::p_DestroyQueries(void)
0x140080221  mov     [rbx+14h], r13d
0x140080225  mov     rcx, [rsi]
0x140080228  test    rcx, rcx
0x14008022b  jz      loc_1400801A2
0x140080231  mov     rdx, [rcx]
0x140080234  mov     rax, [rdx+10h]
0x140080238  jmp     loc_14008019A
0x14008023d  mov     dword ptr [rbx+10h], 1
0x140080244  mov     cs:?sm_hrWndProcResult@DX10Framework@D3DCommon@@0JA, r13d; long D3DCommon::DX10Framework::sm_hrWndProcResult
0x14008024b  mov     cs:?sm_pWndProcInstance@DX10Framework@D3DCommon@@0PEAV12@EA, rbx; D3DCommon::DX10Framework * D3DCommon::DX10Framework::sm_pWndProcInstance
0x140080252  lea     rcx, ?sp_StaticWndProc@DX10Framework@D3DCommon@@CA_JPEAUHWND__@@I_K_J@Z; this
0x140080259  call    ?DXSetWindowProc@D3DCommon@@YAXP6A_JPEAUHWND__@@I_K_J@Z@Z; D3DCommon::DXSetWindowProc(__int64 (*)(HWND__ *,uint,unsigned __int64,__int64))
0x14008025e  mov     rcx, [rbx]
0x140080261  test    rcx, rcx
0x140080264  jz      short loc_1400802BD
0x140080266  mov     rax, [rcx]
0x140080269  mov     r9, [rsi]
0x14008026c  mov     r8, [rbx+20h]
0x140080270  mov     rdx, rbx
0x140080273  mov     rax, [rax+8]
0x140080277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008027c  mov     ebp, eax
0x14008027e  test    eax, eax
0x140080280  jns     short loc_1400802BD
0x140080282  xor     ecx, ecx; this
0x140080284  call    ?DXSetWindowProc@D3DCommon@@YAXP6A_JPEAUHWND__@@I_K_J@Z@Z; D3DCommon::DXSetWindowProc(__int64 (*)(HWND__ *,uint,unsigned __int64,__int64))
0x140080289  mov     cs:?sm_pWndProcInstance@DX10Framework@D3DCommon@@0PEAV12@EA, r13; D3DCommon::DX10Framework * D3DCommon::DX10Framework::sm_pWndProcInstance
0x140080290  mov     rcx, rbx; this
0x140080293  call    ?p_DestroyQueries@DX10Framework@D3DCommon@@AEAAXXZ; D3DCommon::DX10Framework::p_DestroyQueries(void)
0x140080298  mov     [rbx+14h], r13d
0x14008029c  mov     rcx, [rsi]
0x14008029f  test    rcx, rcx
0x1400802a2  jz      loc_1400801A2
0x1400802a8  mov     rdx, [rcx]
0x1400802ab  mov     rax, [rdx+10h]
0x1400802af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400802b4  mov     [rbx+28h], r13
0x1400802b8  jmp     loc_1400801A2
0x1400802bd  mov     r8, r13
0x1400802c0  mov     rax, [rbx+8]
0x1400802c4  test    rax, rax
0x1400802c7  jz      short loc_1400802D2
0x1400802c9  cmp     [rax+30h], r13
0x1400802cd  cmovnz  r8, [rax+30h]; hWndInsertAfter
0x1400802d2  mov     r12, [rsp+98h+arg_10]
0x1400802da  mov     edx, [r12+4]; cy
0x1400802df  mov     ecx, [r12]; this
0x1400802e3  call    ?DXResetWindow@D3DCommon@@YAXIIPEAUHWND__@@@Z; D3DCommon::DXResetWindow(uint,uint,HWND__ *)
0x1400802e8  mov     byte ptr [rbx+54h], 1
0x1400802ec  mov     rcx, [rbx+20h]
0x1400802f0  mov     rax, [rcx]
0x1400802f3  xor     r8d, r8d
0x1400802f6  xor     edx, edx
0x1400802f8  mov     rax, [rax+40h]
0x1400802fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080301  test    eax, eax
0x140080303  jns     short loc_14008036A
0x140080305  xor     ecx, ecx; this
0x140080307  call    ?DXSetWindowProc@D3DCommon@@YAXP6A_JPEAUHWND__@@I_K_J@Z@Z; D3DCommon::DXSetWindowProc(__int64 (*)(HWND__ *,uint,unsigned __int64,__int64))
0x14008030c  mov     cs:?sm_pWndProcInstance@DX10Framework@D3DCommon@@0PEAV12@EA, r13; D3DCommon::DX10Framework * D3DCommon::DX10Framework::sm_pWndProcInstance
0x140080313  mov     rcx, rbx; this
0x140080316  call    ?p_DestroyQueries@DX10Framework@D3DCommon@@AEAAXXZ; D3DCommon::DX10Framework::p_DestroyQueries(void)
0x14008031b  mov     [rbx+14h], r13d
0x14008031f  mov     rcx, [rbx+28h]
0x140080323  test    rcx, rcx
0x140080326  jz      short loc_140080338
0x140080328  mov     rax, [rcx]
0x14008032b  mov     rax, [rax+10h]
0x14008032f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080334  mov     [rbx+28h], r13
0x140080338  mov     rcx, [rbx+30h]
0x14008033c  test    rcx, rcx
0x14008033f  jz      short loc_140080351
0x140080341  mov     rax, [rcx]
0x140080344  mov     rax, [rax+10h]
0x140080348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008034d  mov     [rbx+30h], r13
0x140080351  mov     rcx, [rbx+20h]
0x140080355  test    rcx, rcx
0x140080358  jz      short loc_14008036A
0x14008035a  mov     rax, [rcx]
0x14008035d  mov     rax, [rax+10h]
0x140080361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080366  mov     [rbx+20h], r13
0x14008036a  mov     ecx, 31h ; '1'; this
0x14008036f  xor     r8d, r8d; unsigned int
0x140080372  lea     edx, [rcx-30h]; unsigned __int16
0x140080375  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x14008037a  mov     rax, [rdi]
0x14008037d  mov     rcx, rdi
0x140080380  mov     rax, [rax+10h]
0x140080384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080389  xor     eax, eax
0x14008038b  jmp     short loc_140080392
0x14008038d  mov     eax, 80070057h
0x140080392  mov     rbx, [rsp+98h+arg_0]
0x14008039a  add     rsp, 60h
0x14008039e  pop     r15
0x1400803a0  pop     r14
0x1400803a2  pop     r13
0x1400803a4  pop     r12
0x1400803a6  pop     rdi
0x1400803a7  pop     rsi
0x1400803a8  pop     rbp
0x1400803a9  retn
  ... truncated ...
```
