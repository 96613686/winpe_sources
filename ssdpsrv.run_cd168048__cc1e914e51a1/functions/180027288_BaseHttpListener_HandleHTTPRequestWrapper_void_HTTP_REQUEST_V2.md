# BaseHttpListener::HandleHTTPRequestWrapper(void *,_HTTP_REQUEST_V2 *)

- ea: `0x180027288`
- end: `0x180027b3f`
- name: `?HandleHTTPRequestWrapper@BaseHttpListener@@IEAAJPEAXPEAU_HTTP_REQUEST_V2@@@Z`
- size: `2231`
- prototype: `int(BaseHttpListener *__hidden this, void *, struct _HTTP_REQUEST_V2 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b344`
- `0x180033640`

## callees

- `0x1800271fc`
- `0x180027288`
- `0x180029df0`
- `0x1800312cc`
- `0x180033c20`
- `0x180033c5c`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1800272e2`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1800272e2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027491`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800274a5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027491`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800274a5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800273ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800273ee`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002774d`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002774d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002776d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800277a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027939`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027a87`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002776d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800277a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027939`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027a87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002736b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002736b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800275e3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800275e3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180027500`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180027500`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800274e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027692`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800279ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800274e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027692`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800279ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002761b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002761b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027aee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274ba`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180027a5d`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180027a5d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180027607`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180027607`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::HandleHTTPRequestWrapper(HANDLE *this, void *a2, struct _HTTP_REQUEST_V2 *a3)
{
  HTTP_VERB Verb; // r9d
  unsigned int v4; // ebx
  int IsEnabled; // r13d
  __int32 v8; // r9d
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // r14d
  char *v13; // r12
  LPCSTR v14; // rdi
  HTTP_REQUEST_ID v15; // rdx
  __int64 (__fastcall *v16)(HANDLE, HTTP_REQUEST_ID, _QWORD); // rax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  int v21; // r12d
  unsigned int v22; // edi
  HTTP_REQUEST_ID RequestId; // rdx
  __int64 (__fastcall *v24)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD); // rax
  HANDLE v25; // rcx
  DWORD v26; // ebx
  LPCSTR v27; // rcx
  LPCSTR v28; // rcx
  DWORD v29; // eax
  DWORD v30; // ecx
  LPCSTR v31; // rcx
  __int64 v32; // rdx
  void *v33; // rbx
  DWORD v34; // eax
  signed int v35; // eax
  signed int LastError; // eax
  int bAlertable; // [rsp+20h] [rbp-49h]
  char *v38; // [rsp+40h] [rbp-29h]
  HANDLE hObject[2]; // [rsp+48h] [rbp-21h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-11h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+D0h] [rbp+67h] BYREF
  void *v42; // [rsp+D8h] [rbp+6Fh]
  DWORD TickCount; // [rsp+E0h] [rbp+77h]
  unsigned int v44; // [rsp+E8h] [rbp+7Fh]

  v42 = a2;
  Verb = a3->Verb;
  v4 = 0;
  IsEnabled = 0;
  NumberOfBytesTransferred = 0;
  v8 = Verb - 1;
  if ( v8 )
  {
    if ( v8 == 5 )
      v9 = 320;
    else
      v9 = 324;
  }
  else
  {
    v10 = _strnicmp(a3->pUnknownVerb, "M-POST", 6u);
    v11 = 324;
    if ( !v10 )
      v11 = 320;
    v9 = v11;
  }
  v44 = *(_DWORD *)((char *)this + v9);
  v12 = v44;
  *(_OWORD *)&Overlapped.Internal = 0;
  if ( v44 > 0x19000 )
    v12 = 102400;
  *(_OWORD *)&Overlapped.Offset = 0;
  *(_OWORD *)hObject = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  hObject[0] = this[39];
  hObject[1] = CreateEventW(0, 1, 0, 0);
  if ( !hObject[1] )
  {
    v13 = 0;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    goto LABEL_24;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    v14 = WPP_GLOBAL_Control;
  }
  v38 = (char *)malloc(v12 + 1);
  v13 = v38;
  if ( !v38 )
  {
    if ( v14 != (LPCSTR)&WPP_GLOBAL_Control && (v14[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)v14 + 2), 97, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    goto LABEL_24;
  }
  v21 = 0;
  v22 = 0;
  TickCount = GetTickCount();
  while ( 1 )
  {
    while ( 1 )
    {
      memset(&Overlapped, 0, sizeof(Overlapped));
      if ( !ResetEvent(hObject[1]) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v4);
        goto LABEL_126;
      }
      RequestId = a3->RequestId;
      Overlapped.hEvent = hObject[1];
      v24 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD))this[9];
      v25 = this[15];
      NumberOfBytesTransferred = 0;
      v26 = v24(v25, RequestId, 0, &v38[v22], v12 - v22, 0, &Overlapped);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v26);
          v27 = WPP_GLOBAL_Control;
        }
        if ( v27 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v27 + 7) & 0x100) != 0 )
          WPP_SF_d(*((_QWORD *)v27 + 2), 100, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, NumberOfBytesTransferred);
      }
      if ( v26 == 997 || !v26 )
      {
        if ( WaitForMultipleObjectsEx(2u, hObject, 0, 0xFFFFFFFF, 0) != 1 )
        {
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
          if ( (CancelIoEx(this[15], &Overlapped) || GetLastError() != 1168)
            && WaitForSingleObject(hObject[1], 0xFFFFFFFF)
            && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            v35 = GetLastError();
            if ( v35 > 0 )
              v35 = (unsigned __int16)v35 | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              104,
              WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
              (unsigned int)v35);
          }
          v4 = 0;
          goto LABEL_126;
        }
        if ( GetOverlappedResult(this[15], &Overlapped, &NumberOfBytesTransferred, 0) )
          v26 = 0;
        else
          v26 = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v26);
            v28 = WPP_GLOBAL_Control;
          }
          if ( v28 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v28 + 7) & 0x100) != 0 )
            WPP_SF_d(
              *((_QWORD *)v28 + 2),
              102,
              WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
              NumberOfBytesTransferred);
        }
      }
      if ( GetTickCount() > TickCount + 120000 )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        {
          v34 = GetTickCount();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
            v34 - TickCount);
        }
        goto LABEL_113;
      }
      if ( v26 )
        break;
      if ( NumberOfBytesTransferred )
      {
        v21 += NumberOfBytesTransferred;
        v22 += NumberOfBytesTransferred;
      }
      if ( WaitForSingleObject(this[39], 0) != 258 )
      {
        v4 = 0;
LABEL_74:
        v13 = v38;
        goto LABEL_24;
      }
    }
    if ( v26 == 38 )
      break;
    if ( v26 != 234 )
    {
      if ( v26 == 995 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        {
          v32 = 111;
LABEL_88:
          WPP_SF_(*((_QWORD *)v31 + 2), v32, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
        }
LABEL_89:
        v4 = -2147467259;
        goto LABEL_90;
      }
      if ( v26 != 1229 )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v26);
        goto LABEL_89;
      }
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
LABEL_113:
      v4 = -2147467259;
      goto LABEL_126;
    }
    v29 = NumberOfBytesTransferred;
    if ( NumberOfBytesTransferred < 0x8000 )
      v29 = 0x8000;
    v30 = v44 - v22;
    if ( v29 < v44 - v22 )
    {
      if ( NumberOfBytesTransferred < 0x8000 )
      {
        v30 = 0x8000;
        goto LABEL_67;
      }
      v30 = NumberOfBytesTransferred;
    }
    if ( !v30 )
      goto LABEL_85;
LABEL_67:
    if ( v30 < NumberOfBytesTransferred )
    {
LABEL_85:
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v32 = 106;
        goto LABEL_88;
      }
      goto LABEL_89;
    }
    v12 = v30 + v22;
    if ( v30 + v22 < v22 )
    {
      v4 = -2147024362;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
          2147942934LL);
LABEL_90:
      IsEnabled = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl);
LABEL_126:
      v13 = v38;
      goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v12);
    v38 = (char *)_o_realloc(v38, v12 + 1);
    if ( !v38 )
    {
      v4 = -2147024882;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
      goto LABEL_90;
    }
    v4 = 0;
    if ( WaitForSingleObject(this[39], 0) != 258 )
      goto LABEL_74;
  }
  if ( NumberOfBytesTransferred )
    v21 += NumberOfBytesTransferred;
  v4 = 0;
  if ( WaitForSingleObject(this[39], 0) != 258 || *((_DWORD *)this + 82) )
    goto LABEL_74;
  v33 = v42;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      113,
      (unsigned int)WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      (_DWORD)v42,
      (__int64)a3->pRawUrl);
  bAlertable = v21;
  v13 = v38;
  v4 = (*((__int64 (__fastcall **)(HANDLE *, void *, struct _HTTP_REQUEST_V2 *, char *, int, HANDLE))*this + 1))(
         this,
         v33,
         a3,
         v38,
         bAlertable,
         this[15]);
LABEL_24:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    if ( IsEnabled )
    {
      v15 = a3->RequestId;
      if ( v15 )
      {
        v16 = (__int64 (__fastcall *)(HANDLE, HTTP_REQUEST_ID, _QWORD))this[5];
        if ( v16 )
        {
          v17 = v16(this[15], v15, 0);
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
            WPP_SF_Id(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, a3->RequestId, v17);
        }
      }
    }
  }
  free(a3);
  if ( v13 )
    free(v13);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  return v4;
}

```

## disassembly

```asm
0x180027288  mov     [rsp-8+arg_8], rdx
0x18002728d  push    rbp
0x18002728e  push    rbx
0x18002728f  push    rsi
0x180027290  push    rdi
0x180027291  push    r12
0x180027293  push    r13
0x180027295  push    r14
0x180027297  push    r15
0x180027299  lea     rbp, [rsp-1Fh]
0x18002729e  sub     rsp, 88h
0x1800272a5  mov     r9d, [r8+24h]
0x1800272a9  xor     ebx, ebx
0x1800272ab  xor     r13d, r13d
0x1800272ae  mov     [rbp+57h+NumberOfBytesTransferred], ebx
0x1800272b1  mov     r15, r8
0x1800272b4  mov     rsi, rcx
0x1800272b7  sub     r9d, 1
0x1800272bb  jz      short loc_1800272D1
0x1800272bd  cmp     r9d, 5
0x1800272c1  jz      short loc_1800272CA
0x1800272c3  mov     edx, 144h
0x1800272c8  jmp     short loc_1800272FD
0x1800272ca  mov     edx, 140h
0x1800272cf  jmp     short loc_1800272FD
0x1800272d1  mov     rcx, [r15+30h]; String1
0x1800272d5  lea     rdx, aMPost; "M-POST"
0x1800272dc  mov     r8d, 6; MaxCount
0x1800272e2  call    cs:__imp__strnicmp
0x1800272e9  nop     dword ptr [rax+rax+00h]
0x1800272ee  mov     ecx, 144h
0x1800272f3  test    eax, eax
0x1800272f5  lea     edx, [rcx-4]
0x1800272f8  cmovz   ecx, edx
0x1800272fb  mov     edx, ecx
0x1800272fd  mov     eax, [rdx+rsi]
0x180027300  xorps   xmm0, xmm0
0x180027303  mov     ecx, 19000h
0x180027308  mov     [rbp+57h+arg_18], eax
0x18002730b  cmp     eax, ecx
0x18002730d  mov     r14d, eax
0x180027310  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180027314  cmova   r14d, ecx
0x180027318  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002731c  movups  xmmword ptr [rbp+57h+hObject], xmm0
0x180027320  mov     rcx, cs:WPP_GLOBAL_Control
0x180027327  lea     rdi, WPP_GLOBAL_Control
0x18002732e  mov     r12d, 100h
0x180027334  cmp     rcx, rdi
0x180027337  jz      short loc_180027354
0x180027339  test    [rcx+1Ch], r12d
0x18002733d  jz      short loc_180027354
0x18002733f  mov     rcx, [rcx+10h]
0x180027343  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002734a  mov     edx, 5Eh ; '^'
0x18002734f  call    WPP_SF_
0x180027354  mov     rax, [rsi+138h]
0x18002735b  xor     r9d, r9d; lpName
0x18002735e  xor     r8d, r8d; bInitialState
0x180027361  mov     [rbp+57h+hObject], rax
0x180027365  xor     ecx, ecx; lpEventAttributes
0x180027367  lea     edx, [r9+1]; bManualReset
0x18002736b  call    cs:__imp_CreateEventW
0x180027372  nop     dword ptr [rax+rax+00h]
0x180027377  mov     [rbp+57h+hObject+8], rax
0x18002737b  test    rax, rax
0x18002737e  jnz     short loc_1800273B5
0x180027380  xor     r12d, r12d
0x180027383  mov     rcx, cs:WPP_GLOBAL_Control
0x18002738a  cmp     rcx, rdi
0x18002738d  jz      loc_180027438
0x180027393  test    byte ptr [rcx+1Ch], 1
0x180027397  jz      loc_180027438
0x18002739d  mov     rcx, [rcx+10h]
0x1800273a1  lea     edx, [rax+5Fh]
0x1800273a4  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800273ab  call    WPP_SF_
0x1800273b0  jmp     loc_180027438
0x1800273b5  mov     rdi, cs:WPP_GLOBAL_Control
0x1800273bc  lea     rax, WPP_GLOBAL_Control
0x1800273c3  cmp     rdi, rax
0x1800273c6  jz      short loc_1800273EA
0x1800273c8  test    [rdi+1Ch], r12d
0x1800273cc  jz      short loc_1800273EA
0x1800273ce  mov     rcx, [rdi+10h]
0x1800273d2  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800273d9  mov     edx, 60h ; '`'
0x1800273de  call    WPP_SF_
0x1800273e3  mov     rdi, cs:WPP_GLOBAL_Control
0x1800273ea  lea     ecx, [r14+1]; Size
0x1800273ee  call    cs:__imp_malloc
0x1800273f5  nop     dword ptr [rax+rax+00h]
0x1800273fa  mov     [rbp+57h+var_80], rax
0x1800273fe  mov     r12, rax
0x180027401  test    rax, rax
0x180027404  jnz     loc_1800274DD
0x18002740a  lea     rax, WPP_GLOBAL_Control
0x180027411  cmp     rdi, rax
0x180027414  jz      short loc_180027431
0x180027416  test    byte ptr [rdi+1Ch], 1
0x18002741a  jz      short loc_180027431
0x18002741c  mov     rcx, [rdi+10h]
0x180027420  lea     edx, [r12+61h]
0x180027425  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002742c  call    WPP_SF_
0x180027431  lea     rdi, WPP_GLOBAL_Control
0x180027438  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18002743f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x180027444  test    al, al
0x180027446  jz      short loc_18002748E
0x180027448  test    r13d, r13d
0x18002744b  jz      short loc_18002748E
0x18002744d  mov     rdx, [r15+10h]
0x180027451  test    rdx, rdx
0x180027454  jz      short loc_18002748E
0x180027456  mov     rax, [rsi+28h]
0x18002745a  test    rax, rax
0x18002745d  jz      short loc_18002748E
0x18002745f  mov     rcx, [rsi+78h]
0x180027463  xor     r8d, r8d
0x180027466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002746b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027472  cmp     rcx, rdi
0x180027475  jz      short loc_18002748E
0x180027477  test    byte ptr [rcx+1Ch], 1
0x18002747b  jz      short loc_18002748E
0x18002747d  mov     r9, [r15+10h]
0x180027481  mov     rcx, [rcx+10h]
0x180027485  mov     [rsp+0C0h+bAlertable], eax
0x180027489  call    WPP_SF_Id
0x18002748e  mov     rcx, r15; Block
0x180027491  call    cs:__imp_free
0x180027498  nop     dword ptr [rax+rax+00h]
0x18002749d  test    r12, r12
0x1800274a0  jz      short loc_1800274B1
0x1800274a2  mov     rcx, r12; Block
0x1800274a5  call    cs:__imp_free
0x1800274ac  nop     dword ptr [rax+rax+00h]
0x1800274b1  mov     rcx, [rbp+57h+hObject+8]; hObject
0x1800274b5  test    rcx, rcx
0x1800274b8  jz      short loc_1800274C6
0x1800274ba  call    cs:__imp_CloseHandle
0x1800274c1  nop     dword ptr [rax+rax+00h]
0x1800274c6  mov     eax, ebx
0x1800274c8  add     rsp, 88h
0x1800274cf  pop     r15
0x1800274d1  pop     r14
0x1800274d3  pop     r13
0x1800274d5  pop     r12
0x1800274d7  pop     rdi
0x1800274d8  pop     rsi
0x1800274d9  pop     rbx
0x1800274da  pop     rbp
0x1800274db  retn
0x1800274dd  xor     r12d, r12d
0x1800274e0  xor     edi, edi
0x1800274e2  call    cs:__imp_GetTickCount
0x1800274e9  nop     dword ptr [rax+rax+00h]
0x1800274ee  mov     [rbp+57h+arg_10], eax
0x1800274f1  mov     rcx, [rbp+57h+hObject+8]; hEvent
0x1800274f5  xorps   xmm0, xmm0
0x1800274f8  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1800274fc  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180027500  call    cs:__imp_ResetEvent
0x180027507  nop     dword ptr [rax+rax+00h]
0x18002750c  test    eax, eax
0x18002750e  jz      loc_180027AEE
0x180027514  mov     rax, [rbp+57h+hObject+8]
0x180027518  mov     ecx, r14d
0x18002751b  mov     rdx, [r15+10h]
0x18002751f  sub     ecx, edi
0x180027521  mov     [rbp+57h+Overlapped.hEvent], rax
0x180027525  xor     r8d, r8d
0x180027528  lea     rax, [rbp+57h+Overlapped]
0x18002752c  mov     r9d, edi
0x18002752f  add     r9, [rbp+57h+var_80]
0x180027533  mov     [rsp+0C0h+var_90], rax
0x180027538  mov     rax, [rsi+48h]
0x18002753c  mov     [rsp+0C0h+var_98], r13
0x180027541  mov     [rsp+0C0h+bAlertable], ecx
0x180027545  mov     rcx, [rsi+78h]
0x180027549  mov     [rbp+57h+NumberOfBytesTransferred], r13d
0x18002754d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027552  mov     ebx, eax
0x180027554  mov     rcx, cs:WPP_GLOBAL_Control
0x18002755b  lea     rax, WPP_GLOBAL_Control
0x180027562  cmp     rcx, rax
0x180027565  jz      short loc_1800275BD
0x180027567  test    dword ptr [rcx+1Ch], 100h
0x18002756e  jz      short loc_180027596
0x180027570  mov     rcx, [rcx+10h]
0x180027574  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002757b  mov     edx, 63h ; 'c'
0x180027580  mov     r9d, ebx
0x180027583  call    WPP_SF_d
0x180027588  mov     rcx, cs:WPP_GLOBAL_Control
0x18002758f  lea     rax, WPP_GLOBAL_Control
0x180027596  cmp     rcx, rax
0x180027599  jz      short loc_1800275BD
0x18002759b  test    dword ptr [rcx+1Ch], 100h
0x1800275a2  jz      short loc_1800275BD
0x1800275a4  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x1800275a8  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800275af  mov     rcx, [rcx+10h]
0x1800275b3  mov     edx, 64h ; 'd'
0x1800275b8  call    WPP_SF_d
0x1800275bd  cmp     ebx, 3E5h
0x1800275c3  jz      short loc_1800275CD
0x1800275c5  test    ebx, ebx
0x1800275c7  jnz     loc_180027692
0x1800275cd  xor     r8d, r8d; bWaitAll
0x1800275d0  mov     [rsp+0C0h+bAlertable], r13d; bAlertable
0x1800275d5  or      ebx, 0FFFFFFFFh
0x1800275d8  lea     rdx, [rbp+57h+hObject]; lpHandles
0x1800275dc  mov     r9d, ebx; dwMilliseconds
0x1800275df  lea     ecx, [r8+2]; nCount
0x1800275e3  call    cs:__imp_WaitForMultipleObjectsEx
0x1800275ea  nop     dword ptr [rax+rax+00h]
0x1800275ef  cmp     eax, 1
0x1800275f2  jnz     loc_180027A24
0x1800275f8  mov     rcx, [rsi+78h]; hFile
0x1800275fc  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180027600  xor     r9d, r9d; bWait
0x180027603  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180027607  call    cs:__imp_GetOverlappedResult
0x18002760e  nop     dword ptr [rax+rax+00h]
0x180027613  test    eax, eax
0x180027615  jz      short loc_18002761B
0x180027617  xor     ebx, ebx
0x180027619  jmp     short loc_180027629
0x18002761b  call    cs:__imp_GetLastError
0x180027622  nop     dword ptr [rax+rax+00h]
0x180027627  mov     ebx, eax
0x180027629  mov     rcx, cs:WPP_GLOBAL_Control
0x180027630  lea     rax, WPP_GLOBAL_Control
0x180027637  cmp     rcx, rax
0x18002763a  jz      short loc_180027692
0x18002763c  test    dword ptr [rcx+1Ch], 100h
0x180027643  jz      short loc_18002766B
0x180027645  mov     rcx, [rcx+10h]
0x180027649  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180027650  mov     edx, 65h ; 'e'
0x180027655  mov     r9d, ebx
0x180027658  call    WPP_SF_d
0x18002765d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027664  lea     rax, WPP_GLOBAL_Control
0x18002766b  cmp     rcx, rax
0x18002766e  jz      short loc_180027692
0x180027670  test    dword ptr [rcx+1Ch], 100h
0x180027677  jz      short loc_180027692
0x180027679  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x18002767d  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180027684  mov     rcx, [rcx+10h]
0x180027688  mov     edx, 66h ; 'f'
0x18002768d  call    WPP_SF_d
0x180027692  call    cs:__imp_GetTickCount
0x180027699  nop     dword ptr [rax+rax+00h]
0x18002769e  mov     ecx, eax
0x1800276a0  mov     eax, [rbp+57h+arg_10]
0x1800276a3  add     eax, 1D4C0h
0x1800276a8  cmp     ecx, eax
0x1800276aa  ja      loc_1800279D3
0x1800276b0  test    ebx, ebx
0x1800276b2  jz      loc_18002778D
0x1800276b8  cmp     ebx, 26h ; '&'
0x1800276bb  jz      loc_180027926
0x1800276c1  cmp     ebx, 0EAh
0x1800276c7  jnz     loc_18002787D
0x1800276cd  mov     edx, [rbp+57h+NumberOfBytesTransferred]
0x1800276d0  mov     r8d, 8000h
0x1800276d6  mov     ecx, [rbp+57h+arg_18]
0x1800276d9  cmp     edx, r8d
0x1800276dc  mov     eax, edx
0x1800276de  cmovb   eax, r8d
0x1800276e2  sub     ecx, edi
0x1800276e4  cmp     eax, ecx
0x1800276e6  jnb     short loc_1800276F4
0x1800276e8  cmp     edx, r8d
0x1800276eb  jnb     short loc_1800276F2
0x1800276ed  mov     ecx, r8d
0x1800276f0  jmp     short loc_1800276FC
0x1800276f2  mov     ecx, edx
0x1800276f4  test    ecx, ecx
0x1800276f6  jz      loc_180027835
0x1800276fc  cmp     ecx, edx
0x1800276fe  jb      loc_180027835
0x180027704  lea     r14d, [rcx+rdi]
0x180027708  cmp     r14d, edi
0x18002770b  jb      loc_1800277FA
0x180027711  mov     rcx, cs:WPP_GLOBAL_Control
0x180027718  lea     rax, WPP_GLOBAL_Control
0x18002771f  cmp     rcx, rax
0x180027722  jz      short loc_180027745
0x180027724  test    dword ptr [rcx+1Ch], 100h
0x18002772b  jz      short loc_180027745
0x18002772d  mov     rcx, [rcx+10h]
0x180027731  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180027738  mov     edx, 6Ch ; 'l'
0x18002773d  mov     r9d, r14d
0x180027740  call    WPP_SF_d
  ... truncated ...
```
