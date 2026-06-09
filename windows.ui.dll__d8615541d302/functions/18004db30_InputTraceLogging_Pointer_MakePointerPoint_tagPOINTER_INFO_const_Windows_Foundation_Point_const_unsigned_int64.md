# InputTraceLogging::Pointer::MakePointerPoint(tagPOINTER_INFO const *,Windows::Foundation::Point const &,unsigned __int64,tagINPUT_TRANSFORM const *,bool)

- ea: `0x18004db30`
- end: `0x18004e0c7`
- name: `?MakePointerPoint@Pointer@InputTraceLogging@@SAXPEBUtagPOINTER_INFO@@AEBUPoint@Foundation@Windows@@_KPEBUtagINPUT_TRANSFORM@@_N@Z`
- size: `1431`
- prototype: `void __fastcall(const struct tagPOINTER_INFO *, const struct Windows::Foundation::Point *, unsigned __int64, const struct tagINPUT_TRANSFORM *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180031f04`

## callees

- `0x18004db30`
- `0x18005f330`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004db8a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004db8a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004dc96`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004dc96`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18004dc5f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18004dc5f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004e099`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004e099`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18004dc44`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18004dc44`

## pseudocode

```c
void __fastcall InputTraceLogging::Pointer::MakePointerPoint(
        const struct tagPOINTER_INFO *a1,
        const struct Windows::Foundation::Point *a2,
        __int64 a3,
        const struct tagINPUT_TRANSFORM *a4,
        bool a5)
{
  _QWORD *v9; // rbx
  ULONGLONG *v10; // r9
  __int64 v11; // r10
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  const char *v17; // rcx
  __int64 v18; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+4Ch] [rbp-B4h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+5Ch] [rbp-A4h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+64h] [rbp-9Ch] BYREF
  int v31; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+6Ch] [rbp-94h] BYREF
  int v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+74h] [rbp-8Ch] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+7Ch] [rbp-84h] BYREF
  int v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+84h] [rbp-7Ch] BYREF
  int v39; // [rsp+88h] [rbp-78h] BYREF
  int v40; // [rsp+8Ch] [rbp-74h] BYREF
  int v41; // [rsp+90h] [rbp-70h] BYREF
  int v42; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h] BYREF
  GUID ProviderId; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  char *v48; // [rsp+D0h] [rbp-30h]
  int v49; // [rsp+D8h] [rbp-28h]
  int v50; // [rsp+DCh] [rbp-24h]
  __int64 *v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  int *v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  const char *v55; // [rsp+100h] [rbp+0h]
  int v56; // [rsp+108h] [rbp+8h]
  int v57; // [rsp+10Ch] [rbp+Ch]
  int *v58; // [rsp+110h] [rbp+10h]
  __int64 v59; // [rsp+118h] [rbp+18h]
  int *v60; // [rsp+120h] [rbp+20h]
  __int64 v61; // [rsp+128h] [rbp+28h]
  int *v62; // [rsp+130h] [rbp+30h]
  __int64 v63; // [rsp+138h] [rbp+38h]
  __int64 *v64; // [rsp+140h] [rbp+40h]
  __int64 v65; // [rsp+148h] [rbp+48h]
  int *v66; // [rsp+150h] [rbp+50h]
  __int64 v67; // [rsp+158h] [rbp+58h]
  int *v68; // [rsp+160h] [rbp+60h]
  __int64 v69; // [rsp+168h] [rbp+68h]
  __int64 *v70; // [rsp+170h] [rbp+70h]
  __int64 v71; // [rsp+178h] [rbp+78h]
  int *v72; // [rsp+180h] [rbp+80h]
  __int64 v73; // [rsp+188h] [rbp+88h]
  int *v74; // [rsp+190h] [rbp+90h]
  __int64 v75; // [rsp+198h] [rbp+98h]
  int *v76; // [rsp+1A0h] [rbp+A0h]
  __int64 v77; // [rsp+1A8h] [rbp+A8h]
  int *v78; // [rsp+1B0h] [rbp+B0h]
  __int64 v79; // [rsp+1B8h] [rbp+B8h]
  int *v80; // [rsp+1C0h] [rbp+C0h]
  __int64 v81; // [rsp+1C8h] [rbp+C8h]
  int *v82; // [rsp+1D0h] [rbp+D0h]
  __int64 v83; // [rsp+1D8h] [rbp+D8h]
  int *v84; // [rsp+1E0h] [rbp+E0h]
  __int64 v85; // [rsp+1E8h] [rbp+E8h]
  int *v86; // [rsp+1F0h] [rbp+F0h]
  __int64 v87; // [rsp+1F8h] [rbp+F8h]
  int *v88; // [rsp+200h] [rbp+100h]
  __int64 v89; // [rsp+208h] [rbp+108h]
  int *v90; // [rsp+210h] [rbp+110h]
  __int64 v91; // [rsp+218h] [rbp+118h]
  int *v92; // [rsp+220h] [rbp+120h]
  __int64 v93; // [rsp+228h] [rbp+128h]
  int *v94; // [rsp+230h] [rbp+130h]
  __int64 v95; // [rsp+238h] [rbp+138h]
  int *v96; // [rsp+240h] [rbp+140h]
  __int64 v97; // [rsp+248h] [rbp+148h]
  int *v98; // [rsp+250h] [rbp+150h]
  __int64 v99; // [rsp+258h] [rbp+158h]
  int *v100; // [rsp+260h] [rbp+160h]
  __int64 v101; // [rsp+268h] [rbp+168h]
  int *v102; // [rsp+270h] [rbp+170h]
  __int64 v103; // [rsp+278h] [rbp+178h]
  WINBOOL *p_fPending; // [rsp+280h] [rbp+180h]
  __int64 v105; // [rsp+288h] [rbp+188h]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    Context = &qword_1801353C8;
    qword_1801353C8 = &PopupMenuTelemetry::`vftable';
    qword_1801353D0 = 0;
    byte_1801353D8 = 0;
    dword_1801353DC = 0;
    CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_a8e7baa2fca040c17c3e795f3590cb07_::_lambda_invoker_cdecl_);
    v9 = CallbackContext;
    qword_1801353D0 = (__int64)CallbackContext;
    byte_1801353D8 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v10 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v9[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v9, v10) )
      EventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
    dword_1801353DC = 1;
    (*(void (__fastcall **)(void *))(qword_1801353C8 + 8LL))(&qword_1801353C8);
    InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1801353C8);
  }
  v11 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v11 > 5u
    && (*(_QWORD *)(v11 + 16) & 0x20) != 0
    && (*(_QWORD *)(v11 + 24) & 0x20LL) == *(_QWORD *)(v11 + 24) )
  {
    v12 = *(_DWORD *)a1;
    fPending = a5;
    v21 = *((_DWORD *)a4 + 15);
    v22 = *((_DWORD *)a4 + 14);
    v23 = *((_DWORD *)a4 + 13);
    v24 = *((_DWORD *)a4 + 12);
    v25 = *((_DWORD *)a4 + 11);
    v26 = *((_DWORD *)a4 + 10);
    v27 = *((_DWORD *)a4 + 9);
    v28 = *((_DWORD *)a4 + 8);
    v29 = *((_DWORD *)a4 + 7);
    v30 = *((_DWORD *)a4 + 6);
    v31 = *((_DWORD *)a4 + 5);
    v32 = *((_DWORD *)a4 + 4);
    v33 = *((_DWORD *)a4 + 3);
    v34 = *((_DWORD *)a4 + 2);
    v35 = *((_DWORD *)a4 + 1);
    v36 = *(_DWORD *)a4;
    v37 = *((_DWORD *)a2 + 1);
    v38 = *(_DWORD *)a2;
    v44 = *((_QWORD *)a1 + 3);
    v39 = *((_DWORD *)a1 + 9);
    v40 = *((_DWORD *)a1 + 8);
    v41 = *((_DWORD *)a1 + 3);
    v43 = a3;
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 == 1 )
              v17 = "Touchpad";
            else
              v17 = "UNKNOWN";
          }
          else
          {
            v17 = "Mouse";
          }
        }
        else
        {
          v17 = "Pen";
        }
      }
      else
      {
        v17 = "Touch";
      }
    }
    else
    {
      v17 = "Pointer";
    }
    v42 = *((_DWORD *)a1 + 1);
    v45 = *((_QWORD *)a1 + 10);
    p_fPending = &fPending;
    v102 = &v21;
    v100 = &v22;
    v98 = &v23;
    v96 = &v24;
    v94 = &v25;
    v92 = &v26;
    v90 = &v27;
    v88 = &v28;
    v86 = &v29;
    v84 = &v30;
    v82 = &v31;
    v80 = &v32;
    v78 = &v33;
    v76 = &v34;
    v74 = &v35;
    v72 = &v36;
    v70 = &v43;
    v68 = &v37;
    v66 = &v38;
    v64 = &v44;
    v62 = &v39;
    v60 = &v40;
    v58 = &v41;
    v18 = -1;
    v105 = 4;
    v103 = 4;
    v101 = 4;
    v99 = 4;
    v97 = 4;
    v95 = 4;
    v93 = 4;
    v91 = 4;
    v89 = 4;
    v87 = 4;
    v85 = 4;
    v83 = 4;
    v81 = 4;
    v79 = 4;
    v77 = 4;
    v75 = 4;
    v73 = 4;
    v71 = 8;
    v69 = 4;
    v67 = 4;
    v65 = 8;
    v63 = 4;
    v61 = 4;
    v59 = 4;
    do
      ++v18;
    while ( v17[v18] );
    v55 = v17;
    v56 = v18 + 1;
    v57 = 0;
    v53 = &v42;
    v54 = 4;
    v51 = &v45;
    *(_DWORD *)&ProviderId.Data2 = 5;
    UserData.Ptr = *(_QWORD *)(v11 + 8);
    v52 = 8;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 32;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v48 = &byte_18012196F;
    UserData.Reserved = 2;
    v49 = 259;
    v50 = 1;
    LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v11 + 32), (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 0x1Du, &UserData);
  }
}

```

## disassembly

```asm
0x18004db30  mov     [rsp-8+arg_10], rdi
0x18004db35  push    rbp
0x18004db36  push    r12
0x18004db38  push    r13
0x18004db3a  push    r14
0x18004db3c  push    r15
0x18004db3e  lea     rbp, [rsp-1A0h]
0x18004db46  sub     rsp, 2A0h
0x18004db4d  mov     rax, cs:__security_cookie
0x18004db54  xor     rax, rsp
0x18004db57  mov     [rbp+1C0h+var_30], rax
0x18004db5e  mov     rdi, r9
0x18004db61  mov     r12, r8
0x18004db64  mov     r15, rdx
0x18004db67  lea     r9, [rsp+2C0h+Context]; lpContext
0x18004db6c  mov     r14, rcx
0x18004db6f  lea     r8, [rsp+2C0h+fPending]; fPending
0x18004db74  xor     r13d, r13d
0x18004db77  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18004db7e  xor     edx, edx; dwFlags
0x18004db80  mov     [rsp+2C0h+Context], r13
0x18004db85  mov     [rsp+2C0h+fPending], r13d
0x18004db8a  call    cs:__imp_InitOnceBeginInitialize
0x18004db90  test    eax, eax
0x18004db92  jz      loc_18004DCAC
0x18004db98  cmp     [rsp+2C0h+fPending], r13d
0x18004db9d  jz      loc_18004DCAC
0x18004dba3  lea     rax, qword_1801353C8
0x18004dbaa  mov     [rsp+2C0h+arg_0], rbx
0x18004dbb2  mov     [rsp+2C0h+Context], rax
0x18004dbb7  lea     rax, ??_7PopupMenuTelemetry@@6B@; const PopupMenuTelemetry::`vftable'
0x18004dbbe  mov     cs:qword_1801353C8, rax
0x18004dbc5  mov     [rsp+2C0h+arg_8], rsi
0x18004dbcd  mov     cs:qword_1801353D0, r13
0x18004dbd4  mov     cs:byte_1801353D8, r13b
0x18004dbdb  mov     cs:dword_1801353DC, r13d
0x18004dbe2  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18004dbe9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a8e7baa2fca040c17c3e795f3590cb07_@@CA@XZ; void (__cdecl *)()
0x18004dbf0  mov     cs:CallbackContext, rax
0x18004dbf7  call    atexit
0x18004dbfc  mov     rbx, cs:CallbackContext
0x18004dc03  mov     cs:qword_1801353D0, rbx
0x18004dc0a  mov     cs:byte_1801353D8, 1
0x18004dc11  mov     rax, [rbx+8]
0x18004dc15  movups  xmm0, xmmword ptr [rax-10h]
0x18004dc19  movups  xmmword ptr [rbp+1C0h+ProviderId.Data1], xmm0
0x18004dc1d  cmp     [rbx+20h], r13
0x18004dc21  jz      short loc_18004DC2A
0x18004dc23  mov     ecx, 5
0x18004dc28  int     29h; Win8: RtlFailFast(ecx)
0x18004dc2a  lea     r9, [rbx+20h]; RegHandle
0x18004dc2e  mov     [rbx+28h], r13
0x18004dc32  mov     r8, rbx; CallbackContext
0x18004dc35  mov     [rbx+30h], r13
0x18004dc39  lea     rdx, _tlgEnableCallback; EnableCallback
0x18004dc40  lea     rcx, [rbp+1C0h+ProviderId]; ProviderId
0x18004dc44  call    cs:__imp_EventRegister
0x18004dc4a  test    eax, eax
0x18004dc4c  jnz     short loc_18004DC65
0x18004dc4e  mov     r8, [rbx+8]
0x18004dc52  mov     edx, 2
0x18004dc57  mov     rcx, [rbx+20h]
0x18004dc5b  movzx   r9d, word ptr [r8]
0x18004dc5f  call    cs:__imp_EventSetInformation
0x18004dc65  mov     rax, cs:qword_1801353C8
0x18004dc6c  lea     rcx, qword_1801353C8
0x18004dc73  mov     cs:dword_1801353DC, 1
0x18004dc7d  mov     rax, [rax+8]
0x18004dc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc86  lea     r8, qword_1801353C8; lpContext
0x18004dc8d  xor     edx, edx; dwFlags
0x18004dc8f  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18004dc96  call    cs:__imp_InitOnceComplete
0x18004dc9c  mov     rsi, [rsp+2C0h+arg_8]
0x18004dca4  mov     rbx, [rsp+2C0h+arg_0]
0x18004dcac  mov     rax, [rsp+2C0h+Context]
0x18004dcb1  mov     r10, [rax+8]
0x18004dcb5  mov     eax, [r10]
0x18004dcb8  cmp     eax, 5
0x18004dcbb  jbe     loc_18004E09F
0x18004dcc1  mov     rcx, [r10+18h]
0x18004dcc5  mov     rax, [r10+10h]
0x18004dcc9  test    al, 20h
0x18004dccb  jz      loc_18004E09F
0x18004dcd1  mov     rax, rcx
0x18004dcd4  and     eax, 20h
0x18004dcd7  cmp     rax, rcx
0x18004dcda  jnz     loc_18004E09F
0x18004dce0  movzx   eax, [rbp+1C0h+arg_20]
0x18004dce7  mov     ecx, [r14]
0x18004dcea  mov     [rsp+2C0h+fPending], eax
0x18004dcee  mov     eax, [rdi+3Ch]
0x18004dcf1  mov     [rsp+2C0h+var_280], eax
0x18004dcf5  mov     eax, [rdi+38h]
0x18004dcf8  mov     [rsp+2C0h+var_27C], eax
0x18004dcfc  mov     eax, [rdi+34h]
0x18004dcff  mov     [rsp+2C0h+var_278], eax
0x18004dd03  mov     eax, [rdi+30h]
0x18004dd06  mov     [rsp+2C0h+var_274], eax
0x18004dd0a  mov     eax, [rdi+2Ch]
0x18004dd0d  mov     [rsp+2C0h+var_270], eax
0x18004dd11  mov     eax, [rdi+28h]
0x18004dd14  mov     [rsp+2C0h+var_26C], eax
0x18004dd18  mov     eax, [rdi+24h]
0x18004dd1b  mov     [rsp+2C0h+var_268], eax
0x18004dd1f  mov     eax, [rdi+20h]
0x18004dd22  mov     [rsp+2C0h+var_264], eax
0x18004dd26  mov     eax, [rdi+1Ch]
0x18004dd29  mov     [rsp+2C0h+var_260], eax
0x18004dd2d  mov     eax, [rdi+18h]
0x18004dd30  mov     [rsp+2C0h+var_25C], eax
0x18004dd34  mov     eax, [rdi+14h]
0x18004dd37  mov     [rsp+2C0h+var_258], eax
0x18004dd3b  mov     eax, [rdi+10h]
0x18004dd3e  mov     [rsp+2C0h+var_254], eax
0x18004dd42  mov     eax, [rdi+0Ch]
0x18004dd45  mov     [rsp+2C0h+var_250], eax
0x18004dd49  mov     eax, [rdi+8]
0x18004dd4c  mov     [rsp+2C0h+var_24C], eax
0x18004dd50  mov     eax, [rdi+4]
0x18004dd53  mov     [rsp+2C0h+var_248], eax
0x18004dd57  mov     eax, [rdi]
0x18004dd59  mov     [rsp+2C0h+var_244], eax
0x18004dd5d  mov     eax, [r15+4]
0x18004dd61  mov     [rbp+1C0h+var_240], eax
0x18004dd64  mov     eax, [r15]
0x18004dd67  mov     [rbp+1C0h+var_23C], eax
0x18004dd6a  mov     rax, [r14+18h]
0x18004dd6e  mov     [rbp+1C0h+var_220], rax
0x18004dd72  mov     eax, [r14+24h]
0x18004dd76  mov     [rbp+1C0h+var_238], eax
0x18004dd79  mov     eax, [r14+20h]
0x18004dd7d  mov     [rbp+1C0h+var_234], eax
0x18004dd80  mov     eax, [r14+0Ch]
0x18004dd84  mov     [rbp+1C0h+var_230], eax
0x18004dd87  mov     [rbp+1C0h+var_228], r12
0x18004dd8b  sub     ecx, 1
0x18004dd8e  jz      short loc_18004DDD1
0x18004dd90  sub     ecx, 1
0x18004dd93  jz      short loc_18004DDC8
0x18004dd95  sub     ecx, 1
0x18004dd98  jz      short loc_18004DDBF
0x18004dd9a  sub     ecx, 1
0x18004dd9d  jz      short loc_18004DDB6
0x18004dd9f  cmp     ecx, 1
0x18004dda2  jz      short loc_18004DDAD
0x18004dda4  lea     rcx, aUnknown; "UNKNOWN"
0x18004ddab  jmp     short loc_18004DDD8
0x18004ddad  lea     rcx, aTouchpad; "Touchpad"
0x18004ddb4  jmp     short loc_18004DDD8
0x18004ddb6  lea     rcx, aMouse; "Mouse"
0x18004ddbd  jmp     short loc_18004DDD8
0x18004ddbf  lea     rcx, aPen; "Pen"
0x18004ddc6  jmp     short loc_18004DDD8
0x18004ddc8  lea     rcx, aTouch; "Touch"
0x18004ddcf  jmp     short loc_18004DDD8
0x18004ddd1  lea     rcx, aPointer; "Pointer"
0x18004ddd8  mov     eax, [r14+4]
0x18004dddc  mov     [rbp+1C0h+var_22C], eax
0x18004dddf  mov     rax, [r14+50h]
0x18004dde3  mov     [rbp+1C0h+var_218], rax
0x18004dde7  lea     rax, [rsp+2C0h+fPending]
0x18004ddec  mov     [rbp+1C0h+var_40], rax
0x18004ddf3  lea     rax, [rsp+2C0h+var_280]
0x18004ddf8  mov     [rbp+1C0h+var_50], rax
0x18004ddff  lea     rax, [rsp+2C0h+var_27C]
0x18004de04  mov     [rbp+1C0h+var_60], rax
0x18004de0b  lea     rax, [rsp+2C0h+var_278]
0x18004de10  mov     [rbp+1C0h+var_70], rax
0x18004de17  lea     rax, [rsp+2C0h+var_274]
0x18004de1c  mov     [rbp+1C0h+var_80], rax
0x18004de23  lea     rax, [rsp+2C0h+var_270]
0x18004de28  mov     [rbp+1C0h+var_90], rax
0x18004de2f  lea     rax, [rsp+2C0h+var_26C]
0x18004de34  mov     [rbp+1C0h+var_A0], rax
0x18004de3b  lea     rax, [rsp+2C0h+var_268]
0x18004de40  mov     [rbp+1C0h+var_B0], rax
0x18004de47  lea     rax, [rsp+2C0h+var_264]
0x18004de4c  mov     [rbp+1C0h+var_C0], rax
0x18004de53  lea     rax, [rsp+2C0h+var_260]
0x18004de58  mov     [rbp+1C0h+var_D0], rax
0x18004de5f  lea     rax, [rsp+2C0h+var_25C]
0x18004de64  mov     [rbp+1C0h+var_E0], rax
0x18004de6b  lea     rax, [rsp+2C0h+var_258]
0x18004de70  mov     [rbp+1C0h+var_F0], rax
0x18004de77  lea     rax, [rsp+2C0h+var_254]
0x18004de7c  mov     [rbp+1C0h+var_100], rax
0x18004de83  lea     rax, [rsp+2C0h+var_250]
0x18004de88  mov     [rbp+1C0h+var_110], rax
0x18004de8f  lea     rax, [rsp+2C0h+var_24C]
0x18004de94  mov     [rbp+1C0h+var_120], rax
0x18004de9b  lea     rax, [rsp+2C0h+var_248]
0x18004dea0  mov     [rbp+1C0h+var_130], rax
0x18004dea7  lea     rax, [rsp+2C0h+var_244]
0x18004deac  mov     [rbp+1C0h+var_140], rax
0x18004deb3  lea     rax, [rbp+1C0h+var_228]
0x18004deb7  mov     [rbp+1C0h+var_150], rax
0x18004debb  lea     rax, [rbp+1C0h+var_240]
0x18004debf  mov     [rbp+1C0h+var_160], rax
0x18004dec3  lea     rax, [rbp+1C0h+var_23C]
0x18004dec7  mov     [rbp+1C0h+var_170], rax
0x18004decb  lea     rax, [rbp+1C0h+var_220]
0x18004decf  mov     [rbp+1C0h+var_180], rax
0x18004ded3  lea     rax, [rbp+1C0h+var_238]
0x18004ded7  mov     [rbp+1C0h+var_190], rax
0x18004dedb  lea     rax, [rbp+1C0h+var_234]
0x18004dedf  mov     [rbp+1C0h+var_1A0], rax
0x18004dee3  lea     rax, [rbp+1C0h+var_230]
0x18004dee7  mov     [rbp+1C0h+var_1B0], rax
0x18004deeb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004def2  mov     [rbp+1C0h+var_38], 4
0x18004defd  mov     [rbp+1C0h+var_48], 4
0x18004df08  mov     [rbp+1C0h+var_58], 4
0x18004df13  mov     [rbp+1C0h+var_68], 4
0x18004df1e  mov     [rbp+1C0h+var_78], 4
0x18004df29  mov     [rbp+1C0h+var_88], 4
0x18004df34  mov     [rbp+1C0h+var_98], 4
0x18004df3f  mov     [rbp+1C0h+var_A8], 4
0x18004df4a  mov     [rbp+1C0h+var_B8], 4
0x18004df55  mov     [rbp+1C0h+var_C8], 4
0x18004df60  mov     [rbp+1C0h+var_D8], 4
0x18004df6b  mov     [rbp+1C0h+var_E8], 4
0x18004df76  mov     [rbp+1C0h+var_F8], 4
0x18004df81  mov     [rbp+1C0h+var_108], 4
0x18004df8c  mov     [rbp+1C0h+var_118], 4
0x18004df97  mov     [rbp+1C0h+var_128], 4
0x18004dfa2  mov     [rbp+1C0h+var_138], 4
0x18004dfad  mov     [rbp+1C0h+var_148], 8
0x18004dfb5  mov     [rbp+1C0h+var_158], 4
0x18004dfbd  mov     [rbp+1C0h+var_168], 4
0x18004dfc5  mov     [rbp+1C0h+var_178], 8
0x18004dfcd  mov     [rbp+1C0h+var_188], 4
0x18004dfd5  mov     [rbp+1C0h+var_198], 4
0x18004dfdd  mov     [rbp+1C0h+var_1A8], 4
0x18004dfe5  inc     rax
0x18004dfe8  cmp     [rcx+rax], r13b
0x18004dfec  jnz     short loc_18004DFE5
0x18004dfee  inc     eax
0x18004dff0  mov     [rbp+1C0h+var_1C0], rcx
0x18004dff4  mov     [rbp+1C0h+var_1B8], eax
0x18004dff7  lea     rcx, _TraceLoggingMetadata
0x18004dffe  mov     [rbp+1C0h+var_1B4], r13d
0x18004e002  lea     rax, [rbp+1C0h+var_22C]
0x18004e006  mov     [rbp+1C0h+var_1D0], rax
0x18004e00a  lea     rdx, [rbp+1C0h+ProviderId]; EventDescriptor
0x18004e00e  lea     rax, [rbp+1C0h+var_218]
0x18004e012  mov     [rbp+1C0h+var_1C8], 4
0x18004e01a  mov     [rbp+1C0h+var_1E0], rax
0x18004e01e  xor     r9d, r9d; RelatedActivityId
0x18004e021  movzx   eax, cs:word_180121965
0x18004e028  xor     r8d, r8d; ActivityId
0x18004e02b  mov     dword ptr [rbp+1C0h+ProviderId.Data2], eax
0x18004e02e  mov     rax, [r10+8]
0x18004e032  mov     [rbp+1C0h+var_200.Ptr], rax
0x18004e036  mov     [rbp+1C0h+var_1D8], 8
0x18004e03e  mov     [rbp+1C0h+ProviderId.Data1], 0B000000h
0x18004e045  mov     qword ptr [rbp+1C0h+ProviderId.Data4], 20h ; ' '
0x18004e04d  movzx   eax, word ptr [rax]
0x18004e050  mov     [rbp+1C0h+var_200.Size], eax
0x18004e053  lea     rax, byte_18012196F
0x18004e05a  mov     [rbp+1C0h+var_1F0], rax
0x18004e05e  lea     rax, _TraceLoggingMetadataEnd
0x18004e065  sub     eax, ecx
0x18004e067  mov     dword ptr [rbp+1C0h+var_200.0Ch], 2
0x18004e06e  mov     [rbp+1C0h+var_1E8], 103h
0x18004e075  mov     [rbp+1C0h+var_1E4], 1
0x18004e07c  mov     dword ptr [rsp+2C0h+Context], eax
0x18004e080  mov     eax, dword ptr [rsp+2C0h+Context]
0x18004e084  mov     rcx, [r10+20h]; RegHandle
0x18004e088  lea     rax, [rbp+1C0h+var_200]
0x18004e08c  mov     [rsp+2C0h+UserData], rax; UserData
0x18004e091  mov     [rsp+2C0h+UserDataCount], 1Dh; UserDataCount
0x18004e099  call    cs:__imp_EventWriteTransfer
0x18004e09f  mov     rcx, [rbp+1C0h+var_30]
0x18004e0a6  xor     rcx, rsp; StackCookie
0x18004e0a9  call    __security_check_cookie
0x18004e0ae  mov     rdi, [rsp+2C0h+arg_10]
0x18004e0b6  add     rsp, 2A0h
0x18004e0bd  pop     r15
0x18004e0bf  pop     r14
0x18004e0c1  pop     r13
0x18004e0c3  pop     r12
0x18004e0c5  pop     rbp
0x18004e0c6  retn
```
