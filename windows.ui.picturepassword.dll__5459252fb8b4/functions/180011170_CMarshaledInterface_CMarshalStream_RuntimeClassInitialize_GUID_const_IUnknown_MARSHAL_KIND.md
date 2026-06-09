# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x180011170`
- end: `0x18001121a`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, const IID *, IUnknown *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c9dc`

## callees

- `0x1800043a4`
- `0x180011170`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011185`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180011207`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180011207`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800111bb`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800111bb`

## pseudocode

```c
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        __int64 a1,
        const IID *a2,
        IUnknown *a3,
        int a4)
{
  DWORD CurrentThreadId; // eax
  __int64 v9; // rax
  unsigned int AgileReference; // ebx
  __int64 v12[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 24) = a4;
  *(_DWORD *)(a1 + 40) = CurrentThreadId;
  if ( a4 == 2 )
  {
    v9 = 0;
    AgileReference = 0;
    v13 = 0;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      AgileReference = RoGetAgileReference(0, a2, a3, &v13);
      v9 = v13;
    }
    v12[0] = *(_QWORD *)(a1 + 32);
    v13 = 0;
    *(_QWORD *)(a1 + 32) = v9;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)(a1 + 16));
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x180011170  push    rbx
0x180011172  push    rbp
0x180011173  push    rsi
0x180011174  push    rdi
0x180011175  sub     rsp, 38h
0x180011179  mov     ebx, r9d
0x18001117c  mov     rsi, r8
0x18001117f  mov     rbp, rdx
0x180011182  mov     rdi, rcx
0x180011185  call    cs:__imp_GetCurrentThreadId
0x18001118b  mov     [rdi+18h], ebx
0x18001118e  mov     [rdi+28h], eax
0x180011191  cmp     ebx, 2
0x180011194  jnz     short loc_1800111F4
0x180011196  xor     eax, eax
0x180011198  xor     ebx, ebx
0x18001119a  mov     [rsp+58h+arg_0], rax
0x18001119f  test    rsi, rsi
0x1800111a2  jz      short loc_1800111C8
0x1800111a4  lea     rcx, [rsp+58h+arg_0]
0x1800111a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800111ae  lea     r9, [rsp+58h+arg_0]
0x1800111b3  mov     r8, rsi
0x1800111b6  mov     rdx, rbp
0x1800111b9  xor     ecx, ecx
0x1800111bb  call    cs:__imp_RoGetAgileReference
0x1800111c1  mov     ebx, eax
0x1800111c3  mov     rax, [rsp+58h+arg_0]
0x1800111c8  mov     rcx, [rdi+20h]
0x1800111cc  mov     [rsp+58h+var_38], rcx
0x1800111d1  lea     rcx, [rsp+58h+var_38]
0x1800111d6  mov     [rsp+58h+arg_0], 0
0x1800111df  mov     [rdi+20h], rax
0x1800111e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800111e8  lea     rcx, [rsp+58h+arg_0]
0x1800111ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800111f2  jmp     short loc_18001120F
0x1800111f4  lea     rcx, [rdi+10h]
0x1800111f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800111fd  lea     r8, [rdi+10h]; ppStm
0x180011201  mov     rdx, rsi; pUnk
0x180011204  mov     rcx, rbp; riid
0x180011207  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18001120d  mov     ebx, eax
0x18001120f  mov     eax, ebx
0x180011211  add     rsp, 38h
0x180011215  pop     rdi
0x180011216  pop     rsi
0x180011217  pop     rbp
0x180011218  pop     rbx
0x180011219  retn
```
