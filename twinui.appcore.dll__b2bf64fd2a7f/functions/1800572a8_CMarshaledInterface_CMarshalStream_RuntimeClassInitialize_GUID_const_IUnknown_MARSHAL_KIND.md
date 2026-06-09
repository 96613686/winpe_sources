# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x1800572a8`
- end: `0x180057352`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180047f94`

## callees

- `0x180003d24`
- `0x1800572a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800572bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800572bd`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18005733f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18005733f`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800572f3`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800572f3`

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
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
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
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 16);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x1800572a8  push    rbx
0x1800572aa  push    rbp
0x1800572ab  push    rsi
0x1800572ac  push    rdi
0x1800572ad  sub     rsp, 38h
0x1800572b1  mov     ebx, r9d
0x1800572b4  mov     rsi, r8
0x1800572b7  mov     rbp, rdx
0x1800572ba  mov     rdi, rcx
0x1800572bd  call    cs:__imp_GetCurrentThreadId
0x1800572c3  mov     [rdi+18h], ebx
0x1800572c6  mov     [rdi+28h], eax
0x1800572c9  cmp     ebx, 2
0x1800572cc  jnz     short loc_18005732C
0x1800572ce  xor     eax, eax
0x1800572d0  xor     ebx, ebx
0x1800572d2  mov     [rsp+58h+arg_0], rax
0x1800572d7  test    rsi, rsi
0x1800572da  jz      short loc_180057300
0x1800572dc  lea     rcx, [rsp+58h+arg_0]
0x1800572e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800572e6  lea     r9, [rsp+58h+arg_0]
0x1800572eb  mov     r8, rsi
0x1800572ee  mov     rdx, rbp
0x1800572f1  xor     ecx, ecx
0x1800572f3  call    cs:__imp_RoGetAgileReference
0x1800572f9  mov     ebx, eax
0x1800572fb  mov     rax, [rsp+58h+arg_0]
0x180057300  mov     rcx, [rdi+20h]
0x180057304  mov     [rsp+58h+var_38], rcx
0x180057309  lea     rcx, [rsp+58h+var_38]
0x18005730e  mov     [rsp+58h+arg_0], 0
0x180057317  mov     [rdi+20h], rax
0x18005731b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180057320  lea     rcx, [rsp+58h+arg_0]
0x180057325  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005732a  jmp     short loc_180057347
0x18005732c  lea     rcx, [rdi+10h]
0x180057330  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180057335  lea     r8, [rdi+10h]; ppStm
0x180057339  mov     rdx, rsi; pUnk
0x18005733c  mov     rcx, rbp; riid
0x18005733f  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180057345  mov     ebx, eax
0x180057347  mov     eax, ebx
0x180057349  add     rsp, 38h
0x18005734d  pop     rdi
0x18005734e  pop     rsi
0x18005734f  pop     rbp
0x180057350  pop     rbx
0x180057351  retn
```
