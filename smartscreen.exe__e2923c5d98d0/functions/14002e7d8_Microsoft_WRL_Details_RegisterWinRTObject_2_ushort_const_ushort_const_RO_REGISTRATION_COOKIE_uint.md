# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x14002e7d8`
- end: `0x14002e8d8`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002efc0`

## callees

- `0x140025f04`
- `0x140025fe4`
- `0x14002e7d8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14002e86f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14002e86f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14002e8a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14002e8a2`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14002e88d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x14002e88d`

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
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
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
0x14002e7d8  push    rbx
0x14002e7da  push    rbp
0x14002e7db  push    rsi
0x14002e7dc  push    rdi
0x14002e7dd  push    r12
0x14002e7df  push    r13
0x14002e7e1  push    r14
0x14002e7e3  push    r15
0x14002e7e5  sub     rsp, 28h
0x14002e7e9  mov     r12, rdx
0x14002e7ec  mov     edi, r9d
0x14002e7ef  mov     esi, 8
0x14002e7f4  mov     rbp, r8
0x14002e7f7  mov     eax, esi
0x14002e7f9  mul     rdi
0x14002e7fc  lea     r14, [rsi-9]
0x14002e800  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002e807  cmovb   rax, r14
0x14002e80b  mov     rcx, rax; unsigned __int64
0x14002e80e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002e813  mov     r15, rax
0x14002e816  mov     eax, esi
0x14002e818  mul     rdi
0x14002e81b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002e822  cmovb   rax, r14
0x14002e826  mov     rcx, rax; unsigned __int64
0x14002e829  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002e82e  xor     r13d, r13d
0x14002e831  mov     r14, rax
0x14002e834  test    r15, r15
0x14002e837  jz      short loc_14002E8B0
0x14002e839  test    rax, rax
0x14002e83c  jz      short loc_14002E8B0
0x14002e83e  mov     ebx, r13d
0x14002e841  mov     esi, r13d
0x14002e844  test    edi, edi
0x14002e846  jz      short loc_14002E881
0x14002e848  test    ebx, ebx
0x14002e84a  js      short loc_14002E895
0x14002e84c  mov     eax, esi
0x14002e84e  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x14002e855  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002e859  mov     [r15+rax*8], rcx
0x14002e85d  mov     rcx, [r12+rax*8]; sourceString
0x14002e861  inc     rdx; length
0x14002e864  cmp     [rcx+rdx*2], r13w
0x14002e869  jnz     short loc_14002E861
0x14002e86b  lea     r8, [r14+rax*8]; string
0x14002e86f  call    cs:__imp_WindowsCreateString
0x14002e875  inc     esi
0x14002e877  mov     ebx, eax
0x14002e879  cmp     esi, edi
0x14002e87b  jb      short loc_14002E848
0x14002e87d  test    eax, eax
0x14002e87f  js      short loc_14002E895
0x14002e881  mov     r9, rbp
0x14002e884  mov     r8d, edi
0x14002e887  mov     rdx, r15
0x14002e88a  mov     rcx, r14
0x14002e88d  call    cs:__imp_RoRegisterActivationFactories
0x14002e893  mov     ebx, eax
0x14002e895  mov     edi, r13d
0x14002e898  test    esi, esi
0x14002e89a  jz      short loc_14002E8B5
0x14002e89c  mov     ecx, edi
0x14002e89e  mov     rcx, [r14+rcx*8]; string
0x14002e8a2  call    cs:__imp_WindowsDeleteString
0x14002e8a8  inc     edi
0x14002e8aa  cmp     edi, esi
0x14002e8ac  jb      short loc_14002E89C
0x14002e8ae  jmp     short loc_14002E8B5
0x14002e8b0  mov     ebx, 8007000Eh
0x14002e8b5  mov     rcx, r15; void *
0x14002e8b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002e8bd  mov     rcx, r14; void *
0x14002e8c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002e8c5  mov     eax, ebx
0x14002e8c7  add     rsp, 28h
0x14002e8cb  pop     r15
0x14002e8cd  pop     r14
0x14002e8cf  pop     r13
0x14002e8d1  pop     r12
0x14002e8d3  pop     rdi
0x14002e8d4  pop     rsi
0x14002e8d5  pop     rbp
0x14002e8d6  pop     rbx
0x14002e8d7  retn
```
