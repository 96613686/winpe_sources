# SCMControlQueue::Push(ulong,ulong,void *,void *)

- ea: `0x18000fdf4`
- end: `0x180010337`
- name: `?Push@SCMControlQueue@@QEAAKKKPEAX0@Z`
- size: `1347`
- prototype: `unsigned int(SCMControlQueue *__hidden this, unsigned int, unsigned int, void *, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de60`

## callees

- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000fdf4`
- `0x18001e55c`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033884`
- `0x180034558`
- `0x180077608`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000fefc`
- `KERNEL32!LeaveCriticalSection` at `0x18000fefc`

## string_xrefs

- `0x18000ffe6`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_HANDLE (%u), %u bytes`
- `0x180010015`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_HANDLE (%u), %u bytes`
- `0x1800100ff`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_DEVICEINTERFACE (%u), %u bytes`
- `0x18001013d`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_DEVICEINTERFACE (%u), %u bytes`
- `0x1800101f0`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_OEM (%u), %u bytes`
- `0x180010239`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_OEM (%u), %u bytes`
- `0x18001014c`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_PORT (%u), %u bytes`
- `0x18001018a`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_PORT (%u), %u bytes`
- `0x180010199`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_VOLUME (%u), %u bytes`
- `0x1800101d9`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_VOLUME (%u), %u bytes`
- `0x180010089`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): unknown device type (%u), default %u bytes`
- `0x1800100cb`: `SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): unknown device type (%u), default %u bytes`
- `0x1800102bf`: `SERVICE_CONTROL_POWEREVENT (control: %u, event type: %u): %u bytes`
- `0x180010307`: `SERVICE_CONTROL_POWEREVENT (control: %u, event type: %u): %u bytes`

## pseudocode

```c
__int64 __fastcall SCMControlQueue::Push(SCMControlQueue *this, int a2, int a3, _DWORD *a4, void *a5)
{
  SCMControlQueue::ControlRequest *v9; // rax
  SCMControlQueue::ControlRequest *v10; // rdi
  unsigned int v11; // r14d
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  int v17; // ecx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // edx
  int v25; // r13d
  unsigned __int64 v26; // rsi
  int v27; // r13d
  char *v28; // rbx
  void *v29; // rdx
  const char *v30; // r8
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  void *v34; // rax
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  char *v40; // rbx
  void *v41; // rdx
  char *v42; // rbx
  void *v43; // rdx
  char *v44; // rbx
  void *v45; // rdx
  char *v46; // rbx
  void *v47; // rdx
  __int64 v48; // r9
  const char *v49; // r8
  char *v50; // rbx
  void *v51; // rdx
  void **v52; // rax
  void *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rsi
  char *v56; // rbx
  void *v57; // rdx
  LPVOID lpMem; // [rsp+20h] [rbp-68h]
  LPVOID lpMema; // [rsp+20h] [rbp-68h]
  __int64 v60; // [rsp+28h] [rbp-60h]
  _DWORD *v61; // [rsp+28h] [rbp-60h]
  unsigned __int64 v62; // [rsp+30h] [rbp-58h]
  unsigned __int64 v63; // [rsp+30h] [rbp-58h]

  v9 = (SCMControlQueue::ControlRequest *)operator new(0x20u);
  v10 = v9;
  if ( !v9 )
  {
    v10 = 0;
    goto LABEL_12;
  }
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *(_DWORD *)v9 = a2;
  *((_DWORD *)v9 + 1) = a3;
  *((_QWORD *)v9 + 2) = a5;
  if ( !a4 )
  {
LABEL_6:
    v11 = 0;
    v12 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "Adding control request to queue (control: %u, event type: %u)",
                    a2,
                    a3);
    WriteDbgTraceInfoWI("SCMControlQueue::Push", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "Adding control request to queue (control: %u, event type: %u)",
                     a2,
                     a3);
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"SCMControlQueue::Push", 4, v14);
    v17 = CRIT_SECT::Lock((SCMControlQueue *)((char *)this + 16));
    if ( *(_QWORD *)this )
    {
      *(_QWORD *)(*((_QWORD *)this + 1) + 24LL) = v10;
      *((_QWORD *)this + 1) = v10;
    }
    else
    {
      *((_QWORD *)this + 1) = v10;
      *(_QWORD *)this = v10;
      *((_QWORD *)v10 + 3) = 0;
    }
    if ( v17 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    return v11;
  }
  if ( a2 != 11 )
  {
    if ( a2 != 254 )
    {
      if ( a2 != 13 )
        goto LABEL_6;
      v26 = (unsigned int)a4[4] + 20LL;
      v56 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "SERVICE_CONTROL_POWEREVENT (control: %u, event type: %u): %u bytes",
                      13,
                      a3,
                      a4[4] + 20);
      WriteDbgTraceInfoWI("SCMControlQueue::Push", v56);
      WiaTrcLib::Free((WiaTrcLib *)v56, v57);
      v52 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "SERVICE_CONTROL_POWEREVENT (control: %u, event type: %u): %u bytes",
                       13,
                       a3,
                       v26);
      goto LABEL_36;
    }
    v55 = -1;
    do
      ++v55;
    while ( *((_WORD *)a4 + v55) );
    v26 = 2 * v55 + 2;
    v50 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "REG_DEVICE_CONTROL (control: %u, event type: %u), value: %ws, %u bytes",
                    254,
                    a3,
                    a4,
                    v26);
    WriteDbgTraceInfoWI("SCMControlQueue::Push", v50);
    WiaTrcLib::Free((WiaTrcLib *)v50, v51);
    v63 = v26;
    v49 = "REG_DEVICE_CONTROL (control: %u, event type: %u), value: %ws, %u bytes";
    v61 = a4;
    v48 = 254;
LABEL_31:
    LODWORD(lpMema) = a3;
    v52 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, v49, v48, lpMema, v61, v63);
LABEL_36:
    WiaTrace_ProcessTrace_Ex(v54, v53, (void *)"SCMControlQueue::Push", 4, v52);
LABEL_23:
    if ( !v26 )
      goto LABEL_6;
    goto LABEL_24;
  }
  v25 = a4[1];
  switch ( v25 )
  {
    case 0:
      v26 = (unsigned int)*a4;
      v46 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_OEM (%u), %u bytes",
                      11,
                      a3,
                      0,
                      *a4);
      WriteDbgTraceInfoWI("SCMControlQueue::Push", v46);
      WiaTrcLib::Free((WiaTrcLib *)v46, v47);
      v63 = v26;
      v48 = 11;
      LODWORD(v61) = 0;
      v49 = "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_OEM (%u), %u bytes";
      goto LABEL_31;
    case 2:
      v26 = (unsigned int)*a4;
      v44 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_VOLUME (%u), %u bytes",
                      11,
                      a3,
                      2,
                      *a4);
      WriteDbgTraceInfoWI("SCMControlQueue::Push", v44);
      WiaTrcLib::Free((WiaTrcLib *)v44, v45);
      v62 = v26;
      v30 = "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_VOLUME (%u), %u bytes";
      LODWORD(v60) = 2;
      goto LABEL_22;
    case 3:
      v26 = (unsigned int)*a4;
      v27 = 3;
      v42 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_PORT (%u), %u bytes",
                      11,
                      a3,
                      3,
                      *a4);
      WriteDbgTraceInfoWI("SCMControlQueue::Push", v42);
      WiaTrcLib::Free((WiaTrcLib *)v42, v43);
      v30 = "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_PORT (%u), %u bytes";
      goto LABEL_21;
    case 5:
      v26 = (unsigned int)*a4;
      v27 = 5;
      v40 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_DEVICEINTERFACE (%u), %u bytes",
                      11,
                      a3,
                      5,
                      *a4);
      WriteDbgTraceInfoWI("SCMControlQueue::Push", v40);
      WiaTrcLib::Free((WiaTrcLib *)v40, v41);
      v30 = "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_DEVICEINTERFACE (%u), %u bytes";
      goto LABEL_21;
    case 6:
      v26 = (unsigned int)*a4;
      v27 = 6;
      v28 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_HANDLE (%u), %u bytes",
                      11,
                      a3,
                      6,
                      *a4);
      WriteDbgTraceInfoWI("SCMControlQueue::Push", v28);
      WiaTrcLib::Free((WiaTrcLib *)v28, v29);
      v30 = "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): DBT_DEVTYP_HANDLE (%u), %u bytes";
LABEL_21:
      v62 = v26;
      LODWORD(v60) = v27;
LABEL_22:
      LODWORD(lpMem) = a3;
      v31 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, v30, 11, lpMem, v60, v62);
      WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"SCMControlQueue::Push", 4, v31);
      goto LABEL_23;
  }
  v26 = 12;
  v35 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                  0,
                  0,
                  "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): unknown device type (%u), default %u bytes",
                  11,
                  a3,
                  v25,
                  12);
  WriteDbgTraceInfoWI("SCMControlQueue::Push", v35);
  WiaTrcLib::Free((WiaTrcLib *)v35, v36);
  v37 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                   0,
                   0,
                   "SERVICE_CONTROL_DEVICEEVENT (control: %u, event type: %u): unknown device type (%u), default %u bytes",
                   11,
                   a3,
                   v25,
                   12);
  WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"SCMControlQueue::Push", 4, v37);
LABEL_24:
  v34 = operator new[](v26);
  *((_QWORD *)v10 + 1) = v34;
  if ( v34 )
  {
    memcpy_0(v34, a4, v26);
    goto LABEL_6;
  }
LABEL_12:
  v11 = 14;
  v19 = (char *)WiaTrace_TraceLog("Cannot queue control request (control code: %u, event type: %u), error code %u");
  WriteDbgTraceErrorWI("SCMControlQueue::Push", v19);
  WiaTrcLib::Free((WiaTrcLib *)v19, v20);
  v21 = (void **)WiaTrace_Trace(
                   "Cannot queue control request (control code: %u, event type: %u), error code %u",
                   a2,
                   a3,
                   14);
  WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"SCMControlQueue::Push", 1, v21);
  if ( v10 )
    SCMControlQueue::ControlRequest::`scalar deleting destructor'(v10, v24);
  return v11;
}

```

## disassembly

```asm
0x18000fdf4  push    rbx
0x18000fdf6  push    rbp
0x18000fdf7  push    rsi
0x18000fdf8  push    rdi
0x18000fdf9  push    r12
0x18000fdfb  push    r13
0x18000fdfd  push    r14
0x18000fdff  push    r15
0x18000fe01  sub     rsp, 48h
0x18000fe05  mov     r12, rcx
0x18000fe08  mov     r14, r9
0x18000fe0b  mov     ecx, 20h ; ' '; Size
0x18000fe10  mov     ebp, r8d
0x18000fe13  mov     r15d, edx
0x18000fe16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fe1b  xor     r13d, r13d
0x18000fe1e  mov     rdi, rax
0x18000fe21  test    rax, rax
0x18000fe24  jz      loc_18000FF16
0x18000fe2a  mov     [rax+8], r13
0x18000fe2e  mov     [rax+18h], r13
0x18000fe32  mov     [rax], r15d
0x18000fe35  mov     [rax+4], ebp
0x18000fe38  mov     rax, [rsp+88h+arg_20]
0x18000fe40  mov     [rdi+10h], rax
0x18000fe44  test    r14, r14
0x18000fe47  jz      short loc_18000FE6E
0x18000fe49  lea     ecx, [r13+0Bh]
0x18000fe4d  cmp     r15d, ecx
0x18000fe50  jz      loc_18000FF9F
0x18000fe56  mov     eax, 0FEh
0x18000fe5b  cmp     r15d, eax
0x18000fe5e  jz      loc_1800102AB
0x18000fe64  cmp     r15d, 0Dh
0x18000fe68  jz      loc_1800102BB
0x18000fe6e  mov     r9d, r15d
0x18000fe71  mov     dword ptr [rsp+88h+lpMem], ebp
0x18000fe75  lea     r8, aAddingControlR; "Adding control request to queue (contro"...
0x18000fe7c  xor     edx, edx
0x18000fe7e  xor     ecx, ecx
0x18000fe80  mov     r14d, r13d
0x18000fe83  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000fe88  mov     rdx, rax; char *
0x18000fe8b  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18000fe92  mov     rbx, rax
0x18000fe95  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000fe9a  mov     rcx, rbx; this
0x18000fe9d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000fea2  mov     r9d, r15d
0x18000fea5  mov     dword ptr [rsp+88h+lpMem], ebp
0x18000fea9  lea     r8, aAddingControlR; "Adding control request to queue (contro"...
0x18000feb0  xor     edx, edx
0x18000feb2  xor     ecx, ecx
0x18000feb4  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000feb9  mov     r9d, 4; int
0x18000febf  mov     [rsp+88h+lpMem], rax; lpMem
0x18000fec4  lea     r8, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18000fecb  call    WiaTrace_ProcessTrace_Ex
0x18000fed0  lea     rcx, [r12+10h]; this
0x18000fed5  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18000feda  mov     ecx, eax
0x18000fedc  cmp     [r12], r13
0x18000fee0  jnz     loc_18000FF8C
0x18000fee6  mov     [r12+8], rdi
0x18000feeb  mov     [r12], rdi
0x18000feef  mov     [rdi+18h], r13
0x18000fef3  test    ecx, ecx
0x18000fef5  jz      short loc_18000FF02
0x18000fef7  lea     rcx, [r12+10h]; lpCriticalSection
0x18000fefc  call    cs:__imp_LeaveCriticalSection
0x18000ff02  mov     eax, r14d
0x18000ff05  add     rsp, 48h
0x18000ff09  pop     r15
0x18000ff0b  pop     r14
0x18000ff0d  pop     r13
0x18000ff0f  pop     r12
0x18000ff11  pop     rdi
0x18000ff12  pop     rsi
0x18000ff13  pop     rbp
0x18000ff14  pop     rbx
0x18000ff15  retn
0x18000ff16  mov     rdi, r13
0x18000ff19  mov     esi, 0Eh
0x18000ff1e  lea     rcx, aCannotQueueCon; "Cannot queue control request (control c"...
0x18000ff25  mov     r9d, esi
0x18000ff28  mov     r8d, ebp
0x18000ff2b  mov     edx, r15d
0x18000ff2e  mov     r14d, esi
0x18000ff31  call    WiaTrace_TraceLog
0x18000ff36  mov     rdx, rax; char *
0x18000ff39  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18000ff40  mov     rbx, rax
0x18000ff43  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000ff48  mov     rcx, rbx; this
0x18000ff4b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000ff50  mov     r9d, esi
0x18000ff53  lea     rcx, aCannotQueueCon; "Cannot queue control request (control c"...
0x18000ff5a  mov     r8d, ebp
0x18000ff5d  mov     edx, r15d
0x18000ff60  call    WiaTrace_Trace
0x18000ff65  lea     r9d, [rsi-0Dh]; int
0x18000ff69  mov     [rsp+88h+lpMem], rax; lpMem
0x18000ff6e  lea     r8, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18000ff75  call    WiaTrace_ProcessTrace_Ex
0x18000ff7a  test    rdi, rdi
0x18000ff7d  jz      short loc_18000FF02
0x18000ff7f  mov     rcx, rdi; this
0x18000ff82  call    ??_GControlRequest@SCMControlQueue@@QEAAPEAXI@Z; SCMControlQueue::ControlRequest::`scalar deleting destructor'(uint)
0x18000ff87  jmp     loc_18000FF02
0x18000ff8c  mov     rax, [r12+8]
0x18000ff91  mov     [rax+18h], rdi
0x18000ff95  mov     [r12+8], rdi
0x18000ff9a  jmp     loc_18000FEF3
0x18000ff9f  mov     r13d, [r14+4]
0x18000ffa3  mov     r9d, ecx
0x18000ffa6  mov     eax, r13d
0x18000ffa9  test    r13d, r13d
0x18000ffac  jz      loc_1800101ED
0x18000ffb2  sub     eax, 2
0x18000ffb5  jz      loc_180010196
0x18000ffbb  sub     eax, 1
0x18000ffbe  jz      loc_180010149
0x18000ffc4  sub     eax, 2
0x18000ffc7  jz      loc_1800100FC
0x18000ffcd  xor     edx, edx
0x18000ffcf  xor     ecx, ecx
0x18000ffd1  cmp     eax, 1
0x18000ffd4  jnz     loc_180010084
0x18000ffda  mov     esi, [r14]
0x18000ffdd  lea     r13d, [rdx+6]
0x18000ffe1  mov     [rsp+88h+var_58], rsi
0x18000ffe6  lea     r8, aServiceControl_2; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x18000ffed  mov     dword ptr [rsp+88h+var_60], r13d
0x18000fff2  mov     dword ptr [rsp+88h+lpMem], ebp
0x18000fff6  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000fffb  mov     rdx, rax; char *
0x18000fffe  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x180010005  mov     rbx, rax
0x180010008  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001000d  mov     rcx, rbx; this
0x180010010  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180010015  lea     r8, aServiceControl_2; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x18001001c  mov     [rsp+88h+var_58], rsi
0x180010021  mov     dword ptr [rsp+88h+var_60], r13d
0x180010026  mov     r9d, 0Bh
0x18001002c  mov     dword ptr [rsp+88h+lpMem], ebp
0x180010030  xor     edx, edx
0x180010032  xor     ecx, ecx
0x180010034  call    WiaTrace_TraceWithSubCompTraceLevel
0x180010039  mov     r9d, 4; int
0x18001003f  mov     [rsp+88h+lpMem], rax; lpMem
0x180010044  lea     r8, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18001004b  call    WiaTrace_ProcessTrace_Ex
0x180010050  xor     r13d, r13d
0x180010053  test    rsi, rsi
0x180010056  jz      loc_18000FE6E
0x18001005c  mov     rcx, rsi; unsigned __int64
0x18001005f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010064  mov     [rdi+8], rax
0x180010068  test    rax, rax
0x18001006b  jz      loc_18000FF19
0x180010071  mov     r8, rsi; Size
0x180010074  mov     rdx, r14; Src
0x180010077  mov     rcx, rax; void *
0x18001007a  call    memcpy_0
0x18001007f  jmp     loc_18000FE6E
0x180010084  mov     esi, 0Ch
0x180010089  lea     r8, aServiceControl; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x180010090  mov     [rsp+88h+var_58], rsi
0x180010095  mov     dword ptr [rsp+88h+var_60], r13d
0x18001009a  mov     dword ptr [rsp+88h+lpMem], ebp
0x18001009e  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800100a3  mov     rdx, rax; char *
0x1800100a6  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x1800100ad  mov     rbx, rax
0x1800100b0  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800100b5  mov     rcx, rbx; this
0x1800100b8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800100bd  mov     [rsp+88h+var_58], rsi
0x1800100c2  lea     r9d, [rsi-1]
0x1800100c6  mov     dword ptr [rsp+88h+var_60], r13d
0x1800100cb  lea     r8, aServiceControl; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x1800100d2  xor     edx, edx
0x1800100d4  mov     dword ptr [rsp+88h+lpMem], ebp
0x1800100d8  xor     ecx, ecx
0x1800100da  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800100df  lea     r9d, [rsi-8]; int
0x1800100e3  mov     [rsp+88h+lpMem], rax; lpMem
0x1800100e8  lea     r8, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x1800100ef  call    WiaTrace_ProcessTrace_Ex
0x1800100f4  xor     r13d, r13d
0x1800100f7  jmp     loc_18001005C
0x1800100fc  mov     esi, [r14]
0x1800100ff  lea     r8, aServiceControl_3; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x180010106  mov     [rsp+88h+var_58], rsi
0x18001010b  mov     r13d, 5
0x180010111  mov     dword ptr [rsp+88h+var_60], r13d
0x180010116  xor     edx, edx
0x180010118  xor     ecx, ecx
0x18001011a  mov     dword ptr [rsp+88h+lpMem], ebp
0x18001011e  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180010123  mov     rdx, rax; char *
0x180010126  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18001012d  mov     rbx, rax
0x180010130  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180010135  mov     rcx, rbx; this
0x180010138  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001013d  lea     r8, aServiceControl_3; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x180010144  jmp     loc_18001001C
0x180010149  mov     esi, [r14]
0x18001014c  lea     r8, aServiceControl_6; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x180010153  mov     [rsp+88h+var_58], rsi
0x180010158  mov     r13d, 3
0x18001015e  mov     dword ptr [rsp+88h+var_60], r13d
0x180010163  xor     edx, edx
0x180010165  xor     ecx, ecx
0x180010167  mov     dword ptr [rsp+88h+lpMem], ebp
0x18001016b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180010170  mov     rdx, rax; char *
0x180010173  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18001017a  mov     rbx, rax
0x18001017d  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180010182  mov     rcx, rbx; this
0x180010185  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001018a  lea     r8, aServiceControl_6; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x180010191  jmp     loc_18001001C
0x180010196  mov     esi, [r14]
0x180010199  lea     r8, aServiceControl_0; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x1800101a0  mov     [rsp+88h+var_58], rsi
0x1800101a5  xor     edx, edx
0x1800101a7  mov     dword ptr [rsp+88h+var_60], 2
0x1800101af  xor     ecx, ecx
0x1800101b1  mov     dword ptr [rsp+88h+lpMem], ebp
0x1800101b5  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800101ba  mov     rdx, rax; char *
0x1800101bd  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x1800101c4  mov     rbx, rax
0x1800101c7  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800101cc  mov     rcx, rbx; this
0x1800101cf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800101d4  mov     [rsp+88h+var_58], rsi
0x1800101d9  lea     r8, aServiceControl_0; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x1800101e0  mov     dword ptr [rsp+88h+var_60], 2
0x1800101e8  jmp     loc_180010026
0x1800101ed  mov     esi, [r14]
0x1800101f0  lea     r8, aServiceControl_4; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x1800101f7  mov     [rsp+88h+var_58], rsi
0x1800101fc  xor     r13d, r13d
0x1800101ff  mov     dword ptr [rsp+88h+var_60], r13d
0x180010204  xor     edx, edx
0x180010206  xor     ecx, ecx
0x180010208  mov     dword ptr [rsp+88h+lpMem], ebp
0x18001020c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180010211  mov     rdx, rax; char *
0x180010214  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x18001021b  mov     rbx, rax
0x18001021e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180010223  mov     rcx, rbx; this
0x180010226  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001022b  mov     [rsp+88h+var_58], rsi
0x180010230  lea     r9d, [r13+0Bh]
0x180010234  mov     dword ptr [rsp+88h+var_60], r13d
0x180010239  lea     r8, aServiceControl_4; "SERVICE_CONTROL_DEVICEEVENT (control: %"...
0x180010240  jmp     short loc_18001029C
0x180010242  lea     rsi, ds:2[rsi*2]
0x18001024a  mov     r9d, eax
0x18001024d  mov     [rsp+88h+var_58], rsi
0x180010252  lea     r8, aRegDeviceContr; "REG_DEVICE_CONTROL (control: %u, event "...
0x180010259  mov     [rsp+88h+var_60], r14
0x18001025e  xor     edx, edx
0x180010260  xor     ecx, ecx
0x180010262  mov     dword ptr [rsp+88h+lpMem], ebp
0x180010266  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001026b  mov     rdx, rax; char *
0x18001026e  lea     rcx, aScmcontrolqueu_1; "SCMControlQueue::Push"
0x180010275  mov     rbx, rax
0x180010278  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001027d  mov     rcx, rbx; this
0x180010280  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180010285  mov     [rsp+88h+var_58], rsi
0x18001028a  lea     r8, aRegDeviceContr; "REG_DEVICE_CONTROL (control: %u, event "...
0x180010291  mov     [rsp+88h+var_60], r14
0x180010296  mov     r9d, 0FEh
0x18001029c  xor     edx, edx
0x18001029e  mov     dword ptr [rsp+88h+lpMem], ebp
0x1800102a2  xor     ecx, ecx
0x1800102a4  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800102a9  jmp     short loc_18001031B
0x1800102ab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800102af  inc     rsi
0x1800102b2  cmp     [r14+rsi*2], r13w
0x1800102b7  jnz     short loc_1800102AF
0x1800102b9  jmp     short loc_180010242
0x1800102bb  mov     esi, [r14+10h]
0x1800102bf  lea     r8, aServiceControl_5; "SERVICE_CONTROL_POWEREVENT (control: %u"...
0x1800102c6  add     rsi, 14h
0x1800102ca  mov     r9d, 0Dh
0x1800102d0  mov     [rsp+88h+var_60], rsi
0x1800102d5  xor     edx, edx
0x1800102d7  xor     ecx, ecx
  ... truncated ...
```
