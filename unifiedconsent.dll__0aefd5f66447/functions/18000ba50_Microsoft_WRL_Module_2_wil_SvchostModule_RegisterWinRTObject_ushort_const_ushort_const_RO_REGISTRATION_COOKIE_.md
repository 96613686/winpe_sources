# Microsoft::WRL::Module<2,wil::SvchostModule>::RegisterWinRTObject(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000ba50`
- end: `0x18000bb54`
- name: `?RegisterWinRTObject@?$Module@$01VSvchostModule@wil@@@WRL@Microsoft@@UEAAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002834`
- `0x180002d00`
- `0x18000ba50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bb1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bb1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000baeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000baeb`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000bb09`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000bb09`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,wil::SvchostModule>::RegisterWinRTObject(
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
  unsigned __int64 v11; // rdx
  HSTRING *v12; // r14
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  HRESULT String; // eax
  unsigned int i; // edi
  unsigned __int64 v19; // rdx

  v6 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v6 = -1;
  v8 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v10;
  if ( v8 && v10 )
  {
    v13 = 0;
    v14 = 0;
    if ( a5 )
    {
      while ( v13 >= 0 )
      {
        v15 = -1;
        v8[v14] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v16 = *(const WCHAR **)(a3 + 8LL * v14);
        do
          ++v15;
        while ( v16[v15] );
        String = WindowsCreateString(v16, v15, &v12[v14++]);
        v13 = String;
        if ( v14 >= a5 )
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
      v13 = RoRegisterActivationFactories(v12, v8, a5, a4);
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
0x18000ba50  push    rbx
0x18000ba52  push    rbp
0x18000ba53  push    rsi
0x18000ba54  push    rdi
0x18000ba55  push    r12
0x18000ba57  push    r13
0x18000ba59  push    r14
0x18000ba5b  push    r15
0x18000ba5d  sub     rsp, 28h
0x18000ba61  mov     edi, [rsp+68h+arg_20]
0x18000ba68  mov     esi, 8
0x18000ba6d  mov     eax, esi
0x18000ba6f  mov     rbp, r9
0x18000ba72  mul     rdi
0x18000ba75  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ba7c  mov     r12, r8
0x18000ba7f  lea     r14, [rsi-9]
0x18000ba83  cmovb   rax, r14
0x18000ba87  mov     rcx, rax; unsigned __int64
0x18000ba8a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ba8f  mov     r15, rax
0x18000ba92  mov     eax, esi
0x18000ba94  mul     rdi
0x18000ba97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ba9e  cmovb   rax, r14
0x18000baa2  mov     rcx, rax; unsigned __int64
0x18000baa5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000baaa  xor     r13d, r13d
0x18000baad  mov     r14, rax
0x18000bab0  test    r15, r15
0x18000bab3  jz      short loc_18000BB2C
0x18000bab5  test    rax, rax
0x18000bab8  jz      short loc_18000BB2C
0x18000baba  mov     ebx, r13d
0x18000babd  mov     esi, r13d
0x18000bac0  test    edi, edi
0x18000bac2  jz      short loc_18000BAFD
0x18000bac4  test    ebx, ebx
0x18000bac6  js      short loc_18000BB11
0x18000bac8  mov     eax, esi
0x18000baca  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000bad1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000bad5  mov     [r15+rax*8], rcx
0x18000bad9  mov     rcx, [r12+rax*8]; sourceString
0x18000badd  inc     rdx; length
0x18000bae0  cmp     [rcx+rdx*2], r13w
0x18000bae5  jnz     short loc_18000BADD
0x18000bae7  lea     r8, [r14+rax*8]; string
0x18000baeb  call    cs:__imp_WindowsCreateString
0x18000baf1  inc     esi
0x18000baf3  mov     ebx, eax
0x18000baf5  cmp     esi, edi
0x18000baf7  jb      short loc_18000BAC4
0x18000baf9  test    eax, eax
0x18000bafb  js      short loc_18000BB11
0x18000bafd  mov     r9, rbp
0x18000bb00  mov     r8d, edi
0x18000bb03  mov     rdx, r15
0x18000bb06  mov     rcx, r14
0x18000bb09  call    cs:__imp_RoRegisterActivationFactories
0x18000bb0f  mov     ebx, eax
0x18000bb11  mov     edi, r13d
0x18000bb14  test    esi, esi
0x18000bb16  jz      short loc_18000BB31
0x18000bb18  mov     ecx, edi
0x18000bb1a  mov     rcx, [r14+rcx*8]; string
0x18000bb1e  call    cs:__imp_WindowsDeleteString
0x18000bb24  inc     edi
0x18000bb26  cmp     edi, esi
0x18000bb28  jb      short loc_18000BB18
0x18000bb2a  jmp     short loc_18000BB31
0x18000bb2c  mov     ebx, 8007000Eh
0x18000bb31  mov     rcx, r15; void *
0x18000bb34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bb39  mov     rcx, r14; void *
0x18000bb3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bb41  mov     eax, ebx
0x18000bb43  add     rsp, 28h
0x18000bb47  pop     r15
0x18000bb49  pop     r14
0x18000bb4b  pop     r13
0x18000bb4d  pop     r12
0x18000bb4f  pop     rdi
0x18000bb50  pop     rsi
0x18000bb51  pop     rbp
0x18000bb52  pop     rbx
0x18000bb53  retn
```
