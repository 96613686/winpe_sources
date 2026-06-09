# BaseHttpListener::HandleHTTPRequestWrapper(void *,_HTTP_REQUEST_V2 *)

- ea: `0x18002b1d4`
- end: `0x18002ba74`
- name: `?HandleHTTPRequestWrapper@BaseHttpListener@@IEAAJPEAXPEAU_HTTP_REQUEST_V2@@@Z`
- size: `2208`
- prototype: `__int64 __fastcall(HANDLE *this, void *, struct _HTTP_REQUEST_V2 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002b0e0`
- `0x180054660`

## callees

- `0x18002b1d4`
- `0x18003b1cc`
- `0x18003c018`
- `0x18004e098`
- `0x180054e68`
- `0x180054f2c`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18002b22e`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18002b22e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002b670`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002b684`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002b670`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002b684`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002b329`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002b329`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002b5d1`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002b5d1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b384`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002b384`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b2b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b2b5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002b467`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002b467`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b5f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b6d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b864`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b9b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b5f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b6d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b864`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b699`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b366`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b516`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b91f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b366`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b516`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b91f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002b48b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002b48b`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002b98b`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18002b98b`

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
0x18002b1d4  mov     [rsp-8+arg_8], rdx
0x18002b1d9  push    rbp
0x18002b1da  push    rbx
0x18002b1db  push    rsi
0x18002b1dc  push    rdi
0x18002b1dd  push    r12
0x18002b1df  push    r13
0x18002b1e1  push    r14
0x18002b1e3  push    r15
0x18002b1e5  lea     rbp, [rsp-1Fh]
0x18002b1ea  sub     rsp, 88h
0x18002b1f1  mov     r9d, [r8+24h]
0x18002b1f5  xor     ebx, ebx
0x18002b1f7  xor     r13d, r13d
0x18002b1fa  mov     [rbp+57h+NumberOfBytesTransferred], ebx
0x18002b1fd  mov     r14, r8
0x18002b200  mov     rdi, rcx
0x18002b203  sub     r9d, 1
0x18002b207  jz      short loc_18002B21D
0x18002b209  cmp     r9d, 5
0x18002b20d  jz      short loc_18002B216
0x18002b20f  mov     edx, 144h
0x18002b214  jmp     short loc_18002B249
0x18002b216  mov     edx, 140h
0x18002b21b  jmp     short loc_18002B249
0x18002b21d  mov     rcx, [r14+30h]; String1
0x18002b221  lea     rdx, aMPost; "M-POST"
0x18002b228  mov     r8d, 6; MaxCount
0x18002b22e  call    cs:__imp__strnicmp
0x18002b235  nop     dword ptr [rax+rax+00h]
0x18002b23a  mov     ecx, 144h
0x18002b23f  test    eax, eax
0x18002b241  lea     edx, [rcx-4]
0x18002b244  cmovz   ecx, edx
0x18002b247  mov     edx, ecx
0x18002b249  mov     eax, [rdx+rdi]
0x18002b24c  xorps   xmm0, xmm0
0x18002b24f  mov     ecx, 19000h
0x18002b254  mov     [rbp+57h+arg_18], eax
0x18002b257  cmp     eax, ecx
0x18002b259  mov     esi, eax
0x18002b25b  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002b25f  cmova   esi, ecx
0x18002b262  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002b266  movups  xmmword ptr [rbp+57h+hEvent], xmm0
0x18002b26a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b271  lea     r12, WPP_GLOBAL_Control
0x18002b278  mov     r15d, 100h
0x18002b27e  cmp     rcx, r12
0x18002b281  jz      short loc_18002B29E
0x18002b283  test    [rcx+1Ch], r15d
0x18002b287  jz      short loc_18002B29E
0x18002b289  mov     rcx, [rcx+10h]
0x18002b28d  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b294  mov     edx, 5Eh ; '^'
0x18002b299  call    WPP_SF_
0x18002b29e  mov     rax, [rdi+138h]
0x18002b2a5  xor     r9d, r9d; lpName
0x18002b2a8  xor     r8d, r8d; bInitialState
0x18002b2ab  mov     [rbp+57h+hEvent], rax
0x18002b2af  xor     ecx, ecx; lpEventAttributes
0x18002b2b1  lea     edx, [r9+1]; bManualReset
0x18002b2b5  call    cs:__imp_CreateEventW
0x18002b2bc  nop     dword ptr [rax+rax+00h]
0x18002b2c1  mov     [rbp+57h+hEvent+8], rax
0x18002b2c5  test    rax, rax
0x18002b2c8  jnz     short loc_18002B2FF
0x18002b2ca  xor     r15d, r15d
0x18002b2cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2d4  cmp     rcx, r12
0x18002b2d7  jz      loc_18002B617
0x18002b2dd  test    byte ptr [rcx+1Ch], 1
0x18002b2e1  jz      loc_18002B617
0x18002b2e7  lea     edx, [rax+5Fh]
0x18002b2ea  mov     rcx, [rcx+10h]
0x18002b2ee  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b2f5  call    WPP_SF_
0x18002b2fa  jmp     loc_18002B617
0x18002b2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b306  cmp     rcx, r12
0x18002b309  jz      short loc_18002B326
0x18002b30b  test    [rcx+1Ch], r15d
0x18002b30f  jz      short loc_18002B326
0x18002b311  mov     rcx, [rcx+10h]
0x18002b315  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b31c  mov     edx, 60h ; '`'
0x18002b321  call    WPP_SF_
0x18002b326  lea     ecx, [rsi+1]; Size
0x18002b329  call    cs:__imp_malloc
0x18002b330  nop     dword ptr [rax+rax+00h]
0x18002b335  mov     [rbp+57h+var_80], rax
0x18002b339  mov     r15, rax
0x18002b33c  test    rax, rax
0x18002b33f  jnz     short loc_18002B360
0x18002b341  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b348  cmp     rcx, r12
0x18002b34b  jz      loc_18002B617
0x18002b351  test    byte ptr [rcx+1Ch], 1
0x18002b355  jz      loc_18002B617
0x18002b35b  lea     edx, [rax+61h]
0x18002b35e  jmp     short loc_18002B2EA
0x18002b360  xor     r12d, r12d
0x18002b363  xor     r15d, r15d
0x18002b366  call    cs:__imp_GetTickCount
0x18002b36d  nop     dword ptr [rax+rax+00h]
0x18002b372  mov     [rbp+57h+arg_10], eax
0x18002b375  mov     rcx, [rbp+57h+hEvent+8]; hEvent
0x18002b379  xorps   xmm0, xmm0
0x18002b37c  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002b380  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002b384  call    cs:__imp_ResetEvent
0x18002b38b  nop     dword ptr [rax+rax+00h]
0x18002b390  test    eax, eax
0x18002b392  jz      loc_18002BA18
0x18002b398  mov     rax, [rbp+57h+hEvent+8]
0x18002b39c  mov     ecx, esi
0x18002b39e  mov     rdx, [r14+10h]
0x18002b3a2  sub     ecx, r15d
0x18002b3a5  mov     [rbp+57h+Overlapped.hEvent], rax
0x18002b3a9  xor     r8d, r8d
0x18002b3ac  lea     rax, [rbp+57h+Overlapped]
0x18002b3b0  mov     r9d, r15d
0x18002b3b3  add     r9, [rbp+57h+var_80]
0x18002b3b7  mov     [rsp+0C0h+var_90], rax
0x18002b3bc  mov     rax, [rdi+48h]
0x18002b3c0  mov     [rsp+0C0h+var_98], r13
0x18002b3c5  mov     [rsp+0C0h+bAlertable], ecx
0x18002b3c9  mov     rcx, [rdi+78h]
0x18002b3cd  mov     [rbp+57h+NumberOfBytesTransferred], r13d
0x18002b3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3d6  mov     ebx, eax
0x18002b3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3df  lea     rax, WPP_GLOBAL_Control
0x18002b3e6  cmp     rcx, rax
0x18002b3e9  jz      short loc_18002B441
0x18002b3eb  test    dword ptr [rcx+1Ch], 100h
0x18002b3f2  jz      short loc_18002B41A
0x18002b3f4  mov     rcx, [rcx+10h]
0x18002b3f8  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b3ff  mov     edx, 63h ; 'c'
0x18002b404  mov     r9d, ebx
0x18002b407  call    WPP_SF_d
0x18002b40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b413  lea     rax, WPP_GLOBAL_Control
0x18002b41a  cmp     rcx, rax
0x18002b41d  jz      short loc_18002B441
0x18002b41f  test    dword ptr [rcx+1Ch], 100h
0x18002b426  jz      short loc_18002B441
0x18002b428  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x18002b42c  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b433  mov     rcx, [rcx+10h]
0x18002b437  mov     edx, 64h ; 'd'
0x18002b43c  call    WPP_SF_d
0x18002b441  cmp     ebx, 3E5h
0x18002b447  jz      short loc_18002B451
0x18002b449  test    ebx, ebx
0x18002b44b  jnz     loc_18002B516
0x18002b451  xor     r8d, r8d; bWaitAll
0x18002b454  mov     [rsp+0C0h+bAlertable], r13d; bAlertable
0x18002b459  or      ebx, 0FFFFFFFFh
0x18002b45c  lea     rdx, [rbp+57h+hEvent]; lpHandles
0x18002b460  mov     r9d, ebx; dwMilliseconds
0x18002b463  lea     ecx, [r8+2]; nCount
0x18002b467  call    cs:__imp_WaitForMultipleObjectsEx
0x18002b46e  nop     dword ptr [rax+rax+00h]
0x18002b473  cmp     eax, 1
0x18002b476  jnz     loc_18002B952
0x18002b47c  mov     rcx, [rdi+78h]; hFile
0x18002b480  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002b484  xor     r9d, r9d; bWait
0x18002b487  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002b48b  call    cs:__imp_GetOverlappedResult
0x18002b492  nop     dword ptr [rax+rax+00h]
0x18002b497  test    eax, eax
0x18002b499  jz      short loc_18002B49F
0x18002b49b  xor     ebx, ebx
0x18002b49d  jmp     short loc_18002B4AD
0x18002b49f  call    cs:__imp_GetLastError
0x18002b4a6  nop     dword ptr [rax+rax+00h]
0x18002b4ab  mov     ebx, eax
0x18002b4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4b4  lea     rax, WPP_GLOBAL_Control
0x18002b4bb  cmp     rcx, rax
0x18002b4be  jz      short loc_18002B516
0x18002b4c0  test    dword ptr [rcx+1Ch], 100h
0x18002b4c7  jz      short loc_18002B4EF
0x18002b4c9  mov     rcx, [rcx+10h]
0x18002b4cd  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b4d4  mov     edx, 65h ; 'e'
0x18002b4d9  mov     r9d, ebx
0x18002b4dc  call    WPP_SF_d
0x18002b4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4e8  lea     rax, WPP_GLOBAL_Control
0x18002b4ef  cmp     rcx, rax
0x18002b4f2  jz      short loc_18002B516
0x18002b4f4  test    dword ptr [rcx+1Ch], 100h
0x18002b4fb  jz      short loc_18002B516
0x18002b4fd  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x18002b501  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b508  mov     rcx, [rcx+10h]
0x18002b50c  mov     edx, 66h ; 'f'
0x18002b511  call    WPP_SF_d
0x18002b516  call    cs:__imp_GetTickCount
0x18002b51d  nop     dword ptr [rax+rax+00h]
0x18002b522  mov     ecx, eax
0x18002b524  mov     eax, [rbp+57h+arg_10]
0x18002b527  add     eax, 1D4C0h
0x18002b52c  cmp     ecx, eax
0x18002b52e  ja      loc_18002B8FE
0x18002b534  test    ebx, ebx
0x18002b536  jz      loc_18002B6BC
0x18002b53c  cmp     ebx, 26h ; '&'
0x18002b53f  jz      loc_18002B851
0x18002b545  cmp     ebx, 0EAh
0x18002b54b  jnz     loc_18002B7AB
0x18002b551  mov     edx, [rbp+57h+NumberOfBytesTransferred]
0x18002b554  mov     r8d, 8000h
0x18002b55a  mov     ecx, [rbp+57h+arg_18]
0x18002b55d  cmp     edx, r8d
0x18002b560  mov     eax, edx
0x18002b562  cmovb   eax, r8d
0x18002b566  sub     ecx, r15d
0x18002b569  cmp     eax, ecx
0x18002b56b  jnb     short loc_18002B579
0x18002b56d  cmp     edx, r8d
0x18002b570  jnb     short loc_18002B577
0x18002b572  mov     ecx, r8d
0x18002b575  jmp     short loc_18002B581
0x18002b577  mov     ecx, edx
0x18002b579  test    ecx, ecx
0x18002b57b  jz      loc_18002B773
0x18002b581  cmp     ecx, edx
0x18002b583  jb      loc_18002B773
0x18002b589  lea     esi, [rcx+r15]
0x18002b58d  cmp     esi, r15d
0x18002b590  jb      loc_18002B738
0x18002b596  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b59d  lea     rax, WPP_GLOBAL_Control
0x18002b5a4  cmp     rcx, rax
0x18002b5a7  jz      short loc_18002B5CA
0x18002b5a9  test    dword ptr [rcx+1Ch], 100h
0x18002b5b0  jz      short loc_18002B5CA
0x18002b5b2  mov     rcx, [rcx+10h]
0x18002b5b6  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002b5bd  mov     edx, 6Ch ; 'l'
0x18002b5c2  mov     r9d, esi
0x18002b5c5  call    WPP_SF_d
0x18002b5ca  mov     rcx, [rbp+57h+var_80]
0x18002b5ce  lea     edx, [rsi+1]
0x18002b5d1  call    cs:__imp__o_realloc
0x18002b5d8  nop     dword ptr [rax+rax+00h]
0x18002b5dd  mov     [rbp+57h+var_80], rax
0x18002b5e1  test    rax, rax
0x18002b5e4  jz      loc_18002B6F0
0x18002b5ea  mov     rcx, [rdi+138h]; hHandle
0x18002b5f1  xor     edx, edx; dwMilliseconds
0x18002b5f3  xor     ebx, ebx
0x18002b5f5  call    cs:__imp_WaitForSingleObject
0x18002b5fc  nop     dword ptr [rax+rax+00h]
0x18002b601  cmp     eax, 102h
0x18002b606  jz      loc_18002B375
0x18002b60c  lea     r12, WPP_GLOBAL_Control
0x18002b613  mov     r15, [rbp+57h+var_80]
0x18002b617  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18002b61e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18002b623  test    al, al
0x18002b625  jz      short loc_18002B66D
0x18002b627  test    r13d, r13d
0x18002b62a  jz      short loc_18002B66D
0x18002b62c  mov     rdx, [r14+10h]
0x18002b630  test    rdx, rdx
0x18002b633  jz      short loc_18002B66D
0x18002b635  mov     rax, [rdi+28h]
0x18002b639  test    rax, rax
0x18002b63c  jz      short loc_18002B66D
0x18002b63e  mov     rcx, [rdi+78h]
0x18002b642  xor     r8d, r8d
0x18002b645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b651  cmp     rcx, r12
0x18002b654  jz      short loc_18002B66D
0x18002b656  test    byte ptr [rcx+1Ch], 1
0x18002b65a  jz      short loc_18002B66D
0x18002b65c  mov     r9, [r14+10h]
0x18002b660  mov     rcx, [rcx+10h]
0x18002b664  mov     [rsp+0C0h+bAlertable], eax
0x18002b668  call    WPP_SF_Id
0x18002b66d  mov     rcx, r14; Block
0x18002b670  call    cs:__imp_free
0x18002b677  nop     dword ptr [rax+rax+00h]
0x18002b67c  test    r15, r15
0x18002b67f  jz      short loc_18002B690
0x18002b681  mov     rcx, r15; Block
0x18002b684  call    cs:__imp_free
0x18002b68b  nop     dword ptr [rax+rax+00h]
0x18002b690  mov     rcx, [rbp+57h+hEvent+8]; hObject
0x18002b694  test    rcx, rcx
0x18002b697  jz      short loc_18002B6A5
0x18002b699  call    cs:__imp_CloseHandle
0x18002b6a0  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
