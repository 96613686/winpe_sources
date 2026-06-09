# CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)

- ea: `0x180003670`
- end: `0x1800037d3`
- name: `?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z`
- size: `355`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005800`
- `0x180005950`
- `0x180005c10`
- `0x180005d60`
- `0x180006bf0`

## callees

- `0x180001dc0`
- `0x180003670`
- `0x1800158f9`
- `0x180016010`

## pseudocode

```c
void __fastcall CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(__int64 a1, __int64 a2)
{
  void (__fastcall *v3)(__int64, GUID *); // rax
  const GUID *v4; // r8
  GUID v5; // [rsp+20h] [rbp-38h] BYREF
  GUID Buf2; // [rsp+30h] [rbp-28h] BYREF

  if ( a2 )
  {
    v3 = *(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)a2 + 264LL);
    Buf2 = GUID_00000000_0000_0000_0000_000000000000;
    v5 = GUID_00000000_0000_0000_0000_000000000000;
    v3(a2, &Buf2);
    if ( !memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) )
    {
      (*(void (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)a2 + 80LL))(a2, &MF_MT_SUBTYPE, &v5);
      if ( !memcmp_0(&MEDIASUBTYPE_ARGB32, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_ARGB32;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB24, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB24;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB32, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB32;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB555, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB555;
      }
      else
      {
        if ( memcmp_0(&MEDIASUBTYPE_RGB565, &v5, 0x10u) )
          return;
        v4 = &MFVideoFormat_RGB565;
      }
      (*(void (__fastcall **)(__int64, const GUID *, const GUID *))(*(_QWORD *)a2 + 192LL))(a2, &MF_MT_SUBTYPE, v4);
    }
  }
}

```

## disassembly

```asm
0x180003670  test    rdx, rdx
0x180003673  jz      locret_1800037D2
0x180003679  push    rbx
0x18000367a  sub     rsp, 50h
0x18000367e  mov     rax, cs:__security_cookie
0x180003685  xor     rax, rsp
0x180003688  mov     [rsp+58h+var_18], rax
0x18000368d  mov     rax, [rdx]
0x180003690  mov     rbx, rdx
0x180003693  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000369a  lea     rdx, [rsp+58h+Buf2]
0x18000369f  mov     rcx, rbx
0x1800036a2  mov     rax, [rax+108h]
0x1800036a9  movups  [rsp+58h+Buf2], xmm0
0x1800036ae  movups  [rsp+58h+var_38], xmm0
0x1800036b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b8  mov     r8d, 10h; Size
0x1800036be  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800036c3  lea     rcx, MEDIATYPE_Video; Buf1
0x1800036ca  call    memcmp_0
0x1800036cf  test    eax, eax
0x1800036d1  jnz     loc_1800037C0
0x1800036d7  mov     rax, [rbx]
0x1800036da  lea     r8, [rsp+58h+var_38]
0x1800036df  lea     rdx, MF_MT_SUBTYPE
0x1800036e6  mov     rcx, rbx
0x1800036e9  mov     rax, [rax+50h]
0x1800036ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f2  mov     r8d, 10h; Size
0x1800036f8  lea     rdx, [rsp+58h+var_38]; Buf2
0x1800036fd  lea     rcx, MEDIASUBTYPE_ARGB32; Buf1
0x180003704  call    memcmp_0
0x180003709  test    eax, eax
0x18000370b  jnz     short loc_180003719
0x18000370d  lea     r8, MFVideoFormat_ARGB32
0x180003714  jmp     loc_1800037A7
0x180003719  mov     r8d, 10h; Size
0x18000371f  lea     rdx, [rsp+58h+var_38]; Buf2
0x180003724  lea     rcx, MEDIASUBTYPE_RGB24; Buf1
0x18000372b  call    memcmp_0
0x180003730  test    eax, eax
0x180003732  jnz     short loc_18000373D
0x180003734  lea     r8, MFVideoFormat_RGB24
0x18000373b  jmp     short loc_1800037A7
0x18000373d  mov     r8d, 10h; Size
0x180003743  lea     rdx, [rsp+58h+var_38]; Buf2
0x180003748  lea     rcx, MEDIASUBTYPE_RGB32; Buf1
0x18000374f  call    memcmp_0
0x180003754  test    eax, eax
0x180003756  jnz     short loc_180003761
0x180003758  lea     r8, MFVideoFormat_RGB32
0x18000375f  jmp     short loc_1800037A7
0x180003761  mov     r8d, 10h; Size
0x180003767  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000376c  lea     rcx, MEDIASUBTYPE_RGB555; Buf1
0x180003773  call    memcmp_0
0x180003778  test    eax, eax
0x18000377a  jnz     short loc_180003785
0x18000377c  lea     r8, MFVideoFormat_RGB555
0x180003783  jmp     short loc_1800037A7
0x180003785  mov     r8d, 10h; Size
0x18000378b  lea     rdx, [rsp+58h+var_38]; Buf2
0x180003790  lea     rcx, MEDIASUBTYPE_RGB565; Buf1
0x180003797  call    memcmp_0
0x18000379c  test    eax, eax
0x18000379e  jnz     short loc_1800037C0
0x1800037a0  lea     r8, MFVideoFormat_RGB565
0x1800037a7  mov     rax, [rbx]
0x1800037aa  lea     rdx, MF_MT_SUBTYPE
0x1800037b1  mov     rcx, rbx
0x1800037b4  mov     rax, [rax+0C0h]
0x1800037bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c0  mov     rcx, [rsp+58h+var_18]
0x1800037c5  xor     rcx, rsp; StackCookie
0x1800037c8  call    __security_check_cookie
0x1800037cd  add     rsp, 50h
0x1800037d1  pop     rbx
0x1800037d2  retn
```
