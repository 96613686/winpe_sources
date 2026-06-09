# SerializeAsStringFailOverToPropVariant(IInspectable *,bool,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18004a1a0`
- end: `0x18004a325`
- name: `?SerializeAsStringFailOverToPropVariant@@YAJPEAUIInspectable@@_NPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct IInspectable *, bool, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180053930`

## callees

- `0x1800236bc`
- `0x180023f10`
- `0x18004a0d8`
- `0x18004a1a0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a2c5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18004a30c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18004a30c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004a2fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004a2fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004a2b6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004a2b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SerializeAsStringFailOverToPropVariant(
        IUnknown *a1,
        __int64 a2,
        struct Windows::Storage::Streams::IRandomAccessStream **a3)
{
  IUnknown *v5; // rsi
  int v6; // edi
  int v7; // eax
  HSTRING v8; // rcx
  int v9; // ebx
  unsigned int StringW; // eax
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  HGLOBAL hMem; // [rsp+70h] [rbp+40h] BYREF

  *a3 = 0;
  string = 0;
  if ( a1 )
  {
    hMem = 0;
    v7 = ((__int64 (__fastcall *)(IUnknown *, GUID *, HGLOBAL *))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
           &hMem);
    v6 = v7;
    if ( v7 < 0 )
    {
      if ( v7 == -2147467262 )
      {
        v5 = a1;
        v6 = 1;
      }
      else
      {
        v5 = 0;
      }
    }
    else
    {
      v5 = (IUnknown *)hMem;
      v6 = 7;
    }
  }
  else
  {
    v5 = 0;
    v6 = 0;
  }
  v8 = 0;
  string = 0;
  if ( v6 == 7 )
  {
    v9 = ((__int64 (__fastcall *)(IUnknown *, HSTRING *))v5->lpVtbl[6].AddRef)(v5, &string);
    v8 = string;
  }
  else if ( v6 < 0 )
  {
    v9 = v6;
  }
  else
  {
    v9 = -2147316576;
  }
  if ( v5 && ((v6 - 3) & 0xFFFFFFFB) == 0 )
  {
    ((void (__fastcall *)(IUnknown *))v5->lpVtbl->Release)(v5);
    v8 = string;
  }
  if ( v9 >= 0 )
  {
    *a3 = 0;
    hMem = 0;
    v9 = CreateGlobalFromString(v8, 0, &hMem);
    if ( v9 >= 0 )
      v9 = CreateRandomAccessStreamOnHGlobal(&hMem, 1, a3);
    GlobalFree(hMem);
    v8 = string;
  }
  if ( v8 )
    WindowsDeleteString(v8);
  if ( v9 < 0 )
  {
    v9 = SerializeAsPropVariant(a1, a3);
    if ( v9 < 0 )
    {
      string = 0;
      StringW = LoadStringW(&_ImageBase, 7u, (LPWSTR)&string, 0);
      if ( StringW )
        RoOriginateErrorW((unsigned int)v9, StringW, string);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004a1a0  mov     [rsp-28h+arg_18], rbx
0x18004a1a5  push    rbp
0x18004a1a6  push    rsi
0x18004a1a7  push    rdi
0x18004a1a8  push    r14
0x18004a1aa  push    r15
0x18004a1ac  mov     rbp, rsp
0x18004a1af  sub     rsp, 30h
0x18004a1b3  mov     r15, r8
0x18004a1b6  mov     r14, rcx
0x18004a1b9  mov     qword ptr [r8], 0
0x18004a1c0  mov     [rbp+string], 0
0x18004a1c8  test    rcx, rcx
0x18004a1cb  jnz     short loc_18004A1D6
0x18004a1cd  xor     esi, esi
0x18004a1cf  xor     edi, edi
0x18004a1d1  mov     [rbp+var_8], edi
0x18004a1d4  jmp     short loc_18004A222
0x18004a1d6  mov     [rbp+hMem], 0
0x18004a1de  mov     rax, [rcx]
0x18004a1e1  lea     r8, [rbp+hMem]
0x18004a1e5  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18004a1ec  mov     rax, [rax]
0x18004a1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1f4  mov     edi, eax
0x18004a1f6  test    eax, eax
0x18004a1f8  js      short loc_18004A205
0x18004a1fa  mov     rsi, [rbp+hMem]
0x18004a1fe  mov     edi, 7
0x18004a203  jmp     short loc_18004A1D1
0x18004a205  cmp     eax, 80004002h
0x18004a20a  jnz     short loc_18004A21D
0x18004a20c  mov     rsi, r14
0x18004a20f  mov     [rbp+var_10], r14
0x18004a213  mov     edi, 1
0x18004a218  mov     [rbp+var_8], edi
0x18004a21b  jmp     short loc_18004A226
0x18004a21d  xor     esi, esi
0x18004a21f  mov     [rbp+var_8], eax
0x18004a222  mov     [rbp+var_10], rsi
0x18004a226  xor     ecx, ecx
0x18004a228  mov     [rbp+string], rcx
0x18004a22c  cmp     edi, 7
0x18004a22f  jz      short loc_18004A240
0x18004a231  test    edi, edi
0x18004a233  js      short loc_18004A23C
0x18004a235  mov     ebx, 80028CA0h
0x18004a23a  jmp     short loc_18004A25C
0x18004a23c  mov     ebx, edi
0x18004a23e  jmp     short loc_18004A25C
0x18004a240  mov     rax, [rsi]
0x18004a243  lea     rdx, [rbp+string]
0x18004a247  mov     rcx, rsi
0x18004a24a  mov     rax, [rax+98h]
0x18004a251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a256  mov     ebx, eax
0x18004a258  mov     rcx, [rbp+string]
0x18004a25c  test    rsi, rsi
0x18004a25f  jz      short loc_18004A27E
0x18004a261  lea     eax, [rdi-3]
0x18004a264  test    eax, 0FFFFFFFBh
0x18004a269  jnz     short loc_18004A27E
0x18004a26b  mov     rax, [rsi]
0x18004a26e  mov     rcx, rsi
0x18004a271  mov     rax, [rax+10h]
0x18004a275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a27a  mov     rcx, [rbp+string]; string
0x18004a27e  test    ebx, ebx
0x18004a280  js      short loc_18004A2C0
0x18004a282  mov     qword ptr [r15], 0
0x18004a289  mov     [rbp+hMem], 0
0x18004a291  lea     r8, [rbp+hMem]; void **
0x18004a295  xor     edx, edx; bool
0x18004a297  call    ?CreateGlobalFromString@@YAJPEAUHSTRING__@@_NPEAPEAX@Z; CreateGlobalFromString(HSTRING__ *,bool,void * *)
0x18004a29c  mov     ebx, eax
0x18004a29e  test    eax, eax
0x18004a2a0  js      short loc_18004A2B2
0x18004a2a2  mov     r8, r15
0x18004a2a5  mov     dl, 1
0x18004a2a7  lea     rcx, [rbp+hMem]
0x18004a2ab  call    ?CreateRandomAccessStreamOnHGlobal@@YAJ$$QEAPEAX_NPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CreateRandomAccessStreamOnHGlobal(void * &&,bool,Windows::Storage::Streams::IRandomAccessStream * *)
0x18004a2b0  mov     ebx, eax
0x18004a2b2  mov     rcx, [rbp+hMem]; hMem
0x18004a2b6  call    cs:__imp_GlobalFree
0x18004a2bc  mov     rcx, [rbp+string]; string
0x18004a2c0  test    rcx, rcx
0x18004a2c3  jz      short loc_18004A2CB
0x18004a2c5  call    cs:__imp_WindowsDeleteString
0x18004a2cb  test    ebx, ebx
0x18004a2cd  jns     short loc_18004A312
0x18004a2cf  mov     rdx, r15; struct Windows::Storage::Streams::IRandomAccessStream **
0x18004a2d2  mov     rcx, r14; struct IInspectable *
0x18004a2d5  call    ?SerializeAsPropVariant@@YAJPEAUIInspectable@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; SerializeAsPropVariant(IInspectable *,Windows::Storage::Streams::IRandomAccessStream * *)
0x18004a2da  mov     ebx, eax
0x18004a2dc  test    eax, eax
0x18004a2de  jns     short loc_18004A312
0x18004a2e0  mov     [rbp+string], 0
0x18004a2e8  xor     r9d, r9d; cchBufferMax
0x18004a2eb  lea     r8, [rbp+string]; lpBuffer
0x18004a2ef  lea     edx, [r9+7]; uID
0x18004a2f3  lea     rcx, __ImageBase; hInstance
0x18004a2fa  call    cs:__imp_LoadStringW
0x18004a300  test    eax, eax
0x18004a302  jz      short loc_18004A312
0x18004a304  mov     r8, [rbp+string]
0x18004a308  mov     edx, eax
0x18004a30a  mov     ecx, ebx
0x18004a30c  call    cs:__imp_RoOriginateErrorW
0x18004a312  mov     eax, ebx
0x18004a314  mov     rbx, [rsp+30h+arg_18]
0x18004a319  add     rsp, 30h
0x18004a31d  pop     r15
0x18004a31f  pop     r14
0x18004a321  pop     rdi
0x18004a322  pop     rsi
0x18004a323  pop     rbp
0x18004a324  retn
```
