# COSDownloader::CancelDownloadRequest(void)

- ea: `0x18001fb58`
- end: `0x18001fe75`
- name: `?CancelDownloadRequest@COSDownloader@@QEAAXXZ`
- size: `797`
- prototype: `void __fastcall(COSDownloader *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180024f80`
- `0x180025690`

## callees

- `0x18000956c`
- `0x18000c0b4`
- `0x18001fb58`
- `0x180024050`
- `0x18002e9b4`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd9a`

## string_xrefs

- `0x18001fb9a`: `CancelDownloadRequest - GDR already cancelled`
- `0x18001fd4e`: `CancelDownloadRequest -  GDR already cancelled`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall COSDownloader::CancelDownloadRequest(COSDownloader *this)
{
  char IsEnabled; // al
  char v3; // cl
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 *v8; // r14
  int v9; // eax
  __int64 v10; // rax
  __int64 *v11; // rcx
  char *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 *v15; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl'::`2'::impl);
  v3 = *((_BYTE *)this + 16);
  if ( IsEnabled )
  {
    if ( v3 )
    {
LABEL_3:
      WUTrace(0, 0, 4096, 4);
      return;
    }
    WUTrace(0, 0, 4096, 4);
    *((_BYTE *)this + 16) = 1;
    if ( this != (COSDownloader *)-536LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
    v4 = *((_QWORD *)this + 73);
    if ( v4 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x26E,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
          (const char *)(unsigned int)v5,
          0);
    }
    if ( this != (COSDownloader *)-536LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
    if ( this != (COSDownloader *)-80LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v6 = *((_QWORD *)this + 17);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    }
    else
    {
      v7 = *((_QWORD *)this + 18);
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)this + 18) = 0;
    }
    v8 = (__int64 *)*((_QWORD *)this + 17);
    if ( this != (COSDownloader *)-80LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( v8 )
    {
      WUTrace(0, 0, 4096, 4);
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v8 + 32))(v8, 2149851144LL);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x28C,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
          (const char *)(unsigned int)v9,
          0);
      OSDeploymentRemote::RemoteDeploymentSessionWrapper::Shutdown((COSDownloader *)((char *)this + 480));
    }
    else
    {
      WUTrace(0, 0, 4096, 4);
    }
    if ( v8 )
    {
      v10 = *v8;
      v11 = v8;
LABEL_39:
      (*(void (__fastcall **)(__int64 *))(v10 + 16))(v11);
    }
  }
  else
  {
    if ( v3 )
      goto LABEL_3;
    WUTrace(0, 0, 4096, 4);
    *((_BYTE *)this + 16) = 1;
    v12 = (char *)this + 80;
    if ( this != (COSDownloader *)-80LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v13 = *((_QWORD *)this + 16);
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    }
    else
    {
      v14 = *((_QWORD *)this + 18);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *((_QWORD *)this + 18) = 0;
    }
    v15 = (__int64 *)*((_QWORD *)this + 16);
    if ( v12 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    WUTrace(0, 0, 4096, 4);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64 *, __int64))(*v15 + 64))(v15, 2149851144LL);
      v10 = *v15;
      v11 = v15;
      goto LABEL_39;
    }
  }
}

```

## disassembly

```asm
0x18001fb58  mov     [rsp+arg_8], rbx
0x18001fb5d  mov     [rsp+arg_10], rdi
0x18001fb62  push    r12
0x18001fb64  push    r14
0x18001fb66  push    r15
0x18001fb68  sub     rsp, 40h
0x18001fb6c  mov     rdi, rcx
0x18001fb6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl(void)'::`2'::impl
0x18001fb76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(void)
0x18001fb7b  mov     cl, [rdi+10h]
0x18001fb7e  xor     r12d, r12d
0x18001fb81  test    al, al
0x18001fb83  jz      loc_18001FD39
0x18001fb89  xor     edx, edx
0x18001fb8b  lea     r9d, [r12+4]
0x18001fb90  mov     r8d, 1000h
0x18001fb96  test    cl, cl
0x18001fb98  jz      short loc_18001FBB7
0x18001fb9a  lea     rax, aCanceldownload_0; "CancelDownloadRequest - GDR already can"...
0x18001fba1  mov     [rsp+58h+var_30], rax
0x18001fba6  mov     qword ptr [rsp+58h+var_38], r12
0x18001fbab  xor     ecx, ecx
0x18001fbad  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fbb2  jmp     loc_18001FE60
0x18001fbb7  lea     rax, aCanceldownload_4; "CancelDownloadRequest - GDR cancel"
0x18001fbbe  mov     [rsp+58h+var_30], rax
0x18001fbc3  mov     qword ptr [rsp+58h+var_38], r12; int
0x18001fbc8  xor     ecx, ecx
0x18001fbca  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fbcf  mov     byte ptr [rdi+10h], 1
0x18001fbd3  lea     rbx, [rdi+218h]
0x18001fbda  mov     [rsp+58h+var_28], rbx
0x18001fbdf  test    rbx, rbx
0x18001fbe2  jz      short loc_18001FBEF
0x18001fbe4  lea     rcx, [rbx+8]; lpCriticalSection
0x18001fbe8  call    cs:__imp_EnterCriticalSection
0x18001fbee  nop
0x18001fbef  mov     rcx, [rdi+248h]
0x18001fbf6  test    rcx, rcx
0x18001fbf9  jz      short loc_18001FC25
0x18001fbfb  mov     rax, [rcx]
0x18001fbfe  mov     rax, [rax+18h]
0x18001fc02  call    _guard_dispatch_icall
0x18001fc07  mov     rcx, [rsp+58h]; this
0x18001fc0c  test    eax, eax
0x18001fc0e  jns     short loc_18001FC25
0x18001fc10  mov     r9d, eax; char *
0x18001fc13  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001fc1a  mov     edx, 26Eh; void *
0x18001fc1f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fc24  nop
0x18001fc25  test    rbx, rbx
0x18001fc28  jz      short loc_18001FC34
0x18001fc2a  lea     rcx, [rbx+8]; lpCriticalSection
0x18001fc2e  call    cs:__imp_LeaveCriticalSection
0x18001fc34  mov     [rsp+58h+var_28], r12
0x18001fc39  lea     rbx, [rdi+50h]
0x18001fc3d  mov     [rsp+58h+var_20], rbx
0x18001fc42  test    rbx, rbx
0x18001fc45  jz      short loc_18001FC52
0x18001fc47  lea     rcx, [rbx+8]; lpCriticalSection
0x18001fc4b  call    cs:__imp_EnterCriticalSection
0x18001fc51  nop
0x18001fc52  mov     rcx, [rdi+88h]
0x18001fc59  test    rcx, rcx
0x18001fc5c  jz      short loc_18001FC6C
0x18001fc5e  mov     rax, [rcx]
0x18001fc61  mov     rax, [rax+8]
0x18001fc65  call    _guard_dispatch_icall
0x18001fc6a  jmp     short loc_18001FC8B
0x18001fc6c  mov     rcx, [rdi+90h]
0x18001fc73  test    rcx, rcx
0x18001fc76  jz      short loc_18001FC84
0x18001fc78  mov     rax, [rcx]
0x18001fc7b  mov     rax, [rax+10h]
0x18001fc7f  call    _guard_dispatch_icall
0x18001fc84  mov     [rdi+90h], r12
0x18001fc8b  mov     r14, [rdi+88h]
0x18001fc92  mov     [rsp+58h+var_28], r14
0x18001fc97  test    rbx, rbx
0x18001fc9a  jz      short loc_18001FCA6
0x18001fc9c  lea     rcx, [rbx+8]; lpCriticalSection
0x18001fca0  call    cs:__imp_LeaveCriticalSection
0x18001fca6  xor     edx, edx
0x18001fca8  xor     ecx, ecx
0x18001fcaa  lea     r9d, [rdx+4]
0x18001fcae  mov     r8d, 1000h
0x18001fcb4  test    r14, r14
0x18001fcb7  jnz     short loc_18001FCD1
0x18001fcb9  lea     rax, aCanceldownload_2; "CancelDownloadRequest - UUP deployment "...
0x18001fcc0  mov     [rsp+58h+var_30], rax
0x18001fcc5  mov     qword ptr [rsp+58h+var_38], r12
0x18001fcca  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fccf  jmp     short loc_18001FD25
0x18001fcd1  lea     rax, aCanceldownload_5; "CancelDownloadRequest - Cancelling UUP "...
0x18001fcd8  mov     [rsp+58h+var_30], rax
0x18001fcdd  mov     qword ptr [rsp+58h+var_38], r12; int
0x18001fce2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fce7  mov     rax, [r14]
0x18001fcea  mov     edx, 80242008h
0x18001fcef  mov     rcx, r14
0x18001fcf2  mov     rax, [rax+20h]
0x18001fcf6  call    _guard_dispatch_icall
0x18001fcfb  mov     rcx, [rsp+58h]; this
0x18001fd00  test    eax, eax
0x18001fd02  jns     short loc_18001FD18
0x18001fd04  mov     r9d, eax; char *
0x18001fd07  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001fd0e  mov     edx, 28Ch; void *
0x18001fd13  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fd18  lea     rcx, [rdi+1E0h]; this
0x18001fd1f  call    ?Shutdown@RemoteDeploymentSessionWrapper@OSDeploymentRemote@@QEAAXXZ; OSDeploymentRemote::RemoteDeploymentSessionWrapper::Shutdown(void)
0x18001fd24  nop
0x18001fd25  test    r14, r14
0x18001fd28  jz      loc_18001FE60
0x18001fd2e  mov     rax, [r14]
0x18001fd31  mov     rcx, r14
0x18001fd34  jmp     loc_18001FE56
0x18001fd39  mov     [rsp+58h+var_28], r12
0x18001fd3e  xor     edx, edx
0x18001fd40  lea     r9d, [rdx+4]
0x18001fd44  mov     r8d, 1000h
0x18001fd4a  test    cl, cl
0x18001fd4c  jz      short loc_18001FD6C
0x18001fd4e  lea     rax, aCanceldownload; "CancelDownloadRequest -  GDR already ca"...
0x18001fd55  mov     [rsp+58h+var_30], rax
0x18001fd5a  mov     qword ptr [rsp+58h+var_38], r12
0x18001fd5f  xor     ecx, ecx
0x18001fd61  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fd66  nop
0x18001fd67  jmp     loc_18001FE60
0x18001fd6c  lea     rax, aCanceldownload_3; "CancelDownloadRequest -  GDR cancel"
0x18001fd73  mov     [rsp+58h+var_30], rax
0x18001fd78  mov     qword ptr [rsp+58h+var_38], r12
0x18001fd7d  xor     ecx, ecx
0x18001fd7f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fd84  mov     byte ptr [rdi+10h], 1
0x18001fd88  lea     rbx, [rdi+50h]
0x18001fd8c  mov     [rsp+58h+var_20], rbx
0x18001fd91  test    rbx, rbx
0x18001fd94  jz      short loc_18001FDA1
0x18001fd96  lea     rcx, [rbx+8]; lpCriticalSection
0x18001fd9a  call    cs:__imp_EnterCriticalSection
0x18001fda0  nop
0x18001fda1  mov     rcx, [rdi+80h]
0x18001fda8  test    rcx, rcx
0x18001fdab  jz      short loc_18001FDBB
0x18001fdad  mov     rax, [rcx]
0x18001fdb0  mov     rax, [rax+8]
0x18001fdb4  call    _guard_dispatch_icall
0x18001fdb9  jmp     short loc_18001FDDA
0x18001fdbb  mov     rcx, [rdi+90h]
0x18001fdc2  test    rcx, rcx
0x18001fdc5  jz      short loc_18001FDD3
0x18001fdc7  mov     rax, [rcx]
0x18001fdca  mov     rax, [rax+10h]
0x18001fdce  call    _guard_dispatch_icall
0x18001fdd3  mov     [rdi+90h], r12
0x18001fdda  mov     rdi, [rdi+80h]
0x18001fde1  mov     [rsp+58h+var_28], rdi
0x18001fde6  test    rbx, rbx
0x18001fde9  jz      short loc_18001FDF5
0x18001fdeb  lea     rcx, [rbx+8]; lpCriticalSection
0x18001fdef  call    cs:__imp_LeaveCriticalSection
0x18001fdf5  xor     edx, edx
0x18001fdf7  xor     ecx, ecx
0x18001fdf9  lea     r9d, [rdx+4]
0x18001fdfd  mov     r8d, 1000h
0x18001fe03  test    rdi, rdi
0x18001fe06  jnz     short loc_18001FE20
0x18001fe08  lea     rax, aCanceldownload_1; "CancelDownloadRequest -  UUP deployment"...
0x18001fe0f  mov     [rsp+58h+var_30], rax
0x18001fe14  mov     qword ptr [rsp+58h+var_38], r12
0x18001fe19  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fe1e  jmp     short loc_18001FE4B
0x18001fe20  lea     rax, aCanceldownload_5; "CancelDownloadRequest - Cancelling UUP "...
0x18001fe27  mov     [rsp+58h+var_30], rax
0x18001fe2c  mov     qword ptr [rsp+58h+var_38], r12
0x18001fe31  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001fe36  mov     rax, [rdi]
0x18001fe39  mov     edx, 80242008h
0x18001fe3e  mov     rcx, rdi
0x18001fe41  mov     rax, [rax+40h]
0x18001fe45  call    _guard_dispatch_icall
0x18001fe4a  nop
0x18001fe4b  test    rdi, rdi
0x18001fe4e  jz      short loc_18001FE60
0x18001fe50  mov     rax, [rdi]
0x18001fe53  mov     rcx, rdi
0x18001fe56  mov     rax, [rax+10h]
0x18001fe5a  call    _guard_dispatch_icall
0x18001fe5f  nop
0x18001fe60  mov     rbx, [rsp+58h+arg_8]
0x18001fe65  mov     rdi, [rsp+58h+arg_10]
0x18001fe6a  add     rsp, 40h
0x18001fe6e  pop     r15
0x18001fe70  pop     r14
0x18001fe72  pop     r12
0x18001fe74  retn
```
