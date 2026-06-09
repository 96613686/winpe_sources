# CThumbnailCache::GetThumbnailDimensionsWithFlags(IShellItem *,uint,WTS_FLAGS,tagSIZE *)

- ea: `0x180014ae0`
- end: `0x180014c44`
- name: `?GetThumbnailDimensionsWithFlags@CThumbnailCache@@UEAAJPEAUIShellItem@@IW4WTS_FLAGS@@PEAUtagSIZE@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, struct IShellItem *, unsigned int, enum WTS_FLAGS, struct tagSIZE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009ed0`
- `0x18000bfd8`
- `0x18000c6f4`
- `0x18000cb34`
- `0x18001455c`
- `0x180014ae0`
- `0x180014c4c`
- `0x180014cd0`
- `0x18002b11c`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b77`

## string_xrefs

- `0x180014bf4`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThumbnailCache::GetThumbnailDimensionsWithFlags(
        CThumbnailCache *this,
        struct IShellItem *a2,
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
  int v16; // [rsp+20h] [rbp-40h]
  _QWORD v17[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  int v19; // [rsp+48h] [rbp-18h]
  int v20; // [rsp+4Ch] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  *a5 = 0;
  v9 = CThumbnailCache::_ValidateCallingThread(this);
  DimensionsFromMoniker = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1130,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v9,
      v16);
  }
  else
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v10, Thumbnails_GetAspectRatio_Start, v11, 1, v17);
    if ( CThumbnailCache::_ShouldConsiderItem(this, a2) )
    {
      DimensionsFromMoniker = CThumbnailCache::_Initialize(this, a4, a3);
      if ( DimensionsFromMoniker >= 0 )
      {
        v19 = *((_DWORD *)this + 192) & 1;
        v17[0] = 0;
        v18 = 0;
        CoTaskMemFree(0);
        v20 = 0;
        v17[1] = 0;
        DimensionsFromMoniker = CThumbnailMoniker::InitializeWithItem((CThumbnailMoniker *)v17, a2);
        if ( DimensionsFromMoniker >= 0 )
          DimensionsFromMoniker = CThumbnailCache::_TryGetDimensionsFromMoniker(
                                    this,
                                    (struct CThumbnailMoniker *)v17,
                                    a3,
                                    a4,
                                    a5);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v18);
      }
    }
    else
    {
      DimensionsFromMoniker = -2147467259;
    }
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v13, Thumbnails_GetAspectRatio_Stop, v14, 1, v17);
  }
  return (unsigned int)DimensionsFromMoniker;
}

```

## disassembly

```asm
0x180014ae0  push    rbp
0x180014ae2  push    rbx
0x180014ae3  push    rsi
0x180014ae4  push    rdi
0x180014ae5  push    r12
0x180014ae7  push    r14
0x180014ae9  push    r15
0x180014aeb  mov     rbp, rsp
0x180014aee  sub     rsp, 60h
0x180014af2  mov     rax, cs:__security_cookie
0x180014af9  xor     rax, rsp
0x180014afc  mov     [rbp+var_10], rax
0x180014b00  mov     r15d, r9d
0x180014b03  mov     r14d, r8d
0x180014b06  mov     rsi, rdx
0x180014b09  mov     rdi, rcx
0x180014b0c  mov     r12, [rbp+arg_20]
0x180014b10  xor     eax, eax
0x180014b12  mov     [r12], rax
0x180014b16  call    ?_ValidateCallingThread@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_ValidateCallingThread(void)
0x180014b1b  mov     ebx, eax
0x180014b1d  test    eax, eax
0x180014b1f  js      loc_180014BED
0x180014b25  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180014b2c  jnz     loc_180014C07
0x180014b32  mov     rdx, rsi; struct IShellItem *
0x180014b35  mov     rcx, rdi; this
0x180014b38  call    ?_ShouldConsiderItem@CThumbnailCache@@AEAA_NPEAUIShellItem@@@Z; CThumbnailCache::_ShouldConsiderItem(IShellItem *)
0x180014b3d  test    al, al
0x180014b3f  jz      loc_180014BE6
0x180014b45  mov     r8d, r14d; int
0x180014b48  mov     edx, r15d; enum WTS_FLAGS
0x180014b4b  mov     rcx, rdi; this
0x180014b4e  call    ?_Initialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z; CThumbnailCache::_Initialize(WTS_FLAGS,int)
0x180014b53  mov     ebx, eax
0x180014b55  test    eax, eax
0x180014b57  js      short loc_180014BC0
0x180014b59  mov     eax, [rdi+300h]
0x180014b5f  and     eax, 1
0x180014b62  mov     [rbp+var_18], eax
0x180014b65  mov     [rbp+var_30], 0
0x180014b6d  mov     [rbp+var_20], 0
0x180014b75  xor     ecx, ecx; pv
0x180014b77  call    cs:__imp_CoTaskMemFree
0x180014b7d  mov     [rbp+var_14], 0
0x180014b84  mov     [rbp+var_28], 0
0x180014b8c  mov     rdx, rsi; struct IShellItem *
0x180014b8f  lea     rcx, [rbp+var_30]; this
0x180014b93  call    ?InitializeWithItem@CThumbnailMoniker@@QEAAJPEAUIShellItem@@@Z; CThumbnailMoniker::InitializeWithItem(IShellItem *)
0x180014b98  mov     ebx, eax
0x180014b9a  test    eax, eax
0x180014b9c  js      short loc_180014BB7
0x180014b9e  mov     qword ptr [rsp+60h+var_40], r12; struct tagSIZE *
0x180014ba3  mov     r9d, r15d; enum WTS_FLAGS
0x180014ba6  mov     r8d, r14d; unsigned int
0x180014ba9  lea     rdx, [rbp+var_30]; struct CThumbnailMoniker *
0x180014bad  mov     rcx, rdi; this
0x180014bb0  call    ?_TryGetDimensionsFromMoniker@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@IW4WTS_FLAGS@@PEAUtagSIZE@@@Z; CThumbnailCache::_TryGetDimensionsFromMoniker(CThumbnailMoniker &,uint,WTS_FLAGS,tagSIZE *)
0x180014bb5  mov     ebx, eax
0x180014bb7  lea     rcx, [rbp+var_20]
0x180014bbb  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180014bc0  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180014bc7  jnz     short loc_180014C27
0x180014bc9  mov     eax, ebx
0x180014bcb  mov     rcx, [rbp+var_10]
0x180014bcf  xor     rcx, rsp; StackCookie
0x180014bd2  call    __security_check_cookie
0x180014bd7  add     rsp, 60h
0x180014bdb  pop     r15
0x180014bdd  pop     r14
0x180014bdf  pop     r12
0x180014be1  pop     rdi
0x180014be2  pop     rsi
0x180014be3  pop     rbx
0x180014be4  pop     rbp
0x180014be5  retn
0x180014be6  mov     ebx, 80004005h
0x180014beb  jmp     short loc_180014BC0
0x180014bed  mov     rcx, [rbp+38h]; this
0x180014bf1  mov     r9d, ebx; char *
0x180014bf4  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180014bfb  mov     edx, 1130h; void *
0x180014c00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c05  jmp     short loc_180014BC9
0x180014c07  lea     rax, [rbp+var_30]
0x180014c0b  mov     qword ptr [rsp+60h+var_40], rax
0x180014c10  mov     r9d, 1
0x180014c16  lea     rdx, Thumbnails_GetAspectRatio_Start
0x180014c1d  call    McGenEventWrite_EventWriteTransfer
0x180014c22  jmp     loc_180014B32
0x180014c27  lea     rax, [rbp+var_30]
0x180014c2b  mov     qword ptr [rsp+60h+var_40], rax
0x180014c30  mov     r9d, 1
0x180014c36  lea     rdx, Thumbnails_GetAspectRatio_Stop
0x180014c3d  call    McGenEventWrite_EventWriteTransfer
0x180014c42  jmp     short loc_180014BC9
```
