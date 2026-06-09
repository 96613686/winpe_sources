# CBrokeredAppointmentsManager::_RemoveAppointmentAsyncInternal(HSTRING__ *,Windows::Foundation::Rect,Windows::UI::Popups::Placement,Windows::Foundation::DateTime *,Windows::Foundation::IAsyncOperation<bool> * *)

- ea: `0x180186338`
- end: `0x1801864dc`
- name: `?_RemoveAppointmentAsyncInternal@CBrokeredAppointmentsManager@@CAJPEAUHSTRING__@@URect@Foundation@Windows@@W4Placement@Popups@UI@5@PEAUDateTime@45@PEAPEAU?$IAsyncOperation@_N@45@@Z`
- size: `420`
- prototype: `__int64 __usercall@<rax>(HSTRING string@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180185200`
- `0x180185240`
- `0x180185280`

## callees

- `0x180054170`
- `0x18013d330`
- `0x18017c988`
- `0x18017c9e0`
- `0x18017de80`
- `0x180182e10`
- `0x18018622c`
- `0x180186338`
- `0x18036dd0c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801863f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801863f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801863bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801863bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801863a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801863e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018648b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801864a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801864ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801863a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801863e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018648b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801864a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801864ac`

## pseudocode

```c
__int64 __fastcall CBrokeredAppointmentsManager::_RemoveAppointmentAsyncInternal(
        HSTRING string,
        __int128 *a2,
        int a3,
        __int64 *a4,
        _QWORD *a5)
{
  int CallingApplicationWindowAndVerifyVisibility; // edi
  unsigned __int16 **v10; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  char v15; // dl
  void *v16; // rbx
  LPVOID v17; // r8
  __int128 v18; // xmm0
  __int64 v19; // rax
  __int64 v20; // r8
  _BYTE v22[12]; // [rsp+20h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  HWND v24; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  __int128 v26; // [rsp+48h] [rbp-38h]
  int v27; // [rsp+58h] [rbp-28h]
  char v28; // [rsp+5Ch] [rbp-24h]
  __int64 v29; // [rsp+60h] [rbp-20h]
  LPVOID v30; // [rsp+68h] [rbp-18h]
  HWND v31; // [rsp+70h] [rbp-10h]

  v24 = 0;
  pv = 0;
  *a5 = 0;
  CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(
                                                  &v24,
                                                  0);
  if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
  {
    CoTaskMemFree(0);
    CallingApplicationWindowAndVerifyVisibility = CallerIdentity::GetCallingProcessPackageFamilyName(
                                                    (CallerIdentity *)&pv,
                                                    v10);
    if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
    {
      if ( WindowsIsStringEmpty(string) )
      {
        CallingApplicationWindowAndVerifyVisibility = -2147024809;
        OriginateErrorWithResourceString(-2147024809, 0, 0x2BC8u);
      }
      else
      {
        *(_QWORD *)v22 = 0;
        CoTaskMemFree(0);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        CallingApplicationWindowAndVerifyVisibility = _AllocString<CTCoAllocPolicy>(v13, v12, StringRawBuffer, v22);
        if ( CallingApplicationWindowAndVerifyVisibility < 0 )
        {
          v16 = *(void **)v22;
        }
        else
        {
          if ( a4 )
          {
            v14 = *a4;
            v15 = 1;
          }
          else
          {
            v14 = 0;
            v15 = 0;
          }
          v16 = 0;
          v17 = pv;
          v18 = *a2;
          v29 = v14;
          v25 = *(_QWORD *)v22;
          v26 = v18;
          pv = 0;
          v27 = a3;
          v28 = v15;
          v30 = v17;
          v31 = v24;
          *(_DWORD *)v22 = 1;
          *(_QWORD *)&v22[4] = 4;
          v19 = Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<unsigned char,0>,_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_,>(&v25);
          CallingApplicationWindowAndVerifyVisibility = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<unsigned char,0>,bool,Windows::Internal::ComTaskPoolHandler>(
                                                          v22,
                                                          a5,
                                                          v20,
                                                          v19);
          _lambda_d8c49c8fa3285360fd222d9d6c5e0a24_::~_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_((_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_ *)&v25);
          CoTaskMemFree(0);
          CoTaskMemFree(0);
        }
        CoTaskMemFree(v16);
      }
    }
  }
  CoTaskMemFree(pv);
  return (unsigned int)CallingApplicationWindowAndVerifyVisibility;
}

```

## disassembly

```asm
0x180186338  mov     [rsp-28h+arg_8], rbx
0x18018633d  mov     [rsp-28h+arg_10], rsi
0x180186342  push    rbp
0x180186343  push    rdi
0x180186344  push    r12
0x180186346  push    r14
0x180186348  push    r15
0x18018634a  mov     rbp, rsp
0x18018634d  sub     rsp, 80h
0x180186354  mov     rax, cs:__security_cookie
0x18018635b  xor     rax, rsp
0x18018635e  mov     [rbp+var_8], rax
0x180186362  mov     r14, [rbp+arg_20]
0x180186366  mov     r12, rdx
0x180186369  mov     rsi, rcx
0x18018636c  mov     [rbp+var_48], 0
0x180186374  xor     edx, edx; unsigned __int16 **
0x180186376  mov     [rbp+pv], 0
0x18018637e  lea     rcx, [rbp+var_48]; this
0x180186382  mov     rbx, r9
0x180186385  mov     qword ptr [r14], 0
0x18018638c  mov     r15d, r8d
0x18018638f  call    ?_GetCallingApplicationWindowAndVerifyVisibility@CBrokeredAppointmentsManager@@CAJPEAPEAUHWND__@@PEAPEAG@Z; CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(HWND__ * *,ushort * *)
0x180186394  mov     edi, eax
0x180186396  test    eax, eax
0x180186398  js      loc_1801864A8
0x18018639e  xor     ecx, ecx; pv
0x1801863a0  call    cs:__imp_CoTaskMemFree
0x1801863a6  lea     rcx, [rbp+pv]; this
0x1801863aa  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x1801863af  mov     edi, eax
0x1801863b1  test    eax, eax
0x1801863b3  js      loc_1801864A8
0x1801863b9  mov     rcx, rsi; string
0x1801863bc  call    cs:__imp_WindowsIsStringEmpty
0x1801863c2  test    eax, eax
0x1801863c4  jz      short loc_1801863DF
0x1801863c6  mov     edi, 80070057h
0x1801863cb  xor     edx, edx; HINSTANCE
0x1801863cd  mov     ecx, edi; int
0x1801863cf  mov     r8d, 2BC8h; unsigned int
0x1801863d5  call    ?OriginateErrorWithResourceString@@YAXJPEAUHINSTANCE__@@I@Z; OriginateErrorWithResourceString(long,HINSTANCE__ *,uint)
0x1801863da  jmp     loc_1801864A8
0x1801863df  xor     ecx, ecx; pv
0x1801863e1  mov     [rbp+var_60], 0
0x1801863e9  call    cs:__imp_CoTaskMemFree
0x1801863ef  xor     edx, edx; length
0x1801863f1  mov     rcx, rsi; string
0x1801863f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1801863fa  mov     r8, rax
0x1801863fd  lea     r9, [rbp+var_60]
0x180186401  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180186406  mov     edi, eax
0x180186408  test    eax, eax
0x18018640a  js      loc_18018649B
0x180186410  test    rbx, rbx
0x180186413  jz      short loc_18018641C
0x180186415  mov     rax, [rbx]
0x180186418  mov     dl, 1
0x18018641a  jmp     short loc_180186420
0x18018641c  xor     eax, eax
0x18018641e  xor     dl, dl
0x180186420  mov     rcx, [rbp+var_60]
0x180186424  xor     ebx, ebx
0x180186426  mov     r8, [rbp+pv]
0x18018642a  movups  xmm0, xmmword ptr [r12]
0x18018642f  mov     [rbp+var_20], rax
0x180186433  mov     rax, [rbp+var_48]
0x180186437  mov     [rbp+var_40], rcx
0x18018643b  lea     rcx, [rbp+var_40]
0x18018643f  movdqu  [rbp+var_38], xmm0
0x180186444  mov     [rbp+pv], 0
0x18018644c  mov     [rbp+var_28], r15d
0x180186450  mov     [rbp+var_24], dl
0x180186453  mov     [rbp+var_18], r8
0x180186457  mov     [rbp+var_10], rax
0x18018645b  mov     dword ptr [rbp+var_60], 1
0x180186462  mov     [rbp+var_60+4], 4
0x18018646a  call    ??$MakeOpLambda@$0A@V?$CBasicResult@E$0A@@Internal@Windows@@V_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CBasicResult@E$0A@@Internal@Windows@@@01@$$QEAV_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_@@@Z; Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<uchar,0>,_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_,>(_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_ &&)
0x18018646f  mov     r9, rax
0x180186472  lea     rcx, [rbp+var_60]
0x180186476  mov     rdx, r14
0x180186479  call    ??$MakeAsyncOperationHelper@V?$CBasicResult@E$0A@@Internal@Windows@@_NVComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@_N@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@E$0A@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<uchar,0>,bool,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<bool> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<uchar,0>> *)
0x18018647e  lea     rcx, [rbp+var_40]; this
0x180186482  mov     edi, eax
0x180186484  call    ??1_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_@@QEAA@XZ; _lambda_d8c49c8fa3285360fd222d9d6c5e0a24_::~_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_(void)
0x180186489  xor     ecx, ecx; pv
0x18018648b  call    cs:__imp_CoTaskMemFree
0x180186491  xor     ecx, ecx; pv
0x180186493  call    cs:__imp_CoTaskMemFree
0x180186499  jmp     short loc_18018649F
0x18018649b  mov     rbx, [rbp+var_60]
0x18018649f  mov     rcx, rbx; pv
0x1801864a2  call    cs:__imp_CoTaskMemFree
0x1801864a8  mov     rcx, [rbp+pv]; pv
0x1801864ac  call    cs:__imp_CoTaskMemFree
0x1801864b2  mov     eax, edi
0x1801864b4  mov     rcx, [rbp+var_8]
0x1801864b8  xor     rcx, rsp; StackCookie
0x1801864bb  call    __security_check_cookie
0x1801864c0  lea     r11, [rsp+80h+var_s0]
0x1801864c8  mov     rbx, [r11+38h]
0x1801864cc  mov     rsi, [r11+40h]
0x1801864d0  mov     rsp, r11
0x1801864d3  pop     r15
0x1801864d5  pop     r14
0x1801864d7  pop     r12
0x1801864d9  pop     rdi
0x1801864da  pop     rbp
0x1801864db  retn
```
