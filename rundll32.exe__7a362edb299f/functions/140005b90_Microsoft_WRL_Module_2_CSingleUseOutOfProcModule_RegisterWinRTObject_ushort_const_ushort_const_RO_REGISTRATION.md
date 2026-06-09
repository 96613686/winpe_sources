# Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::RegisterWinRTObject(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x140005b90`
- end: `0x140005c94`
- name: `?RegisterWinRTObject@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001260`
- `0x140001858`
- `0x140005b90`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140005c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140005c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005c5e`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140005c49`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140005c49`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::RegisterWinRTObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned __int64 v6; // rax
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

  v6 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v6 = -1;
  v8 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( a5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a3 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= a5 )
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
      v12 = RoRegisterActivationFactories(v11, v8, a5, a4);
    }
    for ( i = 0; i < v13; ++i )
      WindowsDeleteString(v11[i]);
  }
  else
  {
    v12 = -2147024882;
  }
  operator delete(v8);
  operator delete(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140005b90  push    rbx
0x140005b92  push    rbp
0x140005b93  push    rsi
0x140005b94  push    rdi
0x140005b95  push    r12
0x140005b97  push    r13
0x140005b99  push    r14
0x140005b9b  push    r15
0x140005b9d  sub     rsp, 28h
0x140005ba1  mov     edi, [rsp+68h+arg_20]
0x140005ba8  mov     esi, 8
0x140005bad  mov     eax, esi
0x140005baf  mov     rbp, r9
0x140005bb2  mul     rdi
0x140005bb5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005bbc  mov     r12, r8
0x140005bbf  lea     r14, [rsi-9]
0x140005bc3  cmovb   rax, r14
0x140005bc7  mov     rcx, rax; unsigned __int64
0x140005bca  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140005bcf  mov     r15, rax
0x140005bd2  mov     eax, esi
0x140005bd4  mul     rdi
0x140005bd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005bde  cmovb   rax, r14
0x140005be2  mov     rcx, rax; unsigned __int64
0x140005be5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140005bea  xor     r13d, r13d
0x140005bed  mov     r14, rax
0x140005bf0  test    r15, r15
0x140005bf3  jz      short loc_140005C6C
0x140005bf5  test    rax, rax
0x140005bf8  jz      short loc_140005C6C
0x140005bfa  mov     ebx, r13d
0x140005bfd  mov     esi, r13d
0x140005c00  test    edi, edi
0x140005c02  jz      short loc_140005C3D
0x140005c04  test    ebx, ebx
0x140005c06  js      short loc_140005C51
0x140005c08  mov     eax, esi
0x140005c0a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x140005c11  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140005c15  mov     [r15+rax*8], rcx
0x140005c19  mov     rcx, [r12+rax*8]; sourceString
0x140005c1d  inc     rdx; length
0x140005c20  cmp     [rcx+rdx*2], r13w
0x140005c25  jnz     short loc_140005C1D
0x140005c27  lea     r8, [r14+rax*8]; string
0x140005c2b  call    cs:__imp_WindowsCreateString
0x140005c31  inc     esi
0x140005c33  mov     ebx, eax
0x140005c35  cmp     esi, edi
0x140005c37  jb      short loc_140005C04
0x140005c39  test    eax, eax
0x140005c3b  js      short loc_140005C51
0x140005c3d  mov     r9, rbp
0x140005c40  mov     r8d, edi
0x140005c43  mov     rdx, r15
0x140005c46  mov     rcx, r14
0x140005c49  call    cs:__imp_RoRegisterActivationFactories
0x140005c4f  mov     ebx, eax
0x140005c51  mov     edi, r13d
0x140005c54  test    esi, esi
0x140005c56  jz      short loc_140005C71
0x140005c58  mov     ecx, edi
0x140005c5a  mov     rcx, [r14+rcx*8]; string
0x140005c5e  call    cs:__imp_WindowsDeleteString
0x140005c64  inc     edi
0x140005c66  cmp     edi, esi
0x140005c68  jb      short loc_140005C58
0x140005c6a  jmp     short loc_140005C71
0x140005c6c  mov     ebx, 8007000Eh
0x140005c71  mov     rcx, r15; void *
0x140005c74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005c79  mov     rcx, r14; void *
0x140005c7c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005c81  mov     eax, ebx
0x140005c83  add     rsp, 28h
0x140005c87  pop     r15
0x140005c89  pop     r14
0x140005c8b  pop     r13
0x140005c8d  pop     r12
0x140005c8f  pop     rdi
0x140005c90  pop     rsi
0x140005c91  pop     rbp
0x140005c92  pop     rbx
0x140005c93  retn
```
