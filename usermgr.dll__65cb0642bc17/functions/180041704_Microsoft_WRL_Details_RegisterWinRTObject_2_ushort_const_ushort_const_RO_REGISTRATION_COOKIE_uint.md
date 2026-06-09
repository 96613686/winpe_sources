# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180041704`
- end: `0x180041806`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180072ca0`

## callees

- `0x180041704`
- `0x18006c380`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800417e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800417ed`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800417e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800417ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800417ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800417ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004179b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004179b`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800417b9`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800417b9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  HSTRING *v11; // r14
  int v12; // ebx
  unsigned int v13; // esi
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HRESULT String; // eax
  unsigned int i; // edi

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a2 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= (unsigned int)v5 )
        {
          if ( String < 0 )
            break;
          goto LABEL_13;
        }
      }
    }
    else
    {
LABEL_13:
      v12 = RoRegisterActivationFactories(v11, v8, (unsigned int)v5, a3);
    }
    for ( i = 0; i < v13; ++i )
      WindowsDeleteString(v11[i]);
  }
  else
  {
    v12 = -2147024882;
  }
  operator delete[](v8);
  operator delete[](v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180041704  push    rbx
0x180041706  push    rbp
0x180041707  push    rsi
0x180041708  push    rdi
0x180041709  push    r12
0x18004170b  push    r13
0x18004170d  push    r14
0x18004170f  push    r15
0x180041711  sub     rsp, 28h
0x180041715  mov     r12, rdx
0x180041718  mov     edi, r9d
0x18004171b  mov     esi, 8
0x180041720  mov     rbp, r8
0x180041723  mov     eax, esi
0x180041725  mul     rdi
0x180041728  lea     r14, [rsi-9]
0x18004172c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180041733  cmovb   rax, r14
0x180041737  mov     rcx, rax; unsigned __int64
0x18004173a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004173f  mov     r15, rax
0x180041742  mov     eax, esi
0x180041744  mul     rdi
0x180041747  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004174e  cmovb   rax, r14
0x180041752  mov     rcx, rax; unsigned __int64
0x180041755  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004175a  xor     r13d, r13d
0x18004175d  mov     r14, rax
0x180041760  test    r15, r15
0x180041763  jz      short loc_1800417DC
0x180041765  test    rax, rax
0x180041768  jz      short loc_1800417DC
0x18004176a  mov     ebx, r13d
0x18004176d  mov     esi, r13d
0x180041770  test    edi, edi
0x180041772  jz      short loc_1800417AD
0x180041774  test    ebx, ebx
0x180041776  js      short loc_1800417C1
0x180041778  mov     eax, esi
0x18004177a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180041781  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180041785  mov     [r15+rax*8], rcx
0x180041789  mov     rcx, [r12+rax*8]; sourceString
0x18004178d  inc     rdx; length
0x180041790  cmp     [rcx+rdx*2], r13w
0x180041795  jnz     short loc_18004178D
0x180041797  lea     r8, [r14+rax*8]; string
0x18004179b  call    cs:__imp_WindowsCreateString
0x1800417a1  inc     esi
0x1800417a3  mov     ebx, eax
0x1800417a5  cmp     esi, edi
0x1800417a7  jb      short loc_180041774
0x1800417a9  test    eax, eax
0x1800417ab  js      short loc_1800417C1
0x1800417ad  mov     r9, rbp
0x1800417b0  mov     r8d, edi
0x1800417b3  mov     rdx, r15
0x1800417b6  mov     rcx, r14
0x1800417b9  call    cs:__imp_RoRegisterActivationFactories
0x1800417bf  mov     ebx, eax
0x1800417c1  mov     edi, r13d
0x1800417c4  test    esi, esi
0x1800417c6  jz      short loc_1800417E1
0x1800417c8  mov     ecx, edi
0x1800417ca  mov     rcx, [r14+rcx*8]; string
0x1800417ce  call    cs:__imp_WindowsDeleteString
0x1800417d4  inc     edi
0x1800417d6  cmp     edi, esi
0x1800417d8  jb      short loc_1800417C8
0x1800417da  jmp     short loc_1800417E1
0x1800417dc  mov     ebx, 8007000Eh
0x1800417e1  mov     rcx, r15
0x1800417e4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800417ea  mov     rcx, r14
0x1800417ed  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800417f3  mov     eax, ebx
0x1800417f5  add     rsp, 28h
0x1800417f9  pop     r15
0x1800417fb  pop     r14
0x1800417fd  pop     r13
0x1800417ff  pop     r12
0x180041801  pop     rdi
0x180041802  pop     rsi
0x180041803  pop     rbp
0x180041804  pop     rbx
0x180041805  retn
```
