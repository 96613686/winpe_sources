# WFDSConMgr::CInfraCastHelper::GetConnectedInfraCastBackchannelParams(void)

- ea: `0x18004848c`
- end: `0x1800485b9`
- name: `?GetConnectedInfraCastBackchannelParams@CInfraCastHelper@WFDSConMgr@@QEBA?AUInfraBackchannelResults@2@XZ`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180039f5c`

## callees

- `0x180002ffc`
- `0x1800059c0`
- `0x18004848c`
- `0x18005c888`
- `0x18005dcc0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485a7`

## string_xrefs

- `0x1800484ad`: `Tried to read back channel params before connection completed`
- `0x180048575`: `GetPostCompletionParameters failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall WFDSConMgr::CInfraCastHelper::GetConnectedInfraCastBackchannelParams(_QWORD *a1, _OWORD *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+8h] BYREF

  if ( !WFDSConMgr::CManualResetEvent::IsSignalled((WFDSConMgr::CManualResetEvent *)(a1 + 15)) )
    WFDSConMgr::CException::Throw(
      21,
      "WFDSConMgr::CInfraCastHelper::GetConnectedInfraCastBackchannelParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      237,
      L"Tried to read back channel params before connection completed",
      a1);
  memset_0(a2, 0, 0x80u);
  memset_0(a2 + 8, 0, 0x80u);
  a2[16] = 0;
  WFDSConMgr::CriticalSection::Lock(a1 + 9, &lpCriticalSection);
  v4 = a1[21];
  if ( !v4 )
    WFDSConMgr::CException::Throw(
      21,
      "WFDSConMgr::CInfraCastHelper::GetConnectedInfraCastBackchannelParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      246,
      L"No connector object exists",
      a1);
  v5 = (*(__int64 (__fastcall **)(__int64, _OWORD *, _OWORD *, _OWORD *))(*(_QWORD *)v4 + 32LL))(
         v4,
         a2,
         a2 + 8,
         a2 + 16);
  if ( v5 < 0 )
    WFDSConMgr::CException::Throw(
      v5,
      "WFDSConMgr::CInfraCastHelper::GetConnectedInfraCastBackchannelParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      250,
      L"GetPostCompletionParameters failed",
      a1);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x18004848c  push    rbx
0x18004848e  push    rbp
0x18004848f  push    rsi
0x180048490  push    rdi
0x180048491  sub     rsp, 38h
0x180048495  mov     rdi, rdx
0x180048498  mov     rbx, rcx
0x18004849b  add     rcx, 78h ; 'x'; this
0x18004849f  call    ?IsSignalled@CManualResetEvent@WFDSConMgr@@QEBA_NXZ; WFDSConMgr::CManualResetEvent::IsSignalled(void)
0x1800484a4  test    al, al
0x1800484a6  jnz     short loc_1800484D8
0x1800484a8  mov     [rsp+58h+var_30], rbx; void *
0x1800484ad  lea     rax, aTriedToReadBac; "Tried to read back channel params befor"...
0x1800484b4  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800484b9  mov     r9d, 0EDh; char
0x1800484bf  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800484c6  lea     rdx, aWfdsconmgrCinf; "WFDSConMgr::CInfraCastHelper::GetConnec"...
0x1800484cd  mov     ecx, 80070015h; char
0x1800484d2  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800484d8  mov     ebp, 80h
0x1800484dd  mov     r8d, ebp; Size
0x1800484e0  xor     edx, edx; Val
0x1800484e2  mov     rcx, rdi; void *
0x1800484e5  call    memset_0
0x1800484ea  lea     rsi, [rdi+80h]
0x1800484f1  mov     r8d, ebp; Size
0x1800484f4  xor     edx, edx; Val
0x1800484f6  mov     rcx, rsi; void *
0x1800484f9  call    memset_0
0x1800484fe  lea     rbp, [rdi+100h]
0x180048505  xorps   xmm0, xmm0
0x180048508  movups  xmmword ptr [rbp+0], xmm0
0x18004850c  lea     rcx, [rbx+48h]
0x180048510  lea     rdx, [rsp+58h+lpCriticalSection]
0x180048515  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004851a  nop
0x18004851b  mov     rcx, [rbx+0A8h]
0x180048522  test    rcx, rcx
0x180048525  jnz     short loc_180048557
0x180048527  mov     [rsp+58h+var_30], rbx; void *
0x18004852c  lea     rax, aNoConnectorObj; "No connector object exists"
0x180048533  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180048538  mov     r9d, 0F6h; char
0x18004853e  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180048545  lea     rdx, aWfdsconmgrCinf; "WFDSConMgr::CInfraCastHelper::GetConnec"...
0x18004854c  mov     ecx, 80070015h; char
0x180048551  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180048557  mov     rax, [rcx]
0x18004855a  mov     r9, rbp
0x18004855d  mov     r8, rsi
0x180048560  mov     rdx, rdi
0x180048563  mov     rax, [rax+20h]
0x180048567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004856c  test    eax, eax
0x18004856e  jns     short loc_18004859D
0x180048570  mov     [rsp+58h+var_30], rbx; void *
0x180048575  lea     rcx, aGetpostcomplet; "GetPostCompletionParameters failed"
0x18004857c  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x180048581  mov     r9d, 0FAh; char
0x180048587  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004858e  lea     rdx, aWfdsconmgrCinf; "WFDSConMgr::CInfraCastHelper::GetConnec"...
0x180048595  mov     ecx, eax; char
0x180048597  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004859d  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800485a2  test    rcx, rcx
0x1800485a5  jz      short loc_1800485AD
0x1800485a7  call    cs:__imp_LeaveCriticalSection
0x1800485ad  mov     rax, rdi
0x1800485b0  add     rsp, 38h
0x1800485b4  pop     rdi
0x1800485b5  pop     rsi
0x1800485b6  pop     rbp
0x1800485b7  pop     rbx
0x1800485b8  retn
```
