# CThumbnailCache::_GetThumbnailByID(WTS_THUMBNAILID,uint,WTS_FLAGS,IBitmapResult * *,WTS_CACHEFLAGS *)

- ea: `0x180014fd0`
- end: `0x1800152a9`
- name: `?_GetThumbnailByID@CThumbnailCache@@AEAAJUWTS_THUMBNAILID@@IW4WTS_FLAGS@@PEAPEAUIBitmapResult@@PEAW4WTS_CACHEFLAGS@@@Z`
- size: `729`
- prototype: `__int64 __usercall@<rax>(CThumbnailCache *__hidden this@<rcx>, struct WTS_THUMBNAILID *__struct_ptr@<rdx>, unsigned int@<r8d>, enum WTS_FLAGS@<r9d>, struct IBitmapResult **, enum WTS_CACHEFLAGS *)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014eb0`
- `0x18002cac0`

## callees

- `0x180003624`
- `0x180006c94`
- `0x18000bfd8`
- `0x18000c6f4`
- `0x18000cb34`
- `0x180013d80`
- `0x18001455c`
- `0x180014fd0`
- `0x1800152b0`
- `0x18002b024`
- `0x18002b07c`
- `0x18002e860`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001517e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001517e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001507a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001508f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001509d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001507a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001508f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001509d`
- `OLEAUT32!__imp_SysFreeString` at `0x180015188`
- `OLEAUT32!__imp_SysFreeString` at `0x180015188`

## string_xrefs

- `0x180015234`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThumbnailCache::_GetThumbnailByID(
        CThumbnailCache *this,
        struct WTS_THUMBNAILID *a2,
        unsigned int a3,
        enum WTS_FLAGS a4,
        struct IBitmapResult **a5,
        enum WTS_CACHEFLAGS *a6)
{
  unsigned int v9; // r15d
  int v10; // eax
  int ThumbnailFromCache; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  CThumbnailCache *v15; // rcx
  struct IBitmapResult *v16; // rcx
  __int64 v17; // rcx
  int v19; // [rsp+20h] [rbp-79h]
  int v20; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v21; // [rsp+54h] [rbp-45h]
  HANDLE hObject[2]; // [rsp+58h] [rbp-41h] BYREF
  int v23; // [rsp+68h] [rbp-31h]
  unsigned int v24; // [rsp+70h] [rbp-29h] BYREF
  struct IBitmapResult *v25; // [rsp+78h] [rbp-21h] BYREF
  __int64 v26; // [rsp+80h] [rbp-19h] BYREF
  __int64 v27; // [rsp+88h] [rbp-11h]
  LPVOID pv; // [rsp+90h] [rbp-9h] BYREF
  int v29; // [rsp+98h] [rbp-1h]
  int v30; // [rsp+9Ch] [rbp+3h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v21 = a3;
  v9 = a3;
  v24 = a3;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = WTS_DEFAULT;
  v10 = CThumbnailCache::_ValidateCallingThread(this);
  ThumbnailFromCache = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5A,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v10,
      v19);
    return (unsigned int)ThumbnailFromCache;
  }
  ThumbnailFromCache = CThumbnailCache::_Initialize(this, a4, v9);
  if ( ThumbnailFromCache >= 0 )
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v13, v12, &qword_1800509F8, v9);
    v29 = *((_DWORD *)this + 192) & 1;
    v26 = 0;
    CoTaskMemFree(0);
    v27 = 0;
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    pv = 0;
    v30 = 0;
    v26 = *(_QWORD *)a2->rgbKey;
    v27 = 0x1100000000LL;
    if ( (a4 & 0x10000200) != 0 )
    {
      ThumbnailFromCache = CThumbnailCache::_TryAdjustCropSquareRequestSize(
                             this,
                             (struct CThumbnailMoniker *)&v26,
                             a4,
                             &v24);
      if ( ThumbnailFromCache < 0 )
      {
LABEL_20:
        CThumbnailCache::_ResetCacheFilesIfFailedCritically(this, ThumbnailFromCache);
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v17, Thumbnails_GetThumbnail_Stop, (unsigned int)ThumbnailFromCache);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pv);
        goto LABEL_23;
      }
      v9 = v24;
    }
    *(_OWORD *)hObject = 0;
    v23 = 0;
    v24 = 0;
    v20 = 0;
    v14 = 2 * ((*((_DWORD *)this + 192) & 1) == 0);
    if ( (a4 & 0x4000) != 0 )
      v14 |= 4u;
    if ( a4 < WTS_NONE )
      v14 |= 0x20u;
    v25 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    ThumbnailFromCache = CThumbnailCache::_TryGetThumbnailFromCache(
                           this,
                           &v26,
                           v9,
                           v14,
                           hObject,
                           &v24,
                           &v20,
                           &GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f,
                           &v25);
    if ( ThumbnailFromCache >= 0 )
    {
      if ( !a5
        || (ThumbnailFromCache = CThumbnailCache::_PostProcessThumbnail(v15, a4, v21, v25, a5), ThumbnailFromCache >= 0) )
      {
        if ( a6 )
        {
          *a6 = WTS_CACHED;
          if ( v24 )
            *a6 = WTS_CACHED|WTS_LOWQUALITY;
        }
      }
    }
    v16 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    if ( hObject[1] )
      CloseHandle(hObject[1]);
    SysFreeString((BSTR)hObject[0]);
    goto LABEL_20;
  }
LABEL_23:
  if ( ThumbnailFromCache == -2147216863 )
    return (unsigned int)-2147418113;
  return (unsigned int)ThumbnailFromCache;
}

```

## disassembly

```asm
0x180014fd0  mov     [rsp-8+arg_8], rbx
0x180014fd5  push    rbp
0x180014fd6  push    rsi
0x180014fd7  push    rdi
0x180014fd8  push    r12
0x180014fda  push    r13
0x180014fdc  push    r14
0x180014fde  push    r15
0x180014fe0  lea     rbp, [rsp-17h]
0x180014fe5  sub     rsp, 0B0h
0x180014fec  mov     rax, cs:__security_cookie
0x180014ff3  xor     rax, rsp
0x180014ff6  mov     [rbp+47h+var_40], rax
0x180014ffa  mov     r14d, r9d
0x180014ffd  mov     [rbp+47h+var_8C], r8d
0x180015001  mov     r13, rdx
0x180015004  mov     rsi, rcx
0x180015007  mov     r15d, r8d
0x18001500a  mov     [rbp+47h+var_70], r8d
0x18001500e  mov     r12, [rbp+47h+arg_20]
0x180015012  mov     rdi, [rbp+47h+arg_28]
0x180015016  test    r12, r12
0x180015019  jz      short loc_180015023
0x18001501b  mov     qword ptr [r12], 0
0x180015023  test    rdi, rdi
0x180015026  jz      short loc_18001502E
0x180015028  mov     dword ptr [rdi], 0
0x18001502e  call    ?_ValidateCallingThread@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_ValidateCallingThread(void)
0x180015033  mov     ebx, eax
0x180015035  test    eax, eax
0x180015037  js      loc_18001522D
0x18001503d  mov     r8d, r15d; int
0x180015040  mov     edx, r14d; enum WTS_FLAGS
0x180015043  mov     rcx, rsi; this
0x180015046  call    ?_Initialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z; CThumbnailCache::_Initialize(WTS_FLAGS,int)
0x18001504b  mov     ebx, eax
0x18001504d  test    eax, eax
0x18001504f  js      loc_1800151AE
0x180015055  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18001505c  jnz     loc_18001524A
0x180015062  mov     eax, [rsi+300h]
0x180015068  and     eax, 1
0x18001506b  mov     [rbp+47h+var_48], eax
0x18001506e  xor     ebx, ebx
0x180015070  mov     [rbp+47h+var_60], rbx
0x180015074  mov     [rbp+47h+pv], rbx
0x180015078  xor     ecx, ecx; pv
0x18001507a  call    cs:__imp_CoTaskMemFree
0x180015080  mov     [rbp+47h+var_44], ebx
0x180015083  mov     [rbp+47h+var_58], rbx
0x180015087  mov     rcx, [rbp+47h+pv]; pv
0x18001508b  mov     [rbp+47h+pv], rbx
0x18001508f  call    cs:__imp_CoTaskMemFree
0x180015095  mov     rcx, [rbp+47h+pv]; pv
0x180015099  mov     [rbp+47h+pv], rbx
0x18001509d  call    cs:__imp_CoTaskMemFree
0x1800150a3  mov     [rbp+47h+pv], rbx
0x1800150a7  mov     [rbp+47h+var_44], ebx
0x1800150aa  mov     rax, [r13+0]
0x1800150ae  mov     [rbp+47h+var_60], rax
0x1800150b2  xor     r13d, r13d
0x1800150b5  mov     dword ptr [rbp+47h+var_58], r13d
0x1800150b9  mov     dword ptr [rbp+47h+var_58+4], 11h
0x1800150c0  test    r14d, 10000200h
0x1800150c7  jnz     loc_18001525E
0x1800150cd  xorps   xmm0, xmm0
0x1800150d0  movdqu  xmmword ptr [rbp+47h+hObject], xmm0
0x1800150d5  mov     [rbp+47h+var_78], r13d
0x1800150d9  mov     [rbp+47h+var_70], r13d
0x1800150dd  mov     [rbp+47h+var_90], r13d
0x1800150e1  mov     ebx, [rsi+300h]
0x1800150e7  not     ebx
0x1800150e9  and     ebx, 1
0x1800150ec  add     ebx, ebx
0x1800150ee  bt      r14d, 0Eh
0x1800150f3  jb      loc_180015284
0x1800150f9  test    r14d, r14d
0x1800150fc  js      loc_18001528C
0x180015102  mov     [rbp+47h+var_68], r13
0x180015106  lea     rcx, [rbp+47h+var_68]
0x18001510a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001510f  lea     rax, [rbp+47h+var_68]
0x180015113  mov     [rsp+0E0h+var_A0], rax
0x180015118  lea     rax, _GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f
0x18001511f  mov     [rsp+0E0h+var_A8], rax
0x180015124  lea     rax, [rbp+47h+var_90]
0x180015128  mov     [rsp+0E0h+var_B0], rax
0x18001512d  lea     rax, [rbp+47h+var_70]
0x180015131  mov     [rsp+0E0h+var_B8], rax
0x180015136  lea     rax, [rbp+47h+hObject]
0x18001513a  mov     [rsp+0E0h+var_C0], rax
0x18001513f  mov     r9d, ebx
0x180015142  mov     r8d, r15d
0x180015145  lea     rdx, [rbp+47h+var_60]
0x180015149  mov     rcx, rsi
0x18001514c  call    ?_TryGetThumbnailFromCache@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@IW4GFC_FLAGS@@PEAVCGlobalRefCount@@PEAHPEAW4WTS_ALPHATYPE@@AEBU_GUID@@PEAPEAX@Z; CThumbnailCache::_TryGetThumbnailFromCache(CThumbnailMoniker &,uint,GFC_FLAGS,CGlobalRefCount *,int *,WTS_ALPHATYPE *,_GUID const &,void * *)
0x180015151  mov     ebx, eax
0x180015153  test    eax, eax
0x180015155  jns     loc_1800151E5
0x18001515b  mov     rcx, [rbp+47h+var_68]
0x18001515f  test    rcx, rcx
0x180015162  jz      short loc_180015175
0x180015164  mov     [rbp+47h+var_68], r13
0x180015168  mov     rax, [rcx]
0x18001516b  mov     rax, [rax+10h]
0x18001516f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015174  nop
0x180015175  mov     rcx, [rbp+47h+hObject+8]; hObject
0x180015179  test    rcx, rcx
0x18001517c  jz      short loc_180015184
0x18001517e  call    cs:__imp_CloseHandle
0x180015184  mov     rcx, [rbp+47h+hObject]; bstrString
0x180015188  call    cs:__imp_SysFreeString
0x18001518e  mov     edx, ebx; int
0x180015190  mov     rcx, rsi; this
0x180015193  call    ?_ResetCacheFilesIfFailedCritically@CThumbnailCache@@AEAAXJ@Z; CThumbnailCache::_ResetCacheFilesIfFailedCritically(long)
0x180015198  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18001519f  jnz     loc_180015294
0x1800151a5  lea     rcx, [rbp+47h+pv]
0x1800151a9  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800151ae  mov     eax, 8000FFFFh
0x1800151b3  cmp     ebx, 80041221h
0x1800151b9  cmovz   ebx, eax
0x1800151bc  mov     eax, ebx
0x1800151be  mov     rcx, [rbp+47h+var_40]
0x1800151c2  xor     rcx, rsp; StackCookie
0x1800151c5  call    __security_check_cookie
0x1800151ca  mov     rbx, [rsp+0E0h+arg_8]
0x1800151d2  add     rsp, 0B0h
0x1800151d9  pop     r15
0x1800151db  pop     r14
0x1800151dd  pop     r13
0x1800151df  pop     r12
0x1800151e1  pop     rdi
0x1800151e2  pop     rsi
0x1800151e3  pop     rbp
0x1800151e4  retn
0x1800151e5  test    r12, r12
0x1800151e8  jz      short loc_180015209
0x1800151ea  mov     [rsp+0E0h+var_C0], r12; struct IBitmapResult **
0x1800151ef  mov     r9, [rbp+47h+var_68]; struct IBitmapResult *
0x1800151f3  mov     r8d, [rbp+47h+var_8C]; unsigned int
0x1800151f7  mov     edx, r14d; enum WTS_FLAGS
0x1800151fa  call    ?_PostProcessThumbnail@CThumbnailCache@@AEAAJW4WTS_FLAGS@@IPEAUIBitmapResult@@PEAPEAU3@@Z; CThumbnailCache::_PostProcessThumbnail(WTS_FLAGS,uint,IBitmapResult *,IBitmapResult * *)
0x1800151ff  mov     ebx, eax
0x180015201  test    eax, eax
0x180015203  js      loc_18001515B
0x180015209  test    rdi, rdi
0x18001520c  jz      loc_18001515B
0x180015212  mov     dword ptr [rdi], 2
0x180015218  cmp     [rbp+47h+var_70], r13d
0x18001521c  jz      loc_18001515B
0x180015222  mov     dword ptr [rdi], 3
0x180015228  jmp     loc_18001515B
0x18001522d  mov     rcx, [rbp+4Fh]; this
0x180015231  mov     r9d, ebx; char *
0x180015234  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001523b  mov     edx, 0C5Ah; void *
0x180015240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015245  jmp     loc_1800151BC
0x18001524a  mov     r9d, r15d
0x18001524d  lea     r8, qword_1800509F8
0x180015254  call    McTemplateU0zq_EventWriteTransfer
0x180015259  jmp     loc_180015062
0x18001525e  lea     r9, [rbp+47h+var_70]; unsigned int *
0x180015262  mov     r8d, r14d; enum WTS_FLAGS
0x180015265  lea     rdx, [rbp+47h+var_60]; struct CThumbnailMoniker *
0x180015269  mov     rcx, rsi; this
0x18001526c  call    ?_TryAdjustCropSquareRequestSize@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@W4WTS_FLAGS@@PEAI@Z; CThumbnailCache::_TryAdjustCropSquareRequestSize(CThumbnailMoniker &,WTS_FLAGS,uint *)
0x180015271  mov     ebx, eax
0x180015273  test    eax, eax
0x180015275  js      loc_18001518E
0x18001527b  mov     r15d, [rbp+47h+var_70]
0x18001527f  jmp     loc_1800150CD
0x180015284  or      ebx, 4
0x180015287  jmp     loc_1800150F9
0x18001528c  or      ebx, 20h
0x18001528f  jmp     loc_180015102
0x180015294  mov     r8d, ebx
0x180015297  lea     rdx, Thumbnails_GetThumbnail_Stop
0x18001529e  call    McTemplateU0q_EventWriteTransfer
0x1800152a3  jmp     loc_1800151A5
```
