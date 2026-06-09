# SxStartTracing(ushort const *,ushort const *,ulong,unsigned __int64 *,ushort * *)

- ea: `0x14000fa1c`
- end: `0x14000fd05`
- name: `?SxStartTracing@@YAJPEBG0KPEA_KPEAPEAG@Z`
- size: `745`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int64 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1400039e4`

## callees

- `0x140002e1c`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ec40`
- `0x14000f24c`
- `0x14000fa1c`
- `0x140010168`
- `0x140010744`

## import_xrefs

- `ADVAPI32!StartTraceW` at `0x14000fc83`
- `ADVAPI32!StartTraceW` at `0x14000fc83`
- `ole32!CoTaskMemFree` at `0x14000fcd6`
- `ole32!CoTaskMemFree` at `0x14000fcd6`

## string_xrefs

- `0x14000fc79`: `BuiltInSrTasksTracing`

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
  __int64 v21; // rdx
  __int64 v22; // r8
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v25; // [rsp+38h] [rbp-48h] BYREF
  __int64 v26; // [rsp+40h] [rbp-40h]
  signed int v27; // [rsp+48h] [rbp-38h] BYREF
  __int16 v28; // [rsp+4Ch] [rbp-34h]
  __int16 v29; // [rsp+4Eh] [rbp-32h]
  const unsigned __int16 *v30; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v32; // [rsp+D8h] [rbp+58h] BYREF

  v31 = a3;
  v30 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SxStartTracing", 532, 1);
  LODWORD(v30) = 0;
  v7 = 0;
  Properties = 0;
  v31 = 0;
  v32 = 0;
  v25 = qword_140013960;
  v26 = 0;
  if ( a4 )
    *a4 = -1;
  v8 = a5;
  if ( a5 )
    *a5 = 0;
  v28 = 548;
  v9 = 549;
  if ( !a4 || (v28 = 549, v9 = 550, !a2) )
  {
    v27 = -2147024809;
    goto LABEL_36;
  }
  v27 = 0;
  v28 = 550;
  v27 = SxGet0XLogFileCount(a2, (unsigned int *)&v30, &v31, &v32);
  v9 = 559;
  if ( v27 < 0 )
  {
LABEL_36:
    v29 = v9;
    goto LABEL_37;
  }
  v28 = 559;
  if ( (_DWORD)v30 )
  {
    if ( !v31 )
    {
      v27 = CBsString::Format((CBsString *)&v25, (wchar_t *)L"%s.0.1.%s", a2, L"etl");
      v10 = v27 < 0;
      v9 = 577;
      goto LABEL_17;
    }
    goto LABEL_15;
  }
  if ( v31 )
  {
LABEL_15:
    v27 = CBsString::Format((CBsString *)&v25, (wchar_t *)L"%s.0.%d.%s", a2);
    v10 = v27 < 0;
    v9 = 572;
    goto LABEL_17;
  }
  v27 = CBsString::Format((CBsString *)&v25, (wchar_t *)L"%s.0.%s", a2, L"etl");
  v10 = v27 < 0;
  v9 = 563;
LABEL_17:
  if ( v10 )
    goto LABEL_36;
  v28 = v9;
  v11 = SxAllocateEventTraceProp(&Properties);
  v7 = Properties;
  v10 = v11 < 0;
  v27 = v11;
  v9 = 580;
  if ( v10 )
    goto LABEL_36;
  v12 = v25;
  v13 = 2147483646;
  v28 = 580;
  v14 = v25;
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
  v27 = v15 == 0 ? 0x8007007A : 0;
  if ( !v15 )
    goto LABEL_36;
  v28 = 588;
  started = StartTraceW(a4, L"BuiltInSrTasksTracing", v7);
  if ( started == 183 )
    goto LABEL_31;
  if ( started > 0 )
    started = (unsigned __int16)started | 0x80070000;
  v27 = started;
  v10 = started < 0;
  v9 = 594;
  if ( v10 )
    goto LABEL_36;
  v28 = 594;
LABEL_31:
  if ( v8 )
  {
    v25 = qword_140013960;
    v19 = 0;
    v26 = 0;
    if ( v12 != qword_140013960 )
      v19 = v12;
    *v8 = (unsigned __int16 *)v19;
  }
LABEL_37:
  CoTaskMemFree(v7);
  v20 = v27;
  CBsString::_Release((LPVOID *)&v25);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27, v21, v22);
  return v20;
}

```

## disassembly

```asm
0x14000fa1c  mov     [rsp-38h+arg_10], r8d
0x14000fa21  mov     [rsp-38h+arg_0], rcx
0x14000fa26  push    rbp
0x14000fa27  push    rbx
0x14000fa28  push    rsi
0x14000fa29  push    rdi
0x14000fa2a  push    r12
0x14000fa2c  push    r14
0x14000fa2e  push    r15
0x14000fa30  mov     rbp, rsp
0x14000fa33  sub     rsp, 80h
0x14000fa3a  mov     r14, r9
0x14000fa3d  mov     rdi, rdx
0x14000fa40  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa47  lea     rax, WPP_GLOBAL_Control
0x14000fa4e  cmp     rcx, rax
0x14000fa51  jz      short loc_14000FA71
0x14000fa53  test    dword ptr [rcx+1Ch], 20000000h
0x14000fa5a  jz      short loc_14000FA71
0x14000fa5c  mov     rcx, [rcx+10h]
0x14000fa60  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x14000fa67  mov     edx, 15h
0x14000fa6c  call    WPP_SF_
0x14000fa71  mov     r9d, 1; unsigned __int16
0x14000fa77  lea     rdx, aSxstarttracing; "SxStartTracing"
0x14000fa7e  mov     r8d, 214h; unsigned __int16
0x14000fa84  lea     rcx, [rbp+var_38]; this
0x14000fa88  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000fa8d  xor     r15d, r15d
0x14000fa90  lea     r12, qword_140013960
0x14000fa97  mov     dword ptr [rbp+arg_0], r15d
0x14000fa9b  mov     ebx, r15d
0x14000fa9e  mov     [rbp+Properties], rbx
0x14000faa2  mov     [rbp+arg_10], r15d
0x14000faa6  mov     [rbp+arg_18], r15d
0x14000faaa  mov     [rbp+var_48], r12
0x14000faae  mov     [rbp+var_40], r15
0x14000fab2  test    r14, r14
0x14000fab5  jz      short loc_14000FABE
0x14000fab7  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x14000fabe  mov     rsi, [rbp+arg_20]
0x14000fac2  test    rsi, rsi
0x14000fac5  jz      short loc_14000FACA
0x14000fac7  mov     [rsi], r15
0x14000faca  mov     eax, 224h
0x14000facf  mov     [rbp+var_34], ax
0x14000fad3  mov     eax, 225h
0x14000fad8  test    r14, r14
0x14000fadb  jz      loc_14000FCC8
0x14000fae1  mov     [rbp+var_34], ax
0x14000fae5  mov     eax, 226h
0x14000faea  test    rdi, rdi
0x14000faed  jz      loc_14000FCC8
0x14000faf3  lea     r9, [rbp+arg_18]; unsigned int *
0x14000faf7  mov     [rbp+var_38], r15d
0x14000fafb  lea     r8, [rbp+arg_10]; unsigned int *
0x14000faff  mov     [rbp+var_34], ax
0x14000fb03  lea     rdx, [rbp+arg_0]; unsigned int *
0x14000fb07  mov     rcx, rdi; unsigned __int16 *
0x14000fb0a  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x14000fb0f  mov     [rbp+var_38], eax
0x14000fb12  test    eax, eax
0x14000fb14  mov     eax, 22Fh
0x14000fb19  js      loc_14000FCCF
0x14000fb1f  mov     [rbp+var_34], ax
0x14000fb23  mov     eax, [rbp+arg_10]
0x14000fb26  cmp     dword ptr [rbp+arg_0], r15d
0x14000fb2a  jnz     short loc_14000FB56
0x14000fb2c  test    eax, eax
0x14000fb2e  jnz     short loc_14000FB5A
0x14000fb30  lea     r9, aEtl; "etl"
0x14000fb37  mov     r8, rdi
0x14000fb3a  lea     rdx, aS0S; "%s.0.%s"
0x14000fb41  lea     rcx, [rbp+var_48]; this
0x14000fb45  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000fb4a  mov     [rbp+var_38], eax
0x14000fb4d  test    eax, eax
0x14000fb4f  mov     eax, 233h
0x14000fb54  jmp     short loc_14000FBB6
0x14000fb56  test    eax, eax
0x14000fb58  jz      short loc_14000FB92
0x14000fb5a  mov     r9d, [rbp+arg_18]
0x14000fb5e  cmp     r9d, 7
0x14000fb62  jnb     short loc_14000FB67
0x14000fb64  inc     r9d
0x14000fb67  lea     rax, aEtl; "etl"
0x14000fb6e  mov     r8, rdi
0x14000fb71  lea     rdx, aS0DS; "%s.0.%d.%s"
0x14000fb78  mov     [rsp+80h+var_60], rax
0x14000fb7d  lea     rcx, [rbp+var_48]; this
0x14000fb81  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000fb86  mov     [rbp+var_38], eax
0x14000fb89  test    eax, eax
0x14000fb8b  mov     eax, 23Ch
0x14000fb90  jmp     short loc_14000FBB6
0x14000fb92  lea     r9, aEtl; "etl"
0x14000fb99  mov     r8, rdi
0x14000fb9c  lea     rdx, aS01S; "%s.0.1.%s"
0x14000fba3  lea     rcx, [rbp+var_48]; this
0x14000fba7  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000fbac  mov     [rbp+var_38], eax
0x14000fbaf  test    eax, eax
0x14000fbb1  mov     eax, 241h
0x14000fbb6  js      loc_14000FCCF
0x14000fbbc  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x14000fbc0  mov     [rbp+var_34], ax
0x14000fbc4  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x14000fbc9  mov     rbx, [rbp+Properties]
0x14000fbcd  test    eax, eax
0x14000fbcf  mov     [rbp+var_38], eax
0x14000fbd2  mov     eax, 244h
0x14000fbd7  js      loc_14000FCCF
0x14000fbdd  mov     rdi, [rbp+var_48]
0x14000fbe1  mov     ecx, 7FFFFFFEh
0x14000fbe6  mov     [rbp+var_34], ax
0x14000fbea  mov     r8, rdi
0x14000fbed  mov     dword ptr [rbx+40h], 2
0x14000fbf4  mov     edx, 104h
0x14000fbf9  mov     dword ptr [rbx+30h], 40h ; '@'
0x14000fc00  mov     dword ptr [rbx+34h], 3
0x14000fc07  mov     dword ptr [rbx+38h], 6
0x14000fc0e  mov     dword ptr [rbx+3Ch], 0Ah
0x14000fc15  mov     dword ptr [rbx+44h], 0Fh
0x14000fc1c  mov     eax, [rbx+70h]
0x14000fc1f  add     rax, rbx
0x14000fc22  test    rcx, rcx
0x14000fc25  jz      short loc_14000FC46
0x14000fc27  movzx   r9d, word ptr [r8]
0x14000fc2b  test    r9w, r9w
0x14000fc2f  jz      short loc_14000FC46
0x14000fc31  mov     [rax], r9w
0x14000fc35  add     r8, 2
0x14000fc39  add     rax, 2
0x14000fc3d  dec     rcx
0x14000fc40  sub     rdx, 1
0x14000fc44  jnz     short loc_14000FC22
0x14000fc46  lea     rcx, [rax-2]
0x14000fc4a  test    rdx, rdx
0x14000fc4d  cmovnz  rcx, rax
0x14000fc51  mov     rax, rdx
0x14000fc54  neg     rax
0x14000fc57  mov     eax, 24Ch
0x14000fc5c  mov     [rcx], r15w
0x14000fc60  sbb     ecx, ecx
0x14000fc62  not     ecx
0x14000fc64  and     ecx, 8007007Ah
0x14000fc6a  mov     [rbp+var_38], ecx
0x14000fc6d  test    rdx, rdx
0x14000fc70  jz      short loc_14000FCCF
0x14000fc72  mov     r8, rbx; Properties
0x14000fc75  mov     [rbp+var_34], ax
0x14000fc79  lea     rdx, aBuiltinsrtasks; "BuiltInSrTasksTracing"
0x14000fc80  mov     rcx, r14; TraceHandle
0x14000fc83  call    cs:__imp_StartTraceW
0x14000fc89  cmp     eax, 0B7h
0x14000fc8e  jz      short loc_14000FCAC
0x14000fc90  test    eax, eax
0x14000fc92  jle     short loc_14000FC9C
0x14000fc94  movzx   eax, ax
0x14000fc97  or      eax, 80070000h
0x14000fc9c  mov     [rbp+var_38], eax
0x14000fc9f  test    eax, eax
0x14000fca1  mov     eax, 252h
0x14000fca6  js      short loc_14000FCCF
0x14000fca8  mov     [rbp+var_34], ax
0x14000fcac  test    rsi, rsi
0x14000fcaf  jz      short loc_14000FCD3
0x14000fcb1  cmp     rdi, r12
0x14000fcb4  mov     [rbp+var_48], r12
0x14000fcb8  mov     rax, r15
0x14000fcbb  mov     [rbp+var_40], r15
0x14000fcbf  cmovnz  rax, rdi
0x14000fcc3  mov     [rsi], rax
0x14000fcc6  jmp     short loc_14000FCD3
0x14000fcc8  mov     [rbp+var_38], 80070057h
0x14000fccf  mov     [rbp+var_32], ax
0x14000fcd3  mov     rcx, rbx; pv
0x14000fcd6  call    cs:__imp_CoTaskMemFree
0x14000fcdc  mov     ebx, [rbp+var_38]
0x14000fcdf  lea     rcx, [rbp+var_48]; this
0x14000fce3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000fce8  lea     rcx, [rbp+var_38]; this
0x14000fcec  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000fcf1  mov     eax, ebx
0x14000fcf3  add     rsp, 80h
0x14000fcfa  pop     r15
0x14000fcfc  pop     r14
0x14000fcfe  pop     r12
0x14000fd00  pop     rdi
0x14000fd01  pop     rsi
0x14000fd02  pop     rbx
0x14000fd03  pop     rbp
0x14000fd04  retn
```
