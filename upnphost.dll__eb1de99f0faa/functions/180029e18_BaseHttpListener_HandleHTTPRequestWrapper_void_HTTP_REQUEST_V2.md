# BaseHttpListener::HandleHTTPRequestWrapper(void *,_HTTP_REQUEST_V2 *)

- ea: `0x180029e18`
- end: `0x18002a633`
- name: `?HandleHTTPRequestWrapper@BaseHttpListener@@IEAAJPEAXPEAU_HTTP_REQUEST_V2@@@Z`
- size: `2075`
- prototype: `int(BaseHttpListener *__hidden this, void *, struct _HTTP_REQUEST_V2 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180029d40`
- `0x180050f30`

## callees

- `0x180029e18`
- `0x180038ce4`
- `0x180039a84`
- `0x18004ae14`
- `0x1800516c8`
- `0x180051780`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180029e72`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180029e72`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a272`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a280`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a272`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a280`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029f61`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029f61`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002a1df`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002a1df`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029fb0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029fb0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029ef3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029ef3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002a08d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002a08d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a1fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a2c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a44d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a586`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a1fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a2c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a44d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a28f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a28f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180029f98`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a12a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a502`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180029f98`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a12a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a502`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a0ab`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a0ab`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002a568`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002a568`

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
  unsigned int v12; // esi
  char *v13; // r15
  STRSAFE_PCNZWCH v14; // rcx
  __int64 v15; // rdx
  int v16; // r12d
  unsigned int v17; // r15d
  HTTP_REQUEST_ID RequestId; // rdx
  __int64 (__fastcall *v19)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD); // rax
  HANDLE v20; // rcx
  DWORD v21; // ebx
  STRSAFE_PCNZWCH v22; // rcx
  STRSAFE_PCNZWCH v23; // rcx
  DWORD v24; // eax
  DWORD v25; // ecx
  HTTP_REQUEST_ID v26; // rdx
  __int64 (__fastcall *v27)(HANDLE, HTTP_REQUEST_ID, _QWORD); // rax
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  STRSAFE_PCNZWCH v32; // rcx
  __int64 v33; // rdx
  int v34; // r8d
  void *v35; // rbx
  DWORD v36; // eax
  signed int v37; // eax
  signed int LastError; // eax
  char *v39; // [rsp+40h] [rbp-29h]
  HANDLE hEvent[2]; // [rsp+48h] [rbp-21h] BYREF
  _OVERLAPPED Overlapped; // [rsp+58h] [rbp-11h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+D0h] [rbp+67h] BYREF
  void *v43; // [rsp+D8h] [rbp+6Fh]
  DWORD TickCount; // [rsp+E0h] [rbp+77h]
  unsigned int v45; // [rsp+E8h] [rbp+7Fh]

  v43 = a2;
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
  v45 = *(_DWORD *)((char *)this + v9);
  v12 = v45;
  *(_OWORD *)&Overlapped.Internal = 0;
  if ( v45 > 0x19000 )
    v12 = 102400;
  *(_OWORD *)&Overlapped.Offset = 0;
  *(_OWORD *)hEvent = 0;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  hEvent[0] = this[39];
  hEvent[1] = CreateEventW(0, 1, 0, 0);
  if ( !hEvent[1] )
  {
    v13 = 0;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_64;
    v15 = 95;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  v39 = (char *)malloc(v12 + 1);
  v13 = v39;
  if ( !v39 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_64;
    v15 = 97;
LABEL_17:
    WPP_SF_(*((_QWORD *)v14 + 2), v15, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    goto LABEL_64;
  }
  v16 = 0;
  v17 = 0;
  TickCount = GetTickCount();
  while ( 1 )
  {
    while ( 1 )
    {
      memset(&Overlapped, 0, sizeof(Overlapped));
      if ( !ResetEvent(hEvent[1]) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v4);
        }
        goto LABEL_63;
      }
      RequestId = a3->RequestId;
      Overlapped.hEvent = hEvent[1];
      v19 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD))this[9];
      v20 = this[15];
      NumberOfBytesTransferred = 0;
      v21 = v19(v20, RequestId, 0, &v39[v17], v12 - v17, 0, &Overlapped);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v21);
          v22 = WPP_GLOBAL_Control;
        }
        if ( v22 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v22 + 7) & 0x100) != 0 )
          WPP_SF_d(*((_QWORD *)v22 + 2), 100, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, NumberOfBytesTransferred);
      }
      if ( v21 == 997 || !v21 )
      {
        if ( WaitForMultipleObjectsEx(2u, hEvent, 0, 0xFFFFFFFF, 0) != 1 )
        {
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
          }
          if ( (CancelIoEx(this[15], &Overlapped) || GetLastError() != 1168)
            && WaitForSingleObject(hEvent[1], 0xFFFFFFFF)
            && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            v37 = GetLastError();
            if ( v37 > 0 )
              v37 = (unsigned __int16)v37 | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              104,
              WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
              (unsigned int)v37);
          }
          v4 = 0;
          goto LABEL_63;
        }
        if ( GetOverlappedResult(this[15], &Overlapped, &NumberOfBytesTransferred, 0) )
          v21 = 0;
        else
          v21 = GetLastError();
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v21);
            v23 = WPP_GLOBAL_Control;
          }
          if ( v23 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x100) != 0 )
            WPP_SF_d(
              *((_QWORD *)v23 + 2),
              102,
              WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
              NumberOfBytesTransferred);
        }
      }
      if ( GetTickCount() > TickCount + 120000 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v36 = GetTickCount();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
            v36 - TickCount);
        }
        goto LABEL_100;
      }
      if ( v21 )
        break;
      if ( NumberOfBytesTransferred )
      {
        v16 += NumberOfBytesTransferred;
        v17 += NumberOfBytesTransferred;
      }
      if ( WaitForSingleObject(this[39], 0) != 258 )
      {
        v4 = 0;
LABEL_63:
        v13 = v39;
        goto LABEL_64;
      }
    }
    if ( v21 == 38 )
      break;
    if ( v21 != 234 )
    {
      if ( v21 == 995 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v33 = 111;
LABEL_90:
          WPP_SF_(*((_QWORD *)v32 + 2), v33, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
        }
LABEL_91:
        v4 = -2147467259;
LABEL_83:
        IsEnabled = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl);
        goto LABEL_63;
      }
      if ( v21 != 1229 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v21);
        goto LABEL_91;
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
LABEL_100:
      v4 = -2147467259;
      goto LABEL_63;
    }
    v24 = NumberOfBytesTransferred;
    if ( NumberOfBytesTransferred < 0x8000 )
      v24 = 0x8000;
    v25 = v45 - v17;
    if ( v24 < v45 - v17 )
    {
      if ( NumberOfBytesTransferred < 0x8000 )
      {
        v25 = 0x8000;
        goto LABEL_56;
      }
      v25 = NumberOfBytesTransferred;
    }
    if ( !v25 )
      goto LABEL_87;
LABEL_56:
    if ( v25 < NumberOfBytesTransferred )
    {
LABEL_87:
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v33 = 106;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    v12 = v25 + v17;
    if ( v25 + v17 < v17 )
    {
      v4 = -2147024362;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
          2147942934LL);
      goto LABEL_83;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v12);
    }
    v39 = (char *)_o_realloc(v39, v12 + 1);
    if ( !v39 )
    {
      v4 = -2147024882;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
      goto LABEL_83;
    }
    v4 = 0;
    if ( WaitForSingleObject(this[39], 0) != 258 )
      goto LABEL_63;
  }
  if ( NumberOfBytesTransferred )
    v16 += NumberOfBytesTransferred;
  v4 = 0;
  if ( WaitForSingleObject(this[39], 0) != 258 || *((_DWORD *)this + 82) )
    goto LABEL_63;
  v35 = v43;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_qs(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, v34, (_DWORD)v43, (__int64)a3->pRawUrl);
  v13 = v39;
  v4 = (*((__int64 (__fastcall **)(HANDLE *, void *, struct _HTTP_REQUEST_V2 *, char *, int, HANDLE))*this + 1))(
         this,
         v35,
         a3,
         v39,
         v16,
         this[15]);
LABEL_64:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    if ( IsEnabled )
    {
      v26 = a3->RequestId;
      if ( v26 )
      {
        v27 = (__int64 (__fastcall *)(HANDLE, HTTP_REQUEST_ID, _QWORD))this[5];
        if ( v27 )
        {
          v28 = v27(this[15], v26, 0);
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_Id(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, v30, a3->RequestId, v28);
        }
      }
    }
  }
  free(a3);
  if ( v13 )
    free(v13);
  if ( hEvent[1] )
    CloseHandle(hEvent[1]);
  return v4;
}

```

## disassembly

```asm
0x180029e18  mov     [rsp-8+arg_8], rdx
0x180029e1d  push    rbp
0x180029e1e  push    rbx
0x180029e1f  push    rsi
0x180029e20  push    rdi
0x180029e21  push    r12
0x180029e23  push    r13
0x180029e25  push    r14
0x180029e27  push    r15
0x180029e29  lea     rbp, [rsp-1Fh]
0x180029e2e  sub     rsp, 88h
0x180029e35  mov     r9d, [r8+24h]
0x180029e39  xor     ebx, ebx
0x180029e3b  xor     r13d, r13d
0x180029e3e  mov     [rbp+57h+NumberOfBytesTransferred], ebx
0x180029e41  mov     r14, r8
0x180029e44  mov     rdi, rcx
0x180029e47  sub     r9d, 1
0x180029e4b  jz      short loc_180029E61
0x180029e4d  cmp     r9d, 5
0x180029e51  jz      short loc_180029E5A
0x180029e53  mov     edx, 144h
0x180029e58  jmp     short loc_180029E87
0x180029e5a  mov     edx, 140h
0x180029e5f  jmp     short loc_180029E87
0x180029e61  mov     rcx, [r14+30h]; String1
0x180029e65  lea     rdx, aMPost; "M-POST"
0x180029e6c  mov     r8d, 6; MaxCount
0x180029e72  call    cs:__imp__strnicmp
0x180029e78  mov     ecx, 144h
0x180029e7d  test    eax, eax
0x180029e7f  lea     edx, [rcx-4]
0x180029e82  cmovz   ecx, edx
0x180029e85  mov     edx, ecx
0x180029e87  mov     eax, [rdx+rdi]
0x180029e8a  xorps   xmm0, xmm0
0x180029e8d  mov     ecx, 19000h
0x180029e92  mov     [rbp+57h+arg_18], eax
0x180029e95  cmp     eax, ecx
0x180029e97  mov     esi, eax
0x180029e99  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180029e9d  cmova   esi, ecx
0x180029ea0  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180029ea4  movups  xmmword ptr [rbp+57h+hEvent], xmm0
0x180029ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180029eaf  lea     r12, WPP_GLOBAL_Control
0x180029eb6  mov     r15d, 100h
0x180029ebc  cmp     rcx, r12
0x180029ebf  jz      short loc_180029EDC
0x180029ec1  test    [rcx+1Ch], r15d
0x180029ec5  jz      short loc_180029EDC
0x180029ec7  mov     rcx, [rcx+10h]
0x180029ecb  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180029ed2  mov     edx, 5Eh ; '^'
0x180029ed7  call    WPP_SF_
0x180029edc  mov     rax, [rdi+138h]
0x180029ee3  xor     r9d, r9d; lpName
0x180029ee6  xor     r8d, r8d; bInitialState
0x180029ee9  mov     [rbp+57h+hEvent], rax
0x180029eed  xor     ecx, ecx; lpEventAttributes
0x180029eef  lea     edx, [r9+1]; bManualReset
0x180029ef3  call    cs:__imp_CreateEventW
0x180029ef9  mov     [rbp+57h+hEvent+8], rax
0x180029efd  test    rax, rax
0x180029f00  jnz     short loc_180029F37
0x180029f02  xor     r15d, r15d
0x180029f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f0c  cmp     rcx, r12
0x180029f0f  jz      loc_18002A219
0x180029f15  test    byte ptr [rcx+1Ch], 1
0x180029f19  jz      loc_18002A219
0x180029f1f  lea     edx, [rax+5Fh]
0x180029f22  mov     rcx, [rcx+10h]
0x180029f26  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180029f2d  call    WPP_SF_
0x180029f32  jmp     loc_18002A219
0x180029f37  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f3e  cmp     rcx, r12
0x180029f41  jz      short loc_180029F5E
0x180029f43  test    [rcx+1Ch], r15d
0x180029f47  jz      short loc_180029F5E
0x180029f49  mov     rcx, [rcx+10h]
0x180029f4d  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180029f54  mov     edx, 60h ; '`'
0x180029f59  call    WPP_SF_
0x180029f5e  lea     ecx, [rsi+1]; Size
0x180029f61  call    cs:__imp_malloc
0x180029f67  mov     [rbp+57h+var_80], rax
0x180029f6b  mov     r15, rax
0x180029f6e  test    rax, rax
0x180029f71  jnz     short loc_180029F92
0x180029f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f7a  cmp     rcx, r12
0x180029f7d  jz      loc_18002A219
0x180029f83  test    byte ptr [rcx+1Ch], 1
0x180029f87  jz      loc_18002A219
0x180029f8d  lea     edx, [rax+61h]
0x180029f90  jmp     short loc_180029F22
0x180029f92  xor     r12d, r12d
0x180029f95  xor     r15d, r15d
0x180029f98  call    cs:__imp_GetTickCount
0x180029f9e  mov     [rbp+57h+arg_10], eax
0x180029fa1  mov     rcx, [rbp+57h+hEvent+8]; hEvent
0x180029fa5  xorps   xmm0, xmm0
0x180029fa8  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180029fac  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180029fb0  call    cs:__imp_ResetEvent
0x180029fb6  test    eax, eax
0x180029fb8  jz      loc_18002A5DD
0x180029fbe  mov     rax, [rbp+57h+hEvent+8]
0x180029fc2  mov     ecx, esi
0x180029fc4  mov     rdx, [r14+10h]
0x180029fc8  sub     ecx, r15d
0x180029fcb  mov     [rbp+57h+Overlapped.hEvent], rax
0x180029fcf  xor     r8d, r8d
0x180029fd2  lea     rax, [rbp+57h+Overlapped]
0x180029fd6  mov     r9d, r15d
0x180029fd9  add     r9, [rbp+57h+var_80]
0x180029fdd  mov     [rsp+0C0h+var_90], rax
0x180029fe2  mov     rax, [rdi+48h]
0x180029fe6  mov     [rsp+0C0h+var_98], r13
0x180029feb  mov     [rsp+0C0h+bAlertable], ecx
0x180029fef  mov     rcx, [rdi+78h]
0x180029ff3  mov     [rbp+57h+NumberOfBytesTransferred], r13d
0x180029ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ffc  mov     ebx, eax
0x180029ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a005  lea     rax, WPP_GLOBAL_Control
0x18002a00c  cmp     rcx, rax
0x18002a00f  jz      short loc_18002A067
0x18002a011  test    dword ptr [rcx+1Ch], 100h
0x18002a018  jz      short loc_18002A040
0x18002a01a  mov     rcx, [rcx+10h]
0x18002a01e  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002a025  mov     edx, 63h ; 'c'
0x18002a02a  mov     r9d, ebx
0x18002a02d  call    WPP_SF_d
0x18002a032  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a039  lea     rax, WPP_GLOBAL_Control
0x18002a040  cmp     rcx, rax
0x18002a043  jz      short loc_18002A067
0x18002a045  test    dword ptr [rcx+1Ch], 100h
0x18002a04c  jz      short loc_18002A067
0x18002a04e  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x18002a052  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002a059  mov     rcx, [rcx+10h]
0x18002a05d  mov     edx, 64h ; 'd'
0x18002a062  call    WPP_SF_d
0x18002a067  cmp     ebx, 3E5h
0x18002a06d  jz      short loc_18002A077
0x18002a06f  test    ebx, ebx
0x18002a071  jnz     loc_18002A12A
0x18002a077  xor     r8d, r8d; bWaitAll
0x18002a07a  mov     [rsp+0C0h+bAlertable], r13d; bAlertable
0x18002a07f  or      ebx, 0FFFFFFFFh
0x18002a082  lea     rdx, [rbp+57h+hEvent]; lpHandles
0x18002a086  mov     r9d, ebx; dwMilliseconds
0x18002a089  lea     ecx, [r8+2]; nCount
0x18002a08d  call    cs:__imp_WaitForMultipleObjectsEx
0x18002a093  cmp     eax, 1
0x18002a096  jnz     loc_18002A52F
0x18002a09c  mov     rcx, [rdi+78h]; hFile
0x18002a0a0  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002a0a4  xor     r9d, r9d; bWait
0x18002a0a7  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002a0ab  call    cs:__imp_GetOverlappedResult
0x18002a0b1  test    eax, eax
0x18002a0b3  jz      short loc_18002A0B9
0x18002a0b5  xor     ebx, ebx
0x18002a0b7  jmp     short loc_18002A0C1
0x18002a0b9  call    cs:__imp_GetLastError
0x18002a0bf  mov     ebx, eax
0x18002a0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0c8  lea     rax, WPP_GLOBAL_Control
0x18002a0cf  cmp     rcx, rax
0x18002a0d2  jz      short loc_18002A12A
0x18002a0d4  test    dword ptr [rcx+1Ch], 100h
0x18002a0db  jz      short loc_18002A103
0x18002a0dd  mov     rcx, [rcx+10h]
0x18002a0e1  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002a0e8  mov     edx, 65h ; 'e'
0x18002a0ed  mov     r9d, ebx
0x18002a0f0  call    WPP_SF_d
0x18002a0f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0fc  lea     rax, WPP_GLOBAL_Control
0x18002a103  cmp     rcx, rax
0x18002a106  jz      short loc_18002A12A
0x18002a108  test    dword ptr [rcx+1Ch], 100h
0x18002a10f  jz      short loc_18002A12A
0x18002a111  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x18002a115  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002a11c  mov     rcx, [rcx+10h]
0x18002a120  mov     edx, 66h ; 'f'
0x18002a125  call    WPP_SF_d
0x18002a12a  call    cs:__imp_GetTickCount
0x18002a130  mov     ecx, eax
0x18002a132  mov     eax, [rbp+57h+arg_10]
0x18002a135  add     eax, 1D4C0h
0x18002a13a  cmp     ecx, eax
0x18002a13c  ja      loc_18002A4E1
0x18002a142  test    ebx, ebx
0x18002a144  jz      loc_18002A2AB
0x18002a14a  cmp     ebx, 26h ; '&'
0x18002a14d  jz      loc_18002A43A
0x18002a153  cmp     ebx, 0EAh
0x18002a159  jnz     loc_18002A394
0x18002a15f  mov     edx, [rbp+57h+NumberOfBytesTransferred]
0x18002a162  mov     r8d, 8000h
0x18002a168  mov     ecx, [rbp+57h+arg_18]
0x18002a16b  cmp     edx, r8d
0x18002a16e  mov     eax, edx
0x18002a170  cmovb   eax, r8d
0x18002a174  sub     ecx, r15d
0x18002a177  cmp     eax, ecx
0x18002a179  jnb     short loc_18002A187
0x18002a17b  cmp     edx, r8d
0x18002a17e  jnb     short loc_18002A185
0x18002a180  mov     ecx, r8d
0x18002a183  jmp     short loc_18002A18F
0x18002a185  mov     ecx, edx
0x18002a187  test    ecx, ecx
0x18002a189  jz      loc_18002A35C
0x18002a18f  cmp     ecx, edx
0x18002a191  jb      loc_18002A35C
0x18002a197  lea     esi, [rcx+r15]
0x18002a19b  cmp     esi, r15d
0x18002a19e  jb      loc_18002A321
0x18002a1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1ab  lea     rax, WPP_GLOBAL_Control
0x18002a1b2  cmp     rcx, rax
0x18002a1b5  jz      short loc_18002A1D8
0x18002a1b7  test    dword ptr [rcx+1Ch], 100h
0x18002a1be  jz      short loc_18002A1D8
0x18002a1c0  mov     rcx, [rcx+10h]
0x18002a1c4  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002a1cb  mov     edx, 6Ch ; 'l'
0x18002a1d0  mov     r9d, esi
0x18002a1d3  call    WPP_SF_d
0x18002a1d8  mov     rcx, [rbp+57h+var_80]
0x18002a1dc  lea     edx, [rsi+1]
0x18002a1df  call    cs:__imp__o_realloc
0x18002a1e5  mov     [rbp+57h+var_80], rax
0x18002a1e9  test    rax, rax
0x18002a1ec  jz      loc_18002A2D9
0x18002a1f2  mov     rcx, [rdi+138h]; hHandle
0x18002a1f9  xor     edx, edx; dwMilliseconds
0x18002a1fb  xor     ebx, ebx
0x18002a1fd  call    cs:__imp_WaitForSingleObject
0x18002a203  cmp     eax, 102h
0x18002a208  jz      loc_180029FA1
0x18002a20e  lea     r12, WPP_GLOBAL_Control
0x18002a215  mov     r15, [rbp+57h+var_80]
0x18002a219  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18002a220  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18002a225  test    al, al
0x18002a227  jz      short loc_18002A26F
0x18002a229  test    r13d, r13d
0x18002a22c  jz      short loc_18002A26F
0x18002a22e  mov     rdx, [r14+10h]
0x18002a232  test    rdx, rdx
0x18002a235  jz      short loc_18002A26F
0x18002a237  mov     rax, [rdi+28h]
0x18002a23b  test    rax, rax
0x18002a23e  jz      short loc_18002A26F
0x18002a240  mov     rcx, [rdi+78h]
0x18002a244  xor     r8d, r8d
0x18002a247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a24c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a253  cmp     rcx, r12
0x18002a256  jz      short loc_18002A26F
0x18002a258  test    byte ptr [rcx+1Ch], 1
0x18002a25c  jz      short loc_18002A26F
0x18002a25e  mov     r9, [r14+10h]
0x18002a262  mov     rcx, [rcx+10h]
0x18002a266  mov     [rsp+0C0h+bAlertable], eax
0x18002a26a  call    WPP_SF_Id
0x18002a26f  mov     rcx, r14; Block
0x18002a272  call    cs:__imp_free
0x18002a278  test    r15, r15
0x18002a27b  jz      short loc_18002A286
0x18002a27d  mov     rcx, r15; Block
0x18002a280  call    cs:__imp_free
0x18002a286  mov     rcx, [rbp+57h+hEvent+8]; hObject
0x18002a28a  test    rcx, rcx
0x18002a28d  jz      short loc_18002A295
0x18002a28f  call    cs:__imp_CloseHandle
0x18002a295  mov     eax, ebx
0x18002a297  add     rsp, 88h
0x18002a29e  pop     r15
0x18002a2a0  pop     r14
0x18002a2a2  pop     r13
0x18002a2a4  pop     r12
0x18002a2a6  pop     rdi
0x18002a2a7  pop     rsi
0x18002a2a8  pop     rbx
0x18002a2a9  pop     rbp
0x18002a2aa  retn
0x18002a2ab  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x18002a2ae  test    eax, eax
0x18002a2b0  jz      short loc_18002A2B8
  ... truncated ...
```
