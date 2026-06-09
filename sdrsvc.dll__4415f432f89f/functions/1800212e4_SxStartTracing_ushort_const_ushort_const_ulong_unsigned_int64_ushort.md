# SxStartTracing(ushort const *,ushort const *,ulong,unsigned __int64 *,ushort * *)

- ea: `0x1800212e4`
- end: `0x1800215cd`
- name: `?SxStartTracing@@YAJPEBG0KPEA_KPEAPEAG@Z`
- size: `745`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int64 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016520`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001f8ec`
- `0x180020488`
- `0x18002050c`
- `0x180020b18`
- `0x1800212e4`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18002154b`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18002154b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002159e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002159e`

## pseudocode

```c
__int64 __fastcall SxStartTracing(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int64 *a4,
        unsigned __int16 **a5)
{
  PEVENT_TRACE_PROPERTIES v7; // rbx
  unsigned __int16 **v8; // rsi
  __int16 v9; // ax
  bool v10; // sf
  int v11; // eax
  __int64 *v12; // rdi
  __int64 v13; // rcx
  __int64 *v14; // r8
  __int64 v15; // rdx
  _WORD *v16; // rax
  _WORD *v17; // rcx
  signed int started; // eax
  __int64 *v19; // rax
  unsigned int v20; // ebx
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-48h] BYREF
  __int64 v24; // [rsp+40h] [rbp-40h]
  signed int v25; // [rsp+48h] [rbp-38h] BYREF
  __int16 v26; // [rsp+4Ch] [rbp-34h]
  __int16 v27; // [rsp+4Eh] [rbp-32h]
  const unsigned __int16 *v28; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v29; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v30; // [rsp+D8h] [rbp+58h] BYREF

  v29 = a3;
  v28 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v25, "SxStartTracing", 532, 1);
  LODWORD(v28) = 0;
  v7 = 0;
  Properties = 0;
  v29 = 0;
  v30 = 0;
  v23 = qword_180028260;
  v24 = 0;
  if ( a4 )
    *a4 = -1;
  v8 = a5;
  if ( a5 )
    *a5 = 0;
  v26 = 548;
  v9 = 549;
  if ( !a4 || (v26 = 549, v9 = 550, !a2) )
  {
    v25 = -2147024809;
    goto LABEL_36;
  }
  v25 = 0;
  v26 = 550;
  v25 = SxGet0XLogFileCount(a2, (unsigned int *)&v28, &v29, &v30);
  v9 = 559;
  if ( v25 < 0 )
  {
LABEL_36:
    v27 = v9;
    goto LABEL_37;
  }
  v26 = 559;
  if ( (_DWORD)v28 )
  {
    if ( !v29 )
    {
      v25 = CBsString::Format((CBsString *)&v23, (wchar_t *)L"%s.0.1.%s", a2, L"etl");
      v10 = v25 < 0;
      v9 = 577;
      goto LABEL_17;
    }
    goto LABEL_15;
  }
  if ( v29 )
  {
LABEL_15:
    v25 = CBsString::Format((CBsString *)&v23, (wchar_t *)L"%s.0.%d.%s", a2);
    v10 = v25 < 0;
    v9 = 572;
    goto LABEL_17;
  }
  v25 = CBsString::Format((CBsString *)&v23, (wchar_t *)L"%s.0.%s", a2, L"etl");
  v10 = v25 < 0;
  v9 = 563;
LABEL_17:
  if ( v10 )
    goto LABEL_36;
  v26 = v9;
  v11 = SxAllocateEventTraceProp(&Properties);
  v7 = Properties;
  v10 = v11 < 0;
  v25 = v11;
  v9 = 580;
  if ( v10 )
    goto LABEL_36;
  v12 = v23;
  v13 = 2147483646;
  v26 = 580;
  v14 = v23;
  Properties->LogFileMode = 2;
  v15 = 260;
  v7->BufferSize = 64;
  v7->MinimumBuffers = 3;
  v7->MaximumBuffers = 6;
  v7->MaximumFileSize = 10;
  v7->FlushTimer = 15;
  v16 = (_WORD *)((char *)v7 + v7->LogFileNameOffset);
  do
  {
    if ( !v13 )
      break;
    if ( !*(_WORD *)v14 )
      break;
    *v16 = *(_WORD *)v14;
    v14 = (__int64 *)((char *)v14 + 2);
    ++v16;
    --v13;
    --v15;
  }
  while ( v15 );
  v17 = v16 - 1;
  if ( v15 )
    v17 = v16;
  v9 = 588;
  *v17 = 0;
  v25 = v15 == 0 ? 0x8007007A : 0;
  if ( !v15 )
    goto LABEL_36;
  v26 = 588;
  started = StartTraceW(a4, L"BuiltInWindowsBackupTracing", v7);
  if ( started == 183 )
    goto LABEL_31;
  if ( started > 0 )
    started = (unsigned __int16)started | 0x80070000;
  v25 = started;
  v10 = started < 0;
  v9 = 594;
  if ( v10 )
    goto LABEL_36;
  v26 = 594;
LABEL_31:
  if ( v8 )
  {
    v23 = qword_180028260;
    v19 = 0;
    v24 = 0;
    if ( v12 != qword_180028260 )
      v19 = v12;
    *v8 = (unsigned __int16 *)v19;
  }
LABEL_37:
  CoTaskMemFree(v7);
  v20 = v25;
  CBsString::_Release((LPVOID *)&v23);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v25);
  return v20;
}

```

## disassembly

```asm
0x1800212e4  mov     [rsp-38h+arg_10], r8d
0x1800212e9  mov     [rsp-38h+arg_0], rcx
0x1800212ee  push    rbp
0x1800212ef  push    rbx
0x1800212f0  push    rsi
0x1800212f1  push    rdi
0x1800212f2  push    r12
0x1800212f4  push    r14
0x1800212f6  push    r15
0x1800212f8  mov     rbp, rsp
0x1800212fb  sub     rsp, 80h
0x180021302  mov     r14, r9
0x180021305  mov     rdi, rdx
0x180021308  mov     rcx, cs:WPP_GLOBAL_Control
0x18002130f  lea     rax, WPP_GLOBAL_Control
0x180021316  cmp     rcx, rax
0x180021319  jz      short loc_180021339
0x18002131b  test    dword ptr [rcx+1Ch], 20000000h
0x180021322  jz      short loc_180021339
0x180021324  mov     rcx, [rcx+10h]
0x180021328  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x18002132f  mov     edx, 15h
0x180021334  call    WPP_SF_
0x180021339  mov     r9d, 1; unsigned __int16
0x18002133f  lea     rdx, aSxstarttracing; "SxStartTracing"
0x180021346  mov     r8d, 214h; unsigned __int16
0x18002134c  lea     rcx, [rbp+var_38]; this
0x180021350  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180021355  xor     r15d, r15d
0x180021358  lea     r12, qword_180028260
0x18002135f  mov     dword ptr [rbp+arg_0], r15d
0x180021363  mov     ebx, r15d
0x180021366  mov     [rbp+Properties], rbx
0x18002136a  mov     [rbp+arg_10], r15d
0x18002136e  mov     [rbp+arg_18], r15d
0x180021372  mov     [rbp+var_48], r12
0x180021376  mov     [rbp+var_40], r15
0x18002137a  test    r14, r14
0x18002137d  jz      short loc_180021386
0x18002137f  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180021386  mov     rsi, [rbp+arg_20]
0x18002138a  test    rsi, rsi
0x18002138d  jz      short loc_180021392
0x18002138f  mov     [rsi], r15
0x180021392  mov     eax, 224h
0x180021397  mov     [rbp+var_34], ax
0x18002139b  mov     eax, 225h
0x1800213a0  test    r14, r14
0x1800213a3  jz      loc_180021590
0x1800213a9  mov     [rbp+var_34], ax
0x1800213ad  mov     eax, 226h
0x1800213b2  test    rdi, rdi
0x1800213b5  jz      loc_180021590
0x1800213bb  lea     r9, [rbp+arg_18]; unsigned int *
0x1800213bf  mov     [rbp+var_38], r15d
0x1800213c3  lea     r8, [rbp+arg_10]; unsigned int *
0x1800213c7  mov     [rbp+var_34], ax
0x1800213cb  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800213cf  mov     rcx, rdi; unsigned __int16 *
0x1800213d2  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x1800213d7  mov     [rbp+var_38], eax
0x1800213da  test    eax, eax
0x1800213dc  mov     eax, 22Fh
0x1800213e1  js      loc_180021597
0x1800213e7  mov     [rbp+var_34], ax
0x1800213eb  mov     eax, [rbp+arg_10]
0x1800213ee  cmp     dword ptr [rbp+arg_0], r15d
0x1800213f2  jnz     short loc_18002141E
0x1800213f4  test    eax, eax
0x1800213f6  jnz     short loc_180021422
0x1800213f8  lea     r9, aEtl; "etl"
0x1800213ff  mov     r8, rdi
0x180021402  lea     rdx, aS0S; "%s.0.%s"
0x180021409  lea     rcx, [rbp+var_48]; this
0x18002140d  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180021412  mov     [rbp+var_38], eax
0x180021415  test    eax, eax
0x180021417  mov     eax, 233h
0x18002141c  jmp     short loc_18002147E
0x18002141e  test    eax, eax
0x180021420  jz      short loc_18002145A
0x180021422  mov     r9d, [rbp+arg_18]
0x180021426  cmp     r9d, 7
0x18002142a  jnb     short loc_18002142F
0x18002142c  inc     r9d
0x18002142f  lea     rax, aEtl; "etl"
0x180021436  mov     r8, rdi
0x180021439  lea     rdx, aS0DS; "%s.0.%d.%s"
0x180021440  mov     [rsp+80h+var_60], rax
0x180021445  lea     rcx, [rbp+var_48]; this
0x180021449  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18002144e  mov     [rbp+var_38], eax
0x180021451  test    eax, eax
0x180021453  mov     eax, 23Ch
0x180021458  jmp     short loc_18002147E
0x18002145a  lea     r9, aEtl; "etl"
0x180021461  mov     r8, rdi
0x180021464  lea     rdx, aS01S; "%s.0.1.%s"
0x18002146b  lea     rcx, [rbp+var_48]; this
0x18002146f  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180021474  mov     [rbp+var_38], eax
0x180021477  test    eax, eax
0x180021479  mov     eax, 241h
0x18002147e  js      loc_180021597
0x180021484  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180021488  mov     [rbp+var_34], ax
0x18002148c  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x180021491  mov     rbx, [rbp+Properties]
0x180021495  test    eax, eax
0x180021497  mov     [rbp+var_38], eax
0x18002149a  mov     eax, 244h
0x18002149f  js      loc_180021597
0x1800214a5  mov     rdi, [rbp+var_48]
0x1800214a9  mov     ecx, 7FFFFFFEh
0x1800214ae  mov     [rbp+var_34], ax
0x1800214b2  mov     r8, rdi
0x1800214b5  mov     dword ptr [rbx+40h], 2
0x1800214bc  mov     edx, 104h
0x1800214c1  mov     dword ptr [rbx+30h], 40h ; '@'
0x1800214c8  mov     dword ptr [rbx+34h], 3
0x1800214cf  mov     dword ptr [rbx+38h], 6
0x1800214d6  mov     dword ptr [rbx+3Ch], 0Ah
0x1800214dd  mov     dword ptr [rbx+44h], 0Fh
0x1800214e4  mov     eax, [rbx+70h]
0x1800214e7  add     rax, rbx
0x1800214ea  test    rcx, rcx
0x1800214ed  jz      short loc_18002150E
0x1800214ef  movzx   r9d, word ptr [r8]
0x1800214f3  test    r9w, r9w
0x1800214f7  jz      short loc_18002150E
0x1800214f9  mov     [rax], r9w
0x1800214fd  add     r8, 2
0x180021501  add     rax, 2
0x180021505  dec     rcx
0x180021508  sub     rdx, 1
0x18002150c  jnz     short loc_1800214EA
0x18002150e  lea     rcx, [rax-2]
0x180021512  test    rdx, rdx
0x180021515  cmovnz  rcx, rax
0x180021519  mov     rax, rdx
0x18002151c  neg     rax
0x18002151f  mov     eax, 24Ch
0x180021524  mov     [rcx], r15w
0x180021528  sbb     ecx, ecx
0x18002152a  not     ecx
0x18002152c  and     ecx, 8007007Ah
0x180021532  mov     [rbp+var_38], ecx
0x180021535  test    rdx, rdx
0x180021538  jz      short loc_180021597
0x18002153a  mov     r8, rbx; Properties
0x18002153d  mov     [rbp+var_34], ax
0x180021541  lea     rdx, aBuiltinwindows; "BuiltInWindowsBackupTracing"
0x180021548  mov     rcx, r14; TraceHandle
0x18002154b  call    cs:__imp_StartTraceW
0x180021551  cmp     eax, 0B7h
0x180021556  jz      short loc_180021574
0x180021558  test    eax, eax
0x18002155a  jle     short loc_180021564
0x18002155c  movzx   eax, ax
0x18002155f  or      eax, 80070000h
0x180021564  mov     [rbp+var_38], eax
0x180021567  test    eax, eax
0x180021569  mov     eax, 252h
0x18002156e  js      short loc_180021597
0x180021570  mov     [rbp+var_34], ax
0x180021574  test    rsi, rsi
0x180021577  jz      short loc_18002159B
0x180021579  cmp     rdi, r12
0x18002157c  mov     [rbp+var_48], r12
0x180021580  mov     rax, r15
0x180021583  mov     [rbp+var_40], r15
0x180021587  cmovnz  rax, rdi
0x18002158b  mov     [rsi], rax
0x18002158e  jmp     short loc_18002159B
0x180021590  mov     [rbp+var_38], 80070057h
0x180021597  mov     [rbp+var_32], ax
0x18002159b  mov     rcx, rbx; pv
0x18002159e  call    cs:__imp_CoTaskMemFree
0x1800215a4  mov     ebx, [rbp+var_38]
0x1800215a7  lea     rcx, [rbp+var_48]; this
0x1800215ab  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800215b0  lea     rcx, [rbp+var_38]; this
0x1800215b4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800215b9  mov     eax, ebx
0x1800215bb  add     rsp, 80h
0x1800215c2  pop     r15
0x1800215c4  pop     r14
0x1800215c6  pop     r12
0x1800215c8  pop     rdi
0x1800215c9  pop     rsi
0x1800215ca  pop     rbx
0x1800215cb  pop     rbp
0x1800215cc  retn
```
