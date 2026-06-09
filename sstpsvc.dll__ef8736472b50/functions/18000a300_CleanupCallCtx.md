# CleanupCallCtx

- ea: `0x18000a300`
- end: `0x18000a593`
- name: `CleanupCallCtx`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002f50`
- `0x180002f80`
- `0x1800089dc`
- `0x180008b90`
- `0x18000a300`
- `0x180015b6c`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a38c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a38c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4fd`
- `webio!__imp_WebCloseHttpRequest` at `0x18000a3b3`
- `webio!__imp_WebCloseHttpRequest` at `0x18000a3b3`
- `webio!__imp_WebCloseSession` at `0x18000a428`
- `webio!__imp_WebCloseSession` at `0x18000a428`

## string_xrefs

- `0x18000a3da`: `CoId=%hs:WebCloseHttpHandle completes with error %d`
- `0x18000a44f`: `CoId=%hs:WebCloseSession completes with error %d`

## pseudocode

```c
__int64 __fastcall CleanupCallCtx(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // r8
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v1 = a1 - 208;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 184));
  HfFreeHandle32(*((_QWORD *)SstpSvcGlobals + 22), v1 + 244);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 184));
  if ( *(_BYTE *)(v1 + 248) )
  {
    v2 = *(_QWORD *)(v1 + 448);
    if ( v2 )
    {
      v3 = WebCloseHttpRequest(v2, 0);
      if ( v3 )
      {
        if ( (byte_18002E903 & 8) != 0 )
        {
          LOWORD(v10) = 0;
          FormatRRASErrorString(&v10, L"CoId=%hs:WebCloseHttpHandle completes with error %d", v1 + 552, v3);
          if ( (byte_18002E903 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
        }
      }
      *(_QWORD *)(v1 + 448) = 0;
    }
    v4 = *(_QWORD *)(v1 + 440);
    if ( v4 )
    {
      v5 = WebCloseSession(v4, 0);
      if ( v5 )
      {
        if ( (byte_18002E903 & 8) != 0 )
        {
          LOWORD(v10) = 0;
          FormatRRASErrorString(&v10, L"CoId=%hs:WebCloseSession completes with error %d", v1 + 552, v5);
          if ( (byte_18002E903 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
        }
      }
      *(_QWORD *)(v1 + 440) = 0;
    }
    v6 = *((_QWORD *)&xmmword_18002EBA0 + 1);
    v7 = *(_QWORD *)(v1 + 544);
    if ( *((_QWORD *)&xmmword_18002EBA0 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gHostRoutTemplateFunc)(
        gHostRoutEtwContext,
        *((_QWORD *)&xmmword_18002EBA0 + 1),
        L"Entering ReleaseHostRouteInfoContext");
      v6 = *((_QWORD *)&xmmword_18002EBA0 + 1);
    }
    if ( v7 )
    {
      DereferenceRefCount(v7);
      v6 = *((_QWORD *)&xmmword_18002EBA0 + 1);
    }
    if ( v6 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gHostRoutTemplateFunc)(
        gHostRoutEtwContext,
        v6,
        L"Leaving ReleaseHostRouteInfoContext");
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 288));
  if ( (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"CoId=%hs:Freeing up call ctx 0x%p", v1 + 552, v1);
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
  }
  LOBYTE(v8) = 1;
  return FreeBufferToPool((char *)SstpSvcGlobals + 536, v1, v8);
}

```

## disassembly

```asm
0x18000a300  mov     [rsp-8+arg_8], rbx
0x18000a305  mov     [rsp-8+arg_10], rdi
0x18000a30a  push    rbp
0x18000a30b  lea     rbp, [rsp-730h]
0x18000a313  sub     rsp, 830h
0x18000a31a  mov     rax, cs:__security_cookie
0x18000a321  xor     rax, rsp
0x18000a324  mov     [rbp+730h+var_10], rax
0x18000a32b  lea     rbx, [rcx-0D0h]
0x18000a332  xor     eax, eax
0x18000a334  lea     rcx, [rsp+830h+var_80C]; void *
0x18000a339  mov     [rsp+830h+var_810], eax
0x18000a33d  xor     edx, edx; Val
0x18000a33f  mov     r8d, 7FCh; Size
0x18000a345  call    memset_0
0x18000a34a  mov     rcx, cs:SstpSvcGlobals
0x18000a351  add     rcx, 0B8h; lpCriticalSection
0x18000a358  call    cs:__imp_EnterCriticalSection
0x18000a35f  nop     dword ptr [rax+rax+00h]
0x18000a364  mov     rcx, cs:SstpSvcGlobals
0x18000a36b  lea     rdx, [rbx+0F4h]
0x18000a372  mov     rcx, [rcx+0B0h]
0x18000a379  call    HfFreeHandle32
0x18000a37e  mov     rcx, cs:SstpSvcGlobals
0x18000a385  add     rcx, 0B8h; lpCriticalSection
0x18000a38c  call    cs:__imp_LeaveCriticalSection
0x18000a393  nop     dword ptr [rax+rax+00h]
0x18000a398  cmp     byte ptr [rbx+0F8h], 0
0x18000a39f  jz      loc_18000A4F6
0x18000a3a5  mov     rcx, [rbx+1C0h]
0x18000a3ac  test    rcx, rcx
0x18000a3af  jz      short loc_18000A41A
0x18000a3b1  xor     edx, edx
0x18000a3b3  call    cs:__imp_WebCloseHttpRequest
0x18000a3ba  nop     dword ptr [rax+rax+00h]
0x18000a3bf  test    eax, eax
0x18000a3c1  jz      short loc_18000A40F
0x18000a3c3  test    cs:byte_18002E903, 8
0x18000a3ca  jz      short loc_18000A40F
0x18000a3cc  xor     ecx, ecx
0x18000a3ce  lea     r8, [rbx+228h]
0x18000a3d5  mov     word ptr [rsp+830h+var_810], cx
0x18000a3da  lea     rdx, aCoidHsWebclose; "CoId=%hs:WebCloseHttpHandle completes w"...
0x18000a3e1  lea     rcx, [rsp+830h+var_810]
0x18000a3e6  mov     r9d, eax
0x18000a3e9  call    FormatRRASErrorString
0x18000a3ee  test    cs:byte_18002E903, 8
0x18000a3f5  jz      short loc_18000A40F
0x18000a3f7  lea     r8, [rsp+830h+var_810]
0x18000a3fc  lea     rdx, RasSSTPSvcTraceError
0x18000a403  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a40a  call    McTemplateU0z_EventWriteTransfer
0x18000a40f  mov     qword ptr [rbx+1C0h], 0
0x18000a41a  mov     rcx, [rbx+1B8h]
0x18000a421  test    rcx, rcx
0x18000a424  jz      short loc_18000A48F
0x18000a426  xor     edx, edx
0x18000a428  call    cs:__imp_WebCloseSession
0x18000a42f  nop     dword ptr [rax+rax+00h]
0x18000a434  test    eax, eax
0x18000a436  jz      short loc_18000A484
0x18000a438  test    cs:byte_18002E903, 8
0x18000a43f  jz      short loc_18000A484
0x18000a441  xor     ecx, ecx
0x18000a443  lea     r8, [rbx+228h]
0x18000a44a  mov     word ptr [rsp+830h+var_810], cx
0x18000a44f  lea     rdx, aCoidHsWebclose_1; "CoId=%hs:WebCloseSession completes with"...
0x18000a456  lea     rcx, [rsp+830h+var_810]
0x18000a45b  mov     r9d, eax
0x18000a45e  call    FormatRRASErrorString
0x18000a463  test    cs:byte_18002E903, 8
0x18000a46a  jz      short loc_18000A484
0x18000a46c  lea     r8, [rsp+830h+var_810]
0x18000a471  lea     rdx, RasSSTPSvcTraceError
0x18000a478  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a47f  call    McTemplateU0z_EventWriteTransfer
0x18000a484  mov     qword ptr [rbx+1B8h], 0
0x18000a48f  mov     rdx, qword ptr cs:xmmword_18002EBA0+8
0x18000a496  mov     rdi, [rbx+220h]
0x18000a49d  test    rdx, rdx
0x18000a4a0  jz      short loc_18000A4C3
0x18000a4a2  mov     rcx, cs:gHostRoutEtwContext
0x18000a4a9  lea     r8, aEnteringReleas; "Entering ReleaseHostRouteInfoContext"
0x18000a4b0  mov     rax, cs:gHostRoutTemplateFunc
0x18000a4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4bc  mov     rdx, qword ptr cs:xmmword_18002EBA0+8
0x18000a4c3  test    rdi, rdi
0x18000a4c6  jz      short loc_18000A4D7
0x18000a4c8  mov     rcx, rdi
0x18000a4cb  call    DereferenceRefCount
0x18000a4d0  mov     rdx, qword ptr cs:xmmword_18002EBA0+8
0x18000a4d7  test    rdx, rdx
0x18000a4da  jz      short loc_18000A4F6
0x18000a4dc  mov     rcx, cs:gHostRoutEtwContext
0x18000a4e3  lea     r8, aLeavingRelease; "Leaving ReleaseHostRouteInfoContext"
0x18000a4ea  mov     rax, cs:gHostRoutTemplateFunc
0x18000a4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f6  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000a4fd  call    cs:__imp_DeleteCriticalSection
0x18000a504  nop     dword ptr [rax+rax+00h]
0x18000a509  test    cs:byte_18002E903, 8
0x18000a510  jz      short loc_18000A555
0x18000a512  xor     eax, eax
0x18000a514  lea     r8, [rbx+228h]
0x18000a51b  mov     r9, rbx
0x18000a51e  mov     word ptr [rsp+830h+var_810], ax
0x18000a523  lea     rdx, aCoidHsFreeingU; "CoId=%hs:Freeing up call ctx 0x%p"
0x18000a52a  lea     rcx, [rsp+830h+var_810]
0x18000a52f  call    FormatRRASErrorString
0x18000a534  test    cs:byte_18002E903, 8
0x18000a53b  jz      short loc_18000A555
0x18000a53d  lea     r8, [rsp+830h+var_810]
0x18000a542  lea     rdx, RasSSTPSvcTraceError
0x18000a549  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a550  call    McTemplateU0z_EventWriteTransfer
0x18000a555  mov     rcx, cs:SstpSvcGlobals
0x18000a55c  mov     r8b, 1
0x18000a55f  add     rcx, 218h
0x18000a566  mov     rdx, rbx
0x18000a569  call    FreeBufferToPool
0x18000a56e  mov     rcx, [rbp+730h+var_10]
0x18000a575  xor     rcx, rsp; StackCookie
0x18000a578  call    __security_check_cookie
0x18000a57d  lea     r11, [rsp+830h+var_s0]
0x18000a585  mov     rbx, [r11+18h]
0x18000a589  mov     rdi, [r11+20h]
0x18000a58d  mov     rsp, r11
0x18000a590  pop     rbp
0x18000a591  retn
```
