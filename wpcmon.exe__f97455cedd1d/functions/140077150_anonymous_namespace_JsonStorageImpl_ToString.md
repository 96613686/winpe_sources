# _anonymous_namespace_::JsonStorageImpl::ToString

- ea: `0x140077150`
- end: `0x14007725a`
- name: `_anonymous_namespace_::JsonStorageImpl::ToString`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140006338`
- `0x140009858`
- `0x140060f58`
- `0x14007456c`
- `0x140075d60`
- `0x140077150`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140077225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400771ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400771ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::JsonStorageImpl::ToString(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 *v4; // rax
  int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rcx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v9; // r8
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+80h] [rbp+20h] BYREF
  HSTRING string; // [rsp+90h] [rbp+30h] BYREF
  __int64 v14; // [rsp+98h] [rbp+38h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  v12 = v3;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  string = 0;
  v4 = WinRT::As<Windows::Data::Json::IJsonValue,Windows::Data::Json::IJsonArray>(&v14, &v12);
  v5 =  Windows::Data::Json::IJsonValue::`vcall'{56,{flat}}(*v4, &string);
  v6 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v5 < 0 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v7 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  v9 = -1;
  do
    ++v9;
  while ( StringRawBuffer[v9] );
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, StringRawBuffer, v9);
  if ( string )
    WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x140077150  mov     [rsp-18h+arg_8], rbx
0x140077155  push    rbp
0x140077156  push    rsi
0x140077157  push    rdi
0x140077158  mov     rbp, rsp
0x14007715b  sub     rsp, 60h
0x14007715f  mov     rbx, rdx
0x140077162  xor     esi, esi
0x140077164  mov     [rbp+var_40], esi
0x140077167  mov     rcx, [rcx+10h]
0x14007716b  mov     [rbp+arg_0], rcx
0x14007716f  test    rcx, rcx
0x140077172  jz      short loc_140077181
0x140077174  mov     rax, [rcx]
0x140077177  mov     rax, [rax+8]
0x14007717b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077180  nop
0x140077181  lea     rax, [rbp+arg_0]
0x140077185  mov     [rbp+var_38], rax
0x140077189  mov     [rbp+string], rsi
0x14007718d  mov     [rbp+var_40], 2
0x140077194  lea     rdx, [rbp+arg_0]
0x140077198  lea     rcx, [rbp+arg_18]
0x14007719c  call    ??$As@UIJsonValue@Json@Data@Windows@@UIJsonArray@234@@WinRT@@YA?AV?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIJsonArray@Json@Data@Windows@@@23@PEAX@Z; WinRT::As<Windows::Data::Json::IJsonValue,Windows::Data::Json::IJsonArray>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> const &,void *)
0x1400771a1  nop
0x1400771a2  lea     rdx, [rbp+string]
0x1400771a6  mov     rcx, [rax]
0x1400771a9  call    ??_9IJsonValue@Json@Data@Windows@@$BDI@AA; [thunk]: Windows::Data::Json::IJsonValue::`vcall'{56,{flat}}
0x1400771ae  mov     edi, eax
0x1400771b0  mov     rcx, [rbp+arg_18]
0x1400771b4  test    rcx, rcx
0x1400771b7  jz      short loc_1400771CA
0x1400771b9  mov     [rbp+arg_18], rsi
0x1400771bd  mov     rdx, [rcx]
0x1400771c0  mov     rax, [rdx+10h]
0x1400771c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400771c9  nop
0x1400771ca  test    edi, edi
0x1400771cc  js      short loc_14007723E
0x1400771ce  mov     rcx, [rbp+arg_0]
0x1400771d2  test    rcx, rcx
0x1400771d5  jz      short loc_1400771E8
0x1400771d7  mov     [rbp+arg_0], rsi
0x1400771db  mov     rax, [rcx]
0x1400771de  mov     rax, [rax+10h]
0x1400771e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400771e7  nop
0x1400771e8  xor     edx, edx; length
0x1400771ea  mov     rcx, [rbp+string]; string
0x1400771ee  call    cs:__imp_WindowsGetStringRawBuffer
0x1400771f4  xorps   xmm0, xmm0
0x1400771f7  movups  xmmword ptr [rbx], xmm0
0x1400771fa  mov     [rbx+10h], rsi
0x1400771fe  mov     [rbx+18h], rsi
0x140077202  or      r8, 0FFFFFFFFFFFFFFFFh
0x140077206  inc     r8
0x140077209  cmp     [rax+r8*2], si
0x14007720e  jnz     short loc_140077206
0x140077210  mov     rdx, rax
0x140077213  mov     rcx, rbx
0x140077216  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14007721b  nop
0x14007721c  mov     rcx, [rbp+string]; string
0x140077220  test    rcx, rcx
0x140077223  jz      short loc_14007722B
0x140077225  call    cs:__imp_WindowsDeleteString
0x14007722b  mov     rax, rbx
0x14007722e  mov     rbx, [rsp+60h+arg_8]
0x140077236  add     rsp, 60h
0x14007723a  pop     rdi
0x14007723b  pop     rsi
0x14007723c  pop     rbp
0x14007723d  retn
0x14007723e  mov     edx, edi; int
0x140077240  lea     rcx, [rbp+pExceptionObject]; this
0x140077244  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140077249  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140077250  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140077254  call    _CxxThrowException_0
```
