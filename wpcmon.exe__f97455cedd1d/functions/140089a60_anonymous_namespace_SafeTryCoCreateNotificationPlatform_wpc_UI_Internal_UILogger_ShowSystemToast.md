# _anonymous_namespace_::SafeTryCoCreateNotificationPlatform_wpc::UI::Internal::UILogger::ShowSystemToast_

- ea: `0x140089a60`
- end: `0x140089b11`
- name: `_anonymous_namespace_::SafeTryCoCreateNotificationPlatform_wpc::UI::Internal::UILogger::ShowSystemToast_`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400893e8`

## callees

- `0x1400461d8`
- `0x14008997c`
- `0x140089a60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140089aa5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140089aa5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140089ae0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140089ae0`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::SafeTryCoCreateNotificationPlatform_wpc::UI::Internal::UILogger::ShowSystemToast_(
        __int64 *a1,
        __int64 a2)
{
  int v2; // ebx
  unsigned int v4; // edi
  __int64 *ppv; // rax
  HRESULT Instance; // ebp
  unsigned int v8; // edx
  unsigned __int64 v9; // rcx
  unsigned int v10; // eax
  int v12; // [rsp+70h] [rbp+8h] BYREF

  v2 = 1;
  v12 = 1;
  v4 = 1;
  do
  {
    ppv = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(a1);
    Instance = CoCreateInstance(
                 &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                 0,
                 0x17u,
                 &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                 (LPVOID *)ppv);
    if ( Instance >= 0 )
      break;
    v8 = 1;
    LODWORD(v9) = 1000;
    if ( v4 > 1 )
    {
      do
      {
        v9 = 2LL * (unsigned int)v9;
        if ( v9 > 0xFFFFFFFF )
        {
          LODWORD(v9) = 128000;
          goto LABEL_10;
        }
        ++v8;
      }
      while ( v8 < v4 );
      if ( (unsigned int)v9 > 0x1F400 )
        LODWORD(v9) = 128000;
    }
LABEL_10:
    Sleep(v9);
    v10 = v2++;
    v4 = v2;
  }
  while ( v10 < 0xB );
  v12 = v2;
  wpc::UI::Internal::UILogger::ShowSystemToast::Retries<unsigned int &>(a2, &v12);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140089a60  push    rbx
0x140089a62  push    rbp
0x140089a63  push    rsi
0x140089a64  push    rdi
0x140089a65  push    r12
0x140089a67  push    r14
0x140089a69  sub     rsp, 38h
0x140089a6d  mov     ebx, 1
0x140089a72  mov     rsi, rdx
0x140089a75  mov     [rsp+68h+arg_0], ebx
0x140089a79  mov     edi, ebx
0x140089a7b  mov     r14, rcx
0x140089a7e  mov     r12d, 1F400h
0x140089a84  mov     rcx, r14
0x140089a87  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x140089a8c  xor     edx, edx; pUnkOuter
0x140089a8e  mov     [rsp+68h+ppv], rax; ppv
0x140089a93  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x140089a9a  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x140089aa1  lea     r8d, [rdx+17h]; dwClsContext
0x140089aa5  call    cs:__imp_CoCreateInstance
0x140089aab  mov     ebp, eax
0x140089aad  test    eax, eax
0x140089aaf  jns     short loc_140089AF1
0x140089ab1  mov     edx, 1
0x140089ab6  mov     ecx, 3E8h
0x140089abb  cmp     edi, edx
0x140089abd  jbe     short loc_140089AE0
0x140089abf  mov     ecx, ecx
0x140089ac1  mov     eax, 0FFFFFFFFh
0x140089ac6  add     rcx, rcx
0x140089ac9  cmp     rcx, rax
0x140089acc  ja      short loc_140089ADD
0x140089ace  inc     edx
0x140089ad0  cmp     edx, edi
0x140089ad2  jb      short loc_140089ABF
0x140089ad4  cmp     ecx, r12d
0x140089ad7  cmova   ecx, r12d
0x140089adb  jmp     short loc_140089AE0
0x140089add  mov     ecx, r12d; dwMilliseconds
0x140089ae0  call    cs:__imp_Sleep
0x140089ae6  mov     eax, ebx
0x140089ae8  inc     ebx
0x140089aea  mov     edi, ebx
0x140089aec  cmp     eax, 0Bh
0x140089aef  jb      short loc_140089A84
0x140089af1  lea     rdx, [rsp+68h+arg_0]
0x140089af6  mov     [rsp+68h+arg_0], ebx
0x140089afa  mov     rcx, rsi
0x140089afd  call    ??$Retries@AEAI@ShowSystemToast@UILogger@Internal@UI@wpc@@QEAAXAEAI@Z; wpc::UI::Internal::UILogger::ShowSystemToast::Retries<uint &>(uint &)
0x140089b02  mov     eax, ebp
0x140089b04  add     rsp, 38h
0x140089b08  pop     r14
0x140089b0a  pop     r12
0x140089b0c  pop     rdi
0x140089b0d  pop     rsi
0x140089b0e  pop     rbp
0x140089b0f  pop     rbx
0x140089b10  retn
```
