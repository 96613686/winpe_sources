# DevhlprGetReaderBitmapBlobInternal(ushort *,uchar *,ulong,ulong *)

- ea: `0x180038ac0`
- end: `0x180038c65`
- name: `?DevhlprGetReaderBitmapBlobInternal@@YA?AV?$scoped_error@Utag@hresult_error@@@errorlib@@PEAGPEAEKPEAK@Z`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800389bc`

## callees

- `0x180038830`
- `0x180038898`
- `0x1800388cc`
- `0x180038908`
- `0x180038940`
- `0x180038a7c`
- `0x180038ac0`
- `0x180038de0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180038c1a`
- `msvcrt!memcpy_s` at `0x180038c1a`
- `WinSCard!SCardEstablishContext` at `0x180038b54`
- `WinSCard!SCardEstablishContext` at `0x180038b54`
- `WinSCard!SCardGetReaderIconW` at `0x180038b9a`
- `WinSCard!SCardGetReaderIconW` at `0x180038b9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int *__fastcall DevhlprGetReaderBitmapBlobInternal(int *a1, __int64 a2, void *a3, unsigned int a4, _DWORD *a5)
{
  rsize_t v5; // rdi
  _DWORD *v10; // rsi
  int v11; // eax
  rsize_t v12; // rax
  LONG ReaderIconW; // [rsp+20h] [rbp-48h] BYREF
  int v14; // [rsp+28h] [rbp-40h] BYREF
  int v15; // [rsp+2Ch] [rbp-3Ch]
  SCARDCONTEXT phContext; // [rsp+30h] [rbp-38h] BYREF
  void *Source; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-28h] BYREF
  __int16 v19; // [rsp+50h] [rbp-18h]
  rsize_t SourceSize; // [rsp+B0h] [rbp+48h] BYREF

  v5 = a4;
  errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(&v14);
  phContext = 0;
  if ( a3 )
  {
    if ( !(_DWORD)v5 )
      goto LABEL_3;
LABEL_6:
    if ( !a2 )
      goto LABEL_3;
    v10 = a5;
    if ( !a5 )
      goto LABEL_3;
    phContext = 0;
    ReaderIconW = SCardEstablishContext(2u, 0, 0, &phContext);
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v14, &ReaderIconW);
    v15 = 3;
    v11 = v14;
    if ( v14 < 0
      || (Source = 0,
          LODWORD(SourceSize) = -1,
          ReaderIconW = SCardGetReaderIconW(phContext, a2, &Source, &SourceSize),
          errorlib::scoped_error<hresult_error::tag>::receive<long>(&v14, &ReaderIconW),
          v15 = 3,
          v11 = v14,
          v14 < 0) )
    {
      *a1 = v11;
      a1[1] = 2;
      v15 = 5;
      errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
      goto LABEL_4;
    }
    v18[0] = &phContext;
    v18[1] = &Source;
    v19 = 256;
    v12 = (unsigned int)SourceSize;
    *v10 = SourceSize;
    if ( a3 )
    {
      if ( (unsigned int)v5 >= (unsigned int)v12 )
      {
        memcpy_s(a3, v5, Source, v12);
        *a1 = v14;
        a1[1] = 2;
        v15 = 5;
        errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
        goto LABEL_13;
      }
      ReaderIconW = -2146435064;
    }
    else
    {
      ReaderIconW = 0;
    }
    errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(a1, &ReaderIconW);
LABEL_13:
    wil::details::ScopeExitFnGuard__lambda_38cbbc084cd607496c2708d4d1fe6080___::operator()(v18);
    goto LABEL_4;
  }
  if ( !(_DWORD)v5 )
    goto LABEL_6;
LABEL_3:
  ReaderIconW = -2146435068;
  errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(a1, &ReaderIconW);
LABEL_4:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phContext);
  errorlib::scoped_error<hresult_error::tag>::~scoped_error<hresult_error::tag>(&v14);
  return a1;
}

```

## disassembly

```asm
0x180038ac0  push    rbp
0x180038ac2  push    rbx
0x180038ac3  push    rsi
0x180038ac4  push    rdi
0x180038ac5  push    r14
0x180038ac7  push    r15
0x180038ac9  mov     rbp, rsp
0x180038acc  sub     rsp, 68h
0x180038ad0  mov     edi, r9d
0x180038ad3  mov     r14, r8
0x180038ad6  mov     r15, rdx
0x180038ad9  mov     rbx, rcx
0x180038adc  lea     rcx, [rbp+var_40]
0x180038ae0  call    ??0?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(void)
0x180038ae5  nop
0x180038ae6  mov     [rbp+phContext], 0
0x180038aee  test    r14, r14
0x180038af1  jnz     short loc_180038B2E
0x180038af3  test    edi, edi
0x180038af5  jz      short loc_180038B32
0x180038af7  mov     [rbp+var_48], 80100004h
0x180038afe  lea     rdx, [rbp+var_48]
0x180038b02  mov     rcx, rbx
0x180038b05  call    ??$make_initiated@J@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(long &&)
0x180038b0a  nop
0x180038b0b  lea     rcx, [rbp+phContext]
0x180038b0f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?SCardReleaseContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180038b14  nop
0x180038b15  lea     rcx, [rbp+var_40]
0x180038b19  call    ??1?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<hresult_error::tag>::~scoped_error<hresult_error::tag>(void)
0x180038b1e  mov     rax, rbx
0x180038b21  add     rsp, 68h
0x180038b25  pop     r15
0x180038b27  pop     r14
0x180038b29  pop     rdi
0x180038b2a  pop     rsi
0x180038b2b  pop     rbx
0x180038b2c  pop     rbp
0x180038b2d  retn
0x180038b2e  test    edi, edi
0x180038b30  jz      short loc_180038AF7
0x180038b32  test    r15, r15
0x180038b35  jz      short loc_180038AF7
0x180038b37  mov     rsi, [rbp+arg_20]
0x180038b3b  test    rsi, rsi
0x180038b3e  jz      short loc_180038AF7
0x180038b40  mov     [rbp+phContext], 0
0x180038b48  lea     r9, [rbp+phContext]; phContext
0x180038b4c  xor     r8d, r8d; pvReserved2
0x180038b4f  xor     edx, edx; pvReserved1
0x180038b51  lea     ecx, [rdx+2]; dwScope
0x180038b54  call    cs:__imp_SCardEstablishContext
0x180038b5a  mov     [rbp+var_48], eax
0x180038b5d  lea     rdx, [rbp+var_48]
0x180038b61  lea     rcx, [rbp+var_40]
0x180038b65  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x180038b6a  mov     [rbp+var_3C], 3
0x180038b71  mov     eax, [rbp+var_40]
0x180038b74  test    eax, eax
0x180038b76  js      loc_180038C42
0x180038b7c  mov     [rbp+Source], 0
0x180038b84  mov     dword ptr [rbp+SourceSize], 0FFFFFFFFh
0x180038b8b  lea     r9, [rbp+SourceSize]
0x180038b8f  lea     r8, [rbp+Source]
0x180038b93  mov     rdx, r15
0x180038b96  mov     rcx, [rbp+phContext]
0x180038b9a  call    cs:__imp_SCardGetReaderIconW
0x180038ba0  mov     [rbp+var_48], eax
0x180038ba3  lea     rdx, [rbp+var_48]
0x180038ba7  lea     rcx, [rbp+var_40]
0x180038bab  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x180038bb0  mov     [rbp+var_3C], 3
0x180038bb7  mov     eax, [rbp+var_40]
0x180038bba  test    eax, eax
0x180038bbc  js      loc_180038C42
0x180038bc2  lea     rax, [rbp+phContext]
0x180038bc6  mov     [rbp+var_28], rax
0x180038bca  lea     rax, [rbp+Source]
0x180038bce  mov     [rbp+var_20], rax
0x180038bd2  mov     [rbp+var_18], 100h
0x180038bd8  mov     eax, dword ptr [rbp+SourceSize]
0x180038bdb  mov     [rsi], eax
0x180038bdd  test    r14, r14
0x180038be0  jnz     short loc_180038C00
0x180038be2  mov     [rbp+var_48], r14d
0x180038be6  lea     rdx, [rbp+var_48]
0x180038bea  mov     rcx, rbx
0x180038bed  call    ??$make_initiated@J@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<long>(long &&)
0x180038bf2  lea     rcx, [rbp+var_28]
0x180038bf6  call    wil__details__ScopeExitFnGuard__lambda_38cbbc084cd607496c2708d4d1fe6080_____operator__
0x180038bfb  jmp     loc_180038B0B
0x180038c00  cmp     edi, eax
0x180038c02  jnb     short loc_180038C0D
0x180038c04  mov     [rbp+var_48], 80100008h
0x180038c0b  jmp     short loc_180038BE6
0x180038c0d  mov     r9, rax; SourceSize
0x180038c10  mov     rdx, rdi; DestinationSize
0x180038c13  mov     r8, [rbp+Source]; Source
0x180038c17  mov     rcx, r14; Destination
0x180038c1a  call    cs:__imp_memcpy_s
0x180038c20  mov     eax, [rbp+var_40]
0x180038c23  mov     [rbx], eax
0x180038c25  mov     dword ptr [rbx+4], 2
0x180038c2c  mov     [rbp+var_3C], 5
0x180038c33  mov     edx, 3
0x180038c38  mov     rcx, rbx
0x180038c3b  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180038c40  jmp     short loc_180038BF2
0x180038c42  mov     [rbx], eax
0x180038c44  mov     dword ptr [rbx+4], 2
0x180038c4b  mov     [rbp+var_3C], 5
0x180038c52  mov     edx, 3
0x180038c57  mov     rcx, rbx
0x180038c5a  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180038c5f  jmp     loc_180038B0B
```
