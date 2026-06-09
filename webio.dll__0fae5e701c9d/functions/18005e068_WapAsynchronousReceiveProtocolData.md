# WapAsynchronousReceiveProtocolData

- ea: `0x18005e068`
- end: `0x18005e37a`
- name: `WapAsynchronousReceiveProtocolData`
- size: `786`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005e000`
- `0x18005ebf4`

## callees

- `0x1800180e0`
- `0x180018140`
- `0x180039e50`
- `0x180039f40`
- `0x18003a4a0`
- `0x18003a6d0`
- `0x18005e068`
- `0x18005e8a4`
- `0x18005e948`
- `0x18005e964`
- `0x18005ea04`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e130`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e130`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e17f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e1a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e17f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e1a9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005e2d1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005e2d1`

## pseudocode

```c
__int64 __fastcall WapAsynchronousReceiveProtocolData(
        GUID *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  char v8; // si
  int v10; // edi
  GUID *v11; // rax
  GUID *v12; // rbx
  int v13; // ecx
  unsigned int v14; // edi
  __int64 v15; // r8
  unsigned int v16; // eax
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  GUID *v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v24; // [rsp+80h] [rbp-80h] BYREF
  GUID v25; // [rsp+88h] [rbp-78h]
  GUID ActivityId; // [rsp+98h] [rbp-68h] BYREF
  int v27; // [rsp+A8h] [rbp-58h]
  GUID *v28; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+C0h] [rbp-40h] BYREF
  GUID **v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  GUID **v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  int *v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]
  __int64 *v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+108h] [rbp+8h]
  int *v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]
  __int64 *v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]
  __int64 *v42; // [rsp+130h] [rbp+30h]
  __int64 v43; // [rsp+138h] [rbp+38h]

  v23 = a5;
  v22 = a2;
  v8 = a2;
  v19 = a1;
  hObject = (HANDLE)-1LL;
  v10 = (int)a1;
  v27 = 0;
  v25 = 0;
  ActivityId = 0;
  v11 = (GUID *)WaMapHandleToObject(a1, 9, WaReferenceProtocolObject);
  v12 = v11;
  if ( !v11 )
    return 6;
  v25 = 0;
  v27 = 0;
  ActivityId = 0;
  v25 = v11[20];
  WapEtwBeginActivityId(v11 + 20);
  if ( (Microsoft_Windows_WebIOEnableBits & 0x400) != 0 )
    McTemplateU0pxqpqpq_EventWriteTransfer(v13, (unsigned int)ProtocolReceiveData, (_DWORD)v12, v10, v8, a3, a4, a7, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)v12->Data4);
  v14 = WaImpersonateSessionToken(*(_QWORD *)&v12[3].Data1, (__int64 *)&hObject);
  if ( !v14 )
  {
    if ( LOBYTE(v12[5].Data1) )
    {
      v14 = *(_DWORD *)&v12[5].Data2;
    }
    else if ( v12[13].Data4[0] )
    {
      v14 = 5023;
    }
    else
    {
      v14 = WapProtocolObjectTrackerCopyChunk(v12[13].Data4, a3, a4);
      if ( !v14 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&v12->Data2);
        *(_QWORD *)&v12[15].Data1 = a6;
        v12[13].Data4[0] = 1;
        *(_QWORD *)v12[15].Data4 = a7;
        LeaveCriticalSection((LPCRITICAL_SECTION)v12->Data4);
        if ( *(_QWORD *)v12[6].Data4 )
          v16 = WaProtocolCopyBufferedData(v12, v12[13].Data4, v23);
        else
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 (__fastcall *)(), unsigned __int8 *))(*(_QWORD *)v12[3].Data4 + 40LL))(
                  *(_QWORD *)&v12[4].Data1,
                  *(_QWORD *)&v12[14].Data1,
                  *(unsigned int *)v12[14].Data4,
                  v23,
                  WapReceiveProtocolDataCompletion,
                  v12[13].Data4);
        v14 = v16;
        if ( v16 != 997 )
          WaCompleteProtocolTracker(v12, v12[13].Data4, v16);
        goto LABEL_13;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v12->Data4);
LABEL_13:
  if ( (Microsoft_Windows_WebIOEnableBits & 0x400) != 0 )
  {
    v28 = v19;
    v30 = &v19;
    v32 = &v28;
    v34 = &v22;
    v36 = &v20;
    v38 = (int *)&v24;
    v40 = &v21;
    v42 = &v23;
    v35 = 4;
    v39 = 4;
    v43 = 4;
    LODWORD(v23) = v14;
    v21 = a7;
    v24 = a4;
    v20 = a3;
    v19 = v12;
    v31 = 8;
    v33 = 8;
    v37 = 8;
    v41 = 8;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      (const EVENT_DESCRIPTOR *)ProtocolReceiveDataCompleteInline,
      v15,
      8u,
      &v29);
  }
  WaDereferenceProtocolObject(v12);
  WaRestoreToken(hObject);
  if ( (_BYTE)v27 )
    EventActivityIdControl(2u, &ActivityId);
  return v14;
}

```

## disassembly

```asm
0x18005e068  mov     [rsp-8+arg_8], rbx
0x18005e06d  push    rbp
0x18005e06e  push    rsi
0x18005e06f  push    rdi
0x18005e070  push    r12
0x18005e072  push    r13
0x18005e074  push    r14
0x18005e076  push    r15
0x18005e078  lea     rbp, [rsp-50h]
0x18005e07d  sub     rsp, 150h
0x18005e084  mov     rax, cs:__security_cookie
0x18005e08b  xor     rax, rsp
0x18005e08e  mov     [rbp+80h+var_40], rax
0x18005e092  mov     rax, [rbp+80h+arg_20]
0x18005e099  xorps   xmm0, xmm0
0x18005e09c  mov     r15, [rbp+80h+arg_30]
0x18005e0a3  mov     r12, r8
0x18005e0a6  mov     [rsp+180h+var_108], rax
0x18005e0ab  lea     r8, WaReferenceProtocolObject
0x18005e0b2  xor     eax, eax
0x18005e0b4  mov     [rsp+180h+var_110], edx
0x18005e0b8  mov     esi, edx
0x18005e0ba  mov     [rsp+180h+var_128], rcx
0x18005e0bf  mov     r13d, r9d
0x18005e0c2  mov     [rsp+180h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005e0cb  mov     rdi, rcx
0x18005e0ce  mov     [rbp+80h+var_D8], eax
0x18005e0d1  lea     edx, [rax+9]
0x18005e0d4  movups  [rbp+80h+var_F8], xmm0
0x18005e0d8  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm0
0x18005e0dc  call    WaMapHandleToObject
0x18005e0e1  mov     rbx, rax
0x18005e0e4  test    rax, rax
0x18005e0e7  jz      loc_18005E339
0x18005e0ed  xorps   xmm0, xmm0
0x18005e0f0  lea     rcx, [rbx+140h]; ActivityId
0x18005e0f7  xor     eax, eax
0x18005e0f9  lea     r9, [rbp+80h+var_D8]
0x18005e0fd  movups  [rbp+80h+var_F8], xmm0
0x18005e101  mov     [rbp+80h+var_D8], eax
0x18005e104  lea     r8, [rbp+80h+ActivityId]
0x18005e108  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm0
0x18005e10c  lea     edx, [rax+5]
0x18005e10f  movups  xmm0, xmmword ptr [rcx]
0x18005e112  movdqu  [rbp+80h+var_F8], xmm0
0x18005e117  call    WapEtwBeginActivityId
0x18005e11c  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 4
0x18005e123  jnz     loc_18005E307
0x18005e129  lea     r14, [rbx+8]
0x18005e12d  mov     rcx, r14; lpCriticalSection
0x18005e130  call    cs:__imp_EnterCriticalSection
0x18005e137  nop     dword ptr [rax+rax+00h]
0x18005e13c  mov     rcx, [rbx+30h]
0x18005e140  lea     rdx, [rsp+180h+hObject]
0x18005e145  call    WaImpersonateSessionToken
0x18005e14a  mov     edi, eax
0x18005e14c  test    eax, eax
0x18005e14e  jnz     short loc_18005E17C
0x18005e150  cmp     [rbx+50h], al
0x18005e153  jnz     loc_18005E355
0x18005e159  lea     rsi, [rbx+0D8h]
0x18005e160  cmp     [rsi], al
0x18005e162  jnz     loc_18005E35D
0x18005e168  mov     r8d, r13d
0x18005e16b  mov     rdx, r12
0x18005e16e  mov     rcx, rsi
0x18005e171  call    WapProtocolObjectTrackerCopyChunk
0x18005e176  mov     edi, eax
0x18005e178  test    eax, eax
0x18005e17a  jz      short loc_18005E190
0x18005e17c  mov     rcx, r14; lpCriticalSection
0x18005e17f  call    cs:__imp_LeaveCriticalSection
0x18005e186  nop     dword ptr [rax+rax+00h]
0x18005e18b  xor     r14d, r14d
0x18005e18e  jmp     short loc_18005E1FE
0x18005e190  lock inc dword ptr [rbx+4]
0x18005e194  mov     rax, [rbp+80h+arg_28]
0x18005e19b  mov     [rsi+18h], rax
0x18005e19f  mov     byte ptr [rsi], 1
0x18005e1a2  mov     [rsi+20h], r15
0x18005e1a6  mov     rcx, r14; lpCriticalSection
0x18005e1a9  call    cs:__imp_LeaveCriticalSection
0x18005e1b0  nop     dword ptr [rax+rax+00h]
0x18005e1b5  xor     r14d, r14d
0x18005e1b8  cmp     [rbx+68h], r14
0x18005e1bc  ja      loc_18005E340
0x18005e1c2  mov     rax, [rbx+38h]
0x18005e1c6  lea     rcx, WapReceiveProtocolDataCompletion
0x18005e1cd  mov     r9, [rsp+180h+var_108]
0x18005e1d2  mov     r8d, [rsi+10h]
0x18005e1d6  mov     rdx, [rsi+8]
0x18005e1da  mov     rax, [rax+28h]
0x18005e1de  mov     [rsp+180h+var_158], rsi
0x18005e1e3  mov     [rsp+180h+var_160], rcx
0x18005e1e8  mov     rcx, [rbx+40h]
0x18005e1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1f1  mov     edi, eax
0x18005e1f3  cmp     eax, 3E5h
0x18005e1f8  jnz     loc_18005E367
0x18005e1fe  mov     ecx, 4
0x18005e203  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, cl
0x18005e209  jz      loc_18005E2B0
0x18005e20f  mov     eax, [rsp+180h+var_110]
0x18005e213  lea     r9d, [rcx+4]
0x18005e217  mov     [rsp+180h+var_110], eax
0x18005e21b  lea     rdx, ProtocolReceiveDataCompleteInline
0x18005e222  mov     rax, [rsp+180h+var_128]
0x18005e227  mov     [rbp+80h+var_D0], rax
0x18005e22b  lea     rax, [rsp+180h+var_128]
0x18005e230  mov     [rbp+80h+var_B0], rax
0x18005e234  lea     rax, [rbp+80h+var_D0]
0x18005e238  mov     [rbp+80h+var_A0], rax
0x18005e23c  lea     rax, [rsp+180h+var_110]
0x18005e241  mov     [rbp+80h+var_90], rax
0x18005e245  lea     rax, [rsp+180h+var_120]
0x18005e24a  mov     [rbp+80h+var_80], rax
0x18005e24e  lea     rax, [rbp+80h+var_100]
0x18005e252  mov     [rbp+80h+var_70], rax
0x18005e256  lea     rax, [rsp+180h+var_118]
0x18005e25b  mov     [rbp+80h+var_60], rax
0x18005e25f  lea     rax, [rsp+180h+var_108]
0x18005e264  mov     [rbp+80h+var_50], rax
0x18005e268  lea     rax, [rbp+80h+var_C0]
0x18005e26c  mov     [rbp+80h+var_88], rcx
0x18005e270  mov     [rbp+80h+var_68], rcx
0x18005e274  mov     [rbp+80h+var_48], rcx
0x18005e278  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18005e27f  mov     [rsp+180h+var_160], rax
0x18005e284  mov     dword ptr [rsp+180h+var_108], edi
0x18005e288  mov     [rsp+180h+var_118], r15
0x18005e28d  mov     [rbp+80h+var_100], r13d
0x18005e291  mov     [rsp+180h+var_120], r12
0x18005e296  mov     [rsp+180h+var_128], rbx
0x18005e29b  mov     [rbp+80h+var_A8], r9
0x18005e29f  mov     [rbp+80h+var_98], r9
0x18005e2a3  mov     [rbp+80h+var_78], r9
0x18005e2a7  mov     [rbp+80h+var_58], r9
0x18005e2ab  call    McGenEventWrite_EventWriteTransfer
0x18005e2b0  mov     rcx, rbx
0x18005e2b3  call    WaDereferenceProtocolObject
0x18005e2b8  mov     rcx, [rsp+180h+hObject]; hObject
0x18005e2bd  call    WaRestoreToken
0x18005e2c2  cmp     byte ptr [rbp+80h+var_D8], r14b
0x18005e2c6  jz      short loc_18005E2DD
0x18005e2c8  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x18005e2cc  mov     ecx, 2; ControlCode
0x18005e2d1  call    cs:__imp_EventActivityIdControl
0x18005e2d8  nop     dword ptr [rax+rax+00h]
0x18005e2dd  mov     eax, edi
0x18005e2df  mov     rcx, [rbp+80h+var_40]
0x18005e2e3  xor     rcx, rsp; StackCookie
0x18005e2e6  call    __security_check_cookie
0x18005e2eb  mov     rbx, [rsp+180h+arg_8]
0x18005e2f3  add     rsp, 150h
0x18005e2fa  pop     r15
0x18005e2fc  pop     r14
0x18005e2fe  pop     r13
0x18005e300  pop     r12
0x18005e302  pop     rdi
0x18005e303  pop     rsi
0x18005e304  pop     rbp
0x18005e305  retn
0x18005e307  mov     [rsp+180h+var_140], 0
0x18005e30f  lea     rdx, ProtocolReceiveData
0x18005e316  mov     [rsp+180h+var_148], r15
0x18005e31b  mov     r9, rdi
0x18005e31e  mov     [rsp+180h+var_150], r13d
0x18005e323  mov     r8, rbx
0x18005e326  mov     [rsp+180h+var_158], r12
0x18005e32b  mov     dword ptr [rsp+180h+var_160], esi
0x18005e32f  call    McTemplateU0pxqpqpq_EventWriteTransfer
0x18005e334  jmp     loc_18005E129
0x18005e339  mov     eax, 6
0x18005e33e  jmp     short loc_18005E2DF
0x18005e340  mov     r8, [rsp+180h+var_108]
0x18005e345  mov     rdx, rsi
0x18005e348  mov     rcx, rbx
0x18005e34b  call    WaProtocolCopyBufferedData
0x18005e350  jmp     loc_18005E1F1
0x18005e355  mov     edi, [rbx+54h]
0x18005e358  jmp     loc_18005E17C
0x18005e35d  mov     edi, 139Fh
0x18005e362  jmp     loc_18005E17C
0x18005e367  mov     r8d, edi
0x18005e36a  mov     rdx, rsi
0x18005e36d  mov     rcx, rbx
0x18005e370  call    WaCompleteProtocolTracker
0x18005e375  jmp     loc_18005E1FE
```
