# CMarshaledInterface::CMarshalStream::~CMarshalStream(void)

- ea: `0x18000d188`
- end: `0x18000d223`
- name: `??1CMarshalStream@CMarshaledInterface@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CMarshaledInterface::CMarshalStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d940`

## callees

- `0x1800043a4`
- `0x18000d188`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1a9`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18000d1f0`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18000d1f0`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000d1b7`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000d1b7`

## pseudocode

```c
void __fastcall CMarshaledInterface::CMarshalStream::~CMarshalStream(CMarshaledInterface::CMarshalStream *this)
{
  LPSTREAM *v1; // rbx
  bool v3; // zf
  IStream *v4; // rcx
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v1 = (LPSTREAM *)((char *)this + 16);
  v3 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &CMarshaledInterface::CMarshalStream::`vftable';
  if ( !v3 )
  {
    if ( *((_DWORD *)this + 10) == GetCurrentThreadId() )
    {
      CoReleaseMarshalData(*v1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v1);
    }
    else
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v4 = *v1;
      *v1 = 0;
      CoGetInterfaceAndReleaseStream(v4, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v1);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000d188  mov     [rsp+arg_8], rbx
0x18000d18d  push    rdi
0x18000d18e  sub     rsp, 20h
0x18000d192  lea     rbx, [rcx+10h]
0x18000d196  mov     rdi, rcx
0x18000d199  cmp     qword ptr [rbx], 0
0x18000d19d  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x18000d1a4  mov     [rcx], rax
0x18000d1a7  jz      short loc_18000D200
0x18000d1a9  call    cs:__imp_GetCurrentThreadId
0x18000d1af  cmp     [rdi+28h], eax
0x18000d1b2  jnz     short loc_18000D1C7
0x18000d1b4  mov     rcx, [rbx]; pStm
0x18000d1b7  call    cs:__imp_CoReleaseMarshalData
0x18000d1bd  mov     rcx, rbx
0x18000d1c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d1c5  jmp     short loc_18000D200
0x18000d1c7  lea     rcx, [rsp+28h+ppv]
0x18000d1cc  mov     [rsp+28h+ppv], 0
0x18000d1d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d1da  mov     rcx, [rbx]; pStm
0x18000d1dd  lea     r8, [rsp+28h+ppv]; ppv
0x18000d1e2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x18000d1e9  mov     qword ptr [rbx], 0
0x18000d1f0  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18000d1f6  lea     rcx, [rsp+28h+ppv]
0x18000d1fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d200  lea     rcx, [rdi+20h]
0x18000d204  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d209  mov     rcx, rbx
0x18000d20c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d211  mov     rbx, [rsp+28h+arg_8]
0x18000d216  mov     dword ptr [rdi+0Ch], 0C0000001h
0x18000d21d  add     rsp, 20h
0x18000d221  pop     rdi
0x18000d222  retn
```
