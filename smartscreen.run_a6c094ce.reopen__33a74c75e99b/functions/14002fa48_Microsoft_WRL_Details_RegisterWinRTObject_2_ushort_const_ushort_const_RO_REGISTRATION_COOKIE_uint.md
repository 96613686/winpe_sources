# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x14002fa48`
- end: `0x14002fb63`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140030270`

## callees

- `0x140027084`
- `0x140027158`
- `0x14002fa48`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14002fae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14002fae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14002fb26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14002fb26`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14002fb0b`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14002fb0b`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  const struct std::nothrow_t *v11; // rdx
  HSTRING *v12; // r14
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  HRESULT String; // eax
  unsigned int i; // edi
  const struct std::nothrow_t *v19; // rdx

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
  v12 = v10;
  if ( v8 && v10 )
  {
    v13 = 0;
    v14 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v13 >= 0 )
      {
        v15 = -1;
        v8[v14] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v16 = *(const WCHAR **)(a2 + 8LL * v14);
        do
          ++v15;
        while ( v16[v15] );
        String = WindowsCreateString(v16, v15, &v12[v14++]);
        v13 = String;
        if ( v14 >= (unsigned int)v5 )
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
      v13 = RoRegisterActivationFactories(v12, v8, (unsigned int)v5, a3);
    }
    for ( i = 0; i < v14; ++i )
      WindowsDeleteString(v12[i]);
  }
  else
  {
    v13 = -2147024882;
  }
  operator delete(v8, v11);
  operator delete(v12, v19);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002fa48  push    rbx
0x14002fa4a  push    rbp
0x14002fa4b  push    rsi
0x14002fa4c  push    rdi
0x14002fa4d  push    r12
0x14002fa4f  push    r13
0x14002fa51  push    r14
0x14002fa53  push    r15
0x14002fa55  sub     rsp, 28h
0x14002fa59  mov     r12, rdx
0x14002fa5c  mov     edi, r9d
0x14002fa5f  mov     esi, 8
0x14002fa64  mov     rbp, r8
0x14002fa67  mov     eax, esi
0x14002fa69  mul     rdi
0x14002fa6c  lea     r14, [rsi-9]
0x14002fa70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002fa77  cmovb   rax, r14
0x14002fa7b  mov     rcx, rax; unsigned __int64
0x14002fa7e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002fa83  mov     r15, rax
0x14002fa86  mov     eax, esi
0x14002fa88  mul     rdi
0x14002fa8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002fa92  cmovb   rax, r14
0x14002fa96  mov     rcx, rax; unsigned __int64
0x14002fa99  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002fa9e  xor     r13d, r13d
0x14002faa1  mov     r14, rax
0x14002faa4  test    r15, r15
0x14002faa7  jz      loc_14002FB3A
0x14002faad  test    rax, rax
0x14002fab0  jz      loc_14002FB3A
0x14002fab6  mov     ebx, r13d
0x14002fab9  mov     esi, r13d
0x14002fabc  test    edi, edi
0x14002fabe  jz      short loc_14002FAFF
0x14002fac0  test    ebx, ebx
0x14002fac2  js      short loc_14002FB19
0x14002fac4  mov     eax, esi
0x14002fac6  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x14002facd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002fad1  mov     [r15+rax*8], rcx
0x14002fad5  mov     rcx, [r12+rax*8]; sourceString
0x14002fad9  inc     rdx; length
0x14002fadc  cmp     [rcx+rdx*2], r13w
0x14002fae1  jnz     short loc_14002FAD9
0x14002fae3  lea     r8, [r14+rax*8]; string
0x14002fae7  call    cs:__imp_WindowsCreateString
0x14002faee  nop     dword ptr [rax+rax+00h]
0x14002faf3  inc     esi
0x14002faf5  mov     ebx, eax
0x14002faf7  cmp     esi, edi
0x14002faf9  jb      short loc_14002FAC0
0x14002fafb  test    eax, eax
0x14002fafd  js      short loc_14002FB19
0x14002faff  mov     r9, rbp
0x14002fb02  mov     r8d, edi
0x14002fb05  mov     rdx, r15
0x14002fb08  mov     rcx, r14
0x14002fb0b  call    cs:__imp_RoRegisterActivationFactories
0x14002fb12  nop     dword ptr [rax+rax+00h]
0x14002fb17  mov     ebx, eax
0x14002fb19  mov     edi, r13d
0x14002fb1c  test    esi, esi
0x14002fb1e  jz      short loc_14002FB3F
0x14002fb20  mov     ecx, edi
0x14002fb22  mov     rcx, [r14+rcx*8]; string
0x14002fb26  call    cs:__imp_WindowsDeleteString
0x14002fb2d  nop     dword ptr [rax+rax+00h]
0x14002fb32  inc     edi
0x14002fb34  cmp     edi, esi
0x14002fb36  jb      short loc_14002FB20
0x14002fb38  jmp     short loc_14002FB3F
0x14002fb3a  mov     ebx, 8007000Eh
0x14002fb3f  mov     rcx, r15; void *
0x14002fb42  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002fb47  mov     rcx, r14; void *
0x14002fb4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002fb4f  mov     eax, ebx
0x14002fb51  add     rsp, 28h
0x14002fb55  pop     r15
0x14002fb57  pop     r14
0x14002fb59  pop     r13
0x14002fb5b  pop     r12
0x14002fb5d  pop     rdi
0x14002fb5e  pop     rsi
0x14002fb5f  pop     rbp
0x14002fb60  pop     rbx
0x14002fb61  retn
```
