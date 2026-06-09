# CUdpHandler::QueryOpenUdpEndpoints(CRegUdpEndpoint *)

- ea: `0x180002c24`
- end: `0x180003159`
- name: `?QueryOpenUdpEndpoints@CUdpHandler@@AEAAKPEAVCRegUdpEndpoint@@@Z`
- size: `1333`
- prototype: `__int64 __fastcall(CUdpHandler *this, struct CRegUdpEndpoint *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ab0`
- `0x180003680`

## callees

- `0x18000195c`
- `0x180001984`
- `0x180002c24`
- `0x180003944`
- `0x180010048`
- `0x180014a60`
- `0x180015660`
- `0x180018cdc`
- `0x18001a474`
- `0x18001c112`
- `0x18001c11e`
- `0x18001c12a`
- `0x18001d010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002eaf`
- `KERNEL32!InitializeCriticalSection` at `0x180002eca`
- `KERNEL32!InitializeCriticalSection` at `0x180002ef0`
- `KERNEL32!InitializeCriticalSection` at `0x180002f39`
- `KERNEL32!InitializeCriticalSection` at `0x180002eaf`
- `KERNEL32!InitializeCriticalSection` at `0x180002eca`
- `KERNEL32!InitializeCriticalSection` at `0x180002ef0`
- `KERNEL32!InitializeCriticalSection` at `0x180002f39`
- `KERNEL32!LeaveCriticalSection` at `0x1800030bc`
- `KERNEL32!LeaveCriticalSection` at `0x1800030bc`
- `KERNEL32!EnterCriticalSection` at `0x180003053`
- `KERNEL32!EnterCriticalSection` at `0x180003053`
- `KERNEL32!InitializeSListHead` at `0x180002f1a`
- `KERNEL32!InitializeSListHead` at `0x180002f1a`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180002d6c`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180002d83`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180002da0`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000312f`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180002d6c`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180002d83`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180002da0`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000312f`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180002fe3`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180002fe3`
- `WdsServerCommonLib!??0CCompPort@@QEAA@XZ` at `0x180002edd`
- `WdsServerCommonLib!??0CCompPort@@QEAA@XZ` at `0x180002edd`

## pseudocode

```c
__int64 __fastcall CUdpHandler::QueryOpenUdpEndpoints(CUdpHandler *this, struct CRegUdpEndpoint *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  unsigned int *v4; // rbp
  unsigned int v5; // r15d
  unsigned int *v6; // rdi
  unsigned int v7; // r14d
  unsigned int InterfacesAlloc; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  _DWORD *v11; // r13
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r12
  unsigned __int64 v15; // rax
  _DWORD *v16; // rbp
  unsigned int v17; // r14d
  char *v18; // rcx
  unsigned int *v19; // r12
  _BYTE *v20; // rdx
  __int64 v21; // rax
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int64 v30; // rax
  size_t v31; // r8
  char *v32; // rax
  char *v33; // rdi
  unsigned int v34; // eax
  __int64 v35; // rdx
  unsigned int v36; // edx
  int v37; // eax
  unsigned int v39; // [rsp+30h] [rbp-468h]
  void *Src; // [rsp+38h] [rbp-460h] BYREF
  _BYTE v41[16]; // [rsp+40h] [rbp-458h] BYREF
  char v42[16]; // [rsp+50h] [rbp-448h] BYREF
  int v43; // [rsp+60h] [rbp-438h]
  unsigned int v45; // [rsp+4B0h] [rbp+18h] BYREF
  int v46; // [rsp+4B8h] [rbp+20h]

  v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 11);
  v39 = 0;
  v4 = 0;
  v46 = 0;
  v5 = 0;
  Src = 0;
  v6 = 0;
  v45 = 0;
  v7 = 0;
  InterfacesAlloc = CInterfaceMonitor::GetInterfacesAlloc(v2, (struct tagWDS_INTERFACE_INFO **)&Src, &v45);
  v11 = Src;
  v12 = InterfacesAlloc;
  if ( InterfacesAlloc )
  {
    ElValidateWin32_6(InterfacesAlloc, v9, v10, 561);
  }
  else
  {
    v14 = v45;
    v15 = 48LL * v45;
    if ( !is_mul_ok(v45, 0x30u) )
      v15 = -1;
    v6 = (unsigned int *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      if ( !v45 )
        goto LABEL_19;
      v16 = v11;
      do
      {
        if ( (v16[4] != 4 || *((_DWORD *)a2 + 516))
          && (v16[4] != 16 || *((_DWORD *)a2 + 515))
          && !CRegUdpEndpoint::Find(a2, (struct tagWDS_INTERFACE_INFO *)v16, 0)
          && !(*(unsigned int (__fastcall **)(struct CRegUdpEndpoint *, _DWORD *))(*(_QWORD *)a2 + 32LL))(a2, v16) )
        {
          memmove_0(&v6[12 * v7++], v16, 0x30u);
        }
        v16 += 12;
        --v14;
      }
      while ( v14 );
      if ( v7 )
      {
        v4 = v6;
        v5 = v7;
      }
      else
      {
LABEL_19:
        v4 = 0;
        v5 = 0;
        WdsPrivateHpFree(v6);
        v6 = 0;
      }
    }
    else
    {
      v12 = 8;
    }
  }
  if ( v11 )
  {
    WdsPrivateHpFree(v11);
    Src = 0;
  }
  if ( v6 && v12 )
    WdsPrivateHpFree(v6);
  if ( !(unsigned int)ElValidateWin32(v12, v13, "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp", 520) )
  {
    v17 = 0;
    if ( v5 )
    {
      v18 = (char *)a2 + 72;
      v19 = v4 + 4;
      do
      {
        v20 = v41;
        v21 = 8;
        do
        {
          v22 = *(_OWORD *)v18;
          v23 = *((_OWORD *)v18 + 1);
          v18 += 128;
          *(_OWORD *)v20 = v22;
          v24 = *((_OWORD *)v18 - 6);
          *((_OWORD *)v20 + 1) = v23;
          v25 = *((_OWORD *)v18 - 5);
          *((_OWORD *)v20 + 2) = v24;
          v26 = *((_OWORD *)v18 - 4);
          *((_OWORD *)v20 + 3) = v25;
          v27 = *((_OWORD *)v18 - 3);
          *((_OWORD *)v20 + 4) = v26;
          v28 = *((_OWORD *)v18 - 2);
          *((_OWORD *)v20 + 5) = v27;
          v29 = *((_OWORD *)v18 - 1);
          *((_OWORD *)v20 + 6) = v28;
          v20 += 128;
          *((_OWORD *)v20 - 1) = v29;
          --v21;
        }
        while ( v21 );
        v30 = *((_QWORD *)v18 + 2);
        v31 = *v19;
        *(_OWORD *)v20 = *(_OWORD *)v18;
        *((_QWORD *)v20 + 2) = v30;
        *((_DWORD *)v20 + 6) = *((_DWORD *)v18 + 6);
        v43 = v31;
        memcpy_0(v42, &v4[12 * v17], v31);
        v32 = (char *)operator new(0x910u, (const struct std::nothrow_t *)&std::nothrow);
        v33 = v32;
        if ( !v32 )
        {
          v12 = 8;
          goto LABEL_42;
        }
        *((_DWORD *)v32 + 2) = 1;
        *(_QWORD *)v32 = &CUdpEndpoint::`vftable'{for `CRefCount'};
        *((_QWORD *)v32 + 2) = &CUdpEndpoint::`vftable'{for `IMulticastCallback'};
        InitializeCriticalSection((LPCRITICAL_SECTION)(v32 + 24));
        *((_QWORD *)v33 + 12) = &CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::`vftable';
        InitializeCriticalSection((LPCRITICAL_SECTION)(v33 + 104));
        CCompPort::CCompPort((CCompPort *)(v33 + 384));
        InitializeCriticalSection((LPCRITICAL_SECTION)(v33 + 472));
        *((_QWORD *)v33 + 57) = 0;
        *((_QWORD *)v33 + 58) = 0;
        *((_DWORD *)v33 + 128) = 0;
        InitializeSListHead((PSLIST_HEADER)v33 + 33);
        *((_DWORD *)v33 + 136) = 0;
        *((_QWORD *)v33 + 70) = 0;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v33 + 592));
        *((_DWORD *)v33 + 158) = 0;
        *((_QWORD *)v33 + 80) = 0;
        *((_QWORD *)v33 + 81) = 0;
        *((_QWORD *)v33 + 82) = 0;
        *((_QWORD *)v33 + 83) = 0;
        *((_QWORD *)v33 + 84) = 0;
        *((_DWORD *)v33 + 170) = 0;
        *((_QWORD *)v33 + 86) = 0;
        *((_QWORD *)v33 + 87) = 0;
        *((_DWORD *)v33 + 176) = 0;
        *((_DWORD *)v33 + 144) = 0;
        *((_QWORD *)v33 + 73) = 0;
        *((_QWORD *)v33 + 19) = -1;
        *((_QWORD *)v33 + 18) = 0;
        *((_QWORD *)v33 + 20) = 0;
        *((_DWORD *)v33 + 130) = 0;
        *((_DWORD *)v33 + 131) = 0;
        memset_0(v33 + 168, 0, 0xD8u);
        *((_QWORD *)v33 + 8) = this;
        *((_QWORD *)v33 + 288) = 0;
        *((_QWORD *)v33 + 289) = 0;
        CTrace::Trace((CTrace *)qword_180039310, 0x10000u, L"UpdEndpoint::UdpEndpoint = %p\n", v33);
        *((_QWORD *)v33 + 9) = 0;
        *((_QWORD *)v33 + 10) = 0;
        *((_DWORD *)v33 + 234) = 0;
        *((_WORD *)v33 + 1020) = 0;
        *((_DWORD *)v33 + 22) = 0;
        *((_DWORD *)v33 + 574) = 0;
        v34 = CUdpEndpoint::Initialize(
                (CUdpEndpoint *)v33,
                *((struct CMulticastHandler **)this + 12),
                a2,
                (struct tagWDS_ENDPOINT *)v41,
                (struct tagWDS_INTERFACE_INFO *)&v4[12 * v17]);
        v12 = v34;
        if ( v34 == 50
          || (unsigned int)ElValidateWin32(v34, v35, "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp", 559) )
        {
          CUdpEndpoint::Shutdown((CUdpEndpoint *)v33);
          (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 8LL))(v33);
          v39 = v12;
          v36 = v12;
          v12 = 0;
          v37 = v46;
        }
        else
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 16));
          if ( *((_QWORD *)a2 + 227) )
          {
            *((_QWORD *)v33 + 288) = 0;
            *((_QWORD *)v33 + 289) = *((_QWORD *)a2 + 228);
            *(_QWORD *)(*((_QWORD *)a2 + 228) + 2304LL) = v33;
            *((_QWORD *)a2 + 228) = v33;
          }
          else
          {
            *((_QWORD *)a2 + 228) = v33;
            *((_QWORD *)a2 + 227) = v33;
            *((_QWORD *)v33 + 288) = 0;
            *((_QWORD *)v33 + 289) = 0;
          }
          ++*((_DWORD *)a2 + 459);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 16));
          v36 = v39;
          v37 = ++v46;
        }
        ++v17;
        v18 = (char *)a2 + 72;
        v19 += 12;
      }
      while ( v17 < v5 );
      if ( !v37 )
        v12 = v36;
    }
  }
LABEL_42:
  if ( v4 )
    WdsPrivateHpFree(v4);
  return v12;
}

```

## disassembly

```asm
0x180002c24  mov     rax, rsp
0x180002c27  mov     [rax+10h], rbx
0x180002c2b  mov     [rax+8], rcx
0x180002c2f  push    rbp
0x180002c30  push    rsi
0x180002c31  push    rdi
0x180002c32  push    r12
0x180002c34  push    r13
0x180002c36  push    r14
0x180002c38  push    r15
0x180002c3a  sub     rsp, 460h
0x180002c41  mov     rcx, [rcx+58h]; lpCriticalSection
0x180002c45  lea     r8, [rax+18h]; unsigned int *
0x180002c49  xor     r12d, r12d
0x180002c4c  mov     rsi, rdx
0x180002c4f  lea     rdx, [rsp+498h+Src]; struct tagWDS_INTERFACE_INFO **
0x180002c54  mov     [rsp+498h+var_468], r12d
0x180002c59  mov     ebp, r12d
0x180002c5c  mov     [rsp+498h+arg_18], r12d
0x180002c64  mov     r15d, r12d
0x180002c67  mov     [rsp+498h+Src], r12
0x180002c6c  mov     edi, r12d
0x180002c6f  mov     [rax+18h], r12d
0x180002c73  mov     r14d, r12d
0x180002c76  call    ?GetInterfacesAlloc@CInterfaceMonitor@@QEAAKPEAPEAUtagWDS_INTERFACE_INFO@@PEAK@Z; CInterfaceMonitor::GetInterfacesAlloc(tagWDS_INTERFACE_INFO * *,ulong *)
0x180002c7b  mov     r13, [rsp+498h+Src]
0x180002c80  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002c84  mov     ebx, eax
0x180002c86  test    eax, eax
0x180002c88  jz      short loc_180002C9C
0x180002c8a  mov     r9d, 231h
0x180002c90  mov     ecx, eax
0x180002c92  call    ElValidateWin32_6
0x180002c97  jmp     loc_180002D7B
0x180002c9c  mov     r12d, [rsp+498h+arg_10]
0x180002ca4  mov     eax, 30h ; '0'
0x180002ca9  mul     r12
0x180002cac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002cb3  cmovo   rax, rcx
0x180002cb7  mov     rcx, rax; unsigned __int64
0x180002cba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002cbf  mov     rdi, rax
0x180002cc2  test    rax, rax
0x180002cc5  jnz     short loc_180002CD2
0x180002cc7  lea     ebx, [rax+8]
0x180002cca  xor     r12d, r12d
0x180002ccd  jmp     loc_180002D7B
0x180002cd2  cmp     [rsp+498h+arg_10], r15d
0x180002cda  jbe     loc_180002D60
0x180002ce0  mov     rbp, r13
0x180002ce3  cmp     dword ptr [rbp+10h], 4
0x180002ce7  jnz     short loc_180002CF2
0x180002ce9  cmp     [rsi+810h], r15d
0x180002cf0  jz      short loc_180002D49
0x180002cf2  cmp     dword ptr [rbp+10h], 10h
0x180002cf6  jnz     short loc_180002D01
0x180002cf8  cmp     [rsi+80Ch], r15d
0x180002cff  jz      short loc_180002D49
0x180002d01  xor     r8d, r8d; int
0x180002d04  mov     rdx, rbp; struct tagWDS_INTERFACE_INFO *
0x180002d07  mov     rcx, rsi; this
0x180002d0a  call    ?Find@CRegUdpEndpoint@@QEAAPEAVCUdpEndpoint@@PEAUtagWDS_INTERFACE_INFO@@H@Z; CRegUdpEndpoint::Find(tagWDS_INTERFACE_INFO *,int)
0x180002d0f  test    rax, rax
0x180002d12  jnz     short loc_180002D49
0x180002d14  mov     rax, [rsi]
0x180002d17  mov     rdx, rbp
0x180002d1a  mov     rcx, rsi
0x180002d1d  mov     rax, [rax+20h]
0x180002d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d26  test    eax, eax
0x180002d28  jnz     short loc_180002D49
0x180002d2a  mov     eax, r14d
0x180002d2d  mov     r8d, 30h ; '0'; Size
0x180002d33  mov     rdx, rbp; Src
0x180002d36  lea     rcx, [rax+rax*2]
0x180002d3a  shl     rcx, 4
0x180002d3e  add     rcx, rdi; void *
0x180002d41  call    memmove_0
0x180002d46  inc     r14d
0x180002d49  add     rbp, 30h ; '0'
0x180002d4d  sub     r12, 1
0x180002d51  jnz     short loc_180002CE3
0x180002d53  test    r14d, r14d
0x180002d56  jz      short loc_180002D63
0x180002d58  mov     rbp, rdi
0x180002d5b  mov     r15d, r14d
0x180002d5e  jmp     short loc_180002D7B
0x180002d60  xor     r12d, r12d
0x180002d63  mov     rcx, rdi
0x180002d66  mov     rbp, r12
0x180002d69  mov     r15d, r12d
0x180002d6c  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180002d73  nop     dword ptr [rax+rax+00h]
0x180002d78  mov     rdi, r12
0x180002d7b  test    r13, r13
0x180002d7e  jz      short loc_180002D94
0x180002d80  mov     rcx, r13
0x180002d83  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180002d8a  nop     dword ptr [rax+rax+00h]
0x180002d8f  mov     [rsp+498h+Src], r12
0x180002d94  test    rdi, rdi
0x180002d97  jz      short loc_180002DAC
0x180002d99  test    ebx, ebx
0x180002d9b  jz      short loc_180002DAC
0x180002d9d  mov     rcx, rdi
0x180002da0  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180002da7  nop     dword ptr [rax+rax+00h]
0x180002dac  mov     r9d, 208h
0x180002db2  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180002db9  mov     ecx, ebx
0x180002dbb  call    ElValidateWin32
0x180002dc0  test    eax, eax
0x180002dc2  jnz     loc_180003127
0x180002dc8  mov     r14d, r12d
0x180002dcb  test    r15d, r15d
0x180002dce  jz      loc_180003127
0x180002dd4  lea     rcx, [rsi+48h]
0x180002dd8  lea     r12, [rbp+10h]
0x180002ddc  lea     rdx, [rsp+498h+var_458]
0x180002de1  mov     eax, 8
0x180002de6  movups  xmm0, xmmword ptr [rcx]
0x180002de9  movups  xmm1, xmmword ptr [rcx+10h]
0x180002ded  lea     rcx, [rcx+80h]
0x180002df4  movups  xmmword ptr [rdx], xmm0
0x180002df7  movups  xmm0, xmmword ptr [rcx-60h]
0x180002dfb  movups  xmmword ptr [rdx+10h], xmm1
0x180002dff  movups  xmm1, xmmword ptr [rcx-50h]
0x180002e03  movups  xmmword ptr [rdx+20h], xmm0
0x180002e07  movups  xmm0, xmmword ptr [rcx-40h]
0x180002e0b  movups  xmmword ptr [rdx+30h], xmm1
0x180002e0f  movups  xmm1, xmmword ptr [rcx-30h]
0x180002e13  movups  xmmword ptr [rdx+40h], xmm0
0x180002e17  movups  xmm0, xmmword ptr [rcx-20h]
0x180002e1b  movups  xmmword ptr [rdx+50h], xmm1
0x180002e1f  movups  xmm1, xmmword ptr [rcx-10h]
0x180002e23  movups  xmmword ptr [rdx+60h], xmm0
0x180002e27  lea     rdx, [rdx+80h]
0x180002e2e  movups  xmmword ptr [rdx-10h], xmm1
0x180002e32  sub     rax, 1
0x180002e36  jnz     short loc_180002DE6
0x180002e38  mov     rax, [rcx+10h]
0x180002e3c  movups  xmm0, xmmword ptr [rcx]
0x180002e3f  mov     r8d, [r12]; Size
0x180002e43  movups  xmmword ptr [rdx], xmm0
0x180002e46  mov     [rdx+10h], rax
0x180002e4a  mov     eax, [rcx+18h]
0x180002e4d  lea     rcx, [rsp+498h+var_448]; void *
0x180002e52  mov     [rdx+18h], eax
0x180002e55  mov     eax, r14d
0x180002e58  mov     [rsp+498h+var_438], r8d
0x180002e5d  lea     r13, [rax+rax*2]
0x180002e61  shl     r13, 4
0x180002e65  add     r13, rbp
0x180002e68  mov     rdx, r13; Src
0x180002e6b  call    memcpy_0
0x180002e70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002e77  mov     ecx, 910h; unsigned __int64
0x180002e7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002e81  xor     ebx, ebx
0x180002e83  mov     rdi, rax
0x180002e86  test    rax, rax
0x180002e89  jz      loc_180003122
0x180002e8f  mov     dword ptr [rax+8], 1
0x180002e96  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002e9a  lea     rax, ??_7CUdpEndpoint@@6BCRefCount@@@; const CUdpEndpoint::`vftable'{for `CRefCount'}
0x180002ea1  mov     [rdi], rax
0x180002ea4  lea     rax, ??_7CUdpEndpoint@@6BIMulticastCallback@@@; const CUdpEndpoint::`vftable'{for `IMulticastCallback'}
0x180002eab  mov     [rdi+10h], rax
0x180002eaf  call    cs:__imp_InitializeCriticalSection
0x180002eb6  nop     dword ptr [rax+rax+00h]
0x180002ebb  lea     rax, ??_7?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@6B@; const CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::`vftable'
0x180002ec2  lea     rcx, [rdi+68h]; lpCriticalSection
0x180002ec6  mov     [rdi+60h], rax
0x180002eca  call    cs:__imp_InitializeCriticalSection
0x180002ed1  nop     dword ptr [rax+rax+00h]
0x180002ed6  lea     rcx, [rdi+180h]
0x180002edd  call    cs:__imp_??0CCompPort@@QEAA@XZ; CCompPort::CCompPort(void)
0x180002ee4  nop     dword ptr [rax+rax+00h]
0x180002ee9  lea     rcx, [rdi+1D8h]; lpCriticalSection
0x180002ef0  call    cs:__imp_InitializeCriticalSection
0x180002ef7  nop     dword ptr [rax+rax+00h]
0x180002efc  mov     [rdi+1C8h], rbx
0x180002f03  mov     [rdi+1D0h], rbx
0x180002f0a  mov     [rdi+200h], ebx
0x180002f10  lea     rbx, [rdi+210h]
0x180002f17  mov     rcx, rbx; ListHead
0x180002f1a  call    cs:__imp_InitializeSListHead
0x180002f21  nop     dword ptr [rax+rax+00h]
0x180002f26  xor     eax, eax
0x180002f28  mov     [rbx+10h], eax
0x180002f2b  mov     [rbx+20h], rax
0x180002f2f  lea     rbx, [rdi+250h]
0x180002f36  mov     rcx, rbx; lpCriticalSection
0x180002f39  call    cs:__imp_InitializeCriticalSection
0x180002f40  nop     dword ptr [rax+rax+00h]
0x180002f45  xor     ecx, ecx
0x180002f47  xor     eax, eax
0x180002f49  mov     [rbx+28h], ecx
0x180002f4c  xor     edx, edx; Val
0x180002f4e  mov     [rbx+30h], rcx
0x180002f52  mov     r8d, 0D8h; Size
0x180002f58  mov     [rbx+38h], rcx
0x180002f5c  mov     [rbx+40h], rcx
0x180002f60  mov     [rbx+48h], rax
0x180002f64  mov     [rbx+50h], rax
0x180002f68  mov     [rbx+58h], ecx
0x180002f6b  mov     [rbx+60h], rcx
0x180002f6f  mov     [rbx+68h], rcx
0x180002f73  mov     [rbx+70h], ecx
0x180002f76  mov     [rdi+240h], ecx
0x180002f7c  mov     [rdi+248h], rcx
0x180002f83  or      qword ptr [rdi+98h], 0FFFFFFFFFFFFFFFFh
0x180002f8b  mov     [rdi+90h], rcx
0x180002f92  mov     [rdi+0A0h], rcx
0x180002f99  mov     [rdi+208h], ecx
0x180002f9f  mov     [rdi+20Ch], ecx
0x180002fa5  lea     rcx, [rdi+0A8h]; void *
0x180002fac  call    memset_0
0x180002fb1  mov     rbx, [rsp+498h+arg_0]
0x180002fb9  lea     r8, aUpdendpointUdp; "UpdEndpoint::UdpEndpoint = %p\n"
0x180002fc0  xor     eax, eax
0x180002fc2  mov     [rdi+40h], rbx
0x180002fc6  mov     r9, rdi
0x180002fc9  mov     [rdi+900h], rax
0x180002fd0  mov     edx, 10000h
0x180002fd5  mov     [rdi+908h], rax
0x180002fdc  lea     rcx, qword_180039310
0x180002fe3  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180002fea  nop     dword ptr [rax+rax+00h]
0x180002fef  xor     eax, eax
0x180002ff1  mov     [rsp+498h+var_478], r13; struct tagWDS_INTERFACE_INFO *
0x180002ff6  mov     [rdi+48h], rax
0x180002ffa  lea     r9, [rsp+498h+var_458]; struct tagWDS_ENDPOINT *
0x180002fff  mov     [rdi+50h], rax
0x180003003  mov     r8, rsi; struct CRegUdpEndpoint *
0x180003006  mov     [rdi+3A8h], eax
0x18000300c  mov     rcx, rdi; this
0x18000300f  mov     [rdi+7F8h], ax
0x180003016  mov     [rdi+58h], eax
0x180003019  mov     [rdi+8F8h], eax
0x18000301f  mov     rdx, [rbx+60h]; struct CMulticastHandler *
0x180003023  call    ?Initialize@CUdpEndpoint@@QEAAKPEAVCMulticastHandler@@PEAVCRegUdpEndpoint@@PEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@@Z; CUdpEndpoint::Initialize(CMulticastHandler *,CRegUdpEndpoint *,tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *)
0x180003028  mov     ebx, eax
0x18000302a  cmp     eax, 32h ; '2'
0x18000302d  jz      loc_1800030DE
0x180003033  mov     r9d, 22Fh
0x180003039  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180003040  mov     ecx, eax
0x180003042  call    ElValidateWin32
0x180003047  test    eax, eax
0x180003049  jnz     loc_1800030DE
0x18000304f  lea     rcx, [rsi+10h]; lpCriticalSection
0x180003053  call    cs:__imp_EnterCriticalSection
0x18000305a  nop     dword ptr [rax+rax+00h]
0x18000305f  xor     eax, eax
0x180003061  cmp     [rsi+718h], rax
0x180003068  jnz     short loc_180003088
0x18000306a  mov     [rsi+720h], rdi
0x180003071  mov     [rsi+718h], rdi
0x180003078  mov     [rdi+900h], rax
0x18000307f  mov     [rdi+908h], rax
0x180003086  jmp     short loc_1800030B2
0x180003088  mov     [rdi+900h], rax
0x18000308f  mov     rax, [rsi+720h]
0x180003096  mov     [rdi+908h], rax
0x18000309d  mov     rax, [rsi+720h]
0x1800030a4  mov     [rax+900h], rdi
0x1800030ab  mov     [rsi+720h], rdi
0x1800030b2  inc     dword ptr [rsi+72Ch]
0x1800030b8  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800030bc  call    cs:__imp_LeaveCriticalSection
0x1800030c3  nop     dword ptr [rax+rax+00h]
0x1800030c8  mov     eax, [rsp+498h+arg_18]
0x1800030cf  mov     edx, [rsp+498h+var_468]
0x1800030d3  inc     eax
0x1800030d5  mov     [rsp+498h+arg_18], eax
0x1800030dc  jmp     short loc_180003106
0x1800030de  mov     rcx, rdi; this
0x1800030e1  call    ?Shutdown@CUdpEndpoint@@QEAAKXZ; CUdpEndpoint::Shutdown(void)
0x1800030e6  mov     rax, [rdi]
0x1800030e9  mov     rcx, rdi
0x1800030ec  mov     rax, [rax+8]
0x1800030f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f5  xor     eax, eax
0x1800030f7  mov     [rsp+498h+var_468], ebx
0x1800030fb  mov     edx, ebx
0x1800030fd  mov     ebx, eax
0x1800030ff  mov     eax, [rsp+498h+arg_18]
0x180003106  inc     r14d
0x180003109  lea     rcx, [rsi+48h]
0x18000310d  add     r12, 30h ; '0'
0x180003111  cmp     r14d, r15d
0x180003114  jb      loc_180002DDC
0x18000311a  test    eax, eax
0x18000311c  jnz     short loc_180003127
0x18000311e  mov     ebx, edx
0x180003120  jmp     short loc_180003127
0x180003122  mov     ebx, 8
0x180003127  test    rbp, rbp
0x18000312a  jz      short loc_18000313B
  ... truncated ...
```
