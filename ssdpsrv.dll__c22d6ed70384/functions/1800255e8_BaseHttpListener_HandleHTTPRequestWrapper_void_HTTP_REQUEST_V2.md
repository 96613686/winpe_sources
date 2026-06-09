# BaseHttpListener::HandleHTTPRequestWrapper(void *,_HTTP_REQUEST_V2 *)

- ea: `0x1800255e8`
- end: `0x180025e17`
- name: `?HandleHTTPRequestWrapper@BaseHttpListener@@IEAAJPEAXPEAU_HTTP_REQUEST_V2@@@Z`
- size: `2095`
- prototype: `__int64 __fastcall(HANDLE *this, void *, struct _HTTP_REQUEST_V2 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001a088`
- `0x180030f00`

## callees

- `0x1800255a8`
- `0x1800255e8`
- `0x180028000`
- `0x18002f078`
- `0x1800313b8`
- `0x1800313f4`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180025642`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180025642`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800257dc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800257ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800257dc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800257ea`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002573f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002573f`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180025a61`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180025a61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025a7b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025aaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025c3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025d71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025a7b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025aaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025c3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025d71`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800256c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800256c5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002590f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002590f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025832`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025832`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002581a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800259ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025ce8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002581a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800259ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002593b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002593b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800257f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800257f9`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180025d53`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180025d53`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002592d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002592d`

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
0x1800255e8  mov     [rsp-8+arg_8], rdx
0x1800255ed  push    rbp
0x1800255ee  push    rbx
0x1800255ef  push    rsi
0x1800255f0  push    rdi
0x1800255f1  push    r12
0x1800255f3  push    r13
0x1800255f5  push    r14
0x1800255f7  push    r15
0x1800255f9  lea     rbp, [rsp-1Fh]
0x1800255fe  sub     rsp, 88h
0x180025605  mov     r9d, [r8+24h]
0x180025609  xor     ebx, ebx
0x18002560b  xor     r13d, r13d
0x18002560e  mov     [rbp+57h+NumberOfBytesTransferred], ebx
0x180025611  mov     r15, r8
0x180025614  mov     rsi, rcx
0x180025617  sub     r9d, 1
0x18002561b  jz      short loc_180025631
0x18002561d  cmp     r9d, 5
0x180025621  jz      short loc_18002562A
0x180025623  mov     edx, 144h
0x180025628  jmp     short loc_180025657
0x18002562a  mov     edx, 140h
0x18002562f  jmp     short loc_180025657
0x180025631  mov     rcx, [r15+30h]; String1
0x180025635  lea     rdx, aMPost; "M-POST"
0x18002563c  mov     r8d, 6; MaxCount
0x180025642  call    cs:__imp__strnicmp
0x180025648  mov     ecx, 144h
0x18002564d  test    eax, eax
0x18002564f  lea     edx, [rcx-4]
0x180025652  cmovz   ecx, edx
0x180025655  mov     edx, ecx
0x180025657  mov     eax, [rdx+rsi]
0x18002565a  xorps   xmm0, xmm0
0x18002565d  mov     ecx, 19000h
0x180025662  mov     [rbp+57h+arg_18], eax
0x180025665  cmp     eax, ecx
0x180025667  mov     r14d, eax
0x18002566a  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002566e  cmova   r14d, ecx
0x180025672  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180025676  movups  xmmword ptr [rbp+57h+hObject], xmm0
0x18002567a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025681  lea     rdi, WPP_GLOBAL_Control
0x180025688  mov     r12d, 100h
0x18002568e  cmp     rcx, rdi
0x180025691  jz      short loc_1800256AE
0x180025693  test    [rcx+1Ch], r12d
0x180025697  jz      short loc_1800256AE
0x180025699  mov     rcx, [rcx+10h]
0x18002569d  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800256a4  mov     edx, 5Eh ; '^'
0x1800256a9  call    WPP_SF_
0x1800256ae  mov     rax, [rsi+138h]
0x1800256b5  xor     r9d, r9d; lpName
0x1800256b8  xor     r8d, r8d; bInitialState
0x1800256bb  mov     [rbp+57h+hObject], rax
0x1800256bf  xor     ecx, ecx; lpEventAttributes
0x1800256c1  lea     edx, [r9+1]; bManualReset
0x1800256c5  call    cs:__imp_CreateEventW
0x1800256cb  mov     [rbp+57h+hObject+8], rax
0x1800256cf  test    rax, rax
0x1800256d2  jnz     short loc_180025706
0x1800256d4  xor     r12d, r12d
0x1800256d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256de  cmp     rcx, rdi
0x1800256e1  jz      loc_180025783
0x1800256e7  test    byte ptr [rcx+1Ch], 1
0x1800256eb  jz      loc_180025783
0x1800256f1  mov     rcx, [rcx+10h]
0x1800256f5  lea     edx, [rax+5Fh]
0x1800256f8  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800256ff  call    WPP_SF_
0x180025704  jmp     short loc_180025783
0x180025706  mov     rdi, cs:WPP_GLOBAL_Control
0x18002570d  lea     rax, WPP_GLOBAL_Control
0x180025714  cmp     rdi, rax
0x180025717  jz      short loc_18002573B
0x180025719  test    [rdi+1Ch], r12d
0x18002571d  jz      short loc_18002573B
0x18002571f  mov     rcx, [rdi+10h]
0x180025723  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002572a  mov     edx, 60h ; '`'
0x18002572f  call    WPP_SF_
0x180025734  mov     rdi, cs:WPP_GLOBAL_Control
0x18002573b  lea     ecx, [r14+1]; Size
0x18002573f  call    cs:__imp_malloc
0x180025745  mov     [rbp+57h+var_80], rax
0x180025749  mov     r12, rax
0x18002574c  test    rax, rax
0x18002574f  jnz     loc_180025815
0x180025755  lea     rax, WPP_GLOBAL_Control
0x18002575c  cmp     rdi, rax
0x18002575f  jz      short loc_18002577C
0x180025761  test    byte ptr [rdi+1Ch], 1
0x180025765  jz      short loc_18002577C
0x180025767  mov     rcx, [rdi+10h]
0x18002576b  lea     edx, [r12+61h]
0x180025770  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180025777  call    WPP_SF_
0x18002577c  lea     rdi, WPP_GLOBAL_Control
0x180025783  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18002578a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18002578f  test    al, al
0x180025791  jz      short loc_1800257D9
0x180025793  test    r13d, r13d
0x180025796  jz      short loc_1800257D9
0x180025798  mov     rdx, [r15+10h]
0x18002579c  test    rdx, rdx
0x18002579f  jz      short loc_1800257D9
0x1800257a1  mov     rax, [rsi+28h]
0x1800257a5  test    rax, rax
0x1800257a8  jz      short loc_1800257D9
0x1800257aa  mov     rcx, [rsi+78h]
0x1800257ae  xor     r8d, r8d
0x1800257b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257bd  cmp     rcx, rdi
0x1800257c0  jz      short loc_1800257D9
0x1800257c2  test    byte ptr [rcx+1Ch], 1
0x1800257c6  jz      short loc_1800257D9
0x1800257c8  mov     r9, [r15+10h]
0x1800257cc  mov     rcx, [rcx+10h]
0x1800257d0  mov     [rsp+0C0h+bAlertable], eax
0x1800257d4  call    WPP_SF_Id
0x1800257d9  mov     rcx, r15; Block
0x1800257dc  call    cs:__imp_free
0x1800257e2  test    r12, r12
0x1800257e5  jz      short loc_1800257F0
0x1800257e7  mov     rcx, r12; Block
0x1800257ea  call    cs:__imp_free
0x1800257f0  mov     rcx, [rbp+57h+hObject+8]; hObject
0x1800257f4  test    rcx, rcx
0x1800257f7  jz      short loc_1800257FF
0x1800257f9  call    cs:__imp_CloseHandle
0x1800257ff  mov     eax, ebx
0x180025801  add     rsp, 88h
0x180025808  pop     r15
0x18002580a  pop     r14
0x18002580c  pop     r13
0x18002580e  pop     r12
0x180025810  pop     rdi
0x180025811  pop     rsi
0x180025812  pop     rbx
0x180025813  pop     rbp
0x180025814  retn
0x180025815  xor     r12d, r12d
0x180025818  xor     edi, edi
0x18002581a  call    cs:__imp_GetTickCount
0x180025820  mov     [rbp+57h+arg_10], eax
0x180025823  mov     rcx, [rbp+57h+hObject+8]; hEvent
0x180025827  xorps   xmm0, xmm0
0x18002582a  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002582e  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180025832  call    cs:__imp_ResetEvent
0x180025838  test    eax, eax
0x18002583a  jz      loc_180025DCC
0x180025840  mov     rax, [rbp+57h+hObject+8]
0x180025844  mov     ecx, r14d
0x180025847  mov     rdx, [r15+10h]
0x18002584b  sub     ecx, edi
0x18002584d  mov     [rbp+57h+Overlapped.hEvent], rax
0x180025851  xor     r8d, r8d
0x180025854  lea     rax, [rbp+57h+Overlapped]
0x180025858  mov     r9d, edi
0x18002585b  add     r9, [rbp+57h+var_80]
0x18002585f  mov     [rsp+0C0h+var_90], rax
0x180025864  mov     rax, [rsi+48h]
0x180025868  mov     [rsp+0C0h+var_98], r13
0x18002586d  mov     [rsp+0C0h+bAlertable], ecx
0x180025871  mov     rcx, [rsi+78h]
0x180025875  mov     [rbp+57h+NumberOfBytesTransferred], r13d
0x180025879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002587e  mov     ebx, eax
0x180025880  mov     rcx, cs:WPP_GLOBAL_Control
0x180025887  lea     rax, WPP_GLOBAL_Control
0x18002588e  cmp     rcx, rax
0x180025891  jz      short loc_1800258E9
0x180025893  test    dword ptr [rcx+1Ch], 100h
0x18002589a  jz      short loc_1800258C2
0x18002589c  mov     rcx, [rcx+10h]
0x1800258a0  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800258a7  mov     edx, 63h ; 'c'
0x1800258ac  mov     r9d, ebx
0x1800258af  call    WPP_SF_d
0x1800258b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258bb  lea     rax, WPP_GLOBAL_Control
0x1800258c2  cmp     rcx, rax
0x1800258c5  jz      short loc_1800258E9
0x1800258c7  test    dword ptr [rcx+1Ch], 100h
0x1800258ce  jz      short loc_1800258E9
0x1800258d0  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x1800258d4  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800258db  mov     rcx, [rcx+10h]
0x1800258df  mov     edx, 64h ; 'd'
0x1800258e4  call    WPP_SF_d
0x1800258e9  cmp     ebx, 3E5h
0x1800258ef  jz      short loc_1800258F9
0x1800258f1  test    ebx, ebx
0x1800258f3  jnz     loc_1800259AC
0x1800258f9  xor     r8d, r8d; bWaitAll
0x1800258fc  mov     [rsp+0C0h+bAlertable], r13d; bAlertable
0x180025901  or      ebx, 0FFFFFFFFh
0x180025904  lea     rdx, [rbp+57h+hObject]; lpHandles
0x180025908  mov     r9d, ebx; dwMilliseconds
0x18002590b  lea     ecx, [r8+2]; nCount
0x18002590f  call    cs:__imp_WaitForMultipleObjectsEx
0x180025915  cmp     eax, 1
0x180025918  jnz     loc_180025D1A
0x18002591e  mov     rcx, [rsi+78h]; hFile
0x180025922  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180025926  xor     r9d, r9d; bWait
0x180025929  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002592d  call    cs:__imp_GetOverlappedResult
0x180025933  test    eax, eax
0x180025935  jz      short loc_18002593B
0x180025937  xor     ebx, ebx
0x180025939  jmp     short loc_180025943
0x18002593b  call    cs:__imp_GetLastError
0x180025941  mov     ebx, eax
0x180025943  mov     rcx, cs:WPP_GLOBAL_Control
0x18002594a  lea     rax, WPP_GLOBAL_Control
0x180025951  cmp     rcx, rax
0x180025954  jz      short loc_1800259AC
0x180025956  test    dword ptr [rcx+1Ch], 100h
0x18002595d  jz      short loc_180025985
0x18002595f  mov     rcx, [rcx+10h]
0x180025963  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002596a  mov     edx, 65h ; 'e'
0x18002596f  mov     r9d, ebx
0x180025972  call    WPP_SF_d
0x180025977  mov     rcx, cs:WPP_GLOBAL_Control
0x18002597e  lea     rax, WPP_GLOBAL_Control
0x180025985  cmp     rcx, rax
0x180025988  jz      short loc_1800259AC
0x18002598a  test    dword ptr [rcx+1Ch], 100h
0x180025991  jz      short loc_1800259AC
0x180025993  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x180025997  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002599e  mov     rcx, [rcx+10h]
0x1800259a2  mov     edx, 66h ; 'f'
0x1800259a7  call    WPP_SF_d
0x1800259ac  call    cs:__imp_GetTickCount
0x1800259b2  mov     ecx, eax
0x1800259b4  mov     eax, [rbp+57h+arg_10]
0x1800259b7  add     eax, 1D4C0h
0x1800259bc  cmp     ecx, eax
0x1800259be  ja      loc_180025CCF
0x1800259c4  test    ebx, ebx
0x1800259c6  jz      loc_180025A95
0x1800259cc  cmp     ebx, 26h ; '&'
0x1800259cf  jz      loc_180025C28
0x1800259d5  cmp     ebx, 0EAh
0x1800259db  jnz     loc_180025B7F
0x1800259e1  mov     edx, [rbp+57h+NumberOfBytesTransferred]
0x1800259e4  mov     r8d, 8000h
0x1800259ea  mov     ecx, [rbp+57h+arg_18]
0x1800259ed  cmp     edx, r8d
0x1800259f0  mov     eax, edx
0x1800259f2  cmovb   eax, r8d
0x1800259f6  sub     ecx, edi
0x1800259f8  cmp     eax, ecx
0x1800259fa  jnb     short loc_180025A08
0x1800259fc  cmp     edx, r8d
0x1800259ff  jnb     short loc_180025A06
0x180025a01  mov     ecx, r8d
0x180025a04  jmp     short loc_180025A10
0x180025a06  mov     ecx, edx
0x180025a08  test    ecx, ecx
0x180025a0a  jz      loc_180025B37
0x180025a10  cmp     ecx, edx
0x180025a12  jb      loc_180025B37
0x180025a18  lea     r14d, [rcx+rdi]
0x180025a1c  cmp     r14d, edi
0x180025a1f  jb      loc_180025AFC
0x180025a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a2c  lea     rax, WPP_GLOBAL_Control
0x180025a33  cmp     rcx, rax
0x180025a36  jz      short loc_180025A59
0x180025a38  test    dword ptr [rcx+1Ch], 100h
0x180025a3f  jz      short loc_180025A59
0x180025a41  mov     rcx, [rcx+10h]
0x180025a45  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180025a4c  mov     edx, 6Ch ; 'l'
0x180025a51  mov     r9d, r14d
0x180025a54  call    WPP_SF_d
0x180025a59  mov     rcx, [rbp+57h+var_80]
0x180025a5d  lea     edx, [r14+1]
0x180025a61  call    cs:__imp__o_realloc
0x180025a67  mov     [rbp+57h+var_80], rax
0x180025a6b  test    rax, rax
0x180025a6e  jz      short loc_180025ABF
0x180025a70  mov     rcx, [rsi+138h]; hHandle
0x180025a77  xor     edx, edx; dwMilliseconds
0x180025a79  xor     ebx, ebx
0x180025a7b  call    cs:__imp_WaitForSingleObject
0x180025a81  cmp     eax, 102h
0x180025a86  jz      loc_180025823
  ... truncated ...
```
