# OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard(void)

- ea: `0x180018f18`
- end: `0x180019005`
- name: `??1SandboxAccessMutexGuard@OSDeploymentHelper@@QEAA@XZ`
- size: `237`
- prototype: `void __fastcall(OSDeploymentHelper::SandboxAccessMutexGuard *__hidden this)`
- caller_count: `13`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001d2b0`
- `0x18001fe7c`
- `0x180021730`
- `0x180021d90`
- `0x180025850`
- `0x180028ea8`
- `0x18002a83c`
- `0x18002d114`
- `0x18004a56d`
- `0x18004a621`
- `0x18004aa12`
- `0x18004ab44`
- `0x18004ac9a`

## callees

- `0x180005f64`
- `0x18000956c`
- `0x18000a448`
- `0x180018f18`
- `0x180019c64`
- `0x18001a8b8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fe7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fe7`

## string_xrefs

- `0x180018f6f`: `Failed to release sandbox access mutex %ws`

## pseudocode

```c
void __fastcall OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard(
        OSDeploymentHelper::SandboxAccessMutexGuard *this)
{
  void *v2; // rdx
  void *v3; // rcx
  void *v4; // rcx
  _BYTE v5[88]; // [rsp+40h] [rbp-58h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl)
    && *(_QWORD *)this )
  {
    if ( (int)OSDeploymentHelper::ReleaseSandboxAccessMutex(*(OSDeploymentHelper **)this, v2) < 0 )
    {
      if ( !*((_QWORD *)this + 3) )
        Trace::GuidToString::GuidToString((Trace::GuidToString *)v5, (const struct _GUID *)((char *)this + 8));
      WUTrace(0, 0, 4096, 4);
    }
    if ( *(_QWORD *)this )
    {
      CloseHandle(*(HANDLE *)this);
      *(_QWORD *)this = 0;
    }
    *(GUID *)((char *)this + 8) = GUID_NULL;
    v3 = (void *)*((_QWORD *)this + 3);
    if ( v3 )
    {
      CSusBaseAllocTag<942762101>::operator delete(v3);
      *((_QWORD *)this + 3) = 0;
    }
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v4);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *(_QWORD *)this )
  {
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180018f18  mov     [rsp+arg_0], rbx
0x180018f1d  push    rdi
0x180018f1e  sub     rsp, 90h
0x180018f25  mov     rbx, rcx
0x180018f28  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x180018f2f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x180018f34  test    al, al
0x180018f36  jz      loc_180018FC9
0x180018f3c  mov     rcx, [rbx]; this
0x180018f3f  test    rcx, rcx
0x180018f42  jz      loc_180018FC9
0x180018f48  call    ?ReleaseSandboxAccessMutex@OSDeploymentHelper@@YAJPEAX@Z; OSDeploymentHelper::ReleaseSandboxAccessMutex(void *)
0x180018f4d  mov     edi, eax
0x180018f4f  test    eax, eax
0x180018f51  jns     short loc_180018F92
0x180018f53  mov     rax, [rbx+18h]
0x180018f57  test    rax, rax
0x180018f5a  jnz     short loc_180018F6A
0x180018f5c  lea     rdx, [rbx+8]; struct _GUID *
0x180018f60  lea     rcx, [rsp+98h+var_58]; this
0x180018f65  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180018f6a  mov     [rsp+98h+var_68], rax
0x180018f6f  lea     rax, aFailedToReleas; "Failed to release sandbox access mutex "...
0x180018f76  mov     [rsp+98h+var_70], rax
0x180018f7b  mov     [rsp+98h+var_78], edi
0x180018f7f  xor     edx, edx
0x180018f81  xor     ecx, ecx
0x180018f83  lea     r9d, [rdx+4]
0x180018f87  mov     r8d, 1000h
0x180018f8d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180018f92  mov     rcx, [rbx]; hObject
0x180018f95  test    rcx, rcx
0x180018f98  jz      short loc_180018FA7
0x180018f9a  call    cs:__imp_CloseHandle
0x180018fa0  mov     qword ptr [rbx], 0
0x180018fa7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180018fae  movdqu  xmmword ptr [rbx+8], xmm0
0x180018fb3  mov     rcx, [rbx+18h]; lpMem
0x180018fb7  test    rcx, rcx
0x180018fba  jz      short loc_180018FC9
0x180018fbc  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180018fc1  mov     qword ptr [rbx+18h], 0
0x180018fc9  mov     rcx, [rbx+18h]; lpMem
0x180018fcd  test    rcx, rcx
0x180018fd0  jz      short loc_180018FDF
0x180018fd2  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180018fd7  mov     qword ptr [rbx+18h], 0
0x180018fdf  mov     rcx, [rbx]; hObject
0x180018fe2  test    rcx, rcx
0x180018fe5  jz      short loc_180018FF4
0x180018fe7  call    cs:__imp_CloseHandle
0x180018fed  mov     qword ptr [rbx], 0
0x180018ff4  mov     rbx, [rsp+98h+arg_0]
0x180018ffc  add     rsp, 90h
0x180019003  pop     rdi
0x180019004  retn
```
