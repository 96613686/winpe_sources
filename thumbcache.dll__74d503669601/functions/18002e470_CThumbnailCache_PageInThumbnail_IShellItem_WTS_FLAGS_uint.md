# CThumbnailCache::PageInThumbnail(IShellItem *,WTS_FLAGS,uint)

- ea: `0x18002e470`
- end: `0x18002e581`
- name: `?PageInThumbnail@CThumbnailCache@@UEAAJPEAUIShellItem@@W4WTS_FLAGS@@I@Z`
- size: `273`
- prototype: `int(CThumbnailCache *__hidden this, struct IShellItem *, enum WTS_FLAGS, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009ed0`
- `0x18000bfd8`
- `0x18000c6f4`
- `0x18000cb34`
- `0x18001455c`
- `0x18002e470`
- `0x18002e588`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e50e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e50e`

## string_xrefs

- `0x18002e4c4`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThumbnailCache::PageInThumbnail(
        CThumbnailCache *this,
        struct IShellItem *a2,
        enum WTS_FLAGS a3,
        unsigned int a4)
{
  CThumbnailCache *v9; // rdi
  int v10; // eax
  int v11; // ebx
  _QWORD v12[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v13; // [rsp+30h] [rbp-58h] BYREF
  int v14; // [rsp+38h] [rbp-50h]
  int v15; // [rsp+3Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 )
    return 2147500035LL;
  v9 = (CThumbnailCache *)((char *)this - 24);
  v10 = CThumbnailCache::_ValidateCallingThread((CThumbnailCache *)((char *)this - 24));
  v11 = v10;
  if ( v10 >= 0 )
  {
    v11 = CThumbnailCache::_Initialize(v9, a3, a4);
    if ( v11 >= 0 )
    {
      v14 = *((_DWORD *)this + 186) & 1;
      v12[0] = 0;
      v13 = 0;
      CoTaskMemFree(0);
      v15 = 0;
      v12[1] = 0;
      v11 = CThumbnailMoniker::InitializeWithItem((CThumbnailMoniker *)v12, a2);
      if ( v11 >= 0 )
        v11 = CThumbnailCache::_TryPageInThumbail(v9, (struct CThumbnailMoniker *)v12, a3, a4);
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v13);
    }
    if ( v11 == -2147216863 )
      return (unsigned int)-2147418113;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10AC,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v10,
      v12[0]);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002e470  push    rbx
0x18002e472  push    rbp
0x18002e473  push    rsi
0x18002e474  push    rdi
0x18002e475  push    r14
0x18002e477  push    r15
0x18002e479  sub     rsp, 58h
0x18002e47d  mov     rax, cs:__security_cookie
0x18002e484  xor     rax, rsp
0x18002e487  mov     [rsp+88h+var_48], rax
0x18002e48c  mov     r14d, r9d
0x18002e48f  mov     ebp, r8d
0x18002e492  mov     r15, rdx
0x18002e495  mov     rsi, rcx
0x18002e498  test    rdx, rdx
0x18002e49b  jnz     short loc_18002E4A7
0x18002e49d  mov     eax, 80004003h
0x18002e4a2  jmp     loc_18002E567
0x18002e4a7  lea     rdi, [rcx-18h]
0x18002e4ab  mov     rcx, rdi; this
0x18002e4ae  call    ?_ValidateCallingThread@CThumbnailCache@@AEAAJXZ
0x18002e4b3  mov     ebx, eax
0x18002e4b5  test    eax, eax
0x18002e4b7  jns     short loc_18002E4DA
0x18002e4b9  mov     rcx, [rsp+88h]; this
0x18002e4c1  mov     r9d, eax; char *
0x18002e4c4  lea     r8, aOnecoreuapShel_3
0x18002e4cb  mov     edx, 10ACh; void *
0x18002e4d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18002e4d5  jmp     loc_18002E565
0x18002e4da  mov     r8d, r14d; int
0x18002e4dd  mov     edx, ebp; enum WTS_FLAGS
0x18002e4df  mov     rcx, rdi; this
0x18002e4e2  call    ?_Initialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z
0x18002e4e7  mov     ebx, eax
0x18002e4e9  test    eax, eax
0x18002e4eb  js      short loc_18002E557
0x18002e4ed  mov     eax, [rsi+2E8h]
0x18002e4f3  and     eax, 1
0x18002e4f6  mov     [rsp+88h+var_50], eax
0x18002e4fa  mov     [rsp+88h+var_68], 0
0x18002e503  mov     [rsp+88h+var_58], 0
0x18002e50c  xor     ecx, ecx; pv
0x18002e50e  call    cs:__imp_CoTaskMemFree
0x18002e514  mov     [rsp+88h+var_4C], 0
0x18002e51c  mov     [rsp+88h+var_60], 0
0x18002e525  mov     rdx, r15; struct IShellItem *
0x18002e528  lea     rcx, [rsp+88h+var_68]; this
0x18002e52d  call    ?InitializeWithItem@CThumbnailMoniker@@QEAAJPEAUIShellItem@@@Z
0x18002e532  mov     ebx, eax
0x18002e534  test    eax, eax
0x18002e536  js      short loc_18002E54D
0x18002e538  mov     r9d, r14d; unsigned int
0x18002e53b  mov     r8d, ebp; enum WTS_FLAGS
0x18002e53e  lea     rdx, [rsp+88h+var_68]; struct CThumbnailMoniker *
0x18002e543  mov     rcx, rdi; this
0x18002e546  call    ?_TryPageInThumbail@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@W4WTS_FLAGS@@I@Z
0x18002e54b  mov     ebx, eax
0x18002e54d  lea     rcx, [rsp+88h+var_58]
0x18002e552  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ
0x18002e557  mov     eax, 8000FFFFh
0x18002e55c  cmp     ebx, 80041221h
0x18002e562  cmovz   ebx, eax
0x18002e565  mov     eax, ebx
0x18002e567  mov     rcx, [rsp+88h+var_48]
0x18002e56c  xor     rcx, rsp; StackCookie
0x18002e56f  call    __security_check_cookie
0x18002e574  add     rsp, 58h
0x18002e578  pop     r15
0x18002e57a  pop     r14
0x18002e57c  pop     rdi
0x18002e57d  pop     rsi
0x18002e57e  pop     rbp
0x18002e57f  pop     rbx
0x18002e580  retn
```
