# wpc::AppTimeLimits::UI::Private::SafeTryCoCreateNotificationPlatform<wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast>(Microsoft::WRL::ComPtr<IWpnPlatform> &,wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast &)

- ea: `0x140046d88`
- end: `0x140046e8c`
- name: `??$SafeTryCoCreateNotificationPlatform@VShowAppTimeLimitToast@MonitorUILogger@Logging@UI@wpc@@@Private@UI@AppTimeLimits@wpc@@YAJAEAV?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@AEAVShowAppTimeLimitToast@MonitorUILogger@Logging@13@@Z`
- size: `260`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140045d90`

## callees

- `0x140005530`
- `0x14000ccac`
- `0x14002a754`
- `0x1400461d8`
- `0x140046b98`
- `0x140046d88`
- `0x14006065c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140046ddf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140046ddf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140046e43`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140046e43`

## string_xrefs

- `0x140046df1`: `Create push notification platform hr=0x%x, retries=%d`

## pseudocode

```c
__int64 __fastcall wpc::AppTimeLimits::UI::Private::SafeTryCoCreateNotificationPlatform<wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast>(
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
  wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast::Retries<unsigned int &>(a2, &v14);
  return v8;
}

```

## disassembly

```asm
0x140046d88  mov     [rsp+arg_10], rbx
0x140046d8d  push    rbp
0x140046d8e  push    rsi
0x140046d8f  push    rdi
0x140046d90  push    r12
0x140046d92  push    r14
0x140046d94  sub     rsp, 60h
0x140046d98  mov     rax, cs:__security_cookie
0x140046d9f  xor     rax, rsp
0x140046da2  mov     [rsp+88h+var_30], rax
0x140046da7  mov     rbp, rdx
0x140046daa  mov     r14, rcx
0x140046dad  mov     ebx, 1
0x140046db2  mov     [rsp+88h+var_58], ebx
0x140046db6  mov     edi, ebx
0x140046db8  mov     r12d, 1F400h
0x140046dbe  mov     rcx, r14
0x140046dc1  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x140046dc6  mov     [rsp+88h+ppv], rax; ppv
0x140046dcb  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x140046dd2  xor     edx, edx; pUnkOuter
0x140046dd4  lea     r8d, [rdx+17h]; dwClsContext
0x140046dd8  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x140046ddf  call    cs:__imp_CoCreateInstance
0x140046de5  mov     esi, eax
0x140046de7  test    eax, eax
0x140046de9  jns     short loc_140046E58
0x140046deb  mov     r9d, ebx
0x140046dee  mov     r8d, eax
0x140046df1  lea     rdx, aCreatePushNoti; "Create push notification platform hr=0x"...
0x140046df8  lea     rcx, [rsp+88h+var_50]
0x140046dfd  call    ?Format@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; StringAlgo::Format(ushort const *,...)
0x140046e02  mov     rcx, rax
0x140046e05  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x140046e0a  lea     rcx, [rsp+88h+var_50]
0x140046e0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140046e14  mov     ecx, 3E8h
0x140046e19  mov     eax, 1
0x140046e1e  cmp     edi, eax
0x140046e20  jbe     short loc_140046E43
0x140046e22  mov     ecx, ecx
0x140046e24  add     rcx, rcx
0x140046e27  mov     edx, 0FFFFFFFFh
0x140046e2c  cmp     rcx, rdx
0x140046e2f  ja      short loc_140046E40
0x140046e31  inc     eax
0x140046e33  cmp     eax, edi
0x140046e35  jb      short loc_140046E22
0x140046e37  cmp     ecx, r12d
0x140046e3a  cmova   ecx, r12d
0x140046e3e  jmp     short loc_140046E43
0x140046e40  mov     ecx, r12d; dwMilliseconds
0x140046e43  call    cs:__imp_Sleep
0x140046e49  mov     eax, ebx
0x140046e4b  inc     ebx
0x140046e4d  mov     edi, ebx
0x140046e4f  cmp     eax, 0Bh
0x140046e52  jb      loc_140046DBE
0x140046e58  mov     [rsp+88h+var_58], ebx
0x140046e5c  lea     rdx, [rsp+88h+var_58]
0x140046e61  mov     rcx, rbp
0x140046e64  call    ??$Retries@AEAI@ShowAppTimeLimitToast@MonitorUILogger@Logging@UI@wpc@@QEAAXAEAI@Z; wpc::UI::Logging::MonitorUILogger::ShowAppTimeLimitToast::Retries<uint &>(uint &)
0x140046e69  mov     eax, esi
0x140046e6b  mov     rcx, [rsp+88h+var_30]
0x140046e70  xor     rcx, rsp; StackCookie
0x140046e73  call    __security_check_cookie
0x140046e78  mov     rbx, [rsp+88h+arg_10]
0x140046e80  add     rsp, 60h
0x140046e84  pop     r14
0x140046e86  pop     r12
0x140046e88  pop     rdi
0x140046e89  pop     rsi
0x140046e8a  pop     rbp
0x140046e8b  retn
```
