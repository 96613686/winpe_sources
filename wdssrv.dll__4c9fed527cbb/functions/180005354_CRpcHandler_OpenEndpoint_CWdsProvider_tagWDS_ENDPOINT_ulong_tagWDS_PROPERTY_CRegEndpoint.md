# CRpcHandler::OpenEndpoint(CWdsProvider *,tagWDS_ENDPOINT *,ulong,tagWDS_PROPERTY *,CRegEndpoint * *)

- ea: `0x180005354`
- end: `0x180005559`
- name: `?OpenEndpoint@CRpcHandler@@QEAAKPEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@KPEAUtagWDS_PROPERTY@@PEAPEAVCRegEndpoint@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(CRpcHandler *this, struct CWdsProvider *, struct tagWDS_ENDPOINT *, int, struct tagWDS_PROPERTY *, struct CRegEndpoint **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001385c`

## callees

- `0x180002358`
- `0x180003a18`
- `0x180005354`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005389`
- `KERNEL32!EnterCriticalSection` at `0x180005389`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005428`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800054c5`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005428`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800054c5`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000551f`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000551f`

## pseudocode

```c
__int64 __fastcall CRpcHandler::OpenEndpoint(
        CRpcHandler *this,
        struct CWdsProvider *a2,
        struct tagWDS_ENDPOINT *a3,
        int a4,
        struct tagWDS_PROPERTY *a5,
        struct CRegEndpoint **a6)
{
  char *v6; // rbx
  __int64 v10; // rdx
  bool v11; // zf
  unsigned int v12; // r14d
  struct CRegEndpoint *v13; // rbx
  __int64 v15; // [rsp+20h] [rbp-98h]
  __int64 v16; // [rsp+28h] [rbp-90h]
  __int64 v17; // [rsp+30h] [rbp-88h]
  char *v18; // [rsp+80h] [rbp-38h] BYREF
  __int64 v19; // [rsp+88h] [rbp-30h]
  __int128 v20; // [rsp+90h] [rbp-28h]
  struct CRegEndpoint *v21; // [rsp+C0h] [rbp+8h] BYREF

  v21 = 0;
  v6 = (char *)this + 96;
  v18 = (char *)this + 96;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v11 = *((_DWORD *)a3 + 1) == 1;
  LODWORD(v19) = 1;
  if ( !v11 || !*((_DWORD *)a3 + 2) || *(_DWORD *)a3 != 1052 || (*((_DWORD *)a3 + 2) & 0xFFFFFFFC) != 0 )
  {
    v12 = 87;
    goto LABEL_8;
  }
  v12 = CRegEndpoint::Add<CRpcHandler,CRegRpcEndpoint>(v6, v10, a2, a3, a5, a4, &v21);
  if ( v12 )
  {
LABEL_8:
    LODWORD(v17) = *((unsigned __int16 *)a3 + 9);
    LODWORD(v16) = *((unsigned __int16 *)a3 + 8);
    LODWORD(v15) = *((_DWORD *)a3 + 3);
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x80000u,
      L"[%s][RPC][Ep={%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}] Registration Failed (rc=%u)",
      *((_QWORD *)a2 + 2),
      v15,
      v16,
      v17,
      *((unsigned __int8 *)a3 + 20),
      *((unsigned __int8 *)a3 + 21),
      *((unsigned __int8 *)a3 + 22),
      *((unsigned __int8 *)a3 + 23),
      *((unsigned __int8 *)a3 + 24),
      *((unsigned __int8 *)a3 + 25),
      *((unsigned __int8 *)a3 + 26),
      *((unsigned __int8 *)a3 + 27),
      v12,
      v18,
      v19);
    v20 = *(_OWORD *)((char *)a3 + 12);
    CEventLog::Log((CEventLog *)qword_180039300, 0x41010405u, 3);
    goto LABEL_9;
  }
  v13 = v21;
  CTrace::Trace(
    (CTrace *)qword_180039310,
    0x20000u,
    L"[%s][RPC][Ep=%s] Registered",
    *((_QWORD *)a2 + 2),
    (char *)v21 + 1288);
  *a6 = v13;
LABEL_9:
  CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(&v18);
  return v12;
}

```

## disassembly

```asm
0x180005354  mov     rax, rsp
0x180005357  mov     [rax+10h], rbx
0x18000535b  mov     [rax+18h], rbp
0x18000535f  mov     [rax+20h], rsi
0x180005363  push    rdi
0x180005364  push    r14
0x180005366  push    r15
0x180005368  sub     rsp, 0A0h
0x18000536f  and     qword ptr [rax+8], 0
0x180005374  lea     rbx, [rcx+60h]
0x180005378  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000537c  mov     [rax-38h], rbx
0x180005380  mov     edi, r9d
0x180005383  mov     rbp, r8
0x180005386  mov     r15, rdx
0x180005389  call    cs:__imp_EnterCriticalSection
0x180005390  nop     dword ptr [rax+rax+00h]
0x180005395  cmp     dword ptr [rbp+4], 1
0x180005399  mov     dword ptr [rsp+0B8h+var_30], 1
0x1800053a4  jnz     loc_180005444
0x1800053aa  cmp     dword ptr [rbp+8], 0
0x1800053ae  jz      loc_180005444
0x1800053b4  cmp     dword ptr [rbp+0], 41Ch
0x1800053bb  jnz     loc_180005444
0x1800053c1  test    dword ptr [rbp+8], 0FFFFFFFCh
0x1800053c8  jnz     short loc_180005444
0x1800053ca  lea     rax, [rsp+0B8h+arg_0]
0x1800053d2  mov     r9, rbp
0x1800053d5  mov     [rsp+0B8h+var_88], rax
0x1800053da  mov     r8, r15
0x1800053dd  mov     rax, [rsp+0B8h+arg_20]
0x1800053e5  mov     rcx, rbx
0x1800053e8  mov     dword ptr [rsp+0B8h+var_90], edi
0x1800053ec  mov     [rsp+0B8h+var_98], rax
0x1800053f1  call    ??$Add@VCRpcHandler@@VCRegRpcEndpoint@@@CRegEndpoint@@SAKPEAV?$CList@VCRegRpcEndpoint@@VCCriticalSection@@@@PEAVCRpcHandler@@PEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@PEAUtagWDS_PROPERTY@@KPEAPEAVCRegRpcEndpoint@@@Z; CRegEndpoint::Add<CRpcHandler,CRegRpcEndpoint>(CList<CRegRpcEndpoint,CCriticalSection> *,CRpcHandler *,CWdsProvider *,tagWDS_ENDPOINT *,tagWDS_PROPERTY *,ulong,CRegRpcEndpoint * *)
0x1800053f6  mov     r14d, eax
0x1800053f9  test    eax, eax
0x1800053fb  jnz     short loc_18000544A
0x1800053fd  mov     rbx, [rsp+0B8h+arg_0]
0x180005405  lea     r8, aSRpcEpSRegiste; "[%s][RPC][Ep=%s] Registered"
0x18000540c  mov     r9, [r15+10h]
0x180005410  mov     edx, 20000h
0x180005415  lea     rcx, [rbx+508h]
0x18000541c  mov     [rsp+0B8h+var_98], rcx
0x180005421  lea     rcx, qword_180039310
0x180005428  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000542f  nop     dword ptr [rax+rax+00h]
0x180005434  mov     rcx, [rsp+0B8h+arg_28]
0x18000543c  mov     [rcx], rbx
0x18000543f  jmp     loc_18000552B
0x180005444  mov     r14d, 57h ; 'W'
0x18000544a  movzx   eax, byte ptr [rbp+1Bh]
0x18000544e  movzx   ecx, byte ptr [rbp+1Ah]
0x180005452  movzx   edx, byte ptr [rbp+19h]
0x180005456  movzx   r8d, byte ptr [rbp+18h]
0x18000545b  movzx   r9d, byte ptr [rbp+17h]
0x180005460  movzx   r10d, byte ptr [rbp+16h]
0x180005465  movzx   r11d, byte ptr [rbp+15h]
0x18000546a  movzx   ebx, byte ptr [rbp+14h]
0x18000546e  movzx   edi, word ptr [rbp+12h]
0x180005472  movzx   esi, word ptr [rbp+10h]
0x180005476  mov     [rsp+0B8h+var_40], r14d
0x18000547b  mov     [rsp+0B8h+var_48], eax
0x18000547f  mov     eax, [rbp+0Ch]
0x180005482  mov     [rsp+0B8h+var_50], ecx
0x180005486  lea     rcx, qword_180039310
0x18000548d  mov     [rsp+0B8h+var_58], edx
0x180005491  mov     edx, 80000h
0x180005496  mov     [rsp+0B8h+var_60], r8d
0x18000549b  lea     r8, aSRpcEp08x04x04; "[%s][RPC][Ep={%08X-%04X-%04X-%02X%02X-%"...
0x1800054a2  mov     [rsp+0B8h+var_68], r9d
0x1800054a7  mov     r9, [r15+10h]
0x1800054ab  mov     [rsp+0B8h+var_70], r10d
0x1800054b0  mov     [rsp+0B8h+var_78], r11d
0x1800054b5  mov     [rsp+0B8h+var_80], ebx
0x1800054b9  mov     dword ptr [rsp+0B8h+var_88], edi
0x1800054bd  mov     dword ptr [rsp+0B8h+var_90], esi
0x1800054c1  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800054c5  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800054cc  nop     dword ptr [rax+rax+00h]
0x1800054d1  mov     rax, [r15+10h]
0x1800054d5  lea     rcx, qword_180039300
0x1800054dc  movups  xmm0, xmmword ptr [rbp+0Ch]
0x1800054e0  mov     [rsp+0B8h+var_78], r14d
0x1800054e5  mov     r9d, 8
0x1800054eb  mov     [rsp+0B8h+var_80], 5
0x1800054f3  mov     edx, 41010405h
0x1800054f8  mov     [rsp+0B8h+var_88], rax
0x1800054fd  lea     rax, [rsp+0B8h+var_28]
0x180005505  mov     dword ptr [rsp+0B8h+var_90], 1
0x18000550d  lea     r8d, [r9-5]
0x180005511  mov     [rsp+0B8h+var_98], rax
0x180005516  movdqu  [rsp+0B8h+var_28], xmm0
0x18000551f  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180005526  nop     dword ptr [rax+rax+00h]
0x18000552b  lea     rcx, [rsp+0B8h+var_38]
0x180005533  call    ??1?$CAutoTypeLock@V?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@@@QEAA@XZ; CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(void)
0x180005538  lea     r11, [rsp+0B8h+var_18]
0x180005540  mov     eax, r14d
0x180005543  mov     rbx, [r11+28h]
0x180005547  mov     rbp, [r11+30h]
0x18000554b  mov     rsi, [r11+38h]
0x18000554f  mov     rsp, r11
0x180005552  pop     r15
0x180005554  pop     r14
0x180005556  pop     rdi
0x180005557  retn
```
