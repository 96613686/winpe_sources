# CThumbnailCache::GetThumbnailDimensionsByIDWithFlags(WTS_THUMBNAILID,uint,WTS_FLAGS,tagSIZE *)

- ea: `0x18002cc40`
- end: `0x18002cd9e`
- name: `?GetThumbnailDimensionsByIDWithFlags@CThumbnailCache@@UEAAJUWTS_THUMBNAILID@@IW4WTS_FLAGS@@PEAUtagSIZE@@@Z`
- size: `350`
- prototype: `__int64 __usercall@<rax>(CThumbnailCache *__hidden this@<rcx>, struct WTS_THUMBNAILID *__struct_ptr@<rdx>, unsigned int@<r8d>, enum WTS_FLAGS@<r9d>, struct tagSIZE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bfd8`
- `0x18000c6f4`
- `0x18000cb34`
- `0x18001455c`
- `0x180014cd0`
- `0x18002b11c`
- `0x18002cc40`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ccbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ccd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ccbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ccd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cce0`

## string_xrefs

- `0x18002cd4e`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThumbnailCache::GetThumbnailDimensionsByIDWithFlags(
        CThumbnailCache *this,
        struct WTS_THUMBNAILID *a2,
        unsigned int a3,
        enum WTS_FLAGS a4,
        struct tagSIZE *a5)
{
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  int DimensionsFromMoniker; // ebx
  __int64 v13; // rcx
  __int64 v14; // r8
  void *v15; // rcx
  void *v16; // rcx
  int v18; // [rsp+20h] [rbp-40h]
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h]
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  int v22; // [rsp+48h] [rbp-18h]
  int v23; // [rsp+4Ch] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  *a5 = 0;
  v9 = CThumbnailCache::_ValidateCallingThread(this);
  DimensionsFromMoniker = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1151,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v9,
      v18);
  }
  else
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v10, Thumbnails_GetAspectRatio_Start, v11, 1, &v19);
    DimensionsFromMoniker = CThumbnailCache::_Initialize(this, a4, a3);
    if ( DimensionsFromMoniker >= 0 )
    {
      v22 = *((_DWORD *)this + 192) & 1;
      v19 = 0;
      pv = 0;
      CoTaskMemFree(0);
      v23 = 0;
      v20 = 0;
      v15 = pv;
      pv = 0;
      CoTaskMemFree(v15);
      v16 = pv;
      pv = 0;
      CoTaskMemFree(v16);
      pv = 0;
      v23 = 0;
      v19 = *(_QWORD *)a2->rgbKey;
      v20 = 0x1100000000LL;
      DimensionsFromMoniker = CThumbnailCache::_TryGetDimensionsFromMoniker(
                                this,
                                (struct CThumbnailMoniker *)&v19,
                                a3,
                                a4,
                                a5);
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pv);
    }
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v13, Thumbnails_GetAspectRatio_Stop, v14, 1, &v19);
  }
  return (unsigned int)DimensionsFromMoniker;
}

```

## disassembly

```asm
0x18002cc40  push    rbp
0x18002cc42  push    rbx
0x18002cc43  push    rsi
0x18002cc44  push    rdi
0x18002cc45  push    r12
0x18002cc47  push    r14
0x18002cc49  push    r15
0x18002cc4b  mov     rbp, rsp
0x18002cc4e  sub     rsp, 60h
0x18002cc52  mov     rax, cs:__security_cookie
0x18002cc59  xor     rax, rsp
0x18002cc5c  mov     [rbp+var_10], rax
0x18002cc60  mov     r14d, r9d
0x18002cc63  mov     esi, r8d
0x18002cc66  mov     r12, rdx
0x18002cc69  mov     rdi, rcx
0x18002cc6c  mov     r15, [rbp+arg_20]
0x18002cc70  xor     eax, eax
0x18002cc72  mov     [r15], rax
0x18002cc75  call    ?_ValidateCallingThread@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_ValidateCallingThread(void)
0x18002cc7a  mov     ebx, eax
0x18002cc7c  test    eax, eax
0x18002cc7e  js      loc_18002CD47
0x18002cc84  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002cc8b  jnz     loc_18002CD61
0x18002cc91  mov     r8d, esi; int
0x18002cc94  mov     edx, r14d; enum WTS_FLAGS
0x18002cc97  mov     rcx, rdi; this
0x18002cc9a  call    ?_Initialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z; CThumbnailCache::_Initialize(WTS_FLAGS,int)
0x18002cc9f  mov     ebx, eax
0x18002cca1  test    eax, eax
0x18002cca3  js      short loc_18002CD21
0x18002cca5  mov     eax, [rdi+300h]
0x18002ccab  and     eax, 1
0x18002ccae  mov     [rbp+var_18], eax
0x18002ccb1  xor     ebx, ebx
0x18002ccb3  mov     [rbp+var_30], rbx
0x18002ccb7  mov     [rbp+pv], rbx
0x18002ccbb  xor     ecx, ecx; pv
0x18002ccbd  call    cs:__imp_CoTaskMemFree
0x18002ccc3  mov     [rbp+var_14], ebx
0x18002ccc6  mov     [rbp+var_28], rbx
0x18002ccca  mov     rcx, [rbp+pv]; pv
0x18002ccce  mov     [rbp+pv], rbx
0x18002ccd2  call    cs:__imp_CoTaskMemFree
0x18002ccd8  mov     rcx, [rbp+pv]; pv
0x18002ccdc  mov     [rbp+pv], rbx
0x18002cce0  call    cs:__imp_CoTaskMemFree
0x18002cce6  mov     [rbp+pv], rbx
0x18002ccea  mov     [rbp+var_14], ebx
0x18002cced  mov     rax, [r12]
0x18002ccf1  mov     [rbp+var_30], rax
0x18002ccf5  mov     dword ptr [rbp+var_28], ebx
0x18002ccf8  mov     dword ptr [rbp+var_28+4], 11h
0x18002ccff  mov     qword ptr [rsp+60h+var_40], r15; struct tagSIZE *
0x18002cd04  mov     r9d, r14d; enum WTS_FLAGS
0x18002cd07  mov     r8d, esi; unsigned int
0x18002cd0a  lea     rdx, [rbp+var_30]; struct CThumbnailMoniker *
0x18002cd0e  mov     rcx, rdi; this
0x18002cd11  call    ?_TryGetDimensionsFromMoniker@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@IW4WTS_FLAGS@@PEAUtagSIZE@@@Z; CThumbnailCache::_TryGetDimensionsFromMoniker(CThumbnailMoniker &,uint,WTS_FLAGS,tagSIZE *)
0x18002cd16  mov     ebx, eax
0x18002cd18  lea     rcx, [rbp+pv]
0x18002cd1c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18002cd21  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002cd28  jnz     short loc_18002CD81
0x18002cd2a  mov     eax, ebx
0x18002cd2c  mov     rcx, [rbp+var_10]
0x18002cd30  xor     rcx, rsp; StackCookie
0x18002cd33  call    __security_check_cookie
0x18002cd38  add     rsp, 60h
0x18002cd3c  pop     r15
0x18002cd3e  pop     r14
0x18002cd40  pop     r12
0x18002cd42  pop     rdi
0x18002cd43  pop     rsi
0x18002cd44  pop     rbx
0x18002cd45  pop     rbp
0x18002cd46  retn
0x18002cd47  mov     rcx, [rbp+38h]; this
0x18002cd4b  mov     r9d, ebx; char *
0x18002cd4e  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002cd55  mov     edx, 1151h; void *
0x18002cd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd5f  jmp     short loc_18002CD2A
0x18002cd61  lea     rax, [rbp+var_30]
0x18002cd65  mov     qword ptr [rsp+60h+var_40], rax
0x18002cd6a  mov     r9d, 1
0x18002cd70  lea     rdx, Thumbnails_GetAspectRatio_Start
0x18002cd77  call    McGenEventWrite_EventWriteTransfer
0x18002cd7c  jmp     loc_18002CC91
0x18002cd81  lea     rax, [rbp+var_30]
0x18002cd85  mov     qword ptr [rsp+60h+var_40], rax
0x18002cd8a  mov     r9d, 1
0x18002cd90  lea     rdx, Thumbnails_GetAspectRatio_Stop
0x18002cd97  call    McGenEventWrite_EventWriteTransfer
0x18002cd9c  jmp     short loc_18002CD2A
```
