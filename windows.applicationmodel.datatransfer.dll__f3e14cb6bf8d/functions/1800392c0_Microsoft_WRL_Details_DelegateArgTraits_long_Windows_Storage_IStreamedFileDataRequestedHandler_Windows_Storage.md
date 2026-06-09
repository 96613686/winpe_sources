# Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::Invoke(Windows::Storage::Streams::IOutputStream *)

- ea: `0x1800392c0`
- end: `0x180039445`
- name: `?Invoke@?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStreamedFileDataRequestedHandler@Storage@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_@@$0?0PEAUIOutputStream@Streams@Storage@Windows@@@?$DelegateArgTraits@P8IStreamedFileDataRequestedHandler@Storage@Windows@@EAAJPEAUIOutputStream@Streams@23@@Z@Details@WRL@Microsoft@@UEAAJPEAUIOutputStream@Streams@Storage@Windows@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(__int64, struct Windows::Storage::Streams::IOutputStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180022f2c`
- `0x180025abc`
- `0x1800392c0`
- `0x18004e9f8`
- `0x18004eabc`
- `0x180081010`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x1800393db`
- `SHCORE!SHCreateMemStream` at `0x1800393db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003935f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800393a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003935f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800393a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039396`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039396`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Storage::IStreamedFileDataRequestedHandler::*)(Windows::Storage::Streams::IOutputStream *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Storage::IStreamedFileDataRequestedHandler,Microsoft::WRL::FtmBase>,_lambda_bc4a02a5457fa0ad093a971c4b6ec30c_,-1,Windows::Storage::Streams::IOutputStream *>::Invoke(
        __int64 a1,
        struct Windows::Storage::Streams::IOutputStream *a2)
{
  PCWSTR StringRawBuffer; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r14
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // rax
  int v11; // edi
  struct IStream *v12; // rax
  struct IStream *v13; // rbx
  unsigned __int16 v15[8]; // [rsp+20h] [rbp-C8h] BYREF
  __int128 v16; // [rsp+30h] [rbp-B8h]
  __int128 v17; // [rsp+40h] [rbp-A8h]
  __int128 v18; // [rsp+50h] [rbp-98h]
  __int128 v19; // [rsp+60h] [rbp-88h]
  __int128 v20; // [rsp+70h] [rbp-78h]
  __int128 v21; // [rsp+80h] [rbp-68h]
  _OWORD v22[2]; // [rsp+90h] [rbp-58h]

  *(_OWORD *)v15 = *(_OWORD *)L" is managed by your organization which doesn't allow putting it here.";
  v16 = *(_OWORD *)L"ged by your organization which doesn't allow putting it here.";
  v17 = *(_OWORD *)L"our organization which doesn't allow putting it here.";
  v18 = *(_OWORD *)L"nization which doesn't allow putting it here.";
  v19 = *(_OWORD *)L" which doesn't allow putting it here.";
  v20 = *(_OWORD *)L"oesn't allow putting it here.";
  v21 = *(_OWORD *)L"llow putting it here.";
  v22[0] = *(_OWORD *)L"ting it here.";
  *(_OWORD *)((char *)v22 + 12) = *(_OWORD *)L"t here.";
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 64), 0);
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( v15[v6] );
  do
    ++v5;
  while ( StringRawBuffer[v5] );
  v7 = (unsigned int)(v6 + v5 + 1);
  v8 = v6 + v5 + 1;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
  v10 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 64), 0);
  v11 = StringCchCopyW(v9, (unsigned int)v7, v10);
  if ( v11 < 0 || (v11 = StringCchCatW(v9, v8, v15), v11 < 0) )
  {
    Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot((unsigned int)v11);
  }
  else
  {
    v12 = SHCreateMemStream((const BYTE *)v9, 2 * (int)v7);
    v13 = v12;
    if ( v12 )
      CopyStreamToOutputStream(v12, a2);
    CoTaskMemFree(v9);
    if ( v13 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800392c0  mov     r11, rsp
0x1800392c3  mov     [r11+18h], rbx
0x1800392c7  push    rbp
0x1800392c8  push    rsi
0x1800392c9  push    rdi
0x1800392ca  push    r14
0x1800392cc  push    r15
0x1800392ce  sub     rsp, 0C0h
0x1800392d5  mov     rax, cs:__security_cookie
0x1800392dc  xor     rax, rsp
0x1800392df  mov     [rsp+0E8h+var_38], rax
0x1800392e7  mov     rbp, rdx
0x1800392ea  mov     rdi, rcx
0x1800392ed  movaps  xmm0, xmmword ptr cs:aIsManagedByYou; " is managed by your organization which "...
0x1800392f4  movups  xmmword ptr [rsp+0E8h+var_C8], xmm0
0x1800392f9  movaps  xmm1, xmmword ptr cs:aIsManagedByYou+10h; "ged by your organization which doesn't "...
0x180039300  movups  [rsp+0E8h+var_B8], xmm1
0x180039305  movaps  xmm0, xmmword ptr cs:aIsManagedByYou+20h; "our organization which doesn't allow pu"...
0x18003930c  movups  [rsp+0E8h+var_A8], xmm0
0x180039311  movaps  xmm1, xmmword ptr cs:aIsManagedByYou+30h; "nization which doesn't allow putting it"...
0x180039318  movups  [rsp+0E8h+var_98], xmm1
0x18003931d  movaps  xmm0, xmmword ptr cs:aIsManagedByYou+40h; " which doesn't allow putting it here."
0x180039324  movups  [rsp+0E8h+var_88], xmm0
0x180039329  movaps  xmm1, xmmword ptr cs:aIsManagedByYou+50h; "oesn't allow putting it here."
0x180039330  movups  [rsp+0E8h+var_78], xmm1
0x180039335  movaps  xmm0, xmmword ptr cs:aIsManagedByYou+60h; "llow putting it here."
0x18003933c  movups  xmmword ptr [r11-68h], xmm0
0x180039341  movaps  xmm1, xmmword ptr cs:aIsManagedByYou+70h; "ting it here."
0x180039348  movups  xmmword ptr [r11-58h], xmm1
0x18003934d  movups  xmm0, xmmword ptr cs:aIsManagedByYou+7Ch; "t here."
0x180039354  movups  xmmword ptr [r11-4Ch], xmm0
0x180039359  xor     edx, edx; length
0x18003935b  mov     rcx, [rcx+40h]; string
0x18003935f  call    cs:__imp_WindowsGetStringRawBuffer
0x180039365  lea     r8, [rsp+0E8h+var_C8]
0x18003936a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003936e  mov     rdx, rcx
0x180039371  xor     r15d, r15d
0x180039374  inc     rdx
0x180039377  cmp     [r8+rdx*2], r15w
0x18003937c  jnz     short loc_180039374
0x18003937e  inc     rcx
0x180039381  cmp     [rax+rcx*2], r15w
0x180039386  jnz     short loc_18003937E
0x180039388  lea     r14d, [rcx+1]
0x18003938c  add     r14d, edx
0x18003938f  mov     ebx, r14d
0x180039392  lea     rcx, [r14+r14]; cb
0x180039396  call    cs:__imp_CoTaskMemAlloc
0x18003939c  mov     rsi, rax
0x18003939f  xor     edx, edx; length
0x1800393a1  mov     rcx, [rdi+40h]; string
0x1800393a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800393ab  mov     r8, rax; unsigned __int16 *
0x1800393ae  mov     edx, r14d; unsigned __int64
0x1800393b1  mov     rcx, rsi; unsigned __int16 *
0x1800393b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800393b9  mov     edi, eax
0x1800393bb  test    eax, eax
0x1800393bd  js      short loc_180039415
0x1800393bf  lea     r8, [rsp+0E8h+var_C8]; unsigned __int16 *
0x1800393c4  mov     edx, ebx; unsigned __int64
0x1800393c6  mov     rcx, rsi; unsigned __int16 *
0x1800393c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800393ce  mov     edi, eax
0x1800393d0  test    eax, eax
0x1800393d2  js      short loc_180039415
0x1800393d4  lea     edx, [r14+r14]; cbInit
0x1800393d8  mov     rcx, rsi; pInit
0x1800393db  call    cs:__imp_SHCreateMemStream
0x1800393e1  mov     rbx, rax
0x1800393e4  test    rax, rax
0x1800393e7  jz      short loc_1800393F4
0x1800393e9  mov     rdx, rbp; struct Windows::Storage::Streams::IOutputStream *
0x1800393ec  mov     rcx, rax; struct IStream *
0x1800393ef  call    ?CopyStreamToOutputStream@@YAJPEAUIStream@@PEAUIOutputStream@Streams@Storage@Windows@@@Z; CopyStreamToOutputStream(IStream *,Windows::Storage::Streams::IOutputStream *)
0x1800393f4  mov     rcx, rsi; pv
0x1800393f7  call    cs:__imp_CoTaskMemFree
0x1800393fd  nop
0x1800393fe  test    rbx, rbx
0x180039401  jz      short loc_180039413
0x180039403  mov     rax, [rbx]
0x180039406  mov     rcx, rbx
0x180039409  mov     rax, [rax+10h]
0x18003940d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039412  nop
0x180039413  jmp     short loc_18003941C
0x180039415  mov     ecx, edi
0x180039417  call    ?EnsureStackSnapshot@?$DelegateTraits@$0?0@WRL@Microsoft@@SAXJ@Z; Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot(long)
0x18003941c  mov     eax, edi
0x18003941e  mov     rcx, [rsp+0E8h+var_38]
0x180039426  xor     rcx, rsp; StackCookie
0x180039429  call    __security_check_cookie
0x18003942e  mov     rbx, [rsp+0E8h+arg_10]
0x180039436  add     rsp, 0C0h
0x18003943d  pop     r15
0x18003943f  pop     r14
0x180039441  pop     rdi
0x180039442  pop     rsi
0x180039443  pop     rbp
0x180039444  retn
```
