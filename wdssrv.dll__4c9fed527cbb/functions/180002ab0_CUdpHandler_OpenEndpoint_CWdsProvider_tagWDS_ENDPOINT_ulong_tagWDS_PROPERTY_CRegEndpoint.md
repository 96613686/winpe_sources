# CUdpHandler::OpenEndpoint(CWdsProvider *,tagWDS_ENDPOINT *,ulong,tagWDS_PROPERTY *,CRegEndpoint * *)

- ea: `0x180002ab0`
- end: `0x180002c1c`
- name: `?OpenEndpoint@CUdpHandler@@QEAAKPEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@KPEAUtagWDS_PROPERTY@@PEAPEAVCRegEndpoint@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct CWdsProvider *, struct tagWDS_ENDPOINT *, int, struct tagWDS_PROPERTY *, struct CRegEndpoint **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001385c`

## callees

- `0x180002108`
- `0x180002358`
- `0x18000263c`
- `0x180002ab0`
- `0x180002c24`
- `0x180003944`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002b5b`
- `KERNEL32!LeaveCriticalSection` at `0x180002b5b`
- `KERNEL32!EnterCriticalSection` at `0x180002ae6`
- `KERNEL32!EnterCriticalSection` at `0x180002ae6`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180002bd9`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180002bd9`

## pseudocode

```c
__int64 __fastcall CUdpHandler::OpenEndpoint(
        struct _RTL_CRITICAL_SECTION *this,
        struct CWdsProvider *a2,
        struct tagWDS_ENDPOINT *a3,
        int a4,
        struct tagWDS_PROPERTY *a5,
        struct CRegEndpoint **a6)
{
  HANDLE *p_LockSemaphore; // r14
  struct CRegEndpoint *v8; // rbx
  __int64 OpenUdpEndpoints; // rsi
  __int64 v13; // rdx
  __int64 v15; // [rsp+20h] [rbp-48h]
  __int64 v16; // [rsp+28h] [rbp-40h]
  HANDLE *v17; // [rsp+40h] [rbp-28h] BYREF
  int v18; // [rsp+48h] [rbp-20h]
  struct CRegEndpoint *v19; // [rsp+70h] [rbp+8h] BYREF

  p_LockSemaphore = &this->LockSemaphore;
  v8 = 0;
  v17 = &this->LockSemaphore;
  v19 = 0;
  EnterCriticalSection(this + 1);
  v18 = 1;
  if ( *(_QWORD *)((char *)a3 + 4) || *(_DWORD *)a3 != 1052 || *((_DWORD *)a3 + 4) )
  {
    LODWORD(OpenUdpEndpoints) = 87;
LABEL_11:
    LODWORD(v16) = OpenUdpEndpoints;
    LODWORD(v15) = *((unsigned __int16 *)a3 + 6);
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x80000u,
      L"[%s][UDP][Ep=%u] Registration Failed (rc=%u)",
      *((_QWORD *)a2 + 2),
      v15,
      v16);
    if ( v8 )
      CUdpHandler::CloseEndpoint((CUdpHandler *)this, v8);
    goto LABEL_13;
  }
  LODWORD(OpenUdpEndpoints) = CRegEndpoint::Add<CUdpHandler,CRegUdpEndpoint>(
                                p_LockSemaphore,
                                this,
                                a2,
                                a3,
                                a5,
                                a4,
                                &v19);
  if ( (_DWORD)OpenUdpEndpoints )
  {
    v8 = v19;
    goto LABEL_11;
  }
  v18 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
  v8 = v19;
  OpenUdpEndpoints = CUdpHandler::QueryOpenUdpEndpoints((CUdpHandler *)this, v19);
  if ( !(unsigned int)ElValidateWin32(OpenUdpEndpoints, v13, "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp", 341) )
  {
    *((_WORD *)a3 + 6) = *((_WORD *)v8 + 42);
    *a6 = v8;
  }
  if ( (_DWORD)OpenUdpEndpoints )
    goto LABEL_11;
LABEL_13:
  CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(&v17);
  return (unsigned int)OpenUdpEndpoints;
}

```

## disassembly

```asm
0x180002ab0  mov     rax, rsp
0x180002ab3  mov     [rax+10h], rbx
0x180002ab7  mov     [rax+18h], rbp
0x180002abb  mov     [rax+20h], rsi
0x180002abf  push    rdi
0x180002ac0  push    r14
0x180002ac2  push    r15
0x180002ac4  sub     rsp, 50h
0x180002ac8  lea     r14, [rcx+18h]
0x180002acc  mov     rbp, rcx
0x180002acf  xor     ebx, ebx
0x180002ad1  mov     [rax-28h], r14
0x180002ad5  lea     rcx, [r14+10h]; lpCriticalSection
0x180002ad9  mov     [rax+8], rbx
0x180002add  mov     esi, r9d
0x180002ae0  mov     rdi, r8
0x180002ae3  mov     r15, rdx
0x180002ae6  call    cs:__imp_EnterCriticalSection
0x180002aed  nop     dword ptr [rax+rax+00h]
0x180002af2  mov     [rsp+68h+var_20], 1
0x180002afa  cmp     [rdi+4], ebx
0x180002afd  jnz     loc_180002BB1
0x180002b03  cmp     [rdi+8], ebx
0x180002b06  jnz     loc_180002BB1
0x180002b0c  cmp     dword ptr [rdi], 41Ch
0x180002b12  jnz     loc_180002BB1
0x180002b18  cmp     [rdi+10h], ebx
0x180002b1b  jnz     loc_180002BB1
0x180002b21  lea     rax, [rsp+68h+arg_0]
0x180002b26  mov     r9, rdi
0x180002b29  mov     [rsp+68h+var_38], rax
0x180002b2e  mov     r8, r15
0x180002b31  mov     rax, [rsp+68h+arg_20]
0x180002b39  mov     rdx, rbp
0x180002b3c  mov     dword ptr [rsp+68h+var_40], esi
0x180002b40  mov     rcx, r14
0x180002b43  mov     [rsp+68h+var_48], rax
0x180002b48  call    ??$Add@VCUdpHandler@@VCRegUdpEndpoint@@@CRegEndpoint@@SAKPEAV?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@PEAVCUdpHandler@@PEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@PEAUtagWDS_PROPERTY@@KPEAPEAVCRegUdpEndpoint@@@Z; CRegEndpoint::Add<CUdpHandler,CRegUdpEndpoint>(CList<CRegUdpEndpoint,CCriticalSection> *,CUdpHandler *,CWdsProvider *,tagWDS_ENDPOINT *,tagWDS_PROPERTY *,ulong,CRegUdpEndpoint * *)
0x180002b4d  mov     esi, eax
0x180002b4f  test    eax, eax
0x180002b51  jnz     short loc_180002BAA
0x180002b53  and     [rsp+68h+var_20], ebx
0x180002b57  lea     rcx, [r14+10h]; lpCriticalSection
0x180002b5b  call    cs:__imp_LeaveCriticalSection
0x180002b62  nop     dword ptr [rax+rax+00h]
0x180002b67  mov     rbx, [rsp+68h+arg_0]
0x180002b6c  mov     rcx, rbp; this
0x180002b6f  mov     rdx, rbx; struct CRegUdpEndpoint *
0x180002b72  call    ?QueryOpenUdpEndpoints@CUdpHandler@@AEAAKPEAVCRegUdpEndpoint@@@Z; CUdpHandler::QueryOpenUdpEndpoints(CRegUdpEndpoint *)
0x180002b77  mov     r9d, 155h
0x180002b7d  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180002b84  mov     ecx, eax
0x180002b86  mov     esi, eax
0x180002b88  call    ElValidateWin32
0x180002b8d  test    eax, eax
0x180002b8f  jnz     short loc_180002BA4
0x180002b91  movzx   eax, word ptr [rbx+54h]
0x180002b95  mov     [rdi+0Ch], ax
0x180002b99  mov     rax, [rsp+68h+arg_28]
0x180002ba1  mov     [rax], rbx
0x180002ba4  test    esi, esi
0x180002ba6  jz      short loc_180002BF5
0x180002ba8  jmp     short loc_180002BB6
0x180002baa  mov     rbx, [rsp+68h+arg_0]
0x180002baf  jmp     short loc_180002BB6
0x180002bb1  mov     esi, 57h ; 'W'
0x180002bb6  movzx   eax, word ptr [rdi+0Ch]
0x180002bba  lea     r8, aSUdpEpURegistr; "[%s][UDP][Ep=%u] Registration Failed (r"...
0x180002bc1  mov     r9, [r15+10h]
0x180002bc5  lea     rcx, qword_180039310
0x180002bcc  mov     dword ptr [rsp+68h+var_40], esi
0x180002bd0  mov     edx, 80000h
0x180002bd5  mov     dword ptr [rsp+68h+var_48], eax
0x180002bd9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180002be0  nop     dword ptr [rax+rax+00h]
0x180002be5  test    rbx, rbx
0x180002be8  jz      short loc_180002BF5
0x180002bea  mov     rdx, rbx; struct CRegEndpoint *
0x180002bed  mov     rcx, rbp; this
0x180002bf0  call    ?CloseEndpoint@CUdpHandler@@QEAAKPEAVCRegEndpoint@@@Z; CUdpHandler::CloseEndpoint(CRegEndpoint *)
0x180002bf5  lea     rcx, [rsp+68h+var_28]
0x180002bfa  call    ??1?$CAutoTypeLock@V?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@@@QEAA@XZ; CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(void)
0x180002bff  lea     r11, [rsp+68h+var_18]
0x180002c04  mov     eax, esi
0x180002c06  mov     rbx, [r11+28h]
0x180002c0a  mov     rbp, [r11+30h]
0x180002c0e  mov     rsi, [r11+38h]
0x180002c12  mov     rsp, r11
0x180002c15  pop     r15
0x180002c17  pop     r14
0x180002c19  pop     rdi
0x180002c1a  retn
```
