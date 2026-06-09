# wpc::AppTimeLimits::UI::Private::SafeTryCoCreateNotificationPlatform<wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast>(Microsoft::WRL::ComPtr<IWpnPlatform> &,wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast &)

- ea: `0x140046c7c`
- end: `0x140046d80`
- name: `??$SafeTryCoCreateNotificationPlatform@VClearAppTimeLimitToast@MonitorUILogger@Logging@UI@wpc@@@Private@UI@AppTimeLimits@wpc@@YAJAEAV?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@AEAVClearAppTimeLimitToast@MonitorUILogger@Logging@13@@Z`
- size: `260`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140045730`

## callees

- `0x140005530`
- `0x14000ccac`
- `0x14002a754`
- `0x1400461d8`
- `0x140046ab4`
- `0x140046c7c`
- `0x14006065c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140046cd3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140046cd3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140046d37`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140046d37`

## string_xrefs

- `0x140046ce5`: `Create push notification platform hr=0x%x, retries=%d`

## pseudocode

```c
__int64 __fastcall wpc::AppTimeLimits::UI::Private::SafeTryCoCreateNotificationPlatform<wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast>(
        __int64 *a1,
        __int64 a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // edi
  __int64 *ppv; // rax
  HRESULT Instance; // eax
  unsigned int v8; // esi
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v14; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-50h] BYREF

  v4 = 1;
  v14 = 1;
  v5 = 1;
  do
  {
    ppv = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(a1);
    Instance = CoCreateInstance(
                 &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                 0,
                 0x17u,
                 &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                 (LPVOID *)ppv);
    v8 = Instance;
    if ( Instance >= 0 )
      break;
    v9 = StringAlgo::Format(v15, L"Create push notification platform hr=0x%x, retries=%d", (unsigned int)Instance, v4);
    wpc::UI::Logging::MonitorUILogger::LogMessage(v9);
    std::wstring::~wstring(v15);
    LODWORD(v10) = 1000;
    v11 = 1;
    if ( v5 > 1 )
    {
      do
      {
        v10 = 2LL * (unsigned int)v10;
        if ( v10 > 0xFFFFFFFF )
        {
          LODWORD(v10) = 128000;
          goto LABEL_10;
        }
        ++v11;
      }
      while ( v11 < v5 );
      if ( (unsigned int)v10 > 0x1F400 )
        LODWORD(v10) = 128000;
    }
LABEL_10:
    Sleep(v10);
    v12 = v4++;
    v5 = v4;
  }
  while ( v12 < 0xB );
  v14 = v4;
  wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast::Retries<unsigned int &>(a2, &v14);
  return v8;
}

```

## disassembly

```asm
0x140046c7c  mov     [rsp+arg_10], rbx
0x140046c81  push    rbp
0x140046c82  push    rsi
0x140046c83  push    rdi
0x140046c84  push    r12
0x140046c86  push    r14
0x140046c88  sub     rsp, 60h
0x140046c8c  mov     rax, cs:__security_cookie
0x140046c93  xor     rax, rsp
0x140046c96  mov     [rsp+88h+var_30], rax
0x140046c9b  mov     rbp, rdx
0x140046c9e  mov     r14, rcx
0x140046ca1  mov     ebx, 1
0x140046ca6  mov     [rsp+88h+var_58], ebx
0x140046caa  mov     edi, ebx
0x140046cac  mov     r12d, 1F400h
0x140046cb2  mov     rcx, r14
0x140046cb5  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x140046cba  mov     [rsp+88h+ppv], rax; ppv
0x140046cbf  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x140046cc6  xor     edx, edx; pUnkOuter
0x140046cc8  lea     r8d, [rdx+17h]; dwClsContext
0x140046ccc  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x140046cd3  call    cs:__imp_CoCreateInstance
0x140046cd9  mov     esi, eax
0x140046cdb  test    eax, eax
0x140046cdd  jns     short loc_140046D4C
0x140046cdf  mov     r9d, ebx
0x140046ce2  mov     r8d, eax
0x140046ce5  lea     rdx, aCreatePushNoti; "Create push notification platform hr=0x"...
0x140046cec  lea     rcx, [rsp+88h+var_50]
0x140046cf1  call    ?Format@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; StringAlgo::Format(ushort const *,...)
0x140046cf6  mov     rcx, rax
0x140046cf9  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x140046cfe  lea     rcx, [rsp+88h+var_50]
0x140046d03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140046d08  mov     ecx, 3E8h
0x140046d0d  mov     eax, 1
0x140046d12  cmp     edi, eax
0x140046d14  jbe     short loc_140046D37
0x140046d16  mov     ecx, ecx
0x140046d18  add     rcx, rcx
0x140046d1b  mov     edx, 0FFFFFFFFh
0x140046d20  cmp     rcx, rdx
0x140046d23  ja      short loc_140046D34
0x140046d25  inc     eax
0x140046d27  cmp     eax, edi
0x140046d29  jb      short loc_140046D16
0x140046d2b  cmp     ecx, r12d
0x140046d2e  cmova   ecx, r12d
0x140046d32  jmp     short loc_140046D37
0x140046d34  mov     ecx, r12d; dwMilliseconds
0x140046d37  call    cs:__imp_Sleep
0x140046d3d  mov     eax, ebx
0x140046d3f  inc     ebx
0x140046d41  mov     edi, ebx
0x140046d43  cmp     eax, 0Bh
0x140046d46  jb      loc_140046CB2
0x140046d4c  mov     [rsp+88h+var_58], ebx
0x140046d50  lea     rdx, [rsp+88h+var_58]
0x140046d55  mov     rcx, rbp
0x140046d58  call    ??$Retries@AEAI@ClearAppTimeLimitToast@MonitorUILogger@Logging@UI@wpc@@QEAAXAEAI@Z; wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast::Retries<uint &>(uint &)
0x140046d5d  mov     eax, esi
0x140046d5f  mov     rcx, [rsp+88h+var_30]
0x140046d64  xor     rcx, rsp; StackCookie
0x140046d67  call    __security_check_cookie
0x140046d6c  mov     rbx, [rsp+88h+arg_10]
0x140046d74  add     rsp, 60h
0x140046d78  pop     r14
0x140046d7a  pop     r12
0x140046d7c  pop     rdi
0x140046d7d  pop     rsi
0x140046d7e  pop     rbp
0x140046d7f  retn
```
