# CThumbnailCache::AddImage(WTS_THUMBNAILID,uint,HBITMAP__ *)

- ea: `0x180013870`
- end: `0x180013a5d`
- name: `?AddImage@CThumbnailCache@@UEAAJUWTS_THUMBNAILID@@IPEAUHBITMAP__@@@Z`
- size: `493`
- prototype: `int(CThumbnailCache *__hidden this, struct WTS_THUMBNAILID *__struct_ptr, unsigned int, HBITMAP)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800034f8`
- `0x18000b3c0`
- `0x18000c6f4`
- `0x18000cb34`
- `0x180012128`
- `0x180012e60`
- `0x180013870`
- `0x180013d38`
- `0x18001455c`
- `0x180014888`
- `0x18001f73c`
- `0x18002d4f8`
- `0x180035830`
- `0x18004099c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800138f2`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800138f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013916`
- `GDI32!DeleteObject` at `0x180013a3d`
- `GDI32!DeleteObject` at `0x180013a3d`
- `GDI32!GetObjectW` at `0x180013976`
- `GDI32!GetObjectW` at `0x180013976`
- `USER32!CopyImage` at `0x1800139a4`
- `USER32!CopyImage` at `0x1800139a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThumbnailCache::AddImage(
        CThumbnailCache *this,
        struct WTS_THUMBNAILID *a2,
        unsigned int a3,
        HBITMAP a4)
{
  int Error; // ebx
  char *v9; // rsi
  __int64 v10; // r9
  HBITMAP v11; // rbx
  HGDIOBJ v12; // rdi
  bool v13; // zf
  unsigned int NextThumbSizeFromPixelSize; // eax
  HGDIOBJ ho; // [rsp+30h] [rbp-89h] BYREF
  __int128 pv; // [rsp+38h] [rbp-81h] BYREF
  __int128 v18; // [rsp+48h] [rbp-71h]
  _QWORD v19[2]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v20; // [rsp+68h] [rbp-51h] BYREF
  int v21; // [rsp+70h] [rbp-49h]
  int v22; // [rsp+74h] [rbp-45h]
  _WORD v23[40]; // [rsp+80h] [rbp-39h] BYREF

  Error = _ValidateSize(a3);
  if ( Error >= 0 )
  {
    v9 = (char *)this - 32;
    Error = CThumbnailCache::_ValidateCallingThread((CThumbnailCache *)((char *)this - 32));
    if ( Error >= 0 )
    {
      Error = CThumbnailCache::_Initialize((CThumbnailCache *)((char *)this - 32), WTS_NONE, a3);
      if ( Error >= 0 )
      {
        _o__ui64tow_s(*(_QWORD *)a2->rgbKey, v23, 33, 16);
        v21 = *((_DWORD *)this + 184) & 1;
        v19[0] = 0;
        v20 = 0;
        CoTaskMemFree(0);
        v22 = 0;
        v19[1] = 0;
        Error = CThumbnailMoniker::Initialize((__int64)v19, *(_QWORD *)a2->rgbKey, v23, v10, 2, 19);
        if ( Error < 0 )
        {
LABEL_12:
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v20);
          return (unsigned int)Error;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ho);
        pv = 0;
        v18 = 0;
        if ( !GetObjectW(a4, 32, &pv) )
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
          {
LABEL_11:
            wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(&ho);
            goto LABEL_12;
          }
        }
        if ( *((_QWORD *)&v18 + 1) )
        {
          v11 = (HBITMAP)ho;
          v13 = ho == 0;
        }
        else
        {
          v11 = (HBITMAP)CopyImage(a4, 0, SDWORD1(pv), SDWORD2(pv), 0x2000u);
          v12 = ho;
          if ( ho )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&ho);
            DeleteObject(v12);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&ho);
          }
          ho = v11;
          v13 = v11 == 0;
          if ( !v11 )
          {
            Error = -2147024882;
            goto LABEL_11;
          }
        }
        if ( !v13 )
          a4 = v11;
        NextThumbSizeFromPixelSize = CThumbnailCache::_GetNextThumbSizeFromPixelSize(v9, a3);
        Error = CThumbnailCache::_AddBitmapToCache(v9, v19, NextThumbSizeFromPixelSize, a4);
        goto LABEL_11;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180013870  push    rbp
0x180013872  push    rbx
0x180013873  push    rsi
0x180013874  push    rdi
0x180013875  push    r12
0x180013877  push    r14
0x180013879  push    r15
0x18001387b  lea     rbp, [rsp-27h]
0x180013880  sub     rsp, 0E0h
0x180013887  mov     rax, cs:__security_cookie
0x18001388e  xor     rax, rsp
0x180013891  mov     [rbp+57h+var_40], rax
0x180013895  mov     r14, r9
0x180013898  mov     r15d, r8d
0x18001389b  mov     r12, rdx
0x18001389e  mov     rdi, rcx
0x1800138a1  mov     ecx, r8d; unsigned int
0x1800138a4  call    ?_ValidateSize@@YAJI@Z; _ValidateSize(uint)
0x1800138a9  mov     ebx, eax
0x1800138ab  test    eax, eax
0x1800138ad  js      loc_1800139DA
0x1800138b3  lea     rsi, [rdi-20h]
0x1800138b7  mov     rcx, rsi; this
0x1800138ba  call    ?_ValidateCallingThread@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_ValidateCallingThread(void)
0x1800138bf  mov     ebx, eax
0x1800138c1  test    eax, eax
0x1800138c3  js      loc_1800139DA
0x1800138c9  mov     r8d, r15d; int
0x1800138cc  xor     edx, edx; enum WTS_FLAGS
0x1800138ce  mov     rcx, rsi; this
0x1800138d1  call    ?_Initialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z; CThumbnailCache::_Initialize(WTS_FLAGS,int)
0x1800138d6  mov     ebx, eax
0x1800138d8  test    eax, eax
0x1800138da  js      loc_1800139DA
0x1800138e0  mov     r9d, 10h
0x1800138e6  lea     r8d, [r9+11h]
0x1800138ea  lea     rdx, [rbp+57h+var_90]
0x1800138ee  mov     rcx, [r12]
0x1800138f2  call    cs:__imp__o__ui64tow_s
0x1800138f8  mov     eax, [rdi+2E0h]
0x1800138fe  and     eax, 1
0x180013901  mov     [rbp+57h+var_A0], eax
0x180013904  mov     [rbp+57h+var_B8], 0
0x18001390c  mov     [rbp+57h+var_A8], 0
0x180013914  xor     ecx, ecx; pv
0x180013916  call    cs:__imp_CoTaskMemFree
0x18001391c  mov     [rbp+57h+var_9C], 0
0x180013923  mov     [rbp+57h+var_B0], 0
0x18001392b  mov     [rsp+110h+var_E8], 13h
0x180013933  mov     [rsp+110h+flags], 2
0x18001393b  lea     r8, [rbp+57h+var_90]
0x18001393f  mov     rdx, [r12]
0x180013943  lea     rcx, [rbp+57h+var_B8]
0x180013947  call    ?Initialize@CThumbnailMoniker@@QEAAJ_KPEBGHW4TRIBIT@@K@Z; CThumbnailMoniker::Initialize(unsigned __int64,ushort const *,int,TRIBIT,ulong)
0x18001394c  mov     ebx, eax
0x18001394e  test    eax, eax
0x180013950  js      short loc_1800139D1
0x180013952  lea     rcx, [rsp+110h+ho]
0x180013957  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001395c  nop
0x18001395d  xorps   xmm0, xmm0
0x180013960  movups  [rsp+110h+pv], xmm0
0x180013965  movups  [rbp+57h+var_C8], xmm0
0x180013969  lea     r8, [rsp+110h+pv]; pv
0x18001396e  mov     edx, 20h ; ' '; c
0x180013973  mov     rcx, r14; h
0x180013976  call    cs:__imp_GetObjectW
0x18001397c  test    eax, eax
0x18001397e  jz      loc_180013A1F
0x180013984  cmp     qword ptr [rbp+57h+var_C8+8], 0
0x180013989  jnz     loc_180013A52
0x18001398f  mov     [rsp+110h+flags], 2000h; flags
0x180013997  mov     r9d, dword ptr [rbp+57h+pv+8]; cy
0x18001399b  mov     r8d, dword ptr [rbp+57h+pv+4]; cx
0x18001399f  xor     edx, edx; type
0x1800139a1  mov     rcx, r14; h
0x1800139a4  call    cs:__imp_CopyImage
0x1800139aa  mov     rbx, rax
0x1800139ad  mov     rdi, [rsp+110h+ho]
0x1800139b2  test    rdi, rdi
0x1800139b5  jnz     short loc_180013A30
0x1800139b7  mov     [rsp+110h+ho], rbx
0x1800139bc  test    rbx, rbx
0x1800139bf  jnz     short loc_1800139FA
0x1800139c1  mov     ebx, 8007000Eh
0x1800139c6  lea     rcx, [rsp+110h+ho]
0x1800139cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(void)
0x1800139d0  nop
0x1800139d1  lea     rcx, [rbp+57h+var_A8]
0x1800139d5  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800139da  mov     eax, ebx
0x1800139dc  mov     rcx, [rbp+57h+var_40]
0x1800139e0  xor     rcx, rsp; StackCookie
0x1800139e3  call    __security_check_cookie
0x1800139e8  add     rsp, 0E0h
0x1800139ef  pop     r15
0x1800139f1  pop     r14
0x1800139f3  pop     r12
0x1800139f5  pop     rdi
0x1800139f6  pop     rsi
0x1800139f7  pop     rbx
0x1800139f8  pop     rbp
0x1800139f9  retn
0x1800139fa  cmovnz  r14, rbx
0x1800139fe  mov     edx, r15d
0x180013a01  mov     rcx, rsi
0x180013a04  call    ?_GetNextThumbSizeFromPixelSize@CThumbnailCache@@AEAA?AW4THUMBSIZE@@I@Z; CThumbnailCache::_GetNextThumbSizeFromPixelSize(uint)
0x180013a09  mov     r8d, eax
0x180013a0c  mov     r9, r14
0x180013a0f  lea     rdx, [rbp+57h+var_B8]
0x180013a13  mov     rcx, rsi
0x180013a16  call    ?_AddBitmapToCache@CThumbnailCache@@AEAAJAEBVCThumbnailMoniker@@W4THUMBSIZE@@PEAUHBITMAP__@@@Z; CThumbnailCache::_AddBitmapToCache(CThumbnailMoniker const &,THUMBSIZE,HBITMAP__ *)
0x180013a1b  mov     ebx, eax
0x180013a1d  jmp     short loc_1800139C6
0x180013a1f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180013a24  mov     ebx, eax
0x180013a26  test    eax, eax
0x180013a28  jns     loc_180013984
0x180013a2e  jmp     short loc_1800139C6
0x180013a30  lea     rcx, [rsp+110h+ho]; this
0x180013a35  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013a3a  mov     rcx, rdi; ho
0x180013a3d  call    cs:__imp_DeleteObject
0x180013a43  lea     rcx, [rsp+110h+ho]; this
0x180013a48  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180013a4d  jmp     loc_1800139B7
0x180013a52  mov     rbx, [rsp+110h+ho]
0x180013a57  test    rbx, rbx
0x180013a5a  jmp     short loc_1800139FA
```
