# _lambda_b47dd024c43b8dbdfe446eeb01170236_::operator()

- ea: `0x180011ddc`
- end: `0x180012018`
- name: `_lambda_b47dd024c43b8dbdfe446eeb01170236_::operator()`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180010b20`

## callees

- `0x1800038e0`
- `0x180011ddc`
- `0x180012020`
- `0x18001205c`
- `0x1800c7366`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001200c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001200c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011ee2`

## string_xrefs

- `0x180011edb`: `Windows.UI.Core.ComponentDisplayInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall lambda_b47dd024c43b8dbdfe446eeb01170236_::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  __int128 v4; // xmm7
  __int128 v5; // xmm8
  __int128 v6; // xmm9
  __int128 v7; // xmm10
  __m128d v8; // xmm6
  __int128 v9; // xmm11
  int v10; // eax
  __int64 v11; // rsi
  int (__fastcall *v12)(__int64, __int128 *, _QWORD, _QWORD, _DWORD, HSTRING_HEADER *, __int64); // rdi
  __int64 v13; // rbx
  BOOL v14; // ebx
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+68h] [rbp-A0h]
  __int128 v21; // [rsp+78h] [rbp-90h]
  __int128 v22; // [rsp+88h] [rbp-80h]
  __m128d v23; // [rsp+98h] [rbp-70h]
  _BYTE v24[20]; // [rsp+A8h] [rbp-60h]
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-40h] BYREF

  memset_0(&v19, 0, 0x64u);
  Windows::UI::Core::WindowServer::LegacyTransforms_CreateComponentDisplayInformationInternalStruct(
    (Windows::UI::Core::WindowServer *)a3,
    (struct Windows::UI::Core::ComponentDisplayInformationInternal *)&v19);
  v4 = v19;
  *(_OWORD *)(a3 + 2776) = v19;
  v5 = v20;
  *(_OWORD *)(a3 + 2792) = v20;
  v6 = v21;
  *(_OWORD *)(a3 + 2808) = v21;
  v7 = v22;
  *(_OWORD *)(a3 + 2824) = v22;
  v8 = v23;
  *(__m128d *)(a3 + 2840) = v23;
  v9 = *(_OWORD *)v24;
  *(_OWORD *)(a3 + 2856) = *(_OWORD *)v24;
  v10 = *(_DWORD *)&v24[16];
  *(_DWORD *)(a3 + 2872) = *(_DWORD *)&v24[16];
  *(_OWORD *)(a3 + 2876) = v4;
  *(_OWORD *)(a3 + 2892) = v5;
  *(_OWORD *)(a3 + 2908) = v6;
  *(_OWORD *)(a3 + 2924) = v7;
  *(__m128d *)(a3 + 2940) = v8;
  *(_OWORD *)(a3 + 2956) = v9;
  *(_DWORD *)(a3 + 2972) = v10;
  v18 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.UI.Core.ComponentDisplayInformation",
         0x2Bu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::IComponentDisplayInformationFactory>>(
              hstringHeader.Reserved.Reserved1,
              &v18) < 0 )
  {
    v17 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return 0;
  }
  else
  {
    v11 = v18;
    v12 = *(int (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD, _DWORD, HSTRING_HEADER *, __int64))(*(_QWORD *)v18 + 48LL);
    v13 = a3 + 2768;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v13);
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&v24[4];
    v19 = v4;
    v20 = v5;
    v21 = v6;
    v22 = v7;
    v14 = v12(v11, &v19, *(_QWORD *)&v8.m128d_f64[0], *(_OWORD *)&_mm_unpackhi_pd(v8, v8), v9, &hstringHeader, v13) >= 0;
    v15 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x180011ddc  mov     rax, rsp
0x180011ddf  push    rbp
0x180011de0  push    rbx
0x180011de1  push    rsi
0x180011de2  push    rdi
0x180011de3  lea     rbp, [rax-78h]
0x180011de7  sub     rsp, 158h
0x180011dee  movaps  xmmword ptr [rax-38h], xmm6
0x180011df2  movaps  xmmword ptr [rax-48h], xmm7
0x180011df6  movaps  xmmword ptr [rax-58h], xmm8
0x180011dfb  movaps  xmmword ptr [rax-68h], xmm9
0x180011e00  movaps  xmmword ptr [rax-78h], xmm10
0x180011e05  movaps  xmmword ptr [rax-88h], xmm11
0x180011e0d  mov     rax, cs:__security_cookie
0x180011e14  xor     rax, rsp
0x180011e17  mov     [rbp+70h+var_90], rax
0x180011e1b  mov     rbx, r8
0x180011e1e  xor     edx, edx; Val
0x180011e20  lea     r8d, [rdx+64h]; Size
0x180011e24  lea     rcx, [rsp+170h+var_128+8]; void *
0x180011e29  call    memset_0
0x180011e2e  lea     rdx, [rsp+170h+var_128+8]; struct Windows::UI::Core::ComponentDisplayInformationInternal *
0x180011e33  mov     rcx, rbx; this
0x180011e36  call    ?LegacyTransforms_CreateComponentDisplayInformationInternalStruct@WindowServer@Core@UI@Windows@@AEAAXPEAUComponentDisplayInformationInternal@234@@Z; Windows::UI::Core::WindowServer::LegacyTransforms_CreateComponentDisplayInformationInternalStruct(Windows::UI::Core::ComponentDisplayInformationInternal *)
0x180011e3b  movaps  xmm7, [rsp+170h+var_128+8]
0x180011e40  movups  xmmword ptr [rbx+0AD8h], xmm7
0x180011e47  movaps  xmm8, [rsp+170h+var_118+8]
0x180011e4d  movups  xmmword ptr [rbx+0AE8h], xmm8
0x180011e55  movaps  xmm9, xmmword ptr [rsp+170h+var_108+8]
0x180011e5b  movups  xmmword ptr [rbx+0AF8h], xmm9
0x180011e63  movaps  xmm10, [rbp+70h+var_F0]
0x180011e68  movups  xmmword ptr [rbx+0B08h], xmm10
0x180011e70  movaps  xmm6, [rbp+70h+var_E0]
0x180011e74  movups  xmmword ptr [rbx+0B18h], xmm6
0x180011e7b  movaps  xmm11, [rbp+70h+var_D0]
0x180011e80  movups  xmmword ptr [rbx+0B28h], xmm11
0x180011e88  mov     eax, [rbp+70h+var_C0]
0x180011e8b  mov     [rbx+0B38h], eax
0x180011e91  movups  xmmword ptr [rbx+0B3Ch], xmm7
0x180011e98  movups  xmmword ptr [rbx+0B4Ch], xmm8
0x180011ea0  movups  xmmword ptr [rbx+0B5Ch], xmm9
0x180011ea8  movups  xmmword ptr [rbx+0B6Ch], xmm10
0x180011eb0  movups  xmmword ptr [rbx+0B7Ch], xmm6
0x180011eb7  movups  xmmword ptr [rbx+0B8Ch], xmm11
0x180011ebf  mov     [rbx+0B9Ch], eax
0x180011ec5  mov     [rsp+170h+var_130], 0
0x180011ece  lea     r9, [rbp+70h+hstringHeader]; string
0x180011ed2  lea     r8, [rbp+70h+hstringHeader.Reserved+8]; hstringHeader
0x180011ed6  mov     edx, 2Bh ; '+'; length
0x180011edb  lea     rcx, ?RuntimeClass_Windows_UI_Core_ComponentDisplayInformation@@3QBGB; "Windows.UI.Core.ComponentDisplayInforma"...
0x180011ee2  call    cs:__imp_WindowsCreateStringReference
0x180011ee8  test    eax, eax
0x180011eea  js      loc_180011FFD
0x180011ef0  lea     rdx, [rsp+170h+var_130]
0x180011ef5  mov     rcx, qword ptr [rbp+70h+hstringHeader.Reserved]
0x180011ef9  call    ??$GetActivationFactory@V?$ComPtr@UIComponentDisplayInformationFactory@Core@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIComponentDisplayInformationFactory@Core@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::IComponentDisplayInformationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IComponentDisplayInformationFactory>>)
0x180011efe  test    eax, eax
0x180011f00  js      loc_180011FD9
0x180011f06  mov     rsi, [rsp+170h+var_130]
0x180011f0b  mov     rax, [rsi]
0x180011f0e  mov     rdi, [rax+30h]
0x180011f12  add     rbx, 0AD0h
0x180011f19  mov     rcx, rbx
0x180011f1c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180011f21  movups  xmm0, [rbp+70h+var_D0+4]
0x180011f25  movdqa  xmmword ptr [rbp+70h+hstringHeader.Reserved], xmm0
0x180011f2a  movaps  [rsp+170h+var_128+8], xmm7
0x180011f2f  movaps  [rsp+170h+var_118+8], xmm8
0x180011f35  movaps  xmmword ptr [rsp+170h+var_108+8], xmm9
0x180011f3b  movaps  [rbp+70h+var_F0], xmm10
0x180011f40  mov     [rsp+170h+var_140], rbx
0x180011f45  lea     rax, [rbp+70h+hstringHeader]
0x180011f49  mov     [rsp+170h+var_148], rax
0x180011f4e  movss   dword ptr [rsp+170h+var_150], xmm11
0x180011f55  movaps  xmm0, xmm6
0x180011f58  unpckhpd xmm0, xmm6
0x180011f5c  movq    r9, xmm0
0x180011f61  movq    r8, xmm6
0x180011f66  lea     rdx, [rsp+170h+var_128+8]
0x180011f6b  mov     rcx, rsi
0x180011f6e  mov     rax, rdi
0x180011f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f76  mov     ebx, eax
0x180011f78  not     ebx
0x180011f7a  shr     ebx, 1Fh
0x180011f7d  mov     rcx, [rsp+170h+var_130]
0x180011f82  test    rcx, rcx
0x180011f85  jz      short loc_180011F9D
0x180011f87  mov     [rsp+170h+var_130], 0
0x180011f90  mov     rdx, [rcx]
0x180011f93  mov     rax, [rdx+10h]
0x180011f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f9c  nop
0x180011f9d  mov     eax, ebx
0x180011f9f  mov     rcx, [rbp+70h+var_90]
0x180011fa3  xor     rcx, rsp; StackCookie
0x180011fa6  call    __security_check_cookie
0x180011fab  lea     r11, [rsp+170h+var_18]
0x180011fb3  movaps  xmm6, xmmword ptr [r11-18h]
0x180011fb8  movaps  xmm7, xmmword ptr [r11-28h]
0x180011fbd  movaps  xmm8, xmmword ptr [r11-38h]
0x180011fc2  movaps  xmm9, xmmword ptr [r11-48h]
0x180011fc7  movaps  xmm10, xmmword ptr [r11-58h]
0x180011fcc  movaps  xmm11, xmmword ptr [r11-68h]
0x180011fd1  mov     rsp, r11
0x180011fd4  pop     rdi
0x180011fd5  pop     rsi
0x180011fd6  pop     rbx
0x180011fd7  pop     rbp
0x180011fd8  retn
0x180011fd9  mov     rcx, [rsp+170h+var_130]
0x180011fde  test    rcx, rcx
0x180011fe1  jz      short loc_180011FF9
0x180011fe3  mov     [rsp+170h+var_130], 0
0x180011fec  mov     rax, [rcx]
0x180011fef  mov     rax, [rax+10h]
0x180011ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff8  nop
0x180011ff9  xor     eax, eax
0x180011ffb  jmp     short loc_180011F9F
0x180011ffd  xor     r9d, r9d; lpArguments
0x180012000  xor     r8d, r8d; nNumberOfArguments
0x180012003  lea     edx, [r9+1]; dwExceptionFlags
0x180012007  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001200c  call    cs:__imp_RaiseException
0x180012012  jmp     loc_180011EF0
```
